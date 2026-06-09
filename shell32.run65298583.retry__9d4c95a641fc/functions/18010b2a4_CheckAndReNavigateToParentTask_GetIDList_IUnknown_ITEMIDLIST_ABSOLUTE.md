# CheckAndReNavigateToParentTask::_GetIDList(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x18010b2a4`
- end: `0x18010b4eb`
- name: `?_GetIDList@CheckAndReNavigateToParentTask@@AEAAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `583`
- prototype: `int(CheckAndReNavigateToParentTask *__hidden this, struct IUnknown *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18010b040`

## callees

- `0x18004bde8`
- `0x180058b98`
- `0x180073b60`
- `0x18010b2a4`
- `0x1804da710`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18010b3e3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18010b3e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010b4be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010b4be`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18010b439`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18010b439`
- `Windows.Storage!ILClone` at `0x18010b32d`
- `Windows.Storage!ILClone` at `0x18010b32d`
- `Windows.Storage!ILRemoveLastID` at `0x18010b310`
- `Windows.Storage!ILRemoveLastID` at `0x18010b3a5`
- `Windows.Storage!ILRemoveLastID` at `0x18010b310`
- `Windows.Storage!ILRemoveLastID` at `0x18010b3a5`
- `Windows.Storage!ILFree` at `0x18010b36b`
- `Windows.Storage!ILFree` at `0x18010b48c`
- `Windows.Storage!ILFree` at `0x18010b4c7`
- `Windows.Storage!ILFree` at `0x18010b36b`
- `Windows.Storage!ILFree` at `0x18010b48c`
- `Windows.Storage!ILFree` at `0x18010b4c7`
- `Windows.Storage!SHGetNameFromIDList` at `0x18010b3cf`
- `Windows.Storage!SHGetNameFromIDList` at `0x18010b3cf`
- `Windows.Storage!ILIsEqual` at `0x18010b2d9`
- `Windows.Storage!ILIsEqual` at `0x18010b2d9`
- `Windows.Storage!ILFindChild` at `0x18010b357`
- `Windows.Storage!ILFindChild` at `0x18010b357`
- `Windows.Storage!SHGetIDListFromObject` at `0x18010b472`
- `Windows.Storage!SHGetIDListFromObject` at `0x18010b472`
- `Windows.Storage!SHValidateUNC` at `0x18010b3fd`
- `Windows.Storage!SHValidateUNC` at `0x18010b3fd`

## pseudocode

```c
__int64 __fastcall CheckAndReNavigateToParentTask::_GetIDList(
        CheckAndReNavigateToParentTask *this,
        struct IUnknown *a2,
        struct _ITEMIDLIST_ABSOLUTE **a3)
{
  LPCITEMIDLIST *v3; // r14
  const ITEMIDLIST *v5; // rdx
  const ITEMIDLIST *v7; // rcx
  BOOL v9; // eax
  const struct _ITEMIDLIST_RELATIVE *v10; // rcx
  HRESULT v11; // edi
  LPITEMIDLIST v12; // rbx
  LPITEMIDLIST v13; // rax
  void *ppvOut; // [rsp+20h] [rbp-10h] BYREF
  LPITEMIDLIST pidl; // [rsp+70h] [rbp+40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+80h] [rbp+50h] BYREF
  IUnknown *punk; // [rsp+88h] [rbp+58h] BYREF

  v3 = (LPCITEMIDLIST *)((char *)this + 8);
  *a3 = 0;
  v5 = (const ITEMIDLIST *)*((_QWORD *)this + 2);
  v7 = (const ITEMIDLIST *)*((_QWORD *)this + 1);
  pidl = 0;
  v9 = ILIsEqual(v7, v5);
  v10 = (const struct _ITEMIDLIST_RELATIVE *)*((_QWORD *)this + 2);
  if ( v9 )
  {
    v11 = SHILClone(v10, (struct _ITEMIDLIST_RELATIVE **)&pidl);
    if ( (*(_DWORD *)this == 16 || *(_DWORD *)this == 4) && !IsNotifiedItemValid(*((LPCITEMIDLIST *)this + 2)) )
    {
      v12 = pidl;
      ILRemoveLastID(pidl);
    }
    else
    {
      v12 = pidl;
    }
LABEL_17:
    if ( v11 >= 0 )
    {
LABEL_18:
      pidl = 0;
      v11 = SHGetNameFromIDList(v12, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pidl);
      if ( v11 >= 0 )
      {
        if ( !PathIsUNCW(&pidl->mkid.cb) || SHValidateUNC(0, &pidl->mkid.cb, 2u) )
        {
          *a3 = (struct _ITEMIDLIST_ABSOLUTE *)v12;
          v12 = 0;
        }
        else
        {
          v11 = SHILCloneFirst((const struct _ITEMIDLIST_RELATIVE *)v12, a3);
          if ( v11 >= 0 )
          {
            ppvOut = 0;
            if ( IUnknown_QueryService(
                   a2,
                   (const GUID *const)&SID_STopLevelBrowser,
                   &GUID_9536ca39_1acb_4ae6_ad27_2403d04ca28f,
                   &ppvOut) >= 0 )
            {
              punk = 0;
              if ( (*(int (__fastcall **)(void *, GUID *, IUnknown **))(*(_QWORD *)ppvOut + 32LL))(
                     ppvOut,
                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                     &punk) >= 0 )
              {
                ppidl = 0;
                if ( SHGetIDListFromObject(punk, &ppidl) >= 0 )
                {
                  Pidl_Set(v3, ppidl);
                  ILFree(ppidl);
                }
                ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
            }
          }
        }
        CoTaskMemFree(pidl);
      }
      ILFree(v12);
    }
  }
  else
  {
    if ( !v10 )
      return (unsigned int)-2147024809;
    v12 = ILClone((LPCITEMIDLIST)v10);
    pidl = v12;
    v11 = v12 == 0 ? 0x8007000E : 0;
    if ( v12 )
    {
      v13 = ILFindChild(*((LPITEMIDLIST *)this + 2), *v3);
      if ( v13 && v13->mkid.cb )
      {
        ILFree(v12);
        v11 = SHILClone((const struct _ITEMIDLIST_RELATIVE *)*v3, (struct _ITEMIDLIST_RELATIVE **)&pidl);
        if ( v11 < 0 )
          return (unsigned int)v11;
        v12 = pidl;
      }
      if ( !IsNotifiedItemValid(v12) )
      {
        while ( v12 && v12->mkid.cb )
        {
          ILRemoveLastID(v12);
          if ( IsNotifiedItemValid(v12) )
            goto LABEL_17;
        }
      }
      goto LABEL_18;
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18010b2a4  mov     [rsp-38h+arg_8], rbx
0x18010b2a9  push    rbp
0x18010b2aa  push    rsi
0x18010b2ab  push    rdi
0x18010b2ac  push    r12
0x18010b2ae  push    r13
0x18010b2b0  push    r14
0x18010b2b2  push    r15
0x18010b2b4  mov     rbp, rsp
0x18010b2b7  sub     rsp, 30h
0x18010b2bb  xor     r13d, r13d
0x18010b2be  lea     r14, [rcx+8]
0x18010b2c2  mov     [r8], r13
0x18010b2c5  mov     r12, rdx
0x18010b2c8  mov     rdx, [rcx+10h]; pidl2
0x18010b2cc  mov     rsi, rcx
0x18010b2cf  mov     rcx, [r14]; pidl1
0x18010b2d2  mov     r15, r8
0x18010b2d5  mov     [rbp+pidl], r13
0x18010b2d9  call    cs:__imp_ILIsEqual
0x18010b2df  mov     rcx, [rsi+10h]; struct _ITEMIDLIST_RELATIVE *
0x18010b2e3  test    eax, eax
0x18010b2e5  jz      short loc_18010B324
0x18010b2e7  lea     rdx, [rbp+pidl]; struct _ITEMIDLIST_RELATIVE **
0x18010b2eb  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x18010b2f0  cmp     dword ptr [rsi], 10h
0x18010b2f3  mov     edi, eax
0x18010b2f5  jz      short loc_18010B2FC
0x18010b2f7  cmp     dword ptr [rsi], 4
0x18010b2fa  jnz     short loc_18010B31B
0x18010b2fc  mov     rcx, [rsi+10h]; pidl
0x18010b300  call    ?IsNotifiedItemValid@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@@Z; IsNotifiedItemValid(_ITEMIDLIST_ABSOLUTE const *)
0x18010b305  test    al, al
0x18010b307  jnz     short loc_18010B31B
0x18010b309  mov     rbx, [rbp+pidl]
0x18010b30d  mov     rcx, rbx; pidl
0x18010b310  call    cs:__imp_ILRemoveLastID
0x18010b316  jmp     loc_18010B3B7
0x18010b31b  mov     rbx, [rbp+pidl]
0x18010b31f  jmp     loc_18010B3B7
0x18010b324  test    rcx, rcx
0x18010b327  jz      loc_18010B4CF
0x18010b32d  call    cs:__imp_ILClone
0x18010b333  mov     rbx, rax
0x18010b336  mov     [rbp+pidl], rax
0x18010b33a  neg     rax
0x18010b33d  sbb     edi, edi
0x18010b33f  not     edi
0x18010b341  and     edi, 8007000Eh
0x18010b347  test    rbx, rbx
0x18010b34a  jz      loc_18010B4D4
0x18010b350  mov     rdx, [r14]; pidlChild
0x18010b353  mov     rcx, [rsi+10h]; pidlParent
0x18010b357  call    cs:__imp_ILFindChild
0x18010b35d  test    rax, rax
0x18010b360  jz      short loc_18010B38B
0x18010b362  cmp     [rax], r13w
0x18010b366  jz      short loc_18010B38B
0x18010b368  mov     rcx, rbx; pidl
0x18010b36b  call    cs:__imp_ILFree
0x18010b371  mov     rcx, [r14]; struct _ITEMIDLIST_RELATIVE *
0x18010b374  lea     rdx, [rbp+pidl]; struct _ITEMIDLIST_RELATIVE **
0x18010b378  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x18010b37d  mov     edi, eax
0x18010b37f  test    eax, eax
0x18010b381  js      loc_18010B4D4
0x18010b387  mov     rbx, [rbp+pidl]
0x18010b38b  mov     rcx, rbx; pidl
0x18010b38e  call    ?IsNotifiedItemValid@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@@Z; IsNotifiedItemValid(_ITEMIDLIST_ABSOLUTE const *)
0x18010b393  test    al, al
0x18010b395  jnz     short loc_18010B3BF
0x18010b397  test    rbx, rbx
0x18010b39a  jz      short loc_18010B3BF
0x18010b39c  cmp     [rbx], r13w
0x18010b3a0  jz      short loc_18010B3BF
0x18010b3a2  mov     rcx, rbx; pidl
0x18010b3a5  call    cs:__imp_ILRemoveLastID
0x18010b3ab  mov     rcx, rbx; pidl
0x18010b3ae  call    ?IsNotifiedItemValid@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@@Z; IsNotifiedItemValid(_ITEMIDLIST_ABSOLUTE const *)
0x18010b3b3  test    al, al
0x18010b3b5  jz      short loc_18010B397
0x18010b3b7  test    edi, edi
0x18010b3b9  js      loc_18010B4D4
0x18010b3bf  lea     r8, [rbp+pidl]; ppszName
0x18010b3c3  mov     [rbp+pidl], r13
0x18010b3c7  mov     edx, 80028000h; sigdnName
0x18010b3cc  mov     rcx, rbx; pidl
0x18010b3cf  call    cs:__imp_SHGetNameFromIDList
0x18010b3d5  mov     edi, eax
0x18010b3d7  test    eax, eax
0x18010b3d9  js      loc_18010B4C4
0x18010b3df  mov     rcx, [rbp+pidl]; pszPath
0x18010b3e3  call    cs:__imp_PathIsUNCW
0x18010b3e9  test    eax, eax
0x18010b3eb  jz      loc_18010B4B4
0x18010b3f1  mov     rdx, [rbp+pidl]; pszFile
0x18010b3f5  mov     r8d, 2; fConnect
0x18010b3fb  xor     ecx, ecx; hwndOwner
0x18010b3fd  call    cs:__imp_SHValidateUNC
0x18010b403  test    eax, eax
0x18010b405  jnz     loc_18010B4B4
0x18010b40b  mov     rdx, r15; struct _ITEMID_CHILD **
0x18010b40e  mov     rcx, rbx; struct _ITEMIDLIST_RELATIVE *
0x18010b411  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x18010b416  mov     edi, eax
0x18010b418  test    eax, eax
0x18010b41a  js      loc_18010B4BA
0x18010b420  lea     r9, [rbp+ppvOut]; ppvOut
0x18010b424  mov     [rbp+ppvOut], r13
0x18010b428  lea     r8, _GUID_9536ca39_1acb_4ae6_ad27_2403d04ca28f; riid
0x18010b42f  mov     rcx, r12; punk
0x18010b432  lea     rdx, SID_STopLevelBrowser; guidService
0x18010b439  call    cs:__imp_IUnknown_QueryService
0x18010b43f  test    eax, eax
0x18010b441  js      short loc_18010B4BA
0x18010b443  mov     rcx, [rbp+ppvOut]
0x18010b447  lea     r8, [rbp+punk]
0x18010b44b  mov     [rbp+punk], r13
0x18010b44f  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18010b456  mov     rax, [rcx]
0x18010b459  mov     rax, [rax+20h]
0x18010b45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b462  test    eax, eax
0x18010b464  js      short loc_18010B4A2
0x18010b466  mov     rcx, [rbp+punk]; punk
0x18010b46a  lea     rdx, [rbp+ppidl]; ppidl
0x18010b46e  mov     [rbp+ppidl], r13
0x18010b472  call    cs:__imp_SHGetIDListFromObject
0x18010b478  test    eax, eax
0x18010b47a  js      short loc_18010B492
0x18010b47c  mov     rdx, [rbp+ppidl]
0x18010b480  mov     rcx, r14
0x18010b483  call    Pidl_Set
0x18010b488  mov     rcx, [rbp+ppidl]; pidl
0x18010b48c  call    cs:__imp_ILFree
0x18010b492  mov     rcx, [rbp+punk]
0x18010b496  mov     rax, [rcx]
0x18010b499  mov     rax, [rax+10h]
0x18010b49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b4a2  mov     rcx, [rbp+ppvOut]
0x18010b4a6  mov     rax, [rcx]
0x18010b4a9  mov     rax, [rax+10h]
0x18010b4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b4b2  jmp     short loc_18010B4BA
0x18010b4b4  mov     [r15], rbx
0x18010b4b7  mov     rbx, r13
0x18010b4ba  mov     rcx, [rbp+pidl]; pv
0x18010b4be  call    cs:__imp_CoTaskMemFree
0x18010b4c4  mov     rcx, rbx; pidl
0x18010b4c7  call    cs:__imp_ILFree
0x18010b4cd  jmp     short loc_18010B4D4
0x18010b4cf  mov     edi, 80070057h
0x18010b4d4  mov     rbx, [rsp+30h+arg_8]
0x18010b4d9  mov     eax, edi
0x18010b4db  add     rsp, 30h
0x18010b4df  pop     r15
0x18010b4e1  pop     r14
0x18010b4e3  pop     r13
0x18010b4e5  pop     r12
0x18010b4e7  pop     rdi
0x18010b4e8  pop     rsi
0x18010b4e9  pop     rbp
0x18010b4ea  retn
```
