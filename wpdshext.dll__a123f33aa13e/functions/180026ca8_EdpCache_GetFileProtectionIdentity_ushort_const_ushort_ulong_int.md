# EdpCache::_GetFileProtectionIdentity(ushort const *,ushort *,ulong,int)

- ea: `0x180026ca8`
- end: `0x1800273ce`
- name: `?_GetFileProtectionIdentity@EdpCache@@AEAAJPEBGPEAGKH@Z`
- size: `1830`
- prototype: `int(EdpCache *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180072884`

## callees

- `0x18001f6b0`
- `0x180026ca8`
- `0x180028f0c`
- `0x18002bc88`
- `0x18002beb8`
- `0x18002bee4`
- `0x18002e9f0`
- `0x180035590`
- `0x180039d74`
- `0x180039dd4`
- `0x1800723e0`
- `0x180072520`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180027375`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180027375`
- `KERNEL32!RaiseException` at `0x180026ed6`
- `KERNEL32!RaiseException` at `0x180026f8b`
- `KERNEL32!RaiseException` at `0x1800273c7`
- `KERNEL32!RaiseException` at `0x180026ed6`
- `KERNEL32!RaiseException` at `0x180026f8b`
- `KERNEL32!RaiseException` at `0x1800273c7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026d28`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026ef8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027144`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026d28`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180026ef8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800272cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027221`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800272cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027256`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027256`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026ec0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026f75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026ec0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026f75`

## string_xrefs

- `0x180026d3b`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180026dcb`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180026e5a`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180026f0b`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180026fb3`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180027016`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x1800270cb`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180027157`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x1800271a5`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x1800271fa`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x1800272b7`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180027119`: `Windows.Security.EnterpriseData.FileProtectionManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall EdpCache::_GetFileProtectionIdentity(
        EdpCache *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        int a5)
{
  HSTRING v7; // rbx
  int v8; // eax
  int v9; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdi
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, __int64 *); // rdi
  int v20; // eax
  HRESULT v21; // eax
  HSTRING v22; // rbx
  int ActivationFactory; // eax
  _QWORD *v24; // rbx
  __int64 v25; // rdi
  unsigned __int64 v26; // rdx
  HRESULT v27; // eax
  int v28; // eax
  __int64 v29; // rdi
  __int64 v30; // rcx
  __int64 v31; // rcx
  _QWORD *v32; // rcx
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, GUID *, __int64 *); // rdi
  int v35; // eax
  HSTRING v36; // rbx
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64, __int64 *); // rbx
  int v40; // eax
  __int64 v41; // rdi
  __int64 v42; // rdi
  __int64 (__fastcall *v43)(__int64, HSTRING *); // rbx
  int v44; // eax
  __int64 v45; // r9
  __int64 v46; // rdx
  PCWSTR StringRawBuffer; // rbx
  UINT32 v48; // r8d
  UINT32 v49; // [rsp+20h] [rbp-71h]
  __int64 v50; // [rsp+30h] [rbp-61h] BYREF
  _QWORD *v51; // [rsp+38h] [rbp-59h] BYREF
  HSTRING v52; // [rsp+40h] [rbp-51h] BYREF
  __int64 v53; // [rsp+48h] [rbp-49h] BYREF
  _QWORD v54[2]; // [rsp+50h] [rbp-41h] BYREF
  __int64 v55; // [rsp+60h] [rbp-31h] BYREF
  __int64 v56; // [rsp+68h] [rbp-29h] BYREF
  UINT32 length; // [rsp+70h] [rbp-21h] BYREF
  __int64 v58; // [rsp+78h] [rbp-19h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-11h] BYREF
  __int64 v60; // [rsp+88h] [rbp-9h] BYREF
  __int64 v61; // [rsp+90h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp+7h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v54[0] = a2;
  *a3 = 0;
  v50 = 0;
  if ( !a5 )
  {
    v51 = 0;
    string = 0;
    v21 = WindowsCreateStringReference(L"Windows.Storage.StorageFile", 0x1Bu, &hstringHeader, &string);
    if ( v21 < 0 )
    {
      RaiseException(v21, 1u, 0, 0);
      __debugbreak();
    }
    v22 = string;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    ActivationFactory = RoGetActivationFactory(v22, &GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f, &v51);
    v9 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v55 = 0;
      v24 = v51;
      v25 = *v51;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
      string = 0;
      v26 = -1;
      do
        ++v26;
      while ( a2[v26] );
      if ( v26 > 0xFFFFFFFF || (int)v26 + 1 < (unsigned int)v26 )
      {
        RaiseException(0x80070216, 1u, 0, 0);
        JUMPOUT(0x1800273CDLL);
      }
      v27 = WindowsCreateStringReference(a2, v26, &hstringHeader, &string);
      if ( v27 < 0 )
        RaiseException(v27, 1u, 0, 0);
      v28 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v25 + 48))(v24, string, &v55);
      v9 = v28;
      if ( v28 >= 0 )
      {
        v54[0] = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v54);
        v29 = v55;
        v9 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *>(v55);
        if ( v9 >= 0 )
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v29 + 64LL))(v29, v54);
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB3,
            (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
            (const char *)(unsigned int)v9,
            v49);
          v30 = v54[0];
          if ( v54[0] )
          {
            v54[0] = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
          v31 = v55;
          if ( v55 )
          {
            v55 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          }
          v32 = v51;
          if ( v51 )
          {
            v51 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
          }
          return (unsigned int)v9;
        }
        v33 = v54[0];
        v34 = **(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v54[0];
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
        v35 = v34(v33, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v50);
        v9 = v35;
        if ( v35 >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v54);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
          goto LABEL_45;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
          (const char *)(unsigned int)v35,
          v49);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v54);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
          (const char *)(unsigned int)v28,
          v49);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v49);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    goto LABEL_5;
  }
  v60 = 0;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Storage.StorageFolder",
    0x1Eu,
    0x1Du);
  v7 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
  v8 = RoGetActivationFactory(v7, &GUID_08f327ff_85d5_48b9_aee9_28511e339f9f, &v60);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
      (const char *)(unsigned int)v8,
      v49);
