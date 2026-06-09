# CScopePicker::_IsUniqueOrphan(ushort const *,_TREEITEM * *)

- ea: `0x180025540`
- end: `0x180025740`
- name: `?_IsUniqueOrphan@CScopePicker@@AEAAJPEBGPEAPEAU_TREEITEM@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(HWND *this, PCNZWCH lpString2, struct _TREEITEM **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024260`
- `0x180024360`

## callees

- `0x1800248f0`
- `0x1800251d0`
- `0x180025540`
- `0x18002d324`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180025603`
- `SHELL32!__imp_ILFree` at `0x180025603`
- `SHLWAPI!SHStrDupW` at `0x180025614`
- `SHLWAPI!SHStrDupW` at `0x180025614`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002564f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002567b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800256a7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002564f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002567b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800256a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002570c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002570c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025585`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800256c5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800256dd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800256f7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180025585`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800256c5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800256dd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800256f7`

## pseudocode

```c
__int64 __fastcall CScopePicker::_IsUniqueOrphan(HWND *this, PCNZWCH lpString2, struct _TREEITEM **a3)
{
  __int64 cchCount2; // rsi
  struct _TREEITEM *v7; // rbp
  int PidlAbs; // edi
  HWND v9; // rcx
  struct STreeNodeState *Param; // rax
  CShellWrappers *v11; // rcx
  const WCHAR *v12; // r8
  __int64 v13; // rbx
  bool v14; // cc
  LRESULT v15; // rax
  LPARAM v16; // r9
  LPWSTR ppwsz; // [rsp+70h] [rbp+8h] BYREF
  LPITEMIDLIST pidl; // [rsp+80h] [rbp+18h] BYREF

  if ( a3 )
    *a3 = 0;
  cchCount2 = -1;
  do
    ++cchCount2;
  while ( lpString2[cchCount2] );
  v7 = (struct _TREEITEM *)SendMessageW(this[3], 0x110Au, 0, 0);
  PidlAbs = 0;
  while ( PidlAbs >= 0 )
  {
    if ( !v7 )
      return 0;
    v9 = this[3];
    ppwsz = 0;
    Param = TreeView_GetParam(v9, v7);
    if ( Param )
    {
      if ( *((_DWORD *)Param + 7) )
      {
        pidl = 0;
        PidlAbs = CScopePicker::_GetPidlAbs(this, v7, &pidl);
        if ( PidlAbs < 0 )
          goto LABEL_27;
        PidlAbs = CShellWrappers::GetPathFromAbsPidl(v11, (const struct _ITEMIDLIST_ABSOLUTE *)pidl, &ppwsz);
        ILFree(pidl);
      }
      else
      {
        PidlAbs = SHStrDupW(*((LPCWSTR *)Param + 1), &ppwsz);
      }
      if ( PidlAbs >= 0 )
      {
        v12 = ppwsz;
        v13 = -1;
        do
          ++v13;
        while ( ppwsz[v13] );
        v14 = (int)cchCount2 <= (int)v13;
        if ( (_DWORD)cchCount2 == (_DWORD)v13 )
        {
          if ( CompareStringW(0x7Fu, 1u, ppwsz, v13, lpString2, cchCount2) == 2 )
            goto LABEL_28;
          v12 = ppwsz;
          v14 = (int)cchCount2 <= (int)v13;
        }
        if ( !v14 )
        {
          if ( CompareStringW(0x7Fu, 1u, v12, v13, lpString2, v13) == 2 )
          {
LABEL_28:
            PidlAbs = 1;
            if ( a3 )
              *a3 = v7;
            return (unsigned int)PidlAbs;
          }
          v12 = ppwsz;
        }
        if ( (int)cchCount2 < (int)v13 && CompareStringW(0x7Fu, 1u, v12, cchCount2, lpString2, cchCount2) == 2 )
        {
          v15 = SendMessageW(this[3], 0x110Au, 1u, (LPARAM)v7);
          v16 = (LPARAM)v7;
          v7 = (struct _TREEITEM *)v15;
          SendMessageW(this[3], 0x1101u, 0, v16);
        }
        else
        {
          v7 = (struct _TREEITEM *)SendMessageW(this[3], 0x110Au, 1u, (LPARAM)v7);
        }
      }
    }
    else
    {
      PidlAbs = -2147024809;
    }
LABEL_27:
    CoTaskMemFree(ppwsz);
  }
  return (unsigned int)PidlAbs;
}

```

