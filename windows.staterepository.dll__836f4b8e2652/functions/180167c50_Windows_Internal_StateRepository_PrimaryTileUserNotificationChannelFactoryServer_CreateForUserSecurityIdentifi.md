# Windows::Internal::StateRepository::PrimaryTileUserNotificationChannelFactoryServer::CreateForUserSecurityIdentifier(uint,uchar *,Windows::Internal::StateRepository::IPrimaryTileUserNotificationChannel * *)

- ea: `0x180167c50`
- end: `0x180167e54`
- name: `?CreateForUserSecurityIdentifier@PrimaryTileUserNotificationChannelFactoryServer@StateRepository@Internal@Windows@@UEAAJIPEAEPEAPEAUIPrimaryTileUserNotificationChannel@234@@Z`
- size: `516`
- prototype: `int(Windows::Internal::StateRepository::PrimaryTileUserNotificationChannelFactoryServer *__hidden this, unsigned int, unsigned __int8 *, struct Windows::Internal::StateRepository::IPrimaryTileUserNotificationChannel **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a834`
- `0x18000ad44`
- `0x18000b380`
- `0x18000c73c`
- `0x18000ca84`
- `0x18000d170`
- `0x18000e8dc`
- `0x18001a9e0`
- `0x180167c50`
- `0x18018f650`
- `0x1801a4300`
- `0x18027e010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180167d39`
- `ntdll!RtlLengthSid` at `0x180167d39`
- `ntdll!RtlValidSid` at `0x180167d07`
- `ntdll!RtlValidSid` at `0x180167d07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180167d99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180167def`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180167e10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180167d99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180167def`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180167e10`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180167d72`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180167d72`

## string_xrefs

- `0x180167c99`: `PrimaryTileUserNotificationChannelStatics::CreateForUserSecurityIdentifier`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PrimaryTileUserNotificationChannelFactoryServer::CreateForUserSecurityIdentifier(
        Windows::Internal::StateRepository::PrimaryTileUserNotificationChannelFactoryServer *this,
        int a2,
        unsigned __int8 *a3,
        struct Windows::Internal::StateRepository::IPrimaryTileUserNotificationChannel **a4)
{
  WINBOOL v8; // ebx
  BlockRequests *v9; // rcx
  unsigned int LastError; // ebx
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 (__fastcall *v13)(Windows::Internal::StateRepository::PrimaryTileUserNotificationChannelFactoryServer *, _QWORD, struct Windows::Internal::StateRepository::IPrimaryTileUserNotificationChannel **); // rdi
  __int64 v14; // rax
  int v15; // eax
  unsigned int v16; // edi
  int v18; // [rsp+20h] [rbp-E0h]
  LPWSTR StringSid; // [rsp+28h] [rbp-D8h] BYREF
  char *v20; // [rsp+30h] [rbp-D0h]
  unsigned int v21[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v22[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[336]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(
    (StateRepository::WinRT::Client::RequestInProgress *)v21,
    0);
  v8 = v21[0];
  v20 = "PrimaryTileUserNotificationChannelStatics::CreateForUserSecurityIdentifier";
  v18 = v21[0];
  StateRepository::Trace::WinRT::API::Method::Start<char const * &,unsigned int>((StateRepository::Trace::WinRT::API::Method *)v23);
  if ( !BlockRequests::IsCurrentThreadUnblocked(v9) )
  {
    v18 = qword_1804E01A0;
    if ( (*(_BYTE *)(&qword_1804E01A0 + 1) & 2) != 0 )
    {
      LastError = -2147023781;
LABEL_8:
      v11 = 109;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.pri"
                      "marytileusernotificationchannelfactory.cpp",
        (const char *)LastError,
        v18);
      goto LABEL_22;
    }
    if ( (*(_BYTE *)(&qword_1804E01A0 + 1) & 1) != 0 )
    {
      LastError = -2140733424;
      goto LABEL_8;
    }
    if ( qword_1804E01A0 )
    {
      LastError = -2140733434;
      goto LABEL_8;
    }
  }
  if ( !RtlValidSid(a3) )
  {
    v11 = 111;
LABEL_11:
    LastError = -2147024809;
    goto LABEL_12;
  }
  if ( RtlLengthSid(a3) != a2 )
  {
    v11 = 112;
    goto LABEL_11;
  }
  if ( !a4 )
  {
    LastError = -2147467261;
    v11 = 113;
    goto LABEL_12;
  }
  *a4 = 0;
  StringSid = 0;
  if ( ConvertSidToStringSidW(a3, &StringSid) )
  {
    v13 = *(__int64 (__fastcall **)(Windows::Internal::StateRepository::PrimaryTileUserNotificationChannelFactoryServer *, _QWORD, struct Windows::Internal::StateRepository::IPrimaryTileUserNotificationChannel **))(*(_QWORD *)this + 56LL);
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v22, &StringSid);
    v15 = v13(this, *(_QWORD *)(v14 + 24), a4);
    v16 = v15;
    if ( v15 >= 0 )
    {
      StateRepository::Trace::WinRT::API::Method::Stop((StateRepository::Trace::WinRT::API::Method *)v23, v20, v8);
      LocalFree(StringSid);
      LastError = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.pri"
                      "marytileusernotificationchannelfactory.cpp",
        (const char *)(unsigned int)v15,
        v18);
      LocalFree(StringSid);
      LastError = v16;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x76,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepo"
                                "sitory.primarytileusernotificationchannelfactory.cpp",
                  v12);
    LocalFree(StringSid);
  }
