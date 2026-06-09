# CIASMigrationHelper::LoadXMLFromResources(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &,ushort const *,ushort const *)

- ea: `0x18004d900`
- end: `0x18004de97`
- name: `?LoadXMLFromResources@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEBG1@Z`
- size: `1431`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800477a4`
- `0x180047a60`

## callees

- `0x18002cd74`
- `0x18002d08c`
- `0x18002efa0`
- `0x18002f240`
- `0x18003e744`
- `0x1800403bc`
- `0x180042a80`
- `0x180047604`
- `0x180048a2c`
- `0x180048acc`
- `0x180048e7c`
- `0x1800491a0`
- `0x18004c55c`
- `0x18004d24c`
- `0x18004d370`
- `0x18004d3d0`
- `0x18004d434`
- `0x18004d900`
- `0x18004e16c`
- `0x180050044`
- `0x18005102c`
- `0x180051e00`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `KERNEL32!LoadResource` at `0x18004d9e2`
- `KERNEL32!LoadResource` at `0x18004d9e2`
- `KERNEL32!SizeofResource` at `0x18004d9be`
- `KERNEL32!SizeofResource` at `0x18004d9be`
- `KERNEL32!LoadLibraryExW` at `0x18004d956`
- `KERNEL32!LoadLibraryExW` at `0x18004d956`
- `KERNEL32!GetLastError` at `0x18004d964`
- `KERNEL32!GetLastError` at `0x18004d992`
- `KERNEL32!GetLastError` at `0x18004d9ed`
- `KERNEL32!GetLastError` at `0x18004d964`
- `KERNEL32!GetLastError` at `0x18004d992`
- `KERNEL32!GetLastError` at `0x18004d9ed`
- `KERNEL32!FreeLibrary` at `0x18004d9aa`
- `KERNEL32!FreeLibrary` at `0x18004d9ce`
- `KERNEL32!FreeLibrary` at `0x18004da05`
- `KERNEL32!FreeLibrary` at `0x18004da4e`
- `KERNEL32!FreeLibrary` at `0x18004d9aa`
- `KERNEL32!FreeLibrary` at `0x18004d9ce`
- `KERNEL32!FreeLibrary` at `0x18004da05`
- `KERNEL32!FreeLibrary` at `0x18004da4e`
- `KERNEL32!LockResource` at `0x18004da31`
- `KERNEL32!LockResource` at `0x18004da31`
- `KERNEL32!FindResourceW` at `0x18004d984`
- `KERNEL32!FindResourceW` at `0x18004d984`

## string_xrefs

- `0x18004dad3`: `CIASMigrationHelper::LoadXMLFromResources(), failed load xml from %S - %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=36 #try_helpers=1
signed int __fastcall CIASMigrationHelper::LoadXMLFromResources(LPVOID *a1, const WCHAR *a2, IUnknown *a3)
{
  __int64 v5; // rbx
  signed int result; // eax
  HMODULE Library; // rax
  HMODULE v8; // r14
  HRSRC ResourceW; // rax
  HRSRC v10; // r15
  signed int LastError; // eax
  unsigned int v12; // ebx
  DWORD v13; // edi
  HGLOBAL Resource; // rax
  signed int v15; // eax
  char *v16; // rdx
  __int64 *v17; // r14
  struct IUnknown *v18; // rax
  __int16 v19; // dx
  __int64 v20; // rdi
  const unsigned __int16 *v21; // rdx
  _bstr_t *v22; // rax
  __int64 v23; // rdx
  struct IUnknown *v24; // rax
  __int64 *v25; // rax
  _bstr_t *v26; // rdi
  _bstr_t *v27; // rax
  __int64 v28; // rdi
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdi
  _bstr_t *v32; // rax
  __int64 v33; // rdi
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdi
  _bstr_t *v37; // rax
  __int64 v38; // rdi
  struct IUnknown *v39; // rax
  _bstr_t *v40; // rax
  __int64 v41; // rdi
  _bstr_t *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 *v45; // [rsp+30h] [rbp-128h] BYREF
  __int64 v46; // [rsp+38h] [rbp-120h] BYREF
  __int64 v47; // [rsp+40h] [rbp-118h]
  _BYTE v48[8]; // [rsp+48h] [rbp-110h] BYREF
  _BYTE v49[8]; // [rsp+50h] [rbp-108h] BYREF
  _BYTE v50[8]; // [rsp+58h] [rbp-100h] BYREF
  _BYTE v51[8]; // [rsp+60h] [rbp-F8h] BYREF
  _BYTE v52[8]; // [rsp+68h] [rbp-F0h] BYREF
  _BYTE v53[8]; // [rsp+70h] [rbp-E8h] BYREF
  _BYTE v54[8]; // [rsp+78h] [rbp-E0h] BYREF
  _BYTE v55[8]; // [rsp+80h] [rbp-D8h] BYREF
  _BYTE v56[8]; // [rsp+88h] [rbp-D0h] BYREF
  _BYTE v57[8]; // [rsp+90h] [rbp-C8h] BYREF
  _BYTE v58[8]; // [rsp+98h] [rbp-C0h] BYREF
  _BYTE v59[8]; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v60[8]; // [rsp+A8h] [rbp-B0h] BYREF
  _BYTE v61[8]; // [rsp+B0h] [rbp-A8h] BYREF
  __int16 v62; // [rsp+B8h] [rbp-A0h] BYREF
  int v63; // [rsp+C0h] [rbp-98h]
  unsigned __int16 *v64[3]; // [rsp+F0h] [rbp-68h] BYREF
  unsigned __int64 v65; // [rsp+108h] [rbp-50h]

  v45 = (__int64 *)a1;
  v5 = 0;
  v46 = 0;
  result = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(
             a1,
             (__int64)a2,
             a3,
             0x17u);
  if ( result >= 0 )
  {
    Library = LoadLibraryExW(a2, 0, 0x22u);
    v8 = Library;
    if ( !Library )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    ResourceW = FindResourceW(Library, (LPCWSTR)a3, (LPCWSTR)0x17);
    v10 = ResourceW;
    if ( !ResourceW )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_8:
      FreeLibrary(v8);
      return v12;
    }
    v13 = SizeofResource(v8, ResourceW);
    if ( v13 <= 2 )
    {
      FreeLibrary(v8);
      return -2147024883;
    }
    Resource = LoadResource(v8, v10);
    if ( !Resource )
    {
      v15 = GetLastError();
      v12 = v15;
      if ( v15 > 0 )
        v12 = (unsigned __int16)v15 | 0x80070000;
      goto LABEL_8;
    }
    v65 = 7;
    v64[2] = 0;
    LOWORD(v64[0]) = 0;
    v16 = (char *)LockResource(Resource) + 2;
    std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::assign(
      v64,
      v16,
      (v13 >> 1) - 1);
    FreeLibrary(v8);
    v17 = v45;
    v18 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v45);
    MSXML2::IXMLDOMDocument::Putasync(v18, v19);
    v20 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v45);
    v21 = (const unsigned __int16 *)v64;
    if ( v65 >= 8 )
      v21 = v64[0];
    v22 = _bstr_t::_bstr_t((_bstr_t *)&v45, v21);
    if ( (unsigned __int16)MSXML2::IXMLDOMDocument::loadXML(v20, v22) == 0xFFFF )
    {
      LOBYTE(v23) = 1;
      std::wstring::_Tidy(v64, v23, 0);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("CIASMigrationHelper::LoadXMLFromResources(), failed load xml from %S - %S");
        WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
      }
      v24 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(v17);
      v25 = (__int64 *)MSXML2::IXMLDOMDocument::GetparseError(v24);
      if ( *v25 )
      {
        v5 = *v25;
        v46 = *v25;
        _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(&v46);
      }
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      v26 = _bstr_t::_bstr_t((_bstr_t *)v48, "\n=====================");
      v27 = _bstr_t::_bstr_t((_bstr_t *)v61, "\nReason: ");
      v28 = _bstr_t::operator+(v26, v60, v27);
      v29 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v46);
      v30 = MSXML2::IXMLDOMParseError::Getreason(v29, v59);
      v31 = _bstr_t::operator+(v28, v58, v30);
      v32 = _bstr_t::_bstr_t((_bstr_t *)v57, "\nSource: ");
      v33 = _bstr_t::operator+(v31, v56, v32);
      v34 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v46);
      v35 = MSXML2::IXMLDOMParseError::GetsrcText(v34, v55);
      v36 = _bstr_t::operator+(v33, v54, v35);
      v37 = _bstr_t::_bstr_t((_bstr_t *)v53, "\nLine: ");
      v38 = _bstr_t::operator+(v36, v52, v37);
      v39 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(&v46);
      LODWORD(v47) = MSXML2::IXMLDOMParseError::Getline(v39);
      v62 = 3;
      v63 = v47;
      v40 = _bstr_t::_bstr_t((_bstr_t *)v51, (const struct _variant_t *)&v62);
      v41 = _bstr_t::operator+(v38, v50, v40);
      v42 = _bstr_t::_bstr_t((_bstr_t *)v49, "\n");
      _bstr_t::operator+(v41, &v45, v42);
      _bstr_t::_Free((_bstr_t *)v49);
      _bstr_t::_Free((_bstr_t *)v50);
      _bstr_t::_Free((_bstr_t *)v51);
      _variant_t::~_variant_t((_variant_t *)&v62);
      _bstr_t::_Free((_bstr_t *)v52);
      _bstr_t::_Free((_bstr_t *)v53);
      _bstr_t::_Free((_bstr_t *)v54);
      _bstr_t::_Free((_bstr_t *)v55);
      _bstr_t::_Free((_bstr_t *)v56);
      _bstr_t::_Free((_bstr_t *)v57);
      _bstr_t::_Free((_bstr_t *)v58);
      _bstr_t::_Free((_bstr_t *)v59);
      _bstr_t::_Free((_bstr_t *)v60);
      _bstr_t::_Free((_bstr_t *)v61);
      _bstr_t::_Free((_bstr_t *)v48);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("%S");
        if ( v45 )
          v43 = *v45;
        else
          v43 = 0;
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_35f0385197fd35cdb48f774109abba17_Traceguids,
          (unsigned int)"NPSDS",
          v43);
      }
      _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator=(v17);
      _bstr_t::_Free((_bstr_t *)&v45);
      LOBYTE(v44) = 1;
      std::wstring::_Tidy(v64, v44, 0);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      return -2147418113;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004d900  push    rbx
