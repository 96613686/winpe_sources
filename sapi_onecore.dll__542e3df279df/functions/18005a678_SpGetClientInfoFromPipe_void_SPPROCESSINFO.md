# SpGetClientInfoFromPipe(void *,SPPROCESSINFO *)

- ea: `0x18005a678`
- end: `0x18005a8bf`
- name: `?SpGetClientInfoFromPipe@@YAJPEAXPEAUSPPROCESSINFO@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(HANDLE hFile, PULONG ClientProcessId)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800e953c`

## callees

- `0x180026508`
- `0x180026ae4`
- `0x18005a678`
- `0x18005a8c8`
- `0x18005cd84`
- `0x1800b6dc8`
- `0x1800ebc08`
- `0x1800ebc2c`
- `0x1800ebc94`
- `0x1800ec3bc`
- `0x1800ecc2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a86c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a86c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeClientProcessId` at `0x18005a7b6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetNamedPipeClientProcessId` at `0x18005a7b6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005a80b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005a80b`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x18005a862`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x18005a862`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SpGetClientInfoFromPipe(HANDLE hFile, PULONG ClientProcessId)
{
  DWORD Timeout; // eax
  unsigned int v5; // r9d
  int LastError; // ebx
  __int64 v7; // rdx
  PULONG v8; // rcx
  _OWORD *v9; // rax
  __int64 v10; // rdx
  int ClientTokenFromPipe; // eax
  const char *v12; // r9
  __int64 v13; // rax
  HANDLE v14; // rax
  signed int v15; // eax
  __int64 v16; // rdx
  signed int v17; // eax
  __int64 v19; // [rsp+20h] [rbp-20h] BYREF
  __int64 *v20; // [rsp+28h] [rbp-18h] BYREF
  struct SPIPCMSG *v21; // [rsp+30h] [rbp-10h] BYREF
  char v22; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v24; // [rsp+70h] [rbp+30h] BYREF
  HANDLE v25; // [rsp+78h] [rbp+38h] BYREF

  v19 = 0;
  v20 = &v19;
  v21 = 0;
  v22 = 1;
  Timeout = GetTimeout(1);
  LastError = SpReadPipeMsg(hFile, Timeout, &v21, v5);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SPIPCMSG *,void (*)(void *),&void free(void *),wistd::integral_constant<unsigned __int64,0>,SPIPCMSG *,SPIPCMSG *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SPIPCMSG *,void (*)(void *),&void free(void *),wistd::integral_constant<unsigned __int64,0>,SPIPCMSG *,SPIPCMSG *,0,std::nullptr_t>>>>(&v20);
  if ( LastError >= 0 )
  {
    if ( *(_DWORD *)(v19 + 8) != 10 )
    {
      LastError = -2147418113;
      v7 = 1167;
      goto LABEL_5;
    }
    v8 = ClientProcessId + 2;
    v9 = (_OWORD *)(v19 + 20);
    v10 = 4;
    do
    {
      *(_OWORD *)v8 = *v9;
      *((_OWORD *)v8 + 1) = v9[1];
      *((_OWORD *)v8 + 2) = v9[2];
      *((_OWORD *)v8 + 3) = v9[3];
      *((_OWORD *)v8 + 4) = v9[4];
      *((_OWORD *)v8 + 5) = v9[5];
      *((_OWORD *)v8 + 6) = v9[6];
      *((_OWORD *)v8 + 7) = v9[7];
      v8 += 32;
      v9 += 8;
      --v10;
    }
    while ( v10 );
    *(_QWORD *)v8 = *(_QWORD *)v9;
    v24 = 0;
    v20 = &v24;
    v21 = 0;
    v22 = 1;
    ClientTokenFromPipe = SpGetClientTokenFromPipe((char *)hFile, (void **)&v21);
    if ( ClientTokenFromPipe < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x495,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\server\\spipchelper.cpp",
        (const char *)(unsigned int)ClientTokenFromPipe,
        v19);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v20);
    ClientProcessId[1] = 0;
    if ( !GetNamedPipeClientProcessId(hFile, ClientProcessId) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x499,
                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\server\\spipchelper.cpp",
                    v12);
LABEL_12:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v24);
      goto LABEL_31;
    }
    if ( ClientProcessId == (PULONG)-8LL )
      goto LABEL_17;
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)ClientProcessId + v13 + 4) );
    if ( !v13 )
    {
LABEL_17:
      v14 = OpenProcess(0x400u, 0, *ClientProcessId);
      v25 = v14;
      if ( !v14 )
      {
        v15 = GetLastError();
        LastError = v15;
        if ( v15 > 0 )
          LastError = (unsigned __int16)v15 | 0x80070000;
        if ( LastError >= 0 )
          goto LABEL_23;
        v16 = 1188;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\server\\spipchelper.cpp",
          (const char *)(unsigned int)LastError,
          v19);
LABEL_23:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
        goto LABEL_12;
      }
      if ( !K32GetProcessImageFileNameW(v14, (LPWSTR)ClientProcessId + 4, 0x104u) )
      {
        v17 = GetLastError();
        LastError = v17;
        if ( v17 > 0 )
          LastError = (unsigned __int16)v17 | 0x80070000;
        if ( LastError >= 0 )
          goto LABEL_23;
        v16 = 1194;
        goto LABEL_22;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v24);
    LastError = 0;
    goto LABEL_31;
  }
  v7 = 1166;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\server\\spipchelper.cpp",
    (const char *)(unsigned int)LastError,
    v19);
