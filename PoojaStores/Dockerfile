FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app
COPY *.csproj /app
RUN dotnet restore
COPY . /app
RUN dotnet publish --no-restore -o app
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app
COPY --from=build /app/app .
ENTRYPOINT ["dotnet", "--urls", "http://0.0.0.0:5000"]
