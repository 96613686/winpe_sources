# TdxPnpPowerComplete

- ea: `0x140011990`
- end: `0x1400119c7`
- name: `TdxPnpPowerComplete`
- size: `55`
- prototype: `void __stdcall(PNET_PNP_EVENT NetEvent, NTSTATUS ProviderStatus)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140018590`

## pseudocode

```c
void __fastcall TdxPnpPowerComplete(PNET_PNP_EVENT NetEvent, NTSTATUS ProviderStatus)
{
  _DWORD v2[2]; // [rsp+20h] [rbp-28h] BYREF
  PNET_PNP_EVENT v3; // [rsp+28h] [rbp-20h]
  ULONG_PTR v4; // [rsp+30h] [rbp-18h]

  v3 = NetEvent;
  v2[1] = 0;
  v4 = NetEvent->TransportReserved[3];
  v2[0] = ProviderStatus;
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)&WPP_MAIN_CB.DeviceType + 8LL))(v2);
}

```

## disassembly

```asm
0x140011990  sub     rsp, 48h
0x140011994  xor     eax, eax
0x140011996  mov     [rsp+48h+var_20], rcx
0x14001199b  mov     [rsp+48h+var_24], eax
0x14001199f  mov     rax, [rcx+50h]
0x1400119a3  lea     rcx, [rsp+48h+var_28]
0x1400119a8  mov     [rsp+48h+var_18], rax
0x1400119ad  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceType
0x1400119b4  mov     [rsp+48h+var_28], edx
0x1400119b8  mov     rax, [rax+8]
0x1400119bc  call    _guard_dispatch_icall
0x1400119c1  add     rsp, 48h
0x1400119c5  retn
```
