# CStorageContextMenuCB::CallBack(IShellFolder *,HWND__ *,IDataObject *,uint,unsigned __int64,__int64)

- ea: `0x180065550`
- end: `0x180065a6f`
- name: `?CallBack@CStorageContextMenuCB@@UEAAJPEAUIShellFolder@@PEAUHWND__@@PEAUIDataObject@@I_K_J@Z`
- size: `1311`
- prototype: `int(CStorageContextMenuCB *__hidden this, struct IShellFolder *, HWND, struct IDataObject *, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009890`
- `0x18000d610`
- `0x18001d860`
- `0x180024aa4`
- `0x1800285c8`
- `0x18002ff5c`
- `0x1800361ba`
- `0x180041ab0`
- `0x180061e80`
- `0x180062e70`
- `0x180065550`
- `0x18006e410`
- `0x180078010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x1800656c6`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800656c6`
- `ole32!CoTaskMemAlloc` at `0x180065644`
- `ole32!CoTaskMemAlloc` at `0x180065644`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180065600`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180065600`
- `SHELL32!__imp_ILFindLastID` at `0x180065785`
- `SHELL32!__imp_ILFindLastID` at `0x180065785`
- `SHELL32!__imp_ILFree` at `0x18006597e`
- `SHELL32!__imp_ILFree` at `0x18006597e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStorageContextMenuCB::CallBack(
        CStorageContextMenuCB *this,
        struct IShellFolder *a2,
        HWND a3,
        IUnknown *a4,
        unsigned int a5,
        unsigned __int64 a6)
{
  unsigned int v9; // ebx
  HRESULT v10; // eax
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  _QWORD *v14; // rdi
  __int64 v15; // rax
  const ITEMIDLIST *v16; // rdi
  __int64 v17; // rcx
  int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rax
  CStorageFolder *v22; // rcx
  const struct STORAGEITEM *v23; // rax
  HINSTANCE v24; // rcx
  const struct std::nothrow_t *v25; // rdx
  ITEMIDLIST *v26; // rax
  __int64 v27; // rdi
  ITEMIDLIST *v28; // r12
  __int64 v29; // rcx
  _DWORD *HIDA; // rax
  CStorageFolder *v31; // rcx
  const struct STORAGEITEM *v32; // rax
  LPSTREAM ppStm; // [rsp+40h] [rbp-A1h] BYREF
  LPITEMIDLIST ID; // [rsp+48h] [rbp-99h] BYREF
  __int128 v36; // [rsp+50h] [rbp-91h] BYREF
  __int64 v37; // [rsp+60h] [rbp-81h]
  _DWORD v38[4]; // [rsp+70h] [rbp-71h] BYREF
  const char *v39; // [rsp+80h] [rbp-61h]
  int v40; // [rsp+98h] [rbp-49h]
  const wchar_t *v41; // [rsp+B0h] [rbp-31h]

  v9 = 0;
  if ( a5 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, WPP_9caa288f52d13f713777aed0becde05d_Traceguids);
    if ( a4 )
    {
      v36 = 0;
      v37 = 0;
      HIDA = (_DWORD *)DataObj_GetHIDA(a4, &v36);
      if ( HIDA )
      {
        if ( *HIDA == 1 )
        {
          v32 = CStorageFolder::_IsValid(v31, (const struct _ITEMIDLIST *)((char *)HIDA + (unsigned int)HIDA[2]));
          if ( v32 )
          {
            if ( (*((_BYTE *)v32 + 14) & 4) != 0 )
              CDefFolderMenu_MergeMenu(g_hInst);
          }
        }
        ReleaseStgMediumHGLOBAL(v31, &v36);
      }
    }
    return v9;
  }
  if ( a5 != 12 )
  {
    v9 = -2147467263;
LABEL_61:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_62;
  }
  if ( a6 == 31 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, WPP_9caa288f52d13f713777aed0becde05d_Traceguids);
    v36 = 0;
    v37 = 0;
    v21 = DataObj_GetHIDA(a4, &v36);
    if ( !v21 )
      return v9;
    v23 = CStorageFolder::_IsValid(v22, (const struct _ITEMIDLIST *)(v21 + *(unsigned int *)(v21 + 8)));
    if ( v23 )
    {
      ppStm = 0;
      if ( (int)SHILCloneFirst(v23, &ppStm) >= 0 )
      {
        v26 = (ITEMIDLIST *)operator new(0x28u, v25);
        v27 = (__int64)v26;
        ID = v26;
        v28 = (ITEMIDLIST *)ppStm;
        if ( v26 )
        {
          v29 = *((_QWORD *)this + 2);
          *(_QWORD *)&v26->mkid.cb = &CFormatThreadData::`vftable';
          *(_QWORD *)v26[2].mkid.abID = v29;
          *(_QWORD *)((char *)&v26[5].mkid.cb + 1) = v28;
          *(_QWORD *)&v26[8].mkid.cb = 0;
          *(_DWORD *)v26[10].mkid.abID = 1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
        }
        else
        {
          v27 = 0;
        }
        if ( v27 )
        {
          if ( ShellDialogBoxParam(
                 v24,
                 (const unsigned __int16 *)0x12C,
                 a3,
                 (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))CStorageContextMenuCB::s_FormatDlgProc,
                 v27) < 1 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        else if ( v28 )
        {
          ILFree(v28);
        }
      }
    }
    ReleaseStgMediumHGLOBAL(v24, &v36);
    goto LABEL_60;
  }
  if ( a6 == 51 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, WPP_9caa288f52d13f713777aed0becde05d_Traceguids);
    v15 = *((_QWORD *)this + 2);
    if ( !*(_QWORD *)(v15 + 72) )
      return v9;
    v16 = *(const ITEMIDLIST **)(v15 + 64);
    if ( !v16 )
      return v9;
    ppStm = 0;
    memset_0(v38, 0, 0x68u);
    ID = ILFindLastID(v16);
    v17 = *(_QWORD *)(*((_QWORD *)this + 2) + 72LL) + 16LL;
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPITEMIDLIST *, GUID *, _QWORD, LPSTREAM *))(*(_QWORD *)v17 + 80LL))(
            v17,
            0,
            1,
            &ID,
            &GUID_000214e4_0000_0000_c000_000000000046,
            0,
            &ppStm);
    v9 = v18;
    if ( v18 >= 0 )
    {
      v38[0] = 104;
      v39 = "properties";
      v41 = L"properties";
      v40 = 1;
      v38[1] = 0x4000;
      v18 = ((__int64 (__fastcall *)(LPSTREAM, _DWORD *))ppStm->lpVtbl->Write)(ppStm, v38);
      v9 = v18;
      if ( v18 >= 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppStm);
        goto LABEL_60;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_39:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppStm);
        goto LABEL_61;
      }
      v20 = 182;
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_39;
      v20 = 181;
    }
    WPP_SF_d(v19[2], v20, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v18);
    goto LABEL_39;
  }
  if ( a6 != 4294967291 )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_9caa288f52d13f713777aed0becde05d_Traceguids);
  ppStm = 0;
  v10 = CoMarshalInterThreadInterfaceInStream(&IID_IDataObject, a4, &ppStm);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_62;
    v12 = 184;
    v13 = (unsigned int)v10;
    goto LABEL_15;
  }
  v14 = CoTaskMemAlloc(0x10u);
  if ( !v14 )
  {
    if ( ppStm )
    {
      ((void (__fastcall *)(LPSTREAM))ppStm->lpVtbl->Release)(ppStm);
      ppStm = 0;
    }
    v9 = -2147024882;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v12 = 185;
LABEL_22:
        v13 = v9;
LABEL_15:
        WPP_SF_d(v11[2], v12, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v13);
        goto LABEL_61;
      }
      goto LABEL_62;
    }
    return v9;
  }
  (*(void (__fastcall **)(CStorageContextMenuCB *))(*(_QWORD *)this + 8LL))(this);
  *v14 = *((_QWORD *)this + 2);
  v14[1] = ppStm;
  if ( SHCreateThread(_StoragePropSheetThreadProc, v14, 8u, 0) )
  {
LABEL_60:
    if ( (v9 & 0x80000000) == 0 )
      return v9;
    goto LABEL_61;
  }
  if ( ppStm )
  {
    ((void (__fastcall *)(LPSTREAM))ppStm->lpVtbl->Release)(ppStm);
    ppStm = 0;
  }
  (*(void (__fastcall **)(CStorageContextMenuCB *))(*(_QWORD *)this + 16LL))(this);
  v9 = -2147467259;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 186;
      goto LABEL_22;
    }
LABEL_62:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
      WPP_SF_d(v11[2], 187, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x180065550  push    rbp
0x180065552  push    rbx
0x180065553  push    rsi
0x180065554  push    rdi
0x180065555  push    r12
0x180065557  push    r13
0x180065559  push    r14
0x18006555b  push    r15
0x18006555d  lea     rbp, [rsp-7]
0x180065562  sub     rsp, 0E8h
0x180065569  mov     rdi, r9
0x18006556c  mov     r13, r8
0x18006556f  mov     r15, rcx
0x180065572  xor     ebx, ebx
0x180065574  mov     eax, [rbp+3Fh+arg_20]
0x180065577  sub     eax, 1
0x18006557a  jz      loc_1800659C9
0x180065580  lea     rsi, WPP_GLOBAL_Control
0x180065587  lea     r14, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18006558e  cmp     eax, 0Bh
0x180065591  jz      short loc_18006559D
0x180065593  mov     ebx, 80004001h
0x180065598  jmp     loc_180065996
0x18006559d  mov     rax, [rbp+3Fh+arg_28]
0x1800655a1  cmp     rax, 1Fh
0x1800655a5  jz      loc_18006587A
0x1800655ab  cmp     rax, 33h ; '3'
0x1800655af  jz      loc_18006572B
0x1800655b5  mov     ecx, 0FFFFFFFBh
0x1800655ba  cmp     rax, rcx
0x1800655bd  jz      short loc_1800655C9
0x1800655bf  mov     ebx, 1
0x1800655c4  jmp     loc_180065A59
0x1800655c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800655d0  cmp     rcx, rsi
0x1800655d3  jz      short loc_1800655EC
0x1800655d5  test    byte ptr [rcx+1Ch], 40h
0x1800655d9  jz      short loc_1800655EC
0x1800655db  mov     edx, 0B7h
0x1800655e0  mov     r8, r14
0x1800655e3  mov     rcx, [rcx+10h]
0x1800655e7  call    WPP_SF_
0x1800655ec  mov     [rsp+120h+ppStm], rbx
0x1800655f1  lea     r8, [rsp+120h+ppStm]; ppStm
0x1800655f6  mov     rdx, rdi; pUnk
0x1800655f9  lea     rcx, IID_IDataObject; riid
0x180065600  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180065606  mov     ebx, eax
0x180065608  test    eax, eax
0x18006560a  jns     short loc_18006563F
0x18006560c  mov     rcx, cs:WPP_GLOBAL_Control
0x180065613  cmp     rcx, rsi
0x180065616  jz      loc_180065A59
0x18006561c  test    byte ptr [rcx+1Ch], 2
0x180065620  jz      loc_18006599D
0x180065626  mov     edx, 0B8h
0x18006562b  mov     r9d, eax
0x18006562e  mov     r8, r14
0x180065631  mov     rcx, [rcx+10h]
0x180065635  call    WPP_SF_d
0x18006563a  jmp     loc_180065996
0x18006563f  mov     ecx, 10h; cb
0x180065644  call    cs:__imp_CoTaskMemAlloc
0x18006564a  mov     rdi, rax
0x18006564d  test    rax, rax
0x180065650  jnz     short loc_180065696
0x180065652  mov     rcx, [rsp+120h+ppStm]
0x180065657  test    rcx, rcx
0x18006565a  jz      short loc_18006566D
0x18006565c  mov     rax, [rcx]
0x18006565f  mov     rax, [rax+10h]
0x180065663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065668  mov     [rsp+120h+ppStm], rdi
0x18006566d  mov     ebx, 8007000Eh
0x180065672  mov     rcx, cs:WPP_GLOBAL_Control
0x180065679  cmp     rcx, rsi
0x18006567c  jz      loc_180065A59
0x180065682  test    byte ptr [rcx+1Ch], 2
0x180065686  jz      loc_18006599D
0x18006568c  mov     edx, 0B9h
0x180065691  mov     r9d, ebx
0x180065694  jmp     short loc_18006562E
0x180065696  mov     rax, [r15]
0x180065699  mov     rcx, r15
0x18006569c  mov     rax, [rax+8]
0x1800656a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656a5  mov     rax, [r15+10h]
0x1800656a9  mov     [rdi], rax
0x1800656ac  mov     rax, [rsp+120h+ppStm]
0x1800656b1  mov     [rdi+8], rax
0x1800656b5  xor     r9d, r9d; pfnCallback
0x1800656b8  lea     r8d, [r9+8]; flags
0x1800656bc  mov     rdx, rdi; pData
0x1800656bf  lea     rcx, ?_StoragePropSheetThreadProc@@YAKPEAX@Z; pfnThreadProc
0x1800656c6  call    cs:__imp_SHCreateThread
0x1800656cc  test    eax, eax
0x1800656ce  jnz     loc_18006598E
0x1800656d4  mov     rcx, [rsp+120h+ppStm]
0x1800656d9  test    rcx, rcx
0x1800656dc  jz      short loc_1800656F3
0x1800656de  mov     rax, [rcx]
0x1800656e1  mov     rax, [rax+10h]
0x1800656e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800656ea  mov     [rsp+120h+ppStm], 0
0x1800656f3  mov     rax, [r15]
0x1800656f6  mov     rcx, r15
0x1800656f9  mov     rax, [rax+10h]
0x1800656fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065702  mov     ebx, 80004005h
0x180065707  mov     rcx, cs:WPP_GLOBAL_Control
0x18006570e  cmp     rcx, rsi
0x180065711  jz      loc_180065A59
0x180065717  test    byte ptr [rcx+1Ch], 2
0x18006571b  jz      loc_18006599D
0x180065721  mov     edx, 0BAh
0x180065726  jmp     loc_180065691
0x18006572b  mov     rcx, cs:WPP_GLOBAL_Control
0x180065732  cmp     rcx, rsi
0x180065735  jz      short loc_18006574E
0x180065737  test    byte ptr [rcx+1Ch], 40h
0x18006573b  jz      short loc_18006574E
0x18006573d  mov     edx, 0B4h
0x180065742  mov     r8, r14
0x180065745  mov     rcx, [rcx+10h]
0x180065749  call    WPP_SF_
0x18006574e  mov     rax, [r15+10h]
0x180065752  cmp     [rax+48h], rbx
0x180065756  jz      loc_180065A59
0x18006575c  mov     rdi, [rax+40h]
0x180065760  test    rdi, rdi
0x180065763  jz      loc_180065A59
0x180065769  mov     [rsp+120h+ppStm], rbx
0x18006576e  mov     r12d, 68h ; 'h'
0x180065774  mov     r8d, r12d; Size
0x180065777  xor     edx, edx; Val
0x180065779  lea     rcx, [rbp+3Fh+var_B0]; void *
0x18006577d  call    memset_0
0x180065782  mov     rcx, rdi; pidl
0x180065785  call    cs:__imp_ILFindLastID
0x18006578b  mov     [rsp+120h+var_D8], rax
0x180065790  mov     rax, [r15+10h]
0x180065794  mov     rcx, [rax+48h]
0x180065798  add     rcx, 10h
0x18006579c  mov     rax, [rcx]
0x18006579f  lea     rdx, [rsp+120h+ppStm]
0x1800657a4  mov     [rsp+120h+var_F0], rdx
0x1800657a9  mov     [rsp+120h+var_F8], 0
0x1800657b2  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x1800657b9  mov     [rsp+120h+var_100], rdx
0x1800657be  lea     r9, [rsp+120h+var_D8]
0x1800657c3  xor     edx, edx
0x1800657c5  lea     r8d, [r12-67h]
0x1800657ca  mov     rax, [rax+50h]
0x1800657ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800657d3  mov     ebx, eax
0x1800657d5  test    eax, eax
0x1800657d7  jns     short loc_18006580F
0x1800657d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800657e0  cmp     rcx, rsi
0x1800657e3  jz      short loc_180065800
0x1800657e5  test    byte ptr [rcx+1Ch], 2
0x1800657e9  jz      short loc_180065800
0x1800657eb  lea     edx, [r12+4Dh]
0x1800657f0  mov     r9d, eax
0x1800657f3  mov     r8, r14
0x1800657f6  mov     rcx, [rcx+10h]
0x1800657fa  call    WPP_SF_d
0x1800657ff  nop
0x180065800  lea     rcx, [rsp+120h+ppStm]
0x180065805  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006580a  jmp     loc_180065996
0x18006580f  mov     [rbp+3Fh+var_B0], r12d
0x180065813  lea     rax, aProperties; "properties"
0x18006581a  mov     [rbp+3Fh+var_A0], rax
0x18006581e  lea     rax, aProperties_0; "properties"
0x180065825  mov     [rbp+3Fh+var_70], rax
0x180065829  mov     [rbp+3Fh+var_88], 1
0x180065830  mov     [rbp+3Fh+var_AC], 4000h
0x180065837  mov     rcx, [rsp+120h+ppStm]
0x18006583c  mov     rax, [rcx]
0x18006583f  lea     rdx, [rbp+3Fh+var_B0]
0x180065843  mov     rax, [rax+20h]
0x180065847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006584c  mov     ebx, eax
0x18006584e  test    eax, eax
0x180065850  jns     short loc_18006586B
0x180065852  mov     rcx, cs:WPP_GLOBAL_Control
0x180065859  cmp     rcx, rsi
0x18006585c  jz      short loc_180065800
0x18006585e  test    byte ptr [rcx+1Ch], 2
0x180065862  jz      short loc_180065800
0x180065864  mov     edx, 0B6h
0x180065869  jmp     short loc_1800657F0
0x18006586b  lea     rcx, [rsp+120h+ppStm]
0x180065870  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180065875  jmp     loc_18006598E
0x18006587a  mov     rcx, cs:WPP_GLOBAL_Control
0x180065881  cmp     rcx, rsi
0x180065884  jz      short loc_18006589D
0x180065886  test    byte ptr [rcx+1Ch], 40h
0x18006588a  jz      short loc_18006589D
0x18006588c  mov     edx, 0B3h
0x180065891  mov     r8, r14
0x180065894  mov     rcx, [rcx+10h]
0x180065898  call    WPP_SF_
0x18006589d  xorps   xmm0, xmm0
0x1800658a0  xor     eax, eax
0x1800658a2  movups  [rsp+120h+var_D0], xmm0
0x1800658a7  mov     [rsp+120h+var_C0], rax
0x1800658ac  lea     rdx, [rsp+120h+var_D0]
0x1800658b1  mov     rcx, rdi
0x1800658b4  call    DataObj_GetHIDA
0x1800658b9  test    rax, rax
0x1800658bc  jz      loc_180065A59
0x1800658c2  mov     edx, [rax+8]
0x1800658c5  add     rdx, rax; struct _ITEMIDLIST *
0x1800658c8  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x1800658cd  test    rax, rax
0x1800658d0  jz      loc_180065984
0x1800658d6  mov     [rsp+120h+ppStm], rbx
0x1800658db  lea     rdx, [rsp+120h+ppStm]
0x1800658e0  mov     rcx, rax
0x1800658e3  call    SHILCloneFirst
0x1800658e8  test    eax, eax
0x1800658ea  js      loc_180065984
0x1800658f0  mov     ecx, 28h ; '('; unsigned __int64
0x1800658f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800658fa  mov     rdi, rax
0x1800658fd  mov     [rsp+120h+var_D8], rax
0x180065902  mov     r12, [rsp+120h+ppStm]
0x180065907  test    rax, rax
0x18006590a  jz      short loc_18006593F
0x18006590c  mov     rcx, [r15+10h]
0x180065910  lea     rax, ??_7CFormatThreadData@@6B@; const CFormatThreadData::`vftable'
0x180065917  mov     [rdi], rax
0x18006591a  mov     [rdi+8], rcx
0x18006591e  mov     [rdi+10h], r12
0x180065922  mov     qword ptr [rdi+18h], 0
0x18006592a  mov     dword ptr [rdi+20h], 1
0x180065931  mov     rax, [rcx]
0x180065934  mov     rax, [rax+8]
0x180065938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006593d  jmp     short loc_180065941
0x18006593f  xor     edi, edi
0x180065941  test    rdi, rdi
0x180065944  jz      short loc_180065976
0x180065946  mov     [rsp+120h+var_100], rdi; __int64
0x18006594b  lea     r9, ?s_FormatDlgProc@CStorageContextMenuCB@@CA_JPEAUHWND__@@I_K_J@Z; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x180065952  mov     r8, r13; HWND
0x180065955  mov     edx, 12Ch; unsigned __int16 *
0x18006595a  call    ?ShellDialogBoxParam@@YA_JPEAUHINSTANCE__@@PEBGPEAUHWND__@@P6A_J2I_K_J@Z4@Z; ShellDialogBoxParam(HINSTANCE__ *,ushort const *,HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),__int64)
0x18006595f  cmp     rax, 1
0x180065963  jge     short loc_180065984
0x180065965  mov     rax, [rdi]
0x180065968  mov     rcx, rdi
0x18006596b  mov     rax, [rax+10h]
0x18006596f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065974  jmp     short loc_180065984
0x180065976  test    r12, r12
0x180065979  jz      short loc_180065984
0x18006597b  mov     rcx, r12; pidl
0x18006597e  call    cs:__imp_ILFree
0x180065984  lea     rdx, [rsp+120h+var_D0]
0x180065989  call    ReleaseStgMediumHGLOBAL
0x18006598e  test    ebx, ebx
0x180065990  jns     loc_180065A59
0x180065996  mov     rcx, cs:WPP_GLOBAL_Control
0x18006599d  cmp     rcx, rsi
0x1800659a0  jz      loc_180065A59
0x1800659a6  test    byte ptr [rcx+1Ch], 2
0x1800659aa  jz      loc_180065A59
0x1800659b0  mov     edx, 0BBh
0x1800659b5  mov     r9d, ebx
0x1800659b8  mov     r8, r14
0x1800659bb  mov     rcx, [rcx+10h]
0x1800659bf  call    WPP_SF_d
0x1800659c4  jmp     loc_180065A59
0x1800659c9  lea     rsi, WPP_GLOBAL_Control
0x1800659d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800659d7  cmp     rcx, rsi
0x1800659da  jz      short loc_1800659F7
0x1800659dc  test    byte ptr [rcx+1Ch], 40h
0x1800659e0  jz      short loc_1800659F7
0x1800659e2  mov     edx, 0B2h
0x1800659e7  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x1800659ee  mov     rcx, [rcx+10h]
0x1800659f2  call    WPP_SF_
0x1800659f7  test    rdi, rdi
0x1800659fa  jz      short loc_180065A59
0x1800659fc  xorps   xmm0, xmm0
0x1800659ff  xor     eax, eax
0x180065a01  movups  [rsp+120h+var_D0], xmm0
0x180065a06  mov     [rsp+120h+var_C0], rax
0x180065a0b  lea     rdx, [rsp+120h+var_D0]
0x180065a10  mov     rcx, rdi
0x180065a13  call    DataObj_GetHIDA
0x180065a18  test    rax, rax
0x180065a1b  jz      short loc_180065A59
0x180065a1d  cmp     dword ptr [rax], 1
0x180065a20  jnz     short loc_180065A4F
  ... truncated ...
```
