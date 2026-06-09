# Windows::System::Internal::Implementation::RegUtil::ReadValues(HKEY__ *,Windows::Foundation::Collections::IPropertySet * *,std::function<bool (ushort const *)>)

- ea: `0x18004f770`
- end: `0x18004fb68`
- name: `?ReadValues@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEAPEAUIPropertySet@Collections@Foundation@5@V?$function@$$A6A_NPEBG@Z@std@@@Z`
- size: `1016`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004f294`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x1800154b0`
- `0x1800181f0`
- `0x180019600`
- `0x180040a04`
- `0x18004c06c`
- `0x18004e508`
- `0x18004f770`
- `0x180050c38`
- `0x1800513d0`
- `0x18006c380`
- `0x180074aa0`
- `0x1800755e8`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18004faf7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18004faf7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004f8cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004f8cb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004f991`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004f991`

## string_xrefs

- `0x18004f7bc`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004f847`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004f87d`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004f8e0`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004f949`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004f9a6`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004fa89`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004fae2`: `onecore\ds\security\umstartup\usermgr\lib\regutil.h`
- `0x18004fa4a`: `onecore\ds\security\umstartup\usermgr\lib\comutils.h`
- `0x18004fa67`: `IFC(onecore\ds\security\umstartup\usermgr\lib\comutils.h_362)`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::System::Internal::Implementation::RegUtil::ReadValues(HKEY hKey, _QWORD *a2, __int64 a3)
{
  int v6; // eax
  int v7; // eax
  unsigned int v8; // eax
  unsigned __int64 v9; // rax
  WCHAR *v10; // r8
  DWORD i; // r14d
  unsigned int v12; // eax
  __int64 v13; // rdi
  HSTRING_HEADER *v14; // r10
  int v15; // eax
  int v16; // edi
  __int64 v17; // rcx
  int v18; // eax
  const char *v19; // r9
  __int64 result; // rax
  int lpcSubKeys; // [rsp+20h] [rbp-108h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-108h]
  _BYTE v23[4]; // [rsp+60h] [rbp-C8h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-C4h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-C0h] BYREF
  LPCWSTR lpValueName; // [rsp+70h] [rbp-B8h] BYREF
  DWORD cValues; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+80h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+88h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-98h] BYREF
  __int64 v31; // [rsp+98h] [rbp-90h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-88h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-80h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-68h]
  HSTRING_HEADER v35; // [rsp+C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  try
  {
    v32 = a3;
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)0x80004003LL,
        lpcSubKeys);
    *a2 = 0;
    cValues = 0;
    cbMaxValueNameLen = 0;
    lpValueName = 0;
    v30 = 0;
    v29 = 0;
    v31 = 0;
    v23[0] = 0;
    v34 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Collections.PropertySet",
      0x2Bu,
      0x2Au);
    v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
           v34,
           &v30);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)(unsigned int)v6,
        lpcSubKeys);
    v7 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v30,
           (__int64)&v29);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)(unsigned int)v7,
        lpcSubKeys);
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)v8,
        lpcSubKeysa);
    v9 = 2LL * (cbMaxValueNameLen + 1);
    if ( !is_mul_ok(cbMaxValueNameLen + 1, 2u) )
      v9 = -1;
    v10 = (WCHAR *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
    lpValueName = v10;
    hstringHeader.Reserved.Reserved1 = &lpValueName;
    hstringHeader.Reserved.Reserved2[8] = 1;
    if ( !v10 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)0x8007000ELL,
        lpcSubKeysa);
    for ( i = 0; i < cValues; ++i )
    {
      cchValueName = cbMaxValueNameLen + 1;
      v12 = RegEnumValueW(hKey, i, v10, &cchValueName, 0, 0, 0, 0);
      if ( v12 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xAD,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
          (const char *)v12,
          lpcSubKeysa);
      if ( !*(_QWORD *)(a3 + 24)
        || (unsigned __int8)std::_Func_class<bool,unsigned short const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(
                              a3,
                              lpValueName) )
      {
        v28 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
        Windows::System::Internal::Implementation::RegUtil::ReadValue<Windows::Foundation::IPropertyValue *>(
          hKey,
          lpValueName,
          &v28);
        v13 = v28;
        v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v35, &lpValueName);
        v15 = (*(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v29 + 80LL))(
                v29,
                v14[1].Reserved.Reserved1,
                v13,
                v23);
        v16 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16A,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h",
            (const char *)(unsigned int)v15,
            lpcSubKeysa);
          if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 2) != 0 )
            McTemplateU0zd_EventWriteTransfer(
              v17,
              LogWarning,
              L"IFC(onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.h_362)",
              (unsigned int)v16);
        }
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xB6,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
            (const char *)(unsigned int)v16,
            lpcSubKeysa);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      }
      v10 = (WCHAR *)lpValueName;
    }
    v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v29)(
            v29,
            &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
            a2);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
        (const char *)(unsigned int)v18,
        lpcSubKeysa);
    operator delete[]((void *)lpValueName);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    std::function<bool (unsigned short const *,IInspectable *)>::~function<bool (unsigned short const *,IInspectable *)>(a3);
    result = 0;
  }
  catch ( ... )
  {
    cchValueName = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xBD,
                     (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\regutil.h",
                     v19);
    std::function<bool (unsigned short const *,IInspectable *)>::~function<bool (unsigned short const *,IInspectable *)>(v32);
    return cchValueName;
  }
  return result;
}

```

