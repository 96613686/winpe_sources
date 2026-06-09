# SaslGetContextOption

- ea: `0x180019c20`
- end: `0x180019d5d`
- name: `SaslGetContextOption`
- size: `317`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle ContextHandle, ULONG Option, PVOID Value, ULONG Size, PULONG Needed)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001ae0`
- `0x1800136dc`
- `0x180019c20`
- `0x180022047`
- `0x180022190`

## pseudocode

```c
SECURITY_STATUS __stdcall SaslGetContextOption(
        PCtxtHandle ContextHandle,
        ULONG Option,
        PVOID Value,
        ULONG Size,
        PULONG Needed)
{
  struct _SASL_CONTEXT *Context; // rax
  struct _SASL_CONTEXT *v10; // rsi
  SECURITY_STATUS result; // eax
  SECURITY_STATUS v12; // ebx
  ULONG v13; // edi
  ULONG v14; // edi
  ULONG v15; // edi
  ULONG v16; // edi
  unsigned int v17; // eax
  unsigned int v18; // r8d
  __int128 pBuffer; // [rsp+20h] [rbp-48h] BYREF

  Context = SaslFindContext(ContextHandle, 0);
  v10 = Context;
  if ( !Context )
    return -2146893055;
  v12 = 0;
  v13 = Option - 1;
  if ( !v13 )
  {
    v16 = 4;
    if ( Size >= 4 )
    {
      pBuffer = 0;
      result = QueryContextAttributesW(ContextHandle, 0, &pBuffer);
      if ( result < 0 )
        return result;
      v17 = 0;
      v18 = DWORD2(pBuffer) + HIDWORD(pBuffer) + DWORD1(pBuffer);
      if ( v18 <= *((_DWORD *)v10 + 14) )
        v17 = *((_DWORD *)v10 + 14) - v18;
      goto LABEL_23;
    }
    goto LABEL_19;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v16 = 4;
    if ( Size >= 4 )
    {
      v17 = *((_DWORD *)Context + 15);
      goto LABEL_23;
    }
LABEL_19:
    v12 = -2146893023;
    goto LABEL_24;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    if ( *((_DWORD *)Context + 11) )
    {
      if ( Size >= *((_DWORD *)Context + 18) )
        memcpy_0(Value, *((const void **)Context + 8), *((unsigned int *)Context + 18));
      else
        v12 = -2146893023;
      v16 = *((_DWORD *)v10 + 18);
    }
    else
    {
      v12 = -2146893054;
      v16 = 0;
    }
    goto LABEL_24;
  }
  if ( v15 == 1 )
  {
    v16 = 4;
    if ( Size >= 4 )
    {
      v17 = *((_DWORD *)Context + 11);
LABEL_23:
      *(_DWORD *)Value = v17;
      goto LABEL_24;
    }
    goto LABEL_19;
  }
  v16 = 0;
  v12 = -2146893054;
LABEL_24:
  if ( Needed )
    *Needed = v16;
  return v12;
}

