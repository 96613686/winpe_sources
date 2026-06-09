# CheckComClientUserSid

- ea: `0x1800514b4`
- end: `0x1800516a7`
- name: `CheckComClientUserSid`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800513d0`

## callees

- `0x18003ccf8`
- `0x1800514b4`
- `0x1800516b0`
- `0x1800516f0`
- `0x1800517bc`
- `0x180063500`
- `0x180071508`
- `0x180080fb0`
- `0x180081b40`
- `0x180088cf4`
- `0x180088d68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800514e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800514e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800514fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800514fd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800515cd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800515f8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800515cd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800515f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005153b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005153b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180051522`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18005154c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180051522`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18005154c`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x180051612`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x180051628`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x180051612`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x180051628`

## string_xrefs

- `0x18005150b`: `onecoreuap\inetcore\webplatstorageserver\dll\broker.cpp`
- `0x180051583`: `onecoreuap\inetcore\webplatstorageserver\dll\broker.cpp`
- `0x1800515af`: `onecoreuap\inetcore\webplatstorageserver\dll\broker.cpp`
- `0x180051658`: `onecoreuap\inetcore\webplatstorageserver\dll\broker.cpp`
- `0x180051644`: `Server SID:[%hs], Client SID:[%hs]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CheckComClientUserSid()
{
  HANDLE CurrentThread; // rax
  const char *v1; // r9
  unsigned int LastError; // ebx
  int TokenUserSid; // eax
  int ServerUserSid; // eax
  int v6; // [rsp+20h] [rbp-59h]
  _BYTE v7[8]; // [rsp+40h] [rbp-39h] BYREF
  PSID pSid2; // [rsp+48h] [rbp-31h] BYREF
  _DWORD v9[4]; // [rsp+50h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-19h] BYREF
  LPSTR StringSid; // [rsp+68h] [rbp-11h] BYREF
  _BYTE pSid1[80]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  TokenHandle = 0;
  wil::CoImpersonateClient_failfast(v7);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3E,
                  (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\dll\\broker.cpp",
                  v1);
    if ( v7[0] )
      CoRevertToSelf();
    goto LABEL_4;
  }
  if ( v7[0] )
    CoRevertToSelf();
  pSid2 = 0;
  memset_0(pSid1, 0, 0x44u);
  TokenUserSid = GetTokenUserSid(TokenHandle, pSid1);
  LastError = TokenUserSid;
  if ( TokenUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\dll\\broker.cpp",
      (const char *)(unsigned int)TokenUserSid,
      v6);
LABEL_16:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastError;
  }
  ServerUserSid = GetServerUserSid(&pSid2);
  LastError = ServerUserSid;
  if ( ServerUserSid >= 0 )
  {
    if ( EqualSid(pSid1, pSid2) || (v9[0] = 257, v9[1] = 83886080, v9[2] = 18, EqualSid(pSid1, v9)) )
    {
      LastError = 0;
    }
    else
    {
      StringSid = 0;
      ConvertSidToStringSidA(pSid2, &StringSid);
      pSid2 = 0;
      ConvertSidToStringSidA(pSid1, (LPSTR *)&pSid2);
      LastError = -2147024891;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\dll\\broker.cpp",
        (const char *)0x80070005LL,
        (int)"Server SID:[%hs], Client SID:[%hs]",
        StringSid,
        pSid2);
      wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&pSid2);
      wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(&StringSid);
    }
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A,
    (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\dll\\broker.cpp",
    (const char *)(unsigned int)ServerUserSid,
    v6);
