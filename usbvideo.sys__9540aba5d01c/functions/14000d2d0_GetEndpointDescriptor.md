# GetEndpointDescriptor

- ea: `0x14000d2d0`
- end: `0x14000d3e1`
- name: `GetEndpointDescriptor`
- size: `273`
- prototype: `__int64 __usercall@<rax>(PVOID DescriptorBuffer@<rcx>, PVOID StartPosition@<rdx>, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000c95c`
- `0x14000cbf0`
- `0x140016bf0`
- `0x140016cd4`

## callees

- `0x14000d2d0`
- `0x14000d3e8`
- `0x14000d790`

## import_xrefs

- `USBD!USBD_ParseDescriptors` at `0x14000d30f`
- `USBD!USBD_ParseDescriptors` at `0x14000d30f`

## pseudocode

```c
unsigned __int8 *__fastcall GetEndpointDescriptor(
        unsigned __int16 *DescriptorBuffer,
        PVOID StartPosition,
        char a3,
        unsigned __int8 **a4,
        unsigned __int8 **a5)
{
  unsigned __int16 *v9; // rdi
  unsigned __int8 *NextVideoAltSetting; // rbx
  PUSB_COMMON_DESCRIPTOR v11; // rax
  unsigned __int8 *p_bLength; // rcx
  unsigned __int8 *v13; // rdx
  unsigned __int8 **v14; // r8
  unsigned __int8 *v15; // r9

  v9 = DescriptorBuffer + 1;
  NextVideoAltSetting = (unsigned __int8 *)GetNextVideoAltSetting(DescriptorBuffer, StartPosition);
  if ( !NextVideoAltSetting )
    NextVideoAltSetting = (unsigned __int8 *)DescriptorBuffer + *v9;
  v11 = USBD_ParseDescriptors(DescriptorBuffer, *v9, StartPosition, 5);
  p_bLength = &v11->bLength;
  if ( v11 )
  {
    if ( v11->bLength >= 7u )
    {
      while ( v11 )
      {
        if ( p_bLength[2] == a3 )
        {
          if ( p_bLength > NextVideoAltSetting )
            p_bLength = 0;
          break;
        }
        v11 = USBParseDescriptorWrapper(DescriptorBuffer, *v9, &p_bLength[*p_bLength], 5, 7u);
        p_bLength = &v11->bLength;
      }
    }
    else
    {
      p_bLength = 0;
    }
  }
  if ( a4 && p_bLength )
  {
    v13 = &p_bLength[*p_bLength];
    if ( v13 < NextVideoAltSetting && v13[1] == 48 )
    {
      v14 = a5;
      *a4 = v13;
      if ( !a5 )
        return p_bLength;
      if ( (v13[3] & 0x80u) != 0 )
      {
        _mm_lfence();
        v15 = &v13[*v13];
        if ( v15 >= NextVideoAltSetting || v15[1] != 49 )
          v15 = 0;
        *a5 = v15;
        return p_bLength;
      }
    }
    else
    {
      v14 = a5;
      *a4 = 0;
      if ( !a5 )
        return p_bLength;
    }
    *v14 = 0;
  }
  return p_bLength;
}

```

## disassembly

```asm
0x14000d2d0  push    rbx
0x14000d2d2  push    rbp
0x14000d2d3  push    rsi
0x14000d2d4  push    rdi
0x14000d2d5  push    r14
0x14000d2d7  push    r15
0x14000d2d9  sub     rsp, 38h
0x14000d2dd  mov     rsi, r9
0x14000d2e0  mov     r15b, r8b
0x14000d2e3  mov     r14, rdx
0x14000d2e6  mov     rbp, rcx
0x14000d2e9  call    GetNextVideoAltSetting
0x14000d2ee  lea     rdi, [rbp+2]
0x14000d2f2  mov     rbx, rax
0x14000d2f5  test    rax, rax
0x14000d2f8  jnz     short loc_14000D300
0x14000d2fa  movzx   ebx, word ptr [rdi]
0x14000d2fd  add     rbx, rbp
0x14000d300  movzx   edx, word ptr [rdi]; TotalLength
0x14000d303  mov     r9d, 5; DescriptorType
0x14000d309  mov     r8, r14; StartPosition
0x14000d30c  mov     rcx, rbp; DescriptorBuffer
0x14000d30f  call    cs:__imp_USBD_ParseDescriptors
0x14000d316  nop     dword ptr [rax+rax+00h]
0x14000d31b  mov     rcx, rax
0x14000d31e  test    rax, rax
0x14000d321  jz      short loc_14000D366
0x14000d323  cmp     byte ptr [rax], 7
0x14000d326  jnb     short loc_14000D356
0x14000d328  xor     ecx, ecx
0x14000d32a  jmp     short loc_14000D366
0x14000d32c  cmp     [rcx+2], r15b
0x14000d330  jz      short loc_14000D35D
0x14000d332  movzx   r8d, byte ptr [rcx]
0x14000d336  mov     r9d, 5
0x14000d33c  movzx   edx, word ptr [rdi]
0x14000d33f  add     r8, rcx
0x14000d342  mov     rcx, rbp
0x14000d345  mov     [rsp+68h+var_48], 7
0x14000d34e  call    USBParseDescriptorWrapper
0x14000d353  mov     rcx, rax
0x14000d356  test    rax, rax
0x14000d359  jnz     short loc_14000D32C
0x14000d35b  jmp     short loc_14000D366
0x14000d35d  xor     eax, eax
0x14000d35f  cmp     rcx, rbx
0x14000d362  cmova   rcx, rax
0x14000d366  test    rsi, rsi
0x14000d369  jz      short loc_14000D3D0
0x14000d36b  test    rcx, rcx
0x14000d36e  jz      short loc_14000D3D0
0x14000d370  movzx   edx, byte ptr [rcx]
0x14000d373  add     rdx, rcx
0x14000d376  cmp     rdx, rbx
0x14000d379  jnb     short loc_14000D3B5
0x14000d37b  cmp     byte ptr [rdx+1], 30h ; '0'
0x14000d37f  jnz     short loc_14000D3B5
0x14000d381  mov     r8, [rsp+68h+arg_20]
0x14000d389  mov     [rsi], rdx
0x14000d38c  test    r8, r8
0x14000d38f  jz      short loc_14000D3D0
0x14000d391  cmp     byte ptr [rdx+3], 0
0x14000d395  jge     short loc_14000D3C9
0x14000d397  lfence
0x14000d39a  movzx   r9d, byte ptr [rdx]
0x14000d39e  add     r9, rdx
0x14000d3a1  cmp     r9, rbx
0x14000d3a4  jnb     short loc_14000D3AD
0x14000d3a6  cmp     byte ptr [r9+1], 31h ; '1'
0x14000d3ab  jz      short loc_14000D3B0
0x14000d3ad  xor     r9d, r9d
0x14000d3b0  mov     [r8], r9
0x14000d3b3  jmp     short loc_14000D3D0
0x14000d3b5  mov     r8, [rsp+68h+arg_20]
0x14000d3bd  mov     qword ptr [rsi], 0
0x14000d3c4  test    r8, r8
0x14000d3c7  jz      short loc_14000D3D0
0x14000d3c9  mov     qword ptr [r8], 0
0x14000d3d0  mov     rax, rcx
0x14000d3d3  add     rsp, 38h
0x14000d3d7  pop     r15
0x14000d3d9  pop     r14
0x14000d3db  pop     rdi
0x14000d3dc  pop     rsi
0x14000d3dd  pop     rbp
0x14000d3de  pop     rbx
0x14000d3df  retn
```
