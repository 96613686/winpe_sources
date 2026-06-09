# CContentFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x18000b740`
- end: `0x18000ba7b`
- name: `?CreateViewObject@CContentFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `827`
- prototype: `int(CContentFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b740`
- `0x18000d610`
- `0x1800285c8`
- `0x18002ddc8`
- `0x18002ff5c`
- `0x18004663c`
- `0x180078010`

## import_xrefs

- `SHELL32!SHGetIconOverlayIndexW` at `0x18000b786`
- `SHELL32!SHGetIconOverlayIndexW` at `0x18000b798`
- `SHELL32!SHGetIconOverlayIndexW` at `0x18000b786`
- `SHELL32!SHGetIconOverlayIndexW` at `0x18000b798`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18000b9ca`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18000b9ca`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x18000b910`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x18000b910`

## string_xrefs

- `0x18000b77f`: `wpdshext.dll`
- `0x18000b791`: `wpdshext.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall CContentFolder::CreateViewObject(CContentFolder *this, HWND a2, const struct _GUID *a3, void **a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  HRESULT v10; // edi
  __int64 v11; // rax
  const struct std::nothrow_t *v12; // rdx
  PVOID *v13; // rcx
  HRESULT result; // eax
  CContentDropTarget *v15; // rsi
  int v16; // eax
  struct IContextMenuCB *v17; // rax
  IShellFolder *v18; // rax
  SFV_CREATE pcsfv; // [rsp+20h] [rbp-59h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+40h] [rbp-39h] BYREF
  struct IContextMenuCB *v21; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( !a4 )
  {
    v10 = -2147467261;
    goto LABEL_13;
  }
  *a4 = 0;
  SHGetIconOverlayIndexW(L"wpdshext.dll", -681);
  SHGetIconOverlayIndexW(L"wpdshext.dll", -683);
  v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( v8 )
  {
    v9 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v9 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( v9 )
    {
      v10 = -2147467262;
      v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
        v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
      if ( v11
        || !(*(unsigned int (__fastcall **)(char *, _QWORD, const PROPERTYKEY *))(*((_QWORD *)this - 2) + 72LL))(
              (char *)this - 16,
              *((_QWORD *)this + 6),
              &WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_ONLY)
        && !(*(unsigned int (__fastcall **)(char *, _QWORD, const PROPERTYKEY *))(*((_QWORD *)this - 2) + 72LL))(
              (char *)this - 16,
              *((_QWORD *)this + 6),
              &WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_AND_DATA) )
      {
        goto LABEL_13;
      }
      v17 = (struct IContextMenuCB *)operator new(0x60u, v12);
      v21 = v17;
      if ( v17 )
        v15 = CContentDropTarget::CContentDropTarget(
                (CContentDropTarget *)v17,
                (CContentFolder *)((char *)this - 16),
                a2);
      else
        v15 = 0;
      if ( !v15 )
      {
        v10 = -2147024882;
        goto LABEL_13;
      }
      v16 = (**(__int64 (__fastcall ***)(CContentDropTarget *, const struct _GUID *, void **))v15)(v15, a3, a4);
      v10 = v16;
      if ( v16 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)v16);
      (*(void (__fastcall **)(CContentDropTarget *))(*(_QWORD *)v15 + 16LL))(v15);
      goto LABEL_23;
    }
    v21 = 0;
    v10 = CContentFolder::_ContextMenuCBCreate((CContentFolder *)((char *)this - 16), &v21, 1);
    if ( v10 < 0 )
      goto LABEL_41;
    pdcm.hwnd = a2;
    pdcm.pcmcb = v21;
    pdcm.pidlFolder = (LPCITEMIDLIST)*((_QWORD *)this + 6);
    v18 = 0;
    if ( this != (CContentFolder *)16 )
      v18 = (IShellFolder *)this;
    pdcm.psf = v18;
    memset(&pdcm.cidl, 0, 40);
    v10 = SHCreateDefaultContextMenu(&pdcm, a3, a4);
    if ( v10 < 0 )
    {
LABEL_41:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)v10);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
LABEL_23:
      if ( v10 >= 0 )
        return v10;
LABEL_13:
      v13 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    return v10;
  }
  *(_QWORD *)&pcsfv.cbSize = 32;
  pcsfv.psvOuter = 0;
  if ( this == (CContentFolder *)16 )
  {
    pcsfv.psfvcb = 0;
    pcsfv.pshf = 0;
  }
  else
  {
    pcsfv.psfvcb = (IShellFolderViewCB *)((char *)this + 88);
    pcsfv.pshf = (IShellFolder *)this;
  }
  result = SHCreateShellFolderView(&pcsfv, (IShellView **)a4);
  v10 = result;
  if ( result < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_14:
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
          WPP_SF_d(v13[2], 38, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v10);
        return v10;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)result);
      goto LABEL_13;
    }
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18000b740  push    rbp
0x18000b742  push    rbx
0x18000b743  push    rsi
0x18000b744  push    rdi
0x18000b745  push    r12
0x18000b747  push    r13
0x18000b749  push    r14
0x18000b74b  push    r15
0x18000b74d  lea     rbp, [rsp-1Fh]
0x18000b752  sub     rsp, 98h
0x18000b759  mov     r14, r9
0x18000b75c  mov     rbx, r8
0x18000b75f  mov     r12, rdx
0x18000b762  mov     r15, rcx
0x18000b765  lea     r13, WPP_GLOBAL_Control
0x18000b76c  test    r9, r9
0x18000b76f  jz      loc_18000B8D4
0x18000b775  xor     edi, edi
0x18000b777  mov     [r9], rdi
0x18000b77a  mov     edx, 0FFFFFD57h; iIconIndex
0x18000b77f  lea     rcx, szFile; "wpdshext.dll"
0x18000b786  call    cs:__imp_SHGetIconOverlayIndexW
0x18000b78c  mov     edx, 0FFFFFD55h; iIconIndex
0x18000b791  lea     rcx, szFile; "wpdshext.dll"
0x18000b798  call    cs:__imp_SHGetIconOverlayIndexW
0x18000b79e  mov     rax, [rbx]
0x18000b7a1  sub     rax, qword ptr cs:IID_IShellView.Data1
0x18000b7a8  jnz     short loc_18000B7B5
0x18000b7aa  mov     rax, [rbx+8]
0x18000b7ae  sub     rax, qword ptr cs:IID_IShellView.Data4
0x18000b7b5  test    rax, rax
0x18000b7b8  jz      loc_18000B8DE
0x18000b7be  mov     rax, [rbx]
0x18000b7c1  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x18000b7c8  jnz     short loc_18000B7D5
0x18000b7ca  mov     rax, [rbx+8]
0x18000b7ce  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x18000b7d5  test    rax, rax
0x18000b7d8  jz      loc_18000B957
0x18000b7de  mov     edi, 80004002h
0x18000b7e3  mov     rax, [rbx]
0x18000b7e6  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x18000b7ed  jnz     short loc_18000B7FA
0x18000b7ef  mov     rax, [rbx+8]
0x18000b7f3  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x18000b7fa  test    rax, rax
0x18000b7fd  jnz     short loc_18000B843
0x18000b7ff  mov     rax, [r15-10h]
0x18000b803  lea     r8, WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_ONLY
0x18000b80a  mov     rdx, [r15+30h]
0x18000b80e  lea     rcx, [r15-10h]
0x18000b812  mov     rax, [rax+48h]
0x18000b816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b81b  test    eax, eax
0x18000b81d  jnz     loc_18000B8BD
0x18000b823  mov     rax, [r15-10h]
0x18000b827  lea     r8, WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_AND_DATA
0x18000b82e  mov     rdx, [r15+30h]
0x18000b832  lea     rcx, [r15-10h]
0x18000b836  mov     rax, [rax+48h]
0x18000b83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b83f  test    eax, eax
0x18000b841  jnz     short loc_18000B8BD
0x18000b843  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b84a  cmp     rcx, r13
0x18000b84d  jz      short loc_18000B859
0x18000b84f  test    byte ptr [rcx+1Ch], 2
0x18000b853  jnz     loc_18000BA5E
0x18000b859  mov     eax, edi
0x18000b85b  add     rsp, 98h
0x18000b862  pop     r15
0x18000b864  pop     r14
0x18000b866  pop     r13
0x18000b868  pop     r12
0x18000b86a  pop     rdi
0x18000b86b  pop     rsi
0x18000b86c  pop     rbx
0x18000b86d  pop     rbp
0x18000b86e  retn
0x18000b86f  mov     r8, r12; HWND
0x18000b872  lea     rdx, [r15-10h]; struct CContentFolder *
0x18000b876  mov     rcx, rax; this
0x18000b879  call    ??0CContentDropTarget@@QEAA@PEAVCContentFolder@@PEAUHWND__@@@Z; CContentDropTarget::CContentDropTarget(CContentFolder *,HWND__ *)
0x18000b87e  mov     rsi, rax
0x18000b881  test    rsi, rsi
0x18000b884  jz      loc_18000BA1D
0x18000b88a  mov     rax, [rsi]
0x18000b88d  mov     r8, r14
0x18000b890  mov     rdx, rbx
0x18000b893  mov     rcx, rsi
0x18000b896  mov     rax, [rax]
0x18000b899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b89e  mov     edi, eax
0x18000b8a0  test    eax, eax
0x18000b8a2  js      loc_18000BA27
0x18000b8a8  mov     rax, [rsi]
0x18000b8ab  mov     rcx, rsi
0x18000b8ae  mov     rax, [rax+10h]
0x18000b8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8b7  test    edi, edi
0x18000b8b9  js      short loc_18000B843
0x18000b8bb  jmp     short loc_18000B859
0x18000b8bd  mov     ecx, 60h ; '`'; unsigned __int64
0x18000b8c2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b8c7  mov     [rbp+57h+arg_18], rax
0x18000b8cb  test    rax, rax
0x18000b8ce  jnz     short loc_18000B86F
0x18000b8d0  xor     esi, esi
0x18000b8d2  jmp     short loc_18000B881
0x18000b8d4  mov     edi, 80004003h
0x18000b8d9  jmp     loc_18000B843
0x18000b8de  mov     qword ptr [rbp+57h+pcsfv.cbSize], 20h ; ' '
0x18000b8e6  mov     [rbp+57h+pcsfv.psvOuter], rdi
0x18000b8ea  lea     rax, [r15-10h]
0x18000b8ee  test    rax, rax
0x18000b8f1  jz      short loc_18000B901
0x18000b8f3  lea     rax, [r15+58h]
0x18000b8f7  mov     [rbp+57h+pcsfv.psfvcb], rax
0x18000b8fb  mov     [rbp+57h+pcsfv.pshf], r15
0x18000b8ff  jmp     short loc_18000B909
0x18000b901  mov     [rbp+57h+pcsfv.psfvcb], rdi
0x18000b905  mov     [rbp+57h+pcsfv.pshf], rdi
0x18000b909  mov     rdx, r14; ppsv
0x18000b90c  lea     rcx, [rbp+57h+pcsfv]; pcsfv
0x18000b910  call    cs:__imp_SHCreateShellFolderView
0x18000b916  mov     edi, eax
0x18000b918  test    eax, eax
0x18000b91a  jns     loc_18000B85B
0x18000b920  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b927  cmp     rcx, r13
0x18000b92a  jz      loc_18000B859
0x18000b930  test    byte ptr [rcx+1Ch], 2
0x18000b934  jz      loc_18000B84A
0x18000b93a  mov     edx, 23h ; '#'
0x18000b93f  mov     r9d, eax
0x18000b942  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18000b949  mov     rcx, [rcx+10h]
0x18000b94d  call    WPP_SF_d
0x18000b952  jmp     loc_18000B843
0x18000b957  mov     [rbp+57h+arg_18], rdi
0x18000b95b  lea     rsi, [r15-10h]
0x18000b95f  mov     r8d, 1; int
0x18000b965  lea     rdx, [rbp+57h+arg_18]; struct IContextMenuCB **
0x18000b969  mov     rcx, rsi; this
0x18000b96c  call    ?_ContextMenuCBCreate@CContentFolder@@AEAAJPEAPEAUIContextMenuCB@@H@Z; CContentFolder::_ContextMenuCBCreate(IContextMenuCB * *,int)
0x18000b971  mov     edi, eax
0x18000b973  test    eax, eax
0x18000b975  js      short loc_18000B9E4
0x18000b977  mov     [rbp+57h+pdcm.hwnd], r12
0x18000b97b  mov     rax, [rbp+57h+arg_18]
0x18000b97f  mov     [rbp+57h+pdcm.pcmcb], rax
0x18000b983  mov     rax, [r15+30h]
0x18000b987  mov     [rbp+57h+pdcm.pidlFolder], rax
0x18000b98b  xor     eax, eax
0x18000b98d  test    rsi, rsi
0x18000b990  cmovnz  rax, r15
0x18000b994  mov     [rbp+57h+pdcm.psf], rax
0x18000b998  mov     qword ptr [rbp+57h+pdcm.cidl], 0
0x18000b9a0  mov     [rbp+57h+pdcm.apidl], 0
0x18000b9a8  mov     [rbp+57h+pdcm.punkAssociationInfo], 0
0x18000b9b0  mov     qword ptr [rbp+57h+pdcm.cKeys], 0
0x18000b9b8  mov     [rbp+57h+pdcm.aKeys], 0
0x18000b9c0  mov     r8, r14; ppv
0x18000b9c3  mov     rdx, rbx; riid
0x18000b9c6  lea     rcx, [rbp+57h+pdcm]; pdcm
0x18000b9ca  call    cs:__imp_SHCreateDefaultContextMenu
0x18000b9d0  mov     edi, eax
0x18000b9d2  test    eax, eax
0x18000b9d4  js      short loc_18000B9E4
0x18000b9d6  lea     rcx, [rbp+57h+arg_18]
0x18000b9da  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b9df  jmp     loc_18000B859
0x18000b9e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9eb  cmp     rcx, r13
0x18000b9ee  jz      short loc_18000BA0F
0x18000b9f0  test    byte ptr [rcx+1Ch], 2
0x18000b9f4  jz      short loc_18000BA0F
0x18000b9f6  mov     edx, 24h ; '$'
0x18000b9fb  mov     r9d, edi
0x18000b9fe  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18000ba05  mov     rcx, [rcx+10h]
0x18000ba09  call    WPP_SF_d
0x18000ba0e  nop
0x18000ba0f  lea     rcx, [rbp+57h+arg_18]
0x18000ba13  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000ba18  jmp     loc_18000B8B7
0x18000ba1d  mov     edi, 8007000Eh
0x18000ba22  jmp     loc_18000B843
0x18000ba27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba2e  cmp     rcx, r13
0x18000ba31  jz      loc_18000B8A8
0x18000ba37  test    byte ptr [rcx+1Ch], 2
0x18000ba3b  jz      loc_18000B8A8
0x18000ba41  mov     edx, 25h ; '%'
0x18000ba46  mov     r9d, eax
0x18000ba49  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18000ba50  mov     rcx, [rcx+10h]
0x18000ba54  call    WPP_SF_d
0x18000ba59  jmp     loc_18000B8A8
0x18000ba5e  mov     edx, 26h ; '&'
0x18000ba63  mov     r9d, edi
0x18000ba66  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18000ba6d  mov     rcx, [rcx+10h]
0x18000ba71  call    WPP_SF_d
0x18000ba76  jmp     loc_18000B859
```
