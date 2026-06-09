# Windows::System::Internal::UserManagerStatics::GetUserBySid(HSTRING__ *,Windows::System::Internal::IUserProfile * *)

- ea: `0x180093864`
- end: `0x180093baf`
- name: `?GetUserBySid@UserManagerStatics@Internal@System@Windows@@AEAAJPEAUHSTRING__@@PEAPEAUIUserProfile@234@@Z`
- size: `843`
- prototype: `int(Windows::System::Internal::UserManagerStatics *__hidden this, HSTRING, struct Windows::System::Internal::IUserProfile **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a0128`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x180011880`
- `0x180012890`
- `0x180016c50`
- `0x180024828`
- `0x1800346b8`
- `0x180093864`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180093a2d`
- `msvcrt!_wcsicmp` at `0x180093a2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009389b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093a11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093a21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009389b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093a11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093a21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800939e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093a52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093aee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800939e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093a52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093aee`

## string_xrefs

- `0x180093b1f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093b36`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093b4b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093b5f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093b74`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093b88`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093b9c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::System::Internal::UserManagerStatics::GetUserBySid(
        Windows::System::Internal::UserManagerStatics *this,
        HSTRING a2,
        struct Windows::System::Internal::IUserProfile **a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  int v8; // r9d
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  int v12; // eax
  unsigned int i; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, struct Windows::System::Internal::IUserProfile **); // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  const wchar_t *StringRawBuffer; // rbx
  const wchar_t *v22; // rax
  const struct _tlgProvider_t *v23; // rbx
  int v24; // r8d
  int v25; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v27; // rax
  int v28; // ebx
  wil *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  int v32; // [rsp+20h] [rbp-48h]
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  struct Windows::System::Internal::IUserProfile *v34; // [rsp+38h] [rbp-30h] BYREF
  __int64 v35; // [rsp+40h] [rbp-28h] BYREF
  int v36[2]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HSTRING v38; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v39; // [rsp+88h] [rbp+20h] BYREF

  v38 = a2;
  v6 = UserMgrUserModelTelemetry::Provider();
  v7 = (int)v6;
  if ( *(_DWORD *)v6 > 4u )
  {
    *(_QWORD *)v36 = WindowsGetStringRawBuffer(a2, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v7,
      (unsigned int)byte_180126A23,
      0,
      v8,
      (__int64)v36);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80070057LL,
        v32);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80004003LL,
        v32);
    v35 = 0;
    v39 = 0;
    *a3 = 0;
    v9 = *((_QWORD *)this + 67);
    v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v11 = v10(v9, &v35);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x592,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v11,
        v32);
    v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 56LL))(v35, &v39);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x593,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v12,
        v32);
    for ( i = 0; i < v39; ++i )
    {
      v34 = 0;
      *(_QWORD *)v36 = 0;
      string = 0;
      v14 = v35;
      v15 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::System::Internal::IUserProfile **))(*(_QWORD *)v35 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      v16 = v15(v14, i, &v34);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x59A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v16,
          v32);
      v17 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::IUserProfile2>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v34,
              (__int64)v36);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x59B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v17,
          v32);
      v18 = *(_QWORD *)v36;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v36 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      v20 = v19(v18, &string);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x59E,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v20,
          v32);
      StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
      v22 = WindowsGetStringRawBuffer(string, 0);
      if ( !_wcsicmp(v22, StringRawBuffer) )
      {
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v34);
        *a3 = v34;
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        break;
      }
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v36);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    }
    v23 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v23 > 4u )
    {
      LODWORD(string) = 0;
      *(_QWORD *)v36 = WindowsGetStringRawBuffer(a2, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v23,
        (unsigned int)byte_1801269ED,
        v24,
        v25,
        (__int64)v36,
        (__int64)&string);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    result = 0;
  }
  catch ( ... )
  {
    v27 = UserMgrUserModelTelemetry::Provider();
    v28 = (int)v27;
    v29 = (wil *)*(unsigned int *)v27;
    if ( (unsigned int)v29 > 4 )
    {
      v39 = wil::ResultFromCaughtException(v29);
      WindowsGetStringRawBuffer(v38, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v28,
        (unsigned int)&dword_1801269A4,
        v30,
        v31,
        (__int64)&v38,
        (__int64)&v39);
    }
    return (unsigned int)wil::ResultFromCaughtException(v29);
  }
  return result;
}

