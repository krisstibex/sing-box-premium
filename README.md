# 自动构建sing box 内核
* 支持 proxy provider
* full tag
* 来自于[sing-box下游仓库](https://github.com/CHIZI-0618/sing-box)
* 手动构建:
```
CGO_ENABLED=0 go build -v -trimpath -ldflags "-checklinkname=0 -X 'github.com/sagernet/sing-box/constant.Version=$(ccurl -s https://api.github.com/repos/SagerNet/sing-box/releases | grep '"tag_name"' | head -n 1 | cut -d ":" -f2 | sed 's/[",v ]//g')' -s -w -buildid=" -tags "with_quic with_grpc with_dhcp with_wireguard with_ech with_utls with_reality_server with_acme with_clash_api with_v2ray_api with_gvisor with_tailscale" ./cmd/sing-box
```

## 使用说明
* [官方文档](https://sing-box.sagernet.org/zh/configuration/)
* [proxy-provider](https://github.com/CHIZI-0618/sing-box/blob/dev-next/docs/configuration/provider/index.zh.md)
