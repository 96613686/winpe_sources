# CFSFolder::_DiscoverLocalizedName(_ITEMIDLIST_RELATIVE const *,tagWIN32_FIND_DATA_EX const *,ushort *,uint)

- ea: `0x1800d9c10`
- end: `0x1800da3a7`
- name: `?_DiscoverLocalizedName@CFSFolder@@IEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBUtagWIN32_FIND_DATA_EX@@PEAGI@Z`
- size: `1943`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct tagWIN32_FIND_DATA_EX *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d8af0`

## callees

- `0x1800432f0`
- `0x18008b3a0`
- `0x1800d9c10`
- `0x1801089a0`
- `0x1801deff0`
- `0x180201a20`
- `0x1803a4cb0`
- `0x18054ae1c`
- `0x18054afc8`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d9cbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d9ff5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d9cbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d9ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9fe2`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x1800d9c65`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x1800d9c65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9d67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9fbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9d67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9f3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d9fbb`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d9d35`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800d9d35`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800da05c`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800da05c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9cb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9d0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9e3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9f81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9fed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da14c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da2c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9cb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9d0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9e3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9f81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9fed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da14c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da2c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da379`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CFSFolder::_DiscoverLocalizedName(
        CFSFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const WCHAR *a3,
        unsigned __int16 *a4)
{
  __int64 v8; // rcx
  bool v9; // al
  __int64 (__fastcall *v10)(char *, const struct _ITEMIDLIST_RELATIVE *, __int64, LPVOID *); // r13
  HRESULT Instance; // ebx
  __int64 v12; // rdx
  HRESULT v14; // eax
  struct ICachedPrivateProfile *v15; // rdx
  __int64 v16; // rax
  void *v17; // r9
  WCHAR *v18; // rcx
  __int64 v19; // rbx
  WCHAR *v20; // rdx
  WCHAR v21; // r8
  WCHAR *v22; // rcx
  unsigned int v23; // r8d
  int v24; // eax
  struct ICachedPrivateProfile *v25; // rcx
  struct ICachedPrivateProfile *v26; // rcx
  struct ICachedPrivateProfile *v27; // rcx
  struct ICachedPrivateProfile *v28; // rcx
  struct ICachedPrivateProfile *v29; // rcx
  __int64 (__fastcall *v30)(char *, const struct _ITEMIDLIST_RELATIVE *, __int64, LPVOID *); // r13
  LPVOID v31; // rdi
  __int64 v32; // rax
  PWSTR v33; // r9
  PWSTR v34; // rcx
  __int64 v35; // rbx
  WCHAR *v36; // r8
  WCHAR v37; // dx
  WCHAR *v38; // rcx
  unsigned int v39; // r8d
  int v40; // eax
  struct ICachedPrivateProfile *v41; // rcx
  struct ICachedPrivateProfile *v42; // rcx
  struct ICachedPrivateProfile *v43; // rcx
  struct ICachedPrivateProfile *v44; // rcx
  __int64 v45; // rax
  PWSTR v46; // r9
  PWSTR v47; // rdx
  __int64 v48; // rbx
  WCHAR *v49; // r8
  WCHAR v50; // cx
  WCHAR *v51; // rdx
  unsigned int v52; // r8d
  int v53; // eax
  struct ICachedPrivateProfile *v54; // rcx
  struct ICachedPrivateProfile *v55; // rcx
  struct ICachedPrivateProfile *v56; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPathOut; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v59; // [rsp+48h] [rbp-B8h] BYREF
  struct ICachedPrivateProfile *v60; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszFirst[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *a4 = 0;
  pv = 0;
  v8 = *(unsigned int *)a3;
  v9 = (v8 & 0x400) != 0 && !(unsigned __int8)RtlIsCloudFilesPlaceholder(v8, *((unsigned int *)a3 + 9));
  if ( (*(_DWORD *)a3 & 0x10) == 0 || v9 || (*(_DWORD *)a3 & 5) == 0 )
  {
    if ( a2 )
    {
      v30 = *(__int64 (__fastcall **)(char *, const struct _ITEMIDLIST_RELATIVE *, __int64, LPVOID *))(*((_QWORD *)this + 39) + 112LL);
      pv = 0;
      Instance = v30((char *)this + 312, a2, 1, &pv);
      if ( Instance < 0 )
      {
        v12 = 1624;
        goto LABEL_10;
      }
      v31 = pv;
      v60 = 0;
      ppszPathOut = 0;
      Instance = SHCoCreateInstance(
                   0,
                   &GUID_75847177_f077_4171_bd2c_a6bb2164fbd0,
                   0,
                   &GUID_b57046bc_32e5_428a_9887_19f712b907bf,
                   (void **)&ppszPathOut);
      if ( Instance < 0 )
        goto LABEL_81;
      Instance = (*(__int64 (__fastcall **)(PWSTR, LPVOID, __int64))(*(_QWORD *)ppszPathOut + 24LL))(
                   ppszPathOut,
                   v31,
                   0x100000);
      if ( Instance >= 0 )
        Instance = (**(__int64 (__fastcall ***)(PWSTR, GUID *, struct ICachedPrivateProfile **))ppszPathOut)(
                     ppszPathOut,
                     &GUID_b57046bc_32e5_428a_9887_19f712b907bf,
                     &v60);
      (*(void (__fastcall **)(PWSTR))(*(_QWORD *)ppszPathOut + 16LL))(ppszPathOut);
      if ( Instance < 0 )
      {
LABEL_81:
        v43 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v43 + 16LL))(v43);
        }
        goto LABEL_11;
      }
      ppszPathOut = 0;
      if ( (*(int (__fastcall **)(struct ICachedPrivateProfile *, const wchar_t *, char *, _QWORD))(*(_QWORD *)v60 + 48LL))(
             v60,
             L"LocalizedFileNames",
             (char *)a3 + 44,
             0) < 0 )
        goto LABEL_78;
      v32 = 2147483646;
      v33 = ppszPathOut;
      v34 = ppszPathOut;
      v35 = 260;
      v36 = pszFirst;
      do
      {
        if ( !v32 )
          break;
        v37 = *v34;
        if ( !*v34 )
          break;
        ++v34;
        *v36++ = v37;
        --v32;
        --v35;
      }
      while ( v35 );
      v38 = v36 - 1;
      if ( v35 )
        v38 = v36;
      *v38 = 0;
      CoTaskMemFree(v33);
      if ( !v35 )
      {
LABEL_78:
        v42 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v42 + 16LL))(v42);
        }
        goto LABEL_108;
      }
      v40 = _CopyResource(pszFirst, a4, v39);
      Instance = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x65E,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\fileext.cpp",
          (const char *)(unsigned int)v40,
          2);
        v41 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v41 + 16LL))(v41);
        }
        goto LABEL_11;
      }
    }
    else
    {
      if ( (CFSFolder::_Attributes(this) & 5) == 0 )
        goto LABEL_108;
      v60 = 0;
      Instance = CFSFolder::_GetDesktopIni(this, &v60);
      if ( Instance < 0 )
      {
        v44 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v44 + 16LL))(v44);
        }
        goto LABEL_11;
      }
      ppszPathOut = 0;
      if ( (*(int (__fastcall **)(struct ICachedPrivateProfile *, const wchar_t *, char *, _QWORD))(*(_QWORD *)v60 + 48LL))(
             v60,
             L"LocalizedFileNames",
             (char *)a3 + 44,
             0) < 0 )
        goto LABEL_106;
      v45 = 2147483646;
      v46 = ppszPathOut;
      v47 = ppszPathOut;
      v48 = 260;
      v49 = pszFirst;
      do
      {
        if ( !v45 )
          break;
        v50 = *v47;
        if ( !*v47 )
          break;
        ++v47;
        *v49++ = v50;
        --v45;
        --v48;
      }
      while ( v48 );
      v51 = v49 - 1;
      if ( v48 )
        v51 = v49;
      *v51 = 0;
      CoTaskMemFree(v46);
      if ( !v48 )
      {
LABEL_106:
        v56 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v56 + 16LL))(v56);
        }
        goto LABEL_108;
      }
      v53 = _CopyResource(pszFirst, a4, v52);
      Instance = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x666,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\fileext.cpp",
          (const char *)(unsigned int)v53,
          2);
        v54 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v54 + 16LL))(v54);
        }
        goto LABEL_11;
      }
    }
    v55 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v55 + 16LL))(v55);
    }
