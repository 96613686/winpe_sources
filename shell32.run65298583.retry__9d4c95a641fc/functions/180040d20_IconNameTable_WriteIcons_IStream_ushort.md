# IconNameTable::WriteIcons(IStream *,ushort *)

- ea: `0x180040d20`
- end: `0x1800415d4`
- name: `?WriteIcons@IconNameTable@@AEAAJPEAUIStream@@PEAG@Z`
- size: `2228`
- prototype: `__int64 __fastcall(IconNameTable *__hidden this, struct IStream *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f9a70`

## callees

- `0x18003ac60`
- `0x18003cd64`
- `0x18003eab0`
- `0x18003eb50`
- `0x180040d20`
- `0x1800415dc`
- `0x180041770`
- `0x180080470`
- `0x1801be5c8`
- `0x180233280`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180041076`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180041076`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004100a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004120e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004128d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041297`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004137c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041415`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040ff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004100a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004120e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004128d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041297`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004137c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041415`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IconNameTable::WriteIcons(IconNameTable *this, struct IStream *a2, unsigned __int16 *a3)
{
  int v5; // ebx
  size_t v6; // rdx
  unsigned __int16 *v7; // rax
  HRESULT v8; // ecx
  __int64 v9; // rdx
  unsigned __int16 *v10; // rax
  int v11; // ecx
  __int64 v12; // r8
  __int64 v13; // rdx
  unsigned __int64 v14; // r9
  int v16; // eax
  int v17; // ecx
  __int64 v18; // r8
  int v19; // edi
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  void *v22; // rcx
  __int64 v23; // rcx
  const unsigned __int16 *v24; // r9
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rcx
  unsigned __int16 *v27; // rsi
  unsigned __int64 v28; // rdi
  unsigned __int16 *v29; // r14
  __int64 v30; // rax
  LPWSTR ExtensionW; // rax
  const wchar_t *v32; // r9
  unsigned __int64 v33; // r15
  int v34; // eax
  int v35; // ebx
  void *v36; // rsi
  bool v37; // bl
  int v38; // edx
  __int64 v39; // rax
  __int64 v40; // r10
  int v41; // ecx
  int v42; // eax
  void *v43; // rbx
  __int64 v44; // rdx
  unsigned __int16 **cotaskmem_string_nothrow; // rax
  unsigned int v46; // ebx
  __int64 v47; // rsi
  __int64 v48; // rsi
  int v49; // eax
  unsigned __int64 v50; // r8
  int v51; // eax
  int v52; // eax
  __int64 v53; // rcx
  const unsigned __int16 *v54; // r9
  unsigned __int16 *v55; // rax
  unsigned __int16 *v56; // rcx
  __int64 v57; // rax
  int v58; // ecx
  __int64 v59; // rdx
  __int64 v60; // rdx
  unsigned __int16 *v61; // rax
  __int64 v62; // rcx
  unsigned __int16 *v63; // r9
  unsigned __int16 *v64; // rax
  unsigned __int16 *v65; // rcx
  unsigned __int16 v66; // r8
  __int64 v67; // r8
  unsigned __int16 *v68; // rax
  unsigned __int16 v69; // dx
  unsigned __int16 v70; // r8
  LPVOID v71; // [rsp+20h] [rbp-E0h]
  int v72; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+20h] [rbp-E0h]
  int v74; // [rsp+20h] [rbp-E0h]
  __int64 v75; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v76; // [rsp+30h] [rbp-D0h] BYREF
  struct IStream *v77; // [rsp+38h] [rbp-C8h]
  LPVOID v78; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v79; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v80; // [rsp+50h] [rbp-B0h]
  LPVOID *v81; // [rsp+58h] [rbp-A8h]
  LPVOID v82; // [rsp+60h] [rbp-A0h]
  char v83; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v85; // [rsp+78h] [rbp-88h] BYREF
  int v86; // [rsp+80h] [rbp-80h] BYREF
  int v87; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v88; // [rsp+88h] [rbp-78h] BYREF
  wchar_t pszSrc[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v80 = a3;
  v77 = a2;
  pv = (LPVOID)*((_QWORD *)this + 2);
  if ( a2 )
  {
    v86 = 0;
    v16 = ((__int64 (__fastcall *)(struct IStream *, LPVOID *, __int64, int *))a2->lpVtbl->Write)(a2, &pv, 8, &v86);
    v5 = v16;
    if ( v16 < 0 )
    {
      v14 = (unsigned int)v16;
      v13 = 17;
      goto LABEL_23;
    }
  }
  if ( a3 )
  {
    v5 = StringCchPrintfW(pszSrc, 0x100u, L"    Icon Lookup Table Count: %d");
    if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147024774 )
    {
      v13 = 47;
      goto LABEL_22;
    }
    v6 = 64000;
    v7 = a3;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v6;
    }
    while ( v6 );
    v8 = -2147024809;
    if ( v6 )
      v8 = StringCopyWorkerW_0(&a3[64000 - v6], v6, (size_t *)(64000 - v6), pszSrc, (size_t)v71);
    v5 = 0;
    if ( v8 != -2147024774 )
      v5 = v8;
    if ( v5 < 0 )
    {
      v13 = 49;
      goto LABEL_22;
    }
    v9 = 64000;
    v10 = a3;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    v11 = -2147024809;
    if ( v9 )
      v11 = 0;
    v12 = 64000 - v9;
    if ( v9 )
    {
      v53 = 2147483646;
      v54 = L"\r\n";
      v55 = &a3[v12];
      if ( v12 != 64000 )
      {
        do
        {
          if ( !v53 )
            break;
          v66 = *v54;
          if ( !*v54 )
            break;
          ++v54;
          *v55++ = v66;
          --v53;
          --v9;
        }
        while ( v9 );
      }
      v56 = v55 - 1;
      if ( v9 )
        v56 = v55;
      *v56 = 0;
      v11 = -2147024774;
      if ( v9 )
        v11 = 0;
    }
    v5 = 0;
    if ( v11 != -2147024774 )
      v5 = v11;
    if ( v5 < 0 )
    {
      v13 = 50;
LABEL_22:
      v14 = (unsigned int)v5;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\DesktopIconLayoutHelpers.h",
        (const char *)v14,
        (int)v71);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\iconnametable.cpp",
        (const char *)(unsigned int)v5,
        v72);
      return (unsigned int)v5;
    }
  }
  v28 = 0;
  while ( 1 )
  {
    if ( v28 >= *((_QWORD *)this + 2) )
      return 0;
    v29 = 0;
    v76 = 0;
    v85 = 0;
    v81 = &v85;
    v83 = 1;
    v30 = *((_QWORD *)this + 4);
    v82 = 0;
    pv = 0;
    if ( (*(_BYTE *)(v30 + 4 * v28) & 2) != 0 )
    {
      v32 = L"folder";
    }
    else
    {
      ExtensionW = PathFindExtensionW(*(LPCWSTR *)(*((_QWORD *)this + 3) + 8 * v28));
      v32 = L"no_ext";
      if ( *ExtensionW )
        v32 = ExtensionW;
    }
    v33 = v28 + 1;
    v34 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pv,
            L"\"%zu_%ls\"",
            v28 + 1,
            v32);
    v35 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"shell\\shell32\\DesktopIconLayoutTelemetry.h",
        (const char *)(unsigned int)v34,
        (int)v71);
      if ( pv )
        CoTaskMemFree(pv);
      v36 = 0;
    }
    else
    {
      v36 = pv;
      v82 = pv;
      v35 = 0;
    }
    v37 = v35 >= 0;
    if ( v85 )
      wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(v85);
    v85 = v36;
    if ( v37 )
    {
      cotaskmem_string_nothrow = (unsigned __int16 **)wil::make_cotaskmem_string_nothrow((wil *)&v78, 0, 0x104u);
      if ( &v76 != cotaskmem_string_nothrow )
      {
        v29 = *cotaskmem_string_nothrow;
        v76 = *cotaskmem_string_nothrow;
        *cotaskmem_string_nothrow = 0;
      }
      if ( v78 )
        CoTaskMemFree(v78);
      if ( !v29 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7C,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\iconnametable.cpp",
          (const char *)0x8007000ELL,
          (int)v71);
        if ( v85 )
          CoTaskMemFree(v85);
        return 2147942414LL;
      }
      v71 = v85;
      v46 = StringCchPrintfW(v29, 0x104u, L"      %03d: \"%ls\"", (unsigned int)v28);
      if ( (int)(v46 + 0x80000000) >= 0 && v46 != -2147024774 )
        break;
    }
    pv = 0;
    v38 = *(_DWORD *)(*((_QWORD *)this + 4) + 4 * v28);
    v39 = *((_QWORD *)this + 3);
    v40 = *(_QWORD *)(v39 + 8 * v28);
    if ( (v38 & 1) != 0 )
    {
      v41 = 124;
      if ( (v38 & 4) == 0 )
        v41 = 32;
      v42 = 92;
      if ( (v38 & 2) == 0 )
        v42 = 32;
      LODWORD(v75) = v41;
      LODWORD(v71) = v42;
      v19 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &pv,
              L"%ls%c%c%c",
              v40,
              62,
              v71,
              v75,
              v76);
      v43 = pv;
      if ( v19 < 0 )
      {
        v44 = 102;
        goto LABEL_76;
      }
    }
    else
    {
      v57 = wil::make_cotaskmem_string_nothrow(
              (wil *)&v79,
              *(const unsigned __int16 **)(v39 + 8 * v28),
              0xFFFFFFFFFFFFFFFFuLL);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &pv,
        v57);
      if ( v79 )
        CoTaskMemFree(v79);
      v43 = pv;
      if ( !pv )
      {
        v19 = -2147024882;
        v44 = 107;
LABEL_76:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v44,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\iconnametable.cpp",
          (const char *)(unsigned int)v19,
          (int)v71);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\iconnametable.cpp",
          (const char *)(unsigned int)v19,
          v74);
        if ( v43 )
          CoTaskMemFree(v43);
        v22 = v85;
        if ( v85 )
