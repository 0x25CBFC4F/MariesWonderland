FROM mcr.microsoft.com/dotnet/sdk:9.0 AS build
WORKDIR /app
COPY . /app/
RUN dotnet build -c Release

FROM mcr.microsoft.com/dotnet/aspnet:9.0 AS release
WORKDIR /app
COPY --from=build /app/bin/Release/net9.0/ /app/
RUN chmod +x /app/MariesWonderland
ENTRYPOINT /app/MariesWonderland
