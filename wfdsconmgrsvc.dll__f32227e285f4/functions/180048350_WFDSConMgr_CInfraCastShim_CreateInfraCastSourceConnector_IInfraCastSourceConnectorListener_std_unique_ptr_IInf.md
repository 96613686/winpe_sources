# WFDSConMgr::CInfraCastShim::CreateInfraCastSourceConnector(IInfraCastSourceConnectorListener *,std::unique_ptr<IInfraCastSourceConnector,std::default_delete<IInfraCastSourceConnector>> &)

- ea: `0x180048350`
- end: `0x18004839c`
- name: `?CreateInfraCastSourceConnector@CInfraCastShim@WFDSConMgr@@UEBAJPEAVIInfraCastSourceConnectorListener@@AEAV?$unique_ptr@VIInfraCastSourceConnector@@U?$default_delete@VIInfraCastSourceConnector@@@std@@@std@@@Z`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800051f8`
- `0x180048350`

## import_xrefs

- `WiFiDisplay!CreateInfraCastSourceConnector` at `0x18004836e`
- `WiFiDisplay!CreateInfraCastSourceConnector` at `0x18004836e`

## pseudocode

```c
__int64 __fastcall WFDSConMgr::CInfraCastShim::CreateInfraCastSourceConnector(
        __int64 a1,
        struct IInfraCastSourceConnectorListener *a2,
        __int64 *a3)
{
  int v4; // edi
  __int64 v5; // rdx
  struct IInfraCastSourceConnector *v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v4 = CreateInfraCastSourceConnector(a2, &v7);
  if ( v4 >= 0 )
  {
    v5 = *a3;
    *a3 = (__int64)v7;
    if ( v5 )
      std::default_delete<WFDSConMgr::RPC::IServiceLifetimeToken>::operator()();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180048350  mov     [rsp+arg_0], rbx
0x180048355  push    rdi
0x180048356  sub     rsp, 20h
0x18004835a  mov     rcx, rdx
0x18004835d  mov     [rsp+28h+arg_18], 0
0x180048366  lea     rdx, [rsp+28h+arg_18]
0x18004836b  mov     rbx, r8
0x18004836e  call    cs:__imp_?CreateInfraCastSourceConnector@@YAJPEAVIInfraCastSourceConnectorListener@@PEAPEAVIInfraCastSourceConnector@@@Z; CreateInfraCastSourceConnector(IInfraCastSourceConnectorListener *,IInfraCastSourceConnector * *)
0x180048374  mov     edi, eax
0x180048376  test    eax, eax
0x180048378  js      short loc_18004838F
0x18004837a  mov     rdx, [rbx]
0x18004837d  mov     rcx, [rsp+28h+arg_18]
0x180048382  mov     [rbx], rcx
0x180048385  test    rdx, rdx
0x180048388  jz      short loc_18004838F
0x18004838a  call    ??R?$default_delete@VIServiceLifetimeToken@RPC@WFDSConMgr@@@std@@QEBAXPEAVIServiceLifetimeToken@RPC@WFDSConMgr@@@Z; std::default_delete<WFDSConMgr::RPC::IServiceLifetimeToken>::operator()(WFDSConMgr::RPC::IServiceLifetimeToken *)
0x18004838f  mov     rbx, [rsp+28h+arg_0]
0x180048394  mov     eax, edi
0x180048396  add     rsp, 20h
0x18004839a  pop     rdi
0x18004839b  retn
```
