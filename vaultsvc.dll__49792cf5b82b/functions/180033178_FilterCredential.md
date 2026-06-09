# _FilterCredential

- ea: `0x180033178`
- end: `0x18003370f`
- name: `_FilterCredential`
- size: `1431`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001cecc`
- `0x180020030`

## callees

- `0x180003140`
- `0x18001cea8`
- `0x180033178`
- `0x180033718`
- `0x180038c6c`
- `0x180038d64`
- `0x18003a580`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003347e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003347e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033652`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033342`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033499`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003366d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033342`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033499`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003366d`

## string_xrefs

- `0x180033271`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x1800332db`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x1800333c7`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x18003342f`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x180033519`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x180033587`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`
- `0x1800335f9`: `onecore\ds\security\vault\vaultserver\vaultcds.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall FilterCredential(
        struct _GUID *a1,
        const unsigned __int16 *a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64 **))
{
  __int64 (__fastcall **v4)(_QWORD, GUID *, __int64 **); // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rax
  int v9; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 (__fastcall **v11)(_QWORD, GUID *, __int64 **); // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  const WCHAR *v15; // rax
  __int64 (__fastcall **v16)(_QWORD, GUID *, __int64 **); // rax
  int v17; // eax
  __int64 (__fastcall **v18)(HSTRING, GUID *, __int64 **); // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  const WCHAR *v22; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-69h]
  __int64 *v24; // [rsp+40h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v26; // [rsp+50h] [rbp-39h] BYREF
  __int64 v27; // [rsp+58h] [rbp-31h] BYREF
  LPCWCH v28; // [rsp+60h] [rbp-29h] BYREF
  int v29; // [rsp+68h] [rbp-21h]
  __int64 v30; // [rsp+70h] [rbp-19h] BYREF
  LPCWCH v31; // [rsp+78h] [rbp-11h] BYREF
  int v32; // [rsp+80h] [rbp-9h]
  __int64 v33; // [rsp+88h] [rbp-1h] BYREF
  LPCWCH lpString2; // [rsp+90h] [rbp+7h] BYREF
  int v35; // [rsp+98h] [rbp+Fh]
  struct _GUID Buf1; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  lpString2 = 0;
  v35 = 0;
  v33 = 0;
  v31 = 0;
  v32 = 0;
  v30 = 0;
  v28 = 0;
  v29 = 0;
  v27 = 0;
  Buf1 = 0;
  if ( VaultGetSettingUnitInfo(
         (struct IVaultAllocator *)VaultGlobals::g_HeapAlloc,
         a2,
         (unsigned __int16 **)&lpString2,
         (unsigned __int16 **)&v31,
         (unsigned __int16 **)&v28,
         &Buf1,
         a1) )
  {
    goto LABEL_31;
  }
  if ( memcmp_0(&Buf1, qword_180052390, 0x10u) )
  {
    if ( lpString2 )
    {
      v4 = *a3;
      v24 = 0;
      v5 = (*v4)(a3, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v24);
      v6 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
          (const char *)(unsigned int)v5,
          bIgnoreCase);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
        return v6;
      }
      string = 0;
      v8 = *v24;
      string = 0;
      v9 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v8 + 48))(v24, &string);
      v6 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
          (const char *)(unsigned int)v9,
          bIgnoreCase);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
        return v6;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, lpString2, -1, 1) != 2 )
        goto LABEL_11;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
    }
    if ( v31 )
    {
      v11 = *a3;
      v24 = 0;
      v12 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **), __int64 **))v11[6])(a3, &v24);
      v6 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBF,
          (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
          (const char *)(unsigned int)v12,
          bIgnoreCase);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
        return v6;
      }
      string = 0;
      v13 = *v24;
      string = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v13 + 48))(v24, &string);
      v6 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
          (const char *)(unsigned int)v14,
          bIgnoreCase);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
        return v6;
      }
      v15 = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(v15, -1, v31, -1, 1) != 2 )
      {
LABEL_11:
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
        return 2147500037LL;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
    }
    if ( v28 )
    {
      v16 = *a3;
      string = 0;
      v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **), HSTRING *))v16[6])(
              a3,
              &string);
      v6 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
          (const char *)(unsigned int)v17,
          bIgnoreCase);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&string);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
        return v6;
      }
      v24 = 0;
      v18 = *(__int64 (__fastcall ***)(HSTRING, GUID *, __int64 **))string;
      v24 = 0;
      v19 = (*v18)(string, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v24);
      v6 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD0,
          (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
          (const char *)(unsigned int)v19,
          bIgnoreCase);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&string);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
        return v6;
      }
      v26 = 0;
      v20 = *v24;
      v26 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v20 + 56))(v24, &v26);
      v6 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\ds\\security\\vault\\vaultserver\\vaultcds.cpp",
          (const char *)(unsigned int)v21,
          bIgnoreCase);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v26);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&string);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
        return v6;
      }
      v22 = WindowsGetStringRawBuffer(v26, 0);
      if ( CompareStringOrdinal(v22, -1, v28, -1, 1) != 2 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v26);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
        wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&string);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
        return 2147500037LL;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v26);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&v24);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(&string);
    }
