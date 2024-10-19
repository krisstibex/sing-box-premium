# 自动构建sing box 内核
* 支持 proxy provider
* full tag
* 来自于[sing-box下游仓库](https://github.com/qjebbs/sing-box)
* 构建命令:
```
CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -v -trimpath -ldflags "-checklinkname=0 -X 'github.com/sagernet/sing-box/constant.Version=$(curl -s https://api.github.com/repos/SagerNet/sing-box/releases/latest | grep tag_name | cut -d ':' -f2 | sed 's/[\", ]//g;s/v//')' -s -w -buildid=" -tags "with_quic with_grpc with_dhcp with_wireguard with_ech with_utls with_reality_server with_acme with_clash_api with_v2ray_api with_gvisor" ./cmd/sing-box
```

