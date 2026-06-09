# CFSFolder::_DiscoverLocalizedName(_ITEMIDLIST_RELATIVE const *,tagWIN32_FIND_DATA_EX const *,ushort *,uint)

- ea: `0x18006ba00`
- end: `0x18006c20c`
- name: `?_DiscoverLocalizedName@CFSFolder@@IEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBUtagWIN32_FIND_DATA_EX@@PEAGI@Z`
- size: `2060`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct tagWIN32_FIND_DATA_EX *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006a8c0`

## callees

- `0x180038f50`
- `0x18006ba00`
- `0x1800aba40`
- `0x1800bb450`
- `0x180201b50`
- `0x180202c40`
- `0x1803b1f60`
- `0x180562f60`
- `0x180563118`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006babf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006be39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006babf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006be39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006baa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006baa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006be1a`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x18006ba55`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x18006ba55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bd5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bd96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bded`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bd5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bd96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bded`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18006bb43`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18006bb43`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x18006bea6`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x18006bea6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bb17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bc56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bdad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006be2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bf9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c1a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c1d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bb17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bc56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bdad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006be2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bf9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c1a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006c1d7`

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
0x18006ba00  push    rbp
0x18006ba02  push    rbx
0x18006ba03  push    rsi
0x18006ba04  push    rdi
0x18006ba05  push    r12
0x18006ba07  push    r13
0x18006ba09  push    r14
0x18006ba0b  push    r15
0x18006ba0d  lea     rbp, [rsp-188h]
0x18006ba15  sub     rsp, 288h
0x18006ba1c  mov     rax, cs:__security_cookie
0x18006ba23  xor     rax, rsp
0x18006ba26  mov     [rbp+1C0h+var_50], rax
0x18006ba2d  mov     rsi, r9
0x18006ba30  mov     r15, r8
0x18006ba33  mov     r12, rdx
0x18006ba36  mov     rbx, rcx
0x18006ba39  xor     r14d, r14d
0x18006ba3c  mov     [r9], r14w
0x18006ba40  mov     edi, r14d
0x18006ba43  mov     [rsp+2C0h+pv], r14
0x18006ba48  mov     ecx, [r8]
0x18006ba4b  bt      ecx, 0Ah
0x18006ba4f  jnb     short loc_18006BA6E
0x18006ba51  mov     edx, [r8+24h]
0x18006ba55  call    cs:__imp_RtlIsCloudFilesPlaceholder
0x18006ba5c  nop     dword ptr [rax+rax+00h]
0x18006ba61  mov     rdi, [rsp+2C0h+pv]
0x18006ba66  test    al, al
0x18006ba68  jnz     short loc_18006BA6E
0x18006ba6a  mov     al, 1
0x18006ba6c  jmp     short loc_18006BA70
0x18006ba6e  xor     al, al
0x18006ba70  mov     ecx, [r15]
0x18006ba73  test    cl, 10h
0x18006ba76  jz      loc_18006BDFE
0x18006ba7c  test    al, al
0x18006ba7e  jnz     loc_18006BDFE
0x18006ba84  test    cl, 5
0x18006ba87  jz      loc_18006BDFE
0x18006ba8d  lea     r14, [rbx+138h]
0x18006ba94  mov     rax, [r14]
0x18006ba97  mov     r13, [rax+70h]
0x18006ba9b  test    rdi, rdi
0x18006ba9e  jz      short loc_18006BACB
0x18006baa0  call    cs:__imp_GetLastError
0x18006baa7  nop     dword ptr [rax+rax+00h]
0x18006baac  mov     ebx, eax
0x18006baae  mov     rcx, rdi; pv
0x18006bab1  call    cs:__imp_CoTaskMemFree
0x18006bab8  nop     dword ptr [rax+rax+00h]
0x18006babd  mov     ecx, ebx; dwErrCode
0x18006babf  call    cs:__imp_SetLastError
0x18006bac6  nop     dword ptr [rax+rax+00h]
0x18006bacb  xor     edi, edi
0x18006bacd  mov     [rsp+2C0h+pv], rdi
0x18006bad2  lea     r9, [rsp+2C0h+pv]
0x18006bad7  mov     r8d, 1
0x18006badd  mov     rdx, r12
0x18006bae0  mov     rcx, r14
0x18006bae3  mov     rax, r13
0x18006bae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006baeb  mov     ebx, eax
0x18006baed  test    eax, eax
0x18006baef  jns     short loc_18006BB2A
0x18006baf1  mov     edx, 62Eh; void *
0x18006baf6  lea     r8, aOnecoreuapShel_66; "onecoreuap\\shell\\windows.storage\\fil"...
0x18006bafd  mov     r9d, ebx; char *
0x18006bb00  mov     rcx, [rbp+1C8h]; this
0x18006bb07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bb0c  nop
0x18006bb0d  mov     rcx, [rsp+2C0h+pv]; pv
0x18006bb12  test    rcx, rcx
0x18006bb15  jz      short loc_18006BB23
0x18006bb17  call    cs:__imp_CoTaskMemFree
0x18006bb1e  nop     dword ptr [rax+rax+00h]
0x18006bb23  mov     eax, ebx
0x18006bb25  jmp     loc_18006C1E8
0x18006bb2a  mov     [rsp+2C0h+ppszPathOut], rdi
0x18006bb2f  lea     rdx, [r15+2Ch]; pszMore
0x18006bb33  lea     r9, [rsp+2C0h+ppszPathOut]; ppszPathOut
0x18006bb38  mov     r8d, 1; dwFlags
0x18006bb3e  mov     rcx, [rsp+2C0h+pv]; pszPathIn
0x18006bb43  call    cs:__imp_PathAllocCombine
0x18006bb4a  nop     dword ptr [rax+rax+00h]
0x18006bb4f  mov     ebx, eax
0x18006bb51  test    eax, eax
0x18006bb53  jns     short loc_18006BB89
0x18006bb55  mov     rcx, [rbp+1C8h]; this
0x18006bb5c  mov     r9d, eax; char *
0x18006bb5f  lea     r8, aOnecoreuapShel_66; "onecoreuap\\shell\\windows.storage\\fil"...
0x18006bb66  mov     edx, 631h; void *
0x18006bb6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bb70  nop
0x18006bb71  mov     rcx, [rsp+2C0h+ppszPathOut]; hMem
0x18006bb76  test    rcx, rcx
0x18006bb79  jz      short loc_18006BB0D
0x18006bb7b  call    cs:__imp_LocalFree
0x18006bb82  nop     dword ptr [rax+rax+00h]
0x18006bb87  jmp     short loc_18006BB0D
0x18006bb89  mov     [rsp+2C0h+var_270], rdi
0x18006bb8e  lea     r8, [rsp+2C0h+var_270]
0x18006bb93  mov     edx, 100000h
0x18006bb98  mov     rcx, [rsp+2C0h+ppszPathOut]
0x18006bb9d  call    ?SHGetCachedPrivateProfile@@YAJPEBGW4CACHEDPRIVATEPROFILEFLAGS@@PEAPEAUICachedPrivateProfile@@@Z; SHGetCachedPrivateProfile(ushort const *,CACHEDPRIVATEPROFILEFLAGS,ICachedPrivateProfile * *)
0x18006bba2  mov     ebx, eax
0x18006bba4  test    eax, eax
0x18006bba6  jns     short loc_18006BBC9
0x18006bba8  mov     rdx, [rsp+2C0h+var_270]
0x18006bbad  test    rdx, rdx
0x18006bbb0  jz      short loc_18006BBC7
0x18006bbb2  mov     [rsp+2C0h+var_270], rdi
0x18006bbb7  mov     rcx, [rdx]
0x18006bbba  mov     rax, [rcx+10h]
0x18006bbbe  mov     rcx, rdx
0x18006bbc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbc6  nop
0x18006bbc7  jmp     short loc_18006BB71
0x18006bbc9  mov     rcx, [rsp+2C0h+var_270]
0x18006bbce  mov     [rsp+2C0h+var_278], rdi
0x18006bbd3  mov     rax, [rcx]
0x18006bbd6  lea     rdx, [rsp+2C0h+var_278]
0x18006bbdb  mov     [rsp+2C0h+var_298], rdx
0x18006bbe0  mov     dword ptr [rsp+2C0h+ppv], 2; int
0x18006bbe8  xor     r9d, r9d
0x18006bbeb  lea     r8, propName; "LocalizedResourceName"
0x18006bbf2  lea     rdx, aShellclassinfo; ".ShellClassInfo"
0x18006bbf9  mov     rax, [rax+30h]
0x18006bbfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc02  test    eax, eax
0x18006bc04  js      loc_18006BDC3
0x18006bc0a  mov     eax, 7FFFFFFEh
0x18006bc0f  mov     r9, [rsp+2C0h+var_278]
0x18006bc14  mov     rcx, r9
0x18006bc17  mov     ebx, 104h
0x18006bc1c  lea     rdx, [rsp+2C0h+pszFirst]
0x18006bc21  test    rax, rax
0x18006bc24  jz      short loc_18006BC45
0x18006bc26  movzx   r8d, word ptr [rcx]
0x18006bc2a  test    r8w, r8w
0x18006bc2e  jz      short loc_18006BC45
0x18006bc30  add     rcx, 2
0x18006bc34  mov     [rdx], r8w
0x18006bc38  add     rdx, 2
0x18006bc3c  dec     rax
0x18006bc3f  sub     rbx, 1
0x18006bc43  jnz     short loc_18006BC21
0x18006bc45  lea     rcx, [rdx-2]
0x18006bc49  test    rbx, rbx
0x18006bc4c  cmovnz  rcx, rdx
0x18006bc50  mov     [rcx], di
0x18006bc53  mov     rcx, r9; pv
0x18006bc56  call    cs:__imp_CoTaskMemFree
0x18006bc5d  nop     dword ptr [rax+rax+00h]
0x18006bc62  test    rbx, rbx
0x18006bc65  jz      loc_18006BDC3
0x18006bc6b  mov     rdx, rsi; unsigned __int16 *
0x18006bc6e  lea     rcx, [rsp+2C0h+pszFirst]; pszFirst
0x18006bc73  call    ?_CopyResource@@YAJPEAG0I@Z; _CopyResource(ushort *,ushort *,uint)
0x18006bc78  mov     ebx, eax
0x18006bc7a  test    eax, eax
0x18006bc7c  jns     short loc_18006BCBB
0x18006bc7e  mov     rcx, [rbp+1C8h]; this
0x18006bc85  mov     r9d, eax; char *
0x18006bc88  lea     r8, aOnecoreuapShel_66; "onecoreuap\\shell\\windows.storage\\fil"...
0x18006bc8f  mov     edx, 638h; void *
0x18006bc94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bc99  nop
0x18006bc9a  mov     rcx, [rsp+2C0h+var_270]
0x18006bc9f  test    rcx, rcx
0x18006bca2  jz      short loc_18006BCB6
0x18006bca4  mov     [rsp+2C0h+var_270], rdi
0x18006bca9  mov     rax, [rcx]
0x18006bcac  mov     rax, [rax+10h]
0x18006bcb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bcb5  nop
0x18006bcb6  jmp     loc_18006BB71
0x18006bcbb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LocalizedResourceName@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalizedResourceName@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalizedResourceName> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LocalizedResourceName>::GetImpl(void)'::`2'::impl
0x18006bcc2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LocalizedResourceName@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LocalizedResourceName>::__private_IsEnabled(void)
0x18006bcc7  test    al, al
0x18006bcc9  jz      short loc_18006BD12
0x18006bccb  cmp     word ptr [rsi], 40h ; '@'
0x18006bccf  jnz     short loc_18006BD32
0x18006bcd1  mov     dword ptr [rsp+2C0h+var_278], 0FFFFFFFFh
0x18006bcd9  lea     rdx, [rsp+2C0h+var_278]; unsigned int *
0x18006bcde  mov     rcx, rsi; unsigned __int16 *
0x18006bce1  call    ?TryGetResourceStringZone@@YAHPEBGPEAK@Z; TryGetResourceStringZone(ushort const *,ulong *)
0x18006bce6  test    eax, eax
0x18006bce8  jz      short loc_18006BCF1
0x18006bcea  cmp     dword ptr [rsp+2C0h+var_278], 2
0x18006bcef  jbe     short loc_18006BD32
0x18006bcf1  mov     [rsi], di
0x18006bcf4  mov     rcx, [rsp+2C0h+var_270]
0x18006bcf9  test    rcx, rcx
0x18006bcfc  jz      short loc_18006BD10
0x18006bcfe  mov     [rsp+2C0h+var_270], rdi
0x18006bd03  mov     rax, [rcx]
0x18006bd06  mov     rax, [rax+10h]
0x18006bd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd0f  nop
0x18006bd10  jmp     short loc_18006BD8C
0x18006bd12  mov     dword ptr [rsp+2C0h+var_278], 0FFFFFFFFh
0x18006bd1a  lea     rdx, [rsp+2C0h+var_278]; unsigned int *
0x18006bd1f  mov     rcx, rsi; unsigned __int16 *
0x18006bd22  call    ?TryGetResourceStringZone@@YAHPEBGPEAK@Z; TryGetResourceStringZone(ushort const *,ulong *)
0x18006bd27  test    eax, eax
0x18006bd29  jz      short loc_18006BD6D
0x18006bd2b  cmp     dword ptr [rsp+2C0h+var_278], 2
0x18006bd30  ja      short loc_18006BD6D
0x18006bd32  mov     rcx, [rsp+2C0h+var_270]
0x18006bd37  test    rcx, rcx
0x18006bd3a  jz      short loc_18006BD4E
0x18006bd3c  mov     [rsp+2C0h+var_270], rdi
0x18006bd41  mov     rax, [rcx]
0x18006bd44  mov     rax, [rax+10h]
0x18006bd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd4d  nop
0x18006bd4e  mov     rcx, [rsp+2C0h+ppszPathOut]; hMem
0x18006bd53  test    rcx, rcx
0x18006bd56  jz      loc_18006C197
0x18006bd5c  call    cs:__imp_LocalFree
0x18006bd63  nop     dword ptr [rax+rax+00h]
0x18006bd68  jmp     loc_18006C197
0x18006bd6d  mov     [rsi], di
0x18006bd70  mov     rcx, [rsp+2C0h+var_270]
0x18006bd75  test    rcx, rcx
0x18006bd78  jz      short loc_18006BD8C
0x18006bd7a  mov     [rsp+2C0h+var_270], rdi
0x18006bd7f  mov     rax, [rcx]
0x18006bd82  mov     rax, [rax+10h]
0x18006bd86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd8b  nop
0x18006bd8c  mov     rcx, [rsp+2C0h+ppszPathOut]; hMem
0x18006bd91  test    rcx, rcx
0x18006bd94  jz      short loc_18006BDA3
0x18006bd96  call    cs:__imp_LocalFree
0x18006bd9d  nop     dword ptr [rax+rax+00h]
0x18006bda2  nop
0x18006bda3  mov     rcx, [rsp+2C0h+pv]; pv
0x18006bda8  test    rcx, rcx
0x18006bdab  jz      short loc_18006BDB9
0x18006bdad  call    cs:__imp_CoTaskMemFree
0x18006bdb4  nop     dword ptr [rax+rax+00h]
0x18006bdb9  mov     eax, 80070005h
0x18006bdbe  jmp     loc_18006C1E8
0x18006bdc3  mov     rcx, [rsp+2C0h+var_270]
0x18006bdc8  test    rcx, rcx
0x18006bdcb  jz      short loc_18006BDDF
0x18006bdcd  mov     [rsp+2C0h+var_270], rdi
0x18006bdd2  mov     rax, [rcx]
0x18006bdd5  mov     rax, [rax+10h]
0x18006bdd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bdde  nop
0x18006bddf  mov     rcx, [rsp+2C0h+ppszPathOut]; hMem
0x18006bde4  test    rcx, rcx
0x18006bde7  jz      loc_18006C1CD
0x18006bded  call    cs:__imp_LocalFree
0x18006bdf4  nop     dword ptr [rax+rax+00h]
0x18006bdf9  jmp     loc_18006C1CD
0x18006bdfe  test    r12, r12
0x18006be01  jz      loc_18006C044
0x18006be07  lea     r14, [rbx+138h]
0x18006be0e  mov     rax, [r14]
0x18006be11  mov     r13, [rax+70h]
0x18006be15  test    rdi, rdi
0x18006be18  jz      short loc_18006BE45
0x18006be1a  call    cs:__imp_GetLastError
0x18006be21  nop     dword ptr [rax+rax+00h]
0x18006be26  mov     ebx, eax
0x18006be28  mov     rcx, rdi; pv
0x18006be2b  call    cs:__imp_CoTaskMemFree
0x18006be32  nop     dword ptr [rax+rax+00h]
0x18006be37  mov     ecx, ebx; dwErrCode
0x18006be39  call    cs:__imp_SetLastError
0x18006be40  nop     dword ptr [rax+rax+00h]
0x18006be45  mov     [rsp+2C0h+pv], 0
0x18006be4e  lea     r9, [rsp+2C0h+pv]
0x18006be53  mov     r8d, 1
0x18006be59  mov     rdx, r12
0x18006be5c  mov     rcx, r14
0x18006be5f  mov     rax, r13
0x18006be62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be67  mov     ebx, eax
0x18006be69  test    eax, eax
0x18006be6b  jns     short loc_18006BE77
0x18006be6d  mov     edx, 658h
0x18006be72  jmp     loc_18006BAF6
0x18006be77  mov     rdi, [rsp+2C0h+pv]
0x18006be7c  xor     r14d, r14d
0x18006be7f  mov     [rsp+2C0h+var_270], r14
0x18006be84  mov     [rsp+2C0h+ppszPathOut], r14
0x18006be89  lea     rax, [rsp+2C0h+ppszPathOut]
0x18006be8e  mov     [rsp+2C0h+ppv], rax; ppv
0x18006be93  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x18006be9a  xor     r8d, r8d; pUnkOuter
0x18006be9d  lea     rdx, _GUID_75847177_f077_4171_bd2c_a6bb2164fbd0; pclsid
0x18006bea4  xor     ecx, ecx; pszCLSID
0x18006bea6  call    cs:__imp_SHCoCreateInstance
0x18006bead  nop     dword ptr [rax+rax+00h]
0x18006beb2  mov     ebx, eax
  ... truncated ...
```
