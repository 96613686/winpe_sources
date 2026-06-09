# VerifyCallerHAsAccessToProcess(CToken *,ulong,ulong,int *)

- ea: `0x1800f1cb8`
- end: `0x1800f200e`
- name: `?VerifyCallerHAsAccessToProcess@@YAJPEAVCToken@@KKPEAH@Z`
- size: `854`
- prototype: `int(struct CToken *, unsigned int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800f3070`

## callees

- `0x180025088`
- `0x180034260`
- `0x180074d98`
- `0x1800f1cb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1cf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1cf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1f62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1fd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1fe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1fd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1fe5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1800f1e7e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1800f1e7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800f1daf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800f1daf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f1f4e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f1f4e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800f1cdd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800f1cdd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f1ff1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800f1ff1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1d45`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1e1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1ee4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1fae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1d45`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1e1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1ee4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f1fae`

## string_xrefs

- `0x1800f1d86`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x1800f1e5c`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x1800f1f25`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x1800f1d69`: `VerifyCallerHAsAccessToProcess`
- `0x1800f1e3f`: `VerifyCallerHAsAccessToProcess`
- `0x1800f1f0e`: `VerifyCallerHAsAccessToProcess`

## pseudocode

```c
__int64 __fastcall VerifyCallerHAsAccessToProcess(HANDLE *a1, __int64 a2, DWORD a3, int *a4)
{
  signed int v7; // eax
  unsigned int v8; // ebx
  LPWSTR v9; // rcx
  HANDLE v10; // rax
  void *v11; // r14
  signed int LastError; // eax
  LPWSTR v13; // rcx
  DWORD ProcessIdOfThread; // eax
  HANDLE v15; // rsi
  signed int v16; // eax
  int v17; // r8d
  LPWSTR v18; // rcx
  signed int v19; // eax
  LPWSTR StringSid; // [rsp+80h] [rbp+38h] BYREF

  *a4 = 0;
  if ( ImpersonateLoggedOnUser(a1[9]) )
  {
    v10 = OpenThread(0x800u, 0, a3);
    v11 = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1)) )
      {
        StringSid = 0;
        ConvertSidToStringSidW((char *)a1 + 156, &StringSid);
        v13 = (LPWSTR)&Class;
        if ( StringSid )
          v13 = StringSid;
        ComTraceMessageT<unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmif.cxx",
          (unsigned int)"VerifyCallerHAsAccessToProcess",
          1357,
          1,
          (__int64)L"%ws %!HRESULT!",
          v13,
          v8);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      }
LABEL_39:
      RevertToSelf();
      return v8;
    }
    ProcessIdOfThread = GetProcessIdOfThread(v10);
    if ( ProcessIdOfThread )
    {
      v15 = OpenProcess(0x1FFFFFu, 0, ProcessIdOfThread);
      if ( v15 )
      {
        v8 = 0;
        *a4 = 1;
LABEL_37:
        CloseHandle(v11);
        if ( v15 )
          CloseHandle(v15);
        goto LABEL_39;
      }
      v19 = GetLastError();
      v8 = v19;
      if ( v19 > 0 )
        v8 = (unsigned __int16)v19 | 0x80070000;
      if ( !dword_1801574B8
        && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1))) )
      {
        goto LABEL_37;
      }
      StringSid = 0;
      ConvertSidToStringSidW((char *)a1 + 156, &StringSid);
      v17 = 1371;
    }
    else
    {
      v15 = 0;
      v16 = GetLastError();
      v8 = v16;
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      if ( !dword_1801574B8
        && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1))) )
      {
        goto LABEL_37;
      }
      StringSid = 0;
      ConvertSidToStringSidW((char *)a1 + 156, &StringSid);
      v17 = 1364;
    }
    v18 = (LPWSTR)&Class;
    if ( StringSid )
      v18 = StringSid;
    ComTraceMessageT<unsigned short *,long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmif.cxx",
      (unsigned int)"VerifyCallerHAsAccessToProcess",
      v17,
      1,
      (__int64)L"%ws %!HRESULT!",
      v18,
      v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    goto LABEL_37;
  }
  v7 = GetLastError();
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_1801574B8 + 1)) )
  {
    StringSid = 0;
    ConvertSidToStringSidW((char *)a1 + 156, &StringSid);
    v9 = (LPWSTR)&Class;
    if ( StringSid )
      v9 = StringSid;
    ComTraceMessageT<unsigned short *,long>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\scmif.cxx",
      (unsigned int)"VerifyCallerHAsAccessToProcess",
      1349,
      1,
      (__int64)L"%ws %!HRESULT!",
      v9,
      v8);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  }
  return v8;
}