```

## disassembly

```asm
0x180093864  mov     [rsp+arg_0], rbx
0x180093869  mov     [rsp+arg_10], rsi
0x18009386e  mov     [rsp+arg_8], rdx
0x180093873  push    rdi
0x180093874  push    r14
0x180093876  push    r15
0x180093878  sub     rsp, 50h
0x18009387c  mov     r15, r8
0x18009387f  mov     r14, rdx
0x180093882  mov     rdi, rcx
0x180093885  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18009388a  mov     rbx, rax
0x18009388d  mov     r9d, [rax]
0x180093890  cmp     r9d, 4
0x180093894  jbe     short loc_1800938C2
0x180093896  xor     edx, edx; length
0x180093898  mov     rcx, r14; string
0x18009389b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800938a1  mov     qword ptr [rsp+68h+var_20], rax
0x1800938a6  lea     rax, [rsp+68h+var_20]
0x1800938ab  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800938b0  xor     r8d, r8d
0x1800938b3  lea     rdx, byte_180126A23
0x1800938ba  mov     rcx, rbx
0x1800938bd  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800938c2  mov     rcx, [rsp+68h]; this
0x1800938c7  test    r14, r14
0x1800938ca  jz      loc_180093B19
0x1800938d0  mov     rcx, [rsp+68h]; this
0x1800938d5  test    r15, r15
0x1800938d8  jz      loc_180093B30
0x1800938de  mov     [rsp+68h+var_28], 0
0x1800938e7  mov     [rsp+68h+arg_18], 0
0x1800938f2  mov     qword ptr [r15], 0
0x1800938f9  mov     rdi, [rdi+218h]
0x180093900  mov     rax, [rdi]
0x180093903  mov     rbx, [rax+68h]
0x180093907  lea     rcx, [rsp+68h+var_28]
0x18009390c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093911  lea     rdx, [rsp+68h+var_28]
0x180093916  mov     rcx, rdi
0x180093919  mov     rax, rbx
0x18009391c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093921  mov     rcx, [rsp+68h]; this
0x180093926  test    eax, eax
0x180093928  js      loc_180093B48
0x18009392e  mov     rcx, [rsp+68h+var_28]
0x180093933  mov     rax, [rcx]
0x180093936  lea     rdx, [rsp+68h+arg_18]
0x18009393e  mov     rax, [rax+38h]
0x180093942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093947  mov     rcx, [rsp+68h]; this
0x18009394c  test    eax, eax
0x18009394e  js      loc_180093B5C
0x180093954  xor     esi, esi
0x180093956  cmp     esi, [rsp+68h+arg_18]
0x18009395d  jnb     loc_180093A76
0x180093963  mov     [rsp+68h+var_30], 0
0x18009396c  mov     qword ptr [rsp+68h+var_20], 0
0x180093975  mov     [rsp+68h+string], 0
0x18009397e  mov     rdi, [rsp+68h+var_28]
0x180093983  mov     rax, [rdi]
0x180093986  mov     rbx, [rax+30h]
0x18009398a  lea     rcx, [rsp+68h+var_30]
0x18009398f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093994  lea     r8, [rsp+68h+var_30]
0x180093999  mov     edx, esi
0x18009399b  mov     rcx, rdi
0x18009399e  mov     rax, rbx
0x1800939a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800939a6  mov     rcx, [rsp+68h]; this
0x1800939ab  test    eax, eax
0x1800939ad  js      loc_180093B71
0x1800939b3  lea     rdx, [rsp+68h+var_20]
0x1800939b8  lea     rcx, [rsp+68h+var_30]
0x1800939bd  call    ??$As@UIUserProfile2@Internal@System@Windows@@@?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserProfile2@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::IUserProfile2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile2>>)
0x1800939c2  mov     rcx, [rsp+68h]; this
0x1800939c7  test    eax, eax
0x1800939c9  js      loc_180093B85
0x1800939cf  mov     rdi, qword ptr [rsp+68h+var_20]
0x1800939d4  mov     rax, [rdi]
0x1800939d7  mov     rbx, [rax+38h]
0x1800939db  mov     rcx, [rsp+68h+string]; string
0x1800939e0  call    cs:__imp_WindowsDeleteString
0x1800939e6  mov     [rsp+68h+string], 0
0x1800939ef  lea     rdx, [rsp+68h+string]
0x1800939f4  mov     rcx, rdi
0x1800939f7  mov     rax, rbx
0x1800939fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800939ff  mov     rcx, [rsp+68h]; this
0x180093a04  test    eax, eax
0x180093a06  js      loc_180093B99
0x180093a0c  xor     edx, edx; length
0x180093a0e  mov     rcx, r14; string
0x180093a11  call    cs:__imp_WindowsGetStringRawBuffer
0x180093a17  mov     rbx, rax
0x180093a1a  xor     edx, edx; length
0x180093a1c  mov     rcx, [rsp+68h+string]; string
0x180093a21  call    cs:__imp_WindowsGetStringRawBuffer
0x180093a27  mov     rdx, rbx; String2
0x180093a2a  mov     rcx, rax; String1
0x180093a2d  call    cs:__imp__wcsicmp
0x180093a33  test    eax, eax
0x180093a35  jnz     loc_180093AE9
0x180093a3b  lea     rcx, [rsp+68h+var_30]
0x180093a40  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180093a45  mov     rax, [rsp+68h+var_30]
0x180093a4a  mov     [r15], rax
0x180093a4d  mov     rcx, [rsp+68h+string]; string
0x180093a52  call    cs:__imp_WindowsDeleteString
0x180093a58  mov     [rsp+68h+string], 0
0x180093a61  lea     rcx, [rsp+68h+var_20]
0x180093a66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093a6b  nop
0x180093a6c  lea     rcx, [rsp+68h+var_30]
0x180093a71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093a76  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180093a7b  mov     rbx, rax
0x180093a7e  mov     ecx, [rax]
0x180093a80  cmp     ecx, 4
0x180093a83  jbe     short loc_180093AC1
0x180093a85  mov     dword ptr [rsp+68h+string], 0
0x180093a8d  xor     edx, edx; length
0x180093a8f  mov     rcx, r14; string
0x180093a92  call    cs:__imp_WindowsGetStringRawBuffer
0x180093a98  mov     qword ptr [rsp+68h+var_20], rax
0x180093a9d  lea     rax, [rsp+68h+string]
0x180093aa2  mov     [rsp+68h+var_40], rax
0x180093aa7  lea     rax, [rsp+68h+var_20]
0x180093aac  mov     qword ptr [rsp+68h+var_48], rax
0x180093ab1  lea     rdx, byte_1801269ED
0x180093ab8  mov     rcx, rbx
0x180093abb  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180093ac0  nop
0x180093ac1  lea     rcx, [rsp+68h+var_28]
0x180093ac6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093acb  xor     eax, eax
0x180093acd  jmp     short loc_180093AD3
0x180093acf  mov     eax, dword ptr [rsp+68h+arg_8]
0x180093ad3  lea     r11, [rsp+68h+var_18]
0x180093ad8  mov     rbx, [r11+20h]
0x180093adc  mov     rsi, [r11+30h]
0x180093ae0  mov     rsp, r11
0x180093ae3  pop     r15
0x180093ae5  pop     r14
0x180093ae7  pop     rdi
0x180093ae8  retn
0x180093ae9  mov     rcx, [rsp+68h+string]; string
0x180093aee  call    cs:__imp_WindowsDeleteString
0x180093af4  mov     [rsp+68h+string], 0
0x180093afd  lea     rcx, [rsp+68h+var_20]
0x180093b02  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093b07  nop
0x180093b08  lea     rcx, [rsp+68h+var_30]
0x180093b0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180093b12  inc     esi
0x180093b14  jmp     loc_180093956
0x180093b19  mov     r9d, 80070057h; char *
0x180093b1f  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093b26  mov     edx, 58Ah; void *
0x180093b2b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093b30  mov     r9d, 80004003h; char *
0x180093b36  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093b3d  mov     edx, 58Bh; void *
0x180093b42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093b48  mov     r9d, eax; char *
0x180093b4b  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093b52  mov     edx, 592h; void *
0x180093b57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093b5c  mov     r9d, eax; char *
0x180093b5f  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093b66  mov     edx, 593h; void *
0x180093b6b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093b71  mov     r9d, eax; char *
0x180093b74  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093b7b  mov     edx, 59Ah; void *
0x180093b80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093b85  mov     r9d, eax; char *
0x180093b88  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093b8f  mov     edx, 59Bh; void *
0x180093b94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093b99  mov     r9d, eax; char *
0x180093b9c  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093ba3  mov     edx, 59Eh; void *
0x180093ba8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
