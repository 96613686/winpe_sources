# ShellMRTHelper::MRTHelperBase::Resolve(ShellMRTHelper::MRTHelperBase::MRTResolutionType,ushort const *,ushort * *)

- ea: `0x1801383c0`
- end: `0x180138ab2`
- name: `?Resolve@MRTHelperBase@ShellMRTHelper@@AEAAJW4MRTResolutionType@12@PEBGPEAPEAG@Z`
- size: `1778`
- prototype: `int __high(enum ShellMRTHelper::MRTHelperBase::MRTResolutionType, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180320a78`

## callees

- `0x180008acc`
- `0x18002769c`
- `0x180027ee4`
- `0x180036250`
- `0x18003c5e4`
- `0x18003c898`
- `0x180052980`
- `0x1800542a8`
- `0x18007abd0`
- `0x1800b5e48`
- `0x1800ffe5c`
- `0x1801057fc`
- `0x180105850`
- `0x1801383c0`
- `0x18013d330`
- `0x18031ec90`
- `0x18031ed38`
- `0x180324838`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18013859b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18013859b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801384b6`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1801384b6`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18013870d`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x18013870d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138a11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138a11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180138a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180138a2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180138a2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801387f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801387f6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013886d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013886d`

## string_xrefs

- `0x180138434`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x1801385c6`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x1801386d6`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x180138798`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x180138949`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`
- `0x1801389f6`: `ShellCommonDesktopBase\Internal\ShellCommonDesktopBase\Inc\tiles\ShellMRTHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ShellMRTHelper::MRTHelperBase::Resolve(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  HSTRING v7; // rdx
  HSTRING v8; // rdx
  bool HasFileUriScheme; // bl
  const WCHAR *v10; // r13
  int v11; // eax
  unsigned int v12; // ebx
  HRESULT v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rax
  wchar_t *v17; // rax
  signed int v18; // edi
  wchar_t *v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, GUID *, UINT32 *); // rbx
  int v23; // eax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, _QWORD, LPVOID *); // rbx
  LPVOID v28; // rdi
  __int64 (__fastcall *v29)(LPVOID, int *); // rbx
  HRESULT v30; // eax
  signed int v31; // eax
  unsigned __int16 **v32; // r8
  int v33; // eax
  void *v34; // rbx
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, _QWORD, void *, int *); // rdi
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD, __int64, int *); // rbx
  HRESULT v39; // eax
  wil::details::in1diag3 *v40; // rcx
  __int64 v41; // rdx
  LPVOID v42; // rdi
  __int64 (__fastcall *v43)(LPVOID, __int64, int *); // rbx
  LPVOID v44; // rdi
  __int64 (__fastcall *v45)(LPVOID, __int64, const WCHAR *, _QWORD); // rbx
  const WCHAR *v46; // r8
  HSTRING v47; // rdi
  __int64 v48; // rcx
  const WCHAR *v49; // rdx
  HSTRING v50; // rbx
  __int64 v51; // rcx
  __int64 v52; // rax
  int v53; // eax
  __int64 v54; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v56; // rax
  int *ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  int v61[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v62; // [rsp+40h] [rbp-C0h]
  __int64 v63; // [rsp+48h] [rbp-B8h]
  UINT32 length[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v65; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR ppszPathOut; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v67; // [rsp+68h] [rbp-98h]
  __int64 v68; // [rsp+70h] [rbp-90h]
  _BYTE v69[24]; // [rsp+80h] [rbp-80h] BYREF
  ShellMRTHelper::Common *v70; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER v72; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v65 = a3;
  *a4 = 0;
  *(_QWORD *)v61 = 0;
  v62 = 0;
  v63 = 0;
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v69, &v65);
  HasFileUriScheme = ShellMRTHelper::Common::HasFileUriScheme(v70, v7);
  v10 = &pszDefault;
  if ( HasFileUriScheme || ShellMRTHelper::Common::HasMsAppDataUriScheme(v70, v8) )
  {
    pv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
    v39 = CoCreateInstance(
            &GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169,
            0,
            1u,
            &GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7,
            &pv);
    v18 = v39;
    v40 = retaddr;
    if ( v39 >= 0 )
    {
      if ( HasFileUriScheme )
      {
        v42 = pv;
        v43 = *(__int64 (__fastcall **)(LPVOID, __int64, int *))(*(_QWORD *)pv + 56LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v61);
        v62 = -1;
        v63 = -1;
        v39 = v43(v42, a3, v61);
        v18 = v39;
        v40 = retaddr;
        if ( v39 >= 0 )
        {
LABEL_58:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
          goto LABEL_59;
        }
        v41 = 285;
      }
      else
      {
        if ( !*(_BYTE *)(a1 + 45) )
        {
          v18 = -2147024809;
          goto LABEL_58;
        }
        v44 = pv;
        v45 = *(__int64 (__fastcall **)(LPVOID, __int64, const WCHAR *, _QWORD))(*(_QWORD *)pv + 48LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v61);
        v62 = -1;
        v63 = -1;
        v46 = &pszDefault;
        if ( *(_QWORD *)(a1 + 48) )
          v46 = *(const WCHAR **)(a1 + 48);
        ppv = v61;
        v39 = v45(v44, a3, v46, 0);
        v18 = v39;
        v40 = retaddr;
        if ( v39 >= 0 )
          goto LABEL_58;
        v41 = 291;
      }
    }
    else
    {
      v41 = 281;
    }
    wil::details::in1diag3::_Log_Hr(
      v40,
      (void *)v41,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
      (const char *)(unsigned int)v39,
      (int)ppv);
    goto LABEL_58;
  }
  v11 = ShellMRTHelper::MRTHelperBase::InitializeMRTObjects((ShellMRTHelper::MRTHelperBase *)a1);
  v12 = v11;
  if ( *(_BYTE *)(a1 + 46) && ((unsigned int)(v11 + 2147024894) <= 1 || v11 == -2147023728) )
  {
    ppszPathOut = 0;
    v67 = 0;
    v68 = 0;
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(
      &ppszPathOut,
      2147943568LL);
    v67 = -1;
    v68 = -1;
    v13 = PathAllocCombine(*(PCWSTR *)(a1 + 72), (PCWSTR)a3, 0, &ppszPathOut);
    v12 = v13;
    if ( v13 >= 0 )
    {
      v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v61,
              ppszPathOut,
              -1);
      v12 = v15;
      if ( v15 >= 0 )
      {
        v16 = *(_QWORD *)v61;
        *(_QWORD *)v61 = 0;
        v63 = 0;
        v62 = 0;
        *a4 = v16;
        v12 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13A,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v15,
          (int)ppv);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
        (const char *)(unsigned int)v13,
        (int)ppv);
    }
    Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(&ppszPathOut, v14);
    goto LABEL_71;
  }
  if ( v11 >= 0 )
  {
    if ( *(_WORD *)a3 == 64 )
    {
      if ( *(_WORD *)(a3 + 2) == 123 )
      {
        v17 = wcschr((const wchar_t *)a3, 0x3Fu);
        v18 = v17 == 0 ? 0x8000FFFF : 0;
        if ( v17 )
        {
          v19 = v17 + 1;
          v20 = -1;
          do
            ++v20;
          while ( v19[v20] );
          v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  v61,
                  v19,
                  v20 - 1);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x14A,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
            (const char *)(unsigned int)v18,
            (int)ppv);
        }
        *(_QWORD *)length = 0;
        pv = 0;
        if ( v18 < 0 )
          goto LABEL_32;
        v21 = *(_QWORD *)(a1 + 8);
        v22 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, UINT32 *))(*(_QWORD *)v21 + 88LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
        v23 = v22(v21, *(_QWORD *)v61, &GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2, length);
        v18 = v23;
        v24 = retaddr;
        if ( v23 >= 0 )
        {
          v26 = *(_QWORD *)length;
          v27 = *(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(**(_QWORD **)length + 56LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
          v23 = v27(v26, *(_QWORD *)(a1 + 16), &pv);
          v18 = v23;
          v24 = retaddr;
          if ( v23 >= 0 )
          {
            v28 = pv;
            v29 = *(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)pv + 32LL);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v61);
            v62 = -1;
            v63 = -1;
            v23 = v29(v28, v61);
            v18 = v23;
            v24 = retaddr;
            if ( v23 >= 0 )
            {
LABEL_32:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
              goto LABEL_59;
            }
            v25 = 357;
          }
          else
          {
            v25 = 346;
          }
        }
        else
        {
          v25 = 341;
        }
        wil::details::in1diag3::_Log_Hr(
          v24,
          (void *)v25,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v23,
          (int)ppv);
        goto LABEL_32;
      }
      v30 = SHLoadIndirectString((PCWSTR)a3, pszOutBuf, 0x104u, 0);
      if ( v30 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x172,
          (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
          (const char *)(unsigned int)v30,
          (int)ppv);
LABEL_60:
        pv = 0;
        WindowsDeleteString(0);
        pv = 0;
        v47 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&ppszPathOut, &v65) + 24);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(a1 + 48);
        v49 = &pszDefault;
        if ( *(_QWORD *)v48 )
          v49 = *(const WCHAR **)v48;
        v50 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                             &hstringHeader,
                             v49,
                             *(_DWORD *)(v48 + 8))
                         + 24);
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(a1 + 72);
        if ( *(_QWORD *)v51 )
          v10 = *(const WCHAR **)v51;
        v52 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v72, v10, *(_DWORD *)(v51 + 8));
        v53 = ShellMRTHelper::Common::TryFallbackToFilePath(
                *(ShellMRTHelper::Common **)(v52 + 24),
                v50,
                v47,
                (HSTRING)&pv,
                (HSTRING *)ppv);
        v12 = v53;
        if ( v53 < 0 )
        {
          v54 = 457;
LABEL_66:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v54,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
            (const char *)(unsigned int)v53,
            ppva);
          WindowsDeleteString((HSTRING)pv);
          pv = 0;
          goto LABEL_71;
        }
        length[0] = 0;
        StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)pv, length);
        v53 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v61,
                StringRawBuffer,
                length[0]);
        v12 = v53;
        if ( v53 < 0 )
        {
          v54 = 461;
          goto LABEL_66;
        }
        WindowsDeleteString((HSTRING)pv);
