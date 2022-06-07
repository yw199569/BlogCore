#这种模式是先dotnet build后，然后再把dll进行构建镜像。
#如果你想把这两步合在一起，可以看.sln根目录下的那个dockerfile。

#FROM swr.cn-south-1.myhuaweicloud.com/mcr/aspnet:5.0-alpine
#FROM mcr.microsoft.com/dotnet/core/aspnet:5.0-buster-slim
FROM mcr.microsoft.com/dotnet/aspnet:6.0-bullseye-slim AS base
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' >/etc/timezone
WORKDIR /app
COPY . . 
EXPOSE 9291 
ENTRYPOINT ["dotnet", "Blog.Core.Api.dll","-b","0.0.0.0"]