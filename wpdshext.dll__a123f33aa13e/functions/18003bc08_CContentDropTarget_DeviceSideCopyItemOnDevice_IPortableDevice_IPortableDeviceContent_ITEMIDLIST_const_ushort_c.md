# CContentDropTarget::_DeviceSideCopyItemOnDevice(IPortableDevice *,IPortableDeviceContent *,_ITEMIDLIST const *,ushort const *,ushort const *,ushort const *,int,CProgressUI *)

- ea: `0x18003bc08`
- end: `0x18003c06c`
- name: `?_DeviceSideCopyItemOnDevice@CContentDropTarget@@AEAAJPEAUIPortableDevice@@PEAUIPortableDeviceContent@@PEFBU_ITEMIDLIST@@PEBG33HPEAVCProgressUI@@@Z`
- size: `1124`
- prototype: `int(CContentDropTarget *__hidden this, struct IPortableDevice *, struct IPortableDeviceContent *, const struct _ITEMIDLIST *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, struct CProgressUI *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003c074`

## callees

- `0x18000ef50`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ff5c`
- `0x18003b8e4`
- `0x18003bc08`
- `0x180054524`
- `0x1800545c8`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003be41`
- `KERNEL32!Sleep` at `0x18003c017`
- `KERNEL32!Sleep` at `0x18003be41`
- `KERNEL32!Sleep` at `0x18003c017`
- `ole32!PropVariantClear` at `0x18003bfeb`
- `ole32!PropVariantClear` at `0x18003bfeb`
- `ole32!CoCreateInstance` at `0x18003bc82`
- `ole32!CoCreateInstance` at `0x18003bc82`
- `SHELL32!__imp_ILFree` at `0x18003bd06`
- `SHELL32!__imp_ILFree` at `0x18003bd1b`
- `SHELL32!__imp_ILFree` at `0x18003bd06`
- `SHELL32!__imp_ILFree` at `0x18003bd1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDropTarget::_DeviceSideCopyItemOnDevice(
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
        84,
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
        85,
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
      v20 = 86;
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
      v20 = 87;
      goto LABEL_44;
    }
    ChangeNotify(v23 != 0 ? 16 : 4, 0, pidl, 0);
  }
  v22 = 0;
  while ( 1 )
  {
    lVal = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, LPVOID, const unsigned __int16 *, __int64 *))a3->lpVtbl->Copy)(
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
    v20 = 88;
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
    WPP_SF_d(v14[2], 89, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)lVal);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)lVal;
}

```

## disassembly

