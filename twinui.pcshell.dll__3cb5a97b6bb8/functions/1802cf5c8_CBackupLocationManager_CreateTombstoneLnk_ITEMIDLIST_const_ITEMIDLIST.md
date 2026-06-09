# CBackupLocationManager::CreateTombstoneLnk(_ITEMIDLIST const *,_ITEMIDLIST * *)

- ea: `0x1802cf5c8`
- end: `0x1802cf9b5`
- name: `?CreateTombstoneLnk@CBackupLocationManager@@QEBAJPEFBU_ITEMIDLIST@@PEAPEFAU2@@Z`
- size: `1005`
- prototype: `__int64 __fastcall(CBackupLocationManager *__hidden this, LPCITEMIDLIST pidl, struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802eb2f8`

## callees

- `0x1800237c8`
- `0x180031c70`
- `0x1800a316c`
- `0x1802789e0`
- `0x1802cf5c8`
- `0x1802cf9f0`
- `0x1802cfa14`
- `0x180356360`
- `0x180356edc`
- `0x18038fcdc`
- `0x18038fd5c`
- `0x18067aea4`
- `0x18067f190`
- `0x180684700`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf7d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf968`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf7d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cf968`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x1802cf845`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x1802cf845`
- `api-ms-win-shell-namespace-l1-1-0!ILFindLastID` at `0x1802cf8b6`
- `api-ms-win-shell-namespace-l1-1-0!ILFindLastID` at `0x1802cf8b6`
- `SHELL32!SHFileOperationW` at `0x1802cf6a6`
- `SHELL32!SHFileOperationW` at `0x1802cf6a6`
- `Windows.Storage!ILFindChild` at `0x1802cf7ea`
- `Windows.Storage!ILFindChild` at `0x1802cf7ea`
- `Windows.Storage!ILCombine` at `0x1802cf866`
- `Windows.Storage!ILCombine` at `0x1802cf866`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x1802cf78d`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x1802cf78d`
- `Windows.Storage!SHGetPathFromIDListW` at `0x1802cf616`
- `Windows.Storage!SHGetPathFromIDListW` at `0x1802cf616`
- `Windows.Storage!__imp_SHILCreateFromPath` at `0x1802cf714`
- `Windows.Storage!__imp_SHILCreateFromPath` at `0x1802cf714`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CBackupLocationManager::CreateTombstoneLnk(
        CBackupLocationManager *this,
        LPCITEMIDLIST pidl,
        struct _ITEMIDLIST **a3)
{
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  HRESULT TombstoneShortcutLocation; // ebx
  int v9; // eax
  void *v10; // rcx
  LPITEMIDLIST v11; // rcx
  struct _ITEMIDLIST *v12; // rdi
  const ITEMIDLIST *v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  LPITEMIDLIST v17; // rax
  ITEMIDLIST *v18; // rcx
  LPVOID v19; // rdx
  const struct _ITEMIDLIST *ID; // rbx
  const struct _HIDDENITEMID *HiddenID; // rax
  const struct _ITEMIDLIST *i; // r14
  const struct _HIDDENITEMID *v23; // rsi
  struct _ITEMIDLIST *v24; // rax
  LPITEMIDLIST v25; // rcx
  void *v26; // rcx
  int psfgaoOut; // [rsp+20h] [rbp-E0h]
  void *p_pv; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-C8h] BYREF
  char v31; // [rsp+40h] [rbp-C0h]
  struct _SHFILEOPSTRUCTW FileOp; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  struct _ITEMIDLIST *v34; // [rsp+88h] [rbp-78h] BYREF
  LPITEMIDLIST pidlParent; // [rsp+90h] [rbp-70h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+98h] [rbp-68h] BYREF
  IBindCtx *pbc[2]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszPath[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v39[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  memset_0(pszPath, 0, 0x20Au);
  if ( !SHGetPathFromIDListW(pidl, pszPath) )
  {
    v6 = 3168;
LABEL_36:
    TombstoneShortcutLocation = -2147467259;
    goto LABEL_37;
  }
  memset_0(v39, 0, 0x20Au);
  TombstoneShortcutLocation = CBackupLocationManager::_GetTombstoneShortcutLocation(this, pszPath, v39, v7);
  if ( TombstoneShortcutLocation < 0 )
  {
    v6 = 3172;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)TombstoneShortcutLocation,
      psfgaoOut);
    return (unsigned int)TombstoneShortcutLocation;
  }
  *(_OWORD *)&FileOp.hwnd = 0;
  memset(&FileOp.fFlags, 0, 24);
  FileOp.wFunc = 2;
  FileOp.pFrom = pszPath;
  FileOp.pTo = v39;
  FileOp.fFlags = 1556;
  if ( SHFileOperationW(&FileOp) || FileOp.fAnyOperationsAborted )
  {
    v6 = 3179;
    goto LABEL_36;
  }
  v9 = CBackupLocationManager::s_CopyLocalizedName(pszPath, v39);
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC6E,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)v9,
      psfgaoOut);
  pv = 0;
  p_pv = &pv;
  ppidl = 0;
  v31 = 1;
  TombstoneShortcutLocation = SHILCreateFromPath(v39, &ppidl, 0);
  wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( TombstoneShortcutLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC71,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)TombstoneShortcutLocation,
      psfgaoOut);