LABEL_4:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800514b4  mov     [rsp-8+arg_0], rbx
0x1800514b9  push    rbp
0x1800514ba  lea     rbp, [rsp-57h]
0x1800514bf  sub     rsp, 0D0h
0x1800514c6  mov     rax, cs:__security_cookie
0x1800514cd  xor     rax, rsp
0x1800514d0  mov     [rbp+57h+var_10], rax
0x1800514d4  mov     [rbp+57h+TokenHandle], 0
0x1800514dc  lea     rcx, [rbp+57h+var_90]
0x1800514e0  call    ?CoImpersonateClient_failfast@wil@@YA?AV?$unique_call@P6AJXZ$1?CoRevertToSelf@@YAJXZ$00@1@XZ; wil::CoImpersonateClient_failfast(void)
0x1800514e5  call    cs:__imp_GetCurrentThread
0x1800514eb  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800514ef  mov     edx, 20008h; DesiredAccess
0x1800514f4  mov     r8d, 1; OpenAsSelf
0x1800514fa  mov     rcx, rax; ThreadHandle
0x1800514fd  call    cs:__imp_OpenThreadToken
0x180051503  test    eax, eax
0x180051505  jnz     short loc_180051546
0x180051507  mov     rcx, [rbp+5Fh]; this
0x18005150b  lea     r8, aOnecoreuapInet_26; "onecoreuap\\inetcore\\webplatstorageser"...
0x180051512  lea     edx, [rax+3Eh]; void *
0x180051515  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005151a  mov     ebx, eax
0x18005151c  cmp     [rbp+57h+var_90], 0
0x180051520  jz      short loc_180051529
0x180051522  call    cs:__imp_CoRevertToSelf
0x180051528  nop
0x180051529  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18005152d  lea     rdx, [rcx-1]
0x180051531  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180051535  ja      loc_180051688
0x18005153b  call    cs:__imp_CloseHandle
0x180051541  jmp     loc_180051688
0x180051546  cmp     [rbp+57h+var_90], 0
0x18005154a  jz      short loc_180051552
0x18005154c  call    cs:__imp_CoRevertToSelf
0x180051552  mov     [rbp+57h+pSid2], 0
0x18005155a  xor     edx, edx; Val
0x18005155c  lea     r8d, [rdx+44h]; Size
0x180051560  lea     rcx, [rbp+57h+pSid1]; void *
0x180051564  call    memset_0
0x180051569  lea     rdx, [rbp+57h+pSid1]; pDestinationSid
0x18005156d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180051571  call    GetTokenUserSid
0x180051576  mov     ebx, eax
0x180051578  test    eax, eax
0x18005157a  jns     short loc_180051599
0x18005157c  mov     rcx, [rbp+5Fh]; this
0x180051580  mov     r9d, eax; char *
0x180051583  lea     r8, aOnecoreuapInet_26; "onecoreuap\\inetcore\\webplatstorageser"...
0x18005158a  mov     edx, 49h ; 'I'; void *
0x18005158f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051594  jmp     loc_18005167F
0x180051599  lea     rcx, [rbp+57h+pSid2]
0x18005159d  call    GetServerUserSid
0x1800515a2  mov     ebx, eax
0x1800515a4  test    eax, eax
0x1800515a6  jns     short loc_1800515C5
0x1800515a8  mov     rcx, [rbp+5Fh]; this
0x1800515ac  mov     r9d, eax; char *
0x1800515af  lea     r8, aOnecoreuapInet_26; "onecoreuap\\inetcore\\webplatstorageser"...
0x1800515b6  mov     edx, 4Ah ; 'J'; void *
0x1800515bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800515c0  jmp     loc_180051529
0x1800515c5  mov     rdx, [rbp+57h+pSid2]; pSid2
0x1800515c9  lea     rcx, [rbp+57h+pSid1]; pSid1
0x1800515cd  call    cs:__imp_EqualSid
0x1800515d3  test    eax, eax
0x1800515d5  jnz     loc_18005167D
0x1800515db  mov     [rbp+57h+var_80], 101h
0x1800515e2  mov     [rbp+57h+var_7C], 5000000h
0x1800515e9  mov     [rbp+57h+var_78], 12h
0x1800515f0  lea     rdx, [rbp+57h+var_80]; pSid2
0x1800515f4  lea     rcx, [rbp+57h+pSid1]; pSid1
0x1800515f8  call    cs:__imp_EqualSid
0x1800515fe  test    eax, eax
0x180051600  jnz     short loc_18005167D
0x180051602  mov     [rbp+57h+StringSid], 0
0x18005160a  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18005160e  mov     rcx, [rbp+57h+pSid2]; Sid
0x180051612  call    cs:__imp_ConvertSidToStringSidA
0x180051618  mov     [rbp+57h+pSid2], 0
0x180051620  lea     rdx, [rbp+57h+pSid2]; StringSid
0x180051624  lea     rcx, [rbp+57h+pSid1]; Sid
0x180051628  call    cs:__imp_ConvertSidToStringSidA
0x18005162e  mov     rcx, [rbp+5Fh]; this
0x180051632  mov     rax, [rbp+57h+pSid2]
0x180051636  mov     [rsp+0D0h+var_A0], rax
0x18005163b  mov     rax, [rbp+57h+StringSid]
0x18005163f  mov     [rsp+0D0h+var_A8], rax; char *
0x180051644  lea     rax, aServerSidHsCli; "Server SID:[%hs], Client SID:[%hs]"
0x18005164b  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180051650  mov     ebx, 80070005h
0x180051655  mov     r9d, ebx; char *
0x180051658  lea     r8, aOnecoreuapInet_26; "onecoreuap\\inetcore\\webplatstorageser"...
0x18005165f  mov     edx, 56h ; 'V'; void *
0x180051664  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180051669  lea     rcx, [rbp+57h+pSid2]
0x18005166d  call    ??1?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x180051672  lea     rcx, [rbp+57h+StringSid]
0x180051676  call    ??1?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18005167b  jmp     short loc_18005167F
0x18005167d  xor     ebx, ebx
0x18005167f  lea     rcx, [rbp+57h+TokenHandle]
0x180051683  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180051688  mov     eax, ebx
0x18005168a  mov     rcx, [rbp+57h+var_10]
0x18005168e  xor     rcx, rsp; StackCookie
0x180051691  call    __security_check_cookie
0x180051696  mov     rbx, [rsp+0D0h+arg_0]
0x18005169e  add     rsp, 0D0h
0x1800516a5  pop     rbp
0x1800516a6  retn
```