LABEL_103:
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  v10 = *(__int64 (__fastcall **)(char *, const struct _ITEMIDLIST_RELATIVE *, __int64, LPVOID *))(*((_QWORD *)this + 39)
                                                                                                 + 112LL);
  pv = 0;
  Instance = v10((char *)this + 312, a2, 1, &pv);
  if ( Instance < 0 )
  {
    v12 = 1582;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\fileext.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
LABEL_11:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)Instance;
  }
  ppszPathOut = 0;
  v14 = PathAllocCombine((PCWSTR)pv, a3 + 22, 1u, &ppszPathOut);
  Instance = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x631,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\fileext.cpp",
      (const char *)(unsigned int)v14,
      ppv);
LABEL_16:
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    goto LABEL_11;
  }
  v60 = 0;
  Instance = SHGetCachedPrivateProfile(ppszPathOut, 0x100000, &v60);
  if ( Instance < 0 )
  {
    v15 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_16;
  }
  v59 = 0;
  if ( (*(int (__fastcall **)(struct ICachedPrivateProfile *, const wchar_t *, const WCHAR *, _QWORD))(*(_QWORD *)v60 + 48LL))(
         v60,
         L".ShellClassInfo",
         L"LocalizedResourceName",
         0) >= 0 )
  {
    v16 = 2147483646;
    v17 = v59;
    v18 = (WCHAR *)v59;
    v19 = 260;
    v20 = pszFirst;
    do
    {
      if ( !v16 )
        break;
      v21 = *v18;
      if ( !*v18 )
        break;
      ++v18;
      *v20++ = v21;
      --v16;
      --v19;
    }
    while ( v19 );
    v22 = v20 - 1;
    if ( v19 )
      v22 = v20;
    *v22 = 0;
    CoTaskMemFree(v17);
    if ( v19 )
    {
      v24 = _CopyResource(pszFirst, a4, v23);
      Instance = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x638,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\fileext.cpp",
          (const char *)(unsigned int)v24,
          2);
        v25 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v25 + 16LL))(v25);
        }
        goto LABEL_16;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalizedResourceName>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalizedResourceName>::GetImpl'::`2'::impl) )
      {
        if ( *a4 == 64 )
        {
          LODWORD(v59) = -1;
          if ( !(unsigned int)TryGetResourceStringZone(a4, (unsigned int *)&v59) || (unsigned int)v59 > 2 )
          {
            *a4 = 0;
            v26 = v60;
            if ( v60 )
            {
              v60 = 0;
              (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v26 + 16LL))(v26);
            }
LABEL_49:
            if ( ppszPathOut )
              LocalFree(ppszPathOut);
            if ( pv )
              CoTaskMemFree(pv);
            return 2147942405LL;
          }
        }
      }
      else
      {
        LODWORD(v59) = -1;
        if ( !(unsigned int)TryGetResourceStringZone(a4, (unsigned int *)&v59) || (unsigned int)v59 > 2 )
        {
          *a4 = 0;
          v28 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v28 + 16LL))(v28);
          }
          goto LABEL_49;
        }
      }
      v27 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v27 + 16LL))(v27);
      }
      if ( ppszPathOut )
        LocalFree(ppszPathOut);
      goto LABEL_103;
    }
  }
  v29 = v60;
  if ( v60 )
  {
    v60 = 0;
    (*(void (__fastcall **)(struct ICachedPrivateProfile *))(*(_QWORD *)v29 + 16LL))(v29);
  }
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
LABEL_108:
  if ( pv )
    CoTaskMemFree(pv);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800d9c10  push    rbp
