# WxCopyProxyResultAndFixTheScheme(int,int,void *,_PROXY_RESULT const *,_PROXY_RESULT *)

- ea: `0x18000b2c0`
- end: `0x18000b58d`
- name: `?WxCopyProxyResultAndFixTheScheme@@YAJHHPEAXPEBU_PROXY_RESULT@@PEAU1@@Z`
- size: `717`
- prototype: `int(int, int, void *, const struct _PROXY_RESULT *, struct _PROXY_RESULT *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000afbc`
- `0x18002a044`

## callees

- `0x18000b2c0`
- `0x18000b594`
- `0x18000b8d0`
- `0x18007bc48`
- `0x1800a1d10`
- `0x1800db704`
- `0x1800dd2e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b4dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b486`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b546`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b573`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b582`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b546`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b573`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b582`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b501`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000b501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b450`

## pseudocode

```c
__int64 __fastcall WxCopyProxyResultAndFixTheScheme(
        int a1,
        int a2,
        void *a3,
        const struct _PROXY_RESULT *a4,
        struct _PROXY_RESULT *a5)
{
  __int64 v8; // rcx
  struct _PROXY_RESULT *v9; // rax
  int v10; // ebx
  unsigned int v11; // r11d
  unsigned int v12; // r8d
  char *v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // edi
  __int16 v16; // r10
  __int128 v17; // xmm1
  _OWORD *v18; // rsi
  unsigned int v20; // r14d
  unsigned int i; // edi
  int v22; // eax
  __int64 v23; // rdx
  signed int LastError; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v26; // rax
  HANDLE TargetHandle; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-30h] BYREF
  HANDLE hObject[2]; // [rsp+60h] [rbp-20h]

  TargetHandle = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)hObject = 0;
  if ( a5 )
  {
    v8 = 32;
    v9 = a5;
    do
    {
      *(_BYTE *)v9 = 0;
      v9 = (struct _PROXY_RESULT *)((char *)v9 + 1);
      --v8;
    }
    while ( v8 );
  }
  if ( !a4 )
  {
    v10 = -2147024809;
    goto LABEL_22;
  }
  if ( !a5 )
  {
    v10 = -2147024809;
    goto LABEL_22;
  }
  v10 = CopyProxyResult<WxCoTaskAllocator>((__int64)a4, pv);
  if ( v10 >= 0 )
  {
    if ( !a3 )
    {
LABEL_8:
      v11 = (unsigned int)pv[0];
      v12 = 0;
      if ( LODWORD(pv[0]) )
      {
        v13 = (char *)pv[1];
        do
        {
          v14 = 32LL * v12;
          v15 = *(_DWORD *)&v13[v14 + 8];
          if ( a1 && !*(_WORD *)&v13[v14 + 24] )
          {
            v16 = 0;
            if ( v15 == 3 || v15 == 4 )
            {
              v16 = 80;
            }
            else if ( v15 == 8 )
            {
              v16 = 1080;
            }
            *(_WORD *)&v13[v14 + 24] = v16;
          }
          if ( a2 )
          {
            v22 = WxProxySchemeToWinHttpScheme(v15);
            *(_DWORD *)&v13[v23 + 8] = v22;
          }
          ++v12;
        }
        while ( v12 < v11 );
      }
      v17 = *(_OWORD *)hObject;
      *(_OWORD *)a5 = *(_OWORD *)pv;
      *(_OWORD *)pv = 0;
      *(_OWORD *)hObject = 0;
      *((_OWORD *)a5 + 1) = v17;
      goto LABEL_22;
    }
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_q(1029, 33, WPP_23d61de28852329ea54c9edce07bfeba_Traceguids);
    CurrentProcess = GetCurrentProcess();
    v26 = GetCurrentProcess();
    if ( DuplicateHandle(v26, a3, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      v10 = 0;
      if ( (xmmword_180107A60 & 0x20) != 0 )
        WPP_SF_qq(
          1029,
          34,
          (unsigned int)WPP_23d61de28852329ea54c9edce07bfeba_Traceguids,
          (_DWORD)a3,
          (__int64)TargetHandle);
      if ( hObject[0] )
        CloseHandle(hObject[0]);
      hObject[0] = TargetHandle;
      TargetHandle = 0;
      goto LABEL_8;
    }
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 >= 0 )
      v10 = -2147418113;
  }
LABEL_22:
  if ( TargetHandle )
  {
    CloseHandle(TargetHandle);
    TargetHandle = 0;
  }
  v18 = pv[1];
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  if ( v18 )
  {
    v20 = (unsigned int)pv[0];
    for ( i = 0; i < v20; ++i )
      FreeProxyResultEntry<WxCoTaskAllocator>(&v18[2 * i]);
    CoTaskMemFree(v18);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000b2c0  mov     [rsp-28h+arg_0], rbx
0x18000b2c5  mov     [rsp-28h+arg_8], rsi
0x18000b2ca  push    rbp
0x18000b2cb  push    rdi
0x18000b2cc  push    r12
0x18000b2ce  push    r14
0x18000b2d0  push    r15
0x18000b2d2  mov     rbp, rsp
0x18000b2d5  sub     rsp, 80h
0x18000b2dc  mov     rax, cs:__security_cookie
0x18000b2e3  xor     rax, rsp
0x18000b2e6  mov     [rbp+var_10], rax
0x18000b2ea  mov     rsi, [rbp+arg_20]
0x18000b2ee  xor     r12d, r12d
0x18000b2f1  mov     [rbp+var_3C], r12d
0x18000b2f5  xorps   xmm0, xmm0
0x18000b2f8  mov     [rbp+TargetHandle], r12
0x18000b2fc  mov     rdi, r8
0x18000b2ff  mov     r14d, edx
0x18000b302  mov     r15d, ecx
0x18000b305  movups  xmmword ptr [rbp+pv], xmm0
0x18000b309  movups  xmmword ptr [rbp+hObject], xmm0
0x18000b30d  test    rsi, rsi
0x18000b310  jz      short loc_18000B326
0x18000b312  lea     ecx, [r12+20h]
0x18000b317  mov     rax, rsi
0x18000b31a  mov     [rax], r12b
0x18000b31d  inc     rax
0x18000b320  sub     rcx, 1
0x18000b324  jnz     short loc_18000B31A
0x18000b326  test    r9, r9
0x18000b329  jz      loc_18000B3D3
0x18000b32f  test    rsi, rsi
0x18000b332  jz      loc_18000B475
0x18000b338  lea     rdx, [rbp+pv]
0x18000b33c  mov     rcx, r9
0x18000b33f  call    ??$CopyProxyResult@VWxCoTaskAllocator@@@@YAJPEBU_PROXY_RESULT@@PEAU0@@Z; CopyProxyResult<WxCoTaskAllocator>(_PROXY_RESULT const *,_PROXY_RESULT *)
0x18000b344  mov     ebx, eax
0x18000b346  test    eax, eax
0x18000b348  js      loc_18000B469
0x18000b34e  test    rdi, rdi
0x18000b351  jnz     loc_18000B4B1
0x18000b357  mov     r11d, dword ptr [rbp+pv]
0x18000b35b  mov     r8d, r12d
0x18000b35e  test    r11d, r11d
0x18000b361  jz      short loc_18000B3B7
0x18000b363  mov     r9, [rbp+pv+8]
0x18000b367  mov     edx, r8d
0x18000b36a  shl     rdx, 5
0x18000b36e  mov     edi, [rdx+r9+8]
0x18000b373  test    r15d, r15d
0x18000b376  jz      short loc_18000B3A6
0x18000b378  cmp     [rdx+r9+18h], r12w
0x18000b37e  jnz     short loc_18000B3A6
0x18000b380  mov     ecx, edi
0x18000b382  mov     r10d, r12d
0x18000b385  sub     ecx, 3
0x18000b388  jz      loc_18000B568
0x18000b38e  sub     ecx, 1
0x18000b391  jz      loc_18000B568
0x18000b397  cmp     ecx, 4
0x18000b39a  jz      loc_18000B55D
0x18000b3a0  mov     [rdx+r9+18h], r10w
0x18000b3a6  test    r14d, r14d
0x18000b3a9  jnz     loc_18000B458
0x18000b3af  inc     r8d
0x18000b3b2  cmp     r8d, r11d
0x18000b3b5  jb      short loc_18000B367
0x18000b3b7  movups  xmm0, xmmword ptr [rbp+pv]
0x18000b3bb  movups  xmm1, xmmword ptr [rbp+hObject]
0x18000b3bf  movups  xmmword ptr [rsi], xmm0
0x18000b3c2  xorps   xmm0, xmm0
0x18000b3c5  movups  xmmword ptr [rbp+pv], xmm0
0x18000b3c9  movups  xmmword ptr [rbp+hObject], xmm0
0x18000b3cd  movups  xmmword ptr [rsi+10h], xmm1
0x18000b3d1  jmp     short loc_18000B3DF
0x18000b3d3  mov     ebx, 80070057h
0x18000b3d8  mov     [rbp+var_3C], 4E9h
0x18000b3df  mov     rcx, [rbp+TargetHandle]; hObject
0x18000b3e3  test    rcx, rcx
0x18000b3e6  jnz     loc_18000B573
0x18000b3ec  mov     rcx, [rbp+hObject]; hObject
0x18000b3f0  mov     rsi, [rbp+pv+8]
0x18000b3f4  test    rcx, rcx
0x18000b3f7  jnz     loc_18000B582
0x18000b3fd  test    rsi, rsi
0x18000b400  jnz     short loc_18000B42C
0x18000b402  mov     eax, ebx
0x18000b404  mov     rcx, [rbp+var_10]
0x18000b408  xor     rcx, rsp; StackCookie
0x18000b40b  call    __security_check_cookie
0x18000b410  lea     r11, [rsp+80h+var_s0]
0x18000b418  mov     rbx, [r11+30h]
0x18000b41c  mov     rsi, [r11+38h]
0x18000b420  mov     rsp, r11
0x18000b423  pop     r15
0x18000b425  pop     r14
0x18000b427  pop     r12
0x18000b429  pop     rdi
0x18000b42a  pop     rbp
0x18000b42b  retn
0x18000b42c  mov     r14d, dword ptr [rbp+pv]
0x18000b430  mov     edi, r12d
0x18000b433  test    r14d, r14d
0x18000b436  jz      short loc_18000B44D
0x18000b438  mov     ecx, edi
0x18000b43a  shl     rcx, 5
0x18000b43e  add     rcx, rsi
0x18000b441  call    ??$FreeProxyResultEntry@VWxCoTaskAllocator@@@@YAXPEAU_PROXY_RESULT_ENTRY@@@Z; FreeProxyResultEntry<WxCoTaskAllocator>(_PROXY_RESULT_ENTRY *)
0x18000b446  inc     edi
0x18000b448  cmp     edi, r14d
0x18000b44b  jb      short loc_18000B438
0x18000b44d  mov     rcx, rsi; pv
0x18000b450  call    cs:__imp_CoTaskMemFree
0x18000b456  jmp     short loc_18000B402
0x18000b458  mov     ecx, edi
0x18000b45a  call    ?WxProxySchemeToWinHttpScheme@@YAHW4ProxyResolveScheme@@@Z; WxProxySchemeToWinHttpScheme(ProxyResolveScheme)
0x18000b45f  mov     [rdx+r9+8], eax
0x18000b464  jmp     loc_18000B3AF
0x18000b469  mov     [rbp+var_3C], 4ECh
0x18000b470  jmp     loc_18000B3DF
0x18000b475  mov     ebx, 80070057h
0x18000b47a  mov     [rbp+var_3C], 4EAh
0x18000b481  jmp     loc_18000B3DF
0x18000b486  call    cs:__imp_GetLastError
0x18000b48c  mov     ebx, eax
0x18000b48e  test    eax, eax
0x18000b490  jle     short loc_18000B49B
0x18000b492  movzx   ebx, ax
0x18000b495  or      ebx, 80070000h
0x18000b49b  test    ebx, ebx
0x18000b49d  mov     [rbp+var_3C], 4FBh
0x18000b4a4  mov     eax, 8000FFFFh
0x18000b4a9  cmovns  ebx, eax
0x18000b4ac  jmp     loc_18000B3DF
0x18000b4b1  test    byte ptr cs:xmmword_180107A60, 20h
0x18000b4b8  jz      short loc_18000B4D3
0x18000b4ba  mov     edx, 21h ; '!'
0x18000b4bf  lea     r8, WPP_23d61de28852329ea54c9edce07bfeba_Traceguids
0x18000b4c6  mov     ecx, 405h
0x18000b4cb  mov     r9, rdi
0x18000b4ce  call    WPP_SF_q
0x18000b4d3  call    cs:__imp_GetCurrentProcess
0x18000b4d9  mov     rbx, rax
0x18000b4dc  call    cs:__imp_GetCurrentProcess
0x18000b4e2  mov     [rsp+80h+dwOptions], 2; dwOptions
0x18000b4ea  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x18000b4ee  mov     rcx, rax; hSourceProcessHandle
0x18000b4f1  mov     [rsp+80h+bInheritHandle], r12d; bInheritHandle
0x18000b4f6  mov     r8, rbx; hTargetProcessHandle
0x18000b4f9  mov     [rsp+80h+dwDesiredAccess], r12d; dwDesiredAccess
0x18000b4fe  mov     rdx, rdi; hSourceHandle
0x18000b501  call    cs:__imp_DuplicateHandle
0x18000b507  test    eax, eax
0x18000b509  jz      loc_18000B486
0x18000b50f  mov     ebx, r12d
0x18000b512  test    byte ptr cs:xmmword_180107A60, 20h
0x18000b519  jz      short loc_18000B53D
0x18000b51b  mov     rax, [rbp+TargetHandle]
0x18000b51f  lea     r8, WPP_23d61de28852329ea54c9edce07bfeba_Traceguids
0x18000b526  mov     edx, 22h ; '"'
0x18000b52b  mov     qword ptr [rsp+80h+dwDesiredAccess], rax
0x18000b530  mov     ecx, 405h
0x18000b535  mov     r9, rdi
0x18000b538  call    WPP_SF_qq
0x18000b53d  mov     rcx, [rbp+hObject]; hObject
0x18000b541  test    rcx, rcx
0x18000b544  jz      short loc_18000B54C
0x18000b546  call    cs:__imp_CloseHandle
0x18000b54c  mov     rax, [rbp+TargetHandle]
0x18000b550  mov     [rbp+hObject], rax
0x18000b554  mov     [rbp+TargetHandle], r12
0x18000b558  jmp     loc_18000B357
0x18000b55d  mov     r10d, 438h
0x18000b563  jmp     loc_18000B3A0
0x18000b568  mov     r10d, 50h ; 'P'
0x18000b56e  jmp     loc_18000B3A0
0x18000b573  call    cs:__imp_CloseHandle
0x18000b579  mov     [rbp+TargetHandle], r12
0x18000b57d  jmp     loc_18000B3EC
0x18000b582  call    cs:__imp_CloseHandle
0x18000b588  jmp     loc_18000B3FD
```
