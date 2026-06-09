# CDeviceContextMenuCB::CallBack(IShellFolder *,HWND__ *,IDataObject *,uint,unsigned __int64,__int64)

- ea: `0x180056bf0`
- end: `0x180056f2f`
- name: `?CallBack@CDeviceContextMenuCB@@UEAAJPEAUIShellFolder@@PEAUHWND__@@PEAUIDataObject@@I_K_J@Z`
- size: `831`
- prototype: `int(CDeviceContextMenuCB *__hidden this, struct IShellFolder *, HWND, struct IDataObject *, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180024aa4`
- `0x18002ff5c`
- `0x180041ab0`
- `0x180056bf0`
- `0x1800598e0`
- `0x1800602b8`
- `0x1800628cc`
- `0x180062e70`
- `0x180078010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x180056d58`
- `SHLWAPI!__imp_SHCreateThread` at `0x180056d58`
- `ole32!CoTaskMemAlloc` at `0x180056cd6`
- `ole32!CoTaskMemAlloc` at `0x180056cd6`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180056c92`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180056c92`
- `SHELL32!__imp_ILFree` at `0x180056f11`
- `SHELL32!__imp_ILFree` at `0x180056f11`

## pseudocode

```c
__int64 __fastcall CDeviceContextMenuCB::CallBack(
        CDeviceContextMenuCB *this,
        struct IShellFolder *a2,
        HWND a3,
        struct IDataObject *a4,
        unsigned int a5,
        unsigned __int64 a6,
        struct _QCMINFO *a7)
{
  unsigned int v9; // edi
  HRESULT v10; // eax
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  _QWORD *v14; // r14
  CDeviceFolder *v15; // rcx
  _DWORD *HIDA; // rax
  __int64 v17; // rcx
  ITEMIDLIST *v18; // rsi
  unsigned int idCmdFirst; // r14d
  HINSTANCE v20; // rcx
  unsigned int v21; // eax
  HINSTANCE v22; // rcx
  LPSTREAM ppStm; // [rsp+30h] [rbp-48h] BYREF
  __int128 v25; // [rsp+38h] [rbp-40h] BYREF
  __int64 v26; // [rsp+48h] [rbp-30h]

  if ( a5 == 1 )
  {
    v9 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids);
    if ( a4 )
    {
      v25 = 0;
      v26 = 0;
      HIDA = (_DWORD *)DataObj_GetHIDA(a4, &v25);
      if ( HIDA )
      {
        if ( *HIDA == 1 )
        {
          v18 = (ITEMIDLIST *)IDA_ILClone(HIDA, 0);
          if ( v18 )
          {
            idCmdFirst = a7->idCmdFirst;
            if ( (*(unsigned int (__fastcall **)(_QWORD, ITEMIDLIST *, const GUID *))(**((_QWORD **)this + 2) + 56LL))(
                   *((_QWORD *)this + 2),
                   v18,
                   &WPD_CONTENT_TYPE_IMAGE)
              || (*(unsigned int (__fastcall **)(_QWORD, ITEMIDLIST *, const GUID *))(**((_QWORD **)this + 2) + 56LL))(
                   *((_QWORD *)this + 2),
                   v18,
                   &WPD_CONTENT_TYPE_VIDEO) )
            {
              v21 = MergeMenu(v20, 0x14u, a7, idCmdFirst, 0);
              idCmdFirst = MergeMenu(v22, 0x13u, a7, v21, 0);
            }
            a7->idCmdFirst = idCmdFirst;
            ILFree(v18);
          }
        }
        ReleaseStgMediumHGLOBAL(v17, &v25);
      }
    }
    return v9;
  }
  if ( a5 != 12 )
  {
    v9 = -2147467263;
LABEL_33:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  if ( a6 == 21 )
  {
    v15 = (CDeviceFolder *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids);
    v9 = CDeviceFolder::_OnImportPictures(v15, a4);
    goto LABEL_32;
  }
  if ( a6 != 4294967291 )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids);
  ppStm = 0;
  v10 = CoMarshalInterThreadInterfaceInStream(&IID_IDataObject, (LPUNKNOWN)a4, &ppStm);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_34;
    v12 = 170;
    v13 = (unsigned int)v10;
    goto LABEL_14;
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
        v12 = 171;
LABEL_21:
        v13 = v9;
LABEL_14:
        WPP_SF_d(v11[2], v12, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v13);
        goto LABEL_33;
      }
      goto LABEL_34;
    }
    return v9;
  }
  (*(void (__fastcall **)(CDeviceContextMenuCB *))(*(_QWORD *)this + 8LL))(this);
  *v14 = *((_QWORD *)this + 2);
  v14[1] = ppStm;
  if ( SHCreateThread(_DevicePropSheetThreadProc, v14, 8u, 0) )
  {
LABEL_32:
    if ( (v9 & 0x80000000) == 0 )
      return v9;
    goto LABEL_33;
  }
  if ( ppStm )
  {
    ((void (__fastcall *)(LPSTREAM))ppStm->lpVtbl->Release)(ppStm);
    ppStm = 0;
  }
  (*(void (__fastcall **)(CDeviceContextMenuCB *))(*(_QWORD *)this + 16LL))(this);
  v9 = -2147467259;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 172;
      goto LABEL_21;
    }
LABEL_34:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
      WPP_SF_d(v11[2], 173, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x180056bf0  push    rbp
0x180056bf2  push    rsi
0x180056bf3  push    rdi
0x180056bf4  push    r14
0x180056bf6  push    r15
0x180056bf8  sub     rsp, 50h
0x180056bfc  mov     eax, [rsp+78h+arg_20]
0x180056c03  lea     rsi, WPP_GLOBAL_Control
0x180056c0a  mov     r14, r9
0x180056c0d  mov     r15, rcx
0x180056c10  sub     eax, 1
0x180056c13  jz      loc_180056E21
0x180056c19  lea     rbp, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x180056c20  cmp     eax, 0Bh
0x180056c23  jz      short loc_180056C2F
0x180056c25  mov     edi, 80004001h
0x180056c2a  jmp     loc_180056DEE
0x180056c2f  cmp     [rsp+78h+arg_28], 15h
0x180056c38  jz      loc_180056DB9
0x180056c3e  mov     eax, 0FFFFFFFBh
0x180056c43  cmp     [rsp+78h+arg_28], rax
0x180056c4b  jz      short loc_180056C57
0x180056c4d  mov     edi, 1
0x180056c52  jmp     loc_180056F21
0x180056c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c5e  cmp     rcx, rsi
0x180056c61  jz      short loc_180056C7A
0x180056c63  test    byte ptr [rcx+1Ch], 40h
0x180056c67  jz      short loc_180056C7A
0x180056c69  mov     rcx, [rcx+10h]
0x180056c6d  mov     edx, 0A9h
0x180056c72  mov     r8, rbp
0x180056c75  call    WPP_SF_
0x180056c7a  lea     r8, [rsp+78h+ppStm]; ppStm
0x180056c7f  mov     [rsp+78h+ppStm], 0
0x180056c88  mov     rdx, r14; pUnk
0x180056c8b  lea     rcx, IID_IDataObject; riid
0x180056c92  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180056c98  mov     edi, eax
0x180056c9a  test    eax, eax
0x180056c9c  jns     short loc_180056CD1
0x180056c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ca5  cmp     rcx, rsi
0x180056ca8  jz      loc_180056F21
0x180056cae  test    byte ptr [rcx+1Ch], 2
0x180056cb2  jz      loc_180056DF5
0x180056cb8  mov     edx, 0AAh
0x180056cbd  mov     r9d, eax
0x180056cc0  mov     rcx, [rcx+10h]
0x180056cc4  mov     r8, rbp
0x180056cc7  call    WPP_SF_d
0x180056ccc  jmp     loc_180056DEE
0x180056cd1  mov     ecx, 10h; cb
0x180056cd6  call    cs:__imp_CoTaskMemAlloc
0x180056cdc  mov     r14, rax
0x180056cdf  test    rax, rax
0x180056ce2  jnz     short loc_180056D28
0x180056ce4  mov     rcx, [rsp+78h+ppStm]
0x180056ce9  test    rcx, rcx
0x180056cec  jz      short loc_180056CFF
0x180056cee  mov     rax, [rcx]
0x180056cf1  mov     rax, [rax+10h]
0x180056cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cfa  mov     [rsp+78h+ppStm], r14
0x180056cff  mov     edi, 8007000Eh
0x180056d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d0b  cmp     rcx, rsi
0x180056d0e  jz      loc_180056F21
0x180056d14  test    byte ptr [rcx+1Ch], 2
0x180056d18  jz      loc_180056DF5
0x180056d1e  mov     edx, 0ABh
0x180056d23  mov     r9d, edi
0x180056d26  jmp     short loc_180056CC0
0x180056d28  mov     rax, [r15]
0x180056d2b  mov     rcx, r15
0x180056d2e  mov     rax, [rax+8]
0x180056d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d37  mov     rax, [r15+10h]
0x180056d3b  lea     rcx, ?_DevicePropSheetThreadProc@@YAKPEAX@Z; pfnThreadProc
0x180056d42  xor     r9d, r9d; pfnCallback
0x180056d45  mov     [r14], rax
0x180056d48  mov     rax, [rsp+78h+ppStm]
0x180056d4d  mov     rdx, r14; pData
0x180056d50  mov     [r14+8], rax
0x180056d54  lea     r8d, [r9+8]; flags
0x180056d58  call    cs:__imp_SHCreateThread
0x180056d5e  test    eax, eax
0x180056d60  jnz     loc_180056DE6
0x180056d66  mov     rcx, [rsp+78h+ppStm]
0x180056d6b  test    rcx, rcx
0x180056d6e  jz      short loc_180056D85
0x180056d70  mov     rax, [rcx]
0x180056d73  mov     rax, [rax+10h]
0x180056d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d7c  mov     [rsp+78h+ppStm], 0
0x180056d85  mov     rax, [r15]
0x180056d88  mov     rcx, r15
0x180056d8b  mov     rax, [rax+10h]
0x180056d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d94  mov     edi, 80004005h
0x180056d99  mov     rcx, cs:WPP_GLOBAL_Control
0x180056da0  cmp     rcx, rsi
0x180056da3  jz      loc_180056F21
0x180056da9  test    byte ptr [rcx+1Ch], 2
0x180056dad  jz      short loc_180056DF5
0x180056daf  mov     edx, 0ACh
0x180056db4  jmp     loc_180056D23
0x180056db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180056dc0  cmp     rcx, rsi
0x180056dc3  jz      short loc_180056DDC
0x180056dc5  test    byte ptr [rcx+1Ch], 40h
0x180056dc9  jz      short loc_180056DDC
0x180056dcb  mov     rcx, [rcx+10h]
0x180056dcf  mov     edx, 0A8h
0x180056dd4  mov     r8, rbp
0x180056dd7  call    WPP_SF_
0x180056ddc  mov     rdx, r14; struct IDataObject *
0x180056ddf  call    ?_OnImportPictures@CDeviceFolder@@AEAAJPEAUIDataObject@@@Z; CDeviceFolder::_OnImportPictures(IDataObject *)
0x180056de4  mov     edi, eax
0x180056de6  test    edi, edi
0x180056de8  jns     loc_180056F21
0x180056dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180056df5  cmp     rcx, rsi
0x180056df8  jz      loc_180056F21
0x180056dfe  test    byte ptr [rcx+1Ch], 2
0x180056e02  jz      loc_180056F21
0x180056e08  mov     rcx, [rcx+10h]
0x180056e0c  mov     edx, 0ADh
0x180056e11  mov     r9d, edi
0x180056e14  mov     r8, rbp
0x180056e17  call    WPP_SF_d
0x180056e1c  jmp     loc_180056F21
0x180056e21  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e28  xor     edi, edi
0x180056e2a  cmp     rcx, rsi
0x180056e2d  jz      short loc_180056E4A
0x180056e2f  test    byte ptr [rcx+1Ch], 40h
0x180056e33  jz      short loc_180056E4A
0x180056e35  mov     rcx, [rcx+10h]
0x180056e39  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x180056e40  mov     edx, 0A7h
0x180056e45  call    WPP_SF_
0x180056e4a  test    r14, r14
0x180056e4d  jz      loc_180056F21
0x180056e53  xorps   xmm0, xmm0
0x180056e56  lea     rdx, [rsp+78h+var_40]
0x180056e5b  xor     eax, eax
0x180056e5d  mov     rcx, r14
0x180056e60  movups  [rsp+78h+var_40], xmm0
0x180056e65  mov     [rsp+78h+var_30], rax
0x180056e6a  call    DataObj_GetHIDA
0x180056e6f  test    rax, rax
0x180056e72  jz      loc_180056F21
0x180056e78  cmp     dword ptr [rax], 1
0x180056e7b  jnz     loc_180056F17
0x180056e81  xor     edx, edx
0x180056e83  mov     rcx, rax
0x180056e86  call    IDA_ILClone
0x180056e8b  mov     rsi, rax
0x180056e8e  test    rax, rax
0x180056e91  jz      loc_180056F17
0x180056e97  mov     rcx, [r15+10h]
0x180056e9b  lea     r8, WPD_CONTENT_TYPE_IMAGE
0x180056ea2  mov     rbp, [rsp+78h+arg_30]
0x180056eaa  mov     rdx, [rcx]
0x180056ead  mov     r14d, [rbp+0Ch]
0x180056eb1  mov     rax, [rdx+38h]
0x180056eb5  mov     rdx, rsi
0x180056eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ebd  test    eax, eax
0x180056ebf  jnz     short loc_180056EDF
0x180056ec1  mov     rcx, [r15+10h]
0x180056ec5  lea     r8, WPD_CONTENT_TYPE_VIDEO
0x180056ecc  mov     rdx, rsi
0x180056ecf  mov     rax, [rcx]
0x180056ed2  mov     rax, [rax+38h]
0x180056ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056edb  test    eax, eax
0x180056edd  jz      short loc_180056F0A
0x180056edf  mov     r9d, r14d; unsigned int
0x180056ee2  mov     [rsp+78h+var_58], edi; int
0x180056ee6  mov     r8, rbp; struct _QCMINFO *
0x180056ee9  mov     edx, 14h; unsigned int
0x180056eee  call    ?MergeMenu@@YAIPEAUHINSTANCE__@@IPEAU_QCMINFO@@IH@Z; MergeMenu(HINSTANCE__ *,uint,_QCMINFO *,uint,int)
0x180056ef3  mov     r9d, eax; unsigned int
0x180056ef6  mov     [rsp+78h+var_58], edi; int
0x180056efa  mov     r8, rbp; struct _QCMINFO *
0x180056efd  mov     edx, 13h; unsigned int
0x180056f02  call    ?MergeMenu@@YAIPEAUHINSTANCE__@@IPEAU_QCMINFO@@IH@Z; MergeMenu(HINSTANCE__ *,uint,_QCMINFO *,uint,int)
0x180056f07  mov     r14d, eax
0x180056f0a  mov     rcx, rsi; pidl
0x180056f0d  mov     [rbp+0Ch], r14d
0x180056f11  call    cs:__imp_ILFree
0x180056f17  lea     rdx, [rsp+78h+var_40]
0x180056f1c  call    ReleaseStgMediumHGLOBAL
0x180056f21  mov     eax, edi
0x180056f23  add     rsp, 50h
0x180056f27  pop     r15
0x180056f29  pop     r14
0x180056f2b  pop     rdi
0x180056f2c  pop     rsi
0x180056f2d  pop     rbp
0x180056f2e  retn
```
