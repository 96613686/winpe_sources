# CScopePicker::_OnStateClick(_TREEITEM *)

- ea: `0x1800268f8`
- end: `0x180026b07`
- name: `?_OnStateClick@CScopePicker@@AEAAJPEAU_TREEITEM@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(HWND *this, struct _TREEITEM *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800263bc`
- `0x180026f30`

## callees

- `0x18000d78c`
- `0x18000dd40`
- `0x18001a220`
- `0x180024148`
- `0x1800246f8`
- `0x1800248f0`
- `0x1800251d0`
- `0x1800268f8`
- `0x180026b10`
- `0x180026b6c`
- `0x18002d324`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x1800269f5`
- `SHELL32!__imp_ILFree` at `0x1800269f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ae8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026929`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026979`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026ad2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026929`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026979`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180026ad2`

## pseudocode

```c
__int64 __fastcall CScopePicker::_OnStateClick(HWND *this, struct _TREEITEM *a2)
{
  int PidlAbs; // ebx
  STreeNodeState *Param; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int16 *v8; // rdi
  __int16 v9; // ax
  __int64 v10; // r8
  __int64 v11; // r9
  CShellWrappers *v12; // rcx
  HWND v13; // rcx
  unsigned __int16 **v15; // [rsp+28h] [rbp-8h]
  unsigned __int16 *v16; // [rsp+60h] [rbp+30h] BYREF
  LPITEMIDLIST pidl; // [rsp+70h] [rbp+40h] BYREF

  SendMessageW(this[3], 0x110Bu, 9u, (LPARAM)a2);
  PidlAbs = 0;
  Param = TreeView_GetParam(this[3], a2);
  if ( (unsigned int)STreeNodeState::IsClickable(Param) )
  {
    v8 = 0;
    v16 = 0;
    if ( *(_DWORD *)(v7 + 28) )
    {
      pidl = 0;
      PidlAbs = CScopePicker::_GetPidlAbs(this, a2, &pidl);
      if ( PidlAbs < 0 )
        goto LABEL_15;
      PidlAbs = CShellWrappers::GetPathFromAbsPidl(v12, (const struct _ITEMIDLIST_ABSOLUTE *)pidl, &v16);
      ILFree(pidl);
    }
    else
    {
      if ( *(_BYTE *)(v7 + 44) )
      {
        v9 = SendMessageW(this[3], 0x1127u, (WPARAM)a2, 61440);
        CScopePicker::_UpdateStateIcon(this, a2, (unsigned int)((v9 & 0xF000) == 4096) + 1);
LABEL_19:
        CoTaskMemFree(v8);
        return (unsigned int)PidlAbs;
      }
      v10 = *(_QWORD *)(v7 + 8);
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      v15 = &v16;
      PidlAbs = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, v10, v11);
    }
    v8 = v16;
    if ( PidlAbs < 0 )
      goto LABEL_19;
    v13 = this[415];
    if ( v13 )
    {
      LODWORD(v16) = 0;
      PidlAbs = (*(__int64 (__fastcall **)(HWND, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v13 + 104LL))(
                  v13,
                  v8,
                  &v16);
      if ( PidlAbs >= 0 )
        PidlAbs = (*(__int64 (__fastcall **)(HWND, unsigned __int16 *, bool, _QWORD, _DWORD, unsigned __int16 **))(*(_QWORD *)this[415] + 56LL))(
                    this[415],
                    v8,
                    (_DWORD)v16 == 0,
                    0,
                    0,
                    v15);
    }
    else
    {
      PidlAbs = -2147467261;
    }
LABEL_15:
    if ( PidlAbs >= 0 )
    {
      LODWORD(v16) = 0;
      PidlAbs = CCrawlScopeManagerWrapper::IncludedOrNot((CCrawlScopeManagerWrapper *)(this + 415), v8, (int *)&v16, 0);
      if ( PidlAbs >= 0 )
      {
        CScopePicker::_UpdateStateIcon(this, a2, (unsigned int)((_DWORD)v16 != 0) + 1);
        PidlAbs = CScopePicker::_UpdateStateIconRec((CScopePicker *)this, a2);
        SearchOptionsTelemetry::ScopeTreeItemClicked<int &>(&v16);
        if ( PidlAbs >= 0 )
        {
          SendMessageW(this[18], 0x1009u, 0, 0);
          PidlAbs = CCrawlScopeManagerWrapper::EnumerateClusions(
                      (CCrawlScopeManagerWrapper *)(this + 415),
                      (struct IClusionConsumer *)(this + 16));
        }
      }
    }
    goto LABEL_19;
  }
  return (unsigned int)PidlAbs;
}

