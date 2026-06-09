# Windows::System::Internal::UserManagerStatics::GetUserByName(HSTRING__ *,Windows::System::Internal::IUserProfile * *)

- ea: `0x180093560`
- end: `0x18009385c`
- name: `?GetUserByName@UserManagerStatics@Internal@System@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIUserProfile@234@@Z`
- size: `764`
- prototype: `int(Windows::System::Internal::UserManagerStatics *__hidden this, HSTRING, struct Windows::System::Internal::IUserProfile **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180011880`
- `0x180012890`
- `0x180016c50`
- `0x180024828`
- `0x180093560`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180093704`
- `msvcrt!_wcsicmp` at `0x180093704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093597`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800936e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800936f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009375e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093597`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800936e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800936f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009375e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800936b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800937ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800936b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093729`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800937ba`

## string_xrefs

- `0x1800937e0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800937f7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009380c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093820`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093835`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093849`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::System::Internal::UserManagerStatics::GetUserByName(
        Windows::System::Internal::UserManagerStatics *this,
        HSTRING a2,
        struct Windows::System::Internal::IUserProfile **a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  int v8; // r9d
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD *); // rbx
  int v11; // eax
  int v12; // eax
  unsigned int i; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, int *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  const wchar_t *StringRawBuffer; // rbx
  const wchar_t *v21; // rax
  const struct _tlgProvider_t *v22; // rbx
  int v23; // r8d
  int v24; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v26; // rax
  int v27; // ebx
  wil *v28; // rcx
  int v29; // r8d
  int v30; // r9d
  int v31; // [rsp+20h] [rbp-48h]
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  int v33[2]; // [rsp+38h] [rbp-30h] BYREF
  _QWORD v34[2]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HSTRING v36; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v37; // [rsp+88h] [rbp+20h] BYREF

  v36 = a2;
  v6 = UserMgrUserModelTelemetry::Provider();
  v7 = (int)v6;
  if ( *(_DWORD *)v6 > 4u )
  {
    *(_QWORD *)v33 = WindowsGetStringRawBuffer(a2, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v7,
      (unsigned int)byte_180126ADB,
      0,
      v8,
      (__int64)v33);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x550,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80070057LL,
        v31);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x551,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80070057LL,
        v31);
    v34[0] = 0;
    v37 = 0;
    *a3 = 0;
    v9 = *((_QWORD *)this + 62);
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v9 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
    v11 = v10(v9, v34);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x558,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v11,
        v31);
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v34[0] + 56LL))(v34[0], &v37);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x559,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v12,
        v31);
    for ( i = 0; i < v37; ++i )
    {
      *(_QWORD *)v33 = 0;
      string = 0;
      v14 = v34[0];
      v15 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v34[0] + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v33);
      v16 = v15(v14, i, v33);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x55F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v16,
          v31);
      v17 = *(_QWORD *)v33;
      v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v33 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      v19 = v18(v17, &string);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x561,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v19,
          v31);
      StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
      v21 = WindowsGetStringRawBuffer(string, 0);
      if ( !_wcsicmp(v21, StringRawBuffer) )
      {
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v33);
        *a3 = *(struct Windows::System::Internal::IUserProfile **)v33;
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v33);
        break;
      }
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v33);
    }
    v22 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v22 > 4u )
    {
      LODWORD(string) = 0;
      *(_QWORD *)v33 = WindowsGetStringRawBuffer(a2, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v22,
        (unsigned int)&dword_180126A9C,
        v23,
        v24,
        (__int64)v33,
        (__int64)&string);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
    result = 0;
  }
  catch ( ... )
  {
    v26 = UserMgrUserModelTelemetry::Provider();
    v27 = (int)v26;
    v28 = (wil *)*(unsigned int *)v26;
    if ( (unsigned int)v28 > 4 )
    {
      v37 = wil::ResultFromCaughtException(v28);
      WindowsGetStringRawBuffer(v36, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v27,
        (unsigned int)word_180126A4A,
        v29,
        v30,
        (__int64)&v36,
        (__int64)&v37);
    }
    return (unsigned int)wil::ResultFromCaughtException(v28);
  }
  return result;
}

