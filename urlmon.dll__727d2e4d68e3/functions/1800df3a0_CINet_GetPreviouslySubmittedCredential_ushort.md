# CINet::GetPreviouslySubmittedCredential(ushort * *)

- ea: `0x1800df3a0`
- end: `0x1800df5c3`
- name: `?GetPreviouslySubmittedCredential@CINet@@IEAAHPEAPEAG@Z`
- size: `547`
- prototype: `__int64 __fastcall(CINet *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800decb8`

## callees

- `0x1800df3a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df4b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df4b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800df42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800df4d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800df42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800df4d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df599`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df599`
- `WININET!InternetQueryOptionW` at `0x1800df3f6`
- `WININET!InternetQueryOptionW` at `0x1800df469`
- `WININET!InternetQueryOptionW` at `0x1800df4a3`
- `WININET!InternetQueryOptionW` at `0x1800df506`
- `WININET!InternetQueryOptionW` at `0x1800df3f6`
- `WININET!InternetQueryOptionW` at `0x1800df469`
- `WININET!InternetQueryOptionW` at `0x1800df4a3`
- `WININET!InternetQueryOptionW` at `0x1800df506`

## pseudocode

```c
__int64 __fastcall CINet::GetPreviouslySubmittedCredential(CINet *this, unsigned __int16 **a2)
{
  char v4; // al
  void *v5; // rcx
  unsigned __int16 *v6; // rsi
  _WORD *v7; // rdi
  BOOL OptionW; // ebx
  DWORD LastError; // eax
  __int64 v10; // r14
  unsigned __int16 *v11; // rax
  void *v12; // rcx
  bool v13; // cf
  unsigned int v14; // ebx
  DWORD v15; // eax
  _WORD *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int16 *i; // rax
  __int64 v20; // rcx
  _BYTE *j; // rax
  SIZE_T cb; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(cb) = 0;
  if ( a2 )
  {
    v4 = *((_BYTE *)this + 992);
    v5 = (void *)*((_QWORD *)this + 44);
    *a2 = 0;
    v6 = 0;
    v7 = 0;
    OptionW = InternetQueryOptionW(v5, (v4 & 1) != 0 ? 43 : 28, 0, (LPDWORD)&cb);
    LastError = GetLastError();
    v10 = -1;
    if ( OptionW
      || LastError == 122
      && (_DWORD)cb
      && (v11 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb), (v6 = v11) != 0)
      && InternetQueryOptionW(*((HINTERNET *)this + 44), (*((_BYTE *)this + 992) & 1) != 0 ? 43 : 28, v11, (LPDWORD)&cb) )
    {
      v12 = (void *)*((_QWORD *)this + 44);
      v13 = (*((_BYTE *)this + 992) & 1) != 0;
      LODWORD(cb) = 0;
      v14 = InternetQueryOptionW(v12, v13 ? 44 : 29, 0, (LPDWORD)&cb);
      v15 = GetLastError();
      if ( v14
        || v15 == 122
        && (_DWORD)cb
        && (v16 = CoTaskMemAlloc((unsigned int)cb), (v7 = v16) != 0)
        && (v14 = InternetQueryOptionW(
                    *((HINTERNET *)this + 44),
                    (*((_BYTE *)this + 992) & 1) != 0 ? 44 : 29,
                    v16,
                    (LPDWORD)&cb)) != 0 )
      {
        if ( !v6 )
          goto LABEL_22;
        if ( *v6 && v7 && *v7 )
        {
          *a2 = v6;
          goto LABEL_23;
        }
      }
    }
    if ( v6 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v6[v17] );
      v18 = 2 * v17;
      for ( i = v6; v18; --v18 )
      {
        *(_BYTE *)i = 0;
        i = (unsigned __int16 *)((char *)i + 1);
      }
    }
LABEL_22:
    CoTaskMemFree(v6);
    v14 = 0;
    if ( !v7 )
    {
LABEL_26:
      CoTaskMemFree(v7);
      return v14;
    }
    do
LABEL_23:
      ++v10;
    while ( v7[v10] );
    v20 = 2 * v10;
    for ( j = v7; v20; --v20 )
      *j++ = 0;
    goto LABEL_26;
  }
  return 0;
}

