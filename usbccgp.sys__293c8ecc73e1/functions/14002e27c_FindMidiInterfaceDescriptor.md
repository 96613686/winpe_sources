# FindMidiInterfaceDescriptor

- ea: `0x14002e27c`
- end: `0x14002e3d7`
- name: `FindMidiInterfaceDescriptor`
- size: `347`
- prototype: `__int64 __fastcall(PVOID DescriptorBuffer)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400249d4`

## callees

- `0x1400083c8`
- `0x14000b4bc`
- `0x14002e27c`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14002e2b2`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14002e2fb`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14002e2b2`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14002e2fb`
- `USBD!USBD_ParseDescriptors` at `0x14002e31b`
- `USBD!USBD_ParseDescriptors` at `0x14002e31b`

## pseudocode

```c
PUSB_INTERFACE_DESCRIPTOR __fastcall FindMidiInterfaceDescriptor(
        struct _USB_CONFIGURATION_DESCRIPTOR *DescriptorBuffer,
        void *a2,
        __int64 a3,
        int a4)
{
  __int64 v5; // rsi
  int v7; // edx
  PUSB_INTERFACE_DESCRIPTOR i; // rbx
  __int64 bLength; // rcx
  unsigned __int8 *v10; // rbp
  PUSB_INTERFACE_DESCRIPTOR v11; // rdi
  PUSB_COMMON_DESCRIPTOR v12; // rax

  v5 = 0;
  for ( i = USBD_ParseConfigurationDescriptorEx(DescriptorBuffer, a2, -1, -1, 1, 3, -1); i; i = v11 )
  {
    bLength = i->bLength;
    v10 = &i->bLength + bLength;
    if ( (PUSB_INTERFACE_DESCRIPTOR)((char *)i + bLength) < i )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_qD(a4, v7, 8, 18, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids, (char)i, bLength);
      }
      return (PUSB_INTERFACE_DESCRIPTOR)v5;
    }
    v11 = USBD_ParseConfigurationDescriptorEx(DescriptorBuffer, &i->bLength + bLength, -1, -1, 1, 3, -1);
    v12 = USBD_ParseDescriptors(DescriptorBuffer, DescriptorBuffer->wTotalLength, v10, 36);
    if ( !v12 || v11 && v12 > (PUSB_COMMON_DESCRIPTOR)v11 || v12->bLength < 7u || v12[1].bLength != 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_q(a4, v7, 8, 19, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids, (char)i);
      }
      return (PUSB_INTERFACE_DESCRIPTOR)v5;
    }
    if ( v12[2].bLength == 2 )
      return i;
  }
  return (PUSB_INTERFACE_DESCRIPTOR)v5;
}

```

## disassembly

```asm
0x14002e27c  push    rbx
0x14002e27e  push    rbp
0x14002e27f  push    rsi
0x14002e280  push    rdi
0x14002e281  push    r12
0x14002e283  push    r14
0x14002e285  push    r15
0x14002e287  sub     rsp, 40h
0x14002e28b  or      r12d, 0FFFFFFFFh
0x14002e28f  mov     r14, r9
0x14002e292  mov     [rsp+78h+InterfaceProtocol], r12d; InterfaceProtocol
0x14002e297  xor     esi, esi
0x14002e299  mov     [rsp+78h+InterfaceSubClass], 3; InterfaceSubClass
0x14002e2a1  mov     r9d, r12d; AlternateSetting
0x14002e2a4  mov     r8d, r12d; InterfaceNumber
0x14002e2a7  mov     [rsp+78h+InterfaceClass], 1; InterfaceClass
0x14002e2af  mov     r15, rcx
0x14002e2b2  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x14002e2b9  nop     dword ptr [rax+rax+00h]
0x14002e2be  mov     rbx, rax
0x14002e2c1  test    rbx, rbx
0x14002e2c4  jz      loc_14002E3C4
0x14002e2ca  movzx   ecx, byte ptr [rbx]
0x14002e2cd  lea     rbp, [rcx+rbx]
0x14002e2d1  cmp     rbp, rbx
0x14002e2d4  jb      loc_14002E38B
0x14002e2da  mov     [rsp+78h+InterfaceProtocol], r12d; InterfaceProtocol
0x14002e2df  mov     r9d, r12d; AlternateSetting
0x14002e2e2  mov     [rsp+78h+InterfaceSubClass], 3; InterfaceSubClass
0x14002e2ea  mov     r8d, r12d; InterfaceNumber
0x14002e2ed  mov     rdx, rbp; StartPosition
0x14002e2f0  mov     [rsp+78h+InterfaceClass], 1; InterfaceClass
0x14002e2f8  mov     rcx, r15; ConfigurationDescriptor
0x14002e2fb  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x14002e302  nop     dword ptr [rax+rax+00h]
0x14002e307  movzx   edx, word ptr [r15+2]; TotalLength
0x14002e30c  mov     r9d, 24h ; '$'; DescriptorType
0x14002e312  mov     r8, rbp; StartPosition
0x14002e315  mov     rcx, r15; DescriptorBuffer
0x14002e318  mov     rdi, rax
0x14002e31b  call    cs:__imp_USBD_ParseDescriptors
0x14002e322  nop     dword ptr [rax+rax+00h]
0x14002e327  test    rax, rax
0x14002e32a  jz      short loc_14002E354
0x14002e32c  test    rdi, rdi
0x14002e32f  jz      short loc_14002E336
0x14002e331  cmp     rax, rdi
0x14002e334  ja      short loc_14002E354
0x14002e336  cmp     byte ptr [rax], 7
0x14002e339  jb      short loc_14002E354
0x14002e33b  cmp     byte ptr [rax+2], 1
0x14002e33f  jnz     short loc_14002E354
0x14002e341  cmp     byte ptr [rax+4], 2
0x14002e345  jz      short loc_14002E34F
0x14002e347  mov     rbx, rdi
0x14002e34a  jmp     loc_14002E2C1
0x14002e34f  mov     rsi, rbx
0x14002e352  jmp     short loc_14002E3C4
0x14002e354  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002e35b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e362  jz      short loc_14002E3C4
0x14002e364  mov     r9d, 13h
0x14002e36a  mov     qword ptr [rsp+78h+InterfaceSubClass], rbx
0x14002e36f  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x14002e376  mov     dl, 2
0x14002e378  mov     rcx, r14
0x14002e37b  mov     qword ptr [rsp+78h+InterfaceClass], rax
0x14002e380  lea     r8d, [r9-0Bh]
0x14002e384  call    WPP_RECORDER_SF_q
0x14002e389  jmp     short loc_14002E3C4
0x14002e38b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002e392  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e399  jz      short loc_14002E3C4
0x14002e39b  mov     [rsp+78h+InterfaceProtocol], ecx
0x14002e39f  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x14002e3a6  mov     r9d, 12h
0x14002e3ac  mov     qword ptr [rsp+78h+InterfaceSubClass], rbx
0x14002e3b1  mov     dl, 2
0x14002e3b3  mov     qword ptr [rsp+78h+InterfaceClass], rax
0x14002e3b8  mov     rcx, r14
0x14002e3bb  lea     r8d, [r9-0Ah]
0x14002e3bf  call    WPP_RECORDER_SF_qD
0x14002e3c4  mov     rax, rsi
0x14002e3c7  add     rsp, 40h
0x14002e3cb  pop     r15
0x14002e3cd  pop     r14
0x14002e3cf  pop     r12
0x14002e3d1  pop     rdi
0x14002e3d2  pop     rsi
0x14002e3d3  pop     rbp
0x14002e3d4  pop     rbx
0x14002e3d5  retn
```