## disassembly

```asm
0x18004f770  push    rbx
0x18004f772  push    rsi
0x18004f773  push    rdi
0x18004f774  push    r12
0x18004f776  push    r13
0x18004f778  push    r14
0x18004f77a  push    r15
0x18004f77c  sub     rsp, 0F0h
0x18004f783  mov     rax, cs:__security_cookie
0x18004f78a  xor     rax, rsp
0x18004f78d  mov     [rsp+128h+var_40], rax
0x18004f795  mov     rsi, r8
0x18004f798  mov     r15, rdx
0x18004f79b  mov     r12, rcx
0x18004f79e  mov     [rsp+128h+var_88], r8
0x18004f7a6  mov     rcx, [rsp+128h]; this
0x18004f7ae  xor     r13d, r13d
0x18004f7b1  test    rdx, rdx
0x18004f7b4  jnz     short loc_18004F7CD
0x18004f7b6  mov     r9d, 80004003h; char *
0x18004f7bc  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f7c3  mov     edx, 93h; void *
0x18004f7c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f7cd  mov     [rdx], r13
0x18004f7d0  mov     [rsp+128h+cValues], r13d
0x18004f7d5  mov     [rsp+128h+cbMaxValueNameLen], r13d
0x18004f7da  mov     [rsp+128h+lpValueName], r13
0x18004f7df  mov     [rsp+128h+var_98], r13
0x18004f7e7  mov     [rsp+128h+var_A0], r13
0x18004f7ef  mov     [rsp+128h+var_90], r13
0x18004f7f7  mov     [rsp+128h+var_C8], r13b
0x18004f7fc  mov     [rsp+128h+var_68], r13
0x18004f804  mov     r9d, 2Ah ; '*'; unsigned int
0x18004f80a  lea     r8d, [r9+1]; unsigned int
0x18004f80e  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x18004f815  lea     rcx, [rsp+128h+hstringHeader]; hstringHeader
0x18004f81d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004f822  nop
0x18004f823  lea     rdx, [rsp+128h+var_98]
0x18004f82b  mov     rcx, [rsp+128h+var_68]
0x18004f833  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18004f838  mov     rcx, [rsp+128h]; this
0x18004f840  test    eax, eax
0x18004f842  jns     short loc_18004F859
0x18004f844  mov     r9d, eax; char *
0x18004f847  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f84e  mov     edx, 0A1h; void *
0x18004f853  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f859  lea     rdx, [rsp+128h+var_A0]
0x18004f861  lea     rcx, [rsp+128h+var_98]
0x18004f869  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18004f86e  mov     rcx, [rsp+128h]; this
0x18004f876  test    eax, eax
0x18004f878  jns     short loc_18004F88E
0x18004f87a  mov     r9d, eax; char *
0x18004f87d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f884  mov     edx, 0A3h; void *
0x18004f889  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f88e  mov     [rsp+128h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18004f893  mov     [rsp+128h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18004f898  mov     [rsp+128h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18004f89d  lea     rax, [rsp+128h+cbMaxValueNameLen]
0x18004f8a2  mov     [rsp+128h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18004f8a7  lea     rax, [rsp+128h+cValues]
0x18004f8ac  mov     [rsp+128h+lpcValues], rax; lpcValues
0x18004f8b1  mov     [rsp+128h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18004f8b6  mov     [rsp+128h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18004f8bb  mov     [rsp+128h+lpcSubKeys], r13; int
0x18004f8c0  xor     r9d, r9d; lpReserved
0x18004f8c3  xor     r8d, r8d; lpcchClass
0x18004f8c6  xor     edx, edx; lpClass
0x18004f8c8  mov     rcx, r12; hKey
0x18004f8cb  call    cs:__imp_RegQueryInfoKeyW
0x18004f8d1  mov     rcx, [rsp+128h]; this
0x18004f8d9  test    eax, eax
0x18004f8db  jz      short loc_18004F8F1
0x18004f8dd  mov     r9d, eax; char *
0x18004f8e0  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f8e7  mov     edx, 0A5h; void *
0x18004f8ec  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004f8f1  mov     ecx, [rsp+128h+cbMaxValueNameLen]
0x18004f8f5  inc     ecx
0x18004f8f7  mov     eax, 2
0x18004f8fc  mul     rcx
0x18004f8ff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004f906  cmovb   rax, rcx
0x18004f90a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f911  mov     rcx, rax; unsigned __int64
0x18004f914  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004f919  mov     r8, rax; lpValueName
0x18004f91c  mov     [rsp+128h+lpValueName], rax
0x18004f921  lea     rbx, [rsp+128h+lpValueName]
0x18004f926  mov     qword ptr [rsp+128h+hstringHeader.Reserved], rbx
0x18004f92e  mov     byte ptr [rsp+128h+hstringHeader.Reserved+8], 1
0x18004f936  mov     rcx, [rsp+128h]; this
0x18004f93e  test    rax, rax
0x18004f941  jnz     short loc_18004F95A
0x18004f943  mov     r9d, 8007000Eh; char *
0x18004f949  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f950  mov     edx, 0A9h; void *
0x18004f955  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f95a  mov     r14d, r13d
0x18004f95d  cmp     r14d, [rsp+128h+cValues]
0x18004f962  jnb     loc_18004FAB5
0x18004f968  mov     eax, [rsp+128h+cbMaxValueNameLen]
0x18004f96c  inc     eax
0x18004f96e  mov     [rsp+128h+cchValueName], eax
0x18004f972  mov     [rsp+128h+lpcValues], r13; lpcbData
0x18004f977  mov     [rsp+128h+lpcbMaxClassLen], r13; lpData
0x18004f97c  mov     [rsp+128h+lpcbMaxSubKeyLen], r13; lpType
0x18004f981  mov     [rsp+128h+lpcSubKeys], r13; int
0x18004f986  lea     r9, [rsp+128h+cchValueName]; lpcchValueName
0x18004f98b  mov     edx, r14d; dwIndex
0x18004f98e  mov     rcx, r12; hKey
0x18004f991  call    cs:__imp_RegEnumValueW
0x18004f997  mov     rcx, [rsp+128h]; this
0x18004f99f  test    eax, eax
0x18004f9a1  jz      short loc_18004F9B7
0x18004f9a3  mov     r9d, eax; char *
0x18004f9a6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f9ad  mov     edx, 0ADh; void *
0x18004f9b2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004f9b7  cmp     [rsi+18h], r13
0x18004f9bb  jz      short loc_18004F9D2
0x18004f9bd  mov     rdx, [rsp+128h+lpValueName]
0x18004f9c2  mov     rcx, rsi
0x18004f9c5  call    ??R?$_Func_class@_NPEBGU_Nil@std@@U12@U12@U12@U12@U12@@std@@QEBA_NPEBG@Z; std::_Func_class<bool,ushort const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::operator()(ushort const *)
0x18004f9ca  test    al, al
0x18004f9cc  jz      loc_18004FAA8
0x18004f9d2  mov     [rsp+128h+var_A8], r13
0x18004f9da  lea     rcx, [rsp+128h+var_A8]
0x18004f9e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f9e7  lea     r8, [rsp+128h+var_A8]
0x18004f9ef  mov     rdx, [rsp+128h+lpValueName]; lpValueName
0x18004f9f4  mov     rcx, r12; hKey
0x18004f9f7  call    ??$ReadValue@PEAUIPropertyValue@Foundation@Windows@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAPEAUIPropertyValue@Foundation@4@@Z; Windows::System::Internal::Implementation::RegUtil::ReadValue<Windows::Foundation::IPropertyValue *>(HKEY__ *,ushort const *,Windows::Foundation::IPropertyValue * *)
0x18004f9fc  mov     rdi, [rsp+128h+var_A8]
0x18004fa04  lea     rdx, [rsp+128h+lpValueName]
0x18004fa09  lea     rcx, [rsp+128h+var_60]
0x18004fa11  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004fa16  mov     r10, rax
0x18004fa19  mov     rcx, [rsp+128h+var_A0]
0x18004fa21  mov     rdx, [rcx]
0x18004fa24  mov     rax, [rdx+50h]
0x18004fa28  lea     r9, [rsp+128h+var_C8]
0x18004fa2d  mov     r8, rdi
0x18004fa30  mov     rdx, [r10+18h]
0x18004fa34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fa39  mov     edi, eax
0x18004fa3b  mov     rcx, [rsp+128h]; this
0x18004fa43  test    eax, eax
0x18004fa45  jns     short loc_18004FA7A
0x18004fa47  mov     r9d, eax; char *
0x18004fa4a  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\umstartup\\userm"...
0x18004fa51  mov     edx, 16Ah; void *
0x18004fa56  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004fa5b  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 2
0x18004fa62  jz      short loc_18004FA7A
0x18004fa64  mov     r9d, edi
0x18004fa67  lea     r8, aIfcOnecoreDsSe_15; "IFC(onecore\\ds\\security\\umstartup\\u"...
0x18004fa6e  lea     rdx, LogWarning
0x18004fa75  call    McTemplateU0zd_EventWriteTransfer
0x18004fa7a  mov     rcx, [rsp+128h]; this
0x18004fa82  test    edi, edi
0x18004fa84  jns     short loc_18004FA9B
0x18004fa86  mov     r9d, edi; char *
0x18004fa89  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004fa90  mov     edx, 0B6h; void *
0x18004fa95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004fa9b  lea     rcx, [rsp+128h+var_A8]
0x18004faa3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004faa8  inc     r14d
0x18004faab  mov     r8, [rsp+128h+lpValueName]
0x18004fab0  jmp     loc_18004F95D
0x18004fab5  mov     rcx, [rsp+128h+var_A0]
0x18004fabd  mov     rax, [rcx]
0x18004fac0  mov     r8, r15
0x18004fac3  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x18004faca  mov     rax, [rax]
0x18004facd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fad2  nop
0x18004fad3  mov     rcx, [rsp+128h]; this
0x18004fadb  test    eax, eax
0x18004fadd  jns     short loc_18004FAF4
0x18004fadf  mov     r9d, eax; char *
0x18004fae2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\umstartup\\userm"...
0x18004fae9  mov     edx, 0B9h; void *
0x18004faee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004faf4  mov     rcx, [rbx]
0x18004faf7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18004fafd  nop
0x18004fafe  lea     rcx, [rsp+128h+var_90]
0x18004fb06  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fb0b  nop
0x18004fb0c  lea     rcx, [rsp+128h+var_A0]
0x18004fb14  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fb19  nop
0x18004fb1a  lea     rcx, [rsp+128h+var_98]
0x18004fb22  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004fb27  nop
0x18004fb28  mov     rcx, rsi
0x18004fb2b  call    ??1?$function@$$A6A_NPEBGPEAUIInspectable@@@Z@std@@QEAA@XZ; std::function<bool (ushort const *,IInspectable *)>::~function<bool (ushort const *,IInspectable *)>(void)
0x18004fb30  xor     eax, eax
0x18004fb32  jmp     short loc_18004FB45
0x18004fb34  mov     rcx, [rsp+128h+var_88]
0x18004fb3c  call    ??1?$function@$$A6A_NPEBGPEAUIInspectable@@@Z@std@@QEAA@XZ; std::function<bool (ushort const *,IInspectable *)>::~function<bool (ushort const *,IInspectable *)>(void)
0x18004fb41  mov     eax, [rsp+128h+cchValueName]
0x18004fb45  mov     rcx, [rsp+128h+var_40]
0x18004fb4d  xor     rcx, rsp; StackCookie
0x18004fb50  call    __security_check_cookie
0x18004fb55  add     rsp, 0F0h
0x18004fb5c  pop     r15
0x18004fb5e  pop     r14
0x18004fb60  pop     r13
0x18004fb62  pop     r12
0x18004fb64  pop     rdi
0x18004fb65  pop     rsi
0x18004fb66  pop     rbx
0x18004fb67  retn
```