```

## disassembly

```asm
0x1800df3a0  mov     r11, rsp
0x1800df3a3  mov     [r11+8], rbx
0x1800df3a7  mov     [r11+18h], rbp
0x1800df3ab  push    rsi
0x1800df3ac  push    rdi
0x1800df3ad  push    r12
0x1800df3af  push    r14
0x1800df3b1  push    r15
0x1800df3b3  sub     rsp, 20h
0x1800df3b7  xor     r12d, r12d
0x1800df3ba  mov     r15, rdx
0x1800df3bd  mov     [r11+10h], r12d
0x1800df3c1  mov     rbp, rcx
0x1800df3c4  test    rdx, rdx
0x1800df3c7  jz      loc_1800DF5A9
0x1800df3cd  mov     al, [rcx+3E0h]
0x1800df3d3  lea     r9, [r11+10h]; lpdwBufferLength
0x1800df3d7  mov     rcx, [rcx+160h]; hInternet
0x1800df3de  and     al, 1
0x1800df3e0  mov     [rdx], r12
0x1800df3e3  neg     al
0x1800df3e5  mov     esi, r12d
0x1800df3e8  mov     edi, r12d
0x1800df3eb  sbb     edx, edx
0x1800df3ed  xor     r8d, r8d; lpBuffer
0x1800df3f0  and     edx, 0Fh
0x1800df3f3  add     edx, 1Ch; dwOption
0x1800df3f6  call    cs:__imp_InternetQueryOptionW
0x1800df3fd  nop     dword ptr [rax+rax+00h]
0x1800df402  mov     ebx, eax
0x1800df404  call    cs:__imp_GetLastError
0x1800df40b  nop     dword ptr [rax+rax+00h]
0x1800df410  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800df414  test    ebx, ebx
0x1800df416  jnz     short loc_1800DF47D
0x1800df418  cmp     eax, 7Ah ; 'z'
0x1800df41b  jnz     loc_1800DF533
0x1800df421  mov     eax, dword ptr [rsp+48h+cb]
0x1800df425  test    eax, eax
0x1800df427  jz      loc_1800DF533
0x1800df42d  mov     ecx, eax; cb
0x1800df42f  call    cs:__imp_CoTaskMemAlloc
0x1800df436  nop     dword ptr [rax+rax+00h]
0x1800df43b  mov     rsi, rax
0x1800df43e  test    rax, rax
0x1800df441  jz      loc_1800DF533
0x1800df447  mov     cl, [rbp+3E0h]
0x1800df44d  lea     r9, [rsp+48h+cb]; lpdwBufferLength
0x1800df452  and     cl, 1
0x1800df455  mov     r8, rax; lpBuffer
0x1800df458  neg     cl
0x1800df45a  mov     rcx, [rbp+160h]; hInternet
0x1800df461  sbb     edx, edx
0x1800df463  and     edx, 0Fh
0x1800df466  add     edx, 1Ch; dwOption
0x1800df469  call    cs:__imp_InternetQueryOptionW
0x1800df470  nop     dword ptr [rax+rax+00h]
0x1800df475  test    eax, eax
0x1800df477  jz      loc_1800DF533
0x1800df47d  mov     al, [rbp+3E0h]
0x1800df483  lea     r9, [rsp+48h+cb]; lpdwBufferLength
0x1800df488  mov     rcx, [rbp+160h]; hInternet
0x1800df48f  and     al, 1
0x1800df491  neg     al
0x1800df493  mov     dword ptr [rsp+48h+cb], r12d
0x1800df498  sbb     edx, edx
0x1800df49a  xor     r8d, r8d; lpBuffer
0x1800df49d  and     edx, 0Fh
0x1800df4a0  add     edx, 1Dh; dwOption
0x1800df4a3  call    cs:__imp_InternetQueryOptionW
0x1800df4aa  nop     dword ptr [rax+rax+00h]
0x1800df4af  mov     ebx, eax
0x1800df4b1  call    cs:__imp_GetLastError
0x1800df4b8  nop     dword ptr [rax+rax+00h]
0x1800df4bd  test    ebx, ebx
0x1800df4bf  jnz     short loc_1800DF518
0x1800df4c1  cmp     eax, 7Ah ; 'z'
0x1800df4c4  jnz     short loc_1800DF533
0x1800df4c6  mov     eax, dword ptr [rsp+48h+cb]
0x1800df4ca  test    eax, eax
0x1800df4cc  jz      short loc_1800DF533
0x1800df4ce  mov     ecx, eax; cb
0x1800df4d0  call    cs:__imp_CoTaskMemAlloc
0x1800df4d7  nop     dword ptr [rax+rax+00h]
0x1800df4dc  mov     rdi, rax
0x1800df4df  test    rax, rax
0x1800df4e2  jz      short loc_1800DF533
0x1800df4e4  mov     cl, [rbp+3E0h]
0x1800df4ea  lea     r9, [rsp+48h+cb]; lpdwBufferLength
0x1800df4ef  and     cl, 1
0x1800df4f2  mov     r8, rax; lpBuffer
0x1800df4f5  neg     cl
0x1800df4f7  mov     rcx, [rbp+160h]; hInternet
0x1800df4fe  sbb     edx, edx
0x1800df500  and     edx, 0Fh
0x1800df503  add     edx, 1Dh; dwOption
0x1800df506  call    cs:__imp_InternetQueryOptionW
0x1800df50d  nop     dword ptr [rax+rax+00h]
0x1800df512  mov     ebx, eax
0x1800df514  test    eax, eax
0x1800df516  jz      short loc_1800DF533
0x1800df518  test    rsi, rsi
0x1800df51b  jz      short loc_1800DF55D
0x1800df51d  cmp     [rsi], r12w
0x1800df521  jz      short loc_1800DF533
0x1800df523  test    rdi, rdi
0x1800df526  jz      short loc_1800DF533
0x1800df528  cmp     [rdi], r12w
0x1800df52c  jz      short loc_1800DF533
0x1800df52e  mov     [r15], rsi
0x1800df531  jmp     short loc_1800DF574
0x1800df533  test    rsi, rsi
0x1800df536  jz      short loc_1800DF55D
0x1800df538  mov     rax, r14
0x1800df53b  inc     rax
0x1800df53e  cmp     [rsi+rax*2], r12w
0x1800df543  jnz     short loc_1800DF53B
0x1800df545  lea     rcx, [rax+rax]
0x1800df549  mov     rax, rsi
0x1800df54c  test    rcx, rcx
0x1800df54f  jz      short loc_1800DF55D
0x1800df551  mov     [rax], r12b
0x1800df554  inc     rax
0x1800df557  sub     rcx, 1
0x1800df55b  jnz     short loc_1800DF551
0x1800df55d  mov     rcx, rsi; pv
0x1800df560  call    cs:__imp_CoTaskMemFree
0x1800df567  nop     dword ptr [rax+rax+00h]
0x1800df56c  mov     ebx, r12d
0x1800df56f  test    rdi, rdi
0x1800df572  jz      short loc_1800DF596
0x1800df574  inc     r14
0x1800df577  cmp     [rdi+r14*2], r12w
0x1800df57c  jnz     short loc_1800DF574
0x1800df57e  lea     rcx, [r14+r14]
0x1800df582  mov     rax, rdi
0x1800df585  test    rcx, rcx
0x1800df588  jz      short loc_1800DF596
0x1800df58a  mov     [rax], r12b
0x1800df58d  inc     rax
0x1800df590  sub     rcx, 1
0x1800df594  jnz     short loc_1800DF58A
0x1800df596  mov     rcx, rdi; pv
0x1800df599  call    cs:__imp_CoTaskMemFree
0x1800df5a0  nop     dword ptr [rax+rax+00h]
0x1800df5a5  mov     eax, ebx
0x1800df5a7  jmp     short loc_1800DF5AB
0x1800df5a9  xor     eax, eax
0x1800df5ab  mov     rbx, [rsp+48h+arg_0]
0x1800df5b0  mov     rbp, [rsp+48h+arg_10]
0x1800df5b5  add     rsp, 20h
0x1800df5b9  pop     r15
0x1800df5bb  pop     r14
0x1800df5bd  pop     r12
0x1800df5bf  pop     rdi
0x1800df5c0  pop     rsi
0x1800df5c1  retn
```
