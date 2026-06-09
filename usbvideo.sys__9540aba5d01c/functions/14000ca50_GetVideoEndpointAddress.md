# GetVideoEndpointAddress

- ea: `0x14000ca50`
- end: `0x14000cb1a`
- name: `GetVideoEndpointAddress`
- size: `202`
- prototype: `__int64 __fastcall(PVOID StartPosition)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c95c`
- `0x14000c9e4`
- `0x14000cbf0`
- `0x1400171d0`
- `0x140017e4c`
- `0x140017ed0`

## callees

- `0x140004bac`
- `0x14000ca50`
- `0x14000d790`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000ca87`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000ca87`

## pseudocode

```c
__int64 __fastcall GetVideoEndpointAddress(
        struct _USB_CONFIGURATION_DESCRIPTOR *StartPosition,
        unsigned __int8 *a2,
        UCHAR *a3)
{
  PUSB_INTERFACE_DESCRIPTOR v6; // rax
  PUSB_COMMON_DESCRIPTOR v7; // rax

  v6 = USBD_ParseConfigurationDescriptorEx(StartPosition, StartPosition, a2[2], -1, 14, 2, -1);
  if ( v6
    && (v7 = USBParseDescriptorWrapper(StartPosition, StartPosition->wTotalLength, &v6->bLength + *a2, 36, 3u)) != 0
    && (v7[1].bLength == 1 || v7[1].bLength == 2) )
  {
    *a3 = v7[3].bLength;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x14000ca50  mov     rax, rsp
0x14000ca53  mov     [rax+8], rbx
0x14000ca57  mov     [rax+10h], rsi
0x14000ca5b  push    rdi
0x14000ca5c  sub     rsp, 40h
0x14000ca60  or      r9d, 0FFFFFFFFh; AlternateSetting
0x14000ca64  mov     rbx, r8
0x14000ca67  movzx   r8d, byte ptr [rdx+2]; InterfaceNumber
0x14000ca6c  mov     rsi, rdx
0x14000ca6f  mov     [rax-18h], r9d
0x14000ca73  mov     rdx, rcx; StartPosition
0x14000ca76  mov     dword ptr [rax-20h], 2
0x14000ca7d  mov     rdi, rcx
0x14000ca80  mov     dword ptr [rax-28h], 0Eh
0x14000ca87  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x14000ca8e  nop     dword ptr [rax+rax+00h]
0x14000ca93  test    rax, rax
0x14000ca96  jz      short loc_14000CAD6
0x14000ca98  movzx   r8d, byte ptr [rsi]
0x14000ca9c  mov     r9d, 24h ; '$'
0x14000caa2  movzx   edx, word ptr [rdi+2]
0x14000caa6  add     r8, rax
0x14000caa9  mov     rcx, rdi
0x14000caac  mov     [rsp+48h+var_28], 3
0x14000cab5  call    USBParseDescriptorWrapper
0x14000caba  test    rax, rax
0x14000cabd  jz      short loc_14000CAD6
0x14000cabf  movzx   edx, byte ptr [rax+2]
0x14000cac3  sub     edx, 1
0x14000cac6  jz      short loc_14000CACD
0x14000cac8  cmp     edx, 1
0x14000cacb  jnz     short loc_14000CAD6
0x14000cacd  mov     al, [rax+6]
0x14000cad0  mov     [rbx], al
0x14000cad2  xor     eax, eax
0x14000cad4  jmp     short loc_14000CB09
0x14000cad6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cadd  lea     rax, WPP_GLOBAL_Control
0x14000cae4  cmp     rcx, rax
0x14000cae7  jz      short loc_14000CB04
0x14000cae9  cmp     byte ptr [rcx+29h], 2
0x14000caed  jb      short loc_14000CB04
0x14000caef  mov     rcx, [rcx+18h]
0x14000caf3  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000cafa  mov     edx, 0Eh
0x14000caff  call    WPP_SF_
0x14000cb04  mov     eax, 0C0000001h
0x14000cb09  mov     rbx, [rsp+48h+arg_0]
0x14000cb0e  mov     rsi, [rsp+48h+arg_8]
0x14000cb13  add     rsp, 40h
0x14000cb17  pop     rdi
0x14000cb18  retn
```
