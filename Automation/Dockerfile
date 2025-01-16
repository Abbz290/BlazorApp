# Build stage
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app
COPY . ./
RUN dotnet restore
RUN dotnet publish -c Release -o /out

# Runtime stage
FROM nginx:alpine
WORKDIR /usr/share/nginx/html

# Copy the published app from the build stage
COPY --from=build /out/wwwroot .
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