LABEL_22:
  StateRepository::Trace::WinRT::API::Method::~Method((StateRepository::Trace::WinRT::API::Method *)v23);
  StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress((StateRepository::WinRT::Client::RequestInProgress *)v21);
  return LastError;
}

```

## disassembly

```asm
0x180167c50  mov     [rsp-8+arg_8], rbx
0x180167c55  push    rbp
0x180167c56  push    rsi
0x180167c57  push    rdi
0x180167c58  push    r14
0x180167c5a  push    r15
0x180167c5c  lea     rbp, [rsp-0C0h]
0x180167c64  sub     rsp, 1C0h
0x180167c6b  mov     rax, cs:__security_cookie
0x180167c72  xor     rax, rsp
0x180167c75  mov     [rbp+0E0h+var_30], rax
0x180167c7c  mov     r14d, edx
0x180167c7f  mov     r15, rcx
0x180167c82  xor     edx, edx; bool
0x180167c84  lea     rcx, [rsp+1E0h+var_1A8]; this
0x180167c89  mov     rsi, r9
0x180167c8c  mov     rdi, r8
0x180167c8f  call    ??0RequestInProgress@Client@WinRT@StateRepository@@QEAA@_N@Z; StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(bool)
0x180167c94  mov     rbx, qword ptr [rsp+1E0h+var_1A8]
0x180167c99  lea     rax, aPrimarytileuse_48; "PrimaryTileUserNotificationChannelStati"...
0x180167ca0  lea     r8, [rsp+1E0h+var_1C0]
0x180167ca5  mov     [rsp+1E0h+var_1B0], rax
0x180167caa  lea     rdx, [rsp+1E0h+var_1B0]
0x180167caf  mov     [rsp+1E0h+var_1C0], ebx; int
0x180167cb3  lea     rcx, [rsp+1E0h+var_180]; this
0x180167cb8  call    ??$Start@AEAPEBDI@Method@API@WinRT@Trace@StateRepository@@SA?AV01234@AEAPEBD$$QEAI@Z; StateRepository::Trace::WinRT::API::Method::Start<char const * &,uint>(char const * &,uint &&)
0x180167cbd  call    ?IsCurrentThreadUnblocked@BlockRequests@@QEAA_NXZ; BlockRequests::IsCurrentThreadUnblocked(void)
0x180167cc2  test    al, al
0x180167cc4  jnz     short loc_180167D04
0x180167cc6  mov     rax, cs:qword_1804E01A0
0x180167ccd  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x180167cd2  mov     eax, [rsp+1E0h+var_1C0+4]
0x180167cd6  test    al, 2
0x180167cd8  jz      short loc_180167CE1
0x180167cda  mov     ebx, 8007045Bh
0x180167cdf  jmp     short loc_180167CFD
0x180167ce1  mov     eax, [rsp+1E0h+var_1C0+4]
0x180167ce5  test    al, 1
0x180167ce7  jz      short loc_180167CF0
0x180167ce9  mov     ebx, 80670010h
0x180167cee  jmp     short loc_180167CFD
0x180167cf0  mov     eax, [rsp+1E0h+var_1C0]
0x180167cf4  test    eax, eax
0x180167cf6  jz      short loc_180167D04
0x180167cf8  mov     ebx, 80670006h
0x180167cfd  mov     edx, 6Dh ; 'm'
0x180167d02  jmp     short loc_180167D1B
0x180167d04  mov     rcx, rdi; Sid
0x180167d07  call    cs:__imp_RtlValidSid
0x180167d0d  test    al, al
0x180167d0f  jnz     short loc_180167D36
0x180167d11  mov     edx, 6Fh ; 'o'; void *
0x180167d16  mov     ebx, 80070057h
0x180167d1b  mov     rcx, [rbp+0E8h]; this
0x180167d22  lea     r8, aOnecoreBaseApp_427; "onecore\\base\\appmodel\\staterepositor"...
0x180167d29  mov     r9d, ebx; char *
0x180167d2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180167d31  jmp     loc_180167E18
0x180167d36  mov     rcx, rdi; Sid
0x180167d39  call    cs:__imp_RtlLengthSid
0x180167d3f  cmp     eax, r14d
0x180167d42  jz      short loc_180167D4B
0x180167d44  mov     edx, 70h ; 'p'
0x180167d49  jmp     short loc_180167D16
0x180167d4b  test    rsi, rsi
0x180167d4e  jnz     short loc_180167D5A
0x180167d50  mov     ebx, 80004003h
0x180167d55  lea     edx, [rsi+71h]
0x180167d58  jmp     short loc_180167D1B
0x180167d5a  lea     rdx, [rsp+1E0h+StringSid]; StringSid
0x180167d5f  mov     qword ptr [rsi], 0
0x180167d66  mov     rcx, rdi; Sid
0x180167d69  mov     [rsp+1E0h+StringSid], 0
0x180167d72  call    cs:__imp_ConvertSidToStringSidW
0x180167d78  test    eax, eax
0x180167d7a  jnz     short loc_180167DA1
0x180167d7c  mov     rcx, [rbp+0E8h]; this
0x180167d83  lea     r8, aOnecoreBaseApp_427; "onecore\\base\\appmodel\\staterepositor"...
0x180167d8a  lea     edx, [rax+76h]; void *
0x180167d8d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180167d92  mov     rcx, [rsp+1E0h+StringSid]; hMem
0x180167d97  mov     ebx, eax
0x180167d99  call    cs:__imp_LocalFree
0x180167d9f  jmp     short loc_180167E18
0x180167da1  mov     rax, [r15]
0x180167da4  lea     rdx, [rsp+1E0h+StringSid]
0x180167da9  lea     rcx, [rsp+1E0h+var_1A0]
0x180167dae  mov     rdi, [rax+38h]
0x180167db2  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180167db7  mov     r8, rsi
0x180167dba  mov     rcx, r15
0x180167dbd  mov     rdx, [rax+18h]
0x180167dc1  mov     rax, rdi
0x180167dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167dc9  mov     edi, eax
0x180167dcb  test    eax, eax
0x180167dcd  jns     short loc_180167DF9
0x180167dcf  mov     rcx, [rbp+0E8h]; this
0x180167dd6  lea     r8, aOnecoreBaseApp_427; "onecore\\base\\appmodel\\staterepositor"...
0x180167ddd  mov     r9d, eax; char *
0x180167de0  mov     edx, 77h ; 'w'; void *
0x180167de5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180167dea  mov     rcx, [rsp+1E0h+StringSid]; hMem
0x180167def  call    cs:__imp_LocalFree
0x180167df5  mov     ebx, edi
0x180167df7  jmp     short loc_180167E18
0x180167df9  mov     rdx, [rsp+1E0h+var_1B0]; char *
0x180167dfe  lea     rcx, [rsp+1E0h+var_180]; this
0x180167e03  mov     r8d, ebx; unsigned int
0x180167e06  call    ?Stop@Method@API@WinRT@Trace@StateRepository@@QEAAXPEBDI@Z; StateRepository::Trace::WinRT::API::Method::Stop(char const *,uint)
0x180167e0b  mov     rcx, [rsp+1E0h+StringSid]; hMem
0x180167e10  call    cs:__imp_LocalFree
0x180167e16  xor     ebx, ebx
0x180167e18  lea     rcx, [rsp+1E0h+var_180]; this
0x180167e1d  call    ??1Method@API@WinRT@Trace@StateRepository@@QEAA@XZ; StateRepository::Trace::WinRT::API::Method::~Method(void)
0x180167e22  lea     rcx, [rsp+1E0h+var_1A8]; this
0x180167e27  call    ??1RequestInProgress@Client@WinRT@StateRepository@@QEAA@XZ; StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress(void)
0x180167e2c  mov     eax, ebx
0x180167e2e  mov     rcx, [rbp+0E0h+var_30]
0x180167e35  xor     rcx, rsp; StackCookie
0x180167e38  call    __security_check_cookie
0x180167e3d  mov     rbx, [rsp+1E0h+arg_8]
0x180167e45  add     rsp, 1C0h
0x180167e4c  pop     r15
0x180167e4e  pop     r14
0x180167e50  pop     rdi
0x180167e51  pop     rsi
0x180167e52  pop     rbp
0x180167e53  retn
```
