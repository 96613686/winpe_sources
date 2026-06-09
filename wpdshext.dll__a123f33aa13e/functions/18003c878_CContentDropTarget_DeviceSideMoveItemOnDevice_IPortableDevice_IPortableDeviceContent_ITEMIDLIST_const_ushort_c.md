# CContentDropTarget::_DeviceSideMoveItemOnDevice(IPortableDevice *,IPortableDeviceContent *,_ITEMIDLIST const *,ushort const *,ushort const *,ushort const *,int,CProgressUI *)

- ea: `0x18003c878`
- end: `0x18003ccdc`
- name: `?_DeviceSideMoveItemOnDevice@CContentDropTarget@@AEAAJPEAUIPortableDevice@@PEAUIPortableDeviceContent@@PEFBU_ITEMIDLIST@@PEBG33HPEAVCProgressUI@@@Z`
- size: `1124`
- prototype: `int(CContentDropTarget *__hidden this, struct IPortableDevice *, struct IPortableDeviceContent *, const struct _ITEMIDLIST *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, struct CProgressUI *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003cce4`

## callees

- `0x18000ef50`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ff5c`
- `0x18003b8e4`
- `0x18003c878`
- `0x180054524`
- `0x1800545c8`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003cab1`
- `KERNEL32!Sleep` at `0x18003cc87`
- `KERNEL32!Sleep` at `0x18003cab1`
- `KERNEL32!Sleep` at `0x18003cc87`
- `ole32!PropVariantClear` at `0x18003cc5b`
- `ole32!PropVariantClear` at `0x18003cc5b`
- `ole32!CoCreateInstance` at `0x18003c8f2`
- `ole32!CoCreateInstance` at `0x18003c8f2`
- `SHELL32!__imp_ILFree` at `0x18003c976`
- `SHELL32!__imp_ILFree` at `0x18003c98b`
- `SHELL32!__imp_ILFree` at `0x18003c976`
- `SHELL32!__imp_ILFree` at `0x18003c98b`

## pseudocode

```c
__int64 __fastcall CContentDropTarget::_DeviceSideMoveItemOnDevice(
        CContentFolder **this,
        struct IPortableDevice *a2,
        struct IPortableDeviceContent *a3,
        const struct _ITEMIDLIST *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned __int16 *a7,
        int a8,
        struct CProgressUI *a9)
{
  const ITEMIDLIST *v9; // r14
  ITEMIDLIST *v12; // rsi
  int lVal; // ebx
  PVOID *v14; // rcx
  int v16; // r14d
  int v17; // esi
  int v18; // eax
  CContentDropTarget *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  int v22; // r14d
  int v23; // [rsp+38h] [rbp-59h] BYREF
  struct _ITEMIDLIST *v24; // [rsp+40h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-49h] BYREF
  LPITEMIDLIST pidl; // [rsp+50h] [rbp-41h] BYREF
  __int64 v27; // [rsp+58h] [rbp-39h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp-31h] BYREF
  __int128 v29; // [rsp+78h] [rbp-19h] BYREF
  __int64 v30; // [rsp+88h] [rbp-9h]

  v9 = a4;
  v23 = 0;
  v12 = 0;
  v24 = 0;
  pidl = 0;
  memset(&pvar, 0, sizeof(pvar));
  ppv = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  lVal = CoCreateInstance(
           &CLSID_PortableDevicePropVariantCollection,
           0,
           1u,
           &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
           &ppv);
  if ( lVal < 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)lVal);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_5;
  }
  LOWORD(v29) = 31;
  *((_QWORD *)&v29 + 1) = a6;
  (*(void (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 40LL))(ppv, &v29);
  if ( a7 )
  {
    if ( a9 )
    {
      v16 = 0;
      v17 = 0;
      while ( !*((_DWORD *)a9 + 26) )
      {
        lVal = CContentFolder::_CreateIDList(this[10], a2, a7, 0, &v24, &v23);
        if ( lVal != -2147024726 )
          goto LABEL_28;
        if ( !v16 )
        {
          v16 = 1;
          v17 = 1;
          CProgressUI::_StartMarquee(a9);
        }
        if ( *((_DWORD *)a9 + 26) )
          break;
        Sleep(0x5DCu);
      }
      lVal = -2147023673;
LABEL_28:
      if ( v17 )
        CProgressUI::_StopMarquee(a9);
      if ( *((_DWORD *)a9 + 26) )
      {
        lVal = -2147023673;
        goto LABEL_35;
      }
      v9 = a4;
    }
    else
    {
      lVal = CContentFolder::_CreateIDList(this[10], a2, a7, 0, &v24, &v23);
    }
    if ( lVal < 0 )
    {
LABEL_35:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        v12 = v24;
        goto LABEL_5;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)lVal);
      v12 = v24;
LABEL_38:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_5;
    }
    v12 = v24;
    v18 = SHILCombine(v9, v24, &pidl);
    lVal = v18;
    if ( v18 < 0 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_5;
      v20 = 60;
LABEL_44:
      v21 = (unsigned int)v18;
LABEL_45:
      WPP_SF_d(v14[2], v20, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v21);
      goto LABEL_38;
    }
    v18 = CContentDropTarget::_DeleteExistingObject(v19, a2, a7, a8, a9);
    lVal = v18;
    if ( v18 < 0 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_5;
      v20 = 61;
      goto LABEL_44;
    }
    ChangeNotify(v23 != 0 ? 16 : 4, 0, pidl, 0);
  }
  v22 = 0;
  while ( 1 )
  {
    lVal = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, LPVOID, const unsigned __int16 *, __int64 *))a3->lpVtbl->Move)(
             a3,
             ppv,
             a5,
             &v27);
    if ( lVal == 1 )
    {
      lVal = -2147467259;
      memset(&pvar, 0, sizeof(pvar));
      if ( (*(int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v27 + 32LL))(v27, 0, &pvar) >= 0
        && pvar.vt == 10
        && pvar.lVal < 0 )
      {
        lVal = pvar.lVal;
      }
      PropVariantClear(&pvar);
    }
    if ( lVal != -2147024726 )
      break;
    if ( !v22 )
    {
      v22 = 1;
      CProgressUI::_StartMarquee(a9);
    }
    if ( *((_DWORD *)a9 + 26) )
    {
      lVal = -2147023673;
      goto LABEL_65;
    }
    Sleep(0x5DCu);
  }
  if ( lVal >= 0 )
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_5;
  }
LABEL_65:
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v20 = 62;
    v21 = (unsigned int)lVal;
    goto LABEL_45;
  }
LABEL_5:
  if ( *((_DWORD *)a9 + 27) )
  {
    CProgressUI::_StopMarquee(a9);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a9 + 26) )
    lVal = -2147023673;
  if ( pidl )
  {
    ILFree(pidl);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 )
  {
    ILFree(v12);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lVal < 0 && v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
    WPP_SF_d(v14[2], 63, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)lVal);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)lVal;
}

```

