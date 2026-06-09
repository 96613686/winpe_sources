# IconNameTable::WriteIcons(IStream *,ushort *)

- ea: `0x18003c710`
- end: `0x18003d014`
- name: `?WriteIcons@IconNameTable@@AEAAJPEAUIStream@@PEAG@Z`
- size: `2308`
- prototype: `__int64 __fastcall(IconNameTable *__hidden this, struct IStream *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180101360`

## callees

- `0x1800364c0`
- `0x180038608`
- `0x18003a3e0`
- `0x18003a480`
- `0x18003c710`
- `0x18003d01c`
- `0x18003d1c0`
- `0x18007c180`
- `0x1801d3200`
- `0x180249490`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18003ca86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18003ca86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c96e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cb9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cbf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ccb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ccc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cdb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ce4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c96e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c983`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cb9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cbf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ccb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ccc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cdb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ce4f`

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
0x18003c710  mov     [rsp-8+arg_18], rbx
0x18003c715  push    rbp
0x18003c716  push    rsi
0x18003c717  push    rdi
0x18003c718  push    r12
0x18003c71a  push    r13
0x18003c71c  push    r14
0x18003c71e  push    r15
0x18003c720  lea     rbp, [rsp-1A0h]
0x18003c728  sub     rsp, 2A0h
0x18003c72f  mov     rax, cs:__security_cookie
0x18003c736  xor     rax, rsp
0x18003c739  mov     [rbp+1D0h+var_40], rax
0x18003c740  mov     rsi, r8
0x18003c743  mov     [rsp+2D0h+var_280], r8
0x18003c748  mov     r10, rdx
0x18003c74b  mov     [rsp+2D0h+var_298], rdx
0x18003c750  mov     r13, rcx
0x18003c753  mov     r9, [rcx+10h]
0x18003c757  mov     [rsp+2D0h+pv], r9
0x18003c75c  xor     r15d, r15d
0x18003c75f  test    rdx, rdx
0x18003c762  jnz     loc_18003C896
0x18003c768  test    rsi, rsi
0x18003c76b  jz      loc_18003CA3D
0x18003c771  lea     r8, aIconLookupTabl; "    Icon Lookup Table Count: %d"
0x18003c778  mov     edx, 100h; unsigned __int64
0x18003c77d  lea     rcx, [rbp+1D0h+pszSrc]; unsigned __int16 *
0x18003c781  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c786  mov     ebx, eax
0x18003c788  mov     ecx, 80000000h
0x18003c78d  add     eax, ecx
0x18003c78f  test    ecx, eax
0x18003c791  jz      loc_18003C8CC
0x18003c797  mov     edx, 0FA00h
0x18003c79c  mov     rax, rsi
0x18003c79f  cmp     [rax], r15w
0x18003c7a3  jz      short loc_18003C7AF
0x18003c7a5  add     rax, 2
0x18003c7a9  sub     rdx, 1
0x18003c7ad  jnz     short loc_18003C79F
0x18003c7af  mov     ecx, 80070057h
0x18003c7b4  test    rdx, rdx
0x18003c7b7  cmovnz  ecx, r15d
0x18003c7bb  mov     r8d, 0FA00h
0x18003c7c1  sub     r8, rdx
0x18003c7c4  test    rdx, rdx
0x18003c7c7  cmovz   r8, r15; pcchNewDestLength
0x18003c7cb  jnz     loc_18003CF12
0x18003c7d1  mov     ebx, r15d
0x18003c7d4  cmp     ecx, 8007007Ah
0x18003c7da  cmovnz  ebx, ecx
0x18003c7dd  test    ebx, ebx
0x18003c7df  js      loc_18003CF08
0x18003c7e5  mov     edx, 0FA00h
0x18003c7ea  mov     rax, rsi
0x18003c7ed  cmp     [rax], r15w
0x18003c7f1  jz      short loc_18003C7FD
0x18003c7f3  add     rax, 2
0x18003c7f7  sub     rdx, 1
0x18003c7fb  jnz     short loc_18003C7ED
0x18003c7fd  mov     ecx, 80070057h
0x18003c802  test    rdx, rdx
0x18003c805  cmovnz  ecx, r15d
0x18003c809  mov     r8d, 0FA00h
0x18003c80f  sub     r8, rdx
0x18003c812  test    rdx, rdx
0x18003c815  cmovz   r8, r15
0x18003c819  jnz     loc_18003CDE9
0x18003c81f  mov     ebx, r15d
0x18003c822  cmp     ecx, 8007007Ah
0x18003c828  cmovnz  ebx, ecx
0x18003c82b  test    ebx, ebx
0x18003c82d  jns     loc_18003CA3D
0x18003c833  mov     edx, 32h ; '2'; void *
0x18003c838  mov     r9d, ebx; char *
0x18003c83b  lea     r8, aShellShell32Ic_6; "shell\\shell32\\iconlayoutengine\\datam"...
0x18003c842  mov     rcx, [rbp+1D8h]; this
0x18003c849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c84e  mov     rcx, [rbp+1D8h]; this
0x18003c855  mov     r9d, ebx; char *
0x18003c858  lea     r8, aShellShell32Ic_4; "shell\\shell32\\iconlayoutengine\\datam"...
0x18003c85f  mov     edx, 72h ; 'r'; void *
0x18003c864  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c869  mov     eax, ebx
0x18003c86b  mov     rcx, [rbp+1D0h+var_40]
0x18003c872  xor     rcx, rsp; StackCookie
0x18003c875  call    __security_check_cookie
0x18003c87a  mov     rbx, [rsp+2D0h+arg_18]
0x18003c882  add     rsp, 2A0h
0x18003c889  pop     r15
0x18003c88b  pop     r14
0x18003c88d  pop     r13
0x18003c88f  pop     r12
0x18003c891  pop     rdi
0x18003c892  pop     rsi
0x18003c893  pop     rbp
0x18003c894  retn
0x18003c896  mov     [rbp+1D0h+var_250], r15d
0x18003c89a  mov     rax, [rdx]
0x18003c89d  lea     r9, [rbp+1D0h+var_250]
0x18003c8a1  mov     r8d, 8
0x18003c8a7  lea     rdx, [rsp+2D0h+pv]
0x18003c8ac  mov     rcx, r10
0x18003c8af  mov     rax, [rax+20h]
0x18003c8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8b8  mov     ebx, eax
0x18003c8ba  test    eax, eax
0x18003c8bc  js      loc_18003CF2E
0x18003c8c2  mov     r9, [rsp+2D0h+pv]
0x18003c8c7  jmp     loc_18003C768
0x18003c8cc  cmp     ebx, 8007007Ah
0x18003c8d2  jz      loc_18003C797
0x18003c8d8  mov     edx, 2Fh ; '/'
0x18003c8dd  jmp     loc_18003C838
0x18003c8e2  mov     ecx, 80070057h
0x18003c8e7  xor     eax, eax
0x18003c8e9  test    rdx, rdx
0x18003c8ec  cmovnz  ecx, eax
0x18003c8ef  mov     r8d, 0FA00h
0x18003c8f5  sub     r8, rdx
0x18003c8f8  test    rdx, rdx
0x18003c8fb  cmovz   r8, rax
0x18003c8ff  jnz     loc_18003C996
0x18003c905  xor     edi, edi
0x18003c907  cmp     ecx, 8007007Ah
0x18003c90d  cmovnz  edi, ecx
0x18003c910  test    edi, edi
0x18003c912  jns     loc_18003C9F5
0x18003c918  mov     edx, 59h ; 'Y'; void *
0x18003c91d  mov     r9d, edi; char *
0x18003c920  lea     r8, aShellShell32Ic_6; "shell\\shell32\\iconlayoutengine\\datam"...
0x18003c927  mov     rcx, [rbp+1D8h]; this
0x18003c92e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c933  mov     rcx, [rbp+1D8h]; this
0x18003c93a  mov     r9d, edi; char *
0x18003c93d  lea     r8, aShellShell32Ic_4; "shell\\shell32\\iconlayoutengine\\datam"...
0x18003c944  mov     edx, 85h; void *
0x18003c949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c94e  nop
0x18003c94f  test    rbx, rbx
0x18003c952  jz      short loc_18003C964
0x18003c954  mov     rcx, rbx; pv
0x18003c957  call    cs:__imp_CoTaskMemFree
0x18003c95e  nop     dword ptr [rax+rax+00h]
0x18003c963  nop
0x18003c964  mov     rcx, [rsp+2D0h+var_258]; pv
0x18003c969  test    rcx, rcx
0x18003c96c  jz      short loc_18003C97B
0x18003c96e  call    cs:__imp_CoTaskMemFree
0x18003c975  nop     dword ptr [rax+rax+00h]
0x18003c97a  nop
0x18003c97b  test    r14, r14
0x18003c97e  jz      short loc_18003C98F
0x18003c980  mov     rcx, r14; pv
0x18003c983  call    cs:__imp_CoTaskMemFree
0x18003c98a  nop     dword ptr [rax+rax+00h]
0x18003c98f  mov     eax, edi
0x18003c991  jmp     loc_18003C86B
0x18003c996  mov     ecx, 7FFFFFFEh
0x18003c99b  lea     r9, asc_180614FAC; "\r\n"
0x18003c9a2  mov     edx, 0FA00h
0x18003c9a7  sub     rdx, r8
0x18003c9aa  lea     rax, [rsi+r8*2]
0x18003c9ae  jnz     loc_18003CFBD
0x18003c9b4  lea     rcx, [rax-2]
0x18003c9b8  test    rdx, rdx
0x18003c9bb  cmovnz  rcx, rax
0x18003c9bf  xor     eax, eax
0x18003c9c1  mov     [rcx], ax
0x18003c9c4  mov     ecx, 8007007Ah
0x18003c9c9  test    rdx, rdx
0x18003c9cc  cmovnz  ecx, eax
0x18003c9cf  jmp     loc_18003C905
0x18003c9d4  mov     rcx, [rsp+2D0h+var_298]
0x18003c9d9  test    rcx, rcx
0x18003c9dc  jnz     loc_18003CCE2
0x18003c9e2  mov     rsi, [rsp+2D0h+var_280]
0x18003c9e7  test    rsi, rsi
0x18003c9ea  jz      short loc_18003C9F5
0x18003c9ec  test    r14, r14
0x18003c9ef  jnz     loc_18003CF6C
0x18003c9f5  mov     rdi, r15
0x18003c9f8  test    rbx, rbx
0x18003c9fb  jz      short loc_18003CA0D
0x18003c9fd  mov     rcx, rbx; pv
0x18003ca00  call    cs:__imp_CoTaskMemFree
0x18003ca07  nop     dword ptr [rax+rax+00h]
0x18003ca0c  nop
0x18003ca0d  mov     rcx, [rsp+2D0h+var_258]; pv
0x18003ca12  test    rcx, rcx
0x18003ca15  jz      short loc_18003CA24
0x18003ca17  call    cs:__imp_CoTaskMemFree
0x18003ca1e  nop     dword ptr [rax+rax+00h]
0x18003ca23  nop
0x18003ca24  test    r14, r14
0x18003ca27  jz      short loc_18003CA38
0x18003ca29  mov     rcx, r14; pv
0x18003ca2c  call    cs:__imp_CoTaskMemFree
0x18003ca33  nop     dword ptr [rax+rax+00h]
0x18003ca38  xor     r15d, r15d
0x18003ca3b  jmp     short loc_18003CA40
0x18003ca3d  mov     rdi, r15
0x18003ca40  cmp     rdi, [r13+10h]
0x18003ca44  jnb     loc_18003CD83
0x18003ca4a  mov     r14, r15
0x18003ca4d  mov     [rsp+2D0h+var_2A0], r15
0x18003ca52  mov     [rsp+2D0h+var_258], r15
0x18003ca57  lea     rax, [rsp+2D0h+var_258]
0x18003ca5c  mov     [rsp+2D0h+var_278], rax
0x18003ca61  mov     [rsp+2D0h+var_268], 1
0x18003ca66  mov     rax, [r13+20h]
0x18003ca6a  mov     [rsp+2D0h+var_270], r15
0x18003ca6f  mov     [rsp+2D0h+pv], r15
0x18003ca74  test    byte ptr [rax+rdi*4], 2
0x18003ca78  jnz     loc_18003CC44
0x18003ca7e  mov     rcx, [r13+18h]
0x18003ca82  mov     rcx, [rcx+rdi*8]; pszPath
0x18003ca86  call    cs:__imp_PathFindExtensionW
0x18003ca8d  nop     dword ptr [rax+rax+00h]
0x18003ca92  lea     r9, aNoExt; "no_ext"
0x18003ca99  cmp     word ptr [rax], 0
0x18003ca9d  cmovnz  r9, rax
0x18003caa1  lea     r15, [rdi+1]
0x18003caa5  mov     r8, r15
0x18003caa8  lea     rdx, aZuLs; "\"%zu_%ls\""
0x18003caaf  lea     rcx, [rsp+2D0h+pv]
0x18003cab4  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003cab9  mov     ebx, eax
0x18003cabb  test    eax, eax
0x18003cabd  js      loc_18003CD8A
0x18003cac3  mov     rsi, [rsp+2D0h+pv]
0x18003cac8  mov     [rsp+2D0h+var_270], rsi
0x18003cacd  xor     ebx, ebx
0x18003cacf  shr     ebx, 1Fh
0x18003cad2  xor     bl, 1
0x18003cad5  mov     rcx, [rsp+2D0h+var_258]; pv
0x18003cada  test    rcx, rcx
0x18003cadd  jnz     loc_18003CCD8
0x18003cae3  mov     [rsp+2D0h+var_258], rsi
0x18003cae8  test    bl, bl
0x18003caea  jnz     loc_18003CBBF
0x18003caf0  mov     [rsp+2D0h+pv], 0
0x18003caf9  mov     rax, [r13+20h]
0x18003cafd  mov     edx, [rax+rdi*4]
0x18003cb00  mov     rax, [r13+18h]
0x18003cb04  mov     r10, [rax+rdi*8]
0x18003cb08  test    dl, 1
0x18003cb0b  jz      loc_18003CE24
0x18003cb11  test    dl, 4
0x18003cb14  mov     ecx, 7Ch ; '|'
0x18003cb19  mov     r8d, 20h ; ' '
0x18003cb1f  cmovz   ecx, r8d
0x18003cb23  test    dl, 2
0x18003cb26  mov     eax, 5Ch ; '\'
0x18003cb2b  cmovz   eax, r8d
0x18003cb2f  mov     dword ptr [rsp+2D0h+var_2A8], ecx
0x18003cb33  mov     [rsp+2D0h+var_2B0], eax; int
0x18003cb37  mov     r9d, 3Eh ; '>'
0x18003cb3d  mov     r8, r10
0x18003cb40  lea     rdx, aLsCCC; "%ls%c%c%c"
0x18003cb47  lea     rcx, [rsp+2D0h+pv]
0x18003cb4c  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003cb51  mov     edi, eax
0x18003cb53  mov     rbx, [rsp+2D0h+pv]
0x18003cb58  test    eax, eax
0x18003cb5a  jns     loc_18003C9D4
0x18003cb60  mov     edx, 66h ; 'f'; void *
0x18003cb65  mov     r9d, edi; char *
0x18003cb68  mov     rcx, [rbp+1D8h]; this
0x18003cb6f  lea     r8, aShellShell32Ic_4; "shell\\shell32\\iconlayoutengine\\datam"...
0x18003cb76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb7b  mov     rcx, [rbp+1D8h]; this
0x18003cb82  mov     r9d, edi; char *
0x18003cb85  lea     r8, aShellShell32Ic_4; "shell\\shell32\\iconlayoutengine\\datam"...
0x18003cb8c  mov     edx, 83h; void *
0x18003cb91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb96  nop
0x18003cb97  test    rbx, rbx
0x18003cb9a  jz      short loc_18003CBAC
0x18003cb9c  mov     rcx, rbx; pv
0x18003cb9f  call    cs:__imp_CoTaskMemFree
0x18003cba6  nop     dword ptr [rax+rax+00h]
0x18003cbab  nop
0x18003cbac  mov     rcx, [rsp+2D0h+var_258]
0x18003cbb1  test    rcx, rcx
0x18003cbb4  jz      loc_18003C97B
0x18003cbba  jmp     loc_18003C96E
0x18003cbbf  xor     edx, edx; unsigned __int16 *
0x18003cbc1  mov     r8d, 104h; unsigned __int64
0x18003cbc7  lea     rcx, [rsp+2D0h+var_290]; this
0x18003cbcc  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18003cbd1  lea     rcx, [rsp+2D0h+var_2A0]
0x18003cbd6  cmp     rcx, rax
0x18003cbd9  jz      short loc_18003CBEA
0x18003cbdb  mov     r14, [rax]
0x18003cbde  mov     [rsp+2D0h+var_2A0], r14
0x18003cbe3  mov     qword ptr [rax], 0
0x18003cbea  mov     rcx, [rsp+2D0h+var_290]; pv
0x18003cbef  test    rcx, rcx
  ... truncated ...
```
