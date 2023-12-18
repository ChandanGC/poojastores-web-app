FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
WORKDIR /app
COPY . /app
RUN dotnet build -o /app 
FROM mcr.microsoft.com/dotnet/aspnet:3.1
WORKDIR /app
COPY --from=build /app/app .
ENTRYPOINT ["dotnet", "run", "--urls", "http://0.0.0.0:5000"]