```asm
0x18003bc08  mov     rax, rsp
0x18003bc0b  mov     [rax+8], rbx
0x18003bc0f  mov     [rax+20h], r9
0x18003bc13  mov     [rax+18h], r8
0x18003bc17  push    rbp
0x18003bc18  push    rsi
0x18003bc19  push    rdi
0x18003bc1a  push    r12
0x18003bc1c  push    r13
0x18003bc1e  push    r14
0x18003bc20  push    r15
0x18003bc22  lea     rbp, [rax-3Fh]
0x18003bc26  sub     rsp, 90h
0x18003bc2d  mov     r14, r9
0x18003bc30  mov     r12, rdx
0x18003bc33  mov     r13, rcx
0x18003bc36  xor     r15d, r15d
0x18003bc39  mov     [rbp+37h+var_90], r15d
0x18003bc3d  mov     esi, r15d
0x18003bc40  mov     [rbp+37h+var_88], r15
0x18003bc44  mov     [rbp+37h+pidl], r15
0x18003bc48  xorps   xmm0, xmm0
0x18003bc4b  xor     eax, eax
0x18003bc4d  movups  xmmword ptr [rbp+37h+pvar], xmm0
0x18003bc51  mov     qword ptr [rbp+37h+pvar+10h], rax
0x18003bc55  mov     [rbp+37h+var_80], r15
0x18003bc59  mov     [rbp+37h+var_70], r15
0x18003bc5d  movups  [rbp+37h+var_50], xmm0
0x18003bc61  mov     [rbp+37h+var_40], rax
0x18003bc65  lea     rax, [rbp+37h+var_80]
0x18003bc69  mov     [rsp+0C0h+ppv], rax; ppv
0x18003bc6e  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x18003bc75  xor     edx, edx; pUnkOuter
0x18003bc77  lea     r8d, [r15+1]; dwClsContext
0x18003bc7b  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x18003bc82  call    cs:__imp_CoCreateInstance
0x18003bc88  mov     ebx, eax
0x18003bc8a  mov     rdi, [rbp+37h+arg_40]
0x18003bc91  lea     rax, WPP_GLOBAL_Control
0x18003bc98  test    ebx, ebx
0x18003bc9a  jns     loc_18003BD80
0x18003bca0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bca7  cmp     rcx, rax
0x18003bcaa  jz      short loc_18003BCD0
0x18003bcac  test    byte ptr [rcx+1Ch], 2
0x18003bcb0  jz      short loc_18003BCD0
0x18003bcb2  lea     edx, [r15+54h]
0x18003bcb6  mov     r9d, ebx
0x18003bcb9  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003bcc0  mov     rcx, [rcx+10h]
0x18003bcc4  call    WPP_SF_d
0x18003bcc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bcd0  mov     r13d, 800704C7h
0x18003bcd6  lea     r14, WPP_GLOBAL_Control
0x18003bcdd  cmp     dword ptr [rdi+6Ch], 0
0x18003bce1  jz      short loc_18003BCF2
0x18003bce3  mov     rcx, rdi; this
0x18003bce6  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003bceb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bcf2  cmp     dword ptr [rdi+68h], 0
0x18003bcf6  cmovnz  ebx, r13d
0x18003bcfa  mov     rax, [rbp+37h+pidl]
0x18003bcfe  test    rax, rax
0x18003bd01  jz      short loc_18003BD13
0x18003bd03  mov     rcx, rax; pidl
0x18003bd06  call    cs:__imp_ILFree
0x18003bd0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd13  test    rsi, rsi
0x18003bd16  jz      short loc_18003BD28
0x18003bd18  mov     rcx, rsi; pidl
0x18003bd1b  call    cs:__imp_ILFree
0x18003bd21  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bd28  test    ebx, ebx
0x18003bd2a  jns     short loc_18003BD50
0x18003bd2c  cmp     rcx, r14
0x18003bd2f  jz      short loc_18003BD50
0x18003bd31  test    byte ptr [rcx+1Ch], 2
0x18003bd35  jz      short loc_18003BD50
0x18003bd37  mov     edx, 59h ; 'Y'
0x18003bd3c  mov     r9d, ebx
0x18003bd3f  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003bd46  mov     rcx, [rcx+10h]
0x18003bd4a  call    WPP_SF_d
0x18003bd4f  nop
0x18003bd50  lea     rcx, [rbp+37h+var_70]
0x18003bd54  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003bd59  nop
0x18003bd5a  lea     rcx, [rbp+37h+var_80]
0x18003bd5e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003bd63  mov     eax, ebx
0x18003bd65  mov     rbx, [rsp+0C0h+arg_0]
0x18003bd6d  add     rsp, 90h
0x18003bd74  pop     r15
0x18003bd76  pop     r14
0x18003bd78  pop     r13
0x18003bd7a  pop     r12
0x18003bd7c  pop     rdi
0x18003bd7d  pop     rsi
0x18003bd7e  pop     rbp
0x18003bd7f  retn
0x18003bd80  mov     eax, 1Fh
0x18003bd85  mov     word ptr [rbp+37h+var_50], ax
0x18003bd89  mov     rax, [rbp+37h+arg_28]
0x18003bd8d  mov     qword ptr [rbp+37h+var_50+8], rax
0x18003bd91  mov     rcx, [rbp+37h+var_80]
0x18003bd95  mov     rax, [rcx]
0x18003bd98  lea     rdx, [rbp+37h+var_50]
0x18003bd9c  mov     rax, [rax+28h]
0x18003bda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bda5  mov     r15, [rbp+37h+arg_30]
0x18003bda9  test    r15, r15
0x18003bdac  jz      loc_18003BF79
0x18003bdb2  test    rdi, rdi
0x18003bdb5  jnz     short loc_18003BDE8
0x18003bdb7  lea     rax, [rbp+37h+var_90]
0x18003bdbb  mov     [rsp+28h], rax; int *
0x18003bdc0  lea     rax, [rbp+37h+var_88]
0x18003bdc4  mov     [rsp+0C0h+ppv], rax; struct _ITEMIDLIST **
0x18003bdc9  xor     r9d, r9d; int
0x18003bdcc  mov     r8, r15; unsigned __int16 *
0x18003bdcf  mov     rdx, r12; struct IPortableDevice *
0x18003bdd2  mov     rcx, [r13+50h]; this
0x18003bdd6  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x18003bddb  mov     ebx, eax
0x18003bddd  mov     r13d, 800704C7h
0x18003bde3  jmp     loc_18003BE78
0x18003bde8  xor     r14d, r14d
0x18003bdeb  xor     esi, esi
0x18003bded  cmp     dword ptr [rdi+68h], 0
0x18003bdf1  jnz     short loc_18003BE69
0x18003bdf3  lea     rax, [rbp+37h+var_90]
0x18003bdf7  mov     [rsp+28h], rax; int *
0x18003bdfc  lea     rax, [rbp+37h+var_88]
0x18003be00  mov     [rsp+0C0h+ppv], rax; struct _ITEMIDLIST **
0x18003be05  xor     r9d, r9d; int
0x18003be08  mov     r8, r15; unsigned __int16 *
0x18003be0b  mov     rdx, r12; struct IPortableDevice *
0x18003be0e  mov     rcx, [r13+50h]; this
0x18003be12  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x18003be17  mov     ebx, eax
0x18003be19  cmp     eax, 800700AAh
0x18003be1e  jnz     short loc_18003BE4C
0x18003be20  test    r14d, r14d
0x18003be23  jnz     short loc_18003BE36
0x18003be25  lea     eax, [r14+1]
0x18003be29  mov     r14d, eax
0x18003be2c  mov     esi, eax
0x18003be2e  mov     rcx, rdi; this
0x18003be31  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003be36  cmp     dword ptr [rdi+68h], 0
0x18003be3a  jnz     short loc_18003BE69
0x18003be3c  mov     ecx, 5DCh; dwMilliseconds
0x18003be41  call    cs:__imp_Sleep
0x18003be47  test    r14d, r14d
0x18003be4a  jnz     short loc_18003BDED
0x18003be4c  mov     r13d, 800704C7h
0x18003be52  test    esi, esi
0x18003be54  jz      short loc_18003BE5E
0x18003be56  mov     rcx, rdi; this
0x18003be59  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003be5e  cmp     dword ptr [rdi+68h], 0
0x18003be62  jz      short loc_18003BE74
0x18003be64  mov     ebx, r13d
0x18003be67  jmp     short loc_18003BE7C
0x18003be69  mov     r13d, 800704C7h
0x18003be6f  mov     ebx, r13d
0x18003be72  jmp     short loc_18003BE52
0x18003be74  mov     r14, [rbp+37h+arg_18]
0x18003be78  test    ebx, ebx
0x18003be7a  jns     short loc_18003BEC6
0x18003be7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003be83  lea     r14, WPP_GLOBAL_Control
0x18003be8a  cmp     rcx, r14
0x18003be8d  jz      short loc_18003BEBD
0x18003be8f  test    byte ptr [rcx+1Ch], 2
0x18003be93  jz      short loc_18003BEBD
0x18003be95  mov     edx, 55h ; 'U'
0x18003be9a  mov     r9d, ebx
0x18003be9d  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003bea4  mov     rcx, [rcx+10h]
0x18003bea8  call    WPP_SF_d
0x18003bead  mov     rsi, [rbp+37h+var_88]
0x18003beb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003beb8  jmp     loc_18003BCDD
0x18003bebd  mov     rsi, [rbp+37h+var_88]
0x18003bec1  jmp     loc_18003BCDD
0x18003bec6  lea     r8, [rbp+37h+pidl]
0x18003beca  mov     rsi, [rbp+37h+var_88]
0x18003bece  mov     rdx, rsi
0x18003bed1  mov     rcx, r14
0x18003bed4  call    SHILCombine
0x18003bed9  mov     ebx, eax
0x18003bedb  test    eax, eax
0x18003bedd  jns     short loc_18003BF1A
0x18003bedf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bee6  lea     r14, WPP_GLOBAL_Control
0x18003beed  cmp     rcx, r14
0x18003bef0  jz      loc_18003BCDD
0x18003bef6  test    byte ptr [rcx+1Ch], 2
0x18003befa  jz      loc_18003BCDD
0x18003bf00  mov     edx, 56h ; 'V'
0x18003bf05  mov     r9d, eax
0x18003bf08  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003bf0f  mov     rcx, [rcx+10h]
0x18003bf13  call    WPP_SF_d
0x18003bf18  jmp     short loc_18003BEB1
0x18003bf1a  mov     [rsp+0C0h+ppv], rdi; struct CProgressUI *
0x18003bf1f  mov     r9d, [rbp+37h+arg_38]; int
0x18003bf23  mov     r8, r15; unsigned __int16 *
0x18003bf26  mov     rdx, r12; struct IPortableDevice *
0x18003bf29  call    ?_DeleteExistingObject@CContentDropTarget@@AEAAJPEAUIPortableDevice@@PEBGHPEAVCProgressUI@@@Z; CContentDropTarget::_DeleteExistingObject(IPortableDevice *,ushort const *,int,CProgressUI *)
0x18003bf2e  mov     ebx, eax
0x18003bf30  test    eax, eax
0x18003bf32  jns     short loc_18003BF5C
0x18003bf34  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf3b  lea     r14, WPP_GLOBAL_Control
0x18003bf42  cmp     rcx, r14
0x18003bf45  jz      loc_18003BCDD
0x18003bf4b  test    byte ptr [rcx+1Ch], 2
0x18003bf4f  jz      loc_18003BCDD
0x18003bf55  mov     edx, 57h ; 'W'
0x18003bf5a  jmp     short loc_18003BF05
0x18003bf5c  mov     eax, [rbp+37h+var_90]
0x18003bf5f  neg     eax
0x18003bf61  sbb     ecx, ecx
0x18003bf63  and     ecx, 0Ch
0x18003bf66  add     ecx, 4; wEventId
0x18003bf69  xor     r9d, r9d; dwItem2
0x18003bf6c  mov     r8, [rbp+37h+pidl]; dwItem1
0x18003bf70  xor     edx, edx; uFlags
0x18003bf72  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18003bf77  jmp     short loc_18003BF7F
0x18003bf79  mov     r13d, 800704C7h
0x18003bf7f  xor     r14d, r14d
0x18003bf82  mov     r15, [rbp+37h+arg_10]
0x18003bf86  mov     rax, [r15]
0x18003bf89  lea     r9, [rbp+37h+var_70]
0x18003bf8d  mov     r8, [rbp+37h+arg_20]
0x18003bf91  mov     rdx, [rbp+37h+var_80]
0x18003bf95  mov     rcx, r15
0x18003bf98  mov     rax, [rax+60h]
0x18003bf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfa1  mov     ebx, eax
0x18003bfa3  cmp     eax, 1
0x18003bfa6  jnz     short loc_18003BFF1
0x18003bfa8  mov     ebx, 80004005h
0x18003bfad  xorps   xmm0, xmm0
0x18003bfb0  xor     eax, eax
0x18003bfb2  movups  xmmword ptr [rbp+37h+pvar], xmm0
0x18003bfb6  mov     qword ptr [rbp+37h+pvar+10h], rax
0x18003bfba  mov     rcx, [rbp+37h+var_70]
0x18003bfbe  mov     rax, [rcx]
0x18003bfc1  lea     r8, [rbp+37h+pvar]
0x18003bfc5  xor     edx, edx
0x18003bfc7  mov     rax, [rax+20h]
0x18003bfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfd0  test    eax, eax
0x18003bfd2  js      short loc_18003BFE7
0x18003bfd4  mov     eax, 0Ah
0x18003bfd9  cmp     ax, word ptr [rbp+37h+pvar]
0x18003bfdd  jnz     short loc_18003BFE7
0x18003bfdf  mov     eax, dword ptr [rbp+37h+pvar+8]
0x18003bfe2  test    eax, eax
0x18003bfe4  cmovs   ebx, eax
0x18003bfe7  lea     rcx, [rbp+37h+pvar]; pvar
0x18003bfeb  call    cs:__imp_PropVariantClear
0x18003bff1  cmp     ebx, 800700AAh
0x18003bff7  jnz     short loc_18003C02D
0x18003bff9  test    r14d, r14d
0x18003bffc  jnz     short loc_18003C00C
0x18003bffe  mov     r14d, 1
0x18003c004  mov     rcx, rdi; this
0x18003c007  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003c00c  cmp     dword ptr [rdi+68h], 0
0x18003c010  jnz     short loc_18003C028
0x18003c012  mov     ecx, 5DCh; dwMilliseconds
0x18003c017  call    cs:__imp_Sleep
0x18003c01d  test    r14d, r14d
0x18003c020  jnz     loc_18003BF86
0x18003c026  jmp     short loc_18003C031
0x18003c028  mov     ebx, r13d
0x18003c02b  jmp     short loc_18003C031
0x18003c02d  test    ebx, ebx
0x18003c02f  jns     short loc_18003C05F
0x18003c031  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c038  lea     r14, WPP_GLOBAL_Control
0x18003c03f  cmp     rcx, r14
0x18003c042  jz      loc_18003BCDD
0x18003c048  test    byte ptr [rcx+1Ch], 2
0x18003c04c  jz      loc_18003BCDD
0x18003c052  mov     edx, 58h ; 'X'
0x18003c057  mov     r9d, ebx
0x18003c05a  jmp     loc_18003BF08
0x18003c05f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c066  jmp     loc_18003BCD6
```
