# CScopePicker::_FindChildNode(_TREEITEM *,ushort const *,_TREEITEM * *)

- ea: `0x18002506c`
- end: `0x1800251c8`
- name: `?_FindChildNode@CScopePicker@@AEAAJPEAU_TREEITEM@@PEBGPEAPEAU2@@Z`
- size: `348`
- prototype: `__int64 __fastcall(HWND *this, struct _TREEITEM *, const unsigned __int16 *, struct _TREEITEM **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002506c`
- `0x180025808`

## callees

- `0x18001a220`
- `0x1800248f0`
- `0x18002506c`
- `0x1800251d0`
- `0x180025b24`
- `0x18002d324`
- `0x18002da3c`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x1800250be`
- `SHELL32!__imp_ILFree` at `0x1800250be`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002512e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002512e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800251ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800251ab`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025176`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025176`

## pseudocode

```c
__int64 __fastcall CScopePicker::_FindChildNode(
        HWND *this,
        struct _TREEITEM *a2,
        const unsigned __int16 *a3,
        struct _TREEITEM **a4)
{
  struct _TREEITEM *v6; // rsi
  int PidlAbs; // eax
  CShellWrappers *v9; // rcx
  int PathFromAbsPidl; // ebx
  struct STreeNodeState *Param; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  WPARAM i; // r8
  struct _TREEITEM *v17; // rax
  LPITEMIDLIST pidl; // [rsp+30h] [rbp-48h] BYREF
  PCNZWCH lpString1; // [rsp+38h] [rbp-40h] BYREF

  pidl = 0;
  v6 = a2;
  PidlAbs = CScopePicker::_GetPidlAbs((CScopePicker *)this, a2, (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
  lpString1 = 0;
  if ( PidlAbs < 0 )
  {
    if ( pidl )
      return 1;
  }
  else if ( pidl )
  {
    PathFromAbsPidl = CShellWrappers::GetPathFromAbsPidl(
                        v9,
                        (const struct _ITEMIDLIST_ABSOLUTE *)pidl,
                        (unsigned __int16 **)&lpString1);
    ILFree(pidl);
    goto LABEL_9;
  }
  Param = TreeView_GetParam(this[3], v6);
  if ( !Param )
    return 1;
  v14 = *((_QWORD *)Param + 1);
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v14 + 2 * v15) );
  PathFromAbsPidl = _AllocStringWorker<CTCoAllocPolicy>(v13, v12, v14, v15);
LABEL_9:
  if ( PathFromAbsPidl < 0 )
    return 1;
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, a3, -1) == 2 )
  {
    *a4 = v6;
  }
  else if ( (unsigned int)CShellWrappers::IsPathParent(lpString1, a3) )
  {
    PathFromAbsPidl = CScopePicker::_OnExpandItem((CScopePicker *)this, v6);
    if ( PathFromAbsPidl >= 0 )
    {
      PathFromAbsPidl = 1;
      for ( i = 4; ; i = 1 )
      {
        v17 = (struct _TREEITEM *)SendMessageW(this[3], 0x110Au, i, (LPARAM)v6);
        v6 = v17;
        if ( !v17 )
          break;
        PathFromAbsPidl = CScopePicker::_FindChildNode((CScopePicker *)this, v17, a3, a4);
        if ( PathFromAbsPidl != 1 )
          break;
      }
    }
  }
  else
  {
    PathFromAbsPidl = 1;
  }
  CoTaskMemFree((LPVOID)lpString1);
  return (unsigned int)PathFromAbsPidl;
}

```

## disassembly