0x18004d902  push    rsi
0x18004d903  push    rdi
0x18004d904  push    r12
0x18004d906  push    r13
0x18004d908  push    r14
0x18004d90a  push    r15
0x18004d90c  sub     rsp, 120h
0x18004d913  mov     rax, cs:__security_cookie
0x18004d91a  xor     rax, rsp
0x18004d91d  mov     [rsp+158h+var_48], rax
0x18004d925  mov     r13, r8
0x18004d928  mov     r12, rdx
0x18004d92b  mov     [rsp+158h+var_128], rcx
0x18004d930  xor     esi, esi
0x18004d932  mov     ebx, esi
0x18004d934  mov     [rsp+158h+var_120], rbx
0x18004d939  lea     edi, [rsi+17h]
0x18004d93c  mov     r9d, edi
0x18004d93f  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(_GUID const &,IUnknown *,ulong)
0x18004d944  test    eax, eax
0x18004d946  jns     short loc_18004D94D
0x18004d948  jmp     loc_18004DE74
0x18004d94d  xor     edx, edx; hFile
0x18004d94f  lea     r8d, [rdx+22h]; dwFlags
0x18004d953  mov     rcx, r12; lpLibFileName
0x18004d956  call    cs:__imp_LoadLibraryExW
0x18004d95c  mov     r14, rax
0x18004d95f  test    rax, rax
0x18004d962  jnz     short loc_18004D97B
0x18004d964  call    cs:__imp_GetLastError
0x18004d96a  test    eax, eax
0x18004d96c  jle     short loc_18004D976
0x18004d96e  movzx   eax, ax
0x18004d971  or      eax, 80070000h
0x18004d976  jmp     loc_18004DE74
0x18004d97b  mov     r8, rdi; lpType
0x18004d97e  mov     rdx, r13; lpName
0x18004d981  mov     rcx, r14; hModule
0x18004d984  call    cs:__imp_FindResourceW
0x18004d98a  mov     r15, rax
0x18004d98d  test    rax, rax
0x18004d990  jnz     short loc_18004D9B8
0x18004d992  call    cs:__imp_GetLastError
0x18004d998  mov     ebx, eax
0x18004d99a  test    eax, eax
0x18004d99c  jle     short loc_18004D9A7
0x18004d99e  movzx   ebx, ax
0x18004d9a1  or      ebx, 80070000h
0x18004d9a7  mov     rcx, r14; hLibModule
0x18004d9aa  call    cs:__imp_FreeLibrary
0x18004d9b0  nop
0x18004d9b1  mov     eax, ebx
0x18004d9b3  jmp     loc_18004DE74
0x18004d9b8  mov     rdx, r15; hResInfo
0x18004d9bb  mov     rcx, r14; hModule
0x18004d9be  call    cs:__imp_SizeofResource
0x18004d9c4  mov     edi, eax
0x18004d9c6  mov     rcx, r14; hModule
0x18004d9c9  cmp     eax, 2
0x18004d9cc  ja      short loc_18004D9DF
0x18004d9ce  call    cs:__imp_FreeLibrary
0x18004d9d4  nop
0x18004d9d5  mov     eax, 8007000Dh
0x18004d9da  jmp     loc_18004DE74
0x18004d9df  mov     rdx, r15; hResInfo
0x18004d9e2  call    cs:__imp_LoadResource
0x18004d9e8  test    rax, rax
0x18004d9eb  jnz     short loc_18004DA0E
0x18004d9ed  call    cs:__imp_GetLastError
0x18004d9f3  mov     ebx, eax
0x18004d9f5  test    eax, eax
0x18004d9f7  jle     short loc_18004DA02
0x18004d9f9  movzx   ebx, ax
0x18004d9fc  or      ebx, 80070000h
0x18004da02  mov     rcx, r14; hLibModule
0x18004da05  call    cs:__imp_FreeLibrary
0x18004da0b  nop
0x18004da0c  jmp     short loc_18004D9B1
0x18004da0e  mov     [rsp+158h+var_50], 7
0x18004da1a  mov     [rsp+158h+var_58], rsi
0x18004da22  mov     word ptr [rsp+158h+var_68], si
0x18004da2a  shr     edi, 1
0x18004da2c  dec     edi
0x18004da2e  mov     rcx, rax; hResData
0x18004da31  call    cs:__imp_LockResource
0x18004da37  lea     rdx, [rax+2]
0x18004da3b  mov     r8d, edi
0x18004da3e  lea     rcx, [rsp+158h+var_68]
0x18004da46  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAAAEAV12@PEBG_K@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004da4b  mov     rcx, r14; hLibModule
0x18004da4e  call    cs:__imp_FreeLibrary
0x18004da54  nop
0x18004da55  mov     r14, [rsp+158h+var_128]
0x18004da5a  mov     rcx, r14
0x18004da5d  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004da62  mov     rcx, rax; this
0x18004da65  call    ?Putasync@IXMLDOMDocument@MSXML2@@QEAAXF@Z; MSXML2::IXMLDOMDocument::Putasync(short)
0x18004da6a  mov     rcx, r14
0x18004da6d  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004da72  mov     rdi, rax
0x18004da75  lea     rdx, [rsp+158h+var_68]
0x18004da7d  cmp     [rsp+158h+var_50], 8
0x18004da86  cmovnb  rdx, [rsp+158h+var_68]; unsigned __int16 *
0x18004da8f  lea     rcx, [rsp+158h+var_128]; this
0x18004da94  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004da99  mov     rdx, rax
0x18004da9c  mov     rcx, rdi
0x18004da9f  call    ?loadXML@IXMLDOMDocument@MSXML2@@QEAAFV_bstr_t@@@Z; MSXML2::IXMLDOMDocument::loadXML(_bstr_t)
0x18004daa4  cmp     ax, 0FFFFh
0x18004daa8  jz      loc_18004DE2F
0x18004daae  lea     r15, WPP_GLOBAL_Control
0x18004dab5  mov     rax, cs:WPP_GLOBAL_Control
0x18004dabc  cmp     rax, r15
0x18004dabf  jz      short loc_18004DB0C
0x18004dac1  cmp     byte ptr [rax+19h], 2
0x18004dac5  jb      short loc_18004DB0C
0x18004dac7  test    byte ptr [rax+1Ch], 10h
0x18004dacb  jz      short loc_18004DB0C
0x18004dacd  mov     r8, r13
0x18004dad0  mov     rdx, r12
0x18004dad3  lea     rcx, aCiasmigrationh_0; "CIASMigrationHelper::LoadXMLFromResourc"...
0x18004dada  call    WppDbgPrint
0x18004dadf  mov     edx, 0Ch
0x18004dae4  mov     [rsp+158h+var_130], r13; __int64
0x18004dae9  mov     [rsp+158h+var_138], r12; __int64
0x18004daee  lea     r9, aNpsds; "NPSDS"
0x18004daf5  lea     r8, WPP_35f0385197fd35cdb48f774109abba17_Traceguids
0x18004dafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db03  mov     rcx, [rcx+10h]; LoggerHandle
0x18004db07  call    WPP_SF_sSS
0x18004db0c  mov     rcx, r14
0x18004db0f  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004db14  lea     rdx, [rsp+158h+var_118]
0x18004db19  mov     rcx, rax; struct IUnknown *
0x18004db1c  call    ?GetparseError@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMParseError@MSXML2@@$1?_GUID_3efaa426_272f_11d2_836f_0000f87a7782@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetparseError(void)
0x18004db21  nop
0x18004db22  cmp     [rax], rsi
0x18004db25  jz      short loc_18004DB3A
0x18004db27  mov     rbx, [rax]
0x18004db2a  mov     [rsp+158h+var_120], rbx
0x18004db2f  lea     rcx, [rsp+158h+var_120]
0x18004db34  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMElement@MSXML2@@$1?_GUID_2933bf86_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMElement,&__s_GUID const _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60>>::_AddRef(void)
0x18004db39  nop
0x18004db3a  mov     rcx, [rsp+158h+var_118]
0x18004db3f  test    rcx, rcx
0x18004db42  jz      short loc_18004DB51
0x18004db44  mov     rax, [rcx]
0x18004db47  mov     rax, [rax+10h]
0x18004db4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db50  nop
0x18004db51  lea     rdx, asc_180066E88; "\n====================="
0x18004db58  lea     rcx, [rsp+158h+var_110]; this
0x18004db5d  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004db62  mov     rdi, rax
0x18004db65  lea     rdx, aReason; "\nReason: "
0x18004db6c  lea     rcx, [rsp+158h+var_A8]; this
0x18004db74  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004db79  nop
0x18004db7a  mov     r8, rax
0x18004db7d  lea     rdx, [rsp+158h+var_B0]
0x18004db85  mov     rcx, rdi
0x18004db88  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004db8d  mov     rdi, rax
0x18004db90  lea     rcx, [rsp+158h+var_120]
0x18004db95  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004db9a  lea     rdx, [rsp+158h+var_B8]
0x18004dba2  mov     rcx, rax
0x18004dba5  call    ?Getreason@IXMLDOMParseError@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMParseError::Getreason(void)
0x18004dbaa  nop
0x18004dbab  mov     r8, rax
0x18004dbae  lea     rdx, [rsp+158h+var_C0]
0x18004dbb6  mov     rcx, rdi
0x18004dbb9  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004dbbe  mov     rdi, rax
0x18004dbc1  lea     rdx, aSource; "\nSource: "
0x18004dbc8  lea     rcx, [rsp+158h+var_C8]; this
0x18004dbd0  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004dbd5  nop
0x18004dbd6  mov     r8, rax
0x18004dbd9  lea     rdx, [rsp+158h+var_D0]
0x18004dbe1  mov     rcx, rdi
0x18004dbe4  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004dbe9  mov     rdi, rax
0x18004dbec  lea     rcx, [rsp+158h+var_120]
0x18004dbf1  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004dbf6  lea     rdx, [rsp+158h+var_D8]
0x18004dbfe  mov     rcx, rax
0x18004dc01  call    ?GetsrcText@IXMLDOMParseError@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMParseError::GetsrcText(void)
0x18004dc06  nop
0x18004dc07  mov     r8, rax
0x18004dc0a  lea     rdx, [rsp+158h+var_E0]
0x18004dc0f  mov     rcx, rdi
0x18004dc12  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004dc17  mov     rdi, rax
0x18004dc1a  lea     rdx, aLine; "\nLine: "
0x18004dc21  lea     rcx, [rsp+158h+var_E8]; this
0x18004dc26  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004dc2b  nop
0x18004dc2c  mov     r8, rax
0x18004dc2f  lea     rdx, [rsp+158h+var_F0]
0x18004dc34  mov     rcx, rdi
0x18004dc37  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004dc3c  mov     rdi, rax
0x18004dc3f  lea     rcx, [rsp+158h+var_120]
0x18004dc44  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004dc49  mov     rcx, rax; this
0x18004dc4c  call    ?Getline@IXMLDOMParseError@MSXML2@@QEAAJXZ; MSXML2::IXMLDOMParseError::Getline(void)
0x18004dc51  mov     dword ptr [rsp+158h+var_118], eax
0x18004dc55  mov     ecx, 3
0x18004dc5a  mov     [rsp+158h+var_A0], cx
0x18004dc62  mov     word ptr [rsp+158h+var_98], ax
0x18004dc6a  movzx   eax, word ptr [rsp+158h+var_118+2]
0x18004dc6f  mov     word ptr [rsp+158h+var_98+2], ax
0x18004dc77  lea     rdx, [rsp+158h+var_A0]; struct _variant_t *
0x18004dc7f  lea     rcx, [rsp+158h+var_F8]; this
0x18004dc84  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x18004dc89  nop
0x18004dc8a  mov     r8, rax
0x18004dc8d  lea     rdx, [rsp+158h+var_100]
0x18004dc92  mov     rcx, rdi
0x18004dc95  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004dc9a  mov     rdi, rax
0x18004dc9d  lea     rdx, asc_180066EC8; "\n"
0x18004dca4  lea     rcx, [rsp+158h+var_108]; this
0x18004dca9  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x18004dcae  nop
0x18004dcaf  mov     r8, rax
0x18004dcb2  lea     rdx, [rsp+158h+var_128]
0x18004dcb7  mov     rcx, rdi
0x18004dcba  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x18004dcbf  nop
0x18004dcc0  lea     rcx, [rsp+158h+var_108]; this
0x18004dcc5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dcca  nop
0x18004dccb  lea     rcx, [rsp+158h+var_100]; this
0x18004dcd0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dcd5  nop
0x18004dcd6  lea     rcx, [rsp+158h+var_F8]; this
0x18004dcdb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dce0  nop
0x18004dce1  lea     rcx, [rsp+158h+var_A0]; this
0x18004dce9  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004dcee  nop
0x18004dcef  lea     rcx, [rsp+158h+var_F0]; this
0x18004dcf4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dcf9  nop
0x18004dcfa  lea     rcx, [rsp+158h+var_E8]; this
0x18004dcff  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd04  nop
0x18004dd05  lea     rcx, [rsp+158h+var_E0]; this
0x18004dd0a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd0f  nop
0x18004dd10  lea     rcx, [rsp+158h+var_D8]; this
0x18004dd18  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd1d  nop
0x18004dd1e  lea     rcx, [rsp+158h+var_D0]; this
0x18004dd26  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd2b  nop
0x18004dd2c  lea     rcx, [rsp+158h+var_C8]; this
0x18004dd34  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd39  nop
0x18004dd3a  lea     rcx, [rsp+158h+var_C0]; this
0x18004dd42  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd47  nop
0x18004dd48  lea     rcx, [rsp+158h+var_B8]; this
0x18004dd50  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd55  nop
0x18004dd56  lea     rcx, [rsp+158h+var_B0]; this
0x18004dd5e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd63  nop
0x18004dd64  lea     rcx, [rsp+158h+var_A8]; this
0x18004dd6c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd71  nop
0x18004dd72  lea     rcx, [rsp+158h+var_110]; this
0x18004dd77  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18004dd7c  mov     rax, cs:WPP_GLOBAL_Control
0x18004dd83  cmp     rax, r15
0x18004dd86  jz      short loc_18004DDEC
0x18004dd88  cmp     byte ptr [rax+19h], 2
0x18004dd8c  jb      short loc_18004DDEC
0x18004dd8e  test    byte ptr [rax+1Ch], 10h
0x18004dd92  jz      short loc_18004DDEC
0x18004dd94  mov     rax, [rsp+158h+var_128]
0x18004dd99  test    rax, rax
0x18004dd9c  jz      short loc_18004DDA3
0x18004dd9e  mov     rdx, [rax]
0x18004dda1  jmp     short loc_18004DDA6
0x18004dda3  mov     rdx, rsi
0x18004dda6  lea     rcx, aS_0; "%S"
0x18004ddad  call    WppDbgPrint
0x18004ddb2  mov     rax, [rsp+158h+var_128]
0x18004ddb7  test    rax, rax
0x18004ddba  jz      short loc_18004DDC1
0x18004ddbc  mov     rcx, [rax]
0x18004ddbf  jmp     short loc_18004DDC4
0x18004ddc1  mov     rcx, rsi
0x18004ddc4  mov     edx, 0Dh
0x18004ddc9  mov     [rsp+158h+var_138], rcx
0x18004ddce  lea     r9, aNpsds; "NPSDS"
  ... truncated ...
```
