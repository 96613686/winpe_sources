# CFSFolder::_CreateIDListFromName(ushort const *,ulong,int,IBindCtx *,_ITEMID_CHILD * *)

- ea: `0x1800f1680`
- end: `0x1800f1bb1`
- name: `?_CreateIDListFromName@CFSFolder@@IEAAJPEBGKHPEAUIBindCtx@@PEAPEAU_ITEMID_CHILD@@@Z`
- size: `1329`
- prototype: `__int64 __usercall@<rax>(CFSFolder *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, int@<r9d>, struct IBindCtx *, struct _ITEMID_CHILD **)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f1da0`
- `0x18052abe0`

## callees

- `0x180035d30`
- `0x180038f50`
- `0x180063050`
- `0x18006a8c0`
- `0x1800aeb90`
- `0x1800f0b80`
- `0x1800f1680`
- `0x1800f2df0`
- `0x1800f2ebc`
- `0x1800f3080`
- `0x18015a150`
- `0x1801cff34`
- `0x180209948`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f17f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1b04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1b5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f17f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1b04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f1b5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800f1a79`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800f1a79`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f1724`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f1724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f18f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1acf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1744`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f18f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1acf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f1b38`

## pseudocode

```c
__int64 __fastcall CFSFolder::_CreateIDListFromName(
        CFSFolder *this,
        unsigned __int16 *a2,
        int a3,
        int a4,
        struct IBindCtx *a5,
        struct _ITEMID_CHILD **a6)
{
  size_t *v10; // r8
  const WCHAR *v11; // rcx
  HRESULT v12; // eax
  int DataForPath; // edi
  unsigned int v14; // esi
  int v15; // edi
  int v16; // edi
  PWSTR v17; // rcx
  BOOL v18; // eax
  struct IBindCtxVtbl *lpVtbl; // rax
  char v20; // di
  unsigned int v21; // esi
  enum FOLDER_ENUM_MODE FolderEnumMode; // eax
  unsigned __int16 **v24; // rax
  int FolderPath; // eax
  DWORD TickCount; // eax
  size_t v27; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPathOut; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v31[11]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[290]; // [rsp+9Ch] [rbp-64h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  *a6 = 0;
  memset_0(v31, 0, 0x268u);
  if ( (unsigned int)PathIsInvalidW(a2) )
  {
    DataForPath = -2147023696;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x901,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)0x800704B0LL,
      v27);
    return (unsigned int)DataForPath;
  }
  if ( a3 != -1 )
  {
    StringCopyWorkerW(pszDest, 0x104u, v10, a2, v27);
    v31[0] = a3;
    goto LABEL_15;
  }
  v11 = (const WCHAR *)*((_QWORD *)this + 56);
  ppszPathOut = 0;
  pv = 0;
  if ( !v11 )
  {
    v24 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
    FolderPath = CFSFolder::GetFolderPath(this, v24);
    DataForPath = FolderPath;
    if ( FolderPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E6,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)FolderPath,
        v27);
      if ( pv )
        CoTaskMemFree(pv);
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x906,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)DataForPath,
        v27);
      v17 = ppszPathOut;
      if ( ppszPathOut )
        goto LABEL_55;
      return (unsigned int)DataForPath;
    }
    v11 = (const WCHAR *)pv;
  }
  v12 = PathAllocCombine(v11, a2, 1u, &ppszPathOut);
  DataForPath = v12;
  if ( v12 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v12,
      v27);
  if ( pv )
    CoTaskMemFree(pv);
  if ( DataForPath < 0 )
    goto LABEL_50;
  v30[0] = 0;
  v14 = 0;
  pv = 0;
  v15 = -2147467262;
  if ( a5
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))a5->lpVtbl->GetObjectParam)(
         a5,
         L"bind context timeout value",
         &pv) >= 0 )
  {
    v16 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, _QWORD *))pv)(
            pv,
            &GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000,
            v30);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    if ( v16 < 0 )
      goto LABEL_12;
    pv = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, __int64, __int64))(*(_QWORD *)v30[0] + 48LL))(v30[0], &pv, 1, 8);
    if ( v15 >= 0 )
    {
      TickCount = GetTickCount();
      if ( TickCount - (unsigned int)pv <= HIDWORD(pv) )
        v14 = HIDWORD(pv) - TickCount + (_DWORD)pv - 1;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30[0] + 16LL))(v30[0]);
  }
  if ( v15 < 0 || !(unsigned int)CFSFolder::_IsNetFolder(this) )
  {
LABEL_12:
    DataForPath = GetFindDataForPath(ppszPathOut);
    if ( DataForPath < 0 )
    {
      v17 = ppszPathOut;
      if ( ppszPathOut )
        goto LABEL_55;
      return (unsigned int)DataForPath;
    }
    goto LABEL_31;
  }
  DataForPath = GetFindDataForPathWithTimeout(ppszPathOut, a4, v14, (struct tagWIN32_FIND_DATA_EX *)v31);
  if ( DataForPath >= 0 )
  {
LABEL_31:
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
LABEL_15:
    v18 = 0;
    if ( a5 )
    {
      v30[1] = 0;
      lpVtbl = a5->lpVtbl;
      v30[0] = 16;
      v18 = ((int (__fastcall *)(struct IBindCtx *, _QWORD *))lpVtbl->GetBindOptions)(a5, v30) >= 0
         && HIDWORD(v30[0]) == 2;
    }
    ppszPathOut = 0;
    v20 = 1;
    if ( !v18 )
      v20 = 7;
    v21 = -1091633152;
    if ( (v31[0] & 0x10) == 0 && a5 )
    {
      if ( (int)_BindCtx_GetValue<unsigned short *>(a5, L"ExplicitProgid", &ppszPathOut) >= 0 )
      {
        v21 = -1091633126;
        pv = 0;
        goto LABEL_23;
      }
      ppszPathOut = 0;
      if ( (int)_BindCtx_GetValue<unsigned short *>(a5, L"ExplicitAssociationApp", &ppszPathOut) >= 0 )
      {
        v21 = -1091633125;
        pv = 0;
        goto LABEL_23;
      }
    }
    pv = 0;
    if ( !a5 )
    {
LABEL_25:
      FolderEnumMode = BindCtx_GetFolderEnumMode(a5);
      DataForPath = CFSFolder::_CreateIDList(
                      this,
                      (__int64)v31,
                      0,
                      0,
                      (__int64)ppszPathOut,
                      v21,
                      v20,
                      FolderEnumMode,
                      a6);
      if ( DataForPath >= 0 )
      {
        if ( ppszPathOut )
        {
          DataForPath = _BindCtx_SetValue<int>(a5, L"ExplicitAssociationSuccessful", 1);
          if ( DataForPath < 0 )
          {
            CoTaskMemFree(*a6);
            *a6 = 0;
          }
        }
      }
      CoTaskMemFree(ppszPathOut);
      return (unsigned int)DataForPath;
    }
LABEL_23:
    if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID *))a5->lpVtbl->GetObjectParam)(
           a5,
           L"Win7FileSystemIdList",
           &pv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      v20 |= 8u;
    }
    goto LABEL_25;
  }
  v17 = ppszPathOut;
  if ( ppszPathOut )
