# VerifyCallerHAsAccessToProcess(CToken *,ulong,ulong,int *)

- ea: `0x1800ea3a8`
- end: `0x1800ea6a0`
- name: `?VerifyCallerHAsAccessToProcess@@YAJPEAVCToken@@KKPEAH@Z`
- size: `760`
- prototype: `__int64 __fastcall(HANDLE *, __int64, DWORD, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800eb6c0`

## callees

- `0x18002f058`
- `0x180034540`
- `0x180070740`
- `0x1800ea3a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea3db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea55a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea3db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea55a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea613`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ea676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ea684`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ea676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ea684`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1800ea54a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1800ea54a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800ea48d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800ea48d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ea605`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ea605`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ea3cd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ea3cd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ea68a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ea68a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea429`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea4ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea5a4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea659`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea429`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea4ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea5a4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ea659`

## string_xrefs

- `0x1800ea464`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x1800ea528`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x1800ea5df`: `onecore\com\combase\rpcss\olescm\scmif.cxx`
- `0x1800ea447`: `VerifyCallerHAsAccessToProcess`
- `0x1800ea50b`: `VerifyCallerHAsAccessToProcess`
- `0x1800ea5c8`: `VerifyCallerHAsAccessToProcess`

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
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1)) )
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
      if ( !dword_18014E4B8
        && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1))) )
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
      if ( !dword_18014E4B8
        && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1))) )
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
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)(dword_18014E4B8 + 1)) )
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
0x1800ea3a8  push    rbp
0x1800ea3aa  push    rbx
0x1800ea3ab  push    rsi
0x1800ea3ac  push    r13
0x1800ea3ae  push    r14
0x1800ea3b0  push    r15
0x1800ea3b2  mov     rbp, rsp
0x1800ea3b5  sub     rsp, 48h
0x1800ea3b9  mov     r13, rcx
0x1800ea3bc  mov     dword ptr [r9], 0
0x1800ea3c3  mov     rcx, [rcx+48h]; hToken
0x1800ea3c7  mov     r15, r9
0x1800ea3ca  mov     ebx, r8d
0x1800ea3cd  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ea3d3  test    eax, eax
0x1800ea3d5  jnz     loc_1800EA483
0x1800ea3db  call    cs:__imp_GetLastError
0x1800ea3e1  mov     ebx, eax
0x1800ea3e3  test    eax, eax
0x1800ea3e5  jle     short loc_1800EA3F0
0x1800ea3e7  movzx   ebx, ax
0x1800ea3ea  or      ebx, 80070000h
0x1800ea3f0  mov     eax, cs:dword_18014E4B8
0x1800ea3f6  test    eax, eax
0x1800ea3f8  jnz     short loc_1800EA416
0x1800ea3fa  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800ea400  jz      loc_1800EA690
0x1800ea406  lea     ecx, [rax+1]
0x1800ea409  call    IsWppLevelEnabled
0x1800ea40e  test    al, al
0x1800ea410  jz      loc_1800EA690
0x1800ea416  lea     rcx, [r13+9Ch]; Sid
0x1800ea41d  mov     [rbp+StringSid], 0
0x1800ea425  lea     rdx, [rbp+StringSid]; StringSid
0x1800ea429  call    cs:__imp_ConvertSidToStringSidW
0x1800ea42f  mov     rax, [rbp+StringSid]
0x1800ea433  lea     rcx, Class
0x1800ea43a  test    rax, rax
0x1800ea43d  mov     [rsp+48h+var_18], ebx
0x1800ea441  mov     r9d, 1
0x1800ea447  lea     rdx, aVerifycallerha; "VerifyCallerHAsAccessToProcess"
0x1800ea44e  cmovnz  rcx, rax
0x1800ea452  mov     r8d, 545h
0x1800ea458  mov     [rsp+48h+var_20], rcx
0x1800ea45d  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800ea464  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ea46b  mov     [rsp+48h+var_28], rax
0x1800ea470  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800ea475  lea     rcx, [rbp+StringSid]
0x1800ea479  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800ea47e  jmp     loc_1800EA690
0x1800ea483  mov     r8d, ebx; dwThreadId
0x1800ea486  xor     edx, edx; bInheritHandle
0x1800ea488  mov     ecx, 800h; dwDesiredAccess
0x1800ea48d  call    cs:__imp_OpenThread
0x1800ea493  mov     r14, rax
0x1800ea496  test    rax, rax
0x1800ea499  jnz     loc_1800EA547
0x1800ea49f  call    cs:__imp_GetLastError
0x1800ea4a5  mov     ebx, eax
0x1800ea4a7  test    eax, eax
0x1800ea4a9  jle     short loc_1800EA4B4
0x1800ea4ab  movzx   ebx, ax
0x1800ea4ae  or      ebx, 80070000h
0x1800ea4b4  mov     eax, cs:dword_18014E4B8
0x1800ea4ba  test    eax, eax
0x1800ea4bc  jnz     short loc_1800EA4DA
0x1800ea4be  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800ea4c4  jz      loc_1800EA68A
0x1800ea4ca  lea     ecx, [rax+1]
0x1800ea4cd  call    IsWppLevelEnabled
0x1800ea4d2  test    al, al
0x1800ea4d4  jz      loc_1800EA68A
0x1800ea4da  lea     rcx, [r13+9Ch]; Sid
0x1800ea4e1  mov     [rbp+StringSid], 0
0x1800ea4e9  lea     rdx, [rbp+StringSid]; StringSid
0x1800ea4ed  call    cs:__imp_ConvertSidToStringSidW
0x1800ea4f3  mov     rax, [rbp+StringSid]
0x1800ea4f7  lea     rcx, Class
0x1800ea4fe  test    rax, rax
0x1800ea501  mov     [rsp+48h+var_18], ebx
0x1800ea505  mov     r9d, 1
0x1800ea50b  lea     rdx, aVerifycallerha; "VerifyCallerHAsAccessToProcess"
0x1800ea512  cmovnz  rcx, rax
0x1800ea516  mov     r8d, 54Dh
0x1800ea51c  mov     [rsp+48h+var_20], rcx
0x1800ea521  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800ea528  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ea52f  mov     [rsp+48h+var_28], rax
0x1800ea534  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800ea539  lea     rcx, [rbp+StringSid]
0x1800ea53d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800ea542  jmp     loc_1800EA68A
0x1800ea547  mov     rcx, r14; Thread
0x1800ea54a  call    cs:__imp_GetProcessIdOfThread
0x1800ea550  test    eax, eax
0x1800ea552  jnz     loc_1800EA5FB
0x1800ea558  xor     esi, esi
0x1800ea55a  call    cs:__imp_GetLastError
0x1800ea560  mov     ebx, eax
0x1800ea562  test    eax, eax
0x1800ea564  jle     short loc_1800EA56F
0x1800ea566  movzx   ebx, ax
0x1800ea569  or      ebx, 80070000h
0x1800ea56f  mov     eax, cs:dword_18014E4B8
0x1800ea575  test    eax, eax
0x1800ea577  jnz     short loc_1800EA595
0x1800ea579  cmp     cs:?gfEnableTracing@@3HA, esi; int gfEnableTracing
0x1800ea57f  jz      loc_1800EA673
0x1800ea585  lea     ecx, [rax+1]
0x1800ea588  call    IsWppLevelEnabled
0x1800ea58d  test    al, al
0x1800ea58f  jz      loc_1800EA673
0x1800ea595  lea     rcx, [r13+9Ch]; Sid
0x1800ea59c  mov     [rbp+StringSid], rsi
0x1800ea5a0  lea     rdx, [rbp+StringSid]; StringSid
0x1800ea5a4  call    cs:__imp_ConvertSidToStringSidW
0x1800ea5aa  mov     r8d, 554h
0x1800ea5b0  mov     rax, [rbp+StringSid]
0x1800ea5b4  lea     rcx, Class
0x1800ea5bb  test    rax, rax
0x1800ea5be  mov     [rsp+48h+var_18], ebx
0x1800ea5c2  mov     r9d, 1
0x1800ea5c8  lea     rdx, aVerifycallerha; "VerifyCallerHAsAccessToProcess"
0x1800ea5cf  cmovnz  rcx, rax
0x1800ea5d3  lea     rax, aWsHresult; "%ws %!HRESULT!"
0x1800ea5da  mov     [rsp+48h+var_20], rcx
0x1800ea5df  lea     rcx, aOnecoreComComb_29; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800ea5e6  mov     [rsp+48h+var_28], rax
0x1800ea5eb  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x1800ea5f0  lea     rcx, [rbp+StringSid]
0x1800ea5f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800ea5f9  jmp     short loc_1800EA673
0x1800ea5fb  mov     r8d, eax; dwProcessId
0x1800ea5fe  xor     edx, edx; bInheritHandle
0x1800ea600  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1800ea605  call    cs:__imp_OpenProcess
0x1800ea60b  mov     rsi, rax
0x1800ea60e  test    rax, rax
0x1800ea611  jnz     short loc_1800EA66A
0x1800ea613  call    cs:__imp_GetLastError
0x1800ea619  mov     ebx, eax
0x1800ea61b  test    eax, eax
0x1800ea61d  jle     short loc_1800EA628
0x1800ea61f  movzx   ebx, ax
0x1800ea622  or      ebx, 80070000h
0x1800ea628  mov     eax, cs:dword_18014E4B8
0x1800ea62e  test    eax, eax
0x1800ea630  jnz     short loc_1800EA646
0x1800ea632  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800ea638  jz      short loc_1800EA673
0x1800ea63a  lea     ecx, [rax+1]
0x1800ea63d  call    IsWppLevelEnabled
0x1800ea642  test    al, al
0x1800ea644  jz      short loc_1800EA673
0x1800ea646  lea     rcx, [r13+9Ch]; Sid
0x1800ea64d  mov     [rbp+StringSid], 0
0x1800ea655  lea     rdx, [rbp+StringSid]; StringSid
0x1800ea659  call    cs:__imp_ConvertSidToStringSidW
0x1800ea65f  mov     r8d, 55Bh
0x1800ea665  jmp     loc_1800EA5B0
0x1800ea66a  xor     ebx, ebx
0x1800ea66c  mov     dword ptr [r15], 1
0x1800ea673  mov     rcx, r14; hObject
0x1800ea676  call    cs:__imp_CloseHandle
0x1800ea67c  test    rsi, rsi
0x1800ea67f  jz      short loc_1800EA68A
0x1800ea681  mov     rcx, rsi; hObject
0x1800ea684  call    cs:__imp_CloseHandle
0x1800ea68a  call    cs:__imp_RevertToSelf
0x1800ea690  mov     eax, ebx
0x1800ea692  add     rsp, 48h
0x1800ea696  pop     r15
0x1800ea698  pop     r14
0x1800ea69a  pop     r13
0x1800ea69c  pop     rsi
0x1800ea69d  pop     rbx
0x1800ea69e  pop     rbp
0x1800ea69f  retn
```
