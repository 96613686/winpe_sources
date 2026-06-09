# SaslSetContextOption

- ea: `0x18001a210`
- end: `0x18001a2f3`
- name: `SaslSetContextOption`
- size: `227`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle ContextHandle, ULONG Option, PVOID Value, ULONG Size)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800136dc`
- `0x18001a210`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a284`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a284`

## pseudocode

```c
SECURITY_STATUS __stdcall SaslSetContextOption(PCtxtHandle ContextHandle, ULONG Option, PVOID Value, ULONG Size)
{
  SIZE_T v5; // rbp
  SECURITY_STATUS v7; // ebx
  struct _SASL_CONTEXT *Context; // rax
  struct _SASL_CONTEXT *v9; // rdi
  ULONG v10; // esi
  ULONG v11; // esi
  ULONG v12; // esi
  HLOCAL v13; // rax

  v5 = Size;
  v7 = 0;
  Context = SaslFindContext(ContextHandle, 0);
  v9 = Context;
  v10 = Option - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        if ( v12 != 1 )
          return -2146893054;
        if ( (unsigned int)v5 >= 4 )
        {
          if ( Context )
            *((_DWORD *)Context + 11) = *(_DWORD *)Value;
          else
            SaslGlobalAuthZID = *(_DWORD *)Value;
          return v7;
        }
        return -2146893023;
      }
      if ( !Context )
        return -2146893055;
      if ( !*((_DWORD *)Context + 11) )
        return -2146893054;
      v13 = LocalAlloc(0, v5);
      *((_QWORD *)v9 + 8) = v13;
      if ( v13 )
      {
        *((_DWORD *)v9 + 18) = v5;
        memcpy_0(v13, Value, v5);
      }
      else
      {
        return -2146893056;
      }
    }
    else
    {
      if ( (unsigned int)v5 < 4 )
        return -2146893023;
      if ( Context )
        *((_DWORD *)Context + 15) = *(_DWORD *)Value;
      else
        SaslGlobalRecvSize = *(_DWORD *)Value;
    }
  }
  else
  {
    if ( (unsigned int)v5 < 4 )
      return -2146893023;
    if ( Context )
      *((_DWORD *)Context + 14) = *(_DWORD *)Value;
    else
      SaslGlobalSendSize = *(_DWORD *)Value;
  }
  return v7;
}

```

## disassembly

```asm
0x18001a210  push    rbx
0x18001a212  push    rbp
0x18001a213  push    rsi
0x18001a214  push    rdi
0x18001a215  push    r14
0x18001a217  sub     rsp, 20h
0x18001a21b  mov     esi, edx
0x18001a21d  mov     ebp, r9d
0x18001a220  xor     edx, edx; int
0x18001a222  mov     r14, r8
0x18001a225  xor     ebx, ebx
0x18001a227  call    ?SaslFindContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@H@Z; SaslFindContext(_SecHandle *,int)
0x18001a22c  mov     rdi, rax
0x18001a22f  sub     esi, 1
0x18001a232  jz      loc_18001A2C7
0x18001a238  sub     esi, 1
0x18001a23b  jz      short loc_18001A2AD
0x18001a23d  sub     esi, 1
0x18001a240  jz      short loc_18001A26E
0x18001a242  cmp     esi, 1
0x18001a245  jz      short loc_18001A251
0x18001a247  mov     ebx, 80090302h
0x18001a24c  jmp     loc_18001A2E6
0x18001a251  cmp     ebp, 4
0x18001a254  jb      short loc_18001A2CC
0x18001a256  mov     eax, [r14]
0x18001a259  test    rdi, rdi
0x18001a25c  jz      short loc_18001A266
0x18001a25e  mov     [rdi+2Ch], eax
0x18001a261  jmp     loc_18001A2E6
0x18001a266  mov     cs:?SaslGlobalAuthZID@@3W4_SASL_AUTHZID_STATE@@A, eax; _SASL_AUTHZID_STATE SaslGlobalAuthZID
0x18001a26c  jmp     short loc_18001A2E6
0x18001a26e  test    rdi, rdi
0x18001a271  jnz     short loc_18001A27A
0x18001a273  mov     ebx, 80090301h
0x18001a278  jmp     short loc_18001A2E6
0x18001a27a  cmp     [rax+2Ch], ebx
0x18001a27d  jz      short loc_18001A247
0x18001a27f  mov     rdx, rbp; uBytes
0x18001a282  xor     ecx, ecx; uFlags
0x18001a284  call    cs:__imp_LocalAlloc
0x18001a28a  mov     [rdi+40h], rax
0x18001a28e  test    rax, rax
0x18001a291  jz      short loc_18001A2A6
0x18001a293  mov     r8, rbp; Size
0x18001a296  mov     [rdi+48h], ebp
0x18001a299  mov     rdx, r14; Src
0x18001a29c  mov     rcx, rax; void *
0x18001a29f  call    memcpy_0
0x18001a2a4  jmp     short loc_18001A2E6
0x18001a2a6  mov     ebx, 80090300h
0x18001a2ab  jmp     short loc_18001A2E6
0x18001a2ad  cmp     ebp, 4
0x18001a2b0  jb      short loc_18001A2CC
0x18001a2b2  mov     eax, [r14]
0x18001a2b5  test    rdi, rdi
0x18001a2b8  jz      short loc_18001A2BF
0x18001a2ba  mov     [rdi+3Ch], eax
0x18001a2bd  jmp     short loc_18001A2E6
0x18001a2bf  mov     cs:?SaslGlobalRecvSize@@3KA, eax; ulong SaslGlobalRecvSize
0x18001a2c5  jmp     short loc_18001A2E6
0x18001a2c7  cmp     ebp, 4
0x18001a2ca  jnb     short loc_18001A2D3
0x18001a2cc  mov     ebx, 80090321h
0x18001a2d1  jmp     short loc_18001A2E6
0x18001a2d3  mov     eax, [r14]
0x18001a2d6  test    rdi, rdi
0x18001a2d9  jz      short loc_18001A2E0
0x18001a2db  mov     [rdi+38h], eax
0x18001a2de  jmp     short loc_18001A2E6
0x18001a2e0  mov     cs:?SaslGlobalSendSize@@3KA, eax; ulong SaslGlobalSendSize
0x18001a2e6  mov     eax, ebx
0x18001a2e8  add     rsp, 20h
0x18001a2ec  pop     r14
0x18001a2ee  pop     rdi
0x18001a2ef  pop     rsi
0x18001a2f0  pop     rbp
0x18001a2f1  pop     rbx
0x18001a2f2  retn
```