LABEL_11:
    v10 = pv;
    pv = 0;
    if ( v10 )
      CoTaskMemFree(v10);
    return (unsigned int)TombstoneShortcutLocation;
  }
  pidlParent = 0;
  p_pv = &pidlParent;
  ppidl = 0;
  v31 = 1;
  TombstoneShortcutLocation = SHGetKnownFolderIDList(&FOLDERID_UserPinned, 0x9000u, 0, &ppidl);
  wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( TombstoneShortcutLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC74,
      (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
      (const char *)(unsigned int)TombstoneShortcutLocation,
      psfgaoOut);
LABEL_15:
    v11 = pidlParent;
    pidlParent = 0;
    if ( v11 )
      CoTaskMemFree(v11);
    goto LABEL_11;
  }
  v12 = 0;
  v34 = 0;
  v13 = ILFindChild(pidlParent, (LPCITEMIDLIST)pv);
  if ( !v13 )
    goto LABEL_24;
  pbc[0] = 0;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(pbc);
  if ( (int)BindCtx_SetMode(v15, v14, pbc) >= 0 )
  {
    pidl1 = 0;
    p_pv = &pidl1;
    ppidl = 0;
    v31 = 1;
    v16 = (unsigned int)SHParseDisplayName(L"::{1f3427c8-5c10-4210-aa03-2ee45287d668}", pbc[0], &ppidl, 0, 0) >> 31;
    wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( (unsigned __int8)v16 != 1 )
    {
      v17 = ILCombine(pidl1, v13);
      wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v34,
        v17);
      v12 = v34;
    }
    v18 = (ITEMIDLIST *)pidl1;
    pidl1 = 0;
    if ( v18 )
      CoTaskMemFree(v18);
  }
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(pbc);
  if ( !v12 )
  {
LABEL_24:
    v19 = pv;
    pv = 0;
    wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v34,
      v19);
    v12 = v34;
  }
  ID = ILFindLastID(pidl);
  HiddenID = ILFindFirstHiddenID(ID);
  for ( i = (const struct _ITEMIDLIST *)((char *)ID + ID->mkid.cb); ; HiddenID = ILNextHidden(v23, i) )
  {
    v23 = HiddenID;
    v34 = 0;
    if ( !HiddenID )
      break;
    v24 = ILAppendHiddenID(v12, HiddenID);
    wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      &v34,
      v24);
    v12 = v34;
    if ( !v34 )
    {
      TombstoneShortcutLocation = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC92,
        (unsigned int)"pcshell\\shell\\pinninglib\\lib\\PinnedList.cpp",
        (const char *)0x8007000ELL,
        psfgaoOut);
      wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v34,
        0);
      goto LABEL_15;
    }
  }
  *a3 = v12;
  wistd::unique_ptr<_ITEMIDLIST __unaligned,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &v34,
    0);
  v25 = pidlParent;
  pidlParent = 0;
  if ( v25 )
    CoTaskMemFree(v25);
  v26 = pv;
  pv = 0;
  if ( v26 )
    CoTaskMemFree(v26);
  return 0;
}

