# Windows::System::UserStatics::AddPartialUserAndFireUserAdded(uint,HSTRING__ *,unsigned __int64,uint,unsigned __int64 * const,unsigned __int64,HSTRING__ *,Windows::System::IUser *,uint,Windows::System::UserAuthenticationStatus,Windows::Foundation::Collections::IPropertySet *,Windows::System::IUser * *)

- ea: `0x180077b70`
- end: `0x18007808d`
- name: `?AddPartialUserAndFireUserAdded@UserStatics@System@Windows@@UEAAJIPEAUHSTRING__@@_KIQEA_K10PEAUIUser@23@IW4UserAuthenticationStatus@23@PEAUIPropertySet@Collections@Foundation@3@PEAPEAU523@@Z`
- size: `1309`
- prototype: `int __high(unsigned int, HSTRING, unsigned __int64, unsigned int, unsigned __int64 *const, unsigned __int64, HSTRING, struct Windows::System::IUser *, unsigned int, enum Windows::System::UserAuthenticationStatus, struct Windows::Foundation::Collections::IPropertySet *, struct Windows::System::IUser **)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1800019a0`
- `0x180001aa4`
- `0x180006130`
- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x18000eec0`
- `0x180012890`
- `0x1800179c0`
- `0x180024828`
- `0x18003991c`
- `0x18003a270`
- `0x180053018`
- `0x180053304`
- `0x180077b70`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077c71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180077c71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077bc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077bdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077f4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077bc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077bdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077f4c`

## string_xrefs