```

## disassembly

```asm
0x180093560  mov     [rsp+arg_0], rbx
0x180093565  mov     [rsp+arg_10], rsi
0x18009356a  mov     [rsp+arg_8], rdx
0x18009356f  push    rdi
0x180093570  push    r14
0x180093572  push    r15
0x180093574  sub     rsp, 50h
0x180093578  mov     r15, r8
0x18009357b  mov     r14, rdx
0x18009357e  mov     rdi, rcx
0x180093581  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180093586  mov     rbx, rax
0x180093589  mov     r9d, [rax]
0x18009358c  cmp     r9d, 4
0x180093590  jbe     short loc_1800935BE
0x180093592  xor     edx, edx; length
0x180093594  mov     rcx, r14; string
0x180093597  call    cs:__imp_WindowsGetStringRawBuffer
0x18009359d  mov     qword ptr [rsp+68h+var_30], rax
0x1800935a2  lea     rax, [rsp+68h+var_30]
0x1800935a7  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800935ac  xor     r8d, r8d
0x1800935af  lea     rdx, byte_180126ADB
0x1800935b6  mov     rcx, rbx
0x1800935b9  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800935be  mov     rcx, [rsp+68h]; this
0x1800935c3  test    r14, r14
0x1800935c6  jz      loc_1800937DA
0x1800935cc  mov     rcx, [rsp+68h]; this
0x1800935d1  test    r15, r15
0x1800935d4  jz      loc_1800937F1
0x1800935da  mov     [rsp+68h+var_28], 0
0x1800935e3  mov     [rsp+68h+arg_18], 0
0x1800935ee  mov     qword ptr [r15], 0
0x1800935f5  mov     rdi, [rdi+1F0h]
0x1800935fc  mov     rax, [rdi]
0x1800935ff  mov     rbx, [rax+68h]
0x180093603  lea     rcx, [rsp+68h+var_28]
0x180093608  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009360d  lea     rdx, [rsp+68h+var_28]
0x180093612  mov     rcx, rdi
0x180093615  mov     rax, rbx
0x180093618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009361d  mov     rcx, [rsp+68h]; this
0x180093622  test    eax, eax
0x180093624  js      loc_180093809
0x18009362a  mov     rcx, [rsp+68h+var_28]
0x18009362f  mov     rax, [rcx]
0x180093632  lea     rdx, [rsp+68h+arg_18]
0x18009363a  mov     rax, [rax+38h]
0x18009363e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093643  mov     rcx, [rsp+68h]; this
0x180093648  test    eax, eax
0x18009364a  js      loc_18009381D
0x180093650  xor     esi, esi
0x180093652  cmp     esi, [rsp+68h+arg_18]
0x180093659  jnb     loc_180093742
0x18009365f  mov     qword ptr [rsp+68h+var_30], 0
0x180093668  mov     [rsp+68h+string], 0
0x180093671  mov     rdi, [rsp+68h+var_28]
0x180093676  mov     rax, [rdi]
0x180093679  mov     rbx, [rax+30h]
0x18009367d  lea     rcx, [rsp+68h+var_30]
0x180093682  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093687  lea     r8, [rsp+68h+var_30]
0x18009368c  mov     edx, esi
0x18009368e  mov     rcx, rdi
0x180093691  mov     rax, rbx
0x180093694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093699  mov     rcx, [rsp+68h]; this
0x18009369e  test    eax, eax
0x1800936a0  js      loc_180093832
0x1800936a6  mov     rdi, qword ptr [rsp+68h+var_30]
0x1800936ab  mov     rax, [rdi]
0x1800936ae  mov     rbx, [rax+38h]
0x1800936b2  mov     rcx, [rsp+68h+string]; string
0x1800936b7  call    cs:__imp_WindowsDeleteString
0x1800936bd  mov     [rsp+68h+string], 0
0x1800936c6  lea     rdx, [rsp+68h+string]
0x1800936cb  mov     rcx, rdi
0x1800936ce  mov     rax, rbx
0x1800936d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800936d6  mov     rcx, [rsp+68h]; this
0x1800936db  test    eax, eax
0x1800936dd  js      loc_180093846
0x1800936e3  xor     edx, edx; length
0x1800936e5  mov     rcx, r14; string
0x1800936e8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800936ee  mov     rbx, rax
0x1800936f1  xor     edx, edx; length
0x1800936f3  mov     rcx, [rsp+68h+string]; string
0x1800936f8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800936fe  mov     rdx, rbx; String2
0x180093701  mov     rcx, rax; String1
0x180093704  call    cs:__imp__wcsicmp
0x18009370a  test    eax, eax
0x18009370c  jnz     loc_1800937B5
0x180093712  lea     rcx, [rsp+68h+var_30]
0x180093717  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18009371c  mov     rax, qword ptr [rsp+68h+var_30]
0x180093721  mov     [r15], rax
0x180093724  mov     rcx, [rsp+68h+string]; string
0x180093729  call    cs:__imp_WindowsDeleteString
0x18009372f  mov     [rsp+68h+string], 0
0x180093738  lea     rcx, [rsp+68h+var_30]
0x18009373d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093742  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180093747  mov     rbx, rax
0x18009374a  mov     ecx, [rax]
0x18009374c  cmp     ecx, 4
0x18009374f  jbe     short loc_18009378D
0x180093751  mov     dword ptr [rsp+68h+string], 0
0x180093759  xor     edx, edx; length
0x18009375b  mov     rcx, r14; string
0x18009375e  call    cs:__imp_WindowsGetStringRawBuffer
0x180093764  mov     qword ptr [rsp+68h+var_30], rax
0x180093769  lea     rax, [rsp+68h+string]
0x18009376e  mov     [rsp+68h+var_40], rax
0x180093773  lea     rax, [rsp+68h+var_30]
0x180093778  mov     qword ptr [rsp+68h+var_48], rax
0x18009377d  lea     rdx, dword_180126A9C
0x180093784  mov     rcx, rbx
0x180093787  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18009378c  nop
0x18009378d  lea     rcx, [rsp+68h+var_28]
0x180093792  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093797  xor     eax, eax
0x180093799  jmp     short loc_18009379F
0x18009379b  mov     eax, dword ptr [rsp+68h+arg_8]
0x18009379f  lea     r11, [rsp+68h+var_18]
0x1800937a4  mov     rbx, [r11+20h]
0x1800937a8  mov     rsi, [r11+30h]
0x1800937ac  mov     rsp, r11
0x1800937af  pop     r15
0x1800937b1  pop     r14
0x1800937b3  pop     rdi
0x1800937b4  retn
0x1800937b5  mov     rcx, [rsp+68h+string]; string
0x1800937ba  call    cs:__imp_WindowsDeleteString
0x1800937c0  mov     [rsp+68h+string], 0
0x1800937c9  lea     rcx, [rsp+68h+var_30]
0x1800937ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800937d3  inc     esi
0x1800937d5  jmp     loc_180093652
0x1800937da  mov     r9d, 80070057h; char *
0x1800937e0  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800937e7  mov     edx, 550h; void *
0x1800937ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800937f1  mov     r9d, 80070057h; char *
0x1800937f7  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800937fe  mov     edx, 551h; void *
0x180093803  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093809  mov     r9d, eax; char *
0x18009380c  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093813  mov     edx, 558h; void *
0x180093818  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009381d  mov     r9d, eax; char *
0x180093820  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093827  mov     edx, 559h; void *
0x18009382c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093832  mov     r9d, eax; char *
0x180093835  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18009383c  mov     edx, 55Fh; void *
0x180093841  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093846  mov     r9d, eax; char *
0x180093849  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093850  mov     edx, 561h; void *
0x180093855  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