LABEL_4:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
LABEL_5:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    return (unsigned int)v9;
  }
  v61 = 0;
  v11 = v60;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v60 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v54);
  v14 = v12(v11, *(_QWORD *)(v13 + 24), &v61);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
      (const char *)(unsigned int)v14,
      v49);
LABEL_16:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
    goto LABEL_4;
  }
  v59 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  v15 = v61;
  v9 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> *>(v61);
  if ( v9 >= 0 )
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v15 + 64LL))(
           v15,
           &v59);
  if ( v9 < 0 )
  {
    v16 = (unsigned int)v9;
    v17 = 162;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
      (const char *)v16,
      v49);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
    goto LABEL_16;
  }
  v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
  v19 = **v59;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  v20 = v19(v18, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v50);
  v9 = v20;
  if ( v20 < 0 )
  {
    v16 = (unsigned int)v20;
    v17 = 165;
    goto LABEL_15;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v60);
LABEL_45:
  v53 = 0;
  string = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.EnterpriseData.FileProtectionManager",
    0x36u,
    0x35u);
  v36 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  v37 = RoGetActivationFactory(v36, &GUID_5846fc9b_e613_426b_bb38_88cba1dc9adb, &v53);
  v9 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
      (const char *)(unsigned int)v37,
      v49);
LABEL_63:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
    goto LABEL_5;
  }
  v56 = 0;
  v38 = v53;
  v39 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  v40 = v39(v38, v50, &v56);
  v9 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
      (const char *)(unsigned int)v40,
      v49);
LABEL_62:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
    goto LABEL_63;
  }
  v58 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  v41 = v56;
  v9 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::FileProtectionInfo *> *>(v56);
  if ( v9 >= 0 )
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 64LL))(v41, &v58);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
      (const char *)(unsigned int)v9,
      v49);
