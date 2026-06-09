# Windows::System::Internal::UserManagerStatics::IsUserSignedIn(uint)

- ea: `0x180051470`
- end: `0x1800517ff`
- name: `?IsUserSignedIn@UserManagerStatics@Internal@System@Windows@@AEAA_NI@Z`
- size: `911`
- prototype: `bool __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this, unsigned int)`
- caller_count: `7`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800454c0`
- `0x180092dd4`
- `0x180095f78`
- `0x1800961b0`
- `0x180096548`
- `0x1800a163c`
- `0x1800a2e80`

## callees

- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x1800181f0`
- `0x1800332e8`
- `0x180050c38`
- `0x180051268`
- `0x180051470`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800517a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800517a1`
- `ntdll!RtlIsMultiSessionSku` at `0x1800514a6`
- `ntdll!RtlIsMultiSessionSku` at `0x1800514a6`

## string_xrefs

- `0x1800514be`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18005151b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180051544`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18005157d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800515a9`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180051607`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180051653`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800516b3`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800516e2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180051737`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18005175b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
char __fastcall Windows::System::Internal::UserManagerStatics::IsUserSignedIn(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2)
{
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // rsi
  __int64 (__fastcall *v5)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, _QWORD); // rbx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v20; // [rsp+20h] [rbp-88h]
  HSTRING string; // [rsp+30h] [rbp-78h] BYREF
  __int64 v22; // [rsp+38h] [rbp-70h] BYREF
  int v23; // [rsp+40h] [rbp-68h] BYREF
  _DWORD v24[3]; // [rsp+44h] [rbp-64h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp-58h] BYREF
  __int64 v26; // [rsp+58h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-48h] BYREF
  __int64 v28; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *(_QWORD *)&v24[1] = 0;
  if ( (unsigned __int8)RtlIsMultiSessionSku(this) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D0,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)0x80070032LL,
      v20);
  UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
  v5 = *(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)UserStaticsInternal + 136LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24[1]);
  v6 = v5(UserStaticsInternal, a2, 0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v6,
      (int)&v24[1]);
  if ( !*(_QWORD *)&v24[1] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D2,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)0x80070520LL,
      (int)&v24[1]);
  v23 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)&v24[1] + 56LL))(*(_QWORD *)&v24[1], &v23);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D4,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v7,
      (int)&v24[1]);
  if ( !v23 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D5,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)0x80070520LL,
      (int)&v24[1]);
  if ( v23 == 1 )
  {
    v22 = 0;
    string = 0;
    v8 = *((_QWORD *)this + 67);
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v10 = v9(v8, a2, &v22);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7DC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v10,
        (int)&v24[1]);
    v11 = v22;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 64LL);
    WindowsDeleteString(string);
    string = 0;
    v13 = v12(v11, &string);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7DD,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v13,
        (int)&v24[1]);
    if ( !string )
    {
      WindowsDeleteString(0);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24[1]);
      return 0;
    }
    v25 = 0;
    v26 = 0;
    v24[0] = 0;
    v14 = v22;
    v15 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v22 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v16 = v15(v14, &v25);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7E3,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v16,
        (int)&v24[1]);
    v17 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            &v25,
            (__int64)&v26);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7E5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v17,
        (int)&v24[1]);
    v28 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"lastSigninResult", 0x11u, 0x10u);
    v18 = Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<unsigned long>(v26, v28, (__int64)v24);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7E6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v18,
        (int)&v24[1]);
    if ( v24[0] < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7E7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)v24[0],
        (int)&v24[1]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24[1]);
  return 1;
}

```

## disassembly

