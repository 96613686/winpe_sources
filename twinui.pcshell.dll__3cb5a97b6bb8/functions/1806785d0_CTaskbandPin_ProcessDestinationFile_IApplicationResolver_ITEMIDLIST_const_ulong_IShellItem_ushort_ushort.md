# CTaskbandPin::_ProcessDestinationFile(IApplicationResolver *,_ITEMIDLIST const *,ulong,IShellItem * *,ushort * *,ushort * *)

- ea: `0x1806785d0`
- end: `0x1806788be`
- name: `?_ProcessDestinationFile@CTaskbandPin@@IEAAJPEAUIApplicationResolver@@PEFBU_ITEMIDLIST@@KPEAPEAUIShellItem@@PEAPEAG3@Z`
- size: `750`
- prototype: `__int64 __usercall@<rax>(CTaskbandPin *__hidden this@<rcx>, struct IApplicationResolver *@<rdx>, const struct _ITEMIDLIST *@<r8>, unsigned int@<r9d>, struct IShellItem **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180678d10`

## callees

- `0x180356360`
- `0x180678300`
- `0x1806785d0`
- `0x1806788c4`
- `0x1806789fc`
- `0x18067fb00`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067884e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180678858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180678882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067884e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180678858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180678882`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180678794`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180678794`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180678776`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180678776`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180678680`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180678699`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180678680`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180678699`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180678635`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180678635`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180678811`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x180678811`
- `SHELL32!__imp_ILFree` at `0x180678830`
- `SHELL32!__imp_ILFree` at `0x180678830`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1806787f8`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1806787f8`

## pseudocode

```c
__int64 __fastcall CTaskbandPin::_ProcessDestinationFile(
        CTaskbandPin *this,
        struct IApplicationResolver *a2,
        const struct _ITEMIDLIST *a3,
        int a4,
        struct IShellItem **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7)
{
  HRESULT Application; // edi
  CTaskbandPin *v11; // rcx
  int v12; // eax
  CTaskbandPin *v13; // rcx
  unsigned int v14; // r9d
  const WCHAR *FileNameW; // rax
  struct IShellItem *v16; // rcx
  int IsPinned; // ebx
  unsigned __int16 *v18; // rcx
  unsigned __int16 *v20; // [rsp+30h] [rbp-40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR pszPath; // [rsp+40h] [rbp-30h] BYREF
  struct IAssociationArray *v23; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR pszStr1; // [rsp+50h] [rbp-20h] BYREF
  void *ppv; // [rsp+58h] [rbp-18h] BYREF
  __int64 v26; // [rsp+60h] [rbp-10h] BYREF

  LODWORD(ppidl) = a4;
  *a7 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a5 )
    *a5 = 0;
  ppv = 0;
  Application = SHCreateItemFromIDList(a3, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
  if ( Application >= 0 )
  {
    pszStr1 = 0;
    (*(void (__fastcall **)(void *, const PROPERTYKEY *, LPCWSTR *))(*(_QWORD *)ppv + 136LL))(
      ppv,
      &PKEY_FileExtension,
      &pszStr1);
    if ( pszStr1 )
    {
      Application = -2147467259;
      if ( !StrCmpICW(pszStr1, L".EXE") || !StrCmpICW(pszStr1, L".MSC") )
        goto LABEL_27;
    }
    v23 = 0;
    Application = (*(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *, struct IAssociationArray **))(*(_QWORD *)ppv + 24LL))(
                    ppv,
                    0,
                    &BHID_AssociationArray,
                    &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f,
                    &v23);
    if ( Application < 0 )
      goto LABEL_27;
    Application = CTaskbandPin::_TryDestinationViaAppID(v11, v23, a2, a5, a6, a7);
    if ( Application >= 0
      || (v26 = 0,
          Application = (*(__int64 (__fastcall **)(struct IAssociationArray *, __int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v23 + 64LL))(
                          v23,
                          35651598,
                          0,
                          &GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502,
                          &v26),
          Application < 0) )
    {
LABEL_26:
      (*(void (__fastcall **)(struct IAssociationArray *))(*(_QWORD *)v23 + 16LL))(v23);
LABEL_27:
      CoTaskMemFree((LPVOID)pszStr1);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)Application;
    }
    pszPath = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPCWSTR *))(*(_QWORD *)v26 + 24LL))(
            v26,
            33619975,
            0,
            &pszPath);
    Application = v12;
    if ( ((unsigned int)ppidl & 0x20000000) != 0 )
    {
      if ( v12 < 0
        || (FileNameW = PathFindFileNameW(pszPath), CompareStringOrdinal(FileNameW, -1, L"explorer.exe", -1, 1) == 2) )
      {
        Application = CTaskbandPin::_ProcessDestinationFolder(this, a2, a3, v14, a5, a6);
LABEL_25:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        goto LABEL_26;
      }
    }
    else if ( v12 < 0 )
    {
      goto LABEL_25;
    }
    v20 = 0;
    Application = CTaskbandPin::_GetApplication(v13, a2, pszPath, a5, a6, &v20);
    if ( Application >= 0 )
    {
      if ( (unsigned int)SHWindowsPolicy(POLID_NoPinningToTaskbar)
        && ((v16 = *a5, ppidl = 0, Application = SHGetIDListFromObject((IUnknown *)v16, &ppidl), Application < 0)
         || (IsPinned = CPinnedList::IsPinned((CTaskbandPin *)((char *)this + 16), ppidl), ILFree(ppidl), IsPinned)) )
      {
        v18 = v20;
        Application = -2147024891;
      }
      else
      {
        v18 = 0;
        *a7 = v20;
      }
      CoTaskMemFree(v18);
    }
    CoTaskMemFree((LPVOID)pszPath);
    goto LABEL_25;
  }
  return (unsigned int)Application;
}

