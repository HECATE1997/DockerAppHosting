FROM mcr.microsoft.com/dotnet/sdk:9.0 AS build
WORKDIR /App

# Copy everything
COPY ./TodoApi/TodoApi.csproj ./TodoApi.csproj
# Restore as distinct layers
RUN dotnet restore

COPY . ./
WORKDIR /app/TodoApi


# Build and publish a release
RUN dotnet publish -o out

# RUN dotnet publish -c Release -o /app/out

# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:9.0
WORKDIR /App
COPY --from=build /App/out .
EXPOSE 80
ENTRYPOINT ["dotnet", "TodoApi.dll"]