LABEL_70:
        v56 = *(_QWORD *)v61;
        *(_QWORD *)v61 = 0;
        v63 = 0;
        v62 = 0;
        *a4 = v56;
        v12 = 0;
        goto LABEL_71;
      }
      v31 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v61,
              pszOutBuf,
              -1);
    }
    else
    {
      if ( *(_BYTE *)(a1 + 45) && ShellMRTHelper::Common::HasMsAppXUriScheme(v70, (HSTRING)0x80070490LL) )
      {
        pv = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0);
        v33 = ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(v70, (HSTRING)&pv, v32);
        v18 = v33;
        v34 = pv;
        if ( v33 >= 0 )
        {
          v35 = *(_QWORD *)(a1 + 8);
          v36 = *(__int64 (__fastcall **)(__int64, _QWORD, void *, int *))(*(_QWORD *)v35 + 64LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v61);
          v62 = -1;
          v63 = -1;
          v18 = v36(v35, *(_QWORD *)(a1 + 16), v34, v61);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x19B,
            (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
            (const char *)(unsigned int)v33,
            (int)ppv);
        }
        if ( v34 )
          CoTaskMemFree(v34);
LABEL_59:
        if ( v18 >= 0 )
          goto LABEL_70;
        goto LABEL_60;
      }
      v37 = *(_QWORD *)(a1 + 8);
      v38 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *))(*(_QWORD *)v37 + 64LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v61);
      v62 = -1;
      v63 = -1;
      v31 = v38(v37, *(_QWORD *)(a1 + 16), a3, v61);
    }
    v18 = v31;
    goto LABEL_59;
  }
  if ( v11 != -2147024891 && (unsigned int)(v11 + 2147024894) > 1 && v11 != -2147023728 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"ShellCommonDesktopBase\\Internal\\ShellCommonDesktopBase\\Inc\\tiles\\ShellMRTHelper.h",
      (const char *)(unsigned int)v11,
      (int)ppv);
