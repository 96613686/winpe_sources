# CDeviceFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180056f80`
- end: `0x180057214`
- name: `?CreateViewObject@CDeviceFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `660`
- prototype: `int(CDeviceFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d610`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180041e28`
- `0x180056f80`
- `0x180058a28`
- `0x180078010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x180057079`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180057079`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180057183`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180057183`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDeviceFolder::CreateViewObject(
        unsigned __int64 this,
        const struct std::nothrow_t *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  char *v11; // r15
  struct IContextMenuCB *v12; // rax
  struct IContextMenuCB *v13; // rdi
  _QWORD *v14; // rcx
  char *v15; // rbx
  HRESULT v16; // eax
  SFV_CREATE pcsfv; // [rsp+20h] [rbp-39h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+40h] [rbp-19h] BYREF
  struct IContextMenuCB *v20; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( a4 )
  {
    *a4 = 0;
    v9 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
      v9 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
    if ( v9 )
    {
      v8 = -2147467262;
      v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
        v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
      if ( v10 )
        goto LABEL_27;
      v20 = 0;
      v11 = (char *)(this - 16);
      v8 = CDeviceFolder::_ContextMenuCBCreate((CDeviceFolder *)(this - 16), &v20);
      if ( v8 >= 0 )
      {
        pdcm.hwnd = (HWND)a2;
        pdcm.pcmcb = v20;
        pdcm.pidlFolder = *(LPCITEMIDLIST *)(this + 48);
        pdcm.psf = (IShellFolder *)(this & -(__int64)(v11 != 0));
        memset(&pdcm.cidl, 0, 40);
        v8 = SHCreateDefaultContextMenu(&pdcm, a3, a4);
        if ( v8 >= 0 )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
          return (unsigned int)v8;
        }
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
          (unsigned int)v8);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    }
    else
    {
      v12 = (struct IContextMenuCB *)operator new(0x48u, a2);
      v13 = v12;
      v20 = v12;
      if ( v12 )
      {
        CObjectWithSite::CObjectWithSite((CObjectWithSite *)&v12[2]);
        v13->lpVtbl = (struct IContextMenuCBVtbl *)&CDeviceFolderViewCB::`vftable'{for `IShellFolderViewCB'};
        v13[1].lpVtbl = (struct IContextMenuCBVtbl *)&CDeviceFolderViewCB::`vftable'{for `IFolderViewSettings'};
        *v14 = &CDeviceFolderViewCB::`vftable'{for `CObjectWithSite'};
        v13[4].lpVtbl = (struct IContextMenuCBVtbl *)&CDeviceFolderViewCB::`vftable'{for `IDispatch'};
        LODWORD(v13[5].lpVtbl) = 1;
        v13[6].lpVtbl = (struct IContextMenuCBVtbl *)a2;
        v15 = (char *)(this - 16);
        v13[7].lpVtbl = (struct IContextMenuCBVtbl *)(this - 16);
        LODWORD(v13[8].lpVtbl) = -1;
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)(this - 16) + 8LL))(this - 16);
      }
      else
      {
        v13 = 0;
        v15 = (char *)(this - 16);
      }
      if ( !v13 )
      {
        v8 = -2147024882;
        goto LABEL_27;
      }
      *(_QWORD *)&pcsfv.cbSize = 32;
      pcsfv.psvOuter = 0;
      pcsfv.psfvcb = (IShellFolderViewCB *)v13;
      pcsfv.pshf = (IShellFolder *)(this & -(__int64)(v15 != 0));
      v16 = SHCreateShellFolderView(&pcsfv, (IShellView **)a4);
      v8 = v16;
      if ( v16 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
          (unsigned int)v16);
      ((void (__fastcall *)(struct IContextMenuCB *))v13->lpVtbl->Release)(v13);
    }
    if ( v8 >= 0 )
      return (unsigned int)v8;
    goto LABEL_27;
  }
  v8 = -2147467261;
