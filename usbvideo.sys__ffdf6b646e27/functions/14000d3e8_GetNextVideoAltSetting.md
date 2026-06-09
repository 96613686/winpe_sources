# GetNextVideoAltSetting

- ea: `0x14000d3e8`
- end: `0x14000d42b`
- name: `GetNextVideoAltSetting`
- size: `67`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000cb20`
- `0x14000d2d0`
- `0x14000d434`
- `0x140015234`
- `0x140016cd4`
- `0x140021bc8`

## callees

- `0x14000d3e8`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000d415`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000d415`

## pseudocode

```c
PUSB_INTERFACE_DESCRIPTOR __fastcall GetNextVideoAltSetting(
        struct _USB_CONFIGURATION_DESCRIPTOR *a1,
        unsigned __int8 *a2)
{
  if ( a2 )
    return USBD_ParseConfigurationDescriptorEx(a1, &a2[*a2], a2[2], -1, 14, -1, -1);
  else
    return 0;
}

```

## disassembly

```asm
0x14000d3e8  sub     rsp, 48h
0x14000d3ec  mov     rax, rdx
0x14000d3ef  test    rdx, rdx
0x14000d3f2  jz      short loc_14000D427
0x14000d3f4  movzx   r8d, byte ptr [rdx+2]; InterfaceNumber
0x14000d3f9  or      r9d, 0FFFFFFFFh; AlternateSetting
0x14000d3fd  movzx   edx, byte ptr [rdx]
0x14000d400  mov     [rsp+48h+InterfaceProtocol], r9d; InterfaceProtocol
0x14000d405  add     rdx, rax; StartPosition
0x14000d408  mov     [rsp+48h+InterfaceSubClass], r9d; InterfaceSubClass
0x14000d40d  mov     [rsp+48h+InterfaceClass], 0Eh; InterfaceClass
0x14000d415  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x14000d41c  nop     dword ptr [rax+rax+00h]
0x14000d421  add     rsp, 48h
0x14000d425  retn
0x14000d427  xor     eax, eax
0x14000d429  jmp     short loc_14000D421
```