LABEL_71:
  v70 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v61);
  return v12;
}

```

## disassembly

```asm
0x1801383c0  mov     [rsp-8+arg_8], rbx
0x1801383c5  push    rbp
0x1801383c6  push    rsi
0x1801383c7  push    rdi
0x1801383c8  push    r12
0x1801383ca  push    r13
0x1801383cc  push    r14
0x1801383ce  push    r15
0x1801383d0  lea     rbp, [rsp-200h]
0x1801383d8  sub     rsp, 300h
0x1801383df  mov     rax, cs:__security_cookie
0x1801383e6  xor     rax, rsp
0x1801383e9  mov     [rbp+230h+var_40], rax
0x1801383f0  mov     r12, r9
0x1801383f3  mov     rsi, r8
0x1801383f6  mov     r15, rcx
0x1801383f9  mov     [rsp+330h+var_2D8], r8
0x1801383fe  xor     r14d, r14d
0x180138401  mov     [r9], r14
0x180138404  mov     qword ptr [rsp+330h+var_2F8], r14
0x180138409  mov     [rsp+330h+var_2F0], r14
0x18013840e  mov     [rsp+330h+var_2E8], r14
0x180138413  lea     rdx, [rsp+330h+var_2D8]
0x180138418  lea     rcx, [rbp+230h+var_2B0]
0x18013841c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180138421  nop
0x180138422  mov     rcx, [rbp+230h+var_298]; this
0x180138426  call    ?HasFileUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasFileUriScheme(HSTRING__ *)
0x18013842b  mov     bl, al
0x18013842d  lea     r13, pszDefault
0x180138434  lea     rdi, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18013843b  test    al, al
0x18013843d  jnz     loc_180138840
0x180138443  mov     rcx, [rbp+230h+var_298]; this
0x180138447  call    ?HasMsAppDataUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppDataUriScheme(HSTRING__ *)
0x18013844c  test    al, al
0x18013844e  jnz     loc_180138840
0x180138454  mov     rcx, r15; this
0x180138457  call    ?InitializeMRTObjects@MRTHelperBase@ShellMRTHelper@@AEAAJXZ; ShellMRTHelper::MRTHelperBase::InitializeMRTObjects(void)
0x18013845c  mov     ebx, eax
0x18013845e  mov     edx, 80070490h; HSTRING
0x180138463  cmp     [r15+2Eh], r14b
0x180138467  jz      loc_18013853C
0x18013846d  lea     ecx, [rax+7FF8FFFEh]
0x180138473  cmp     ecx, 1
0x180138476  jbe     short loc_180138480
0x180138478  cmp     eax, edx
0x18013847a  jnz     loc_18013853C
0x180138480  mov     [rsp+330h+ppszPathOut], r14
0x180138485  mov     [rsp+330h+var_2C8], r14
0x18013848a  mov     [rsp+330h+var_2C0], r14
0x18013848f  lea     rcx, [rsp+330h+ppszPathOut]
0x180138494  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180138499  or      r14, 0FFFFFFFFFFFFFFFFh
0x18013849d  mov     [rsp+330h+var_2C8], r14
0x1801384a2  mov     [rsp+330h+var_2C0], r14
0x1801384a7  lea     r9, [rsp+330h+ppszPathOut]; ppszPathOut
0x1801384ac  xor     r8d, r8d; dwFlags
0x1801384af  mov     rdx, rsi; pszMore
0x1801384b2  mov     rcx, [r15+48h]; pszPathIn
0x1801384b6  call    cs:__imp_PathAllocCombine
0x1801384bc  mov     ebx, eax
0x1801384be  test    eax, eax
0x1801384c0  jns     short loc_1801384DE
0x1801384c2  mov     rcx, [rbp+238h]; this
0x1801384c9  mov     r9d, eax; char *
0x1801384cc  mov     r8, rdi; unsigned int
0x1801384cf  mov     edx, 139h; void *
0x1801384d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801384d9  xor     r14d, r14d
0x1801384dc  jmp     short loc_18013852D
0x1801384de  mov     r8, r14
0x1801384e1  mov     rdx, [rsp+330h+ppszPathOut]
0x1801384e6  lea     rcx, [rsp+330h+var_2F8]
0x1801384eb  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801384f0  mov     ebx, eax
0x1801384f2  xor     r14d, r14d
0x1801384f5  test    eax, eax
0x1801384f7  jns     short loc_180138512
0x1801384f9  mov     rcx, [rbp+238h]; this
0x180138500  mov     r9d, eax; char *
0x180138503  mov     r8, rdi; unsigned int
0x180138506  mov     edx, 13Ah; void *
0x18013850b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138510  jmp     short loc_18013852D
0x180138512  mov     rax, qword ptr [rsp+330h+var_2F8]
0x180138517  mov     qword ptr [rsp+330h+var_2F8], r14
0x18013851c  mov     [rsp+330h+var_2E8], r14
0x180138521  mov     [rsp+330h+var_2F0], r14
0x180138526  mov     [r12], rax
0x18013852a  mov     ebx, r14d
0x18013852d  lea     rcx, [rsp+330h+ppszPathOut]
0x180138532  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180138537  jmp     loc_180138A78
0x18013853c  test    ebx, ebx
0x18013853e  jns     short loc_18013857E
0x180138540  cmp     ebx, 80070005h
0x180138546  jz      loc_180138A78
0x18013854c  add     eax, 7FF8FFFEh
0x180138551  cmp     eax, 1
0x180138554  jbe     loc_180138A78
0x18013855a  cmp     ebx, edx
0x18013855c  jz      loc_180138A78
0x180138562  mov     rcx, [rbp+238h]; this
0x180138569  mov     r9d, ebx; char *
0x18013856c  mov     r8, rdi; unsigned int
0x18013856f  mov     edx, 140h; void *
0x180138574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138579  jmp     loc_180138A78
0x18013857e  cmp     word ptr [rsi], 40h ; '@'
0x180138582  jnz     loc_180138749
0x180138588  mov     rcx, rsi; pszSource
0x18013858b  cmp     word ptr [rsi+2], 7Bh ; '{'
0x180138590  jnz     loc_180138700
0x180138596  mov     edx, 3Fh ; '?'; Ch
0x18013859b  call    cs:__imp_wcschr
0x1801385a1  mov     rcx, rax
0x1801385a4  neg     rcx
0x1801385a7  sbb     edi, edi
0x1801385a9  not     edi
0x1801385ab  and     edi, 8000FFFFh
0x1801385b1  mov     rcx, [rbp+238h]; this
0x1801385b8  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801385bc  xor     esi, esi
0x1801385be  test    rax, rax
0x1801385c1  jnz     short loc_1801385D9
0x1801385c3  mov     r9d, edi; char *
0x1801385c6  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1801385cd  mov     edx, 14Ah; void *
0x1801385d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801385d7  jmp     short loc_1801385F9
0x1801385d9  lea     rdx, [rax+2]
0x1801385dd  mov     r8, r14
0x1801385e0  inc     r8
0x1801385e3  cmp     [rdx+r8*2], si
0x1801385e8  jnz     short loc_1801385E0
0x1801385ea  dec     r8
0x1801385ed  lea     rcx, [rsp+330h+var_2F8]
0x1801385f2  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1801385f7  mov     edi, eax
0x1801385f9  mov     qword ptr [rsp+330h+length], rsi
0x1801385fe  mov     [rsp+330h+pv], rsi
0x180138603  test    edi, edi
0x180138605  js      loc_1801386E3
0x18013860b  mov     rdi, [r15+8]
0x18013860f  mov     rax, [rdi]
0x180138612  mov     rbx, [rax+58h]
0x180138616  lea     rcx, [rsp+330h+length]
0x18013861b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180138620  lea     r9, [rsp+330h+length]
0x180138625  lea     r8, _GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2
0x18013862c  mov     rdx, qword ptr [rsp+330h+var_2F8]
0x180138631  mov     rcx, rdi
0x180138634  mov     rax, rbx
0x180138637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013863c  mov     edi, eax
0x18013863e  mov     rcx, [rbp+238h]
0x180138645  test    eax, eax
0x180138647  jns     short loc_180138653
0x180138649  mov     edx, 155h
0x18013864e  jmp     loc_1801386D3
0x180138653  mov     rdi, qword ptr [rsp+330h+length]
0x180138658  mov     rax, [rdi]
0x18013865b  mov     rbx, [rax+38h]
0x18013865f  lea     rcx, [rsp+330h+pv]
0x180138664  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180138669  lea     r8, [rsp+330h+pv]
0x18013866e  mov     rdx, [r15+10h]
0x180138672  mov     rcx, rdi
0x180138675  mov     rax, rbx
0x180138678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013867d  mov     edi, eax
0x18013867f  mov     rcx, [rbp+238h]
0x180138686  test    eax, eax
0x180138688  jns     short loc_180138691
0x18013868a  mov     edx, 15Ah
0x18013868f  jmp     short loc_1801386D3
0x180138691  mov     rdi, [rsp+330h+pv]
0x180138696  mov     rax, [rdi]
0x180138699  mov     rbx, [rax+20h]
0x18013869d  lea     rcx, [rsp+330h+var_2F8]
0x1801386a2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801386a7  mov     [rsp+330h+var_2F0], r14
0x1801386ac  mov     [rsp+330h+var_2E8], r14
0x1801386b1  lea     rdx, [rsp+330h+var_2F8]
0x1801386b6  mov     rcx, rdi
0x1801386b9  mov     rax, rbx
0x1801386bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801386c1  mov     edi, eax
0x1801386c3  mov     rcx, [rbp+238h]; this
0x1801386ca  test    eax, eax
0x1801386cc  jns     short loc_1801386E3
0x1801386ce  mov     edx, 165h; void *
0x1801386d3  mov     r9d, eax; char *
0x1801386d6  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x1801386dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801386e2  nop
0x1801386e3  lea     rcx, [rsp+330h+pv]
0x1801386e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801386ed  nop
0x1801386ee  lea     rcx, [rsp+330h+length]
0x1801386f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801386f8  xor     r14d, r14d
0x1801386fb  jmp     loc_180138966
0x180138700  xor     r9d, r9d; ppvReserved
0x180138703  mov     r8d, 104h; cchOutBuf
0x180138709  lea     rdx, [rbp+230h+pszOutBuf]; pszOutBuf
0x18013870d  call    cs:__imp_SHLoadIndirectString
0x180138713  mov     rcx, [rbp+238h]; this
0x18013871a  test    eax, eax
0x18013871c  jns     short loc_180138733
0x18013871e  mov     r9d, eax; char *
0x180138721  mov     r8, rdi; unsigned int
0x180138724  mov     edx, 172h; void *
0x180138729  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18013872e  jmp     loc_18013896E
0x180138733  or      r8, 0FFFFFFFFFFFFFFFFh
0x180138737  lea     rdx, [rbp+230h+pszOutBuf]
0x18013873b  lea     rcx, [rsp+330h+var_2F8]
0x180138740  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180138745  mov     edi, eax
0x180138747  jmp     short loc_1801386F8
0x180138749  cmp     [r15+2Dh], r14b
0x18013874d  jz      loc_180138801
0x180138753  mov     rcx, [rbp+230h+var_298]; this
0x180138757  call    ?HasMsAppXUriScheme@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::HasMsAppXUriScheme(HSTRING__ *)
0x18013875c  test    al, al
0x18013875e  jz      loc_180138801
0x180138764  mov     [rsp+330h+pv], r14
0x180138769  xor     edx, edx
0x18013876b  lea     rcx, [rsp+330h+pv]
0x180138770  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180138775  lea     rdx, [rsp+330h+pv]; HSTRING
0x18013877a  mov     rcx, [rbp+230h+var_298]; this
0x18013877e  call    ?ConvertMsAppXUriToMsResourceUri@Common@ShellMRTHelper@@YAJPEAUHSTRING__@@PEAPEAG@Z; ShellMRTHelper::Common::ConvertMsAppXUriToMsResourceUri(HSTRING__ *,ushort * *)
0x180138783  mov     edi, eax
0x180138785  mov     rcx, [rbp+238h]; this
0x18013878c  mov     rbx, [rsp+330h+pv]
0x180138791  test    eax, eax
0x180138793  jns     short loc_1801387AB
0x180138795  mov     r9d, eax; char *
0x180138798  lea     r8, aShellcommondes_0; "ShellCommonDesktopBase\\Internal\\Shell"...
0x18013879f  mov     edx, 19Bh; void *
0x1801387a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801387a9  jmp     short loc_1801387EA
0x1801387ab  mov     rsi, [r15+8]
0x1801387af  mov     rax, [rsi]
0x1801387b2  mov     rdi, [rax+40h]
0x1801387b6  lea     rcx, [rsp+330h+var_2F8]
0x1801387bb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801387c0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801387c4  mov     [rsp+330h+var_2F0], r14
0x1801387c9  mov     [rsp+330h+var_2E8], r14
0x1801387ce  lea     r9, [rsp+330h+var_2F8]
0x1801387d3  mov     r8, rbx
0x1801387d6  mov     rdx, [r15+10h]
0x1801387da  mov     rcx, rsi
0x1801387dd  mov     rax, rdi
0x1801387e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801387e5  mov     edi, eax
0x1801387e7  xor     r14d, r14d
0x1801387ea  test    rbx, rbx
0x1801387ed  jz      loc_180138966
0x1801387f3  mov     rcx, rbx; pv
0x1801387f6  call    cs:__imp_CoTaskMemFree
0x1801387fc  jmp     loc_180138966
0x180138801  mov     rdi, [r15+8]
0x180138805  mov     rax, [rdi]
0x180138808  mov     rbx, [rax+40h]
0x18013880c  lea     rcx, [rsp+330h+var_2F8]
0x180138811  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180138816  or      r14, 0FFFFFFFFFFFFFFFFh
0x18013881a  mov     [rsp+330h+var_2F0], r14
0x18013881f  mov     [rsp+330h+var_2E8], r14
0x180138824  lea     r9, [rsp+330h+var_2F8]
0x180138829  mov     r8, rsi
0x18013882c  mov     rdx, [r15+10h]
0x180138830  mov     rcx, rdi
0x180138833  mov     rax, rbx
0x180138836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013883b  jmp     loc_180138745
0x180138840  mov     [rsp+330h+pv], r14
0x180138845  lea     rcx, [rsp+330h+pv]
0x18013884a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013884f  lea     rax, [rsp+330h+pv]
0x180138854  mov     [rsp+330h+ppv], rax; int
0x180138859  lea     r9, _GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7; riid
0x180138860  xor     edx, edx; pUnkOuter
0x180138862  lea     r8d, [rdx+1]; dwClsContext
0x180138866  lea     rcx, _GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169; rclsid
0x18013886d  call    cs:__imp_CoCreateInstance
0x180138873  mov     edi, eax
0x180138875  mov     rcx, [rbp+238h]
0x18013887c  test    eax, eax
0x18013887e  jns     short loc_18013888A
0x180138880  mov     edx, 119h
0x180138885  jmp     loc_180138946
0x18013888a  test    bl, bl
0x18013888c  jz      short loc_1801388E0
0x18013888e  mov     rdi, [rsp+330h+pv]
  ... truncated ...
```