LABEL_39:
          CoTaskMemFree(v22);
LABEL_40:
        if ( v29 )
          CoTaskMemFree(v29);
        return (unsigned int)v19;
      }
    }
    if ( v77 )
    {
      if ( v43 )
      {
        v47 = -1;
        do
          ++v47;
        while ( *((_WORD *)v43 + v47) );
        v48 = v47 + 1;
        v88 = v48;
        v86 = 0;
        v49 = ((__int64 (__fastcall *)(struct IStream *, __int64 *, __int64, int *))v77->lpVtbl->Write)(
                v77,
                &v88,
                8,
                &v86);
        v19 = v49;
        if ( v49 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\DesktopIconLayoutHelpers.h",
            (const char *)(unsigned int)v49,
            (int)v71);
          v20 = 76;
          goto LABEL_35;
        }
        v50 = 2LL * (unsigned int)v48;
        if ( v50 > 0xFFFFFFFF )
        {
          v19 = -2147024362;
          v20 = 79;
          goto LABEL_35;
        }
        v87 = 0;
        v51 = ((__int64 (__fastcall *)(struct IStream *, void *, unsigned __int64, int *))v77->lpVtbl->Write)(
                v77,
                v43,
                v50,
                &v87);
        v19 = v51;
        if ( v51 < 0 )
        {
          v21 = (unsigned int)v51;
          v20 = 82;
          goto LABEL_36;
        }
      }
      else
      {
        v52 = StreamHelper_Write<unsigned __int64>(0, 0, v77, 0);
        v19 = v52;
        if ( v52 < 0 )
        {
          v21 = (unsigned int)v52;
          v20 = 71;
LABEL_36:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\DesktopIconLayoutHelpers.h",
            (const char *)v21,
            (int)v71);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x85,
            (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\iconnametable.cpp",
            (const char *)(unsigned int)v19,
            v73);
          if ( v43 )
            CoTaskMemFree(v43);
          v22 = v85;
          if ( v85 )
            goto LABEL_39;
          goto LABEL_40;
        }
      }
    }
    v27 = v80;
    if ( v80 && v29 )
    {
      v67 = 64000;
      v68 = v80;
      do
      {
        if ( !*v68 )
          break;
        ++v68;
        --v67;
      }
      while ( v67 );
      v58 = -2147024809;
      if ( v67 )
        v58 = 0;
      v59 = 64000 - v67;
      if ( v67 )
      {
        v62 = 2147483646;
        v63 = v29;
        v64 = &v80[v59];
        if ( v59 != 64000 )
        {
          do
          {
            if ( !v62 )
              break;
            v69 = *v63;
            if ( !*v63 )
              break;
            ++v63;
            *v64++ = v69;
            --v62;
            --v67;
          }
          while ( v67 );
        }
        v65 = v64 - 1;
        if ( v67 )
          v65 = v64;
        *v65 = 0;
        v58 = -2147024774;
        if ( v67 )
          v58 = 0;
      }
      v19 = 0;
      if ( v58 != -2147024774 )
        v19 = v58;
      if ( v19 < 0 )
      {
        v20 = 88;
LABEL_35:
        v21 = (unsigned int)v19;
        goto LABEL_36;
      }
      v60 = 64000;
      v61 = v27;
      do
      {
        if ( !*v61 )
          break;
        ++v61;
        --v60;
      }
      while ( v60 );
      v17 = -2147024809;
      if ( v60 )
        v17 = 0;
      v18 = 64000 - v60;
      if ( v60 )
      {
        v23 = 2147483646;
        v24 = L"\r\n";
        v25 = &v27[v18];
        if ( v18 != 64000 )
        {
          do
          {
            if ( !v23 )
              break;
            v70 = *v24;
            if ( !*v24 )
              break;
            ++v24;
            *v25++ = v70;
            --v23;
            --v60;
          }
          while ( v60 );
        }
        v26 = v25 - 1;
        if ( v60 )
          v26 = v25;
        *v26 = 0;
        v17 = -2147024774;
        if ( v60 )
          v17 = 0;
      }
      v19 = 0;
      if ( v17 != -2147024774 )
        v19 = v17;
      if ( v19 < 0 )
      {
        v20 = 89;
        goto LABEL_35;
      }
    }
    v28 = v33;
    if ( v43 )
      CoTaskMemFree(v43);
    if ( v85 )
      CoTaskMemFree(v85);
    if ( v29 )
      CoTaskMemFree(v29);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7F,
    (unsigned int)"shell\\shell32\\iconlayoutengine\\datamodel\\iconnametable.cpp",
    (const char *)v46,
    (int)v71);
  if ( v85 )
    CoTaskMemFree(v85);
  CoTaskMemFree(v29);
  return v46;
}

