# Windows::Internal::StateRepository::SecondaryTileUserNotificationChannelFactoryServer::CreateForUserSecurityIdentifier(uint,uchar *,Windows::Internal::StateRepository::ISecondaryTileUserNotificationChannel * *)

- ea: `0x18011d1f0`
- end: `0x18011d3f4`
- name: `?CreateForUserSecurityIdentifier@SecondaryTileUserNotificationChannelFactoryServer@StateRepository@Internal@Windows@@UEAAJIPEAEPEAPEAUISecondaryTileUserNotificationChannel@234@@Z`
- size: `516`
- prototype: `int(Windows::Internal::StateRepository::SecondaryTileUserNotificationChannelFactoryServer *__hidden this, unsigned int, unsigned __int8 *, struct Windows::Internal::StateRepository::ISecondaryTileUserNotificationChannel **)`
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
- `0x18011d1f0`
- `0x18018f650`
- `0x1801a4300`
- `0x18027e010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18011d2d9`
- `ntdll!RtlLengthSid` at `0x18011d2d9`
- `ntdll!RtlValidSid` at `0x18011d2a7`
- `ntdll!RtlValidSid` at `0x18011d2a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011d339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011d38f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011d3b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011d339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011d38f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011d3b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18011d312`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18011d312`

## string_xrefs

- `0x18011d239`: `SecondaryTileUserNotificationChannelStatics::CreateForUserSecurityIdentifier`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::SecondaryTileUserNotificationChannelFactoryServer::CreateForUserSecurityIdentifier(
        Windows::Internal::StateRepository::SecondaryTileUserNotificationChannelFactoryServer *this,
        int a2,
        unsigned __int8 *a3,
        struct Windows::Internal::StateRepository::ISecondaryTileUserNotificationChannel **a4)
{
  WINBOOL v8; // ebx
  BlockRequests *v9; // rcx
  unsigned int LastError; // ebx
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 (__fastcall *v13)(Windows::Internal::StateRepository::SecondaryTileUserNotificationChannelFactoryServer *, _QWORD, struct Windows::Internal::StateRepository::ISecondaryTileUserNotificationChannel **); // rdi
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
  v20 = "SecondaryTileUserNotificationChannelStatics::CreateForUserSecurityIdentifier";
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
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.sec"
                      "ondarytileusernotificationchannelfactory.cpp",
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
    v13 = *(__int64 (__fastcall **)(Windows::Internal::StateRepository::SecondaryTileUserNotificationChannelFactoryServer *, _QWORD, struct Windows::Internal::StateRepository::ISecondaryTileUserNotificationChannel **))(*(_QWORD *)this + 56LL);
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
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.sec"
                      "ondarytileusernotificationchannelfactory.cpp",
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
                                "sitory.secondarytileusernotificationchannelfactory.cpp",
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
0x18011d1f0  mov     [rsp-8+arg_8], rbx
0x18011d1f5  push    rbp
0x18011d1f6  push    rsi
0x18011d1f7  push    rdi
0x18011d1f8  push    r14
0x18011d1fa  push    r15
0x18011d1fc  lea     rbp, [rsp-0C0h]
0x18011d204  sub     rsp, 1C0h
0x18011d20b  mov     rax, cs:__security_cookie
0x18011d212  xor     rax, rsp
0x18011d215  mov     [rbp+0E0h+var_30], rax
0x18011d21c  mov     r14d, edx
0x18011d21f  mov     r15, rcx
0x18011d222  xor     edx, edx; bool
0x18011d224  lea     rcx, [rsp+1E0h+var_1A8]; this
0x18011d229  mov     rsi, r9
0x18011d22c  mov     rdi, r8
0x18011d22f  call    ??0RequestInProgress@Client@WinRT@StateRepository@@QEAA@_N@Z; StateRepository::WinRT::Client::RequestInProgress::RequestInProgress(bool)
0x18011d234  mov     rbx, qword ptr [rsp+1E0h+var_1A8]
0x18011d239  lea     rax, aSecondarytileu_58; "SecondaryTileUserNotificationChannelSta"...
0x18011d240  lea     r8, [rsp+1E0h+var_1C0]
0x18011d245  mov     [rsp+1E0h+var_1B0], rax
0x18011d24a  lea     rdx, [rsp+1E0h+var_1B0]
0x18011d24f  mov     [rsp+1E0h+var_1C0], ebx; int
0x18011d253  lea     rcx, [rsp+1E0h+var_180]; this
0x18011d258  call    ??$Start@AEAPEBDI@Method@API@WinRT@Trace@StateRepository@@SA?AV01234@AEAPEBD$$QEAI@Z; StateRepository::Trace::WinRT::API::Method::Start<char const * &,uint>(char const * &,uint &&)
0x18011d25d  call    ?IsCurrentThreadUnblocked@BlockRequests@@QEAA_NXZ; BlockRequests::IsCurrentThreadUnblocked(void)
0x18011d262  test    al, al
0x18011d264  jnz     short loc_18011D2A4
0x18011d266  mov     rax, cs:qword_1804E01A0
0x18011d26d  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x18011d272  mov     eax, [rsp+1E0h+var_1C0+4]
0x18011d276  test    al, 2
0x18011d278  jz      short loc_18011D281
0x18011d27a  mov     ebx, 8007045Bh
0x18011d27f  jmp     short loc_18011D29D
0x18011d281  mov     eax, [rsp+1E0h+var_1C0+4]
0x18011d285  test    al, 1
0x18011d287  jz      short loc_18011D290
0x18011d289  mov     ebx, 80670010h
0x18011d28e  jmp     short loc_18011D29D
0x18011d290  mov     eax, [rsp+1E0h+var_1C0]
0x18011d294  test    eax, eax
0x18011d296  jz      short loc_18011D2A4
0x18011d298  mov     ebx, 80670006h
0x18011d29d  mov     edx, 6Dh ; 'm'
0x18011d2a2  jmp     short loc_18011D2BB
0x18011d2a4  mov     rcx, rdi; Sid
0x18011d2a7  call    cs:__imp_RtlValidSid
0x18011d2ad  test    al, al
0x18011d2af  jnz     short loc_18011D2D6
0x18011d2b1  mov     edx, 6Fh ; 'o'; void *
0x18011d2b6  mov     ebx, 80070057h
0x18011d2bb  mov     rcx, [rbp+0E8h]; this
0x18011d2c2  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18011d2c9  mov     r9d, ebx; char *
0x18011d2cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011d2d1  jmp     loc_18011D3B8
0x18011d2d6  mov     rcx, rdi; Sid
0x18011d2d9  call    cs:__imp_RtlLengthSid
0x18011d2df  cmp     eax, r14d
0x18011d2e2  jz      short loc_18011D2EB
0x18011d2e4  mov     edx, 70h ; 'p'
0x18011d2e9  jmp     short loc_18011D2B6
0x18011d2eb  test    rsi, rsi
0x18011d2ee  jnz     short loc_18011D2FA
0x18011d2f0  mov     ebx, 80004003h
0x18011d2f5  lea     edx, [rsi+71h]
0x18011d2f8  jmp     short loc_18011D2BB
0x18011d2fa  lea     rdx, [rsp+1E0h+StringSid]; StringSid
0x18011d2ff  mov     qword ptr [rsi], 0
0x18011d306  mov     rcx, rdi; Sid
0x18011d309  mov     [rsp+1E0h+StringSid], 0
0x18011d312  call    cs:__imp_ConvertSidToStringSidW
0x18011d318  test    eax, eax
0x18011d31a  jnz     short loc_18011D341
0x18011d31c  mov     rcx, [rbp+0E8h]; this
0x18011d323  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18011d32a  lea     edx, [rax+76h]; void *
0x18011d32d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011d332  mov     rcx, [rsp+1E0h+StringSid]; hMem
0x18011d337  mov     ebx, eax
0x18011d339  call    cs:__imp_LocalFree
0x18011d33f  jmp     short loc_18011D3B8
0x18011d341  mov     rax, [r15]
0x18011d344  lea     rdx, [rsp+1E0h+StringSid]
0x18011d349  lea     rcx, [rsp+1E0h+var_1A0]
0x18011d34e  mov     rdi, [rax+38h]
0x18011d352  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18011d357  mov     r8, rsi
0x18011d35a  mov     rcx, r15
0x18011d35d  mov     rdx, [rax+18h]
0x18011d361  mov     rax, rdi
0x18011d364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d369  mov     edi, eax
0x18011d36b  test    eax, eax
0x18011d36d  jns     short loc_18011D399
0x18011d36f  mov     rcx, [rbp+0E8h]; this
0x18011d376  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18011d37d  mov     r9d, eax; char *
0x18011d380  mov     edx, 77h ; 'w'; void *
0x18011d385  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011d38a  mov     rcx, [rsp+1E0h+StringSid]; hMem
0x18011d38f  call    cs:__imp_LocalFree
0x18011d395  mov     ebx, edi
0x18011d397  jmp     short loc_18011D3B8
0x18011d399  mov     rdx, [rsp+1E0h+var_1B0]; char *
0x18011d39e  lea     rcx, [rsp+1E0h+var_180]; this
0x18011d3a3  mov     r8d, ebx; unsigned int
0x18011d3a6  call    ?Stop@Method@API@WinRT@Trace@StateRepository@@QEAAXPEBDI@Z; StateRepository::Trace::WinRT::API::Method::Stop(char const *,uint)
0x18011d3ab  mov     rcx, [rsp+1E0h+StringSid]; hMem
0x18011d3b0  call    cs:__imp_LocalFree
0x18011d3b6  xor     ebx, ebx
0x18011d3b8  lea     rcx, [rsp+1E0h+var_180]; this
0x18011d3bd  call    ??1Method@API@WinRT@Trace@StateRepository@@QEAA@XZ; StateRepository::Trace::WinRT::API::Method::~Method(void)
0x18011d3c2  lea     rcx, [rsp+1E0h+var_1A8]; this
0x18011d3c7  call    ??1RequestInProgress@Client@WinRT@StateRepository@@QEAA@XZ; StateRepository::WinRT::Client::RequestInProgress::~RequestInProgress(void)
0x18011d3cc  mov     eax, ebx
0x18011d3ce  mov     rcx, [rbp+0E0h+var_30]
0x18011d3d5  xor     rcx, rsp; StackCookie
0x18011d3d8  call    __security_check_cookie
0x18011d3dd  mov     rbx, [rsp+1E0h+arg_8]
0x18011d3e5  add     rsp, 1C0h
0x18011d3ec  pop     r15
0x18011d3ee  pop     r14
0x18011d3f0  pop     rdi
0x18011d3f1  pop     rsi
0x18011d3f2  pop     rbp
0x18011d3f3  retn
```