0x1800d9c12  push    rbx
0x1800d9c13  push    rsi
0x1800d9c14  push    rdi
0x1800d9c15  push    r12
0x1800d9c17  push    r13
0x1800d9c19  push    r14
0x1800d9c1b  push    r15
0x1800d9c1d  lea     rbp, [rsp-188h]
0x1800d9c25  sub     rsp, 288h
0x1800d9c2c  mov     rax, cs:__security_cookie
0x1800d9c33  xor     rax, rsp
0x1800d9c36  mov     [rbp+1C0h+var_50], rax
0x1800d9c3d  mov     rsi, r9
0x1800d9c40  mov     r15, r8
0x1800d9c43  mov     r12, rdx
0x1800d9c46  mov     rbx, rcx
0x1800d9c49  xor     r14d, r14d
0x1800d9c4c  mov     [r9], r14w
0x1800d9c50  mov     edi, r14d
0x1800d9c53  mov     [rsp+2C0h+pv], r14
0x1800d9c58  mov     ecx, [r8]
0x1800d9c5b  bt      ecx, 0Ah
0x1800d9c5f  jnb     short loc_1800D9C78
0x1800d9c61  mov     edx, [r8+24h]
0x1800d9c65  call    cs:__imp_RtlIsCloudFilesPlaceholder
0x1800d9c6b  mov     rdi, [rsp+2C0h+pv]
0x1800d9c70  test    al, al
0x1800d9c72  jnz     short loc_1800D9C78
0x1800d9c74  mov     al, 1
0x1800d9c76  jmp     short loc_1800D9C7A
0x1800d9c78  xor     al, al
0x1800d9c7a  mov     ecx, [r15]
0x1800d9c7d  test    cl, 10h
0x1800d9c80  jz      loc_1800D9FC6
0x1800d9c86  test    al, al
0x1800d9c88  jnz     loc_1800D9FC6
0x1800d9c8e  test    cl, 5
0x1800d9c91  jz      loc_1800D9FC6
0x1800d9c97  lea     r14, [rbx+138h]
0x1800d9c9e  mov     rax, [r14]
0x1800d9ca1  mov     r13, [rax+70h]
0x1800d9ca5  test    rdi, rdi
0x1800d9ca8  jz      short loc_1800D9CC3
0x1800d9caa  call    cs:__imp_GetLastError
0x1800d9cb0  mov     ebx, eax
0x1800d9cb2  mov     rcx, rdi; pv
0x1800d9cb5  call    cs:__imp_CoTaskMemFree
0x1800d9cbb  mov     ecx, ebx; dwErrCode
0x1800d9cbd  call    cs:__imp_SetLastError
0x1800d9cc3  xor     edi, edi
0x1800d9cc5  mov     [rsp+2C0h+pv], rdi
0x1800d9cca  lea     r9, [rsp+2C0h+pv]
0x1800d9ccf  mov     r8d, 1
0x1800d9cd5  mov     rdx, r12
0x1800d9cd8  mov     rcx, r14
0x1800d9cdb  mov     rax, r13
0x1800d9cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ce3  mov     ebx, eax
0x1800d9ce5  test    eax, eax
0x1800d9ce7  jns     short loc_1800D9D1C
0x1800d9ce9  mov     edx, 62Eh; void *
0x1800d9cee  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800d9cf5  mov     r9d, ebx; char *
0x1800d9cf8  mov     rcx, [rbp+1C8h]; this
0x1800d9cff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9d04  nop
0x1800d9d05  mov     rcx, [rsp+2C0h+pv]; pv
0x1800d9d0a  test    rcx, rcx
0x1800d9d0d  jz      short loc_1800D9D15
0x1800d9d0f  call    cs:__imp_CoTaskMemFree
0x1800d9d15  mov     eax, ebx
0x1800d9d17  jmp     loc_1800DA384
0x1800d9d1c  mov     [rsp+2C0h+ppszPathOut], rdi
0x1800d9d21  lea     rdx, [r15+2Ch]; pszMore
0x1800d9d25  lea     r9, [rsp+2C0h+ppszPathOut]; ppszPathOut
0x1800d9d2a  mov     r8d, 1; dwFlags
0x1800d9d30  mov     rcx, [rsp+2C0h+pv]; pszPathIn
0x1800d9d35  call    cs:__imp_PathAllocCombine
0x1800d9d3b  mov     ebx, eax
0x1800d9d3d  test    eax, eax
0x1800d9d3f  jns     short loc_1800D9D6F
0x1800d9d41  mov     rcx, [rbp+1C8h]; this
0x1800d9d48  mov     r9d, eax; char *
0x1800d9d4b  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800d9d52  mov     edx, 631h; void *
0x1800d9d57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9d5c  nop
0x1800d9d5d  mov     rcx, [rsp+2C0h+ppszPathOut]; hMem
0x1800d9d62  test    rcx, rcx
0x1800d9d65  jz      short loc_1800D9D05
0x1800d9d67  call    cs:__imp_LocalFree
0x1800d9d6d  jmp     short loc_1800D9D05
0x1800d9d6f  mov     [rsp+2C0h+var_270], rdi
0x1800d9d74  lea     r8, [rsp+2C0h+var_270]
0x1800d9d79  mov     edx, 100000h
0x1800d9d7e  mov     rcx, [rsp+2C0h+ppszPathOut]
0x1800d9d83  call    ?SHGetCachedPrivateProfile@@YAJPEBGW4CACHEDPRIVATEPROFILEFLAGS@@PEAPEAUICachedPrivateProfile@@@Z; SHGetCachedPrivateProfile(ushort const *,CACHEDPRIVATEPROFILEFLAGS,ICachedPrivateProfile * *)
0x1800d9d88  mov     ebx, eax
0x1800d9d8a  test    eax, eax
0x1800d9d8c  jns     short loc_1800D9DAF
0x1800d9d8e  mov     rdx, [rsp+2C0h+var_270]
0x1800d9d93  test    rdx, rdx
0x1800d9d96  jz      short loc_1800D9DAD
0x1800d9d98  mov     [rsp+2C0h+var_270], rdi
0x1800d9d9d  mov     rcx, [rdx]
0x1800d9da0  mov     rax, [rcx+10h]
0x1800d9da4  mov     rcx, rdx
0x1800d9da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9dac  nop
0x1800d9dad  jmp     short loc_1800D9D5D
0x1800d9daf  mov     rcx, [rsp+2C0h+var_270]
0x1800d9db4  mov     [rsp+2C0h+var_278], rdi
0x1800d9db9  mov     rax, [rcx]
0x1800d9dbc  lea     rdx, [rsp+2C0h+var_278]
0x1800d9dc1  mov     [rsp+2C0h+var_298], rdx
0x1800d9dc6  mov     dword ptr [rsp+2C0h+ppv], 2; int
0x1800d9dce  xor     r9d, r9d
0x1800d9dd1  lea     r8, aLocalizedresou_0; "LocalizedResourceName"
0x1800d9dd8  lea     rdx, aShellclassinfo; ".ShellClassInfo"
0x1800d9ddf  mov     rax, [rax+30h]
0x1800d9de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9de8  test    eax, eax
0x1800d9dea  js      loc_1800D9F91
0x1800d9df0  mov     eax, 7FFFFFFEh
0x1800d9df5  mov     r9, [rsp+2C0h+var_278]
0x1800d9dfa  mov     rcx, r9
0x1800d9dfd  mov     ebx, 104h
0x1800d9e02  lea     rdx, [rsp+2C0h+pszFirst]
0x1800d9e07  test    rax, rax
0x1800d9e0a  jz      short loc_1800D9E2B
0x1800d9e0c  movzx   r8d, word ptr [rcx]
0x1800d9e10  test    r8w, r8w
0x1800d9e14  jz      short loc_1800D9E2B
0x1800d9e16  add     rcx, 2
0x1800d9e1a  mov     [rdx], r8w
0x1800d9e1e  add     rdx, 2
0x1800d9e22  dec     rax
0x1800d9e25  sub     rbx, 1
0x1800d9e29  jnz     short loc_1800D9E07
0x1800d9e2b  lea     rcx, [rdx-2]
0x1800d9e2f  test    rbx, rbx
0x1800d9e32  cmovnz  rcx, rdx
0x1800d9e36  mov     [rcx], di
0x1800d9e39  mov     rcx, r9; pv
0x1800d9e3c  call    cs:__imp_CoTaskMemFree
0x1800d9e42  test    rbx, rbx
0x1800d9e45  jz      loc_1800D9F91
0x1800d9e4b  mov     rdx, rsi; unsigned __int16 *
0x1800d9e4e  lea     rcx, [rsp+2C0h+pszFirst]; pszFirst
0x1800d9e53  call    ?_CopyResource@@YAJPEAG0I@Z; _CopyResource(ushort *,ushort *,uint)
0x1800d9e58  mov     ebx, eax
0x1800d9e5a  test    eax, eax
0x1800d9e5c  jns     short loc_1800D9E9B
0x1800d9e5e  mov     rcx, [rbp+1C8h]; this
0x1800d9e65  mov     r9d, eax; char *
0x1800d9e68  lea     r8, aOnecoreuapShel_65; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800d9e6f  mov     edx, 638h; void *
0x1800d9e74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9e79  nop
0x1800d9e7a  mov     rcx, [rsp+2C0h+var_270]
0x1800d9e7f  test    rcx, rcx
0x1800d9e82  jz      short loc_1800D9E96
0x1800d9e84  mov     [rsp+2C0h+var_270], rdi
0x1800d9e89  mov     rax, [rcx]
0x1800d9e8c  mov     rax, [rax+10h]
0x1800d9e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9e95  nop
0x1800d9e96  jmp     loc_1800D9D5D
0x1800d9e9b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LocalizedResourceName@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalizedResourceName@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalizedResourceName> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalizedResourceName>::GetImpl(void)'::`2'::impl
0x1800d9ea2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalizedResourceName@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalizedResourceName>::__private_IsEnabled(void)
0x1800d9ea7  test    al, al
0x1800d9ea9  jz      short loc_1800D9EF2
0x1800d9eab  cmp     word ptr [rsi], 40h ; '@'
0x1800d9eaf  jnz     short loc_1800D9F12
0x1800d9eb1  mov     dword ptr [rsp+2C0h+var_278], 0FFFFFFFFh
0x1800d9eb9  lea     rdx, [rsp+2C0h+var_278]; unsigned int *
0x1800d9ebe  mov     rcx, rsi; unsigned __int16 *
0x1800d9ec1  call    ?TryGetResourceStringZone@@YAHPEBGPEAK@Z; TryGetResourceStringZone(ushort const *,ulong *)
0x1800d9ec6  test    eax, eax
0x1800d9ec8  jz      short loc_1800D9ED1
0x1800d9eca  cmp     dword ptr [rsp+2C0h+var_278], 2
0x1800d9ecf  jbe     short loc_1800D9F12
0x1800d9ed1  mov     [rsi], di
0x1800d9ed4  mov     rcx, [rsp+2C0h+var_270]
0x1800d9ed9  test    rcx, rcx
0x1800d9edc  jz      short loc_1800D9EF0
0x1800d9ede  mov     [rsp+2C0h+var_270], rdi
0x1800d9ee3  mov     rax, [rcx]
0x1800d9ee6  mov     rax, [rax+10h]
0x1800d9eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9eef  nop
0x1800d9ef0  jmp     short loc_1800D9F66
0x1800d9ef2  mov     dword ptr [rsp+2C0h+var_278], 0FFFFFFFFh
0x1800d9efa  lea     rdx, [rsp+2C0h+var_278]; unsigned int *
0x1800d9eff  mov     rcx, rsi; unsigned __int16 *
0x1800d9f02  call    ?TryGetResourceStringZone@@YAHPEBGPEAK@Z; TryGetResourceStringZone(ushort const *,ulong *)
0x1800d9f07  test    eax, eax
0x1800d9f09  jz      short loc_1800D9F47
0x1800d9f0b  cmp     dword ptr [rsp+2C0h+var_278], 2
0x1800d9f10  ja      short loc_1800D9F47
0x1800d9f12  mov     rcx, [rsp+2C0h+var_270]
0x1800d9f17  test    rcx, rcx
0x1800d9f1a  jz      short loc_1800D9F2E
0x1800d9f1c  mov     [rsp+2C0h+var_270], rdi
0x1800d9f21  mov     rax, [rcx]
0x1800d9f24  mov     rax, [rax+10h]
0x1800d9f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f2d  nop
0x1800d9f2e  mov     rcx, [rsp+2C0h+ppszPathOut]; hMem
0x1800d9f33  test    rcx, rcx
0x1800d9f36  jz      loc_1800DA33F
0x1800d9f3c  call    cs:__imp_LocalFree
0x1800d9f42  jmp     loc_1800DA33F
0x1800d9f47  mov     [rsi], di
0x1800d9f4a  mov     rcx, [rsp+2C0h+var_270]
0x1800d9f4f  test    rcx, rcx
0x1800d9f52  jz      short loc_1800D9F66
0x1800d9f54  mov     [rsp+2C0h+var_270], rdi
0x1800d9f59  mov     rax, [rcx]
0x1800d9f5c  mov     rax, [rax+10h]
0x1800d9f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f65  nop
0x1800d9f66  mov     rcx, [rsp+2C0h+ppszPathOut]; hMem
0x1800d9f6b  test    rcx, rcx
0x1800d9f6e  jz      short loc_1800D9F77
0x1800d9f70  call    cs:__imp_LocalFree
0x1800d9f76  nop
0x1800d9f77  mov     rcx, [rsp+2C0h+pv]; pv
0x1800d9f7c  test    rcx, rcx
0x1800d9f7f  jz      short loc_1800D9F87
0x1800d9f81  call    cs:__imp_CoTaskMemFree
0x1800d9f87  mov     eax, 80070005h
0x1800d9f8c  jmp     loc_1800DA384
0x1800d9f91  mov     rcx, [rsp+2C0h+var_270]
0x1800d9f96  test    rcx, rcx
0x1800d9f99  jz      short loc_1800D9FAD
0x1800d9f9b  mov     [rsp+2C0h+var_270], rdi
0x1800d9fa0  mov     rax, [rcx]
0x1800d9fa3  mov     rax, [rax+10h]
0x1800d9fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9fac  nop
0x1800d9fad  mov     rcx, [rsp+2C0h+ppszPathOut]; hMem
0x1800d9fb2  test    rcx, rcx
0x1800d9fb5  jz      loc_1800DA36F
0x1800d9fbb  call    cs:__imp_LocalFree
0x1800d9fc1  jmp     loc_1800DA36F
0x1800d9fc6  test    r12, r12
0x1800d9fc9  jz      loc_1800DA1EE
0x1800d9fcf  lea     r14, [rbx+138h]
0x1800d9fd6  mov     rax, [r14]
0x1800d9fd9  mov     r13, [rax+70h]
0x1800d9fdd  test    rdi, rdi
0x1800d9fe0  jz      short loc_1800D9FFB
0x1800d9fe2  call    cs:__imp_GetLastError
0x1800d9fe8  mov     ebx, eax
0x1800d9fea  mov     rcx, rdi; pv
0x1800d9fed  call    cs:__imp_CoTaskMemFree
0x1800d9ff3  mov     ecx, ebx; dwErrCode
0x1800d9ff5  call    cs:__imp_SetLastError
0x1800d9ffb  mov     [rsp+2C0h+pv], 0
0x1800da004  lea     r9, [rsp+2C0h+pv]
0x1800da009  mov     r8d, 1
0x1800da00f  mov     rdx, r12
0x1800da012  mov     rcx, r14
0x1800da015  mov     rax, r13
0x1800da018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da01d  mov     ebx, eax
0x1800da01f  test    eax, eax
0x1800da021  jns     short loc_1800DA02D
0x1800da023  mov     edx, 658h
0x1800da028  jmp     loc_1800D9CEE
0x1800da02d  mov     rdi, [rsp+2C0h+pv]
0x1800da032  xor     r14d, r14d
0x1800da035  mov     [rsp+2C0h+var_270], r14
0x1800da03a  mov     [rsp+2C0h+ppszPathOut], r14
0x1800da03f  lea     rax, [rsp+2C0h+ppszPathOut]
0x1800da044  mov     [rsp+2C0h+ppv], rax; ppv
0x1800da049  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x1800da050  xor     r8d, r8d; pUnkOuter
0x1800da053  lea     rdx, _GUID_75847177_f077_4171_bd2c_a6bb2164fbd0; pclsid
0x1800da05a  xor     ecx, ecx; pszCLSID
0x1800da05c  call    cs:__imp_SHCoCreateInstance
0x1800da062  mov     ebx, eax
0x1800da064  test    eax, eax
0x1800da066  js      loc_1800DA1CD
0x1800da06c  mov     rcx, [rsp+2C0h+ppszPathOut]
0x1800da071  mov     rax, [rcx]
0x1800da074  mov     r8d, 100000h
0x1800da07a  mov     rdx, rdi
0x1800da07d  mov     rax, [rax+18h]
0x1800da081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da086  mov     ebx, eax
0x1800da088  test    eax, eax
0x1800da08a  js      short loc_1800DA0AA
0x1800da08c  mov     rcx, [rsp+2C0h+ppszPathOut]
0x1800da091  mov     rax, [rcx]
0x1800da094  lea     r8, [rsp+2C0h+var_270]
0x1800da099  lea     rdx, _GUID_b57046bc_32e5_428a_9887_19f712b907bf
0x1800da0a0  mov     rax, [rax]
  ... truncated ...
```