```

## disassembly

```asm
0x180040d20  mov     [rsp-8+arg_18], rbx
0x180040d25  push    rbp
0x180040d26  push    rsi
0x180040d27  push    rdi
0x180040d28  push    r12
0x180040d2a  push    r13
0x180040d2c  push    r14
0x180040d2e  push    r15
0x180040d30  lea     rbp, [rsp-1A0h]
0x180040d38  sub     rsp, 2A0h
0x180040d3f  mov     rax, cs:__security_cookie
0x180040d46  xor     rax, rsp
0x180040d49  mov     [rbp+1D0h+var_40], rax
0x180040d50  mov     rsi, r8
0x180040d53  mov     [rsp+2D0h+var_280], r8
0x180040d58  mov     r10, rdx
0x180040d5b  mov     [rsp+2D0h+var_298], rdx
0x180040d60  mov     r13, rcx
0x180040d63  mov     r9, [rcx+10h]
0x180040d67  mov     [rsp+2D0h+pv], r9
0x180040d6c  xor     r15d, r15d
0x180040d6f  test    rdx, rdx
0x180040d72  jnz     loc_180040EA5
0x180040d78  test    rsi, rsi
0x180040d7b  jz      loc_180041024
0x180040d81  lea     r8, aIconLookupTabl; "    Icon Lookup Table Count: %d"
0x180040d88  mov     edx, 100h; unsigned __int64
0x180040d8d  lea     rcx, [rbp+1D0h+pszSrc]; unsigned __int16 *
0x180040d91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040d96  mov     ebx, eax
0x180040d98  mov     ecx, 80000000h
0x180040d9d  add     eax, ecx
0x180040d9f  test    ecx, eax
0x180040da1  jz      loc_180040EDB
0x180040da7  mov     edx, 0FA00h
0x180040dac  mov     rax, rsi
0x180040daf  cmp     [rax], r15w
0x180040db3  jz      short loc_180040DBF
0x180040db5  add     rax, 2
0x180040db9  sub     rdx, 1
0x180040dbd  jnz     short loc_180040DAF
0x180040dbf  mov     ecx, 80070057h
0x180040dc4  test    rdx, rdx
0x180040dc7  cmovnz  ecx, r15d
0x180040dcb  mov     r8d, 0FA00h
0x180040dd1  sub     r8, rdx
0x180040dd4  test    rdx, rdx
0x180040dd7  cmovz   r8, r15; pcchNewDestLength
0x180040ddb  jnz     loc_1800414D2
0x180040de1  mov     ebx, r15d
0x180040de4  cmp     ecx, 8007007Ah
0x180040dea  cmovnz  ebx, ecx
0x180040ded  test    ebx, ebx
0x180040def  js      loc_1800414C8
0x180040df5  mov     edx, 0FA00h
0x180040dfa  mov     rax, rsi
0x180040dfd  cmp     [rax], r15w
0x180040e01  jz      short loc_180040E0D
0x180040e03  add     rax, 2
0x180040e07  sub     rdx, 1
0x180040e0b  jnz     short loc_180040DFD
0x180040e0d  mov     ecx, 80070057h
0x180040e12  test    rdx, rdx
0x180040e15  cmovnz  ecx, r15d
0x180040e19  mov     r8d, 0FA00h
0x180040e1f  sub     r8, rdx
0x180040e22  test    rdx, rdx
0x180040e25  cmovz   r8, r15
0x180040e29  jnz     loc_1800413AF
0x180040e2f  mov     ebx, r15d
0x180040e32  cmp     ecx, 8007007Ah
0x180040e38  cmovnz  ebx, ecx
0x180040e3b  test    ebx, ebx
0x180040e3d  jns     loc_180041024
0x180040e43  mov     edx, 32h ; '2'; void *
0x180040e48  mov     r9d, ebx; char *
0x180040e4b  lea     r8, aShellShell32Ic_6; "shell\\shell32\\iconlayoutengine\\datam"...
0x180040e52  mov     rcx, [rbp+1D8h]; this
0x180040e59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040e5e  mov     rcx, [rbp+1D8h]; this
0x180040e65  mov     r9d, ebx; char *
0x180040e68  lea     r8, aShellShell32Ic_4; "shell\\shell32\\iconlayoutengine\\datam"...
0x180040e6f  mov     edx, 72h ; 'r'; void *
0x180040e74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040e79  mov     eax, ebx
0x180040e7b  mov     rcx, [rbp+1D0h+var_40]
0x180040e82  xor     rcx, rsp; StackCookie
0x180040e85  call    __security_check_cookie
0x180040e8a  mov     rbx, [rsp+2D0h+arg_18]
0x180040e92  add     rsp, 2A0h
0x180040e99  pop     r15
0x180040e9b  pop     r14
0x180040e9d  pop     r13
0x180040e9f  pop     r12
0x180040ea1  pop     rdi
0x180040ea2  pop     rsi
0x180040ea3  pop     rbp
0x180040ea4  retn
0x180040ea5  mov     [rbp+1D0h+var_250], r15d
0x180040ea9  mov     rax, [rdx]
0x180040eac  lea     r9, [rbp+1D0h+var_250]
0x180040eb0  mov     r8d, 8
0x180040eb6  lea     rdx, [rsp+2D0h+pv]
0x180040ebb  mov     rcx, r10
0x180040ebe  mov     rax, [rax+20h]
0x180040ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ec7  mov     ebx, eax
0x180040ec9  test    eax, eax
0x180040ecb  js      loc_1800414EE
0x180040ed1  mov     r9, [rsp+2D0h+pv]
0x180040ed6  jmp     loc_180040D78
0x180040edb  cmp     ebx, 8007007Ah
0x180040ee1  jz      loc_180040DA7
0x180040ee7  mov     edx, 2Fh ; '/'
0x180040eec  jmp     loc_180040E48
0x180040ef1  mov     ecx, 80070057h
0x180040ef6  xor     eax, eax
0x180040ef8  test    rdx, rdx
0x180040efb  cmovnz  ecx, eax
0x180040efe  mov     r8d, 0FA00h
0x180040f04  sub     r8, rdx
0x180040f07  test    rdx, rdx
0x180040f0a  cmovz   r8, rax
0x180040f0e  jnz     short loc_180040F8F
0x180040f10  xor     edi, edi
0x180040f12  cmp     ecx, 8007007Ah
0x180040f18  cmovnz  edi, ecx
0x180040f1b  test    edi, edi
0x180040f1d  jns     loc_180040FEE
0x180040f23  mov     edx, 59h ; 'Y'; void *
0x180040f28  mov     r9d, edi; char *
0x180040f2b  lea     r8, aShellShell32Ic_6; "shell\\shell32\\iconlayoutengine\\datam"...
0x180040f32  mov     rcx, [rbp+1D8h]; this
0x180040f39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f3e  mov     rcx, [rbp+1D8h]; this
0x180040f45  mov     r9d, edi; char *
0x180040f48  lea     r8, aShellShell32Ic_4; "shell\\shell32\\iconlayoutengine\\datam"...
0x180040f4f  mov     edx, 85h; void *
0x180040f54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f59  nop
0x180040f5a  test    rbx, rbx
0x180040f5d  jz      short loc_180040F69
0x180040f5f  mov     rcx, rbx; pv
0x180040f62  call    cs:__imp_CoTaskMemFree
0x180040f68  nop
0x180040f69  mov     rcx, [rsp+2D0h+var_258]; pv
0x180040f6e  test    rcx, rcx
0x180040f71  jz      short loc_180040F7A
0x180040f73  call    cs:__imp_CoTaskMemFree
0x180040f79  nop
0x180040f7a  test    r14, r14
0x180040f7d  jz      short loc_180040F88
0x180040f7f  mov     rcx, r14; pv
0x180040f82  call    cs:__imp_CoTaskMemFree
0x180040f88  mov     eax, edi
0x180040f8a  jmp     loc_180040E7B
0x180040f8f  mov     ecx, 7FFFFFFEh
0x180040f94  lea     r9, asc_1805D482C; "\r\n"
0x180040f9b  mov     edx, 0FA00h
0x180040fa0  sub     rdx, r8
0x180040fa3  lea     rax, [rsi+r8*2]
0x180040fa7  jnz     loc_18004157D
0x180040fad  lea     rcx, [rax-2]
0x180040fb1  test    rdx, rdx
0x180040fb4  cmovnz  rcx, rax
0x180040fb8  xor     eax, eax
0x180040fba  mov     [rcx], ax
0x180040fbd  mov     ecx, 8007007Ah
0x180040fc2  test    rdx, rdx
0x180040fc5  cmovnz  ecx, eax
0x180040fc8  jmp     loc_180040F10
0x180040fcd  mov     rcx, [rsp+2D0h+var_298]
0x180040fd2  test    rcx, rcx
0x180040fd5  jnz     loc_1800412AE
0x180040fdb  mov     rsi, [rsp+2D0h+var_280]
0x180040fe0  test    rsi, rsi
0x180040fe3  jz      short loc_180040FEE
0x180040fe5  test    r14, r14
0x180040fe8  jnz     loc_18004152C
0x180040fee  mov     rdi, r15
0x180040ff1  test    rbx, rbx
0x180040ff4  jz      short loc_180041000
0x180040ff6  mov     rcx, rbx; pv
0x180040ff9  call    cs:__imp_CoTaskMemFree
0x180040fff  nop
0x180041000  mov     rcx, [rsp+2D0h+var_258]; pv
0x180041005  test    rcx, rcx
0x180041008  jz      short loc_180041011
0x18004100a  call    cs:__imp_CoTaskMemFree
0x180041010  nop
0x180041011  test    r14, r14
0x180041014  jz      short loc_18004101F
0x180041016  mov     rcx, r14; pv
0x180041019  call    cs:__imp_CoTaskMemFree
0x18004101f  xor     r15d, r15d
0x180041022  jmp     short loc_180041030
0x180041024  mov     rdi, r15
0x180041027  nop     word ptr [rax+rax+00000000h]
0x180041030  cmp     rdi, [r13+10h]
0x180041034  jnb     loc_18004134F
0x18004103a  mov     r14, r15
0x18004103d  mov     [rsp+2D0h+var_2A0], r15
0x180041042  mov     [rsp+2D0h+var_258], r15
0x180041047  lea     rax, [rsp+2D0h+var_258]
0x18004104c  mov     [rsp+2D0h+var_278], rax
0x180041051  mov     [rsp+2D0h+var_268], 1
0x180041056  mov     rax, [r13+20h]
0x18004105a  mov     [rsp+2D0h+var_270], r15
0x18004105f  mov     [rsp+2D0h+pv], r15
0x180041064  test    byte ptr [rax+rdi*4], 2
0x180041068  jnz     loc_18004121C
0x18004106e  mov     rcx, [r13+18h]
0x180041072  mov     rcx, [rcx+rdi*8]; pszPath
0x180041076  call    cs:__imp_PathFindExtensionW
0x18004107c  lea     r9, aNoExt; "no_ext"
0x180041083  cmp     word ptr [rax], 0
0x180041087  cmovnz  r9, rax
0x18004108b  lea     r15, [rdi+1]
0x18004108f  mov     r8, r15
0x180041092  lea     rdx, aZuLs; "\"%zu_%ls\""
0x180041099  lea     rcx, [rsp+2D0h+pv]
0x18004109e  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800410a3  mov     ebx, eax
0x1800410a5  test    eax, eax
0x1800410a7  js      loc_180041356
0x1800410ad  mov     rsi, [rsp+2D0h+pv]
0x1800410b2  mov     [rsp+2D0h+var_270], rsi
0x1800410b7  xor     ebx, ebx
0x1800410b9  shr     ebx, 1Fh
0x1800410bc  xor     bl, 1
0x1800410bf  mov     rcx, [rsp+2D0h+var_258]; pv
0x1800410c4  test    rcx, rcx
0x1800410c7  jnz     loc_1800412A4
0x1800410cd  mov     [rsp+2D0h+var_258], rsi
0x1800410d2  test    bl, bl
0x1800410d4  jnz     loc_1800411A3
0x1800410da  mov     [rsp+2D0h+pv], 0
0x1800410e3  mov     rax, [r13+20h]
0x1800410e7  mov     edx, [rax+rdi*4]
0x1800410ea  mov     rax, [r13+18h]
0x1800410ee  mov     r10, [rax+rdi*8]
0x1800410f2  test    dl, 1
0x1800410f5  jz      loc_1800413EA
0x1800410fb  test    dl, 4
0x1800410fe  mov     ecx, 7Ch ; '|'
0x180041103  mov     r8d, 20h ; ' '
0x180041109  cmovz   ecx, r8d
0x18004110d  test    dl, 2
0x180041110  mov     eax, 5Ch ; '\'
0x180041115  cmovz   eax, r8d
0x180041119  mov     dword ptr [rsp+2D0h+var_2A8], ecx
0x18004111d  mov     [rsp+2D0h+var_2B0], eax; int
0x180041121  mov     r9d, 3Eh ; '>'
0x180041127  mov     r8, r10
0x18004112a  lea     rdx, aLsCCC; "%ls%c%c%c"
0x180041131  lea     rcx, [rsp+2D0h+pv]
0x180041136  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004113b  mov     edi, eax
0x18004113d  mov     rbx, [rsp+2D0h+pv]
0x180041142  test    eax, eax
0x180041144  jns     loc_180040FCD
0x18004114a  mov     edx, 66h ; 'f'; void *
0x18004114f  mov     r9d, edi; char *
0x180041152  mov     rcx, [rbp+1D8h]; this
0x180041159  lea     r8, aShellShell32Ic_4; "shell\\shell32\\iconlayoutengine\\datam"...
0x180041160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041165  mov     rcx, [rbp+1D8h]; this
0x18004116c  mov     r9d, edi; char *
0x18004116f  lea     r8, aShellShell32Ic_4; "shell\\shell32\\iconlayoutengine\\datam"...
0x180041176  mov     edx, 83h; void *
0x18004117b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041180  nop
0x180041181  test    rbx, rbx
0x180041184  jz      short loc_180041190
0x180041186  mov     rcx, rbx; pv
0x180041189  call    cs:__imp_CoTaskMemFree
0x18004118f  nop
0x180041190  mov     rcx, [rsp+2D0h+var_258]
0x180041195  test    rcx, rcx
0x180041198  jz      loc_180040F7A
0x18004119e  jmp     loc_180040F73
0x1800411a3  xor     edx, edx; unsigned __int16 *
0x1800411a5  mov     r8d, 104h; unsigned __int64
0x1800411ab  lea     rcx, [rsp+2D0h+var_290]; this
0x1800411b0  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x1800411b5  lea     rcx, [rsp+2D0h+var_2A0]
0x1800411ba  cmp     rcx, rax
0x1800411bd  jz      short loc_1800411CE
0x1800411bf  mov     r14, [rax]
0x1800411c2  mov     [rsp+2D0h+var_2A0], r14
0x1800411c7  mov     qword ptr [rax], 0
0x1800411ce  mov     rcx, [rsp+2D0h+var_290]; pv
0x1800411d3  test    rcx, rcx
0x1800411d6  jz      short loc_1800411DE
0x1800411d8  call    cs:__imp_CoTaskMemFree
0x1800411de  test    r14, r14
0x1800411e1  jnz     short loc_180041228
0x1800411e3  mov     rcx, [rbp+1D8h]; this
0x1800411ea  mov     edi, 8007000Eh
0x1800411ef  mov     r9d, edi; char *
  ... truncated ...
```