## disassembly

```asm
0x18003c878  mov     rax, rsp
0x18003c87b  mov     [rax+8], rbx
0x18003c87f  mov     [rax+20h], r9
0x18003c883  mov     [rax+18h], r8
0x18003c887  push    rbp
0x18003c888  push    rsi
0x18003c889  push    rdi
0x18003c88a  push    r12
0x18003c88c  push    r13
0x18003c88e  push    r14
0x18003c890  push    r15
0x18003c892  lea     rbp, [rax-3Fh]
0x18003c896  sub     rsp, 90h
0x18003c89d  mov     r14, r9
0x18003c8a0  mov     r12, rdx
0x18003c8a3  mov     r13, rcx
0x18003c8a6  xor     r15d, r15d
0x18003c8a9  mov     [rbp+37h+var_90], r15d
0x18003c8ad  mov     esi, r15d
0x18003c8b0  mov     [rbp+37h+var_88], r15
0x18003c8b4  mov     [rbp+37h+pidl], r15
0x18003c8b8  xorps   xmm0, xmm0
0x18003c8bb  xor     eax, eax
0x18003c8bd  movups  xmmword ptr [rbp+37h+pvar], xmm0
0x18003c8c1  mov     qword ptr [rbp+37h+pvar+10h], rax
0x18003c8c5  mov     [rbp+37h+var_80], r15
0x18003c8c9  mov     [rbp+37h+var_70], r15
0x18003c8cd  movups  [rbp+37h+var_50], xmm0
0x18003c8d1  mov     [rbp+37h+var_40], rax
0x18003c8d5  lea     rax, [rbp+37h+var_80]
0x18003c8d9  mov     [rsp+0C0h+ppv], rax; ppv
0x18003c8de  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x18003c8e5  xor     edx, edx; pUnkOuter
0x18003c8e7  lea     r8d, [r15+1]; dwClsContext
0x18003c8eb  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x18003c8f2  call    cs:__imp_CoCreateInstance
0x18003c8f8  mov     ebx, eax
0x18003c8fa  mov     rdi, [rbp+37h+arg_40]
0x18003c901  lea     rax, WPP_GLOBAL_Control
0x18003c908  test    ebx, ebx
0x18003c90a  jns     loc_18003C9F0
0x18003c910  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c917  cmp     rcx, rax
0x18003c91a  jz      short loc_18003C940
0x18003c91c  test    byte ptr [rcx+1Ch], 2
0x18003c920  jz      short loc_18003C940
0x18003c922  lea     edx, [r15+3Ah]
0x18003c926  mov     r9d, ebx
0x18003c929  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003c930  mov     rcx, [rcx+10h]
0x18003c934  call    WPP_SF_d
0x18003c939  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c940  mov     r13d, 800704C7h
0x18003c946  lea     r14, WPP_GLOBAL_Control
0x18003c94d  cmp     dword ptr [rdi+6Ch], 0
0x18003c951  jz      short loc_18003C962
0x18003c953  mov     rcx, rdi; this
0x18003c956  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003c95b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c962  cmp     dword ptr [rdi+68h], 0
0x18003c966  cmovnz  ebx, r13d
0x18003c96a  mov     rax, [rbp+37h+pidl]
0x18003c96e  test    rax, rax
0x18003c971  jz      short loc_18003C983
0x18003c973  mov     rcx, rax; pidl
0x18003c976  call    cs:__imp_ILFree
0x18003c97c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c983  test    rsi, rsi
0x18003c986  jz      short loc_18003C998
0x18003c988  mov     rcx, rsi; pidl
0x18003c98b  call    cs:__imp_ILFree
0x18003c991  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c998  test    ebx, ebx
0x18003c99a  jns     short loc_18003C9C0
0x18003c99c  cmp     rcx, r14
0x18003c99f  jz      short loc_18003C9C0
0x18003c9a1  test    byte ptr [rcx+1Ch], 2
0x18003c9a5  jz      short loc_18003C9C0
0x18003c9a7  mov     edx, 3Fh ; '?'
0x18003c9ac  mov     r9d, ebx
0x18003c9af  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003c9b6  mov     rcx, [rcx+10h]
0x18003c9ba  call    WPP_SF_d
0x18003c9bf  nop
0x18003c9c0  lea     rcx, [rbp+37h+var_70]
0x18003c9c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c9c9  nop
0x18003c9ca  lea     rcx, [rbp+37h+var_80]
0x18003c9ce  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c9d3  mov     eax, ebx
0x18003c9d5  mov     rbx, [rsp+0C0h+arg_0]
0x18003c9dd  add     rsp, 90h
0x18003c9e4  pop     r15
0x18003c9e6  pop     r14
0x18003c9e8  pop     r13
0x18003c9ea  pop     r12
0x18003c9ec  pop     rdi
0x18003c9ed  pop     rsi
0x18003c9ee  pop     rbp
0x18003c9ef  retn
0x18003c9f0  mov     eax, 1Fh
0x18003c9f5  mov     word ptr [rbp+37h+var_50], ax
0x18003c9f9  mov     rax, [rbp+37h+arg_28]
0x18003c9fd  mov     qword ptr [rbp+37h+var_50+8], rax
0x18003ca01  mov     rcx, [rbp+37h+var_80]
0x18003ca05  mov     rax, [rcx]
0x18003ca08  lea     rdx, [rbp+37h+var_50]
0x18003ca0c  mov     rax, [rax+28h]
0x18003ca10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca15  mov     r15, [rbp+37h+arg_30]
0x18003ca19  test    r15, r15
0x18003ca1c  jz      loc_18003CBE9
0x18003ca22  test    rdi, rdi
0x18003ca25  jnz     short loc_18003CA58
0x18003ca27  lea     rax, [rbp+37h+var_90]
0x18003ca2b  mov     [rsp+28h], rax; int *
0x18003ca30  lea     rax, [rbp+37h+var_88]
0x18003ca34  mov     [rsp+0C0h+ppv], rax; struct _ITEMIDLIST **
0x18003ca39  xor     r9d, r9d; int
0x18003ca3c  mov     r8, r15; unsigned __int16 *
0x18003ca3f  mov     rdx, r12; struct IPortableDevice *
0x18003ca42  mov     rcx, [r13+50h]; this
0x18003ca46  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x18003ca4b  mov     ebx, eax
0x18003ca4d  mov     r13d, 800704C7h
0x18003ca53  jmp     loc_18003CAE8
0x18003ca58  xor     r14d, r14d
0x18003ca5b  xor     esi, esi
0x18003ca5d  cmp     dword ptr [rdi+68h], 0
0x18003ca61  jnz     short loc_18003CAD9
0x18003ca63  lea     rax, [rbp+37h+var_90]
0x18003ca67  mov     [rsp+28h], rax; int *
0x18003ca6c  lea     rax, [rbp+37h+var_88]
0x18003ca70  mov     [rsp+0C0h+ppv], rax; struct _ITEMIDLIST **
0x18003ca75  xor     r9d, r9d; int
0x18003ca78  mov     r8, r15; unsigned __int16 *
0x18003ca7b  mov     rdx, r12; struct IPortableDevice *
0x18003ca7e  mov     rcx, [r13+50h]; this
0x18003ca82  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x18003ca87  mov     ebx, eax
0x18003ca89  cmp     eax, 800700AAh
0x18003ca8e  jnz     short loc_18003CABC
0x18003ca90  test    r14d, r14d
0x18003ca93  jnz     short loc_18003CAA6
0x18003ca95  lea     eax, [r14+1]
0x18003ca99  mov     r14d, eax
0x18003ca9c  mov     esi, eax
0x18003ca9e  mov     rcx, rdi; this
0x18003caa1  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003caa6  cmp     dword ptr [rdi+68h], 0
0x18003caaa  jnz     short loc_18003CAD9
0x18003caac  mov     ecx, 5DCh; dwMilliseconds
0x18003cab1  call    cs:__imp_Sleep
0x18003cab7  test    r14d, r14d
0x18003caba  jnz     short loc_18003CA5D
0x18003cabc  mov     r13d, 800704C7h
0x18003cac2  test    esi, esi
0x18003cac4  jz      short loc_18003CACE
0x18003cac6  mov     rcx, rdi; this
0x18003cac9  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003cace  cmp     dword ptr [rdi+68h], 0
0x18003cad2  jz      short loc_18003CAE4
0x18003cad4  mov     ebx, r13d
0x18003cad7  jmp     short loc_18003CAEC
0x18003cad9  mov     r13d, 800704C7h
0x18003cadf  mov     ebx, r13d
0x18003cae2  jmp     short loc_18003CAC2
0x18003cae4  mov     r14, [rbp+37h+arg_18]
0x18003cae8  test    ebx, ebx
0x18003caea  jns     short loc_18003CB36
0x18003caec  mov     rcx, cs:WPP_GLOBAL_Control
0x18003caf3  lea     r14, WPP_GLOBAL_Control
0x18003cafa  cmp     rcx, r14
0x18003cafd  jz      short loc_18003CB2D
0x18003caff  test    byte ptr [rcx+1Ch], 2
0x18003cb03  jz      short loc_18003CB2D
0x18003cb05  mov     edx, 3Bh ; ';'
0x18003cb0a  mov     r9d, ebx
0x18003cb0d  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003cb14  mov     rcx, [rcx+10h]
0x18003cb18  call    WPP_SF_d
0x18003cb1d  mov     rsi, [rbp+37h+var_88]
0x18003cb21  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb28  jmp     loc_18003C94D
0x18003cb2d  mov     rsi, [rbp+37h+var_88]
0x18003cb31  jmp     loc_18003C94D
0x18003cb36  lea     r8, [rbp+37h+pidl]
0x18003cb3a  mov     rsi, [rbp+37h+var_88]
0x18003cb3e  mov     rdx, rsi
0x18003cb41  mov     rcx, r14
0x18003cb44  call    SHILCombine
0x18003cb49  mov     ebx, eax
0x18003cb4b  test    eax, eax
0x18003cb4d  jns     short loc_18003CB8A
0x18003cb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb56  lea     r14, WPP_GLOBAL_Control
0x18003cb5d  cmp     rcx, r14
0x18003cb60  jz      loc_18003C94D
0x18003cb66  test    byte ptr [rcx+1Ch], 2
0x18003cb6a  jz      loc_18003C94D
0x18003cb70  mov     edx, 3Ch ; '<'
0x18003cb75  mov     r9d, eax
0x18003cb78  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003cb7f  mov     rcx, [rcx+10h]
0x18003cb83  call    WPP_SF_d
0x18003cb88  jmp     short loc_18003CB21
0x18003cb8a  mov     [rsp+0C0h+ppv], rdi; struct CProgressUI *
0x18003cb8f  mov     r9d, [rbp+37h+arg_38]; int
0x18003cb93  mov     r8, r15; unsigned __int16 *
0x18003cb96  mov     rdx, r12; struct IPortableDevice *
0x18003cb99  call    ?_DeleteExistingObject@CContentDropTarget@@AEAAJPEAUIPortableDevice@@PEBGHPEAVCProgressUI@@@Z; CContentDropTarget::_DeleteExistingObject(IPortableDevice *,ushort const *,int,CProgressUI *)
0x18003cb9e  mov     ebx, eax
0x18003cba0  test    eax, eax
0x18003cba2  jns     short loc_18003CBCC
0x18003cba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cbab  lea     r14, WPP_GLOBAL_Control
0x18003cbb2  cmp     rcx, r14
0x18003cbb5  jz      loc_18003C94D
0x18003cbbb  test    byte ptr [rcx+1Ch], 2
0x18003cbbf  jz      loc_18003C94D
0x18003cbc5  mov     edx, 3Dh ; '='
0x18003cbca  jmp     short loc_18003CB75
0x18003cbcc  mov     eax, [rbp+37h+var_90]
0x18003cbcf  neg     eax
0x18003cbd1  sbb     ecx, ecx
0x18003cbd3  and     ecx, 0Ch
0x18003cbd6  add     ecx, 4; wEventId
0x18003cbd9  xor     r9d, r9d; dwItem2
0x18003cbdc  mov     r8, [rbp+37h+pidl]; dwItem1
0x18003cbe0  xor     edx, edx; uFlags
0x18003cbe2  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18003cbe7  jmp     short loc_18003CBEF
0x18003cbe9  mov     r13d, 800704C7h
0x18003cbef  xor     r14d, r14d
0x18003cbf2  mov     r15, [rbp+37h+arg_10]
0x18003cbf6  mov     rax, [r15]
0x18003cbf9  lea     r9, [rbp+37h+var_70]
0x18003cbfd  mov     r8, [rbp+37h+arg_20]
0x18003cc01  mov     rdx, [rbp+37h+var_80]
0x18003cc05  mov     rcx, r15
0x18003cc08  mov     rax, [rax+58h]
0x18003cc0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc11  mov     ebx, eax
0x18003cc13  cmp     eax, 1
0x18003cc16  jnz     short loc_18003CC61
0x18003cc18  mov     ebx, 80004005h
0x18003cc1d  xorps   xmm0, xmm0
0x18003cc20  xor     eax, eax
0x18003cc22  movups  xmmword ptr [rbp+37h+pvar], xmm0
0x18003cc26  mov     qword ptr [rbp+37h+pvar+10h], rax
0x18003cc2a  mov     rcx, [rbp+37h+var_70]
0x18003cc2e  mov     rax, [rcx]
0x18003cc31  lea     r8, [rbp+37h+pvar]
0x18003cc35  xor     edx, edx
0x18003cc37  mov     rax, [rax+20h]
0x18003cc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc40  test    eax, eax
0x18003cc42  js      short loc_18003CC57
0x18003cc44  mov     eax, 0Ah
0x18003cc49  cmp     ax, word ptr [rbp+37h+pvar]
0x18003cc4d  jnz     short loc_18003CC57
0x18003cc4f  mov     eax, dword ptr [rbp+37h+pvar+8]
0x18003cc52  test    eax, eax
0x18003cc54  cmovs   ebx, eax
0x18003cc57  lea     rcx, [rbp+37h+pvar]; pvar
0x18003cc5b  call    cs:__imp_PropVariantClear
0x18003cc61  cmp     ebx, 800700AAh
0x18003cc67  jnz     short loc_18003CC9D
0x18003cc69  test    r14d, r14d
0x18003cc6c  jnz     short loc_18003CC7C
0x18003cc6e  mov     r14d, 1
0x18003cc74  mov     rcx, rdi; this
0x18003cc77  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003cc7c  cmp     dword ptr [rdi+68h], 0
0x18003cc80  jnz     short loc_18003CC98
0x18003cc82  mov     ecx, 5DCh; dwMilliseconds
0x18003cc87  call    cs:__imp_Sleep
0x18003cc8d  test    r14d, r14d
0x18003cc90  jnz     loc_18003CBF6
0x18003cc96  jmp     short loc_18003CCA1
0x18003cc98  mov     ebx, r13d
0x18003cc9b  jmp     short loc_18003CCA1
0x18003cc9d  test    ebx, ebx
0x18003cc9f  jns     short loc_18003CCCF
0x18003cca1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cca8  lea     r14, WPP_GLOBAL_Control
0x18003ccaf  cmp     rcx, r14
0x18003ccb2  jz      loc_18003C94D
0x18003ccb8  test    byte ptr [rcx+1Ch], 2
0x18003ccbc  jz      loc_18003C94D
0x18003ccc2  mov     edx, 3Eh ; '>'
0x18003ccc7  mov     r9d, ebx
0x18003ccca  jmp     loc_18003CB78
0x18003cccf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ccd6  jmp     loc_18003C946
```
