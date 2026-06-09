# CStorageFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180024420`
- end: `0x180024864`
- name: `?CreateViewObject@CStorageFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `1092`
- prototype: `int(CStorageFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d610`
- `0x180024420`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x18006709c`
- `0x180070b08`
- `0x180078010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180024748`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180024748`
- `SHELL32!SHBindToParent` at `0x1800245b4`
- `SHELL32!SHBindToParent` at `0x1800245b4`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18002452a`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18002452a`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x1800247b4`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x1800247b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CStorageFolder::CreateViewObject(unsigned __int64 this, HWND a2, const struct _GUID *a3, void **a4)
{
  HRESULT v8; // ebx
  void *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  const struct std::nothrow_t *v13; // rdx
  CDeviceDropTarget *v14; // rax
  CDeviceDropTarget *v15; // rdi
  int v16; // eax
  HRESULT v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  HRESULT v21; // eax
  struct IContextMenuCB *v23; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+40h] [rbp-C0h] BYREF
  SFV_CREATE pcsfv; // [rsp+48h] [rbp-B8h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+70h] [rbp-90h] BYREF
  CDeviceDropTarget *v28; // [rsp+C0h] [rbp-40h]
  WCHAR cTitle[264]; // [rsp+D0h] [rbp-30h] BYREF

  v8 = -2147467262;
  v9 = 0;
  ppv = 0;
  ppidlLast = 0;
  if ( a4 )
  {
    *a4 = 0;
    v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
      v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
    if ( v10 )
    {
      v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
        v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
      if ( !v11 )
      {
        v23 = 0;
        v8 = CStorageFolder::_ContextMenuCBCreate((CStorageFolder *)(this - 16), &v23, 1);
        if ( v8 < 0
          || (pdcm.hwnd = a2,
              pdcm.pcmcb = v23,
              pdcm.pidlFolder = *(LPCITEMIDLIST *)(this + 48),
              pdcm.psf = (IShellFolder *)(this & -(__int64)(this != 16)),
              memset(&pdcm.cidl, 0, 40),
              v8 = SHCreateDefaultContextMenu(&pdcm, a3, a4),
              v8 < 0) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
              (unsigned int)v8);
        }
        goto LABEL_54;
      }
      v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
        v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
      if ( v12 )
        goto LABEL_56;
      v8 = SHBindToParent(*(LPCITEMIDLIST *)(this + 48), &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
      LODWORD(v23) = v8;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v8);
        goto LABEL_55;
      }
      v14 = (CDeviceDropTarget *)operator new(0x68u, v13);
      v28 = v14;
      if ( v14 )
      {
        v15 = CDeviceDropTarget::CDeviceDropTarget(v14, *(struct CBaseFolder **)(this + 56), a2, ppidlLast, (int *)&v23);
        v8 = (int)v23;
      }
      else
      {
        v15 = 0;
      }
      if ( v8 >= 0 )
      {
        if ( !v15 )
        {
          v8 = -2147024882;
          goto LABEL_55;
        }
        v16 = (**(__int64 (__fastcall ***)(CDeviceDropTarget *, GUID *, void **))v15)(v15, &IID_IDropTarget, a4);
        v8 = v16;
        if ( v16 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v16);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v8);
        if ( !v15 )
        {
LABEL_55:
          v9 = ppv;
          if ( v8 >= 0 )
            goto LABEL_59;
          goto LABEL_56;
        }
      }
      (*(void (__fastcall **)(CDeviceDropTarget *))(*(_QWORD *)v15 + 16LL))(v15);
      goto LABEL_55;
    }
    v23 = 0;
    v17 = (*(__int64 (__fastcall **)(unsigned __int64, _QWORD, struct IContextMenuCB **))(*(_QWORD *)(this - 16) + 136LL))(
            this - 16,
            *(_QWORD *)(this + 48),
            &v23);
    v8 = v17;
    if ( v17 == -2147024891 )
    {
      if ( (*(int (__fastcall **)(unsigned __int64, _QWORD, WCHAR *, __int64))(*(_QWORD *)(this - 16) + 144LL))(
             this - 16,
             *(_QWORD *)(this + 48),
             cTitle,
             260) >= 0 )
        ShellMessageBoxW(g_hInst, a2, (LPCWSTR)0xB4, cTitle, 0x10030u);
    }
    else if ( (int)(v17 + 0x80000000) < 0 || v17 == -2147024894 )
    {
      *(_QWORD *)&pcsfv.cbSize = 32;
      pcsfv.psvOuter = 0;
      if ( this == 16 )
      {
        pcsfv.psfvcb = 0;
        pcsfv.pshf = 0;
      }
      else
      {
        pcsfv.psfvcb = (IShellFolderViewCB *)(this + 88);
        pcsfv.pshf = (IShellFolder *)this;
      }
      v21 = SHCreateShellFolderView(&pcsfv, (IShellView **)a4);
      v8 = v21;
      if ( v21 >= 0 )
        goto LABEL_54;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_54;
      v19 = 29;
      v20 = (unsigned int)v21;
      goto LABEL_53;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_54;
    v19 = 28;
    v20 = (unsigned int)v8;
LABEL_53:
    WPP_SF_d(v18[2], v19, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v20);
LABEL_54:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    goto LABEL_55;
  }
  v8 = -2147467261;