LABEL_27:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180056f80  mov     [rsp-8+arg_0], rbx
0x180056f85  mov     [rsp-8+arg_8], rsi
0x180056f8a  push    rbp
0x180056f8b  push    rdi
0x180056f8c  push    r12
0x180056f8e  push    r14
0x180056f90  push    r15
0x180056f92  lea     rbp, [rsp-37h]
0x180056f97  sub     rsp, 90h
0x180056f9e  mov     r14, r9
0x180056fa1  mov     rdi, r8
0x180056fa4  mov     r12, rdx
0x180056fa7  mov     rsi, rcx
0x180056faa  lea     r15, WPP_GLOBAL_Control
0x180056fb1  test    r9, r9
0x180056fb4  jnz     short loc_180056FC0
0x180056fb6  mov     ebx, 80004003h
0x180056fbb  jmp     loc_1800571CC
0x180056fc0  mov     qword ptr [r9], 0
0x180056fc7  mov     rax, [r8]
0x180056fca  sub     rax, qword ptr cs:IID_IShellView.Data1
0x180056fd1  jnz     short loc_180056FDE
0x180056fd3  mov     rax, [r8+8]
0x180056fd7  sub     rax, qword ptr cs:IID_IShellView.Data4
0x180056fde  test    rax, rax
0x180056fe1  jz      loc_1800570D3
0x180056fe7  mov     ebx, 80004002h
0x180056fec  mov     rax, [r8]
0x180056fef  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180056ff6  jnz     short loc_180057003
0x180056ff8  mov     rax, [r8+8]
0x180056ffc  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180057003  test    rax, rax
0x180057006  jnz     loc_1800571CC
0x18005700c  mov     [rbp+57h+arg_18], rax
0x180057010  lea     r15, [rcx-10h]
0x180057014  lea     rdx, [rbp+57h+arg_18]; struct IContextMenuCB **
0x180057018  mov     rcx, r15; this
0x18005701b  call    ?_ContextMenuCBCreate@CDeviceFolder@@AEAAJPEAPEAUIContextMenuCB@@@Z; CDeviceFolder::_ContextMenuCBCreate(IContextMenuCB * *)
0x180057020  mov     ebx, eax
0x180057022  test    eax, eax
0x180057024  js      short loc_180057093
0x180057026  mov     [rbp+57h+pdcm.hwnd], r12
0x18005702a  mov     rax, [rbp+57h+arg_18]
0x18005702e  mov     [rbp+57h+pdcm.pcmcb], rax
0x180057032  mov     rax, [rsi+30h]
0x180057036  mov     [rbp+57h+pdcm.pidlFolder], rax
0x18005703a  neg     r15
0x18005703d  sbb     rax, rax
0x180057040  and     rax, rsi
0x180057043  mov     [rbp+57h+pdcm.psf], rax
0x180057047  mov     qword ptr [rbp+57h+pdcm.cidl], 0
0x18005704f  mov     [rbp+57h+pdcm.apidl], 0
0x180057057  mov     [rbp+57h+pdcm.punkAssociationInfo], 0
0x18005705f  mov     qword ptr [rbp+57h+pdcm.cKeys], 0
0x180057067  mov     [rbp+57h+pdcm.aKeys], 0
0x18005706f  mov     r8, r14; ppv
0x180057072  mov     rdx, rdi; riid
0x180057075  lea     rcx, [rbp+57h+pdcm]; pdcm
0x180057079  call    cs:__imp_SHCreateDefaultContextMenu
0x18005707f  mov     ebx, eax
0x180057081  test    eax, eax
0x180057083  js      short loc_180057093
0x180057085  lea     rcx, [rbp+57h+arg_18]
0x180057089  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005708e  jmp     loc_1800571F6
0x180057093  mov     rcx, cs:WPP_GLOBAL_Control
0x18005709a  lea     r15, WPP_GLOBAL_Control
0x1800570a1  cmp     rcx, r15
0x1800570a4  jz      short loc_1800570C5
0x1800570a6  test    byte ptr [rcx+1Ch], 2
0x1800570aa  jz      short loc_1800570C5
0x1800570ac  mov     edx, 1Bh
0x1800570b1  mov     r9d, ebx
0x1800570b4  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x1800570bb  mov     rcx, [rcx+10h]
0x1800570bf  call    WPP_SF_d
0x1800570c4  nop
0x1800570c5  lea     rcx, [rbp+57h+arg_18]
0x1800570c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800570ce  jmp     loc_1800571C8
0x1800570d3  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800570d8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800570dd  mov     rdi, rax
0x1800570e0  mov     [rbp+57h+arg_18], rax
0x1800570e4  test    rax, rax
0x1800570e7  jz      short loc_180057149
0x1800570e9  lea     rcx, [rax+10h]; this
0x1800570ed  call    ??0CObjectWithSite@@QEAA@XZ; CObjectWithSite::CObjectWithSite(void)
0x1800570f2  nop
0x1800570f3  lea     rax, ??_7CDeviceFolderViewCB@@6BIShellFolderViewCB@@@; const CDeviceFolderViewCB::`vftable'{for `IShellFolderViewCB'}
0x1800570fa  mov     [rdi], rax
0x1800570fd  lea     rax, ??_7CDeviceFolderViewCB@@6BIFolderViewSettings@@@; const CDeviceFolderViewCB::`vftable'{for `IFolderViewSettings'}
0x180057104  mov     [rdi+8], rax
0x180057108  lea     rax, ??_7CDeviceFolderViewCB@@6BCObjectWithSite@@@; const CDeviceFolderViewCB::`vftable'{for `CObjectWithSite'}
0x18005710f  mov     [rcx], rax
0x180057112  lea     rax, ??_7CDeviceFolderViewCB@@6BIDispatch@@@; const CDeviceFolderViewCB::`vftable'{for `IDispatch'}
0x180057119  mov     [rdi+20h], rax
0x18005711d  mov     dword ptr [rdi+28h], 1
0x180057124  mov     [rdi+30h], r12
0x180057128  lea     rbx, [rsi-10h]
0x18005712c  mov     [rdi+38h], rbx
0x180057130  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x180057137  mov     rax, [rbx]
0x18005713a  mov     rcx, rbx
0x18005713d  mov     rax, [rax+8]
0x180057141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057146  nop
0x180057147  jmp     short loc_18005714F
0x180057149  xor     edi, edi
0x18005714b  lea     rbx, [rsi-10h]
0x18005714f  test    rdi, rdi
0x180057152  jnz     short loc_18005715B
0x180057154  mov     ebx, 8007000Eh
0x180057159  jmp     short loc_1800571CC
0x18005715b  mov     qword ptr [rbp+57h+pcsfv.cbSize], 20h ; ' '
0x180057163  mov     [rbp+57h+pcsfv.psvOuter], 0
0x18005716b  mov     [rbp+57h+pcsfv.psfvcb], rdi
0x18005716f  neg     rbx
0x180057172  sbb     rax, rax
0x180057175  and     rax, rsi
0x180057178  mov     [rbp+57h+pcsfv.pshf], rax
0x18005717c  mov     rdx, r14; ppsv
0x18005717f  lea     rcx, [rbp+57h+pcsfv]; pcsfv
0x180057183  call    cs:__imp_SHCreateShellFolderView
0x180057189  mov     ebx, eax
0x18005718b  test    eax, eax
0x18005718d  jns     short loc_1800571B9
0x18005718f  mov     rcx, cs:WPP_GLOBAL_Control
0x180057196  cmp     rcx, r15
0x180057199  jz      short loc_1800571B9
0x18005719b  test    byte ptr [rcx+1Ch], 2
0x18005719f  jz      short loc_1800571B9
0x1800571a1  mov     edx, 1Ah
0x1800571a6  mov     r9d, eax
0x1800571a9  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x1800571b0  mov     rcx, [rcx+10h]
0x1800571b4  call    WPP_SF_d
0x1800571b9  mov     rax, [rdi]
0x1800571bc  mov     rcx, rdi
0x1800571bf  mov     rax, [rax+10h]
0x1800571c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571c8  test    ebx, ebx
0x1800571ca  jns     short loc_1800571F6
0x1800571cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800571d3  cmp     rcx, r15
0x1800571d6  jz      short loc_1800571F6
0x1800571d8  test    byte ptr [rcx+1Ch], 2
0x1800571dc  jz      short loc_1800571F6
0x1800571de  mov     edx, 1Ch
0x1800571e3  mov     r9d, ebx
0x1800571e6  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x1800571ed  mov     rcx, [rcx+10h]
0x1800571f1  call    WPP_SF_d
0x1800571f6  mov     eax, ebx
0x1800571f8  lea     r11, [rsp+0B0h+var_20]
0x180057200  mov     rbx, [r11+30h]
0x180057204  mov     rsi, [r11+38h]
0x180057208  mov     rsp, r11
0x18005720b  pop     r15
0x18005720d  pop     r14
0x18005720f  pop     r12
0x180057211  pop     rdi
0x180057212  pop     rbp
0x180057213  retn
```