```

## disassembly

```asm
0x180019c20  mov     [rsp+arg_8], rbx
0x180019c25  mov     [rsp+arg_18], rbp
0x180019c2a  push    rsi
0x180019c2b  push    rdi
0x180019c2c  push    r12
0x180019c2e  push    r14
0x180019c30  push    r15
0x180019c32  sub     rsp, 40h
0x180019c36  mov     rax, cs:__security_cookie
0x180019c3d  xor     rax, rsp
0x180019c40  mov     [rsp+68h+var_38], rax
0x180019c45  mov     r15, [rsp+68h+Needed]
0x180019c4d  mov     edi, edx
0x180019c4f  xor     edx, edx; int
0x180019c51  mov     ebp, r9d
0x180019c54  mov     r14, r8
0x180019c57  mov     r12, rcx
0x180019c5a  call    ?SaslFindContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@H@Z; SaslFindContext(_SecHandle *,int)
0x180019c5f  mov     rsi, rax
0x180019c62  test    rax, rax
0x180019c65  jnz     short loc_180019C71
0x180019c67  mov     eax, 80090301h
0x180019c6c  jmp     loc_180019D37
0x180019c71  xor     ebx, ebx
0x180019c73  sub     edi, 1
0x180019c76  jz      short loc_180019CE1
0x180019c78  sub     edi, 1
0x180019c7b  jz      short loc_180019CD3
0x180019c7d  sub     edi, 1
0x180019c80  jz      short loc_180019CA4
0x180019c82  cmp     edi, 1
0x180019c85  jz      short loc_180019C93
0x180019c87  xor     edi, edi
0x180019c89  mov     ebx, 80090302h
0x180019c8e  jmp     loc_180019D2D
0x180019c93  mov     edi, 4
0x180019c98  cmp     ebp, edi
0x180019c9a  jb      short loc_180019CEA
0x180019c9c  mov     eax, [rax+2Ch]
0x180019c9f  jmp     loc_180019D2A
0x180019ca4  cmp     [rax+2Ch], ebx
0x180019ca7  jnz     short loc_180019CB2
0x180019ca9  mov     ebx, 80090302h
0x180019cae  xor     edi, edi
0x180019cb0  jmp     short loc_180019D2D
0x180019cb2  cmp     ebp, [rax+48h]
0x180019cb5  jnb     short loc_180019CBE
0x180019cb7  mov     ebx, 80090321h
0x180019cbc  jmp     short loc_180019CCE
0x180019cbe  mov     r8d, [rax+48h]; Size
0x180019cc2  mov     rcx, r14; void *
0x180019cc5  mov     rdx, [rax+40h]; Src
0x180019cc9  call    memcpy_0
0x180019cce  mov     edi, [rsi+48h]
0x180019cd1  jmp     short loc_180019D2D
0x180019cd3  mov     edi, 4
0x180019cd8  cmp     ebp, edi
0x180019cda  jb      short loc_180019CEA
0x180019cdc  mov     eax, [rax+3Ch]
0x180019cdf  jmp     short loc_180019D2A
0x180019ce1  mov     edi, 4
0x180019ce6  cmp     ebp, edi
0x180019ce8  jnb     short loc_180019CF1
0x180019cea  mov     ebx, 80090321h
0x180019cef  jmp     short loc_180019D2D
0x180019cf1  xorps   xmm0, xmm0
0x180019cf4  lea     r8, [rsp+68h+pBuffer]; pBuffer
0x180019cf9  xor     edx, edx; ulAttribute
0x180019cfb  mov     rcx, r12; phContext
0x180019cfe  movups  [rsp+68h+pBuffer], xmm0
0x180019d03  call    QueryContextAttributesW
0x180019d08  test    eax, eax
0x180019d0a  js      short loc_180019D37
0x180019d0c  mov     r8d, dword ptr [rsp+68h+pBuffer+4]
0x180019d11  xor     eax, eax
0x180019d13  add     r8d, dword ptr [rsp+68h+pBuffer+0Ch]
0x180019d18  add     r8d, dword ptr [rsp+68h+pBuffer+8]
0x180019d1d  mov     ecx, [rsi+38h]
0x180019d20  sub     ecx, r8d
0x180019d23  cmp     r8d, [rsi+38h]
0x180019d27  cmovbe  eax, ecx
0x180019d2a  mov     [r14], eax
0x180019d2d  test    r15, r15
0x180019d30  jz      short loc_180019D35
0x180019d32  mov     [r15], edi
0x180019d35  mov     eax, ebx
0x180019d37  mov     rcx, [rsp+68h+var_38]
0x180019d3c  xor     rcx, rsp; StackCookie
0x180019d3f  call    __security_check_cookie
0x180019d44  lea     r11, [rsp+68h+var_28]
0x180019d49  mov     rbx, [r11+38h]
0x180019d4d  mov     rbp, [r11+48h]
0x180019d51  mov     rsp, r11
0x180019d54  pop     r15
0x180019d56  pop     r14
0x180019d58  pop     r12
0x180019d5a  pop     rdi
0x180019d5b  pop     rsi
0x180019d5c  retn
```
