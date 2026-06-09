# GetStatusInterruptEndpointIndex

- ea: `0x140021c54`
- end: `0x140021dcf`
- name: `GetStatusInterruptEndpointIndex`
- size: `379`
- prototype: `__int64 __fastcall(PVOID StartPosition)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140020a94`

## callees

- `0x140004bac`
- `0x14000d790`
- `0x14001b118`
- `0x140021c54`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140021c86`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x140021c86`

## pseudocode

```c
__int64 __fastcall GetStatusInterruptEndpointIndex(
        struct _USB_CONFIGURATION_DESCRIPTOR *StartPosition,
        _DWORD *a2,
        unsigned int *a3)
{
  PUSB_INTERFACE_DESCRIPTOR v6; // rax
  unsigned int v7; // ebx
  PUSB_COMMON_DESCRIPTOR v8; // rax
  PUSB_COMMON_DESCRIPTOR v9; // rax
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // edi
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx

  v6 = USBD_ParseConfigurationDescriptorEx(StartPosition, StartPosition, -1, -1, 14, 1, -1);
  if ( !v6 )
    return (unsigned int)-1073741823;
  if ( !v6->bNumEndpoints )
    return (unsigned int)-1073741823;
  v8 = USBParseDescriptorWrapper(StartPosition, StartPosition->wTotalLength, &v6->bLength + v6->bLength, 36, 0xCu);
  if ( !v8 )
    return (unsigned int)-1073741823;
  v9 = USBParseDescriptorWrapper(
         StartPosition,
         StartPosition->wTotalLength,
         &v8->bLength + *(unsigned __int16 *)&v8[2].bDescriptorType,
         37,
         5u);
  if ( v9 )
  {
    if ( v9[1].bLength != 3 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        return (unsigned int)-1073741823;
      v11 = 16;
      goto LABEL_9;
    }
    v12 = *(unsigned __int16 *)&v9[1].bDescriptorType;
    v7 = 0;
    if ( v12 <= 0x80 )
    {
      if ( v12 >= 0xD )
        goto LABEL_23;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        goto LABEL_23;
      v14 = 18;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        goto LABEL_23;
      v14 = 17;
    }
    WPP_SF_d(
      v13->AttachedDevice,
      v14,
      WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids,
      *(unsigned __int16 *)&v9[1].bDescriptorType);
LABEL_23:
    *a3 = v12;
    *a2 = 1;
    return v7;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    return (unsigned int)-1073741823;
  v11 = 15;
LABEL_9:
  WPP_SF_(v10->AttachedDevice, v11, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids);
  return (unsigned int)-1073741823;
}

```

## disassembly

```asm
0x140021c54  push    rbx
0x140021c56  push    rsi
0x140021c57  push    rdi
0x140021c58  push    r14
0x140021c5a  sub     rsp, 48h
0x140021c5e  mov     rsi, r8
0x140021c61  mov     r14, rdx
0x140021c64  or      r8d, 0FFFFFFFFh; InterfaceNumber
0x140021c68  mov     rdx, rcx; StartPosition
0x140021c6b  mov     [rsp+68h+InterfaceProtocol], r8d; InterfaceProtocol
0x140021c70  mov     r9d, r8d; AlternateSetting
0x140021c73  mov     [rsp+68h+InterfaceSubClass], 1; InterfaceSubClass
0x140021c7b  mov     rbx, rcx
0x140021c7e  mov     [rsp+68h+InterfaceClass], 0Eh; InterfaceClass
0x140021c86  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x140021c8d  nop     dword ptr [rax+rax+00h]
0x140021c92  test    rax, rax
0x140021c95  jnz     short loc_140021CA1
0x140021c97  mov     ebx, 0C0000001h
0x140021c9c  jmp     loc_140021DC2
0x140021ca1  cmp     byte ptr [rax+4], 0
0x140021ca5  jz      short loc_140021C97
0x140021ca7  movzx   r8d, byte ptr [rax]
0x140021cab  mov     r9d, 24h ; '$'
0x140021cb1  movzx   edx, word ptr [rbx+2]
0x140021cb5  add     r8, rax
0x140021cb8  mov     rcx, rbx
0x140021cbb  mov     qword ptr [rsp+68h+InterfaceClass], 0Ch
0x140021cc4  call    USBParseDescriptorWrapper
0x140021cc9  test    rax, rax
0x140021ccc  jz      short loc_140021C97
0x140021cce  movzx   r8d, word ptr [rax+5]
0x140021cd3  mov     r9d, 25h ; '%'
0x140021cd9  movzx   edx, word ptr [rbx+2]
0x140021cdd  add     r8, rax
0x140021ce0  mov     rcx, rbx
0x140021ce3  mov     qword ptr [rsp+68h+InterfaceClass], 5
0x140021cec  call    USBParseDescriptorWrapper
0x140021cf1  test    rax, rax
0x140021cf4  jnz     short loc_140021D29
0x140021cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x140021cfd  lea     rax, WPP_GLOBAL_Control
0x140021d04  cmp     rcx, rax
0x140021d07  jz      short loc_140021C97
0x140021d09  cmp     byte ptr [rcx+29h], 5
0x140021d0d  jb      short loc_140021C97
0x140021d0f  mov     edx, 0Fh
0x140021d14  mov     rcx, [rcx+18h]
0x140021d18  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x140021d1f  call    WPP_SF_
0x140021d24  jmp     loc_140021C97
0x140021d29  cmp     byte ptr [rax+2], 3
0x140021d2d  jz      short loc_140021D57
0x140021d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140021d36  lea     rax, WPP_GLOBAL_Control
0x140021d3d  cmp     rcx, rax
0x140021d40  jz      loc_140021C97
0x140021d46  cmp     byte ptr [rcx+29h], 5
0x140021d4a  jb      loc_140021C97
0x140021d50  mov     edx, 10h
0x140021d55  jmp     short loc_140021D14
0x140021d57  movzx   edi, word ptr [rax+3]
0x140021d5b  xor     ebx, ebx
0x140021d5d  cmp     edi, 80h
0x140021d63  jbe     short loc_140021D83
0x140021d65  mov     rcx, cs:WPP_GLOBAL_Control
0x140021d6c  lea     rax, WPP_GLOBAL_Control
0x140021d73  cmp     rcx, rax
0x140021d76  jz      short loc_140021DB9
0x140021d78  cmp     byte ptr [rcx+29h], 5
0x140021d7c  jb      short loc_140021DB9
0x140021d7e  lea     edx, [rbx+11h]
0x140021d81  jmp     short loc_140021DA6
0x140021d83  cmp     edi, 0Dh
0x140021d86  jnb     short loc_140021DB9
0x140021d88  mov     rcx, cs:WPP_GLOBAL_Control
0x140021d8f  lea     rax, WPP_GLOBAL_Control
0x140021d96  cmp     rcx, rax
0x140021d99  jz      short loc_140021DB9
0x140021d9b  cmp     byte ptr [rcx+29h], 5
0x140021d9f  jb      short loc_140021DB9
0x140021da1  mov     edx, 12h
0x140021da6  mov     rcx, [rcx+18h]
0x140021daa  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x140021db1  mov     r9d, edi
0x140021db4  call    WPP_SF_d
0x140021db9  mov     [rsi], edi
0x140021dbb  mov     dword ptr [r14], 1
0x140021dc2  mov     eax, ebx
0x140021dc4  add     rsp, 48h
0x140021dc8  pop     r14
0x140021dca  pop     rdi
0x140021dcb  pop     rsi
0x140021dcc  pop     rbx
0x140021dcd  retn
```