LABEL_31:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
    return 0;
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v30);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v33);
  return 0;
}

```

## disassembly

```asm
0x180033178  push    rbp
0x18003317a  push    rbx
0x18003317b  push    rsi
0x18003317c  push    r14
0x18003317e  push    r15
0x180033180  lea     rbp, [rsp-37h]
0x180033185  sub     rsp, 0C0h
0x18003318c  mov     rax, cs:__security_cookie
0x180033193  xor     rax, rsp
0x180033196  mov     [rbp+57h+var_30], rax
0x18003319a  mov     rsi, r8
0x18003319d  xor     r14d, r14d
0x1800331a0  mov     [rbp+57h+lpString2], r14
0x1800331a4  mov     [rbp+57h+var_48], r14d
0x1800331a8  mov     [rbp+57h+var_58], r14
0x1800331ac  mov     [rbp+57h+var_68], r14
0x1800331b0  mov     [rbp+57h+var_60], r14d
0x1800331b4  mov     [rbp+57h+var_70], r14
0x1800331b8  mov     [rbp+57h+var_80], r14
0x1800331bc  mov     [rbp+57h+var_78], r14d
0x1800331c0  mov     [rbp+57h+var_88], r14
0x1800331c4  xorps   xmm0, xmm0
0x1800331c7  movups  [rbp+57h+Buf1], xmm0
0x1800331cb  mov     [rsp+0E0h+var_B0], rcx; struct _GUID *
0x1800331d0  lea     rax, [rbp+57h+Buf1]
0x1800331d4  mov     [rsp+0E0h+var_B8], rax; struct _GUID *
0x1800331d9  lea     rax, [rbp+57h+var_80]
0x1800331dd  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax; int
0x1800331e2  lea     r9, [rbp+57h+var_68]; unsigned __int16 **
0x1800331e6  lea     r8, [rbp+57h+lpString2]; unsigned __int16 **
0x1800331ea  lea     rcx, ?g_HeapAlloc@VaultGlobals@@3VCVaultHeapAllocator@@A; struct IVaultAllocator *
0x1800331f1  call    ?VaultGetSettingUnitInfo@@YAKPEAUIVaultAllocator@@PEBGPEAPEAG22PEAU_GUID@@PEBU2@@Z; VaultGetSettingUnitInfo(IVaultAllocator *,ushort const *,ushort * *,ushort * *,ushort * *,_GUID *,_GUID const *)
0x1800331f6  test    eax, eax
0x1800331f8  jnz     loc_1800336D4
0x1800331fe  lea     r8d, [r14+10h]; Size
0x180033202  lea     rdx, qword_180052390; Buf2
0x180033209  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18003320d  call    memcmp_0
0x180033212  test    eax, eax
0x180033214  jnz     short loc_180033239
0x180033216  lea     rcx, [rbp+57h+var_88]
0x18003321a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003321f  nop
0x180033220  lea     rcx, [rbp+57h+var_70]
0x180033224  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033229  nop
0x18003322a  lea     rcx, [rbp+57h+var_58]
0x18003322e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033233  nop
0x180033234  jmp     loc_1800336F2
0x180033239  or      r15d, 0FFFFFFFFh
0x18003323d  cmp     [rbp+57h+lpString2], r14
0x180033241  jz      loc_180033399
0x180033247  mov     rax, [rsi]
0x18003324a  mov     [rbp+57h+var_A0], r14
0x18003324e  lea     r8, [rbp+57h+var_A0]
0x180033252  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x180033259  mov     rcx, rsi
0x18003325c  mov     rax, [rax]
0x18003325f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033264  mov     ebx, eax
0x180033266  test    eax, eax
0x180033268  jns     short loc_1800332B2
0x18003326a  mov     rcx, [rbp+5Fh]; this
0x18003326e  mov     r9d, eax; char *
0x180033271  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x180033278  mov     edx, 0B1h; void *
0x18003327d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033282  nop
0x180033283  lea     rcx, [rbp+57h+var_A0]
0x180033287  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x18003328c  nop
0x18003328d  lea     rcx, [rbp+57h+var_88]
0x180033291  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033296  nop
0x180033297  lea     rcx, [rbp+57h+var_70]
0x18003329b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800332a0  nop
0x1800332a1  lea     rcx, [rbp+57h+var_58]
0x1800332a5  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800332aa  nop
0x1800332ab  mov     eax, ebx
0x1800332ad  jmp     loc_1800336F4
0x1800332b2  mov     [rbp+57h+string], r14
0x1800332b6  mov     rcx, [rbp+57h+var_A0]
0x1800332ba  mov     rax, [rcx]
0x1800332bd  mov     [rbp+57h+string], r14
0x1800332c1  lea     rdx, [rbp+57h+string]
0x1800332c5  mov     rax, [rax+30h]
0x1800332c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800332ce  mov     ebx, eax
0x1800332d0  test    eax, eax
0x1800332d2  jns     short loc_180033321
0x1800332d4  mov     rcx, [rbp+5Fh]; this
0x1800332d8  mov     r9d, eax; char *
0x1800332db  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x1800332e2  mov     edx, 0B4h; void *
0x1800332e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800332ec  nop
0x1800332ed  lea     rcx, [rbp+57h+string]
0x1800332f1  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800332f6  nop
0x1800332f7  lea     rcx, [rbp+57h+var_A0]
0x1800332fb  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x180033300  nop
0x180033301  lea     rcx, [rbp+57h+var_88]
0x180033305  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003330a  nop
0x18003330b  lea     rcx, [rbp+57h+var_70]
0x18003330f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033314  nop
0x180033315  lea     rcx, [rbp+57h+var_58]
0x180033319  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003331e  nop
0x18003331f  jmp     short loc_1800332AB
0x180033321  xor     edx, edx; length
0x180033323  mov     rcx, [rbp+57h+string]; string
0x180033327  call    cs:__imp_WindowsGetStringRawBuffer
0x18003332d  mov     [rsp+0E0h+bIgnoreCase], 1; int
0x180033335  mov     r9d, r15d; cchCount2
0x180033338  mov     r8, [rbp+57h+lpString2]; lpString2
0x18003333c  mov     edx, r15d; cchCount1
0x18003333f  mov     rcx, rax; lpString1
0x180033342  call    cs:__imp_CompareStringOrdinal
0x180033348  nop
0x180033349  lea     rcx, [rbp+57h+string]
0x18003334d  cmp     eax, 2
0x180033350  jz      short loc_18003338A
0x180033352  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180033357  nop
0x180033358  lea     rcx, [rbp+57h+var_A0]
0x18003335c  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x180033361  nop
0x180033362  lea     rcx, [rbp+57h+var_88]
0x180033366  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003336b  nop
0x18003336c  lea     rcx, [rbp+57h+var_70]
0x180033370  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033375  nop
0x180033376  lea     rcx, [rbp+57h+var_58]
0x18003337a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003337f  nop
0x180033380  mov     eax, 80004005h
0x180033385  jmp     loc_1800336F4
0x18003338a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18003338f  nop
0x180033390  lea     rcx, [rbp+57h+var_A0]
0x180033394  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x180033399  cmp     [rbp+57h+var_68], r14
0x18003339d  jz      loc_1800334EB
0x1800333a3  mov     rax, [rsi]
0x1800333a6  mov     [rbp+57h+var_A0], r14
0x1800333aa  lea     rdx, [rbp+57h+var_A0]
0x1800333ae  mov     rcx, rsi
0x1800333b1  mov     rax, [rax+30h]
0x1800333b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333ba  mov     ebx, eax
0x1800333bc  test    eax, eax
0x1800333be  jns     short loc_180033406
0x1800333c0  mov     rcx, [rbp+5Fh]; this
0x1800333c4  mov     r9d, eax; char *
0x1800333c7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x1800333ce  mov     edx, 0BFh; void *
0x1800333d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800333d8  nop
0x1800333d9  lea     rcx, [rbp+57h+var_A0]
0x1800333dd  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x1800333e2  nop
0x1800333e3  lea     rcx, [rbp+57h+var_88]
0x1800333e7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800333ec  nop
0x1800333ed  lea     rcx, [rbp+57h+var_70]
0x1800333f1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800333f6  nop
0x1800333f7  lea     rcx, [rbp+57h+var_58]
0x1800333fb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033400  nop
0x180033401  jmp     loc_1800332AB
0x180033406  mov     [rbp+57h+string], r14
0x18003340a  mov     rcx, [rbp+57h+var_A0]
0x18003340e  mov     rax, [rcx]
0x180033411  mov     [rbp+57h+string], r14
0x180033415  lea     rdx, [rbp+57h+string]
0x180033419  mov     rax, [rax+30h]
0x18003341d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033422  mov     ebx, eax
0x180033424  test    eax, eax
0x180033426  jns     short loc_180033478
0x180033428  mov     rcx, [rbp+5Fh]; this
0x18003342c  mov     r9d, eax; char *
0x18003342f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x180033436  mov     edx, 0C2h; void *
0x18003343b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033440  nop
0x180033441  lea     rcx, [rbp+57h+string]
0x180033445  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18003344a  nop
0x18003344b  lea     rcx, [rbp+57h+var_A0]
0x18003344f  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x180033454  nop
0x180033455  lea     rcx, [rbp+57h+var_88]
0x180033459  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003345e  nop
0x18003345f  lea     rcx, [rbp+57h+var_70]
0x180033463  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033468  nop
0x180033469  lea     rcx, [rbp+57h+var_58]
0x18003346d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033472  nop
0x180033473  jmp     loc_1800332AB
0x180033478  xor     edx, edx; length
0x18003347a  mov     rcx, [rbp+57h+string]; string
0x18003347e  call    cs:__imp_WindowsGetStringRawBuffer
0x180033484  mov     [rsp+0E0h+bIgnoreCase], 1; int
0x18003348c  mov     r9d, r15d; cchCount2
0x18003348f  mov     r8, [rbp+57h+var_68]; lpString2
0x180033493  mov     edx, r15d; cchCount1
0x180033496  mov     rcx, rax; lpString1
0x180033499  call    cs:__imp_CompareStringOrdinal
0x18003349f  nop
0x1800334a0  lea     rcx, [rbp+57h+string]
0x1800334a4  cmp     eax, 2
0x1800334a7  jz      short loc_1800334DC
0x1800334a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800334ae  nop
0x1800334af  lea     rcx, [rbp+57h+var_A0]
0x1800334b3  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x1800334b8  nop
0x1800334b9  lea     rcx, [rbp+57h+var_88]
0x1800334bd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800334c2  nop
0x1800334c3  lea     rcx, [rbp+57h+var_70]
0x1800334c7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800334cc  nop
0x1800334cd  lea     rcx, [rbp+57h+var_58]
0x1800334d1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800334d6  nop
0x1800334d7  jmp     loc_180033380
0x1800334dc  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1800334e1  nop
0x1800334e2  lea     rcx, [rbp+57h+var_A0]
0x1800334e6  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x1800334eb  cmp     [rbp+57h+var_80], r14
0x1800334ef  jz      loc_1800336D4
0x1800334f5  mov     rax, [rsi]
0x1800334f8  mov     [rbp+57h+string], r14
0x1800334fc  lea     rdx, [rbp+57h+string]
0x180033500  mov     rcx, rsi
0x180033503  mov     rax, [rax+30h]
0x180033507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003350c  mov     ebx, eax
0x18003350e  test    eax, eax
0x180033510  jns     short loc_180033558
0x180033512  mov     rcx, [rbp+5Fh]; this
0x180033516  mov     r9d, eax; char *
0x180033519  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x180033520  mov     edx, 0CDh; void *
0x180033525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003352a  nop
0x18003352b  lea     rcx, [rbp+57h+string]
0x18003352f  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x180033534  nop
0x180033535  lea     rcx, [rbp+57h+var_88]
0x180033539  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003353e  nop
0x18003353f  lea     rcx, [rbp+57h+var_70]
0x180033543  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033548  nop
0x180033549  lea     rcx, [rbp+57h+var_58]
0x18003354d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180033552  nop
0x180033553  jmp     loc_1800332AB
0x180033558  mov     [rbp+57h+var_A0], r14
0x18003355c  mov     rcx, [rbp+57h+string]
0x180033560  mov     rax, [rcx]
0x180033563  mov     [rbp+57h+var_A0], r14
0x180033567  lea     r8, [rbp+57h+var_A0]
0x18003356b  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x180033572  mov     rax, [rax]
0x180033575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003357a  mov     ebx, eax
0x18003357c  test    eax, eax
0x18003357e  jns     short loc_1800335D0
0x180033580  mov     rcx, [rbp+5Fh]; this
0x180033584  mov     r9d, eax; char *
0x180033587  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\vault\\vaultserv"...
0x18003358e  mov     edx, 0D0h; void *
0x180033593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033598  nop
0x180033599  lea     rcx, [rbp+57h+var_A0]
0x18003359d  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x1800335a2  nop
0x1800335a3  lea     rcx, [rbp+57h+string]
0x1800335a7  call    ??1?$com_ptr_t@UIWebAccountProvider3@Credentials@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccountProvider3,wil::err_returncode_policy>(void)
0x1800335ac  nop
0x1800335ad  lea     rcx, [rbp+57h+var_88]
0x1800335b1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800335b6  nop
0x1800335b7  lea     rcx, [rbp+57h+var_70]
0x1800335bb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
  ... truncated ...
```