```

## disassembly

```asm
0x1802cf5c8  push    rbp
0x1802cf5ca  push    rbx
0x1802cf5cb  push    rsi
0x1802cf5cc  push    rdi
0x1802cf5cd  push    r12
0x1802cf5cf  push    r14
0x1802cf5d1  push    r15
0x1802cf5d3  lea     rbp, [rsp-3E0h]
0x1802cf5db  sub     rsp, 4E0h
0x1802cf5e2  mov     rax, cs:__security_cookie
0x1802cf5e9  xor     rax, rsp
0x1802cf5ec  mov     [rbp+410h+var_40], rax
0x1802cf5f3  mov     r15, r8
0x1802cf5f6  mov     r14, rdx
0x1802cf5f9  mov     rbx, rcx
0x1802cf5fc  mov     edi, 20Ah
0x1802cf601  mov     r8d, edi; Size
0x1802cf604  xor     edx, edx; Val
0x1802cf606  lea     rcx, [rbp+410h+pszPath]; void *
0x1802cf60a  call    memset_0
0x1802cf60f  lea     rdx, [rbp+410h+pszPath]; pszPath
0x1802cf613  mov     rcx, r14; pidl
0x1802cf616  call    cs:__imp_SHGetPathFromIDListW
0x1802cf61c  xor     r12d, r12d
0x1802cf61f  test    eax, eax
0x1802cf621  jnz     short loc_1802CF62D
0x1802cf623  mov     edx, 0C60h
0x1802cf628  jmp     loc_1802CF977
0x1802cf62d  mov     r8, rdi; Size
0x1802cf630  xor     edx, edx; Val
0x1802cf632  lea     rcx, [rbp+410h+var_250]; void *
0x1802cf639  call    memset_0
0x1802cf63e  lea     r8, [rbp+410h+var_250]; unsigned __int16 *
0x1802cf645  lea     rdx, [rbp+410h+pszPath]; pszPath
0x1802cf649  mov     rcx, rbx; this
0x1802cf64c  call    ?_GetTombstoneShortcutLocation@CBackupLocationManager@@AEBAJPEAG0_K@Z; CBackupLocationManager::_GetTombstoneShortcutLocation(ushort *,ushort *,unsigned __int64)
0x1802cf651  mov     ebx, eax
0x1802cf653  test    eax, eax
0x1802cf655  jns     short loc_1802CF661
0x1802cf657  mov     edx, 0C64h
0x1802cf65c  jmp     loc_1802CF97C
0x1802cf661  xorps   xmm0, xmm0
0x1802cf664  xor     eax, eax
0x1802cf666  movups  xmmword ptr [rsp+510h+FileOp.hwnd], xmm0
0x1802cf66b  movups  xmmword ptr [rsp+510h+FileOp.pFrom], xmm0
0x1802cf670  movups  xmmword ptr [rsp+510h+FileOp.fFlags], xmm0
0x1802cf675  mov     [rsp+510h+FileOp.lpszProgressTitle], rax
0x1802cf67a  mov     [rsp+510h+FileOp.wFunc], 2
0x1802cf682  lea     rax, [rbp+410h+pszPath]
0x1802cf686  mov     [rsp+510h+FileOp.pFrom], rax
0x1802cf68b  lea     rax, [rbp+410h+var_250]
0x1802cf692  mov     [rsp+510h+FileOp.pTo], rax
0x1802cf697  mov     eax, 614h
0x1802cf69c  mov     [rsp+510h+FileOp.fFlags], ax
0x1802cf6a1  lea     rcx, [rsp+510h+FileOp]; lpFileOp
0x1802cf6a6  call    cs:__imp_SHFileOperationW
0x1802cf6ac  test    eax, eax
0x1802cf6ae  jnz     loc_1802CF972
0x1802cf6b4  cmp     [rsp+510h+FileOp.fAnyOperationsAborted], r12d
0x1802cf6b9  jnz     loc_1802CF972
0x1802cf6bf  lea     rdx, [rbp+410h+var_250]; unsigned __int16 *
0x1802cf6c6  lea     rcx, [rbp+410h+pszPath]; unsigned __int16 *
0x1802cf6ca  call    ?s_CopyLocalizedName@CBackupLocationManager@@CAJPEBG0@Z; CBackupLocationManager::s_CopyLocalizedName(ushort const *,ushort const *)
0x1802cf6cf  mov     rcx, [rbp+418h]; this
0x1802cf6d6  test    eax, eax
0x1802cf6d8  jns     short loc_1802CF6EE
0x1802cf6da  mov     r9d, eax; char *
0x1802cf6dd  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x1802cf6e4  mov     edx, 0C6Eh; void *
0x1802cf6e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802cf6ee  mov     [rbp+410h+pv], r12
0x1802cf6f2  lea     rax, [rbp+410h+pv]
0x1802cf6f6  mov     [rsp+510h+var_4E0], rax
0x1802cf6fb  mov     [rsp+510h+ppidl], r12
0x1802cf700  mov     [rsp+510h+var_4D0], 1
0x1802cf705  xor     r8d, r8d; rgfInOut
0x1802cf708  lea     rdx, [rsp+510h+ppidl]; ppidl
0x1802cf70d  lea     rcx, [rbp+410h+var_250]; pszPath
0x1802cf714  call    cs:__imp_SHILCreateFromPath
0x1802cf71a  mov     ebx, eax
0x1802cf71c  lea     rcx, [rsp+510h+var_4E0]
0x1802cf721  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1802cf726  test    ebx, ebx
0x1802cf728  jns     short loc_1802CF762
0x1802cf72a  mov     rcx, [rbp+418h]; this
0x1802cf731  mov     r9d, ebx; char *
0x1802cf734  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x1802cf73b  mov     edx, 0C71h; void *
0x1802cf740  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cf745  nop
0x1802cf746  mov     rcx, [rbp+410h+pv]; pv
0x1802cf74a  mov     [rbp+410h+pv], r12
0x1802cf74e  test    rcx, rcx
0x1802cf751  jz      loc_1802CF992
0x1802cf757  call    cs:__imp_CoTaskMemFree
0x1802cf75d  jmp     loc_1802CF992
0x1802cf762  mov     [rbp+410h+pidlParent], r12
0x1802cf766  lea     rax, [rbp+410h+pidlParent]
0x1802cf76a  mov     [rsp+510h+var_4E0], rax
0x1802cf76f  mov     [rsp+510h+ppidl], r12
0x1802cf774  mov     [rsp+510h+var_4D0], 1
0x1802cf779  lea     r9, [rsp+510h+ppidl]; ppidl
0x1802cf77e  xor     r8d, r8d; hToken
0x1802cf781  mov     edx, 9000h; dwFlags
0x1802cf786  lea     rcx, FOLDERID_UserPinned; rfid
0x1802cf78d  call    cs:__imp_SHGetKnownFolderIDList
0x1802cf793  mov     ebx, eax
0x1802cf795  lea     rcx, [rsp+510h+var_4E0]
0x1802cf79a  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1802cf79f  test    ebx, ebx
0x1802cf7a1  jns     short loc_1802CF7DB
0x1802cf7a3  mov     rcx, [rbp+418h]; this
0x1802cf7aa  mov     r9d, ebx; char *
0x1802cf7ad  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x1802cf7b4  mov     edx, 0C74h; void *
0x1802cf7b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cf7be  nop
0x1802cf7bf  mov     rcx, [rbp+410h+pidlParent]; pv
0x1802cf7c3  mov     [rbp+410h+pidlParent], r12
0x1802cf7c7  test    rcx, rcx
0x1802cf7ca  jz      loc_1802CF746
0x1802cf7d0  call    cs:__imp_CoTaskMemFree
0x1802cf7d6  jmp     loc_1802CF746
0x1802cf7db  mov     rdi, r12
0x1802cf7de  mov     [rbp+410h+var_488], r12
0x1802cf7e2  mov     rdx, [rbp+410h+pv]; pidlChild
0x1802cf7e6  mov     rcx, [rbp+410h+pidlParent]; pidlParent
0x1802cf7ea  call    cs:__imp_ILFindChild
0x1802cf7f0  mov     rsi, rax
0x1802cf7f3  test    rax, rax
0x1802cf7f6  jz      loc_1802CF89E
0x1802cf7fc  mov     [rbp+410h+pbc], r12
0x1802cf800  lea     rcx, [rbp+410h+pbc]
0x1802cf804  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1802cf809  lea     r8, [rbp+410h+pbc]
0x1802cf80d  call    BindCtx_SetMode
0x1802cf812  test    eax, eax
0x1802cf814  js      short loc_1802CF890
0x1802cf816  mov     [rbp+410h+pidl1], r12
0x1802cf81a  lea     rax, [rbp+410h+pidl1]
0x1802cf81e  mov     [rsp+510h+var_4E0], rax
0x1802cf823  mov     [rsp+510h+ppidl], r12
0x1802cf828  mov     [rsp+510h+var_4D0], 1
0x1802cf82d  mov     qword ptr [rsp+510h+psfgaoOut], r12; int
0x1802cf832  xor     r9d, r9d; sfgaoIn
0x1802cf835  lea     r8, [rsp+510h+ppidl]; ppidl
0x1802cf83a  mov     rdx, [rbp+410h+pbc]; pbc
0x1802cf83e  lea     rcx, a1f3427c85c1042; "::{1f3427c8-5c10-4210-aa03-2ee45287d668"...
0x1802cf845  call    cs:__imp_SHParseDisplayName
0x1802cf84b  mov     ebx, eax
0x1802cf84d  shr     ebx, 1Fh
0x1802cf850  lea     rcx, [rsp+510h+var_4E0]
0x1802cf855  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1802cf85a  xor     bl, 1
0x1802cf85d  jz      short loc_1802CF87C
0x1802cf85f  mov     rdx, rsi; pidl2
0x1802cf862  mov     rcx, [rbp+410h+pidl1]; pidl1
0x1802cf866  call    cs:__imp_ILCombine
0x1802cf86c  mov     rdx, rax
0x1802cf86f  lea     rcx, [rbp+410h+var_488]
0x1802cf873  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x1802cf878  mov     rdi, [rbp+410h+var_488]
0x1802cf87c  mov     rcx, [rbp+410h+pidl1]; pv
0x1802cf880  mov     [rbp+410h+pidl1], r12
0x1802cf884  test    rcx, rcx
0x1802cf887  jz      short loc_1802CF890
0x1802cf889  call    cs:__imp_CoTaskMemFree
0x1802cf88f  nop
0x1802cf890  lea     rcx, [rbp+410h+pbc]
0x1802cf894  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1802cf899  test    rdi, rdi
0x1802cf89c  jnz     short loc_1802CF8B3
0x1802cf89e  mov     rdx, [rbp+410h+pv]
0x1802cf8a2  mov     [rbp+410h+pv], r12
0x1802cf8a6  lea     rcx, [rbp+410h+var_488]
0x1802cf8aa  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x1802cf8af  mov     rdi, [rbp+410h+var_488]
0x1802cf8b3  mov     rcx, r14; pidl
0x1802cf8b6  call    cs:__imp_ILFindLastID
0x1802cf8bc  mov     rbx, rax
0x1802cf8bf  mov     rcx, rax; struct _ITEMIDLIST *
0x1802cf8c2  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST@@@Z; ILFindFirstHiddenID(_ITEMIDLIST const *)
0x1802cf8c7  movzx   r14d, word ptr [rbx]
0x1802cf8cb  add     r14, rbx
0x1802cf8ce  mov     rsi, rax
0x1802cf8d1  mov     [rbp+410h+var_488], r12
0x1802cf8d5  test    rax, rax
0x1802cf8d8  jz      short loc_1802CF938
0x1802cf8da  mov     rdx, rax; struct _HIDDENITEMID *
0x1802cf8dd  mov     rcx, rdi; pidl
0x1802cf8e0  call    ?ILAppendHiddenID@@YAPEFAU_ITEMIDLIST@@PEFAU1@PEFBU_HIDDENITEMID@@@Z; ILAppendHiddenID(_ITEMIDLIST *,_HIDDENITEMID const *)
0x1802cf8e5  mov     rdx, rax
0x1802cf8e8  lea     rcx, [rbp+410h+var_488]
0x1802cf8ec  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x1802cf8f1  mov     rdi, [rbp+410h+var_488]
0x1802cf8f5  test    rdi, rdi
0x1802cf8f8  jz      short loc_1802CF907
0x1802cf8fa  mov     rdx, r14; struct _ITEMIDLIST *
0x1802cf8fd  mov     rcx, rsi; struct _HIDDENITEMID *
0x1802cf900  call    ?ILNextHidden@@YAPEFBU_HIDDENITEMID@@PEFBU1@PEFBU_ITEMIDLIST@@@Z; ILNextHidden(_HIDDENITEMID const *,_ITEMIDLIST const *)
0x1802cf905  jmp     short loc_1802CF8CE
0x1802cf907  mov     rcx, [rbp+418h]; this
0x1802cf90e  mov     ebx, 8007000Eh
0x1802cf913  mov     r9d, ebx; char *
0x1802cf916  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x1802cf91d  mov     edx, 0C92h; void *
0x1802cf922  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cf927  nop
0x1802cf928  xor     edx, edx
0x1802cf92a  lea     rcx, [rbp+410h+var_488]
0x1802cf92e  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x1802cf933  jmp     loc_1802CF7BF
0x1802cf938  mov     [r15], rdi
0x1802cf93b  xor     edx, edx
0x1802cf93d  lea     rcx, [rbp+410h+var_488]
0x1802cf941  call    ?reset@?$unique_ptr@$$CFAU_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEFAU_ITEMIDLIST@@@Z; wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST *)
0x1802cf946  nop
0x1802cf947  mov     rcx, [rbp+410h+pidlParent]; pv
0x1802cf94b  mov     [rbp+410h+pidlParent], r12
0x1802cf94f  test    rcx, rcx
0x1802cf952  jz      short loc_1802CF95B
0x1802cf954  call    cs:__imp_CoTaskMemFree
0x1802cf95a  nop
0x1802cf95b  mov     rcx, [rbp+410h+pv]; pv
0x1802cf95f  mov     [rbp+410h+pv], r12
0x1802cf963  test    rcx, rcx
0x1802cf966  jz      short loc_1802CF96E
0x1802cf968  call    cs:__imp_CoTaskMemFree
0x1802cf96e  xor     eax, eax
0x1802cf970  jmp     short loc_1802CF994
0x1802cf972  mov     edx, 0C6Bh; void *
0x1802cf977  mov     ebx, 80004005h
0x1802cf97c  mov     r9d, ebx; char *
0x1802cf97f  lea     r8, aPcshellShellPi_0; "pcshell\\shell\\pinninglib\\lib\\Pinned"...
0x1802cf986  mov     rcx, [rbp+418h]; this
0x1802cf98d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802cf992  mov     eax, ebx
0x1802cf994  mov     rcx, [rbp+410h+var_40]
0x1802cf99b  xor     rcx, rsp; StackCookie
0x1802cf99e  call    __security_check_cookie
0x1802cf9a3  add     rsp, 4E0h
0x1802cf9aa  pop     r15
0x1802cf9ac  pop     r14
0x1802cf9ae  pop     r12
0x1802cf9b0  pop     rdi
0x1802cf9b1  pop     rsi
0x1802cf9b2  pop     rbx
0x1802cf9b3  pop     rbp
0x1802cf9b4  retn
```