```asm
0x18002506c  push    rbx
0x18002506e  push    rbp
0x18002506f  push    rsi
0x180025070  push    r12
0x180025072  push    r13
0x180025074  push    r15
0x180025076  sub     rsp, 48h
0x18002507a  mov     r15, r8
0x18002507d  xor     r13d, r13d
0x180025080  lea     r8, [rsp+78h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180025085  mov     [rsp+78h+pidl], r13
0x18002508a  mov     r12, r9
0x18002508d  mov     rsi, rdx
0x180025090  mov     rbp, rcx
0x180025093  call    ?_GetPidlAbs@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CScopePicker::_GetPidlAbs(_TREEITEM *,_ITEMIDLIST_ABSOLUTE * *)
0x180025098  mov     [rsp+78h+lpString1], r13
0x18002509d  test    eax, eax
0x18002509f  js      short loc_1800250C6
0x1800250a1  cmp     [rsp+78h+pidl], r13
0x1800250a6  jz      short loc_1800250D1
0x1800250a8  mov     rdx, [rsp+78h+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x1800250ad  lea     r8, [rsp+78h+lpString1]; unsigned __int16 **
0x1800250b2  call    ?GetPathFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAG@Z; CShellWrappers::GetPathFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ushort * *)
0x1800250b7  mov     rcx, [rsp+78h+pidl]; pidl
0x1800250bc  mov     ebx, eax
0x1800250be  call    cs:__imp_ILFree
0x1800250c4  jmp     short loc_180025109
0x1800250c6  cmp     [rsp+78h+pidl], r13
0x1800250cb  jnz     loc_1800251B3
0x1800250d1  mov     rcx, [rbp+18h]; HWND
0x1800250d5  mov     rdx, rsi; struct _TREEITEM *
0x1800250d8  call    ?TreeView_GetParam@@YAPEAUSTreeNodeState@@PEAUHWND__@@PEAU_TREEITEM@@@Z; TreeView_GetParam(HWND__ *,_TREEITEM *)
0x1800250dd  test    rax, rax
0x1800250e0  jz      loc_1800251B3
0x1800250e6  mov     r8, [rax+8]
0x1800250ea  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800250ee  inc     r9
0x1800250f1  cmp     [r8+r9*2], r13w
0x1800250f6  jnz     short loc_1800250EE
0x1800250f8  lea     rax, [rsp+78h+lpString1]
0x1800250fd  mov     qword ptr [rsp+78h+cchCount2], rax
0x180025102  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180025107  mov     ebx, eax
0x180025109  test    ebx, ebx
0x18002510b  js      loc_1800251B3
0x180025111  mov     r8, [rsp+78h+lpString1]; lpString1
0x180025116  or      r9d, 0FFFFFFFFh; cchCount1
0x18002511a  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x180025122  mov     [rsp+78h+lpString2], r15; lpString2
0x180025127  lea     edx, [r9+2]; dwCmpFlags
0x18002512b  lea     ecx, [rdx+7Eh]; Locale
0x18002512e  call    cs:__imp_CompareStringW
0x180025134  cmp     eax, 2
0x180025137  jnz     short loc_18002513F
0x180025139  mov     [r12], rsi
0x18002513d  jmp     short loc_1800251A6
0x18002513f  mov     rcx, [rsp+78h+lpString1]; lpString1
0x180025144  mov     rdx, r15; lpString2
0x180025147  call    ?IsPathParent@CShellWrappers@@SAHPEBG0@Z; CShellWrappers::IsPathParent(ushort const *,ushort const *)
0x18002514c  test    eax, eax
0x18002514e  jz      short loc_1800251A1
0x180025150  mov     rdx, rsi; struct _TREEITEM *
0x180025153  mov     rcx, rbp; this
0x180025156  call    ?_OnExpandItem@CScopePicker@@AEAAJPEAU_TREEITEM@@@Z; CScopePicker::_OnExpandItem(_TREEITEM *)
0x18002515b  mov     ebx, eax
0x18002515d  test    eax, eax
0x18002515f  js      short loc_1800251A6
0x180025161  mov     ebx, 1
0x180025166  lea     r8d, [rbx+3]; wParam
0x18002516a  mov     rcx, [rbp+18h]; hWnd
0x18002516e  mov     r9, rsi; lParam
0x180025171  mov     edx, 110Ah; Msg
0x180025176  call    cs:__imp_SendMessageW
0x18002517c  mov     rsi, rax
0x18002517f  test    rax, rax
0x180025182  jz      short loc_1800251A6
0x180025184  mov     r9, r12; struct _TREEITEM **
0x180025187  mov     r8, r15; unsigned __int16 *
0x18002518a  mov     rdx, rax; struct _TREEITEM *
0x18002518d  mov     rcx, rbp; this
0x180025190  call    ?_FindChildNode@CScopePicker@@AEAAJPEAU_TREEITEM@@PEBGPEAPEAU2@@Z; CScopePicker::_FindChildNode(_TREEITEM *,ushort const *,_TREEITEM * *)
0x180025195  mov     ebx, eax
0x180025197  cmp     eax, 1
0x18002519a  jnz     short loc_1800251A6
0x18002519c  mov     r8d, eax
0x18002519f  jmp     short loc_18002516A
0x1800251a1  mov     ebx, 1
0x1800251a6  mov     rcx, [rsp+78h+lpString1]; pv
0x1800251ab  call    cs:__imp_CoTaskMemFree
0x1800251b1  jmp     short loc_1800251B8
0x1800251b3  mov     ebx, 1
0x1800251b8  mov     eax, ebx
0x1800251ba  add     rsp, 48h
0x1800251be  pop     r15
0x1800251c0  pop     r13
0x1800251c2  pop     r12
0x1800251c4  pop     rsi
0x1800251c5  pop     rbp
0x1800251c6  pop     rbx
0x1800251c7  retn
```
