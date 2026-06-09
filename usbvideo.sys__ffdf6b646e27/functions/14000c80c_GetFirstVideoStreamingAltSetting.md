# GetFirstVideoStreamingAltSetting

- ea: `0x14000c80c`
- end: `0x14000c953`
- name: `GetFirstVideoStreamingAltSetting`
- size: `327`
- prototype: `__int64 __fastcall(PVOID DescriptorBuffer)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140015234`
- `0x140016cd4`
- `0x1400171d0`
- `0x140017ed0`
- `0x14001a938`
- `0x14001b2f4`
- `0x140021aa4`
- `0x140021b48`
- `0x140021bc8`
- `0x14002b260`

## callees

- `0x14000c80c`
- `0x14000cb20`
- `0x140021f28`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000c83e`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000c89e`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000c945`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000c83e`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000c89e`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14000c945`

## pseudocode

```c
PUSB_INTERFACE_DESCRIPTOR __fastcall GetFirstVideoStreamingAltSetting(
        struct _USB_CONFIGURATION_DESCRIPTOR *DescriptorBuffer,
        unsigned int a2)
{
  PUSB_INTERFACE_DESCRIPTOR v4; // rbp
  unsigned __int8 *VideoSpecificDescriptor; // rcx
  __int64 v6; // rdi
  __int64 v7; // rax

  v4 = USBD_ParseConfigurationDescriptorEx(DescriptorBuffer, DescriptorBuffer, -1, -1, 14, 1, -1);
  if ( !v4 )
    return 0;
  VideoSpecificDescriptor = (unsigned __int8 *)GetVideoSpecificDescriptor(DescriptorBuffer);
  if ( !VideoSpecificDescriptor )
    return 0;
  while ( 1 )
  {
    v6 = VideoSpecificDescriptor[11];
    if ( a2 < (unsigned int)v6 )
      break;
    v4 = USBD_ParseConfigurationDescriptorEx(DescriptorBuffer, &v4->bLength + v4->bLength, -1, -1, 14, 1, -1);
    if ( !v4 )
      return 0;
    VideoSpecificDescriptor = (unsigned __int8 *)GetVideoSpecificDescriptor(DescriptorBuffer);
    if ( !VideoSpecificDescriptor )
      return 0;
    a2 -= v6;
  }
  v7 = *VideoSpecificDescriptor;
  if ( v7 != v6 + 12 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qddId(
        WPP_GLOBAL_Control->AttachedDevice,
        WPP_GLOBAL_Control,
        v6 + 12,
        VideoSpecificDescriptor,
        v7,
        v6,
        v6 + 12,
        a2);
    return 0;
  }
  return USBD_ParseConfigurationDescriptorEx(
           DescriptorBuffer,
           DescriptorBuffer,
           VideoSpecificDescriptor[a2 + 12],
           -1,
           14,
           2,
           -1);
}

```

## disassembly

