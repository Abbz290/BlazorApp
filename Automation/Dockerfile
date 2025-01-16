# Build stage
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app
COPY . ./
RUN dotnet restore
RUN dotnet publish -c Release -o /out

# Runtime stage
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /app

# Copy the published app from the build stage
COPY --from=build /out .

# Expose port 8080 to allow communication
EXPOSE 8080

# Set the entry point to run your Blazor Server app
ENTRYPOINT ["dotnet", "Automation.dll"]