LABEL_61:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
    goto LABEL_62;
  }
  v52 = 0;
  v42 = v58;
  v43 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v58 + 64LL);
  WindowsDeleteString(0);
  v52 = 0;
  v44 = v43(v42, &v52);
  v9 = v44;
  if ( v44 < 0 )
  {
    v45 = (unsigned int)v44;
    v46 = 199;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v46,
      (unsigned int)"multimedia\\wpd\\ui\\shellext\\edpcache.cpp",
      (const char *)v45,
      v49);
    WindowsDeleteString(v52);
    v52 = 0;
    goto LABEL_61;
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v52, &length);
  v48 = length;
  if ( length + 1 > 0x104 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v49 = length;
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_26bd9f167370339dad26092ea255962f_Traceguids, 260);
    }
    v9 = -2147024774;
    v45 = 2147942522LL;
    v46 = 208;
    goto LABEL_60;
  }
  if ( length )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_26bd9f167370339dad26092ea255962f_Traceguids,
        (_DWORD)a2,
        (__int64)StringRawBuffer);
      v48 = length;
    }
    _o_wcsncpy_s(a3, 260, StringRawBuffer, v48);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_26bd9f167370339dad26092ea255962f_Traceguids, a2);
  }
  WindowsDeleteString(v52);
  v52 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  return 0;
}

