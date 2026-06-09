# CINet::GetPreviouslySubmittedCredential(ushort * *)

- ea: `0x1800d6240`
- end: `0x1800d6426`
- name: `?GetPreviouslySubmittedCredential@CINet@@IEAAHPEAPEAG@Z`
- size: `486`
- prototype: `__int64 __fastcall(CINet *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d5b60`

## callees

- `0x1800d6240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d629e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d629e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d62c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d634c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d62c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d634c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d63d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6403`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d63d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6403`
- `WININET!InternetQueryOptionW` at `0x1800d6296`
- `WININET!InternetQueryOptionW` at `0x1800d62f7`
- `WININET!InternetQueryOptionW` at `0x1800d632b`
- `WININET!InternetQueryOptionW` at `0x1800d637c`
- `WININET!InternetQueryOptionW` at `0x1800d6296`
- `WININET!InternetQueryOptionW` at `0x1800d62f7`
- `WININET!InternetQueryOptionW` at `0x1800d632b`
- `WININET!InternetQueryOptionW` at `0x1800d637c`

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
0x1800d6240  mov     r11, rsp
0x1800d6243  mov     [r11+8], rbx
0x1800d6247  mov     [r11+18h], rbp
0x1800d624b  push    rsi
0x1800d624c  push    rdi
0x1800d624d  push    r12
0x1800d624f  push    r14
0x1800d6251  push    r15
0x1800d6253  sub     rsp, 20h
0x1800d6257  xor     r12d, r12d
0x1800d625a  mov     r15, rdx
0x1800d625d  mov     [r11+10h], r12d
0x1800d6261  mov     rbp, rcx
0x1800d6264  test    rdx, rdx
0x1800d6267  jz      loc_1800D640D
0x1800d626d  mov     al, [rcx+3E0h]
0x1800d6273  lea     r9, [r11+10h]; lpdwBufferLength
0x1800d6277  mov     rcx, [rcx+160h]; hInternet
0x1800d627e  and     al, 1
0x1800d6280  mov     [rdx], r12
0x1800d6283  neg     al
0x1800d6285  mov     esi, r12d
0x1800d6288  mov     edi, r12d
0x1800d628b  sbb     edx, edx
0x1800d628d  xor     r8d, r8d; lpBuffer
0x1800d6290  and     edx, 0Fh
0x1800d6293  add     edx, 1Ch; dwOption
0x1800d6296  call    cs:__imp_InternetQueryOptionW
0x1800d629c  mov     ebx, eax
0x1800d629e  call    cs:__imp_GetLastError
0x1800d62a4  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800d62a8  test    ebx, ebx
0x1800d62aa  jnz     short loc_1800D6305
0x1800d62ac  cmp     eax, 7Ah ; 'z'
0x1800d62af  jnz     loc_1800D63A3
0x1800d62b5  mov     eax, dword ptr [rsp+48h+cb]
0x1800d62b9  test    eax, eax
0x1800d62bb  jz      loc_1800D63A3
0x1800d62c1  mov     ecx, eax; cb
0x1800d62c3  call    cs:__imp_CoTaskMemAlloc
0x1800d62c9  mov     rsi, rax
0x1800d62cc  test    rax, rax
0x1800d62cf  jz      loc_1800D63A3
0x1800d62d5  mov     cl, [rbp+3E0h]
0x1800d62db  lea     r9, [rsp+48h+cb]; lpdwBufferLength
0x1800d62e0  and     cl, 1
0x1800d62e3  mov     r8, rax; lpBuffer
0x1800d62e6  neg     cl
0x1800d62e8  mov     rcx, [rbp+160h]; hInternet
0x1800d62ef  sbb     edx, edx
0x1800d62f1  and     edx, 0Fh
0x1800d62f4  add     edx, 1Ch; dwOption
0x1800d62f7  call    cs:__imp_InternetQueryOptionW
0x1800d62fd  test    eax, eax
0x1800d62ff  jz      loc_1800D63A3
0x1800d6305  mov     al, [rbp+3E0h]
0x1800d630b  lea     r9, [rsp+48h+cb]; lpdwBufferLength
0x1800d6310  mov     rcx, [rbp+160h]; hInternet
0x1800d6317  and     al, 1
0x1800d6319  neg     al
0x1800d631b  mov     dword ptr [rsp+48h+cb], r12d
0x1800d6320  sbb     edx, edx
0x1800d6322  xor     r8d, r8d; lpBuffer
0x1800d6325  and     edx, 0Fh
0x1800d6328  add     edx, 1Dh; dwOption
0x1800d632b  call    cs:__imp_InternetQueryOptionW
0x1800d6331  mov     ebx, eax
0x1800d6333  call    cs:__imp_GetLastError
0x1800d6339  test    ebx, ebx
0x1800d633b  jnz     short loc_1800D6388
0x1800d633d  cmp     eax, 7Ah ; 'z'
0x1800d6340  jnz     short loc_1800D63A3
0x1800d6342  mov     eax, dword ptr [rsp+48h+cb]
0x1800d6346  test    eax, eax
0x1800d6348  jz      short loc_1800D63A3
0x1800d634a  mov     ecx, eax; cb
0x1800d634c  call    cs:__imp_CoTaskMemAlloc
0x1800d6352  mov     rdi, rax
0x1800d6355  test    rax, rax
0x1800d6358  jz      short loc_1800D63A3
0x1800d635a  mov     cl, [rbp+3E0h]
0x1800d6360  lea     r9, [rsp+48h+cb]; lpdwBufferLength
0x1800d6365  and     cl, 1
0x1800d6368  mov     r8, rax; lpBuffer
0x1800d636b  neg     cl
0x1800d636d  mov     rcx, [rbp+160h]; hInternet
0x1800d6374  sbb     edx, edx
0x1800d6376  and     edx, 0Fh
0x1800d6379  add     edx, 1Dh; dwOption
0x1800d637c  call    cs:__imp_InternetQueryOptionW
0x1800d6382  mov     ebx, eax
0x1800d6384  test    eax, eax
0x1800d6386  jz      short loc_1800D63A3
0x1800d6388  test    rsi, rsi
0x1800d638b  jz      short loc_1800D63CD
0x1800d638d  cmp     [rsi], r12w
0x1800d6391  jz      short loc_1800D63A3
0x1800d6393  test    rdi, rdi
0x1800d6396  jz      short loc_1800D63A3
0x1800d6398  cmp     [rdi], r12w
0x1800d639c  jz      short loc_1800D63A3
0x1800d639e  mov     [r15], rsi
0x1800d63a1  jmp     short loc_1800D63DE
0x1800d63a3  test    rsi, rsi
0x1800d63a6  jz      short loc_1800D63CD
0x1800d63a8  mov     rax, r14
0x1800d63ab  inc     rax
0x1800d63ae  cmp     [rsi+rax*2], r12w
0x1800d63b3  jnz     short loc_1800D63AB
0x1800d63b5  lea     rcx, [rax+rax]
0x1800d63b9  mov     rax, rsi
0x1800d63bc  test    rcx, rcx
0x1800d63bf  jz      short loc_1800D63CD
0x1800d63c1  mov     [rax], r12b
0x1800d63c4  inc     rax
0x1800d63c7  sub     rcx, 1
0x1800d63cb  jnz     short loc_1800D63C1
0x1800d63cd  mov     rcx, rsi; pv
0x1800d63d0  call    cs:__imp_CoTaskMemFree
0x1800d63d6  mov     ebx, r12d
0x1800d63d9  test    rdi, rdi
0x1800d63dc  jz      short loc_1800D6400
0x1800d63de  inc     r14
0x1800d63e1  cmp     [rdi+r14*2], r12w
0x1800d63e6  jnz     short loc_1800D63DE
0x1800d63e8  lea     rcx, [r14+r14]
0x1800d63ec  mov     rax, rdi
0x1800d63ef  test    rcx, rcx
0x1800d63f2  jz      short loc_1800D6400
0x1800d63f4  mov     [rax], r12b
0x1800d63f7  inc     rax
0x1800d63fa  sub     rcx, 1
0x1800d63fe  jnz     short loc_1800D63F4
0x1800d6400  mov     rcx, rdi; pv
0x1800d6403  call    cs:__imp_CoTaskMemFree
0x1800d6409  mov     eax, ebx
0x1800d640b  jmp     short loc_1800D640F
0x1800d640d  xor     eax, eax
0x1800d640f  mov     rbx, [rsp+48h+arg_0]
0x1800d6414  mov     rbp, [rsp+48h+arg_10]
0x1800d6419  add     rsp, 20h
0x1800d641d  pop     r15
0x1800d641f  pop     r14
0x1800d6421  pop     r12
0x1800d6423  pop     rdi
0x1800d6424  pop     rsi
0x1800d6425  retn
```