```

## disassembly

```asm
0x1806785d0  mov     [rsp-38h+arg_18], rbx
0x1806785d5  push    rbp
0x1806785d6  push    rsi
0x1806785d7  push    rdi
0x1806785d8  push    r12
0x1806785da  push    r13
0x1806785dc  push    r14
0x1806785de  push    r15
0x1806785e0  mov     rbp, rsp
0x1806785e3  sub     rsp, 70h
0x1806785e7  mov     rax, cs:__security_cookie
0x1806785ee  xor     rax, rsp
0x1806785f1  mov     [rbp+var_8], rax
0x1806785f5  mov     r15, [rbp+arg_30]
0x1806785f9  xor     eax, eax
0x1806785fb  mov     rsi, [rbp+arg_28]
0x1806785ff  mov     r12, r8
0x180678602  mov     rbx, [rbp+arg_20]
0x180678606  mov     r14, rdx
0x180678609  mov     dword ptr [rbp+ppidl], r9d
0x18067860d  mov     r13, rcx
0x180678610  mov     [r15], rax
0x180678613  test    rsi, rsi
0x180678616  jz      short loc_18067861B
0x180678618  mov     [rsi], rax
0x18067861b  test    rbx, rbx
0x18067861e  jz      short loc_180678623
0x180678620  mov     [rbx], rax
0x180678623  lea     r8, [rbp+ppv]; ppv
0x180678627  mov     [rbp+ppv], rax
0x18067862b  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180678632  mov     rcx, r12; pidl
0x180678635  call    cs:__imp_SHCreateItemFromIDList
0x18067863b  mov     edi, eax
0x18067863d  test    eax, eax
0x18067863f  js      loc_180678898
0x180678645  mov     rcx, [rbp+ppv]
0x180678649  lea     r8, [rbp+pszStr1]
0x18067864d  mov     [rbp+pszStr1], 0
0x180678655  lea     rdx, PKEY_FileExtension
0x18067865c  mov     rax, [rcx]
0x18067865f  mov     rax, [rax+88h]
0x180678666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067866b  mov     rcx, [rbp+pszStr1]; pszStr1
0x18067866f  test    rcx, rcx
0x180678672  jz      short loc_1806786A7
0x180678674  lea     rdx, pszStr2; ".EXE"
0x18067867b  mov     edi, 80004005h
0x180678680  call    cs:__imp_StrCmpICW
0x180678686  test    eax, eax
0x180678688  jz      loc_18067887E
0x18067868e  mov     rcx, [rbp+pszStr1]; pszStr1
0x180678692  lea     rdx, aMsc; ".MSC"
0x180678699  call    cs:__imp_StrCmpICW
0x18067869f  test    eax, eax
0x1806786a1  jz      loc_18067887E
0x1806786a7  mov     rcx, [rbp+ppv]
0x1806786ab  lea     rdx, [rbp+var_28]
0x1806786af  mov     [rbp+var_28], 0
0x1806786b7  lea     r9, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x1806786be  mov     qword ptr [rsp+70h+bIgnoreCase], rdx
0x1806786c3  lea     r8, BHID_AssociationArray
0x1806786ca  xor     edx, edx
0x1806786cc  mov     rax, [rcx]
0x1806786cf  mov     rax, [rax+18h]
0x1806786d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806786d8  mov     edi, eax
0x1806786da  test    eax, eax
0x1806786dc  js      loc_18067887E
0x1806786e2  mov     rdx, [rbp+var_28]; struct IAssociationArray *
0x1806786e6  mov     r9, rbx; struct IShellItem **
0x1806786e9  mov     [rsp+70h+var_48], r15; unsigned __int16 **
0x1806786ee  mov     r8, r14; struct IApplicationResolver *
0x1806786f1  mov     qword ptr [rsp+70h+bIgnoreCase], rsi; unsigned __int16 **
0x1806786f6  call    ?_TryDestinationViaAppID@CTaskbandPin@@IEAAJPEAUIAssociationArray@@PEAUIApplicationResolver@@PEAPEAUIShellItem@@PEAPEAG3@Z; CTaskbandPin::_TryDestinationViaAppID(IAssociationArray *,IApplicationResolver *,IShellItem * *,ushort * *,ushort * *)
0x1806786fb  mov     edi, eax
0x1806786fd  test    eax, eax
0x1806786ff  jns     loc_18067886E
0x180678705  mov     rcx, [rbp+var_28]
0x180678709  lea     rdx, [rbp+var_10]
0x18067870d  mov     [rbp+var_10], 0
0x180678715  lea     r9, _GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502
0x18067871c  mov     qword ptr [rsp+70h+bIgnoreCase], rdx
0x180678721  xor     r8d, r8d
0x180678724  mov     edx, 220000Eh
0x180678729  mov     rax, [rcx]
0x18067872c  mov     rax, [rax+40h]
0x180678730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180678735  mov     edi, eax
0x180678737  test    eax, eax
0x180678739  js      loc_18067886E
0x18067873f  mov     rcx, [rbp+var_10]
0x180678743  lea     r9, [rbp+pszPath]
0x180678747  mov     [rbp+pszPath], 0
0x18067874f  xor     r8d, r8d
0x180678752  mov     edx, 2010007h
0x180678757  mov     rax, [rcx]
0x18067875a  mov     rax, [rax+18h]
0x18067875e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180678763  test    dword ptr [rbp+ppidl], 20000000h
0x18067876a  mov     edi, eax
0x18067876c  jz      short loc_1806787BE
0x18067876e  test    eax, eax
0x180678770  js      short loc_18067879F
0x180678772  mov     rcx, [rbp+pszPath]; pszPath
0x180678776  call    cs:__imp_PathFindFileNameW
0x18067877c  or      edx, 0FFFFFFFFh; cchCount1
0x18067877f  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180678787  mov     r9d, edx; cchCount2
0x18067878a  lea     r8, aExplorerExe_1; "explorer.exe"
0x180678791  mov     rcx, rax; lpString1
0x180678794  call    cs:__imp_CompareStringOrdinal
0x18067879a  cmp     eax, 2
0x18067879d  jnz     short loc_1806787C6
0x18067879f  mov     [rsp+70h+var_48], rsi; unsigned __int16 **
0x1806787a4  mov     r8, r12; struct _ITEMIDLIST *
0x1806787a7  mov     rdx, r14; struct IApplicationResolver *
0x1806787aa  mov     qword ptr [rsp+70h+bIgnoreCase], rbx; struct IShellItem **
0x1806787af  mov     rcx, r13; this
0x1806787b2  call    ?_ProcessDestinationFolder@CTaskbandPin@@IEAAJPEAUIApplicationResolver@@PEFBU_ITEMIDLIST@@KPEAPEAUIShellItem@@PEAPEAG@Z; CTaskbandPin::_ProcessDestinationFolder(IApplicationResolver *,_ITEMIDLIST const *,ulong,IShellItem * *,ushort * *)
0x1806787b7  mov     edi, eax
0x1806787b9  jmp     loc_18067885E
0x1806787be  test    eax, eax
0x1806787c0  js      loc_18067885E
0x1806787c6  mov     r8, [rbp+pszPath]; unsigned __int16 *
0x1806787ca  lea     rax, [rbp+var_40]
0x1806787ce  mov     [rsp+70h+var_48], rax; unsigned __int16 **
0x1806787d3  mov     r9, rbx; struct IShellItem **
0x1806787d6  mov     rdx, r14; struct IApplicationResolver *
0x1806787d9  mov     qword ptr [rsp+70h+bIgnoreCase], rsi; unsigned __int16 **
0x1806787de  mov     [rbp+var_40], 0
0x1806787e6  call    ?_GetApplication@CTaskbandPin@@IEAAJPEAUIApplicationResolver@@PEBGPEAPEAUIShellItem@@PEAPEAG3@Z; CTaskbandPin::_GetApplication(IApplicationResolver *,ushort const *,IShellItem * *,ushort * *,ushort * *)
0x1806787eb  mov     edi, eax
0x1806787ed  test    eax, eax
0x1806787ef  js      short loc_180678854
0x1806787f1  lea     rcx, POLID_NoPinningToTaskbar
0x1806787f8  call    cs:__imp_SHWindowsPolicy
0x1806787fe  test    eax, eax
0x180678800  jz      short loc_180678845
0x180678802  mov     rcx, [rbx]; punk
0x180678805  lea     rdx, [rbp+ppidl]; ppidl
0x180678809  mov     [rbp+ppidl], 0
0x180678811  call    cs:__imp_SHGetIDListFromObject
0x180678817  mov     edi, eax
0x180678819  test    eax, eax
0x18067881b  js      short loc_18067883A
0x18067881d  mov     rdx, [rbp+ppidl]; struct _ITEMIDLIST *
0x180678821  lea     rcx, [r13+10h]; this
0x180678825  call    ?IsPinned@CPinnedList@@UEAAJPEFBU_ITEMIDLIST@@@Z; CPinnedList::IsPinned(_ITEMIDLIST const *)
0x18067882a  mov     rcx, [rbp+ppidl]; pidl
0x18067882e  mov     ebx, eax
0x180678830  call    cs:__imp_ILFree
0x180678836  test    ebx, ebx
0x180678838  jz      short loc_180678845
0x18067883a  mov     rcx, [rbp+var_40]
0x18067883e  mov     edi, 80070005h
0x180678843  jmp     short loc_18067884E
0x180678845  mov     rax, [rbp+var_40]
0x180678849  xor     ecx, ecx; pv
0x18067884b  mov     [r15], rax
0x18067884e  call    cs:__imp_CoTaskMemFree
0x180678854  mov     rcx, [rbp+pszPath]; pv
0x180678858  call    cs:__imp_CoTaskMemFree
0x18067885e  mov     rcx, [rbp+var_10]
0x180678862  mov     rax, [rcx]
0x180678865  mov     rax, [rax+10h]
0x180678869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067886e  mov     rcx, [rbp+var_28]
0x180678872  mov     rax, [rcx]
0x180678875  mov     rax, [rax+10h]
0x180678879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18067887e  mov     rcx, [rbp+pszStr1]; pv
0x180678882  call    cs:__imp_CoTaskMemFree
0x180678888  mov     rcx, [rbp+ppv]
0x18067888c  mov     rax, [rcx]
0x18067888f  mov     rax, [rax+10h]
0x180678893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180678898  mov     eax, edi
0x18067889a  mov     rcx, [rbp+var_8]
0x18067889e  xor     rcx, rsp; StackCookie
0x1806788a1  call    __security_check_cookie
0x1806788a6  mov     rbx, [rsp+70h+arg_18]
0x1806788ae  add     rsp, 70h
0x1806788b2  pop     r15
0x1806788b4  pop     r14
0x1806788b6  pop     r13
0x1806788b8  pop     r12
0x1806788ba  pop     rdi
0x1806788bb  pop     rsi
0x1806788bc  pop     rbp
0x1806788bd  retn
```
