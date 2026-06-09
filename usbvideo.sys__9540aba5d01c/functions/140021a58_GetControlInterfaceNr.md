# GetControlInterfaceNr

- ea: `0x140021a58`
- end: `0x140021a9d`
- name: `GetControlInterfaceNr`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14002e900`
- `0x14002e9e0`

## callees

- `0x140021a58`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140021a7f`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140021a7f`

## pseudocode

```c
char __fastcall GetControlInterfaceNr(__int64 a1)
{
  PUSB_INTERFACE_DESCRIPTOR v1; // rax

  v1 = USBD_ParseConfigurationDescriptorEx(
         *(PUSB_CONFIGURATION_DESCRIPTOR *)(a1 + 32),
         *(PVOID *)(a1 + 32),
         -1,
         -1,
         14,
         1,
         -1);
  if ( v1 )
    return v1->bInterfaceNumber;
  else
    return -1;
}

```

## disassembly

```asm
0x140021a58  sub     rsp, 48h
0x140021a5c  mov     rcx, [rcx+20h]; ConfigurationDescriptor
0x140021a60  or      r8d, 0FFFFFFFFh; InterfaceNumber
0x140021a64  mov     [rsp+48h+InterfaceProtocol], r8d; InterfaceProtocol
0x140021a69  mov     r9d, r8d; AlternateSetting
0x140021a6c  mov     [rsp+48h+InterfaceSubClass], 1; InterfaceSubClass
0x140021a74  mov     rdx, rcx; StartPosition
0x140021a77  mov     [rsp+48h+InterfaceClass], 0Eh; InterfaceClass
0x140021a7f  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140021a86  nop     dword ptr [rax+rax+00h]
0x140021a8b  test    rax, rax
0x140021a8e  jnz     short loc_140021A94
0x140021a90  mov     al, 0FFh
0x140021a92  jmp     short loc_140021A97
0x140021a94  mov     al, [rax+2]
0x140021a97  add     rsp, 48h
0x140021a9b  retn
```
