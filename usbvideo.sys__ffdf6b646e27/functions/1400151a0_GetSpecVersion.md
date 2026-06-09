# GetSpecVersion

- ea: `0x1400151a0`
- end: `0x14001522d`
- name: `GetSpecVersion`
- size: `141`
- prototype: `__int64 __fastcall(PVOID StartPosition)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015e60`

## callees

- `0x14000d790`
- `0x1400151a0`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400151d3`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x1400151d3`

## pseudocode

```c
__int64 __fastcall GetSpecVersion(struct _USB_CONFIGURATION_DESCRIPTOR *StartPosition)
{
  unsigned __int16 *p_bLength; // rdi
  unsigned __int16 v2; // bx
  struct _USB_CONFIGURATION_DESCRIPTOR *i; // rdx
  PUSB_INTERFACE_DESCRIPTOR v4; // rax
  PUSB_COMMON_DESCRIPTOR v5; // rax

  p_bLength = (unsigned __int16 *)&StartPosition->bLength;
  v2 = 256;
  for ( i = StartPosition; ; i = (struct _USB_CONFIGURATION_DESCRIPTOR *)(&v4->bLength + v4->bLength) )
  {
    v4 = USBD_ParseConfigurationDescriptorEx(StartPosition, i, -1, -1, 14, -1, -1);
    if ( !v4 )
      break;
    StartPosition = (struct _USB_CONFIGURATION_DESCRIPTOR *)p_bLength;
    if ( v4->bInterfaceSubClass == 1 )
    {
      v5 = USBParseDescriptorWrapper(p_bLength, p_bLength[1], v4, 36, 0xCu);
      if ( v5 )
        return *(unsigned __int16 *)&v5[1].bDescriptorType;
      return v2;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400151a0  mov     [rsp+arg_0], rbx
0x1400151a5  mov     [rsp+arg_8], rsi
0x1400151aa  push    rdi
0x1400151ab  sub     rsp, 40h
0x1400151af  mov     rdi, rcx
0x1400151b2  mov     ebx, 100h
0x1400151b7  or      esi, 0FFFFFFFFh
0x1400151ba  mov     rdx, rcx; StartPosition
0x1400151bd  mov     [rsp+48h+InterfaceProtocol], esi; InterfaceProtocol
0x1400151c1  mov     r9d, esi; AlternateSetting
0x1400151c4  mov     [rsp+48h+InterfaceSubClass], esi; InterfaceSubClass
0x1400151c8  mov     r8d, esi; InterfaceNumber
0x1400151cb  mov     [rsp+48h+InterfaceClass], 0Eh; InterfaceClass
0x1400151d3  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x1400151da  nop     dword ptr [rax+rax+00h]
0x1400151df  test    rax, rax
0x1400151e2  jz      short loc_140015219
0x1400151e4  cmp     byte ptr [rax+6], 1
0x1400151e8  mov     rcx, rdi
0x1400151eb  jz      short loc_1400151F5
0x1400151ed  movzx   edx, byte ptr [rax]
0x1400151f0  add     rdx, rax
0x1400151f3  jmp     short loc_1400151BD
0x1400151f5  movzx   edx, word ptr [rdi+2]
0x1400151f9  mov     r9d, 24h ; '$'
0x1400151ff  mov     r8, rax
0x140015202  mov     qword ptr [rsp+48h+InterfaceClass], 0Ch
0x14001520b  call    USBParseDescriptorWrapper
0x140015210  test    rax, rax
0x140015213  jz      short loc_140015219
0x140015215  movzx   ebx, word ptr [rax+3]
0x140015219  mov     rsi, [rsp+48h+arg_8]
0x14001521e  movzx   eax, bx
0x140015221  mov     rbx, [rsp+48h+arg_0]
0x140015226  add     rsp, 40h
0x14001522a  pop     rdi
0x14001522b  retn
```