```asm
0x180051470  mov     [rsp+arg_10], rbx
0x180051475  mov     [rsp+arg_18], rsi
0x18005147a  push    rdi
0x18005147b  push    r14
0x18005147d  push    r15
0x18005147f  sub     rsp, 90h
0x180051486  mov     rax, cs:__security_cookie
0x18005148d  xor     rax, rsp
0x180051490  mov     [rsp+0A8h+var_28], rax
0x180051498  mov     r14d, edx
0x18005149b  mov     rdi, rcx
0x18005149e  xor     r15d, r15d
0x1800514a1  mov     qword ptr [rsp+0A8h+var_64+4], r15
0x1800514a6  call    cs:__imp_RtlIsMultiSessionSku
0x1800514ac  mov     rcx, [rsp+0A8h]; this
0x1800514b4  test    al, al
0x1800514b6  jz      short loc_1800514CF
0x1800514b8  mov     r9d, 80070032h; char *
0x1800514be  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800514c5  mov     edx, 7D0h; void *
0x1800514ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800514cf  mov     rcx, rdi; this
0x1800514d2  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x1800514d7  mov     rsi, rax
0x1800514da  mov     rcx, [rax]
0x1800514dd  mov     rbx, [rcx+88h]
0x1800514e4  lea     rcx, [rsp+0A8h+var_64+4]
0x1800514e9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800514ee  lea     rax, [rsp+0A8h+var_64+4]
0x1800514f3  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x1800514f8  xor     r9d, r9d
0x1800514fb  xor     r8d, r8d
0x1800514fe  mov     edx, r14d
0x180051501  mov     rcx, rsi
0x180051504  mov     rax, rbx
0x180051507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005150c  mov     rcx, [rsp+0A8h]; this
0x180051514  test    eax, eax
0x180051516  jns     short loc_18005152C
0x180051518  mov     r9d, eax; char *
0x18005151b  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180051522  mov     edx, 7D1h; void *
0x180051527  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005152c  mov     rax, [rsp+0A8h]
0x180051534  mov     rcx, qword ptr [rsp+0A8h+var_64+4]
0x180051539  test    rcx, rcx
0x18005153c  jnz     short loc_180051558
0x18005153e  mov     r9d, 80070520h; char *
0x180051544  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18005154b  mov     edx, 7D2h; void *
0x180051550  mov     rcx, rax; this
0x180051553  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180051558  mov     [rsp+0A8h+var_68], r15d
0x18005155d  mov     rax, [rcx]
0x180051560  lea     rdx, [rsp+0A8h+var_68]
0x180051565  mov     rax, [rax+38h]
0x180051569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005156e  mov     rcx, [rsp+0A8h]; this
0x180051576  test    eax, eax
0x180051578  jns     short loc_18005158E
0x18005157a  mov     r9d, eax; char *
0x18005157d  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180051584  mov     edx, 7D4h; void *
0x180051589  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005158e  mov     edx, [rsp+0A8h+var_68]
0x180051592  test    edx, edx
0x180051594  setz    al
0x180051597  mov     rcx, [rsp+0A8h]; this
0x18005159f  test    al, al
0x1800515a1  jz      short loc_1800515BA
0x1800515a3  mov     r9d, 80070520h; char *
0x1800515a9  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800515b0  mov     edx, 7D5h; void *
0x1800515b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800515ba  cmp     edx, 1
0x1800515bd  jnz     loc_1800517C5
0x1800515c3  mov     [rsp+0A8h+var_70], r15
0x1800515c8  mov     [rsp+0A8h+string], r15
0x1800515cd  mov     rdi, [rdi+218h]
0x1800515d4  mov     rax, [rdi]
0x1800515d7  mov     rbx, [rax+60h]
0x1800515db  lea     rcx, [rsp+0A8h+var_70]
0x1800515e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800515e5  lea     r8, [rsp+0A8h+var_70]
0x1800515ea  mov     edx, r14d
0x1800515ed  mov     rcx, rdi
0x1800515f0  mov     rax, rbx
0x1800515f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515f8  mov     rcx, [rsp+0A8h]; this
0x180051600  test    eax, eax
0x180051602  jns     short loc_180051618
0x180051604  mov     r9d, eax; char *
0x180051607  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18005160e  mov     edx, 7DCh; void *
0x180051613  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180051618  mov     rdi, [rsp+0A8h+var_70]
0x18005161d  mov     rax, [rdi]
0x180051620  mov     rbx, [rax+40h]
0x180051624  mov     rcx, [rsp+0A8h+string]; string
0x180051629  call    cs:__imp_WindowsDeleteString
0x18005162f  mov     [rsp+0A8h+string], r15
0x180051634  lea     rdx, [rsp+0A8h+string]
0x180051639  mov     rcx, rdi
0x18005163c  mov     rax, rbx
0x18005163f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051644  mov     rcx, [rsp+0A8h]; this
0x18005164c  test    eax, eax
0x18005164e  jns     short loc_180051664
0x180051650  mov     r9d, eax; char *
0x180051653  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18005165a  mov     edx, 7DDh; void *
0x18005165f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180051664  cmp     [rsp+0A8h+string], r15
0x180051669  jz      loc_18005179F
0x18005166f  mov     [rsp+0A8h+var_58], r15
0x180051674  mov     [rsp+0A8h+var_50], r15
0x180051679  mov     dword ptr [rsp+0A8h+var_64], r15d
0x18005167e  mov     rdi, [rsp+0A8h+var_70]
0x180051683  mov     rax, [rdi]
0x180051686  mov     rbx, [rax+58h]
0x18005168a  lea     rcx, [rsp+0A8h+var_58]
0x18005168f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051694  lea     rdx, [rsp+0A8h+var_58]
0x180051699  mov     rcx, rdi
0x18005169c  mov     rax, rbx
0x18005169f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516a4  mov     rcx, [rsp+0A8h]; this
0x1800516ac  test    eax, eax
0x1800516ae  jns     short loc_1800516C4
0x1800516b0  mov     r9d, eax; char *
0x1800516b3  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800516ba  mov     edx, 7E3h; void *
0x1800516bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800516c4  lea     rdx, [rsp+0A8h+var_50]
0x1800516c9  lea     rcx, [rsp+0A8h+var_58]
0x1800516ce  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800516d3  mov     rcx, [rsp+0A8h]; this
0x1800516db  test    eax, eax
0x1800516dd  jns     short loc_1800516F3
0x1800516df  mov     r9d, eax; char *
0x1800516e2  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800516e9  mov     edx, 7E5h; void *
0x1800516ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800516f3  mov     [rsp+0A8h+var_30], r15
0x1800516f8  mov     r9d, 10h; unsigned int
0x1800516fe  lea     r8d, [r9+1]; unsigned int
0x180051702  lea     rdx, aLastsigninresu; "lastSigninResult"
0x180051709  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x18005170e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180051713  nop
0x180051714  lea     r8, [rsp+0A8h+var_64]
0x180051719  mov     rdx, [rsp+0A8h+var_30]
0x18005171e  mov     rcx, [rsp+0A8h+var_50]
0x180051723  call    ??$FromPropertyMap@K@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@PEAK@Z; Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<ulong>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,ulong *)
0x180051728  mov     rcx, [rsp+0A8h]; this
0x180051730  test    eax, eax
0x180051732  jns     short loc_180051749
0x180051734  mov     r9d, eax; char *
0x180051737  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18005173e  mov     edx, 7E6h; void *
0x180051743  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180051749  mov     r9d, dword ptr [rsp+0A8h+var_64]; char *
0x18005174e  mov     rcx, [rsp+0A8h]; this
0x180051756  test    r9d, r9d
0x180051759  jns     short loc_18005176D
0x18005175b  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180051762  mov     edx, 7E7h; void *
0x180051767  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005176d  lea     rcx, [rsp+0A8h+var_50]
0x180051772  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051777  nop
0x180051778  lea     rcx, [rsp+0A8h+var_58]
0x18005177d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180051782  nop
0x180051783  mov     rcx, [rsp+0A8h+string]; string
0x180051788  call    cs:__imp_WindowsDeleteString
0x18005178e  mov     [rsp+0A8h+string], r15
0x180051793  lea     rcx, [rsp+0A8h+var_70]
0x180051798  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005179d  jmp     short loc_1800517C5
0x18005179f  xor     ecx, ecx; string
0x1800517a1  call    cs:__imp_WindowsDeleteString
0x1800517a7  mov     [rsp+0A8h+string], r15
0x1800517ac  lea     rcx, [rsp+0A8h+var_70]
0x1800517b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800517b6  nop
0x1800517b7  lea     rcx, [rsp+0A8h+var_64+4]
0x1800517bc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800517c1  xor     al, al
0x1800517c3  jmp     short loc_1800517D5
0x1800517c5  lea     rcx, [rsp+0A8h+var_64+4]
0x1800517ca  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800517cf  mov     al, 1
0x1800517d1  jmp     short loc_1800517D5
0x1800517d3  xor     al, al
0x1800517d5  mov     rcx, [rsp+0A8h+var_28]
0x1800517dd  xor     rcx, rsp; StackCookie
0x1800517e0  call    __security_check_cookie
0x1800517e5  lea     r11, [rsp+0A8h+var_18]
0x1800517ed  mov     rbx, [r11+30h]
0x1800517f1  mov     rsi, [r11+38h]
0x1800517f5  mov     rsp, r11
0x1800517f8  pop     r15
0x1800517fa  pop     r14
0x1800517fc  pop     rdi
0x1800517fd  retn
```
