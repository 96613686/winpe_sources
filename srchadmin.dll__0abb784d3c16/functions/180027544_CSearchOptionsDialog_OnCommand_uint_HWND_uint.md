# CSearchOptionsDialog::_OnCommand(uint,HWND__ *,uint)

- ea: `0x180027544`
- end: `0x1800277a5`
- name: `?_OnCommand@CSearchOptionsDialog@@AEAA_JIPEAUHWND__@@I@Z`
- size: `609`
- prototype: `__int64 __fastcall(CSearchOptionsDialog *this, int, HWND, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028520`

## callees

- `0x1800038ac`
- `0x18001ede4`
- `0x18002716c`
- `0x1800271b0`
- `0x1800271f4`
- `0x180027238`
- `0x180027478`
- `0x180027544`
- `0x180028390`
- `0x180032010`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x1800275d9`
- `ntdll!WinSqmIncrementDWORD` at `0x18002768f`
- `ntdll!WinSqmIncrementDWORD` at `0x18002777f`
- `ntdll!WinSqmIncrementDWORD` at `0x1800275d9`
- `ntdll!WinSqmIncrementDWORD` at `0x18002768f`
- `ntdll!WinSqmIncrementDWORD` at `0x18002777f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800276cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800276cd`

## pseudocode

```c
__int64 __fastcall CSearchOptionsDialog::_OnCommand(CSearchOptionsDialog *this, int a2, HWND a3, int a4)
{
  __int64 v5; // rsi
  int v6; // edx
  int v7; // edx
  int v8; // edx
  HRESULT v9; // eax
  unsigned int v10; // edx
  int v11; // edi
  int v12; // eax
  unsigned int v13; // edx
  HRESULT v14; // edi
  HRESULT v15; // eax
  unsigned int v16; // edx
  HRESULT v17; // eax
  unsigned int v18; // edx
  LPVOID ppv; // [rsp+70h] [rbp+38h] BYREF

  ppv = a3;
  v5 = 0;
  if ( a4 )
    return v5;
  v6 = a2 - 2;
  if ( !v6 )
    return CSearchOptionsDialog::_OnCloseDialog(this);
  v7 = v6 - 404;
  if ( !v7 )
  {
    if ( !*((_DWORD *)this + 431) )
      return v5;
    SearchOptionsTelemetry::ClickModifyScopes();
    ppv = 0;
    v14 = CoCreateInstance(
            &CLSID_IndexedLocationsComWrapper,
            0,
            0x17u,
            &GUID_20076c7e_4851_41ed_9eb8_f4e5f2bb0286,
            &ppv);
    if ( v14 < 0 )
      goto LABEL_27;
    v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, *(_QWORD *)this);
    if ( v14 != 1 )
      goto LABEL_27;
    v15 = CoCreateInstanceAsAdmin(
            *(HWND *)this,
            &CLSID_IndexedLocationsComWrapper,
            &GUID_20076c7e_4851_41ed_9eb8_f4e5f2bb0286,
            &ppv);
    v14 = v15;
    if ( v15 < 0 )
    {
      if ( v15 != -2147023636 )
        goto LABEL_27;
      v17 = ShowErrorMessageBox(*(HWND *)this, v16, -2147023636);
    }
    else
    {
      v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, *(_QWORD *)this);
    }
    v14 = v17;
LABEL_27:
    CSearchOptionsDialog::_SetMainButton(this, 406);
    *((_DWORD *)this + 12) = 0;
    if ( v14 == -2147023170 || v14 == -2147417851 )
    {
      ShowErrorMessageBox(*(HWND *)this, v18, v14);
      CSearchOptionsDialog::_OnCloseDialog(this);
    }
    WinSqmIncrementDWORD(0, 5834, 1);
    goto LABEL_31;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( !*((_DWORD *)this + 430) )
      return v5;
    SearchOptionsTelemetry::ClickAdvancedOptions();
    ppv = 0;
    v9 = CoCreateInstanceAsAdmin(
           *(HWND *)this,
           &CLSID_AdvancedOptionsComWrapper,
           &GUID_20076c7e_4851_41ed_9eb8_f4e5f2bb0286,
           &ppv);
    v11 = v9;
    if ( v9 < 0 )
    {
      if ( v9 != -2147023636 )
        goto LABEL_15;
      v12 = ShowErrorMessageBox(*(HWND *)this, v10, -2147023636);
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, *(_QWORD *)this);
    }
    v11 = v12;
LABEL_15:
    CSearchOptionsDialog::_SetMainButton(this, 407);
    *((_DWORD *)this + 12) = 0;
    if ( v11 == -2147023170 || v11 == -2147417851 )
    {
      ShowErrorMessageBox(*(HWND *)this, v13, v11);
      CSearchOptionsDialog::_OnCloseDialog(this);
    }
    WinSqmIncrementDWORD(0, 5831, 1);