LABEL_56:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v8);
    v9 = ppv;
  }
LABEL_59:
  if ( v9 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180024420  push    rbp
0x180024422  push    rbx
0x180024423  push    rsi
0x180024424  push    rdi
0x180024425  push    r12
0x180024427  push    r13
0x180024429  push    r14
0x18002442b  push    r15
0x18002442d  lea     rbp, [rsp-1F8h]
0x180024435  sub     rsp, 2F8h
0x18002443c  mov     rax, cs:__security_cookie
0x180024443  xor     rax, rsp
0x180024446  mov     [rbp+230h+var_50], rax
0x18002444d  mov     r15, r9
0x180024450  mov     rsi, r8
0x180024453  mov     r12, rdx
0x180024456  mov     rdi, rcx
0x180024459  mov     ebx, 80004002h
0x18002445e  xor     r13d, r13d
0x180024461  mov     ecx, r13d
0x180024464  mov     [rsp+330h+ppv], rcx
0x180024469  mov     [rsp+330h+ppidlLast], r13
0x18002446e  lea     r14, WPP_GLOBAL_Control
0x180024475  test    r9, r9
0x180024478  jnz     short loc_180024484
0x18002447a  mov     ebx, 80004003h
0x18002447f  jmp     loc_1800247FE
0x180024484  mov     [r9], r13
0x180024487  mov     rax, [r8]
0x18002448a  sub     rax, qword ptr cs:IID_IShellView.Data1
0x180024491  jnz     short loc_18002449E
0x180024493  mov     rax, [r8+8]
0x180024497  sub     rax, qword ptr cs:IID_IShellView.Data4
0x18002449e  test    rax, rax
0x1800244a1  jz      loc_1800246DB
0x1800244a7  mov     rax, [r8]
0x1800244aa  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x1800244b1  jnz     short loc_1800244BE
0x1800244b3  mov     rax, [r8+8]
0x1800244b7  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800244be  test    rax, rax
0x1800244c1  jnz     loc_18002457F
0x1800244c7  mov     [rsp+330h+var_300], r13
0x1800244cc  lea     r14, [rdi-10h]
0x1800244d0  lea     r8d, [rax+1]; int
0x1800244d4  lea     rdx, [rsp+330h+var_300]; struct IContextMenuCB **
0x1800244d9  mov     rcx, r14; this
0x1800244dc  call    ?_ContextMenuCBCreate@CStorageFolder@@AEAAJPEAPEAUIContextMenuCB@@H@Z; CStorageFolder::_ContextMenuCBCreate(IContextMenuCB * *,int)
0x1800244e1  mov     ebx, eax
0x1800244e3  test    eax, eax
0x1800244e5  js      short loc_180024536
0x1800244e7  mov     [rsp+330h+pdcm.hwnd], r12
0x1800244ec  mov     rax, [rsp+330h+var_300]
0x1800244f1  mov     [rsp+330h+pdcm.pcmcb], rax
0x1800244f6  mov     rax, [rdi+30h]
0x1800244fa  mov     [rbp+230h+pdcm.pidlFolder], rax
0x1800244fe  neg     r14
0x180024501  sbb     rax, rax
0x180024504  and     rax, rdi
0x180024507  mov     [rbp+230h+pdcm.psf], rax
0x18002450b  mov     qword ptr [rbp+230h+pdcm.cidl], r13
0x18002450f  mov     [rbp+230h+pdcm.apidl], r13
0x180024513  mov     [rbp+230h+pdcm.punkAssociationInfo], r13
0x180024517  mov     qword ptr [rbp+230h+pdcm.cKeys], r13
0x18002451b  mov     [rbp+230h+pdcm.aKeys], r13
0x18002451f  mov     r8, r15; ppv
0x180024522  mov     rdx, rsi; riid
0x180024525  lea     rcx, [rsp+330h+pdcm]; pdcm
0x18002452a  call    cs:__imp_SHCreateDefaultContextMenu
0x180024530  mov     ebx, eax
0x180024532  test    eax, eax
0x180024534  jns     short loc_180024569
0x180024536  mov     rcx, cs:WPP_GLOBAL_Control
0x18002453d  lea     r14, WPP_GLOBAL_Control
0x180024544  cmp     rcx, r14
0x180024547  jz      short loc_180024570
0x180024549  test    byte ptr [rcx+1Ch], 2
0x18002454d  jz      short loc_180024570
0x18002454f  mov     edx, 1Eh
0x180024554  mov     r9d, ebx
0x180024557  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18002455e  mov     rcx, [rcx+10h]
0x180024562  call    WPP_SF_d
0x180024567  jmp     short loc_180024570
0x180024569  lea     r14, WPP_GLOBAL_Control
0x180024570  lea     rcx, [rsp+330h+var_300]
0x180024575  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002457a  jmp     loc_1800247F5
0x18002457f  mov     rax, [r8]
0x180024582  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x180024589  jnz     short loc_180024596
0x18002458b  mov     rax, [r8+8]
0x18002458f  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x180024596  test    rax, rax
0x180024599  jnz     loc_1800247FE
0x18002459f  lea     r9, [rsp+330h+ppidlLast]; ppidlLast
0x1800245a4  lea     r8, [rsp+330h+ppv]; ppv
0x1800245a9  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1800245b0  mov     rcx, [rdi+30h]; pidl
0x1800245b4  call    cs:__imp_SHBindToParent
0x1800245ba  mov     ebx, eax
0x1800245bc  mov     dword ptr [rsp+330h+var_300], eax
0x1800245c0  test    eax, eax
0x1800245c2  jns     short loc_1800245FB
0x1800245c4  mov     rax, cs:WPP_GLOBAL_Control
0x1800245cb  cmp     rax, r14
0x1800245ce  jz      loc_1800247F5
0x1800245d4  test    byte ptr [rax+1Ch], 2
0x1800245d8  jz      loc_1800247F5
0x1800245de  mov     edx, 1Fh
0x1800245e3  mov     r9d, ebx
0x1800245e6  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x1800245ed  mov     rcx, [rax+10h]
0x1800245f1  call    WPP_SF_d
0x1800245f6  jmp     loc_1800247F5
0x1800245fb  mov     ecx, 68h ; 'h'; unsigned __int64
0x180024600  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024605  mov     [rbp+230h+var_270], rax
0x180024609  test    rax, rax
0x18002460c  jz      short loc_180024635
0x18002460e  lea     rcx, [rsp+330h+var_300]
0x180024613  mov     qword ptr [rsp+330h+fuStyle], rcx; int *
0x180024618  mov     r9, [rsp+330h+ppidlLast]; struct _ITEMIDLIST *
0x18002461d  mov     r8, r12; HWND
0x180024620  mov     rdx, [rdi+38h]; struct CBaseFolder *
0x180024624  mov     rcx, rax; this
0x180024627  call    ??0CDeviceDropTarget@@QEAA@PEAVCBaseFolder@@PEAUHWND__@@PEFBU_ITEMIDLIST@@PEAJ@Z; CDeviceDropTarget::CDeviceDropTarget(CBaseFolder *,HWND__ *,_ITEMIDLIST const *,long *)
0x18002462c  mov     rdi, rax
0x18002462f  mov     ebx, dword ptr [rsp+330h+var_300]
0x180024633  jmp     short loc_180024638
0x180024635  mov     rdi, r13
0x180024638  test    ebx, ebx
0x18002463a  jns     short loc_180024670
0x18002463c  mov     rax, cs:WPP_GLOBAL_Control
0x180024643  cmp     rax, r14
0x180024646  jz      short loc_180024666
0x180024648  test    byte ptr [rax+1Ch], 2
0x18002464c  jz      short loc_180024666
0x18002464e  mov     edx, 20h ; ' '
0x180024653  mov     r9d, ebx
0x180024656  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18002465d  mov     rcx, [rax+10h]
0x180024661  call    WPP_SF_d
0x180024666  test    rdi, rdi
0x180024669  jnz     short loc_1800246C7
0x18002466b  jmp     loc_1800247F5
0x180024670  test    rdi, rdi
0x180024673  jnz     short loc_18002467F
0x180024675  mov     ebx, 8007000Eh
0x18002467a  jmp     loc_1800247F5
0x18002467f  mov     rax, [rdi]
0x180024682  mov     r8, r15
0x180024685  lea     rdx, IID_IDropTarget
0x18002468c  mov     rcx, rdi
0x18002468f  mov     rax, [rax]
0x180024692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024697  mov     ebx, eax
0x180024699  test    eax, eax
0x18002469b  jns     short loc_1800246C7
0x18002469d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246a4  cmp     rcx, r14
0x1800246a7  jz      short loc_1800246C7
0x1800246a9  test    byte ptr [rcx+1Ch], 2
0x1800246ad  jz      short loc_1800246C7
0x1800246af  mov     edx, 21h ; '!'
0x1800246b4  mov     r9d, eax
0x1800246b7  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x1800246be  mov     rcx, [rcx+10h]
0x1800246c2  call    WPP_SF_d
0x1800246c7  mov     rax, [rdi]
0x1800246ca  mov     rcx, rdi
0x1800246cd  mov     rax, [rax+10h]
0x1800246d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246d6  jmp     loc_1800247F5
0x1800246db  mov     [rsp+330h+var_300], r13
0x1800246e0  lea     rsi, [rdi-10h]
0x1800246e4  mov     rax, [rsi]
0x1800246e7  lea     r8, [rsp+330h+var_300]
0x1800246ec  mov     rdx, [rdi+30h]
0x1800246f0  mov     rcx, rsi
0x1800246f3  mov     rax, [rax+88h]
0x1800246fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246ff  mov     ebx, eax
0x180024701  cmp     eax, 80070005h
0x180024706  jnz     short loc_180024750
0x180024708  mov     rax, [rsi]
0x18002470b  mov     r9d, 104h
0x180024711  lea     r8, [rbp+230h+cTitle]
0x180024715  mov     rdx, [rdi+30h]
0x180024719  mov     rcx, rsi
0x18002471c  mov     rax, [rax+90h]
0x180024723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024728  test    eax, eax
0x18002472a  js      short loc_180024763
0x18002472c  mov     [rsp+330h+fuStyle], 10030h; fuStyle
0x180024734  lea     r9, [rbp+230h+cTitle]; lpcTitle
0x180024738  mov     r8d, 0B4h; lpcText
0x18002473e  mov     rdx, r12; hWnd
0x180024741  mov     rcx, cs:g_hInst; hAppInst
0x180024748  call    cs:__imp_ShellMessageBoxW
0x18002474e  jmp     short loc_180024763
0x180024750  mov     ecx, 80000000h
0x180024755  add     eax, ecx
0x180024757  test    ecx, eax
0x180024759  jnz     short loc_18002477F
0x18002475b  cmp     ebx, 80070002h
0x180024761  jz      short loc_18002477F
0x180024763  mov     rcx, cs:WPP_GLOBAL_Control
0x18002476a  cmp     rcx, r14
0x18002476d  jz      short loc_1800247EB
0x18002476f  test    byte ptr [rcx+1Ch], 2
0x180024773  jz      short loc_1800247EB
0x180024775  mov     edx, 1Ch
0x18002477a  mov     r9d, ebx
0x18002477d  jmp     short loc_1800247DA
0x18002477f  mov     qword ptr [rsp+330h+pcsfv.cbSize], 20h ; ' '
0x180024788  mov     [rsp+330h+pcsfv.psvOuter], r13
0x18002478d  test    rsi, rsi
0x180024790  jz      short loc_1800247A2
0x180024792  lea     rax, [rdi+58h]
0x180024796  mov     [rsp+330h+pcsfv.psfvcb], rax
0x18002479b  mov     [rsp+330h+pcsfv.pshf], rdi
0x1800247a0  jmp     short loc_1800247AC
0x1800247a2  mov     [rsp+330h+pcsfv.psfvcb], r13
0x1800247a7  mov     [rsp+330h+pcsfv.pshf], r13
0x1800247ac  mov     rdx, r15; ppsv
0x1800247af  lea     rcx, [rsp+330h+pcsfv]; pcsfv
0x1800247b4  call    cs:__imp_SHCreateShellFolderView
0x1800247ba  mov     ebx, eax
0x1800247bc  test    eax, eax
0x1800247be  jns     short loc_1800247EB
0x1800247c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247c7  cmp     rcx, r14
0x1800247ca  jz      short loc_1800247EB
0x1800247cc  test    byte ptr [rcx+1Ch], 2
0x1800247d0  jz      short loc_1800247EB
0x1800247d2  mov     edx, 1Dh
0x1800247d7  mov     r9d, eax
0x1800247da  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x1800247e1  mov     rcx, [rcx+10h]
0x1800247e5  call    WPP_SF_d
0x1800247ea  nop
0x1800247eb  lea     rcx, [rsp+330h+var_300]
0x1800247f0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800247f5  mov     rcx, [rsp+330h+ppv]
0x1800247fa  test    ebx, ebx
0x1800247fc  jns     short loc_18002482D
0x1800247fe  mov     rax, cs:WPP_GLOBAL_Control
0x180024805  cmp     rax, r14
0x180024808  jz      short loc_18002482D
0x18002480a  test    byte ptr [rax+1Ch], 2
0x18002480e  jz      short loc_18002482D
0x180024810  mov     edx, 22h ; '"'
0x180024815  mov     r9d, ebx
0x180024818  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18002481f  mov     rcx, [rax+10h]
0x180024823  call    WPP_SF_d
0x180024828  mov     rcx, [rsp+330h+ppv]
0x18002482d  test    rcx, rcx
0x180024830  jz      short loc_18002483F
0x180024832  mov     rdx, [rcx]
0x180024835  mov     rax, [rdx+10h]
0x180024839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002483e  nop
0x18002483f  mov     eax, ebx
0x180024841  mov     rcx, [rbp+230h+var_50]
0x180024848  xor     rcx, rsp; StackCookie
0x18002484b  call    __security_check_cookie
0x180024850  add     rsp, 2F8h
0x180024857  pop     r15
0x180024859  pop     r14
0x18002485b  pop     r13
0x18002485d  pop     r12
0x18002485f  pop     rdi
0x180024860  pop     rsi
0x180024861  pop     rbx
0x180024862  pop     rbp
0x180024863  retn
```
