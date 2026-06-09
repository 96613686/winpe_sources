# GetMaxPacketSizeForEndpoint

- ea: `0x140016bf0`
- end: `0x140016cce`
- name: `GetMaxPacketSizeForEndpoint`
- size: `222`
- prototype: `__int64 __fastcall(PVOID DescriptorBuffer, PVOID StartPosition)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000c9e4`
- `0x140017e4c`

## callees

- `0x14000d2d0`
- `0x14000d434`
- `0x140016bf0`
- `0x14001709c`

## pseudocode

```c
PUSB_COMMON_DESCRIPTOR __fastcall GetMaxPacketSizeForEndpoint(
        char *DescriptorBuffer,
        UCHAR *StartPosition,
        char a3,
        char a4)
{
  __int64 v4; // rdi
  PUSB_COMMON_DESCRIPTOR result; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  unsigned __int8 *v12; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+38h] [rbp-20h] BYREF
  __int64 v14; // [rsp+40h] [rbp-18h] BYREF

  v4 = 0;
  v14 = 0;
  v12 = 0;
  v13 = 0;
  if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() && a4 )
  {
    result = GetEndpointDescriptorEx(
               DescriptorBuffer,
               StartPosition,
               a3,
               &v12,
               (unsigned __int8 **)&v13,
               (UCHAR **)&v14);
    v4 = v14;
  }
  else
  {
    result = (PUSB_COMMON_DESCRIPTOR)GetEndpointDescriptor(
                                       (unsigned __int16 *)DescriptorBuffer,
                                       StartPosition,
                                       a3,
                                       &v12,
                                       (unsigned __int8 **)&v13);
  }
  v10 = (__int64)result;
  if ( result )
  {
    if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( v4 )
        return (PUSB_COMMON_DESCRIPTOR)*(unsigned int *)(v4 + 4);
      v11 = v13;
      if ( !v13 )
      {
        if ( v12 && v12[2] )
          return (PUSB_COMMON_DESCRIPTOR)*((unsigned __int16 *)v12 + 2);
        return (PUSB_COMMON_DESCRIPTOR)*(unsigned __int16 *)(v10 + 4);
      }
      return (PUSB_COMMON_DESCRIPTOR)*(unsigned int *)(v11 + 4);
    }
    if ( !v12 || !v12[2] )
      return (PUSB_COMMON_DESCRIPTOR)*(unsigned __int16 *)(v10 + 4);
    v11 = v13;
    if ( v13 )
      return (PUSB_COMMON_DESCRIPTOR)*(unsigned int *)(v11 + 4);
    return (PUSB_COMMON_DESCRIPTOR)*((unsigned __int16 *)v12 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x140016bf0  push    rbp
0x140016bf2  push    rbx
0x140016bf3  push    rsi
0x140016bf4  push    rdi
0x140016bf5  push    r14
0x140016bf7  push    r15
0x140016bf9  mov     rbp, rsp
0x140016bfc  sub     rsp, 58h
0x140016c00  xor     edi, edi
0x140016c02  mov     r15b, r9b
0x140016c05  mov     [rbp+var_18], rdi
0x140016c09  mov     bl, r8b
0x140016c0c  mov     [rbp+var_28], rdi
0x140016c10  mov     rsi, rdx
0x140016c13  mov     [rbp+var_20], rdi
0x140016c17  mov     r14, rcx
0x140016c1a  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x140016c1f  lea     r9, [rbp+var_28]
0x140016c23  mov     r8b, bl
0x140016c26  mov     rdx, rsi; StartPosition
0x140016c29  mov     rcx, r14; DescriptorBuffer
0x140016c2c  test    eax, eax
0x140016c2e  jz      short loc_140016C52
0x140016c30  test    r15b, r15b
0x140016c33  jz      short loc_140016C52
0x140016c35  lea     rax, [rbp+var_18]
0x140016c39  mov     [rsp+58h+var_30], rax; __int64
0x140016c3e  lea     rax, [rbp+var_20]
0x140016c42  mov     [rsp+58h+var_38], rax; __int64
0x140016c47  call    GetEndpointDescriptorEx
0x140016c4c  mov     rdi, [rbp+var_18]
0x140016c50  jmp     short loc_140016C60
0x140016c52  lea     rax, [rbp+var_20]
0x140016c56  mov     [rsp+58h+var_38], rax; __int64
0x140016c5b  call    GetEndpointDescriptor
0x140016c60  mov     rbx, rax
0x140016c63  test    rax, rax
0x140016c66  jz      short loc_140016CC0
0x140016c68  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x140016c6d  test    eax, eax
0x140016c6f  jz      short loc_140016C9F
0x140016c71  test    rdi, rdi
0x140016c74  jz      short loc_140016C7B
0x140016c76  mov     eax, [rdi+4]
0x140016c79  jmp     short loc_140016CC0
0x140016c7b  mov     rax, [rbp+var_20]
0x140016c7f  test    rax, rax
0x140016c82  jnz     short loc_140016CB7
0x140016c84  mov     rax, [rbp+var_28]
0x140016c88  test    rax, rax
0x140016c8b  jz      short loc_140016C99
0x140016c8d  cmp     byte ptr [rax+2], 0
0x140016c91  jz      short loc_140016C99
0x140016c93  movzx   eax, word ptr [rax+4]
0x140016c97  jmp     short loc_140016CC0
0x140016c99  movzx   eax, word ptr [rbx+4]
0x140016c9d  jmp     short loc_140016CC0
0x140016c9f  mov     rcx, [rbp+var_28]
0x140016ca3  test    rcx, rcx
0x140016ca6  jz      short loc_140016C99
0x140016ca8  cmp     byte ptr [rcx+2], 0
0x140016cac  jz      short loc_140016C99
0x140016cae  mov     rax, [rbp+var_20]
0x140016cb2  test    rax, rax
0x140016cb5  jz      short loc_140016CBC
0x140016cb7  mov     eax, [rax+4]
0x140016cba  jmp     short loc_140016CC0
0x140016cbc  movzx   eax, word ptr [rcx+4]
0x140016cc0  add     rsp, 58h
0x140016cc4  pop     r15
0x140016cc6  pop     r14
0x140016cc8  pop     rdi
0x140016cc9  pop     rsi
0x140016cca  pop     rbx
0x140016ccb  pop     rbp
0x140016ccc  retn
```
