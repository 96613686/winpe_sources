# CheckAndReNavigateToParentTask::_GetIDList(IUnknown *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180119060`
- end: `0x180119308`
- name: `?_GetIDList@CheckAndReNavigateToParentTask@@AEAAJPEAUIUnknown@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `680`
- prototype: `int(CheckAndReNavigateToParentTask *__hidden this, struct IUnknown *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180118de0`

## callees

- `0x18002931c`
- `0x1800495d4`
- `0x180049790`
- `0x1800497d4`
- `0x180119060`
- `0x180514c60`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1801191cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1801191cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801192d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801192d4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180119232`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180119232`
- `Windows.Storage!ILFindChild` at `0x180119125`
- `Windows.Storage!ILFindChild` at `0x180119125`
- `Windows.Storage!SHValidateUNC` at `0x1801191ec`
- `Windows.Storage!SHValidateUNC` at `0x1801191ec`
- `Windows.Storage!ILClone` at `0x1801190f5`
- `Windows.Storage!ILClone` at `0x1801190f5`
- `Windows.Storage!ILRemoveLastID` at `0x1801190d2`
- `Windows.Storage!ILRemoveLastID` at `0x18011917e`
- `Windows.Storage!ILRemoveLastID` at `0x1801190d2`
- `Windows.Storage!ILRemoveLastID` at `0x18011917e`
- `Windows.Storage!ILFree` at `0x180119140`
- `Windows.Storage!ILFree` at `0x18011929d`
- `Windows.Storage!ILFree` at `0x1801192e3`
- `Windows.Storage!ILFree` at `0x180119140`
- `Windows.Storage!ILFree` at `0x18011929d`
- `Windows.Storage!ILFree` at `0x1801192e3`
- `Windows.Storage!SHGetNameFromIDList` at `0x1801191b2`
- `Windows.Storage!SHGetNameFromIDList` at `0x1801191b2`
- `Windows.Storage!ILIsEqual` at `0x180119095`
- `Windows.Storage!ILIsEqual` at `0x180119095`
- `Windows.Storage!SHGetIDListFromObject` at `0x18011927d`
- `Windows.Storage!SHGetIDListFromObject` at `0x18011927d`

## pseudocode

```c
__int64 __fastcall CheckAndReNavigateToParentTask::_GetIDList(
        LPCITEMIDLIST *this,
        struct IUnknown *a2,
        struct _ITEMIDLIST_ABSOLUTE **a3)
{
  LPCITEMIDLIST *v3; // r15
  BOOL v7; // eax
  const struct _ITEMIDLIST_RELATIVE *v8; // rcx
  HRESULT v9; // edi
  LPITEMIDLIST v10; // rbx
  const struct _ITEMIDLIST_RELATIVE *v11; // rax
  ITEMIDLIST *v12; // rcx
  void *ppvOut; // [rsp+20h] [rbp-10h] BYREF
  LPITEMIDLIST pidl; // [rsp+70h] [rbp+40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+80h] [rbp+50h] BYREF
  IUnknown *punk; // [rsp+88h] [rbp+58h] BYREF

  *a3 = 0;
  v3 = this + 1;
  pidl = 0;
  v7 = ILIsEqual(this[1], this[2]);
  v8 = (const struct _ITEMIDLIST_RELATIVE *)this[2];
  if ( v7 )
  {
    v9 = SHILClone(v8, (struct _ITEMIDLIST_RELATIVE **)&pidl);
    if ( (*(_DWORD *)this == 16 || *(_DWORD *)this == 4) && !IsNotifiedItemValid(this[2]) )
    {
      v10 = pidl;
      ILRemoveLastID(pidl);
    }
    else
    {
      v10 = pidl;
    }
LABEL_15:
    if ( v9 >= 0 )
    {
LABEL_16:
      pidl = 0;
      v9 = SHGetNameFromIDList(v10, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pidl);
      if ( v9 >= 0 )
      {
        if ( !PathIsUNCW(&pidl->mkid.cb) || SHValidateUNC(0, &pidl->mkid.cb, 2u) )
        {
          *a3 = (struct _ITEMIDLIST_ABSOLUTE *)v10;
          v10 = 0;
        }
        else
        {
          v9 = SHILCloneFirst((const struct _ITEMIDLIST_RELATIVE *)v10, a3);
          if ( v9 >= 0 )
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
      ILFree(v10);
    }
  }
  else
  {
    if ( !v8 )
      return (unsigned int)-2147024809;
    v10 = ILClone((LPCITEMIDLIST)v8);
    pidl = v10;
    v9 = v10 == 0 ? 0x8007000E : 0;
    if ( v10 )
    {
      v11 = (const struct _ITEMIDLIST_RELATIVE *)ILFindChild((LPITEMIDLIST)this[2], *v3);
      if ( !(unsigned int)ILIsEmpty(v11) )
      {
        ILFree(v10);
        v9 = SHILClone((const struct _ITEMIDLIST_RELATIVE *)*v3, (struct _ITEMIDLIST_RELATIVE **)&pidl);
        if ( v9 < 0 )
          return (unsigned int)v9;
        v10 = pidl;
      }
      if ( !IsNotifiedItemValid(v10) )
      {
        while ( !(unsigned int)ILIsEmpty((const struct _ITEMIDLIST_RELATIVE *)v10) )
        {
          ILRemoveLastID(v12);
          if ( IsNotifiedItemValid(v10) )
            goto LABEL_15;
        }
      }
      goto LABEL_16;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180119060  push    rbp
0x180119062  push    rbx
0x180119063  push    rsi
0x180119064  push    rdi
0x180119065  push    r12
0x180119067  push    r14
0x180119069  push    r15
0x18011906b  mov     rbp, rsp
0x18011906e  sub     rsp, 30h
0x180119072  mov     qword ptr [r8], 0
0x180119079  lea     r15, [rcx+8]
0x18011907d  mov     r12, rdx
0x180119080  mov     [rbp+pidl], 0
0x180119088  mov     rdx, [rcx+10h]; pidl2
0x18011908c  mov     rsi, rcx
0x18011908f  mov     rcx, [r15]; pidl1
0x180119092  mov     r14, r8
0x180119095  call    cs:__imp_ILIsEqual
0x18011909c  nop     dword ptr [rax+rax+00h]
0x1801190a1  mov     rcx, [rsi+10h]; struct _ITEMIDLIST_RELATIVE *
0x1801190a5  test    eax, eax
0x1801190a7  jz      short loc_1801190EC
0x1801190a9  lea     rdx, [rbp+pidl]; struct _ITEMIDLIST_RELATIVE **
0x1801190ad  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x1801190b2  cmp     dword ptr [rsi], 10h
0x1801190b5  mov     edi, eax
0x1801190b7  jz      short loc_1801190BE
0x1801190b9  cmp     dword ptr [rsi], 4
0x1801190bc  jnz     short loc_1801190E3
0x1801190be  mov     rcx, [rsi+10h]; pidl
0x1801190c2  call    ?IsNotifiedItemValid@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@@Z; IsNotifiedItemValid(_ITEMIDLIST_ABSOLUTE const *)
0x1801190c7  test    al, al
0x1801190c9  jnz     short loc_1801190E3
0x1801190cb  mov     rbx, [rbp+pidl]
0x1801190cf  mov     rcx, rbx; pidl
0x1801190d2  call    cs:__imp_ILRemoveLastID
0x1801190d9  nop     dword ptr [rax+rax+00h]
0x1801190de  jmp     loc_180119196
0x1801190e3  mov     rbx, [rbp+pidl]
0x1801190e7  jmp     loc_180119196
0x1801190ec  test    rcx, rcx
0x1801190ef  jz      loc_1801192F1
0x1801190f5  call    cs:__imp_ILClone
0x1801190fc  nop     dword ptr [rax+rax+00h]
0x180119101  mov     rbx, rax
0x180119104  mov     [rbp+pidl], rax
0x180119108  neg     rax
0x18011910b  sbb     edi, edi
0x18011910d  not     edi
0x18011910f  and     edi, 8007000Eh
0x180119115  test    rbx, rbx
0x180119118  jz      loc_1801192F6
0x18011911e  mov     rdx, [r15]; pidlChild
0x180119121  mov     rcx, [rsi+10h]; pidlParent
0x180119125  call    cs:__imp_ILFindChild
0x18011912c  nop     dword ptr [rax+rax+00h]
0x180119131  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x180119134  call    ?ILIsEmpty@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsEmpty(_ITEMIDLIST_RELATIVE const *)
0x180119139  test    eax, eax
0x18011913b  jnz     short loc_180119166
0x18011913d  mov     rcx, rbx; pidl
0x180119140  call    cs:__imp_ILFree
0x180119147  nop     dword ptr [rax+rax+00h]
0x18011914c  mov     rcx, [r15]; struct _ITEMIDLIST_RELATIVE *
0x18011914f  lea     rdx, [rbp+pidl]; struct _ITEMIDLIST_RELATIVE **
0x180119153  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180119158  mov     edi, eax
0x18011915a  test    eax, eax
0x18011915c  js      loc_1801192F6
0x180119162  mov     rbx, [rbp+pidl]
0x180119166  mov     rcx, rbx; pidl
0x180119169  call    ?IsNotifiedItemValid@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@@Z; IsNotifiedItemValid(_ITEMIDLIST_ABSOLUTE const *)
0x18011916e  test    al, al
0x180119170  jnz     short loc_18011919E
0x180119172  mov     rcx, rbx; struct _ITEMIDLIST_RELATIVE *
0x180119175  call    ?ILIsEmpty@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsEmpty(_ITEMIDLIST_RELATIVE const *)
0x18011917a  test    eax, eax
0x18011917c  jnz     short loc_18011919E
0x18011917e  call    cs:__imp_ILRemoveLastID
0x180119185  nop     dword ptr [rax+rax+00h]
0x18011918a  mov     rcx, rbx; pidl
0x18011918d  call    ?IsNotifiedItemValid@@YA_NPEBU_ITEMIDLIST_ABSOLUTE@@@Z; IsNotifiedItemValid(_ITEMIDLIST_ABSOLUTE const *)
0x180119192  test    al, al
0x180119194  jz      short loc_180119172
0x180119196  test    edi, edi
0x180119198  js      loc_1801192F6
0x18011919e  lea     r8, [rbp+pidl]; ppszName
0x1801191a2  mov     [rbp+pidl], 0
0x1801191aa  mov     edx, 80028000h; sigdnName
0x1801191af  mov     rcx, rbx; pidl
0x1801191b2  call    cs:__imp_SHGetNameFromIDList
0x1801191b9  nop     dword ptr [rax+rax+00h]
0x1801191be  mov     edi, eax
0x1801191c0  test    eax, eax
0x1801191c2  js      loc_1801192E0
0x1801191c8  mov     rcx, [rbp+pidl]; pszPath
0x1801191cc  call    cs:__imp_PathIsUNCW
0x1801191d3  nop     dword ptr [rax+rax+00h]
0x1801191d8  test    eax, eax
0x1801191da  jz      loc_1801192CB
0x1801191e0  mov     rdx, [rbp+pidl]; pszFile
0x1801191e4  mov     r8d, 2; fConnect
0x1801191ea  xor     ecx, ecx; hwndOwner
0x1801191ec  call    cs:__imp_SHValidateUNC
0x1801191f3  nop     dword ptr [rax+rax+00h]
0x1801191f8  test    eax, eax
0x1801191fa  jnz     loc_1801192CB
0x180119200  mov     rdx, r14; struct _ITEMID_CHILD **
0x180119203  mov     rcx, rbx; struct _ITEMIDLIST_RELATIVE *
0x180119206  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x18011920b  mov     edi, eax
0x18011920d  test    eax, eax
0x18011920f  js      loc_1801192D0
0x180119215  lea     r9, [rbp+ppvOut]; ppvOut
0x180119219  mov     [rbp+ppvOut], 0
0x180119221  lea     r8, _GUID_9536ca39_1acb_4ae6_ad27_2403d04ca28f; riid
0x180119228  mov     rcx, r12; punk
0x18011922b  lea     rdx, SID_STopLevelBrowser; guidService
0x180119232  call    cs:__imp_IUnknown_QueryService
0x180119239  nop     dword ptr [rax+rax+00h]
0x18011923e  test    eax, eax
0x180119240  js      loc_1801192D0
0x180119246  mov     rcx, [rbp+ppvOut]
0x18011924a  lea     r8, [rbp+punk]
0x18011924e  mov     [rbp+punk], 0
0x180119256  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18011925d  mov     rax, [rcx]
0x180119260  mov     rax, [rax+20h]
0x180119264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119269  test    eax, eax
0x18011926b  js      short loc_1801192B9
0x18011926d  mov     rcx, [rbp+punk]; punk
0x180119271  lea     rdx, [rbp+ppidl]; ppidl
0x180119275  mov     [rbp+ppidl], 0
0x18011927d  call    cs:__imp_SHGetIDListFromObject
0x180119284  nop     dword ptr [rax+rax+00h]
0x180119289  test    eax, eax
0x18011928b  js      short loc_1801192A9
0x18011928d  mov     rdx, [rbp+ppidl]
0x180119291  mov     rcx, r15
0x180119294  call    Pidl_Set
0x180119299  mov     rcx, [rbp+ppidl]; pidl
0x18011929d  call    cs:__imp_ILFree
0x1801192a4  nop     dword ptr [rax+rax+00h]
0x1801192a9  mov     rcx, [rbp+punk]
0x1801192ad  mov     rax, [rcx]
0x1801192b0  mov     rax, [rax+10h]
0x1801192b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801192b9  mov     rcx, [rbp+ppvOut]
0x1801192bd  mov     rax, [rcx]
0x1801192c0  mov     rax, [rax+10h]
0x1801192c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801192c9  jmp     short loc_1801192D0
0x1801192cb  mov     [r14], rbx
0x1801192ce  xor     ebx, ebx
0x1801192d0  mov     rcx, [rbp+pidl]; pv
0x1801192d4  call    cs:__imp_CoTaskMemFree
0x1801192db  nop     dword ptr [rax+rax+00h]
0x1801192e0  mov     rcx, rbx; pidl
0x1801192e3  call    cs:__imp_ILFree
0x1801192ea  nop     dword ptr [rax+rax+00h]
0x1801192ef  jmp     short loc_1801192F6
0x1801192f1  mov     edi, 80070057h
0x1801192f6  mov     eax, edi
0x1801192f8  add     rsp, 30h
0x1801192fc  pop     r15
0x1801192fe  pop     r14
0x180119300  pop     r12
0x180119302  pop     rdi
0x180119303  pop     rsi
0x180119304  pop     rbx
0x180119305  pop     rbp
0x180119306  retn
```