## disassembly

```asm
0x180025540  mov     [rsp+arg_8], rbx
0x180025545  push    rbp
0x180025546  push    rsi
0x180025547  push    rdi
0x180025548  push    r12
0x18002554a  push    r13
0x18002554c  push    r14
0x18002554e  push    r15
0x180025550  sub     rsp, 30h
0x180025554  xor     r13d, r13d
0x180025557  mov     r14, r8
0x18002555a  mov     r12, rdx
0x18002555d  mov     r15, rcx
0x180025560  test    r8, r8
0x180025563  jz      short loc_180025568
0x180025565  mov     [r8], r13
0x180025568  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002556c  inc     rsi
0x18002556f  cmp     [rdx+rsi*2], r13w
0x180025574  jnz     short loc_18002556C
0x180025576  mov     rcx, [rcx+18h]; hWnd
0x18002557a  xor     r9d, r9d; lParam
0x18002557d  xor     r8d, r8d; wParam
0x180025580  mov     edx, 110Ah; Msg
0x180025585  call    cs:__imp_SendMessageW
0x18002558b  mov     rbp, rax
0x18002558e  mov     edi, r13d
0x180025591  test    edi, edi
0x180025593  js      loc_180025729
0x180025599  test    rbp, rbp
0x18002559c  jz      loc_180025726
0x1800255a2  mov     rcx, [r15+18h]; HWND
0x1800255a6  mov     rdx, rbp; struct _TREEITEM *
0x1800255a9  mov     [rsp+68h+ppwsz], r13
0x1800255ae  call    ?TreeView_GetParam@@YAPEAUSTreeNodeState@@PEAUHWND__@@PEAU_TREEITEM@@@Z; TreeView_GetParam(HWND__ *,_TREEITEM *)
0x1800255b3  test    rax, rax
0x1800255b6  jz      loc_180025702
0x1800255bc  cmp     [rax+1Ch], r13d
0x1800255c0  jz      short loc_18002560B
0x1800255c2  lea     r8, [rsp+68h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x1800255ca  mov     [rsp+68h+pidl], r13
0x1800255d2  mov     rdx, rbp; struct _TREEITEM *
0x1800255d5  mov     rcx, r15; this
0x1800255d8  call    ?_GetPidlAbs@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CScopePicker::_GetPidlAbs(_TREEITEM *,_ITEMIDLIST_ABSOLUTE * *)
0x1800255dd  mov     edi, eax
0x1800255df  test    eax, eax
0x1800255e1  js      loc_180025707
0x1800255e7  mov     rdx, [rsp+68h+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x1800255ef  lea     r8, [rsp+68h+ppwsz]; unsigned __int16 **
0x1800255f4  call    ?GetPathFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAG@Z; CShellWrappers::GetPathFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ushort * *)
0x1800255f9  mov     rcx, [rsp+68h+pidl]; pidl
0x180025601  mov     edi, eax
0x180025603  call    cs:__imp_ILFree
0x180025609  jmp     short loc_18002561C
0x18002560b  mov     rcx, [rax+8]; psz
0x18002560f  lea     rdx, [rsp+68h+ppwsz]; ppwsz
0x180025614  call    cs:__imp_SHStrDupW
0x18002561a  mov     edi, eax
0x18002561c  test    edi, edi
0x18002561e  js      loc_180025707
0x180025624  mov     r8, [rsp+68h+ppwsz]; lpString1
0x180025629  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002562d  inc     rbx
0x180025630  cmp     [r8+rbx*2], r13w
0x180025635  jnz     short loc_18002562D
0x180025637  cmp     esi, ebx
0x180025639  jnz     short loc_180025665
0x18002563b  mov     edx, 1; dwCmpFlags
0x180025640  mov     [rsp+68h+cchCount2], esi; cchCount2
0x180025644  mov     r9d, ebx; cchCount1
0x180025647  mov     [rsp+68h+lpString2], r12; lpString2
0x18002564c  lea     ecx, [rdx+7Eh]; Locale
0x18002564f  call    cs:__imp_CompareStringW
0x180025655  cmp     eax, 2
0x180025658  jz      loc_180025717
0x18002565e  mov     r8, [rsp+68h+ppwsz]; lpString1
0x180025663  cmp     esi, ebx
0x180025665  jle     short loc_18002568F
0x180025667  mov     edx, 1; dwCmpFlags
0x18002566c  mov     [rsp+68h+cchCount2], ebx; cchCount2
0x180025670  mov     r9d, ebx; cchCount1
0x180025673  mov     [rsp+68h+lpString2], r12; lpString2
0x180025678  lea     ecx, [rdx+7Eh]; Locale
0x18002567b  call    cs:__imp_CompareStringW
0x180025681  cmp     eax, 2
0x180025684  jz      loc_180025717
0x18002568a  mov     r8, [rsp+68h+ppwsz]; lpString1
0x18002568f  cmp     esi, ebx
0x180025691  jge     short loc_1800256E5
0x180025693  mov     edx, 1; dwCmpFlags
0x180025698  mov     [rsp+68h+cchCount2], esi; cchCount2
0x18002569c  mov     r9d, esi; cchCount1
0x18002569f  mov     [rsp+68h+lpString2], r12; lpString2
0x1800256a4  lea     ecx, [rdx+7Eh]; Locale
0x1800256a7  call    cs:__imp_CompareStringW
0x1800256ad  cmp     eax, 2
0x1800256b0  jnz     short loc_1800256E5
0x1800256b2  mov     rcx, [r15+18h]; hWnd
0x1800256b6  lea     r8d, [rax-1]; wParam
0x1800256ba  mov     r9, rbp; lParam
0x1800256bd  mov     edx, 110Ah; Msg
0x1800256c2  mov     rbx, rbp
0x1800256c5  call    cs:__imp_SendMessageW
0x1800256cb  mov     rcx, [r15+18h]; hWnd
0x1800256cf  mov     r9, rbx; lParam
0x1800256d2  xor     r8d, r8d; wParam
0x1800256d5  mov     edx, 1101h; Msg
0x1800256da  mov     rbp, rax
0x1800256dd  call    cs:__imp_SendMessageW
0x1800256e3  jmp     short loc_180025707
0x1800256e5  mov     rcx, [r15+18h]; hWnd
0x1800256e9  mov     r9, rbp; lParam
0x1800256ec  mov     edx, 110Ah; Msg
0x1800256f1  mov     r8d, 1; wParam
0x1800256f7  call    cs:__imp_SendMessageW
0x1800256fd  mov     rbp, rax
0x180025700  jmp     short loc_180025707
0x180025702  mov     edi, 80070057h
0x180025707  mov     rcx, [rsp+68h+ppwsz]; pv
0x18002570c  call    cs:__imp_CoTaskMemFree
0x180025712  jmp     loc_180025591
0x180025717  mov     edi, 1
0x18002571c  test    r14, r14
0x18002571f  jz      short loc_180025729
0x180025721  mov     [r14], rbp
0x180025724  jmp     short loc_180025729
0x180025726  mov     edi, r13d
0x180025729  mov     rbx, [rsp+68h+arg_8]
0x18002572e  mov     eax, edi
0x180025730  add     rsp, 30h
0x180025734  pop     r15
0x180025736  pop     r14
0x180025738  pop     r13
0x18002573a  pop     r12
0x18002573c  pop     rdi
0x18002573d  pop     rsi
0x18002573e  pop     rbp
0x18002573f  retn
```