LABEL_31:
  wil::details::unique_storage<wil::details::resource_policy<SPIPCMSG *,void (*)(void *),&void free(void *),wistd::integral_constant<unsigned __int64,0>,SPIPCMSG *,SPIPCMSG *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SPIPCMSG *,void (*)(void *),&void free(void *),wistd::integral_constant<unsigned __int64,0>,SPIPCMSG *,SPIPCMSG *,0,std::nullptr_t>>(&v19);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005a678  mov     [rsp-18h+arg_0], rbx
0x18005a67d  mov     [rsp-18h+arg_8], rsi
0x18005a682  push    rbp
0x18005a683  push    rdi
0x18005a684  push    r14
0x18005a686  mov     rbp, rsp
0x18005a689  sub     rsp, 40h
0x18005a68d  mov     rdi, rdx
0x18005a690  mov     rsi, rcx
0x18005a693  xor     r14d, r14d
0x18005a696  mov     [rbp+var_20], r14
0x18005a69a  lea     rax, [rbp+var_20]
0x18005a69e  mov     [rbp+var_18], rax
0x18005a6a2  mov     [rbp+var_10], r14
0x18005a6a6  mov     [rbp+var_8], 1
0x18005a6aa  lea     ecx, [r14+1]
0x18005a6ae  call    ?GetTimeout@@YAKW4SPTIMEOUT@@@Z; GetTimeout(SPTIMEOUT)
0x18005a6b3  lea     r8, [rbp+var_10]; struct SPIPCMSG **
0x18005a6b7  mov     edx, eax; dwMilliseconds
0x18005a6b9  mov     rcx, rsi; hFile
0x18005a6bc  call    ?SpReadPipeMsg@@YAJPEAXKPEAPEAUSPIPCMSG@@H@Z; SpReadPipeMsg(void *,ulong,SPIPCMSG * *,int)
0x18005a6c1  mov     ebx, eax
0x18005a6c3  lea     rcx, [rbp+var_18]
0x18005a6c7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSPIPCMSG@@P6AXPEAX@Z$1?free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SPIPCMSG *,void (*)(void *),&free(void *),wistd::integral_constant<unsigned __int64,0>,SPIPCMSG *,SPIPCMSG *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SPIPCMSG *,void (*)(void *),&free(void *),wistd::integral_constant<unsigned __int64,0>,SPIPCMSG *,SPIPCMSG *,0,std::nullptr_t>>>>(void)
0x18005a6cc  test    ebx, ebx
0x18005a6ce  jns     short loc_18005A6D7
0x18005a6d0  mov     edx, 48Eh
0x18005a6d5  jmp     short loc_18005A6EB
0x18005a6d7  mov     rax, [rbp+var_20]
0x18005a6db  cmp     dword ptr [rax+8], 0Ah
0x18005a6df  jz      short loc_18005A703
0x18005a6e1  mov     ebx, 8000FFFFh
0x18005a6e6  mov     edx, 48Fh; void *
0x18005a6eb  lea     r8, aOnecoreuapEndu_209; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18005a6f2  mov     r9d, ebx; char *
0x18005a6f5  mov     rcx, [rbp+18h]; this
0x18005a6f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a6fe  jmp     loc_18005A8A1
0x18005a703  lea     rbx, [rdi+8]
0x18005a707  mov     rcx, rbx
0x18005a70a  add     rax, 14h
0x18005a70e  mov     edx, 4
0x18005a713  lea     r8d, [rdx+7Ch]
0x18005a717  movups  xmm0, xmmword ptr [rax]
0x18005a71a  movups  xmmword ptr [rcx], xmm0
0x18005a71d  movups  xmm1, xmmword ptr [rax+10h]
0x18005a721  movups  xmmword ptr [rcx+10h], xmm1
0x18005a725  movups  xmm0, xmmword ptr [rax+20h]
0x18005a729  movups  xmmword ptr [rcx+20h], xmm0
0x18005a72d  movups  xmm1, xmmword ptr [rax+30h]
0x18005a731  movups  xmmword ptr [rcx+30h], xmm1
0x18005a735  movups  xmm0, xmmword ptr [rax+40h]
0x18005a739  movups  xmmword ptr [rcx+40h], xmm0
0x18005a73d  movups  xmm1, xmmword ptr [rax+50h]
0x18005a741  movups  xmmword ptr [rcx+50h], xmm1
0x18005a745  movups  xmm0, xmmword ptr [rax+60h]
0x18005a749  movups  xmmword ptr [rcx+60h], xmm0
0x18005a74d  movups  xmm1, xmmword ptr [rax+70h]
0x18005a751  movups  xmmword ptr [rcx+70h], xmm1
0x18005a755  add     rcx, r8
0x18005a758  add     rax, r8
0x18005a75b  sub     rdx, 1
0x18005a75f  jnz     short loc_18005A717
0x18005a761  mov     rax, [rax]
0x18005a764  mov     [rcx], rax
0x18005a767  mov     [rbp+arg_10], r14
0x18005a76b  lea     rax, [rbp+arg_10]
0x18005a76f  mov     [rbp+var_18], rax
0x18005a773  mov     [rbp+var_10], r14
0x18005a777  mov     [rbp+var_8], 1
0x18005a77b  lea     rdx, [rbp+var_10]; void **
0x18005a77f  mov     rcx, rsi; void *
0x18005a782  call    ?SpGetClientTokenFromPipe@@YAJPEAXPEAPEAX@Z; SpGetClientTokenFromPipe(void *,void * *)
0x18005a787  mov     rcx, [rbp+18h]; this
0x18005a78b  test    eax, eax
0x18005a78d  jns     short loc_18005A7A3
0x18005a78f  mov     r9d, eax; char *
0x18005a792  lea     r8, aOnecoreuapEndu_209; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18005a799  mov     edx, 495h; void *
0x18005a79e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a7a3  lea     rcx, [rbp+var_18]
0x18005a7a7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18005a7ac  mov     [rdi+4], r14d
0x18005a7b0  mov     rdx, rdi; ClientProcessId
0x18005a7b3  mov     rcx, rsi; Pipe
0x18005a7b6  call    cs:__imp_GetNamedPipeClientProcessId
0x18005a7bc  test    eax, eax
0x18005a7be  jnz     short loc_18005A7E5
0x18005a7c0  mov     rcx, [rbp+18h]; this
0x18005a7c4  lea     r8, aOnecoreuapEndu_209; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18005a7cb  mov     edx, 499h; void *
0x18005a7d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005a7d5  mov     ebx, eax
0x18005a7d7  lea     rcx, [rbp+arg_10]
0x18005a7db  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005a7e0  jmp     loc_18005A8A1
0x18005a7e5  test    rbx, rbx
0x18005a7e8  jz      short loc_18005A801
0x18005a7ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005a7ee  inc     rax
0x18005a7f1  cmp     [rbx+rax*2], r14w
0x18005a7f6  jnz     short loc_18005A7EE
0x18005a7f8  test    rax, rax
0x18005a7fb  jnz     loc_18005A895
0x18005a801  mov     r8d, [rdi]; dwProcessId
0x18005a804  xor     edx, edx; bInheritHandle
0x18005a806  mov     ecx, 400h; dwDesiredAccess
0x18005a80b  call    cs:__imp_OpenProcess
0x18005a811  mov     [rbp+arg_18], rax
0x18005a815  test    rax, rax
0x18005a818  jnz     short loc_18005A856
0x18005a81a  call    cs:__imp_GetLastError
0x18005a820  mov     ebx, eax
0x18005a822  test    eax, eax
0x18005a824  jle     short loc_18005A82F
0x18005a826  movzx   ebx, ax
0x18005a829  or      ebx, 80070000h
0x18005a82f  test    ebx, ebx
0x18005a831  jns     short loc_18005A84B
0x18005a833  mov     edx, 4A4h; void *
0x18005a838  lea     r8, aOnecoreuapEndu_209; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18005a83f  mov     r9d, ebx; char *
0x18005a842  mov     rcx, [rbp+18h]; this
0x18005a846  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a84b  lea     rcx, [rbp+arg_18]
0x18005a84f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005a854  jmp     short loc_18005A7D7
0x18005a856  mov     r8d, 104h; nSize
0x18005a85c  mov     rdx, rbx; lpImageFileName
0x18005a85f  mov     rcx, rax; hProcess
0x18005a862  call    cs:__imp_K32GetProcessImageFileNameW
0x18005a868  test    eax, eax
0x18005a86a  jnz     short loc_18005A88C
0x18005a86c  call    cs:__imp_GetLastError
0x18005a872  mov     ebx, eax
0x18005a874  test    eax, eax
0x18005a876  jle     short loc_18005A881
0x18005a878  movzx   ebx, ax
0x18005a87b  or      ebx, 80070000h
0x18005a881  test    ebx, ebx
0x18005a883  jns     short loc_18005A84B
0x18005a885  mov     edx, 4AAh
0x18005a88a  jmp     short loc_18005A838
0x18005a88c  lea     rcx, [rbp+arg_18]
0x18005a890  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005a895  lea     rcx, [rbp+arg_10]
0x18005a899  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005a89e  mov     ebx, r14d
0x18005a8a1  lea     rcx, [rbp+var_20]
0x18005a8a5  call    ??1?$unique_storage@U?$resource_policy@PEAUSPIPCMSG@@P6AXPEAX@Z$1?free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SPIPCMSG *,void (*)(void *),&free(void *),wistd::integral_constant<unsigned __int64,0>,SPIPCMSG *,SPIPCMSG *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SPIPCMSG *,void (*)(void *),&free(void *),wistd::integral_constant<unsigned __int64,0>,SPIPCMSG *,SPIPCMSG *,0,std::nullptr_t>>(void)
0x18005a8aa  mov     eax, ebx
0x18005a8ac  mov     rbx, [rsp+40h+arg_0]
0x18005a8b1  mov     rsi, [rsp+40h+arg_8]
0x18005a8b6  add     rsp, 40h
0x18005a8ba  pop     r14
0x18005a8bc  pop     rdi
0x18005a8bd  pop     rbp
0x18005a8be  retn
```