LABEL_55:
    LocalFree(v17);
  return (unsigned int)DataForPath;
}

```

## disassembly

```asm
0x1800f1680  mov     [rsp-8+arg_10], rbx
0x1800f1685  push    rbp
0x1800f1686  push    rsi
0x1800f1687  push    rdi
0x1800f1688  push    r12
0x1800f168a  push    r13
0x1800f168c  push    r14
0x1800f168e  push    r15
0x1800f1690  lea     rbp, [rsp-1F0h]
0x1800f1698  sub     rsp, 2F0h
0x1800f169f  mov     rax, cs:__security_cookie
0x1800f16a6  xor     rax, rsp
0x1800f16a9  mov     [rbp+220h+var_40], rax
0x1800f16b0  mov     r12, [rbp+220h+arg_28]
0x1800f16b7  mov     edi, r8d
0x1800f16ba  mov     rbx, [rbp+220h+arg_20]
0x1800f16c1  mov     rsi, rdx
0x1800f16c4  mov     r15, rcx
0x1800f16c7  xor     r13d, r13d
0x1800f16ca  xor     edx, edx; Val
0x1800f16cc  lea     rcx, [rsp+320h+var_2B0]; void *
0x1800f16d1  mov     r8d, 268h; Size
0x1800f16d7  mov     [r12], r13
0x1800f16db  mov     r14d, r9d
0x1800f16de  call    memset_0
0x1800f16e3  mov     rcx, rsi; unsigned __int16 *
0x1800f16e6  call    PathIsInvalidW
0x1800f16eb  test    eax, eax
0x1800f16ed  jnz     loc_1800F1B6C
0x1800f16f3  cmp     edi, 0FFFFFFFFh
0x1800f16f6  jnz     loc_1800F1A5F
0x1800f16fc  mov     rcx, [r15+1C0h]; pszPathIn
0x1800f1703  mov     [rsp+320h+ppszPathOut], r13
0x1800f1708  mov     [rsp+320h+pv], r13
0x1800f170d  test    rcx, rcx
0x1800f1710  jz      loc_1800F1A3A
0x1800f1716  lea     r9, [rsp+320h+ppszPathOut]; ppszPathOut
0x1800f171b  mov     r8d, 1; dwFlags
0x1800f1721  mov     rdx, rsi; pszMore
0x1800f1724  call    cs:__imp_PathAllocCombine
0x1800f172b  nop     dword ptr [rax+rax+00h]
0x1800f1730  mov     edi, eax
0x1800f1732  test    eax, eax
0x1800f1734  js      loc_1800F1B91
0x1800f173a  mov     rcx, [rsp+320h+pv]; pv
0x1800f173f  test    rcx, rcx
0x1800f1742  jz      short loc_1800F1750
0x1800f1744  call    cs:__imp_CoTaskMemFree
0x1800f174b  nop     dword ptr [rax+rax+00h]
0x1800f1750  test    edi, edi
0x1800f1752  js      loc_1800F1ADB
0x1800f1758  mov     [rsp+320h+var_2C0], r13
0x1800f175d  mov     esi, r13d
0x1800f1760  mov     [rsp+320h+pv], r13
0x1800f1765  mov     edi, 80004002h
0x1800f176a  test    rbx, rbx
0x1800f176d  jz      loc_1800F1A1E
0x1800f1773  mov     rax, [rbx]
0x1800f1776  lea     r8, [rsp+320h+pv]
0x1800f177b  lea     rdx, aBindContextTim; "bind context timeout value"
0x1800f1782  mov     rcx, rbx
0x1800f1785  mov     rax, [rax+50h]
0x1800f1789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f178e  test    eax, eax
0x1800f1790  js      loc_1800F1A1E
0x1800f1796  mov     rcx, [rsp+320h+pv]
0x1800f179b  lea     r8, [rsp+320h+var_2C0]
0x1800f17a0  lea     rdx, _GUID_bd1ae5e0_a6ae_11ce_bd37_504200c10000
0x1800f17a7  mov     rax, [rcx]
0x1800f17aa  mov     rax, [rax]
0x1800f17ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f17b2  mov     rcx, [rsp+320h+pv]
0x1800f17b7  mov     edi, eax
0x1800f17b9  mov     rax, [rcx]
0x1800f17bc  mov     rax, [rax+10h]
0x1800f17c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f17c5  test    edi, edi
0x1800f17c7  jns     loc_1800F19E0
0x1800f17cd  mov     rcx, [rsp+320h+ppszPathOut]; Src
0x1800f17d2  lea     r8, [rsp+320h+var_2B0]
0x1800f17d7  mov     edx, r14d
0x1800f17da  call    GetFindDataForPath
0x1800f17df  mov     edi, eax
0x1800f17e1  test    eax, eax
0x1800f17e3  jns     loc_1800F195B
0x1800f17e9  mov     rcx, [rsp+320h+ppszPathOut]; hMem
0x1800f17ee  test    rcx, rcx
0x1800f17f1  jz      loc_1800F18FF
0x1800f17f7  call    cs:__imp_LocalFree
0x1800f17fe  nop     dword ptr [rax+rax+00h]
0x1800f1803  jmp     loc_1800F18FF
0x1800f1808  call    cs:__imp_LocalFree
0x1800f180f  nop     dword ptr [rax+rax+00h]
0x1800f1814  mov     eax, r13d
0x1800f1817  test    rbx, rbx
0x1800f181a  jz      short loc_1800F1856
0x1800f181c  mov     [rsp+320h+var_2B8], rax
0x1800f1821  lea     rdx, [rsp+320h+var_2C0]
0x1800f1826  mov     rax, [rbx]
0x1800f1829  mov     rcx, rbx
0x1800f182c  mov     [rsp+320h+var_2C0], 10h
0x1800f1835  mov     rax, [rax+38h]
0x1800f1839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f183e  test    eax, eax
0x1800f1840  js      loc_1800F196E
0x1800f1846  cmp     dword ptr [rsp+320h+var_2C0+4], 2
0x1800f184b  jnz     loc_1800F196E
0x1800f1851  mov     eax, 1
0x1800f1856  test    eax, eax
0x1800f1858  mov     [rsp+320h+ppszPathOut], r13
0x1800f185d  mov     edi, 1
0x1800f1862  mov     ecx, 7
0x1800f1867  cmovz   edi, ecx
0x1800f186a  mov     esi, 0BEEF0000h
0x1800f186f  test    byte ptr [rsp+320h+var_2B0], 10h
0x1800f1874  jz      loc_1800F198F
0x1800f187a  mov     [rsp+320h+pv], r13
0x1800f187f  test    rbx, rbx
0x1800f1882  jz      short loc_1800F18A7
0x1800f1884  mov     rax, [rbx]
0x1800f1887  lea     r8, [rsp+320h+pv]
0x1800f188c  lea     rdx, aWin7filesystem; "Win7FileSystemIdList"
0x1800f1893  mov     rcx, rbx
0x1800f1896  mov     rax, [rax+50h]
0x1800f189a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f189f  test    eax, eax
0x1800f18a1  jns     loc_1800F1976
0x1800f18a7  mov     rcx, rbx; struct IBindCtx *
0x1800f18aa  call    ?BindCtx_GetFolderEnumMode@@YA?AW4FOLDER_ENUM_MODE@@PEAUIBindCtx@@@Z; BindCtx_GetFolderEnumMode(IBindCtx *)
0x1800f18af  mov     rdx, [rsp+320h+ppszPathOut]
0x1800f18b4  xor     r9d, r9d
0x1800f18b7  mov     [rsp+320h+var_2E0], r12
0x1800f18bc  xor     r8d, r8d
0x1800f18bf  mov     [rsp+320h+var_2E8], eax
0x1800f18c3  mov     rcx, r15
0x1800f18c6  mov     [rsp+320h+var_2F0], edi
0x1800f18ca  mov     [rsp+320h+var_2F8], esi
0x1800f18ce  mov     [rsp+320h+var_300], rdx
0x1800f18d3  lea     rdx, [rsp+320h+var_2B0]
0x1800f18d8  call    ?_CreateIDList@CFSFolder@@IEAAJPEBUtagWIN32_FIND_DATA_EX@@PEFBU_ITEMIDLIST_RELATIVE@@PEBG2W4IDLHID@@W4CREATE_IDLIST_FLAGS@@W4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z; CFSFolder::_CreateIDList(tagWIN32_FIND_DATA_EX const *,_ITEMIDLIST_RELATIVE const *,ushort const *,ushort const *,IDLHID,CREATE_IDLIST_FLAGS,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)
0x1800f18dd  mov     edi, eax
0x1800f18df  test    eax, eax
0x1800f18e1  js      short loc_1800F18EE
0x1800f18e3  cmp     [rsp+320h+ppszPathOut], r13
0x1800f18e8  jnz     loc_1800F1B15
0x1800f18ee  mov     rcx, [rsp+320h+ppszPathOut]; pv
0x1800f18f3  call    cs:__imp_CoTaskMemFree
0x1800f18fa  nop     dword ptr [rax+rax+00h]
0x1800f18ff  mov     eax, edi
0x1800f1901  mov     rcx, [rbp+220h+var_40]
0x1800f1908  xor     rcx, rsp; StackCookie
0x1800f190b  call    __security_check_cookie
0x1800f1910  mov     rbx, [rsp+320h+arg_10]
0x1800f1918  add     rsp, 2F0h
0x1800f191f  pop     r15
0x1800f1921  pop     r14
0x1800f1923  pop     r13
0x1800f1925  pop     r12
0x1800f1927  pop     rdi
0x1800f1928  pop     rsi
0x1800f1929  pop     rbp
0x1800f192a  retn
0x1800f192c  mov     rcx, r15; this
0x1800f192f  call    ?_IsNetFolder@CFSFolder@@IEAAHXZ; CFSFolder::_IsNetFolder(void)
0x1800f1934  test    eax, eax
0x1800f1936  jz      loc_1800F17CD
0x1800f193c  mov     rcx, [rsp+320h+ppszPathOut]; unsigned __int16 *
0x1800f1941  lea     r9, [rsp+320h+var_2B0]; struct tagWIN32_FIND_DATA_EX *
0x1800f1946  mov     r8d, esi; unsigned int
0x1800f1949  mov     edx, r14d; int
0x1800f194c  call    ?GetFindDataForPathWithTimeout@@YAJPEBGHKPEAUtagWIN32_FIND_DATA_EX@@@Z; GetFindDataForPathWithTimeout(ushort const *,int,ulong,tagWIN32_FIND_DATA_EX *)
0x1800f1951  mov     edi, eax
0x1800f1953  test    eax, eax
0x1800f1955  js      loc_1800F1B4D
0x1800f195b  mov     rcx, [rsp+320h+ppszPathOut]; hMem
0x1800f1960  test    rcx, rcx
0x1800f1963  jz      loc_1800F1814
0x1800f1969  jmp     loc_1800F1808
0x1800f196e  mov     eax, r13d
0x1800f1971  jmp     loc_1800F1856
0x1800f1976  mov     rcx, [rsp+320h+pv]
0x1800f197b  mov     rax, [rcx]
0x1800f197e  mov     rax, [rax+10h]
0x1800f1982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1987  or      edi, 8
0x1800f198a  jmp     loc_1800F18A7
0x1800f198f  test    rbx, rbx
0x1800f1992  jz      loc_1800F187A
0x1800f1998  lea     r8, [rsp+320h+ppszPathOut]
0x1800f199d  mov     rcx, rbx
0x1800f19a0  lea     rdx, aExplicitprogid; "ExplicitProgid"
0x1800f19a7  call    ??$_BindCtx_GetValue@PEAG@@YAJPEAUIBindCtx@@PEBGPEAPEAG@Z; _BindCtx_GetValue<ushort *>(IBindCtx *,ushort const *,ushort * *)
0x1800f19ac  test    eax, eax
0x1800f19ae  jns     short loc_1800F1A2B
0x1800f19b0  lea     r8, [rsp+320h+ppszPathOut]
0x1800f19b5  mov     [rsp+320h+ppszPathOut], r13
0x1800f19ba  lea     rdx, aExplicitassoci; "ExplicitAssociationApp"
0x1800f19c1  mov     rcx, rbx
0x1800f19c4  call    ??$_BindCtx_GetValue@PEAG@@YAJPEAUIBindCtx@@PEBGPEAPEAG@Z; _BindCtx_GetValue<ushort *>(IBindCtx *,ushort const *,ushort * *)
0x1800f19c9  test    eax, eax
0x1800f19cb  js      loc_1800F187A
0x1800f19d1  mov     esi, 0BEEF001Bh
0x1800f19d6  mov     [rsp+320h+pv], r13
0x1800f19db  jmp     loc_1800F1884
0x1800f19e0  mov     rcx, [rsp+320h+var_2C0]
0x1800f19e5  lea     rdx, [rsp+320h+pv]
0x1800f19ea  mov     [rsp+320h+pv], r13
0x1800f19ef  mov     r9d, 8
0x1800f19f5  mov     r8d, 1
0x1800f19fb  mov     rax, [rcx]
0x1800f19fe  mov     rax, [rax+30h]
0x1800f1a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1a07  mov     edi, eax
0x1800f1a09  test    eax, eax
0x1800f1a0b  jns     short loc_1800F1A79
0x1800f1a0d  mov     rcx, [rsp+320h+var_2C0]
0x1800f1a12  mov     rax, [rcx]
0x1800f1a15  mov     rax, [rax+10h]
0x1800f1a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1a1e  test    edi, edi
0x1800f1a20  js      loc_1800F17CD
0x1800f1a26  jmp     loc_1800F192C
0x1800f1a2b  mov     esi, 0BEEF001Ah
0x1800f1a30  mov     [rsp+320h+pv], r13
0x1800f1a35  jmp     loc_1800F1884
0x1800f1a3a  lea     rcx, [rsp+320h+pv]
0x1800f1a3f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800f1a44  mov     rdx, rax; unsigned __int16 **
0x1800f1a47  mov     rcx, r15; this
0x1800f1a4a  call    ?GetFolderPath@CFSFolder@@QEAAJPEAPEAG@Z; CFSFolder::GetFolderPath(ushort * *)
0x1800f1a4f  mov     edi, eax
0x1800f1a51  test    eax, eax
0x1800f1a53  js      short loc_1800F1AAA
0x1800f1a55  mov     rcx, [rsp+320h+pv]
0x1800f1a5a  jmp     loc_1800F1716
0x1800f1a5f  mov     r9, rsi; pszSrc
0x1800f1a62  lea     rcx, [rbp+220h+pszDest]; pszDest
0x1800f1a66  mov     edx, 104h; cchDest
0x1800f1a6b  call    StringCopyWorkerW
0x1800f1a70  mov     [rsp+320h+var_2B0], edi
0x1800f1a74  jmp     loc_1800F1814
0x1800f1a79  call    cs:__imp_GetTickCount
0x1800f1a80  nop     dword ptr [rax+rax+00h]
0x1800f1a85  mov     rcx, [rsp+320h+pv]
0x1800f1a8a  mov     edx, eax
0x1800f1a8c  mov     r8d, dword ptr [rsp+320h+pv+4]
0x1800f1a91  sub     edx, ecx
0x1800f1a93  cmp     edx, r8d
0x1800f1a96  ja      loc_1800F1A0D
0x1800f1a9c  sub     r8d, eax
0x1800f1a9f  lea     esi, [rcx-1]
0x1800f1aa2  add     esi, r8d
0x1800f1aa5  jmp     loc_1800F1A0D
0x1800f1aaa  mov     rcx, [rbp+228h]; this
0x1800f1ab1  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800f1ab8  mov     r9d, eax; char *
0x1800f1abb  mov     edx, 4E6h; void *
0x1800f1ac0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1ac5  mov     rcx, [rsp+320h+pv]; pv
0x1800f1aca  test    rcx, rcx
0x1800f1acd  jz      short loc_1800F1ADB
0x1800f1acf  call    cs:__imp_CoTaskMemFree
0x1800f1ad6  nop     dword ptr [rax+rax+00h]
0x1800f1adb  mov     rcx, [rbp+228h]; this
0x1800f1ae2  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800f1ae9  mov     r9d, edi; char *
0x1800f1aec  mov     edx, 906h; void *
0x1800f1af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1af6  mov     rcx, [rsp+320h+ppszPathOut]; hMem
0x1800f1afb  test    rcx, rcx
0x1800f1afe  jz      loc_1800F18FF
0x1800f1b04  call    cs:__imp_LocalFree
0x1800f1b0b  nop     dword ptr [rax+rax+00h]
0x1800f1b10  jmp     loc_1800F18FF
0x1800f1b15  mov     r8d, 1
0x1800f1b1b  lea     rdx, aExplicitassoci_0; "ExplicitAssociationSuccessful"
0x1800f1b22  mov     rcx, rbx
0x1800f1b25  call    ??$_BindCtx_SetValue@H@@YAJPEAUIBindCtx@@PEBGH@Z; _BindCtx_SetValue<int>(IBindCtx *,ushort const *,int)
0x1800f1b2a  mov     edi, eax
0x1800f1b2c  test    eax, eax
0x1800f1b2e  jns     loc_1800F18EE
0x1800f1b34  mov     rcx, [r12]; pv
0x1800f1b38  call    cs:__imp_CoTaskMemFree
0x1800f1b3f  nop     dword ptr [rax+rax+00h]
0x1800f1b44  mov     [r12], r13
0x1800f1b48  jmp     loc_1800F18EE
0x1800f1b4d  mov     rcx, [rsp+320h+ppszPathOut]; hMem
0x1800f1b52  test    rcx, rcx
0x1800f1b55  jz      loc_1800F18FF
0x1800f1b5b  call    cs:__imp_LocalFree
0x1800f1b62  nop     dword ptr [rax+rax+00h]
0x1800f1b67  jmp     loc_1800F18FF
0x1800f1b6c  mov     rcx, [rbp+228h]; this
0x1800f1b73  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800f1b7a  mov     edi, 800704B0h
0x1800f1b7f  mov     edx, 901h; void *
0x1800f1b84  mov     r9d, edi; char *
0x1800f1b87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1b8c  jmp     loc_1800F18FF
0x1800f1b91  mov     rcx, [rbp+228h]; this
  ... truncated ...
```
