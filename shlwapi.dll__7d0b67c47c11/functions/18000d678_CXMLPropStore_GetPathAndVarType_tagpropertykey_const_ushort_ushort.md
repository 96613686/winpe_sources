# CXMLPropStore::_GetPathAndVarType(_tagpropertykey const &,ushort * *,ushort *)

- ea: `0x18000d678`
- end: `0x18000d97a`
- name: `?_GetPathAndVarType@CXMLPropStore@@IEAAJAEBU_tagpropertykey@@PEAPEAGPEAG@Z`
- size: `770`
- prototype: `int(CXMLPropStore *__hidden this, const struct _tagpropertykey *, unsigned __int16 **, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d5e0`
- `0x18002f8f0`

## callees

- `0x1800035f0`
- `0x180004e64`
- `0x18000d678`
- `0x18000eb1c`
- `0x1800100d8`
- `0x18001010c`
- `0x180012550`
- `0x18002d55c`
- `0x18002d858`
- `0x180031454`
- `0x180032030`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d7de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d7de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d779`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d779`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d738`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d738`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d84f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d84f`
- `PROPSYS!PSGetPropertyDescription` at `0x18000d80c`
- `PROPSYS!PSGetPropertyDescription` at `0x18000d80c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d942`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d8ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d942`

## string_xrefs

- `0x18000d788`: `XPath`

## pseudocode