- `0x180077fe9`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078001`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078015`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078029`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007803d`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078051`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180078065`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x18007807a`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 Windows::System::UserStatics::AddPartialUserAndFireUserAdded(__int64 a1, unsigned int a2, ...)
{
  __int64 v2; // r15
  HSTRING v3; // r13
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  unsigned int v8; // r14d
  int v9; // r8d
  int v10; // r9d
  _QWORD *v11; // r12
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  _DWORD *v18; // rax
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // r8
  __int64 v20; // rax
  int v21; // eax
  const struct _tlgProvider_t *v22; // rbx
  int v23; // r8d
  int v24; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v26; // rax
  int v27; // ebx
  wil *v28; // rcx
  int v29; // r8d
  int v30; // r9d
  int v31; // [rsp+20h] [rbp-C8h]
  int v32; // [rsp+20h] [rbp-C8h]
  unsigned int v33; // [rsp+50h] [rbp-98h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-90h] BYREF
  __int64 v35; // [rsp+60h] [rbp-88h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-80h] BYREF
  __int64 v37; // [rsp+70h] [rbp-78h] BYREF
  _QWORD v38[4]; // [rsp+78h] [rbp-70h] BYREF
  PCWSTR StringRawBuffer; // [rsp+98h] [rbp-50h] BYREF
  _BYTE v40[72]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  unsigned int v42; // [rsp+F8h] [rbp+10h] BYREF
  HSTRING v43; // [rsp+100h] [rbp+18h] BYREF
  va_list va; // [rsp+100h] [rbp+18h]
  __int64 v45; // [rsp+108h] [rbp+20h]
  __int64 v46; // [rsp+110h] [rbp+28h] BYREF
  va_list va1; // [rsp+110h] [rbp+28h]
  __int64 v48; // [rsp+118h] [rbp+30h] BYREF
  va_list va2; // [rsp+118h] [rbp+30h]
  _QWORD *v50; // [rsp+120h] [rbp+38h]
  HSTRING string; // [rsp+128h] [rbp+40h] BYREF
  va_list stringa; // [rsp+128h] [rbp+40h]
  __int64 v53; // [rsp+130h] [rbp+48h] BYREF
  va_list va4; // [rsp+130h] [rbp+48h]
  __int64 v55; // [rsp+138h] [rbp+50h] BYREF
  va_list va5; // [rsp+138h] [rbp+50h]
  __int64 v57; // [rsp+140h] [rbp+58h]
  __int64 v58; // [rsp+148h] [rbp+60h]
  _QWORD *v59; // [rsp+150h] [rbp+68h] BYREF
  va_list va6; // [rsp+150h] [rbp+68h]
  va_list va7; // [rsp+158h] [rbp+70h] BYREF

  va_start(va7, a2);
  va_start(va6, a2);
  va_start(va5, a2);
  va_start(va4, a2);
  va_start(stringa, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v43 = va_arg(va1, HSTRING);
  v45 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v46 = va_arg(va2, _QWORD);
  va_copy(stringa, va2);
  v48 = va_arg(stringa, _QWORD);
  v50 = va_arg(stringa, _QWORD *);
  va_copy(va4, stringa);
  string = va_arg(va4, HSTRING);
  va_copy(va5, va4);
  v53 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v55 = va_arg(va6, _QWORD);
  v57 = va_arg(va6, _QWORD);
  v58 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v59 = va_arg(va7, _QWORD *);
  v42 = a2;
  v2 = v45;
  v3 = v43;
  v6 = UserMgrUserModelTelemetry::Provider();
  v7 = (int)v6;
  v8 = v55;
  if ( *(_DWORD *)v6 > 4u )
  {
    v33 = v55;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v35 = v2;
    v38[0] = WindowsGetStringRawBuffer(v3, 0);
    LODWORD(v34) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)byte_1801226D5,
      v9,
      v10,
      (__int64)&v34,
      (__int64)v38,
      (__int64)&v35,
      (__int64)&StringRawBuffer,
      (__int64)&v33);
  }
  try
  {
    v11 = v59;
    if ( !v59 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)0x80004003LL,
        v31);
    *v59 = 0;
    v36 = 0;
    v37 = 0;
    v34 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
    v35 = a1 + 72;
    v59 = (_QWORD *)__PAIR64__(v8, a2);
    std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(
      a1 + 112,
      v38,
      (_QWORD **)va6);
    if ( v38[0] != *(_QWORD *)(a1 + 112)
      || *(_QWORD *)std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(
                      a1 + 128,
                      v38,
                      (_QWORD **)va6) != *(_QWORD *)(a1 + 128) )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8F3,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)0x80A20303LL,
        v31);
    }
    v59 = v50;
    v38[0] = v2;
    v13 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::User,Windows::System::User,unsigned int &,HSTRING__ * &,void *,unsigned int &,unsigned __int64 * &,void *,HSTRING__ * &,Windows::System::IUser * &,unsigned int &>(
            (unsigned int)&v34,
            (unsigned int)&v42,
            (unsigned int)va,
            (unsigned int)v38,
            (__int64)va1,
            (__int64)va2,
            (__int64)va6,
            (__int64)stringa,
            (__int64)va4,
            (__int64)va5);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8FE,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v13,
        v32);
    v14 = Microsoft::WRL::ComPtr<Windows::System::User>::As<Windows::System::IUser>(&v34, (__int64)&v36);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8FF,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v14,
        v32);
    v15 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            &v36,
            &v37);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x900,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v15,
        v32);
    if ( (_DWORD)v57 )
    {
      v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 56LL))(v37);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x903,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v16,
          v32);
    }
    if ( v58 )
    {
      LOBYTE(v59) = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v37 + 112LL))(v37, v58, (_QWORD **)va6);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x908,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
          (const char *)(unsigned int)v17,
          v32);
    }
    v38[0] = v36;
    v59 = (_QWORD *)__PAIR64__(v8, a2);
    v18 = std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>(
            &StringRawBuffer,
            (_QWORD **)va6,
            v38);
    std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::insert(
      a1 + 128,
      v38,
      v18);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v40);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 352);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v35);
    if ( v34 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v34)[2])(v34);
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v36);
    v19 = v36;
    *v11 = v36;
    v20 = *(_QWORD *)(a1 - 56);
    v59 = v38;
    v38[0] = off_1800EFFE0;
    v38[3] = v38;
    v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD *))(v20 + 64))(
            a1 - 56,
            a1 + 384,
            v19,
            v38);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v21,
        v32);
    v22 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v22 > 4u )
    {
      LODWORD(v59) = 0;
      LODWORD(v34) = v8;
      v38[0] = WindowsGetStringRawBuffer(string, 0);
      v35 = v2;
      StringRawBuffer = WindowsGetStringRawBuffer(v3, 0);
      v33 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v22,
        (unsigned int)&dword_18012265C,
        v23,
        v24,
        (__int64)&v33,
        (__int64)&StringRawBuffer,
        (__int64)&v35,
        (__int64)v38,
        (__int64)&v34,
        (__int64)va6);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
    result = 0;
  }
  catch ( ... )
  {
    v26 = UserMgrUserModelTelemetry::Provider();
    v27 = (int)v26;
    v28 = (wil *)*(unsigned int *)v26;
    if ( (unsigned int)v28 > 4 )
    {
      LODWORD(v59) = wil::ResultFromCaughtException(v28);
      LODWORD(v34) = v55;
      v38[0] = WindowsGetStringRawBuffer(string, 0);
      v35 = v45;
      StringRawBuffer = WindowsGetStringRawBuffer(v43, 0);
      v33 = v42;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v27,
        (unsigned int)&unk_1801225D0,
        v29,
        v30,
        (__int64)&v33,
        (__int64)&StringRawBuffer,
        (__int64)&v35,
        (__int64)v38,
        (__int64)&v34,
        (__int64)va6);
    }
    LODWORD(v59) = wil::ResultFromCaughtException(v28);
    return (unsigned int)v59;
  }
  return result;
}

```