LABEL_31:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return v5;
  }
  if ( v8 == 4 )
  {
    SearchOptionsTelemetry::ClickPauseIndexer();
    CSearchOptionsDialog::_SetMainButton(this, 411);
    ppv = 0;
    if ( CoCreateInstanceAsAdmin(
           *(HWND *)this,
           &CLSID_ShellIndexerAdminComWrapper,
           &GUID_2ed326ed_c4c0_434a_b4ce_fb0318d725a7,
           &ppv) >= 0 )
      (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 900);
    WinSqmIncrementDWORD(0, 4126, 1);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  }
  return v5;
}

```

## disassembly

```asm
0x180027544  mov     [rsp-20h+arg_10], r8
0x180027549  push    rbp
0x18002754a  push    rbx
0x18002754b  push    rsi
0x18002754c  push    rdi
0x18002754d  mov     rbp, rsp
0x180027550  sub     rsp, 38h
0x180027554  mov     rbx, rcx
0x180027557  xor     esi, esi
0x180027559  test    r9d, r9d
0x18002755c  jnz     loc_180027799
0x180027562  sub     edx, 2
0x180027565  jz      loc_180027791
0x18002756b  sub     edx, 194h
0x180027571  jz      loc_18002769B
0x180027577  sub     edx, 1
0x18002757a  jz      short loc_1800275EE
0x18002757c  cmp     edx, 4
0x18002757f  jnz     loc_180027799
0x180027585  call    ?ClickPauseIndexer@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::ClickPauseIndexer(void)
0x18002758a  mov     edx, 19Bh; int
0x18002758f  mov     rcx, rbx; this
0x180027592  call    ?_SetMainButton@CSearchOptionsDialog@@AEAAXH@Z; CSearchOptionsDialog::_SetMainButton(int)
0x180027597  mov     [rbp+arg_10], rsi
0x18002759b  lea     r9, [rbp+arg_10]; void **
0x18002759f  lea     r8, _GUID_2ed326ed_c4c0_434a_b4ce_fb0318d725a7; struct _GUID *
0x1800275a6  lea     rdx, CLSID_ShellIndexerAdminComWrapper; struct _GUID *
0x1800275ad  mov     rcx, [rbx]; HWND
0x1800275b0  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x1800275b5  test    eax, eax
0x1800275b7  js      short loc_1800275CE
0x1800275b9  mov     rcx, [rbp+arg_10]
0x1800275bd  mov     rax, [rcx]
0x1800275c0  mov     edx, 384h
0x1800275c5  mov     rax, [rax+18h]
0x1800275c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275ce  mov     edx, 101Eh
0x1800275d3  xor     ecx, ecx
0x1800275d5  lea     r8d, [rcx+1]
0x1800275d9  call    cs:__imp_WinSqmIncrementDWORD
0x1800275df  nop
0x1800275e0  lea     rcx, [rbp+arg_10]
0x1800275e4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800275e9  jmp     loc_180027799
0x1800275ee  cmp     [rcx+6B8h], esi
0x1800275f4  jz      loc_180027799
0x1800275fa  call    ?ClickAdvancedOptions@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::ClickAdvancedOptions(void)
0x1800275ff  mov     [rbp+arg_10], rsi
0x180027603  lea     r9, [rbp+arg_10]; void **
0x180027607  lea     r8, _GUID_20076c7e_4851_41ed_9eb8_f4e5f2bb0286; struct _GUID *
0x18002760e  lea     rdx, CLSID_AdvancedOptionsComWrapper; struct _GUID *
0x180027615  mov     rcx, [rbx]; HWND
0x180027618  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18002761d  mov     edi, eax
0x18002761f  test    eax, eax
0x180027621  js      short loc_180027638
0x180027623  mov     rcx, [rbp+arg_10]
0x180027627  mov     rax, [rcx]
0x18002762a  mov     rdx, [rbx]
0x18002762d  mov     rax, [rax+18h]
0x180027631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027636  jmp     short loc_18002764B
0x180027638  mov     r8d, 800704ECh; int
0x18002763e  cmp     eax, r8d
0x180027641  jnz     short loc_18002764D
0x180027643  mov     rcx, [rbx]; hWnd
0x180027646  call    ?ShowErrorMessageBox@@YAJPEAUHWND__@@IJ@Z; ShowErrorMessageBox(HWND__ *,uint,long)
0x18002764b  mov     edi, eax
0x18002764d  mov     edx, 197h; int
0x180027652  mov     rcx, rbx; this
0x180027655  call    ?_SetMainButton@CSearchOptionsDialog@@AEAAXH@Z; CSearchOptionsDialog::_SetMainButton(int)
0x18002765a  mov     dword ptr [rbx+30h], 0
0x180027661  cmp     edi, 800706BEh
0x180027667  jz      short loc_180027671
0x180027669  cmp     edi, 80010105h
0x18002766f  jnz     short loc_180027684
0x180027671  mov     r8d, edi; int
0x180027674  mov     rcx, [rbx]; hWnd
0x180027677  call    ?ShowErrorMessageBox@@YAJPEAUHWND__@@IJ@Z; ShowErrorMessageBox(HWND__ *,uint,long)
0x18002767c  mov     rcx, rbx; this
0x18002767f  call    ?_OnCloseDialog@CSearchOptionsDialog@@AEAA_JXZ; CSearchOptionsDialog::_OnCloseDialog(void)
0x180027684  mov     edx, 16C7h
0x180027689  xor     ecx, ecx
0x18002768b  lea     r8d, [rcx+1]
0x18002768f  call    cs:__imp_WinSqmIncrementDWORD
0x180027695  nop
0x180027696  jmp     loc_180027786
0x18002769b  cmp     [rcx+6BCh], esi
0x1800276a1  jz      loc_180027799
0x1800276a7  call    ?ClickModifyScopes@SearchOptionsTelemetry@@SAXXZ; SearchOptionsTelemetry::ClickModifyScopes(void)
0x1800276ac  mov     [rbp+arg_10], rsi
0x1800276b0  lea     rax, [rbp+arg_10]
0x1800276b4  mov     [rsp+38h+ppv], rax; ppv
0x1800276b9  lea     r9, _GUID_20076c7e_4851_41ed_9eb8_f4e5f2bb0286; riid
0x1800276c0  xor     edx, edx; pUnkOuter
0x1800276c2  lea     r8d, [rdx+17h]; dwClsContext
0x1800276c6  lea     rcx, CLSID_IndexedLocationsComWrapper; rclsid
0x1800276cd  call    cs:__imp_CoCreateInstance
0x1800276d3  mov     edi, eax
0x1800276d5  test    eax, eax
0x1800276d7  js      short loc_18002773D
0x1800276d9  mov     rcx, [rbp+arg_10]
0x1800276dd  mov     rax, [rcx]
0x1800276e0  mov     rdx, [rbx]
0x1800276e3  mov     rax, [rax+18h]
0x1800276e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276ec  mov     edi, eax
0x1800276ee  cmp     eax, 1
0x1800276f1  jnz     short loc_18002773D
0x1800276f3  lea     r9, [rbp+arg_10]; void **
0x1800276f7  lea     r8, _GUID_20076c7e_4851_41ed_9eb8_f4e5f2bb0286; struct _GUID *
0x1800276fe  lea     rdx, CLSID_IndexedLocationsComWrapper; struct _GUID *
0x180027705  mov     rcx, [rbx]; HWND
0x180027708  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18002770d  mov     edi, eax
0x18002770f  test    eax, eax
0x180027711  js      short loc_180027728
0x180027713  mov     rcx, [rbp+arg_10]
0x180027717  mov     rax, [rcx]
0x18002771a  mov     rdx, [rbx]
0x18002771d  mov     rax, [rax+18h]
0x180027721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027726  jmp     short loc_18002773B
0x180027728  mov     r8d, 800704ECh; int
0x18002772e  cmp     eax, r8d
0x180027731  jnz     short loc_18002773D
0x180027733  mov     rcx, [rbx]; hWnd
0x180027736  call    ?ShowErrorMessageBox@@YAJPEAUHWND__@@IJ@Z; ShowErrorMessageBox(HWND__ *,uint,long)
0x18002773b  mov     edi, eax
0x18002773d  mov     edx, 196h; int
0x180027742  mov     rcx, rbx; this
0x180027745  call    ?_SetMainButton@CSearchOptionsDialog@@AEAAXH@Z; CSearchOptionsDialog::_SetMainButton(int)
0x18002774a  mov     dword ptr [rbx+30h], 0
0x180027751  cmp     edi, 800706BEh
0x180027757  jz      short loc_180027761
0x180027759  cmp     edi, 80010105h
0x18002775f  jnz     short loc_180027774
0x180027761  mov     r8d, edi; int
0x180027764  mov     rcx, [rbx]; hWnd
0x180027767  call    ?ShowErrorMessageBox@@YAJPEAUHWND__@@IJ@Z; ShowErrorMessageBox(HWND__ *,uint,long)
0x18002776c  mov     rcx, rbx; this
0x18002776f  call    ?_OnCloseDialog@CSearchOptionsDialog@@AEAA_JXZ; CSearchOptionsDialog::_OnCloseDialog(void)
0x180027774  mov     edx, 16CAh
0x180027779  xor     ecx, ecx
0x18002777b  lea     r8d, [rcx+1]
0x18002777f  call    cs:__imp_WinSqmIncrementDWORD
0x180027785  nop
0x180027786  lea     rcx, [rbp+arg_10]
0x18002778a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002778f  jmp     short loc_180027799
0x180027791  call    ?_OnCloseDialog@CSearchOptionsDialog@@AEAA_JXZ; CSearchOptionsDialog::_OnCloseDialog(void)
0x180027796  mov     rsi, rax
0x180027799  mov     rax, rsi
0x18002779c  add     rsp, 38h
0x1800277a0  pop     rdi
0x1800277a1  pop     rsi
0x1800277a2  pop     rbx
0x1800277a3  pop     rbp
0x1800277a4  retn
```