```c
__int64 __fastcall CXMLPropStore::_GetPathAndVarType(
        HKEY *this,
        const struct _tagpropertykey *a2,
        unsigned __int16 **a3,
        unsigned __int16 *a4)
{
  int v8; // edi
  HKEY v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rcx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rbx
  __int64 v14; // rcx
  DWORD phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v20[4]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[80]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  *a3 = 0;
  v8 = CXMLPropStore::_EnsureXPathProps((CXMLPropStore *)this);
  if ( v8 >= 0 )
  {
    v8 = -2147467259;
    if ( !this[9] )
      goto LABEL_11;
    if ( (int)SHStringFromGUIDW(a2, v23, 39) < 0 )
      goto LABEL_11;
    phkResult = a2->pid;
    if ( (int)StringCchPrintfW(SubKey, 0x104u, L"%s\\%d", v23, phkResult) < 0 )
      goto LABEL_11;
    v9 = this[9];
    hKey = 0;
    if ( RegOpenKeyExW(v9, SubKey, 0, 0x20019u, &hKey) )
      goto LABEL_11;
    *(_DWORD *)Data = 0;
    cbData[0] = 4;
    if ( !RegQueryValueExW(hKey, L"VT", 0, 0, Data, cbData) )
    {
      *(_QWORD *)v20 = 0;
      v21 = 0;
      v22 = 0;
      v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
             (BYTE **)v20,
             hKey,
             L"XPath");
      if ( v8 >= 0 )
      {
        *a3 = *(unsigned __int16 **)v20;
        *a4 = *(_WORD *)Data;
        *(_QWORD *)v20 = 0;
        v22 = 0;
        v21 = 0;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v20);
    }
    RegCloseKey(hKey);
    if ( v8 < 0 )
    {
LABEL_11:
      *a4 = 1;
      ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(cbData);
      if ( PSGetPropertyDescription(a2, &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, (void **)cbData) >= 0 )
      {
        hKey = 0;
        if ( (*(int (__fastcall **)(_QWORD, HKEY *))(**(_QWORD **)cbData + 32LL))(*(_QWORD *)cbData, &hKey) >= 0 )
        {
          v10 = ATL::CComBSTR::Length((ATL::CComBSTR *)(this + 18));
          v11 = v10 + lstrlenW((LPCWSTR)hKey) + 1;
          v12 = (int)v11;
          if ( (int)_AllocArray<unsigned short,CTCoAllocPolicy>(v11, 1, (int)v11, a3) >= 0 )
          {
            v8 = StringCchPrintfW(*a3, v12, (const unsigned __int16 *)this[18], hKey);
            if ( v8 >= 0 )
              (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**(_QWORD **)cbData + 40LL))(*(_QWORD *)cbData, a4);
          }
          CoTaskMemFree(hKey);
        }
      }
      if ( v8 >= 0 )
        goto LABEL_25;
      if ( (int)SHStringFromGUIDW(a2, v23, 39) < 0 || (int)StringCchPrintfW(v20, 0xFu, L"%d", a2->pid) < 0 )
      {
        v8 = -2147467259;
      }
      else
      {
        v13 = (int)(ATL::CComBSTR::Length((ATL::CComBSTR *)(this + 15)) + 55);
        v8 = _AllocArray<unsigned short,CTCoAllocPolicy>(v14, 1, v13, a3);
        if ( v8 >= 0 )
        {
          v8 = StringCchPrintfW(*a3, v13, (const unsigned __int16 *)this[15], v23, v20);
          if ( v8 >= 0 )
            goto LABEL_25;
        }
      }
      CoTaskMemFree(*a3);
      *a3 = 0;
LABEL_25:
      ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(cbData);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000d678  push    rbp
0x18000d67a  push    rbx
0x18000d67b  push    rsi
0x18000d67c  push    rdi
0x18000d67d  push    r12
0x18000d67f  push    r13
0x18000d681  push    r14
0x18000d683  push    r15
0x18000d685  lea     rbp, [rsp-1E8h]
0x18000d68d  sub     rsp, 2E8h
0x18000d694  mov     rax, cs:__security_cookie
0x18000d69b  xor     rax, rsp
0x18000d69e  mov     [rbp+220h+var_50], rax
0x18000d6a5  xor     r13d, r13d
0x18000d6a8  mov     r12, r9
0x18000d6ab  mov     [r8], r13
0x18000d6ae  mov     rsi, r8
0x18000d6b1  mov     r14, rdx
0x18000d6b4  mov     r15, rcx
0x18000d6b7  call    ?_EnsureXPathProps@CXMLPropStore@@IEAAJXZ; CXMLPropStore::_EnsureXPathProps(void)
0x18000d6bc  mov     edi, eax
0x18000d6be  test    eax, eax
0x18000d6c0  js      loc_18000D955
0x18000d6c6  mov     edi, 80004005h
0x18000d6cb  cmp     [r15+48h], r13
0x18000d6cf  jz      loc_18000D7EC
0x18000d6d5  lea     r8d, [r13+27h]
0x18000d6d9  mov     rcx, r14
0x18000d6dc  lea     rdx, [rsp+320h+var_2B0]
0x18000d6e1  call    SHStringFromGUIDW
0x18000d6e6  test    eax, eax
0x18000d6e8  js      loc_18000D7EC
0x18000d6ee  mov     eax, [r14+10h]
0x18000d6f2  lea     r9, [rsp+320h+var_2B0]
0x18000d6f7  lea     r8, aSD; "%s\\%d"
0x18000d6fe  mov     dword ptr [rsp+320h+phkResult], eax
0x18000d702  mov     edx, 104h; unsigned __int64
0x18000d707  lea     rcx, [rbp+220h+SubKey]; unsigned __int16 *
0x18000d70b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d710  test    eax, eax
0x18000d712  js      loc_18000D7EC
0x18000d718  mov     rcx, [r15+48h]; hKey
0x18000d71c  lea     rax, [rsp+320h+hKey]
0x18000d721  mov     r9d, 20019h; samDesired
0x18000d727  mov     [rsp+320h+phkResult], rax; phkResult
0x18000d72c  xor     r8d, r8d; ulOptions
0x18000d72f  mov     [rsp+320h+hKey], r13
0x18000d734  lea     rdx, [rbp+220h+SubKey]; lpSubKey
0x18000d738  call    cs:__imp_RegOpenKeyExW
0x18000d73e  test    eax, eax
0x18000d740  jnz     loc_18000D7EC
0x18000d746  mov     rcx, [rsp+320h+hKey]; hKey
0x18000d74b  lea     rax, [rsp+320h+cbData]
0x18000d750  mov     [rsp+320h+lpcbData], rax; lpcbData
0x18000d755  lea     rdx, ValueName; "VT"
0x18000d75c  lea     rax, [rsp+320h+Data]
0x18000d761  mov     dword ptr [rsp+320h+Data], r13d
0x18000d766  xor     r9d, r9d; lpType
0x18000d769  mov     [rsp+320h+phkResult], rax; lpData
0x18000d76e  xor     r8d, r8d; lpReserved
0x18000d771  mov     [rsp+320h+cbData], 4
0x18000d779  call    cs:__imp_RegQueryValueExW
0x18000d77f  test    eax, eax
0x18000d781  jnz     short loc_18000D7D9
0x18000d783  mov     rdx, [rsp+320h+hKey]
0x18000d788  lea     r8, aXpath; "XPath"
0x18000d78f  lea     rcx, [rsp+320h+var_2D8]
0x18000d794  mov     qword ptr [rsp+320h+var_2D8], r13
0x18000d799  mov     [rsp+320h+var_2D0], r13
0x18000d79e  mov     [rsp+320h+var_2C8], r13
0x18000d7a3  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x18000d7a8  mov     edi, eax
0x18000d7aa  test    eax, eax
0x18000d7ac  js      short loc_18000D7CF
0x18000d7ae  mov     rax, qword ptr [rsp+320h+var_2D8]
0x18000d7b3  mov     [rsi], rax
0x18000d7b6  movzx   eax, word ptr [rsp+320h+Data]
0x18000d7bb  mov     [r12], ax
0x18000d7c0  mov     qword ptr [rsp+320h+var_2D8], r13
0x18000d7c5  mov     [rsp+320h+var_2C8], r13
0x18000d7ca  mov     [rsp+320h+var_2D0], r13
0x18000d7cf  lea     rcx, [rsp+320h+var_2D8]
0x18000d7d4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000d7d9  mov     rcx, [rsp+320h+hKey]; hKey
0x18000d7de  call    cs:__imp_RegCloseKey
0x18000d7e4  test    edi, edi
0x18000d7e6  jns     loc_18000D955
0x18000d7ec  lea     rcx, [rsp+320h+cbData]
0x18000d7f1  mov     word ptr [r12], 1
0x18000d7f8  call    ??0?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::CComPtr<IXMLDOMText>(void)
0x18000d7fd  lea     r8, [rsp+320h+cbData]; ppv
0x18000d802  mov     rcx, r14; propkey
0x18000d805  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x18000d80c  call    cs:__imp_PSGetPropertyDescription
0x18000d812  test    eax, eax
0x18000d814  js      loc_18000D8B2
0x18000d81a  mov     rcx, qword ptr [rsp+320h+cbData]
0x18000d81f  lea     rdx, [rsp+320h+hKey]
0x18000d824  mov     [rsp+320h+hKey], r13
0x18000d829  mov     rax, [rcx]
0x18000d82c  mov     rax, [rax+20h]
0x18000d830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d835  test    eax, eax
0x18000d837  js      short loc_18000D8B2
0x18000d839  lea     r13, [r15+90h]
0x18000d840  mov     rcx, r13; this
0x18000d843  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x18000d848  mov     rcx, [rsp+320h+hKey]; lpString
0x18000d84d  mov     ebx, eax
0x18000d84f  call    cs:__imp_lstrlenW
0x18000d855  mov     r9, rsi
0x18000d858  mov     edx, 1
0x18000d85d  lea     ecx, [rax+1]
0x18000d860  add     ecx, ebx
0x18000d862  movsxd  rbx, ecx
0x18000d865  mov     r8, rbx
0x18000d868  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18000d86d  test    eax, eax
0x18000d86f  js      short loc_18000D8A4
0x18000d871  mov     r9, [rsp+320h+hKey]
0x18000d876  mov     rdx, rbx; unsigned __int64
0x18000d879  mov     r8, [r13+0]; unsigned __int16 *
0x18000d87d  mov     rcx, [rsi]; unsigned __int16 *
0x18000d880  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d885  xor     r13d, r13d
0x18000d888  mov     edi, eax
0x18000d88a  test    eax, eax
0x18000d88c  js      short loc_18000D8A7
0x18000d88e  mov     rcx, qword ptr [rsp+320h+cbData]
0x18000d893  mov     rdx, r12
0x18000d896  mov     rax, [rcx]
0x18000d899  mov     rax, [rax+28h]
0x18000d89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a2  jmp     short loc_18000D8A7
0x18000d8a4  xor     r13d, r13d
0x18000d8a7  mov     rcx, [rsp+320h+hKey]; pv
0x18000d8ac  call    cs:__imp_CoTaskMemFree
0x18000d8b2  test    edi, edi
0x18000d8b4  jns     loc_18000D94B
0x18000d8ba  mov     r8d, 27h ; '''
0x18000d8c0  lea     rdx, [rsp+320h+var_2B0]
0x18000d8c5  mov     rcx, r14
0x18000d8c8  call    SHStringFromGUIDW
0x18000d8cd  test    eax, eax
0x18000d8cf  js      short loc_18000D93A
0x18000d8d1  mov     r9d, [r14+10h]
0x18000d8d5  lea     r8, aD; "%d"
0x18000d8dc  mov     edx, 0Fh; unsigned __int64
0x18000d8e1  lea     rcx, [rsp+320h+var_2D8]; unsigned __int16 *
0x18000d8e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d8eb  test    eax, eax
0x18000d8ed  js      short loc_18000D93A
0x18000d8ef  lea     rcx, [r15+78h]; this
0x18000d8f3  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x18000d8f8  add     eax, 37h ; '7'
0x18000d8fb  mov     r9, rsi
0x18000d8fe  movsxd  rbx, eax
0x18000d901  mov     edx, 1
0x18000d906  mov     r8, rbx
0x18000d909  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18000d90e  mov     edi, eax
0x18000d910  test    eax, eax
0x18000d912  js      short loc_18000D93F
0x18000d914  mov     r8, [r15+78h]; unsigned __int16 *
0x18000d918  lea     rax, [rsp+320h+var_2D8]
0x18000d91d  mov     rcx, [rsi]; unsigned __int16 *
0x18000d920  lea     r9, [rsp+320h+var_2B0]
0x18000d925  mov     rdx, rbx; unsigned __int64
0x18000d928  mov     [rsp+320h+phkResult], rax
0x18000d92d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d932  mov     edi, eax
0x18000d934  test    eax, eax
0x18000d936  js      short loc_18000D93F
0x18000d938  jmp     short loc_18000D94B
0x18000d93a  mov     edi, 80004005h
0x18000d93f  mov     rcx, [rsi]; pv
0x18000d942  call    cs:__imp_CoTaskMemFree
0x18000d948  mov     [rsi], r13
0x18000d94b  lea     rcx, [rsp+320h+cbData]
0x18000d950  call    ??1?$CComPtr@UIXMLDOMText@@@ATL@@QEAA@XZ; ATL::CComPtr<IXMLDOMText>::~CComPtr<IXMLDOMText>(void)
0x18000d955  mov     eax, edi
0x18000d957  mov     rcx, [rbp+220h+var_50]
0x18000d95e  xor     rcx, rsp; StackCookie
0x18000d961  call    __security_check_cookie
0x18000d966  add     rsp, 2E8h
0x18000d96d  pop     r15
0x18000d96f  pop     r14
0x18000d971  pop     r13
0x18000d973  pop     r12
0x18000d975  pop     rdi
0x18000d976  pop     rsi
0x18000d977  pop     rbx
0x18000d978  pop     rbp
0x18000d979  retn
```