```

## disassembly

```asm
0x180026ca8  mov     [rsp-8+arg_0], rbx
0x180026cad  push    rbp
0x180026cae  push    rsi
0x180026caf  push    rdi
0x180026cb0  push    r14
0x180026cb2  push    r15
0x180026cb4  lea     rbp, [rsp-2Fh]
0x180026cb9  sub     rsp, 0C0h
0x180026cc0  mov     rax, cs:__security_cookie
0x180026cc7  xor     rax, rsp
0x180026cca  mov     [rbp+4Fh+var_28], rax
0x180026cce  mov     r14, r8
0x180026cd1  mov     rsi, rdx
0x180026cd4  mov     [rbp+4Fh+var_90], rdx
0x180026cd8  xor     r15d, r15d
0x180026cdb  mov     [r8], r15w
0x180026cdf  mov     [rbp+4Fh+var_B0], r15
0x180026ce3  cmp     [rbp+4Fh+arg_20], r15d
0x180026ce7  jz      loc_180026EA4
0x180026ced  mov     [rbp+4Fh+var_58], r15
0x180026cf1  mov     [rbp+4Fh+string], r15
0x180026cf5  lea     r9d, [r15+1Dh]; unsigned int
0x180026cf9  lea     r8d, [r15+1Eh]; unsigned int
0x180026cfd  lea     rdx, ?RuntimeClass_Windows_Storage_StorageFolder@@3QBGB; "Windows.Storage.StorageFolder"
0x180026d04  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x180026d08  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180026d0d  mov     rbx, [rbp+4Fh+string]
0x180026d11  lea     rcx, [rbp+4Fh+var_58]
0x180026d15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026d1a  lea     r8, [rbp+4Fh+var_58]
0x180026d1e  lea     rdx, _GUID_08f327ff_85d5_48b9_aee9_28511e339f9f
0x180026d25  mov     rcx, rbx
0x180026d28  call    cs:__imp_RoGetActivationFactory
0x180026d2e  mov     ebx, eax
0x180026d30  test    eax, eax
0x180026d32  jns     short loc_180026D85
0x180026d34  mov     rcx, [rbp+57h]; this
0x180026d38  mov     r9d, eax; char *
0x180026d3b  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x180026d42  mov     edx, 9Ah; void *
0x180026d47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d4c  nop
0x180026d4d  lea     rcx, [rbp+4Fh+var_58]
0x180026d51  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026d56  nop
0x180026d57  lea     rcx, [rbp+4Fh+var_B0]
0x180026d5b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026d60  mov     eax, ebx
0x180026d62  mov     rcx, [rbp+4Fh+var_28]
0x180026d66  xor     rcx, rsp; StackCookie
0x180026d69  call    __security_check_cookie
0x180026d6e  mov     rbx, [rsp+0E0h+arg_0]
0x180026d76  add     rsp, 0C0h
0x180026d7d  pop     r15
0x180026d7f  pop     r14
0x180026d81  pop     rdi
0x180026d82  pop     rsi
0x180026d83  pop     rbp
0x180026d84  retn
0x180026d85  mov     [rbp+4Fh+var_50], r15
0x180026d89  mov     rdi, [rbp+4Fh+var_58]
0x180026d8d  mov     rax, [rdi]
0x180026d90  mov     rbx, [rax+30h]
0x180026d94  lea     rcx, [rbp+4Fh+var_50]
0x180026d98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026d9d  lea     rdx, [rbp+4Fh+var_90]
0x180026da1  lea     rcx, [rbp+4Fh+hstringHeader]
0x180026da5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180026daa  nop
0x180026dab  lea     r8, [rbp+4Fh+var_50]
0x180026daf  mov     rdx, [rax+18h]
0x180026db3  mov     rcx, rdi
0x180026db6  mov     rax, rbx
0x180026db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dbe  mov     ebx, eax
0x180026dc0  test    eax, eax
0x180026dc2  jns     short loc_180026DE1
0x180026dc4  mov     rcx, [rbp+57h]; this
0x180026dc8  mov     r9d, eax; char *
0x180026dcb  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x180026dd2  mov     edx, 9Eh; void *
0x180026dd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ddc  jmp     loc_180026E74
0x180026de1  mov     [rbp+4Fh+var_60], r15
0x180026de5  lea     rcx, [rbp+4Fh+var_60]
0x180026de9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026dee  mov     rdi, [rbp+4Fh+var_50]
0x180026df2  mov     rcx, rdi
0x180026df5  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStorageFolder@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> *>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFolder *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180026dfa  mov     ebx, eax
0x180026dfc  test    eax, eax
0x180026dfe  js      short loc_180026E15
0x180026e00  mov     rax, [rdi]
0x180026e03  lea     rdx, [rbp+4Fh+var_60]
0x180026e07  mov     rcx, rdi
0x180026e0a  mov     rax, [rax+40h]
0x180026e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e13  mov     ebx, eax
0x180026e15  test    ebx, ebx
0x180026e17  jns     short loc_180026E23
0x180026e19  mov     r9d, ebx
0x180026e1c  mov     edx, 0A2h
0x180026e21  jmp     short loc_180026E5A
0x180026e23  mov     rbx, [rbp+4Fh+var_60]
0x180026e27  mov     rax, [rbx]
0x180026e2a  mov     rdi, [rax]
0x180026e2d  lea     rcx, [rbp+4Fh+var_B0]
0x180026e31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e36  lea     r8, [rbp+4Fh+var_B0]
0x180026e3a  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180026e41  mov     rcx, rbx
0x180026e44  mov     rax, rdi
0x180026e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e4c  mov     ebx, eax
0x180026e4e  test    eax, eax
0x180026e50  jns     short loc_180026E82
0x180026e52  mov     r9d, eax; char *
0x180026e55  mov     edx, 0A5h; void *
0x180026e5a  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x180026e61  mov     rcx, [rbp+57h]; this
0x180026e65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026e6a  lea     rcx, [rbp+4Fh+var_60]
0x180026e6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e73  nop
0x180026e74  lea     rcx, [rbp+4Fh+var_50]
0x180026e78  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e7d  jmp     loc_180026D4D
0x180026e82  lea     rcx, [rbp+4Fh+var_60]
0x180026e86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e8b  nop
0x180026e8c  lea     rcx, [rbp+4Fh+var_50]
0x180026e90  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e95  nop
0x180026e96  lea     rcx, [rbp+4Fh+var_58]
0x180026e9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026e9f  jmp     loc_180027107
0x180026ea4  mov     [rbp+4Fh+var_A8], r15
0x180026ea8  mov     [rbp+4Fh+string], r15
0x180026eac  lea     r9, [rbp+4Fh+string]; string
0x180026eb0  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180026eb4  mov     edx, 1Bh; length
0x180026eb9  lea     rcx, ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x180026ec0  call    cs:__imp_WindowsCreateStringReference
0x180026ec6  test    eax, eax
0x180026ec8  jns     short loc_180026EDD
0x180026eca  xor     r9d, r9d; lpArguments
0x180026ecd  xor     r8d, r8d; nNumberOfArguments
0x180026ed0  lea     edx, [r9+1]; dwExceptionFlags
0x180026ed4  mov     ecx, eax; dwExceptionCode
0x180026ed6  call    cs:__imp_RaiseException
0x180026edc  int     3; Trap to Debugger
0x180026edd  mov     rbx, [rbp+4Fh+string]
0x180026ee1  lea     rcx, [rbp+4Fh+var_A8]
0x180026ee5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026eea  lea     r8, [rbp+4Fh+var_A8]
0x180026eee  lea     rdx, _GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f
0x180026ef5  mov     rcx, rbx
0x180026ef8  call    cs:__imp_RoGetActivationFactory
0x180026efe  mov     ebx, eax
0x180026f00  test    eax, eax
0x180026f02  jns     short loc_180026F2B
0x180026f04  mov     rcx, [rbp+57h]; this
0x180026f08  mov     r9d, eax; char *
0x180026f0b  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x180026f12  mov     edx, 0ABh; void *
0x180026f17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f1c  nop
0x180026f1d  lea     rcx, [rbp+4Fh+var_A8]
0x180026f21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026f26  jmp     loc_180026D57
0x180026f2b  mov     [rbp+4Fh+var_80], r15
0x180026f2f  mov     rbx, [rbp+4Fh+var_A8]
0x180026f33  mov     rdi, [rbx]
0x180026f36  lea     rcx, [rbp+4Fh+var_80]
0x180026f3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026f3f  mov     [rbp+4Fh+string], r15
0x180026f43  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180026f47  inc     rdx; length
0x180026f4a  cmp     [rsi+rdx*2], r15w
0x180026f4f  jnz     short loc_180026F47
0x180026f51  mov     eax, 0FFFFFFFFh
0x180026f56  cmp     rdx, rax
0x180026f59  ja      loc_1800273B8
0x180026f5f  lea     eax, [rdx+1]
0x180026f62  cmp     eax, edx
0x180026f64  jb      loc_1800273B8
0x180026f6a  lea     r9, [rbp+4Fh+string]; string
0x180026f6e  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180026f72  mov     rcx, rsi; sourceString
0x180026f75  call    cs:__imp_WindowsCreateStringReference
0x180026f7b  test    eax, eax
0x180026f7d  jns     short loc_180026F92
0x180026f7f  xor     r9d, r9d; lpArguments
0x180026f82  xor     r8d, r8d; nNumberOfArguments
0x180026f85  lea     edx, [r9+1]; dwExceptionFlags
0x180026f89  mov     ecx, eax; dwExceptionCode
0x180026f8b  call    cs:__imp_RaiseException
0x180026f91  nop
0x180026f92  lea     r8, [rbp+4Fh+var_80]
0x180026f96  mov     rdx, [rbp+4Fh+string]
0x180026f9a  mov     rcx, rbx
0x180026f9d  mov     rax, [rdi+30h]
0x180026fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fa6  mov     ebx, eax
0x180026fa8  test    eax, eax
0x180026faa  jns     short loc_180026FD3
0x180026fac  mov     rcx, [rbp+57h]; this
0x180026fb0  mov     r9d, eax; char *
0x180026fb3  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x180026fba  mov     edx, 0AFh; void *
0x180026fbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026fc4  nop
0x180026fc5  lea     rcx, [rbp+4Fh+var_80]
0x180026fc9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026fce  jmp     loc_180026F1D
0x180026fd3  mov     [rbp+4Fh+var_90], r15
0x180026fd7  lea     rcx, [rbp+4Fh+var_90]
0x180026fdb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026fe0  mov     rdi, [rbp+4Fh+var_80]
0x180026fe4  mov     rcx, rdi
0x180026fe7  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180026fec  mov     ebx, eax
0x180026fee  test    eax, eax
0x180026ff0  js      short loc_180027007
0x180026ff2  mov     rax, [rdi]
0x180026ff5  lea     rdx, [rbp+4Fh+var_90]
0x180026ff9  mov     rcx, rdi
0x180026ffc  mov     rax, [rax+40h]
0x180027000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027005  mov     ebx, eax
0x180027007  test    ebx, ebx
0x180027009  jns     loc_180027095
0x18002700f  mov     rcx, [rbp+57h]; this
0x180027013  mov     r9d, ebx; char *
0x180027016  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x18002701d  mov     edx, 0B3h; void *
0x180027022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027027  nop
0x180027028  mov     rcx, [rbp+4Fh+var_90]
0x18002702c  test    rcx, rcx
0x18002702f  jz      short loc_180027042
0x180027031  mov     [rbp+4Fh+var_90], r15
0x180027035  mov     rax, [rcx]
0x180027038  mov     rax, [rax+10h]
0x18002703c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027041  nop
0x180027042  mov     rcx, [rbp+4Fh+var_80]
0x180027046  test    rcx, rcx
0x180027049  jz      short loc_18002705C
0x18002704b  mov     [rbp+4Fh+var_80], r15
0x18002704f  mov     rax, [rcx]
0x180027052  mov     rax, [rax+10h]
0x180027056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002705b  nop
0x18002705c  mov     rcx, [rbp+4Fh+var_A8]
0x180027060  test    rcx, rcx
0x180027063  jz      short loc_180027076
0x180027065  mov     [rbp+4Fh+var_A8], r15
0x180027069  mov     rax, [rcx]
0x18002706c  mov     rax, [rax+10h]
0x180027070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027075  nop
0x180027076  mov     rcx, [rbp+4Fh+var_B0]
0x18002707a  test    rcx, rcx
0x18002707d  jz      short loc_180027090
0x18002707f  mov     [rbp+4Fh+var_B0], r15
0x180027083  mov     rax, [rcx]
0x180027086  mov     rax, [rax+10h]
0x18002708a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002708f  nop
0x180027090  jmp     loc_180026D60
0x180027095  mov     rbx, [rbp+4Fh+var_90]
0x180027099  mov     rax, [rbx]
0x18002709c  mov     rdi, [rax]
0x18002709f  lea     rcx, [rbp+4Fh+var_B0]
0x1800270a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800270a8  lea     r8, [rbp+4Fh+var_B0]
0x1800270ac  lea     rdx, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800270b3  mov     rcx, rbx
0x1800270b6  mov     rax, rdi
0x1800270b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270be  mov     ebx, eax
0x1800270c0  test    eax, eax
0x1800270c2  jns     short loc_1800270EA
0x1800270c4  mov     rcx, [rbp+57h]; this
0x1800270c8  mov     r9d, eax; char *
0x1800270cb  lea     r8, aMultimediaWpdU_1; "multimedia\\wpd\\ui\\shellext\\edpcache"...
0x1800270d2  mov     edx, 0B6h; void *
0x1800270d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800270dc  lea     rcx, [rbp+4Fh+var_90]
0x1800270e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800270e5  jmp     loc_180026FC5
0x1800270ea  lea     rcx, [rbp+4Fh+var_90]
0x1800270ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800270f3  nop
0x1800270f4  lea     rcx, [rbp+4Fh+var_80]
0x1800270f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800270fd  nop
0x1800270fe  lea     rcx, [rbp+4Fh+var_A8]
0x180027102  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
  ... truncated ...
```
