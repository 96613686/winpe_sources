# CScopePicker::_UpdateStateIconRec(_TREEITEM *)

- ea: `0x180026b6c`
- end: `0x180026c69`
- name: `?_UpdateStateIconRec@CScopePicker@@AEAAJPEAU_TREEITEM@@@Z`
- size: `253`
- prototype: `__int64 __fastcall(CScopePicker *__hidden this, struct _TREEITEM *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800268f8`
- `0x180026b6c`

## callees

- `0x18000dd40`
- `0x1800251d0`
- `0x180026b10`
- `0x180026b6c`
- `0x18002d324`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180026c0b`
- `SHELL32!__imp_ILFree` at `0x180026c0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026c00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026c00`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026b89`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026c4e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026b89`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026c4e`

## pseudocode

```c
__int64 __fastcall CScopePicker::_UpdateStateIconRec(HWND *this, struct _TREEITEM *a2)
{
  int PidlAbs; // ebx
  struct _TREEITEM *v4; // rdi
  CShellWrappers *v5; // rcx
  int v7; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+18h] BYREF
  LPITEMIDLIST pidl; // [rsp+58h] [rbp+20h] BYREF

  PidlAbs = 0;
  v4 = (struct _TREEITEM *)SendMessageW(this[3], 0x110Au, 4u, (LPARAM)a2);
  do
  {
    if ( !v4 )
      break;
    v7 = 0;
    pidl = 0;
    PidlAbs = CScopePicker::_GetPidlAbs((CScopePicker *)this, v4, (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
    if ( PidlAbs >= 0 )
    {
      pv = 0;
      PidlAbs = CShellWrappers::GetPathFromAbsPidl(
                  v5,
                  (const struct _ITEMIDLIST_ABSOLUTE *)pidl,
                  (unsigned __int16 **)&pv);
      if ( PidlAbs >= 0 )
      {
        PidlAbs = CCrawlScopeManagerWrapper::IncludedOrNot(
                    (CCrawlScopeManagerWrapper *)(this + 415),
                    (const unsigned __int16 *)pv,
                    &v7,
                    0);
        CoTaskMemFree(pv);
      }
      ILFree(pidl);
      if ( PidlAbs >= 0 )
      {
        CScopePicker::_UpdateStateIcon(this, v4, (unsigned int)(v7 != 0) + 1);
        PidlAbs = CScopePicker::_UpdateStateIconRec((CScopePicker *)this, v4);
      }
    }
    v4 = (struct _TREEITEM *)SendMessageW(this[3], 0x110Au, 1u, (LPARAM)v4);
  }
  while ( PidlAbs >= 0 );
  return (unsigned int)PidlAbs;
}

```

## disassembly

```asm
0x180026b6c  push    rbx
0x180026b6e  push    rsi
0x180026b6f  push    rdi
0x180026b70  sub     rsp, 20h
0x180026b74  xor     ebx, ebx
0x180026b76  mov     rsi, rcx
0x180026b79  mov     rcx, [rcx+18h]; hWnd
0x180026b7d  mov     r9, rdx; lParam
0x180026b80  mov     edx, 110Ah; Msg
0x180026b85  lea     r8d, [rbx+4]; wParam
0x180026b89  call    cs:__imp_SendMessageW
0x180026b8f  mov     rdi, rax
0x180026b92  test    rdi, rdi
0x180026b95  jz      loc_180026C5F
0x180026b9b  lea     r8, [rsp+38h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180026ba0  mov     [rsp+38h+arg_0], 0
0x180026ba8  mov     rdx, rdi; struct _TREEITEM *
0x180026bab  mov     [rsp+38h+pidl], 0
0x180026bb4  mov     rcx, rsi; this
0x180026bb7  call    ?_GetPidlAbs@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CScopePicker::_GetPidlAbs(_TREEITEM *,_ITEMIDLIST_ABSOLUTE * *)
0x180026bbc  mov     ebx, eax
0x180026bbe  test    eax, eax
0x180026bc0  js      short loc_180026C3C
0x180026bc2  mov     rdx, [rsp+38h+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x180026bc7  lea     r8, [rsp+38h+pv]; unsigned __int16 **
0x180026bcc  mov     [rsp+38h+pv], 0
0x180026bd5  call    ?GetPathFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAG@Z; CShellWrappers::GetPathFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ushort * *)
0x180026bda  mov     ebx, eax
0x180026bdc  test    eax, eax
0x180026bde  js      short loc_180026C06
0x180026be0  mov     rdx, [rsp+38h+pv]; unsigned __int16 *
0x180026be5  lea     rcx, [rsi+0CF8h]; this
0x180026bec  xor     r9d, r9d; enum __MIDL___MIDL_itf_searchapi_0000_0013_0001 *
0x180026bef  lea     r8, [rsp+38h+arg_0]; int *
0x180026bf4  call    ?IncludedOrNot@CCrawlScopeManagerWrapper@@QEAAJPEBGPEAHPEAW4__MIDL___MIDL_itf_searchapi_0000_0013_0001@@@Z; CCrawlScopeManagerWrapper::IncludedOrNot(ushort const *,int *,__MIDL___MIDL_itf_searchapi_0000_0013_0001 *)
0x180026bf9  mov     rcx, [rsp+38h+pv]; pv
0x180026bfe  mov     ebx, eax
0x180026c00  call    cs:__imp_CoTaskMemFree
0x180026c06  mov     rcx, [rsp+38h+pidl]; pidl
0x180026c0b  call    cs:__imp_ILFree
0x180026c11  test    ebx, ebx
0x180026c13  js      short loc_180026C3C
0x180026c15  mov     eax, [rsp+38h+arg_0]
0x180026c19  mov     rdx, rdi
0x180026c1c  neg     eax
0x180026c1e  mov     rcx, rsi
0x180026c21  sbb     r8d, r8d
0x180026c24  neg     r8d
0x180026c27  inc     r8d
0x180026c2a  call    ?_UpdateStateIcon@CScopePicker@@AEAAXPEAU_TREEITEM@@W4_TREE_ITEM_CHECK@@@Z; CScopePicker::_UpdateStateIcon(_TREEITEM *,_TREE_ITEM_CHECK)
0x180026c2f  mov     rdx, rdi; struct _TREEITEM *
0x180026c32  mov     rcx, rsi; this
0x180026c35  call    ?_UpdateStateIconRec@CScopePicker@@AEAAJPEAU_TREEITEM@@@Z; CScopePicker::_UpdateStateIconRec(_TREEITEM *)
0x180026c3a  mov     ebx, eax
0x180026c3c  mov     rcx, [rsi+18h]; hWnd
0x180026c40  mov     r9, rdi; lParam
0x180026c43  mov     edx, 110Ah; Msg
0x180026c48  mov     r8d, 1; wParam
0x180026c4e  call    cs:__imp_SendMessageW
0x180026c54  mov     rdi, rax
0x180026c57  test    ebx, ebx
0x180026c59  jns     loc_180026B92
0x180026c5f  mov     eax, ebx
0x180026c61  add     rsp, 20h
0x180026c65  pop     rdi
0x180026c66  pop     rsi
0x180026c67  pop     rbx
0x180026c68  retn
```