```

## disassembly

```asm
0x1800f1cb8  push    rbp
0x1800f1cba  push    rbx
0x1800f1cbb  push    rsi
0x1800f1cbc  push    r13
0x1800f1cbe  push    r14
0x1800f1cc0  push    r15
0x1800f1cc2  mov     rbp, rsp
0x1800f1cc5  sub     rsp, 48h
0x1800f1cc9  mov     r13, rcx
0x1800f1ccc  mov     dword ptr [r9], 0
0x1800f1cd3  mov     rcx, [rcx+48h]; hToken
0x1800f1cd7  mov     r15, r9
0x1800f1cda  mov     ebx, r8d
0x1800f1cdd  call    cs:__imp_ImpersonateLoggedOnUser
0x1800f1ce4  nop     dword ptr [rax+rax+00h]
0x1800f1ce9  test    eax, eax
0x1800f1ceb  jnz     loc_1800F1DA5
0x1800f1cf1  call    cs:__imp_GetLastError
0x1800f1cf8  nop     dword ptr [rax+rax+00h]
0x1800f1cfd  mov     ebx, eax
0x1800f1cff  test    eax, eax
0x1800f1d01  jle     short loc_1800F1D0C
0x1800f1d03  movzx   ebx, ax
0x1800f1d06  or      ebx, 80070000h
0x1800f1d0c  mov     eax, cs:dword_1801574B8
0x1800f1d12  test    eax, eax
0x1800f1d14  jnz     short loc_1800F1D32
0x1800f1d16  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f1d1c  jz      loc_1800F1FFD
0x1800f1d22  lea     ecx, [rax+1]
0x1800f1d25  call    IsWppLevelEnabled
0x1800f1d2a  test    al, al
0x1800f1d2c  jz      loc_1800F1FFD
0x1800f1d32  lea     rcx, [r13+9Ch]; Sid
0x1800f1d39  mov     [rbp+StringSid], 0
0x1800f1d41  lea     rdx, [rbp+StringSid]; StringSid
0x1800f1d45  call    cs:__imp_ConvertSidToStringSidW
0x1800f1d4c  nop     dword ptr [rax+rax+00h]
0x1800f1d51  mov     rax, [rbp+StringSid]
0x1800f1d55  lea     rcx, Class
0x1800f1d5c  test    rax, rax
0x1800f1d5f  mov     [rsp+48h+var_18], ebx
0x1800f1d63  mov     r9d, 1
0x1800f1d69  lea     rdx, aVerifycallerha; "VerifyCallerHAsAccessToProcess"
0x1800f1d70  cmovnz  rcx, rax
0x1800f1d74  mov     r8d, 545h
0x1800f1d7a  mov     [rsp+48h+var_20], rcx
0x1800f1d7f  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800f1d86  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f1d8d  mov     [rsp+48h+var_28], rax
0x1800f1d92  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800f1d97  lea     rcx, [rbp+StringSid]
0x1800f1d9b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f1da0  jmp     loc_1800F1FFD
0x1800f1da5  mov     r8d, ebx; dwThreadId
0x1800f1da8  xor     edx, edx; bInheritHandle
0x1800f1daa  mov     ecx, 800h; dwDesiredAccess
0x1800f1daf  call    cs:__imp_OpenThread
0x1800f1db6  nop     dword ptr [rax+rax+00h]
0x1800f1dbb  mov     r14, rax
0x1800f1dbe  test    rax, rax
0x1800f1dc1  jnz     loc_1800F1E7B
0x1800f1dc7  call    cs:__imp_GetLastError
0x1800f1dce  nop     dword ptr [rax+rax+00h]
0x1800f1dd3  mov     ebx, eax
0x1800f1dd5  test    eax, eax
0x1800f1dd7  jle     short loc_1800F1DE2
0x1800f1dd9  movzx   ebx, ax
0x1800f1ddc  or      ebx, 80070000h
0x1800f1de2  mov     eax, cs:dword_1801574B8
0x1800f1de8  test    eax, eax
0x1800f1dea  jnz     short loc_1800F1E08
0x1800f1dec  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f1df2  jz      loc_1800F1FF1
0x1800f1df8  lea     ecx, [rax+1]
0x1800f1dfb  call    IsWppLevelEnabled
0x1800f1e00  test    al, al
0x1800f1e02  jz      loc_1800F1FF1
0x1800f1e08  lea     rcx, [r13+9Ch]; Sid
0x1800f1e0f  mov     [rbp+StringSid], 0
0x1800f1e17  lea     rdx, [rbp+StringSid]; StringSid
0x1800f1e1b  call    cs:__imp_ConvertSidToStringSidW
0x1800f1e22  nop     dword ptr [rax+rax+00h]
0x1800f1e27  mov     rax, [rbp+StringSid]
0x1800f1e2b  lea     rcx, Class
0x1800f1e32  test    rax, rax
0x1800f1e35  mov     [rsp+48h+var_18], ebx
0x1800f1e39  mov     r9d, 1
0x1800f1e3f  lea     rdx, aVerifycallerha; "VerifyCallerHAsAccessToProcess"
0x1800f1e46  cmovnz  rcx, rax
0x1800f1e4a  mov     r8d, 54Dh
0x1800f1e50  mov     [rsp+48h+var_20], rcx
0x1800f1e55  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800f1e5c  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f1e63  mov     [rsp+48h+var_28], rax
0x1800f1e68  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800f1e6d  lea     rcx, [rbp+StringSid]
0x1800f1e71  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f1e76  jmp     loc_1800F1FF1
0x1800f1e7b  mov     rcx, r14; Thread
0x1800f1e7e  call    cs:__imp_GetProcessIdOfThread
0x1800f1e85  nop     dword ptr [rax+rax+00h]
0x1800f1e8a  test    eax, eax
0x1800f1e8c  jnz     loc_1800F1F44
0x1800f1e92  xor     esi, esi
0x1800f1e94  call    cs:__imp_GetLastError
0x1800f1e9b  nop     dword ptr [rax+rax+00h]
0x1800f1ea0  mov     ebx, eax
0x1800f1ea2  test    eax, eax
0x1800f1ea4  jle     short loc_1800F1EAF
0x1800f1ea6  movzx   ebx, ax
0x1800f1ea9  or      ebx, 80070000h
0x1800f1eaf  mov     eax, cs:dword_1801574B8
0x1800f1eb5  test    eax, eax
0x1800f1eb7  jnz     short loc_1800F1ED5
0x1800f1eb9  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x1800f1ebf  jz      loc_1800F1FCE
0x1800f1ec5  lea     ecx, [rax+1]
0x1800f1ec8  call    IsWppLevelEnabled
0x1800f1ecd  test    al, al
0x1800f1ecf  jz      loc_1800F1FCE
0x1800f1ed5  lea     rcx, [r13+9Ch]; Sid
0x1800f1edc  mov     [rbp+StringSid], rsi
0x1800f1ee0  lea     rdx, [rbp+StringSid]; StringSid
0x1800f1ee4  call    cs:__imp_ConvertSidToStringSidW
0x1800f1eeb  nop     dword ptr [rax+rax+00h]
0x1800f1ef0  mov     r8d, 554h
0x1800f1ef6  mov     rax, [rbp+StringSid]
0x1800f1efa  lea     rcx, Class
0x1800f1f01  test    rax, rax
0x1800f1f04  mov     [rsp+48h+var_18], ebx
0x1800f1f08  mov     r9d, 1
0x1800f1f0e  lea     rdx, aVerifycallerha; "VerifyCallerHAsAccessToProcess"
0x1800f1f15  cmovnz  rcx, rax
0x1800f1f19  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800f1f20  mov     [rsp+48h+var_20], rcx
0x1800f1f25  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800f1f2c  mov     [rsp+48h+var_28], rax
0x1800f1f31  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800f1f36  lea     rcx, [rbp+StringSid]
0x1800f1f3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f1f3f  jmp     loc_1800F1FCE
0x1800f1f44  mov     r8d, eax; dwProcessId
0x1800f1f47  xor     edx, edx; bInheritHandle
0x1800f1f49  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1800f1f4e  call    cs:__imp_OpenProcess
0x1800f1f55  nop     dword ptr [rax+rax+00h]
0x1800f1f5a  mov     rsi, rax
0x1800f1f5d  test    rax, rax
0x1800f1f60  jnz     short loc_1800F1FC5
0x1800f1f62  call    cs:__imp_GetLastError
0x1800f1f69  nop     dword ptr [rax+rax+00h]
0x1800f1f6e  mov     ebx, eax
0x1800f1f70  test    eax, eax
0x1800f1f72  jle     short loc_1800F1F7D
0x1800f1f74  movzx   ebx, ax
0x1800f1f77  or      ebx, 80070000h
0x1800f1f7d  mov     eax, cs:dword_1801574B8
0x1800f1f83  test    eax, eax
0x1800f1f85  jnz     short loc_1800F1F9B
0x1800f1f87  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f1f8d  jz      short loc_1800F1FCE
0x1800f1f8f  lea     ecx, [rax+1]
0x1800f1f92  call    IsWppLevelEnabled
0x1800f1f97  test    al, al
0x1800f1f99  jz      short loc_1800F1FCE
0x1800f1f9b  lea     rcx, [r13+9Ch]; Sid
0x1800f1fa2  mov     [rbp+StringSid], 0
0x1800f1faa  lea     rdx, [rbp+StringSid]; StringSid
0x1800f1fae  call    cs:__imp_ConvertSidToStringSidW
0x1800f1fb5  nop     dword ptr [rax+rax+00h]
0x1800f1fba  mov     r8d, 55Bh
0x1800f1fc0  jmp     loc_1800F1EF6
0x1800f1fc5  xor     ebx, ebx
0x1800f1fc7  mov     dword ptr [r15], 1
0x1800f1fce  mov     rcx, r14; hObject
0x1800f1fd1  call    cs:__imp_CloseHandle
0x1800f1fd8  nop     dword ptr [rax+rax+00h]
0x1800f1fdd  test    rsi, rsi
0x1800f1fe0  jz      short loc_1800F1FF1
0x1800f1fe2  mov     rcx, rsi; hObject
0x1800f1fe5  call    cs:__imp_CloseHandle
0x1800f1fec  nop     dword ptr [rax+rax+00h]
0x1800f1ff1  call    cs:__imp_RevertToSelf
0x1800f1ff8  nop     dword ptr [rax+rax+00h]
0x1800f1ffd  mov     eax, ebx
0x1800f1fff  add     rsp, 48h
0x1800f2003  pop     r15
0x1800f2005  pop     r14
0x1800f2007  pop     r13
0x1800f2009  pop     rsi
0x1800f200a  pop     rbx
0x1800f200b  pop     rbp
0x1800f200c  retn
```