```asm
0x14000c80c  push    rbx
0x14000c80e  push    rbp
0x14000c80f  push    rsi
0x14000c810  push    rdi
0x14000c811  push    r14
0x14000c813  sub     rsp, 40h
0x14000c817  or      r14d, 0FFFFFFFFh
0x14000c81b  mov     ebx, edx
0x14000c81d  mov     [rsp+68h+InterfaceProtocol], r14d; InterfaceProtocol
0x14000c822  mov     r9d, r14d; AlternateSetting
0x14000c825  mov     [rsp+68h+InterfaceSubClass], 1; InterfaceSubClass
0x14000c82d  mov     r8d, r14d; InterfaceNumber
0x14000c830  mov     rdx, rcx; StartPosition
0x14000c833  mov     [rsp+68h+InterfaceClass], 0Eh; InterfaceClass
0x14000c83b  mov     rsi, rcx
0x14000c83e  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x14000c845  nop     dword ptr [rax+rax+00h]
0x14000c84a  mov     rbp, rax
0x14000c84d  test    rax, rax
0x14000c850  jz      loc_14000C911
0x14000c856  lea     r8d, [r14+2]
0x14000c85a  mov     rdx, rax
0x14000c85d  mov     rcx, rsi; DescriptorBuffer
0x14000c860  call    GetVideoSpecificDescriptor
0x14000c865  mov     rcx, rax
0x14000c868  test    rax, rax
0x14000c86b  jz      loc_14000C911
0x14000c871  movzx   edi, byte ptr [rcx+0Bh]
0x14000c875  cmp     ebx, edi
0x14000c877  jb      short loc_14000C8CF
0x14000c879  movzx   edx, byte ptr [rbp+0]
0x14000c87d  mov     r9d, r14d; AlternateSetting
0x14000c880  mov     [rsp+68h+InterfaceProtocol], r14d; InterfaceProtocol
0x14000c885  add     rdx, rbp; StartPosition
0x14000c888  mov     [rsp+68h+InterfaceSubClass], 1; InterfaceSubClass
0x14000c890  mov     r8d, r14d; InterfaceNumber
0x14000c893  mov     rcx, rsi; ConfigurationDescriptor
0x14000c896  mov     [rsp+68h+InterfaceClass], 0Eh; InterfaceClass
0x14000c89e  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x14000c8a5  nop     dword ptr [rax+rax+00h]
0x14000c8aa  mov     rbp, rax
0x14000c8ad  test    rax, rax
0x14000c8b0  jz      short loc_14000C911
0x14000c8b2  mov     r8d, 1
0x14000c8b8  mov     rdx, rax
0x14000c8bb  mov     rcx, rsi; DescriptorBuffer
0x14000c8be  call    GetVideoSpecificDescriptor
0x14000c8c3  mov     rcx, rax
0x14000c8c6  test    rax, rax
0x14000c8c9  jz      short loc_14000C911
0x14000c8cb  sub     ebx, edi
0x14000c8cd  jmp     short loc_14000C871
0x14000c8cf  movzx   eax, byte ptr [rcx]
0x14000c8d2  lea     r8, [rdi+0Ch]
0x14000c8d6  cmp     rax, r8
0x14000c8d9  jz      short loc_14000C91F
0x14000c8db  mov     rdx, cs:WPP_GLOBAL_Control
0x14000c8e2  lea     r9, WPP_GLOBAL_Control
0x14000c8e9  cmp     rdx, r9
0x14000c8ec  jz      short loc_14000C911
0x14000c8ee  cmp     byte ptr [rdx+29h], 2
0x14000c8f2  jb      short loc_14000C911
0x14000c8f4  mov     [rsp+68h+var_30], ebx
0x14000c8f8  mov     r9, rcx
0x14000c8fb  mov     rcx, [rdx+18h]
0x14000c8ff  mov     qword ptr [rsp+68h+InterfaceProtocol], r8
0x14000c904  mov     [rsp+68h+InterfaceSubClass], edi
0x14000c908  mov     [rsp+68h+InterfaceClass], eax
0x14000c90c  call    WPP_SF_qddId
0x14000c911  xor     eax, eax
0x14000c913  add     rsp, 40h
0x14000c917  pop     r14
0x14000c919  pop     rdi
0x14000c91a  pop     rsi
0x14000c91b  pop     rbp
0x14000c91c  pop     rbx
0x14000c91d  retn
0x14000c91f  mov     eax, ebx
0x14000c921  mov     r9d, r14d; AlternateSetting
0x14000c924  mov     [rsp+68h+InterfaceProtocol], r14d; InterfaceProtocol
0x14000c929  mov     rdx, rsi; StartPosition
0x14000c92c  mov     [rsp+68h+InterfaceSubClass], 2; InterfaceSubClass
0x14000c934  mov     [rsp+68h+InterfaceClass], 0Eh; InterfaceClass
0x14000c93c  movzx   r8d, byte ptr [rax+rcx+0Ch]; InterfaceNumber
0x14000c942  mov     rcx, rsi; ConfigurationDescriptor
0x14000c945  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x14000c94c  nop     dword ptr [rax+rax+00h]
0x14000c951  jmp     short loc_14000C913
```