```

## disassembly

```asm
0x1800268f8  mov     [rsp-28h+arg_8], rbx
0x1800268fd  mov     [rsp-28h+arg_18], rsi
0x180026902  push    rbp
0x180026903  push    rdi
0x180026904  push    r12
0x180026906  push    r14
0x180026908  push    r15
0x18002690a  mov     rbp, rsp
0x18002690d  sub     rsp, 30h
0x180026911  mov     r14, rdx
0x180026914  mov     rsi, rcx
0x180026917  mov     rcx, [rcx+18h]; hWnd
0x18002691b  mov     r9, rdx; lParam
0x18002691e  mov     edx, 110Bh; Msg
0x180026923  mov     r8d, 9; wParam
0x180026929  call    cs:__imp_SendMessageW
0x18002692f  mov     rcx, [rsi+18h]; HWND
0x180026933  xor     r12d, r12d
0x180026936  mov     rdx, r14; struct _TREEITEM *
0x180026939  mov     ebx, r12d
0x18002693c  call    ?TreeView_GetParam@@YAPEAUSTreeNodeState@@PEAUHWND__@@PEAU_TREEITEM@@@Z; TreeView_GetParam(HWND__ *,_TREEITEM *)
0x180026941  mov     rcx, rax; this
0x180026944  call    ?IsClickable@STreeNodeState@@QEAAHXZ; STreeNodeState::IsClickable(void)
0x180026949  test    eax, eax
0x18002694b  jz      loc_180026AEE
0x180026951  mov     edi, r12d
0x180026954  mov     [rbp+arg_0], r12
0x180026958  cmp     [rcx+1Ch], r12d
0x18002695c  jnz     short loc_1800269C5
0x18002695e  cmp     [rcx+2Ch], r12b
0x180026962  jz      short loc_1800269A1
0x180026964  mov     rcx, [rsi+18h]; hWnd
0x180026968  mov     r15d, 0F000h
0x18002696e  mov     r9d, r15d; lParam
0x180026971  mov     r8, r14; wParam
0x180026974  mov     edx, 1127h; Msg
0x180026979  call    cs:__imp_SendMessageW
0x18002697f  mov     r8d, r12d
0x180026982  mov     rdx, r14
0x180026985  and     eax, r15d
0x180026988  mov     rcx, rsi
0x18002698b  cmp     eax, 1000h
0x180026990  setz    r8b
0x180026994  inc     r8d
0x180026997  call    ?_UpdateStateIcon@CScopePicker@@AEAAXPEAU_TREEITEM@@W4_TREE_ITEM_CHECK@@@Z; CScopePicker::_UpdateStateIcon(_TREEITEM *,_TREE_ITEM_CHECK)
0x18002699c  jmp     loc_180026AE5
0x1800269a1  mov     r8, [rcx+8]
0x1800269a5  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800269a9  inc     r9
0x1800269ac  cmp     [r8+r9*2], r12w
0x1800269b1  jnz     short loc_1800269A9
0x1800269b3  lea     rax, [rbp+arg_0]
0x1800269b7  mov     [rsp+30h+var_8], rax
0x1800269bc  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800269c1  mov     ebx, eax
0x1800269c3  jmp     short loc_1800269FB
0x1800269c5  lea     r8, [rbp+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x1800269c9  mov     [rbp+pidl], r12
0x1800269cd  mov     rdx, r14; struct _TREEITEM *
0x1800269d0  mov     rcx, rsi; this
0x1800269d3  call    ?_GetPidlAbs@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CScopePicker::_GetPidlAbs(_TREEITEM *,_ITEMIDLIST_ABSOLUTE * *)
0x1800269d8  mov     ebx, eax
0x1800269da  test    eax, eax
0x1800269dc  js      loc_180026A62
0x1800269e2  mov     rdx, [rbp+pidl]; struct _ITEMIDLIST_ABSOLUTE *
0x1800269e6  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x1800269ea  call    ?GetPathFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAG@Z; CShellWrappers::GetPathFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ushort * *)
0x1800269ef  mov     rcx, [rbp+pidl]; pidl
0x1800269f3  mov     ebx, eax
0x1800269f5  call    cs:__imp_ILFree
0x1800269fb  mov     rdi, [rbp+arg_0]
0x1800269ff  test    ebx, ebx
0x180026a01  js      loc_180026AE5
0x180026a07  mov     rcx, [rsi+0CF8h]
0x180026a0e  test    rcx, rcx
0x180026a11  jz      short loc_180026A5D
0x180026a13  mov     dword ptr [rbp+arg_0], r12d
0x180026a17  lea     r8, [rbp+arg_0]
0x180026a1b  mov     rax, [rcx]
0x180026a1e  mov     rdx, rdi
0x180026a21  mov     rax, [rax+68h]
0x180026a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a2a  mov     ebx, eax
0x180026a2c  test    eax, eax
0x180026a2e  js      short loc_180026A62
0x180026a30  mov     rcx, [rsi+0CF8h]
0x180026a37  mov     r8d, r12d
0x180026a3a  cmp     dword ptr [rbp+arg_0], r12d
0x180026a3e  mov     rdx, rdi
0x180026a41  mov     [rsp+30h+var_10], r12d
0x180026a46  setz    r8b
0x180026a4a  xor     r9d, r9d
0x180026a4d  mov     rax, [rcx]
0x180026a50  mov     rax, [rax+38h]
0x180026a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a59  mov     ebx, eax
0x180026a5b  jmp     short loc_180026A62
0x180026a5d  mov     ebx, 80004003h
0x180026a62  test    ebx, ebx
0x180026a64  js      short loc_180026AE5
0x180026a66  lea     r15, [rsi+0CF8h]
0x180026a6d  mov     dword ptr [rbp+arg_0], r12d
0x180026a71  mov     rcx, r15; this
0x180026a74  lea     r8, [rbp+arg_0]; int *
0x180026a78  xor     r9d, r9d; enum __MIDL___MIDL_itf_searchapi_0000_0013_0001 *
0x180026a7b  mov     rdx, rdi; unsigned __int16 *
0x180026a7e  call    ?IncludedOrNot@CCrawlScopeManagerWrapper@@QEAAJPEBGPEAHPEAW4__MIDL___MIDL_itf_searchapi_0000_0013_0001@@@Z; CCrawlScopeManagerWrapper::IncludedOrNot(ushort const *,int *,__MIDL___MIDL_itf_searchapi_0000_0013_0001 *)
0x180026a83  mov     ebx, eax
0x180026a85  test    eax, eax
0x180026a87  js      short loc_180026AE5
0x180026a89  mov     eax, dword ptr [rbp+arg_0]
0x180026a8c  mov     rdx, r14
0x180026a8f  neg     eax
0x180026a91  mov     rcx, rsi
0x180026a94  sbb     r8d, r8d
0x180026a97  neg     r8d
0x180026a9a  inc     r8d
0x180026a9d  call    ?_UpdateStateIcon@CScopePicker@@AEAAXPEAU_TREEITEM@@W4_TREE_ITEM_CHECK@@@Z; CScopePicker::_UpdateStateIcon(_TREEITEM *,_TREE_ITEM_CHECK)
0x180026aa2  mov     rdx, r14; struct _TREEITEM *
0x180026aa5  mov     rcx, rsi; this
0x180026aa8  call    ?_UpdateStateIconRec@CScopePicker@@AEAAJPEAU_TREEITEM@@@Z; CScopePicker::_UpdateStateIconRec(_TREEITEM *)
0x180026aad  lea     rcx, [rbp+arg_0]
0x180026ab1  mov     ebx, eax
0x180026ab3  call    ??$ScopeTreeItemClicked@AEAH@SearchOptionsTelemetry@@SAXAEAH@Z; SearchOptionsTelemetry::ScopeTreeItemClicked<int &>(int &)
0x180026ab8  test    ebx, ebx
0x180026aba  js      short loc_180026AE5
0x180026abc  lea     rbx, [rsi+80h]
0x180026ac3  xor     r9d, r9d; lParam
0x180026ac6  mov     rcx, [rbx+10h]; hWnd
0x180026aca  xor     r8d, r8d; wParam
0x180026acd  mov     edx, 1009h; Msg
0x180026ad2  call    cs:__imp_SendMessageW
0x180026ad8  mov     rdx, rbx; struct IClusionConsumer *
0x180026adb  mov     rcx, r15; this
0x180026ade  call    ?EnumerateClusions@CCrawlScopeManagerWrapper@@QEAAJPEAVIClusionConsumer@@@Z; CCrawlScopeManagerWrapper::EnumerateClusions(IClusionConsumer *)
0x180026ae3  mov     ebx, eax
0x180026ae5  mov     rcx, rdi; pv
0x180026ae8  call    cs:__imp_CoTaskMemFree
0x180026aee  mov     rsi, [rsp+30h+arg_18]
0x180026af3  mov     eax, ebx
0x180026af5  mov     rbx, [rsp+30h+arg_8]
0x180026afa  add     rsp, 30h
0x180026afe  pop     r15
0x180026b00  pop     r14
0x180026b02  pop     r12
0x180026b04  pop     rdi
0x180026b05  pop     rbp
0x180026b06  retn
```