## disassembly

```asm
0x180077b70  mov     [rsp+arg_18], r9
0x180077b75  mov     [rsp+arg_10], r8
0x180077b7a  mov     [rsp+arg_8], edx
0x180077b7e  push    rbx
0x180077b7f  push    rsi
0x180077b80  push    rdi
0x180077b81  push    r12
0x180077b83  push    r13
0x180077b85  push    r14
0x180077b87  push    r15
0x180077b89  sub     rsp, 0B0h
0x180077b90  mov     r15, r9
0x180077b93  mov     r13, r8
0x180077b96  mov     esi, edx
0x180077b98  mov     rdi, rcx
0x180077b9b  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180077ba0  mov     rbx, rax
0x180077ba3  mov     r10d, [rax]
0x180077ba6  cmp     r10d, 4
0x180077baa  jbe     loc_180077C34
0x180077bb0  mov     r14d, dword ptr [rsp+0E8h+arg_48]
0x180077bb8  mov     [rsp+0E8h+var_98], r14d
0x180077bbd  xor     edx, edx; length
0x180077bbf  mov     rcx, [rsp+0E8h+string]; string
0x180077bc7  call    cs:__imp_WindowsGetStringRawBuffer
0x180077bcd  mov     [rsp+0E8h+var_50], rax
0x180077bd5  mov     [rsp+0E8h+var_88], r15
0x180077bda  xor     edx, edx; length
0x180077bdc  mov     rcx, r13; string
0x180077bdf  call    cs:__imp_WindowsGetStringRawBuffer
0x180077be5  mov     [rsp+0E8h+var_70], rax
0x180077bea  mov     dword ptr [rsp+0E8h+var_90], esi
0x180077bee  lea     rax, [rsp+0E8h+var_98]
0x180077bf3  mov     [rsp+0E8h+var_A8], rax
0x180077bf8  lea     rax, [rsp+0E8h+var_50]
0x180077c00  mov     [rsp+0E8h+var_B0], rax
0x180077c05  lea     rax, [rsp+0E8h+var_88]
0x180077c0a  mov     [rsp+0E8h+var_B8], rax
0x180077c0f  lea     rax, [rsp+0E8h+var_70]
0x180077c14  mov     [rsp+0E8h+var_C0], rax
0x180077c19  lea     rax, [rsp+0E8h+var_90]
0x180077c1e  mov     qword ptr [rsp+0E8h+var_C8], rax
0x180077c23  lea     rdx, byte_1801226D5
0x180077c2a  mov     rcx, rbx
0x180077c2d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180077c32  jmp     short loc_180077C3C
0x180077c34  mov     r14d, dword ptr [rsp+0E8h+arg_48]
0x180077c3c  mov     rcx, [rsp+0E8h]; this
0x180077c44  mov     r12, [rsp+0E8h+arg_60]
0x180077c4c  xor     eax, eax
0x180077c4e  test    r12, r12
0x180077c51  jz      loc_180077FE3
0x180077c57  mov     [r12], rax
0x180077c5b  mov     [rsp+0E8h+var_80], rax
0x180077c60  mov     [rsp+0E8h+var_78], rax
0x180077c65  mov     [rsp+0E8h+var_90], rax
0x180077c6a  lea     rbx, [rdi+48h]
0x180077c6e  mov     rcx, rbx; lpCriticalSection
0x180077c71  call    cs:__imp_EnterCriticalSection
0x180077c77  mov     [rsp+0E8h+var_88], rbx
0x180077c7c  mov     dword ptr [rsp+0E8h+arg_60], esi
0x180077c83  mov     dword ptr [rsp+0E8h+arg_60+4], r14d
0x180077c8b  lea     r8, [rsp+0E8h+arg_60]
0x180077c93  lea     rdx, [rsp+0E8h+var_70]
0x180077c98  lea     rcx, [rdi+70h]
0x180077c9c  call    ?find@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBU?$pair@IK@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(std::pair<uint,ulong> const &)
0x180077ca1  mov     rdx, [rdi+70h]
0x180077ca5  cmp     [rsp+0E8h+var_70], rdx
0x180077caa  jnz     short loc_180077CD4
0x180077cac  lea     rbx, [rdi+80h]
0x180077cb3  lea     r8, [rsp+0E8h+arg_60]
0x180077cbb  lea     rdx, [rsp+0E8h+var_70]
0x180077cc0  mov     rcx, rbx
0x180077cc3  call    ?find@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBU?$pair@IK@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::find(std::pair<uint,ulong> const &)
0x180077cc8  mov     rcx, [rbx]
0x180077ccb  cmp     [rax], rcx
0x180077cce  jnz     short loc_180077CD4
0x180077cd0  xor     al, al
0x180077cd2  jmp     short loc_180077CD6
0x180077cd4  mov     al, 1
0x180077cd6  mov     rcx, [rsp+0E8h]; this
0x180077cde  test    al, al
0x180077ce0  jnz     loc_180077FFB
0x180077ce6  mov     rax, [rsp+0E8h+arg_30]
0x180077cee  mov     [rsp+0E8h+arg_60], rax
0x180077cf6  mov     [rsp+0E8h+var_70], r15
0x180077cfb  lea     rax, [rsp+0E8h+arg_48]
0x180077d03  mov     [rsp+0E8h+var_A0], rax
0x180077d08  lea     rax, [rsp+0E8h+arg_40]
0x180077d10  mov     [rsp+0E8h+var_A8], rax
0x180077d15  lea     rax, [rsp+0E8h+string]
0x180077d1d  mov     [rsp+0E8h+var_B0], rax
0x180077d22  lea     rax, [rsp+0E8h+arg_60]
0x180077d2a  mov     [rsp+0E8h+var_B8], rax
0x180077d2f  lea     rax, [rsp+0E8h+arg_28]
0x180077d37  mov     [rsp+0E8h+var_C0], rax
0x180077d3c  lea     rax, [rsp+0E8h+arg_20]
0x180077d44  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x180077d49  lea     r9, [rsp+0E8h+var_70]
0x180077d4e  lea     r8, [rsp+0E8h+arg_10]
0x180077d56  lea     rdx, [rsp+0E8h+arg_8]
0x180077d5e  lea     rcx, [rsp+0E8h+var_90]
0x180077d63  call    ??$MakeAndInitialize@VUser@System@Windows@@V123@AEAIAEAPEAUHSTRING__@@PEAXAEAIAEAQEA_KPEAXAEAPEAU4@AEAPEAUIUser@23@AEAI@Details@WRL@Microsoft@@YAJPEAPEAVUser@System@Windows@@AEAIAEAPEAUHSTRING__@@$$QEAPEAX1AEAQEA_K32AEAPEAUIUser@45@1@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::User,Windows::System::User,uint &,HSTRING__ * &,void *,uint &,unsigned __int64 * &,void *,HSTRING__ * &,Windows::System::IUser * &,uint &>(Windows::System::User * *,uint &,HSTRING__ * &,void * &&,uint &,unsigned __int64 * &,void * &&,HSTRING__ * &,Windows::System::IUser * &,uint &)
0x180077d68  mov     rcx, [rsp+0E8h]; this
0x180077d70  test    eax, eax
0x180077d72  js      loc_180078012
0x180077d78  lea     rdx, [rsp+0E8h+var_80]
0x180077d7d  lea     rcx, [rsp+0E8h+var_90]
0x180077d82  call    ??$As@UIUser@System@Windows@@@?$ComPtr@VUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::User>::As<Windows::System::IUser>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::IUser>>)
0x180077d87  mov     rcx, [rsp+0E8h]; this
0x180077d8f  test    eax, eax
0x180077d91  js      loc_180078026
0x180077d97  lea     rdx, [rsp+0E8h+var_78]
0x180077d9c  lea     rcx, [rsp+0E8h+var_80]
0x180077da1  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x180077da6  mov     rcx, [rsp+0E8h]; this
0x180077dae  test    eax, eax
0x180077db0  js      loc_18007803A
0x180077db6  mov     edx, dword ptr [rsp+0E8h+arg_50]
0x180077dbd  test    edx, edx
0x180077dbf  jz      short loc_180077DE2
0x180077dc1  mov     rcx, [rsp+0E8h+var_78]
0x180077dc6  mov     rax, [rcx]
0x180077dc9  mov     rax, [rax+38h]
0x180077dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077dd2  mov     rcx, [rsp+0E8h]; this
0x180077dda  test    eax, eax
0x180077ddc  js      loc_18007804E
0x180077de2  mov     rdx, [rsp+0E8h+arg_58]
0x180077dea  test    rdx, rdx
0x180077ded  jz      short loc_180077E20
0x180077def  mov     byte ptr [rsp+0E8h+arg_60], 0
0x180077df7  mov     rcx, [rsp+0E8h+var_78]
0x180077dfc  mov     rax, [rcx]
0x180077dff  lea     r8, [rsp+0E8h+arg_60]
0x180077e07  mov     rax, [rax+70h]
0x180077e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077e10  mov     rcx, [rsp+0E8h]; this
0x180077e18  test    eax, eax
0x180077e1a  js      loc_180078062
0x180077e20  mov     rax, [rsp+0E8h+var_80]
0x180077e25  mov     [rsp+0E8h+var_70], rax
0x180077e2a  mov     dword ptr [rsp+0E8h+arg_60], esi
0x180077e31  mov     dword ptr [rsp+0E8h+arg_60+4], r14d
0x180077e39  lea     r8, [rsp+0E8h+var_70]
0x180077e3e  lea     rdx, [rsp+0E8h+arg_60]
0x180077e46  lea     rcx, [rsp+0E8h+var_50]
0x180077e4e  call    ??$?0U?$pair@II@std@@PEAUIUser@System@Windows@@@?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@QEAA@$$QEAU?$pair@II@1@$$QEAPEAUIUser@System@Windows@@PEAPEAX@Z; std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>(std::pair<uint,uint> &&,Windows::System::IUser * &&,void * *)
0x180077e53  nop
0x180077e54  mov     r8, rax
0x180077e57  lea     rdx, [rsp+0E8h+var_70]
0x180077e5c  lea     rcx, [rdi+80h]
0x180077e63  call    ?insert@?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@2@$$QEAU?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::insert(std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>> &&)
0x180077e68  nop
0x180077e69  lea     rcx, [rsp+0E8h+var_48]
0x180077e71  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077e76  lea     rcx, [rdi+160h]
0x180077e7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077e82  nop
0x180077e83  lea     rcx, [rsp+0E8h+var_88]; this
0x180077e88  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x180077e8d  nop
0x180077e8e  mov     rcx, [rsp+0E8h+var_90]
0x180077e93  test    rcx, rcx
0x180077e96  jz      short loc_180077EA5
0x180077e98  mov     rax, [rcx]
0x180077e9b  mov     rax, [rax+10h]
0x180077e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077ea4  nop
0x180077ea5  lea     rcx, [rsp+0E8h+var_80]
0x180077eaa  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180077eaf  mov     r8, [rsp+0E8h+var_80]
0x180077eb4  mov     [r12], r8
0x180077eb8  lea     rcx, [rdi-38h]
0x180077ebc  mov     rax, [rcx]
0x180077ebf  lea     rdx, [rsp+0E8h+var_70]
0x180077ec4  mov     [rsp+0E8h+arg_60], rdx
0x180077ecc  lea     rdx, off_1800EFFE0
0x180077ed3  mov     [rsp+0E8h+var_70], rdx
0x180077ed8  lea     rdx, [rsp+0E8h+var_70]
0x180077edd  mov     [rsp+0E8h+var_58], rdx
0x180077ee5  lea     rdx, [rdi+180h]
0x180077eec  lea     r9, [rsp+0E8h+var_70]
0x180077ef1  mov     rax, [rax+40h]
0x180077ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077efa  mov     rcx, [rsp+0E8h]; this
0x180077f02  test    eax, eax
0x180077f04  js      loc_180078077
0x180077f0a  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180077f0f  mov     rbx, rax
0x180077f12  mov     edx, [rax]
0x180077f14  cmp     edx, 4
0x180077f17  jbe     loc_180077FB0
0x180077f1d  mov     dword ptr [rsp+0E8h+arg_60], 0
0x180077f28  mov     dword ptr [rsp+0E8h+var_90], r14d
0x180077f2d  xor     edx, edx; length
0x180077f2f  mov     rcx, [rsp+0E8h+string]; string
0x180077f37  call    cs:__imp_WindowsGetStringRawBuffer
0x180077f3d  mov     [rsp+0E8h+var_70], rax
0x180077f42  mov     [rsp+0E8h+var_88], r15
0x180077f47  xor     edx, edx; length
0x180077f49  mov     rcx, r13; string
0x180077f4c  call    cs:__imp_WindowsGetStringRawBuffer
0x180077f52  mov     [rsp+0E8h+var_50], rax
0x180077f5a  mov     [rsp+0E8h+var_98], esi
0x180077f5e  lea     rax, [rsp+0E8h+arg_60]
0x180077f66  mov     [rsp+0E8h+var_A0], rax
0x180077f6b  lea     rax, [rsp+0E8h+var_90]
0x180077f70  mov     [rsp+0E8h+var_A8], rax
0x180077f75  lea     rax, [rsp+0E8h+var_70]
0x180077f7a  mov     [rsp+0E8h+var_B0], rax
0x180077f7f  lea     rax, [rsp+0E8h+var_88]
0x180077f84  mov     [rsp+0E8h+var_B8], rax
0x180077f89  lea     rax, [rsp+0E8h+var_50]
0x180077f91  mov     [rsp+0E8h+var_C0], rax
0x180077f96  lea     rax, [rsp+0E8h+var_98]
0x180077f9b  mov     qword ptr [rsp+0E8h+var_C8], rax
0x180077fa0  lea     rdx, dword_18012265C
0x180077fa7  mov     rcx, rbx
0x180077faa  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180077faf  nop
0x180077fb0  lea     rcx, [rsp+0E8h+var_78]
0x180077fb5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077fba  nop
0x180077fbb  lea     rcx, [rsp+0E8h+var_80]
0x180077fc0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077fc5  xor     eax, eax
0x180077fc7  jmp     short loc_180077FD0
0x180077fc9  mov     eax, dword ptr [rsp+0E8h+arg_60]
0x180077fd0  add     rsp, 0B0h
0x180077fd7  pop     r15
0x180077fd9  pop     r14
0x180077fdb  pop     r13
0x180077fdd  pop     r12
0x180077fdf  pop     rdi
0x180077fe0  pop     rsi
0x180077fe1  pop     rbx
0x180077fe2  retn
0x180077fe3  mov     r9d, 80004003h; char *
0x180077fe9  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180077ff0  mov     edx, 8D5h; void *
0x180077ff5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180077ffb  mov     r9d, 80A20303h; char *
0x180078001  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180078008  mov     edx, 8F3h; void *
0x18007800d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180078012  mov     r9d, eax; char *
0x180078015  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x18007801c  mov     edx, 8FEh; void *
0x180078021  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180078026  mov     r9d, eax; char *
0x180078029  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180078030  mov     edx, 8FFh; void *
0x180078035  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007803a  mov     r9d, eax; char *
0x18007803d  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180078044  mov     edx, 900h; void *
0x180078049  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007804e  mov     r9d, eax; char *
0x180078051  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180078058  mov     edx, 903h; void *
0x18007805d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180078062  mov     r9d, eax; char *
0x180078065  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x18007806c  mov     edx, 908h; void *
0x180078071  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180078077  mov     r9d, eax; char *
0x18007807a  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180078081  mov     edx, 91Ch; void *
0x180078086  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
