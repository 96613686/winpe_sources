# TdiRegisterAddressChangeHandler

- ea: `0x140005380`
- end: `0x1400053b8`
- name: `TdiRegisterAddressChangeHandler`
- size: `56`
- prototype: `NTSTATUS __stdcall(TDI_ADD_ADDRESS_HANDLER AddHandler, TDI_DEL_ADDRESS_HANDLER DeleteHandler, HANDLE *BindingHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002630`

## pseudocode

```c
NTSTATUS __stdcall TdiRegisterAddressChangeHandler(
        TDI_ADD_ADDRESS_HANDLER AddHandler,
        TDI_DEL_ADDRESS_HANDLER DeleteHandler,
        HANDLE *BindingHandle)
{
  TDI_CLIENT_INTERFACE_INFO v4; // [rsp+20h] [rbp-48h] BYREF

  v4.DelAddressHandlerV2 = (TDI_DEL_ADDRESS_HANDLER_V2)DeleteHandler;
  v4.AddAddressHandlerV2 = (TDI_ADD_ADDRESS_HANDLER_V2)AddHandler;
  memset(&v4, 0, 40);
  v4.TdiVersion = 1;
  return TdiRegisterPnPHandlers(&v4, 0x38u, BindingHandle);
}

```

## disassembly

```asm
0x140005380  mov     rax, rsp
0x140005383  sub     rsp, 68h
0x140005387  xorps   xmm0, xmm0
0x14000538a  mov     [rax-18h], rdx
0x14000538e  movups  xmmword ptr [rax-28h], xmm0
0x140005392  mov     [rax-20h], rcx
0x140005396  mov     edx, 38h ; '8'; InterfaceInfoSize
0x14000539b  movups  xmmword ptr [rax-48h], xmm0
0x14000539f  lea     rcx, [rax-48h]; ClientInterfaceInfo
0x1400053a3  mov     word ptr [rax-48h], 1
0x1400053a9  movups  xmmword ptr [rax-38h], xmm0
0x1400053ad  call    TdiRegisterPnPHandlers
0x1400053b2  add     rsp, 68h
0x1400053b6  retn
```
