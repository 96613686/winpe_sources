# CScopePicker::_GetPidlAbs(_TREEITEM *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x1800251d0`
- end: `0x180025268`
- name: `?_GetPidlAbs@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(HWND *this, struct _TREEITEM *, LPITEMIDLIST *)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024950`
- `0x18002506c`
- `0x1800251d0`
- `0x180025540`
- `0x18002595c`
- `0x180025b24`
- `0x180025e38`
- `0x1800268f8`
- `0x180026b6c`

## callees

- `0x1800248f0`
- `0x1800251d0`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180025241`
- `SHELL32!__imp_ILCombine` at `0x180025241`
- `SHELL32!__imp_ILFree` at `0x180025256`
- `SHELL32!__imp_ILFree` at `0x180025256`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025205`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025205`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CScopePicker::_GetPidlAbs(HWND *this, struct _TREEITEM *a2, LPITEMIDLIST *a3)
{
  struct _TREEITEM *v6; // rax
  int PidlAbs; // ebx
  LPCITEMIDLIST *Param; // rax
  LPCITEMIDLIST pidl1; // [rsp+50h] [rbp+8h] BYREF

  *a3 = 0;
  pidl1 = 0;
  v6 = (struct _TREEITEM *)SendMessageW(this[3], 0x110Au, 3u, (LPARAM)a2);
  if ( !v6
    || (PidlAbs = CScopePicker::_GetPidlAbs((CScopePicker *)this, v6, (struct _ITEMIDLIST_ABSOLUTE **)&pidl1),
        PidlAbs >= 0) )
  {
    Param = (LPCITEMIDLIST *)TreeView_GetParam(this[3], a2);
    if ( Param )
    {
      PidlAbs = 0;
      *a3 = ILCombine(pidl1, *Param);
    }
    else
    {
      PidlAbs = -2147024809;
    }
  }
  ILFree((LPITEMIDLIST)pidl1);
  return (unsigned int)PidlAbs;
}

```

## disassembly

```asm
0x1800251d0  push    rbx
0x1800251d2  push    rsi
0x1800251d3  push    rdi
0x1800251d4  push    r14
0x1800251d6  sub     rsp, 28h
0x1800251da  mov     qword ptr [r8], 0
0x1800251e1  mov     r14, r8
0x1800251e4  mov     rsi, rdx
0x1800251e7  mov     [rsp+48h+pidl1], 0
0x1800251f0  mov     rdi, rcx
0x1800251f3  mov     r9, rdx; lParam
0x1800251f6  mov     rcx, [rcx+18h]; hWnd
0x1800251fa  mov     edx, 110Ah; Msg
0x1800251ff  mov     r8d, 3; wParam
0x180025205  call    cs:__imp_SendMessageW
0x18002520b  test    rax, rax
0x18002520e  jz      short loc_180025226
0x180025210  lea     r8, [rsp+48h+pidl1]; struct _ITEMIDLIST_ABSOLUTE **
0x180025215  mov     rdx, rax; struct _TREEITEM *
0x180025218  mov     rcx, rdi; this
0x18002521b  call    ?_GetPidlAbs@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CScopePicker::_GetPidlAbs(_TREEITEM *,_ITEMIDLIST_ABSOLUTE * *)
0x180025220  mov     ebx, eax
0x180025222  test    eax, eax
0x180025224  js      short loc_180025251
0x180025226  mov     rcx, [rdi+18h]; HWND
0x18002522a  mov     rdx, rsi; struct _TREEITEM *
0x18002522d  call    ?TreeView_GetParam@@YAPEAUSTreeNodeState@@PEAUHWND__@@PEAU_TREEITEM@@@Z; TreeView_GetParam(HWND__ *,_TREEITEM *)
0x180025232  test    rax, rax
0x180025235  jz      short loc_18002524C
0x180025237  mov     rdx, [rax]; pidl2
0x18002523a  xor     ebx, ebx
0x18002523c  mov     rcx, [rsp+48h+pidl1]; pidl1
0x180025241  call    cs:__imp_ILCombine
0x180025247  mov     [r14], rax
0x18002524a  jmp     short loc_180025251
0x18002524c  mov     ebx, 80070057h
0x180025251  mov     rcx, [rsp+48h+pidl1]; pidl
0x180025256  call    cs:__imp_ILFree
0x18002525c  mov     eax, ebx
0x18002525e  add     rsp, 28h
0x180025262  pop     r14
0x180025264  pop     rdi
0x180025265  pop     rsi
0x180025266  pop     rbx
0x180025267  retn
```
