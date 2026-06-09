# CBaseDropTarget::Drop(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x18006f710`
- end: `0x18006fa3c`
- name: `?Drop@CBaseDropTarget@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `812`
- prototype: `__int64 __usercall@<rax>(CBaseDropTarget *__hidden this@<rcx>, struct IDataObject *@<rdx>, unsigned int@<r8d>, struct _POINTL@<r9>, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000d610`
- `0x18001d860`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800621ec`
- `0x18006f0d4`
- `0x18006f3cc`
- `0x18006f434`
- `0x18006f710`
- `0x180078010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18006f950`
- `SHLWAPI!__imp_SHCreateThread` at `0x18006f950`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x18006f904`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x18006f904`
- `SHELL32!__imp_ILFree` at `0x18006f91e`
- `SHELL32!__imp_ILFree` at `0x18006f91e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBaseDropTarget::Drop(
        CBaseDropTarget *this,
        struct IDataObject *a2,
        __int64 a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  int v8; // esi
  int Instance; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  struct CDragDropState *v12; // rbx
  const struct std::nothrow_t *v13; // rdx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  struct CDragDropState *v17; // rax
  unsigned int v18; // r9d
  COPY_THREAD_DATA *v19; // rbx
  unsigned int v20; // edx
  __int64 v21; // r12
  ITEMIDLIST *v22; // rcx
  int v24; // [rsp+40h] [rbp-31h] BYREF
  struct CDragDropState *v25[3]; // [rsp+48h] [rbp-29h] BYREF
  struct _GUID v26; // [rsp+60h] [rbp-11h] BYREF
  GUID v27; // [rsp+70h] [rbp-1h] BYREF

  v24 = 0;
  v27 = GUID_NULL;
  v25[0] = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( !a5 )
      goto LABEL_47;
    goto LABEL_46;
  }
  if ( !a5 )
  {
    v8 = -2147467261;
    goto LABEL_47;
  }
  *a5 = *((_DWORD *)this + 19);
  if ( !*((_DWORD *)this + 19) )
  {
    v8 = 0;
    goto LABEL_47;
  }
  Instance = CDragDropState::CreateInstance(v25);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_46;
    v11 = 18;
    goto LABEL_10;
  }
  v12 = v25[0];
  Instance = (*(__int64 (__fastcall **)(CBaseDropTarget *, struct IDataObject *, struct CDragDropState *))(*(_QWORD *)this + 104LL))(
               this,
               a2,
               v25[0]);
  v8 = Instance;
  if ( Instance < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_46;
    v11 = 19;
    goto LABEL_10;
  }
  if ( (*((_BYTE *)this + 72) & 1) == 0 )
  {
    Instance = (*(__int64 (__fastcall **)(CBaseDropTarget *, struct _POINTL, int *, unsigned int *, GUID *, struct CDragDropState *))(*(_QWORD *)this + 96LL))(
                 this,
                 a4,
                 &v24,
                 a5,
                 &v27,
                 v12);
    v8 = Instance;
    if ( Instance < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_46;
      v11 = 20;
LABEL_10:
      WPP_SF_d(v10[2], v11, WPP_3117870e9a7032c8e21a47ea31dcd621_Traceguids, (unsigned int)Instance);
      goto LABEL_46;
    }
    goto LABEL_23;
  }
  if ( *a5 == 1 )
  {
    v14 = 2;
  }
  else
  {
    if ( *a5 != 2 )
    {
LABEL_23:
      v14 = v24;
      goto LABEL_26;
    }
    v14 = 3;
  }
  v24 = v14;
LABEL_26:
  v15 = v14 - 2;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      if ( v16 != 3 )
        goto LABEL_40;
    }
  }
  v17 = (struct CDragDropState *)operator new(0x11D0u, v13);
  v25[1] = v17;
  if ( v17 )
  {
    v26 = v27;
    v19 = COPY_THREAD_DATA::COPY_THREAD_DATA(v17, this, *a5, v18, &v26, v12);
  }
  else
  {
    v19 = 0;
  }
  if ( !v19 )
  {
    v8 = -2147024882;
    goto LABEL_47;
  }
  if ( CoMarshalInterThreadInterfaceInStream(&IID_IDataObject, *((LPUNKNOWN *)this + 8), (LPSTREAM *)v19 + 568) >= 0 )
  {
    v21 = *((_QWORD *)this + 7);
    v22 = (ITEMIDLIST *)*((_QWORD *)v19 + 3);
    if ( v22 )
      ILFree(v22);
    *((_QWORD *)v19 + 3) = 0;
    if ( !v21 || (int)SHILCloneFirst(v21, (char *)v19 + 24) >= 0 )
    {
      if ( SHCreateThread(CBaseDropTarget::_DoCopyThreadProc, v19, 8u, 0) )
      {
LABEL_40:
        DataObj_SetDWORD(a2, g_cfLogicalPerformedDropEffect, *a5);
        if ( *a5 != 2 )
          goto LABEL_47;
LABEL_46:
        *a5 = 0;
        goto LABEL_47;
      }
    }
  }
  COPY_THREAD_DATA::`scalar deleting destructor'(v19, v20);
  v8 = -2147467259;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_3117870e9a7032c8e21a47ea31dcd621_Traceguids, 2147500037LL);
LABEL_47:
  (*(void (__fastcall **)(CBaseDropTarget *))(*(_QWORD *)this + 40LL))(this);
  if ( v8 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_3117870e9a7032c8e21a47ea31dcd621_Traceguids, (unsigned int)v8);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006f710  mov     [rsp-8+arg_10], rbx
0x18006f715  push    rbp
0x18006f716  push    rsi
0x18006f717  push    rdi
0x18006f718  push    r12
0x18006f71a  push    r13
0x18006f71c  push    r14
0x18006f71e  push    r15
0x18006f720  lea     rbp, [rsp-1Fh]
0x18006f725  sub     rsp, 90h
0x18006f72c  mov     rax, cs:__security_cookie
0x18006f733  xor     rax, rsp
0x18006f736  mov     [rbp+4Fh+var_40], rax
0x18006f73a  mov     rdi, r9
0x18006f73d  mov     r13, rdx
0x18006f740  mov     r15, rcx
0x18006f743  mov     r14, [rbp+4Fh+arg_20]
0x18006f747  mov     [rbp+4Fh+var_80], 0
0x18006f74e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006f755  movdqu  [rbp+4Fh+var_50], xmm0
0x18006f75a  mov     [rbp+4Fh+var_78], 0
0x18006f762  lea     r12, WPP_GLOBAL_Control
0x18006f769  test    rdx, rdx
0x18006f76c  jz      loc_18006F9BB
0x18006f772  test    r14, r14
0x18006f775  jnz     short loc_18006F781
0x18006f777  mov     esi, 80004003h
0x18006f77c  jmp     loc_18006F9CC
0x18006f781  mov     eax, [rcx+4Ch]
0x18006f784  mov     [r14], eax
0x18006f787  cmp     dword ptr [rcx+4Ch], 0
0x18006f78b  jnz     short loc_18006F794
0x18006f78d  xor     esi, esi
0x18006f78f  jmp     loc_18006F9CC
0x18006f794  lea     rcx, [rbp+4Fh+var_78]; struct CDragDropState **
0x18006f798  call    ?CreateInstance@CDragDropState@@SAJPEAPEAV1@@Z; CDragDropState::CreateInstance(CDragDropState * *)
0x18006f79d  mov     esi, eax
0x18006f79f  test    eax, eax
0x18006f7a1  jns     short loc_18006F7DA
0x18006f7a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f7aa  cmp     rcx, r12
0x18006f7ad  jz      loc_18006F9C5
0x18006f7b3  test    byte ptr [rcx+1Ch], 2
0x18006f7b7  jz      loc_18006F9C5
0x18006f7bd  mov     edx, 12h
0x18006f7c2  mov     r9d, eax
0x18006f7c5  lea     r8, WPP_3117870e9a7032c8e21a47ea31dcd621_Traceguids
0x18006f7cc  mov     rcx, [rcx+10h]
0x18006f7d0  call    WPP_SF_d
0x18006f7d5  jmp     loc_18006F9C5
0x18006f7da  mov     rax, [r15]
0x18006f7dd  mov     rbx, [rbp+4Fh+var_78]
0x18006f7e1  mov     r8, rbx
0x18006f7e4  mov     rdx, r13
0x18006f7e7  mov     rcx, r15
0x18006f7ea  mov     rax, [rax+68h]
0x18006f7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7f3  mov     esi, eax
0x18006f7f5  test    eax, eax
0x18006f7f7  jns     short loc_18006F81A
0x18006f7f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f800  cmp     rcx, r12
0x18006f803  jz      loc_18006F9C5
0x18006f809  test    byte ptr [rcx+1Ch], 2
0x18006f80d  jz      loc_18006F9C5
0x18006f813  mov     edx, 13h
0x18006f818  jmp     short loc_18006F7C2
0x18006f81a  test    byte ptr [r15+48h], 1
0x18006f81f  jnz     short loc_18006F872
0x18006f821  mov     rax, [r15]
0x18006f824  mov     [rsp+0C0h+var_98], rbx
0x18006f829  lea     rcx, [rbp+4Fh+var_50]
0x18006f82d  mov     [rsp+0C0h+var_A0], rcx
0x18006f832  mov     r9, r14
0x18006f835  lea     r8, [rbp+4Fh+var_80]
0x18006f839  mov     rdx, rdi
0x18006f83c  mov     rcx, r15
0x18006f83f  mov     rax, [rax+60h]
0x18006f843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f848  mov     esi, eax
0x18006f84a  test    eax, eax
0x18006f84c  jns     short loc_18006F884
0x18006f84e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f855  cmp     rcx, r12
0x18006f858  jz      loc_18006F9C5
0x18006f85e  test    byte ptr [rcx+1Ch], 2
0x18006f862  jz      loc_18006F9C5
0x18006f868  mov     edx, 14h
0x18006f86d  jmp     loc_18006F7C2
0x18006f872  mov     ecx, [r14]
0x18006f875  sub     ecx, 1
0x18006f878  jz      short loc_18006F889
0x18006f87a  cmp     ecx, 1
0x18006f87d  jnz     short loc_18006F884
0x18006f87f  lea     eax, [rcx+2]
0x18006f882  jmp     short loc_18006F88E
0x18006f884  mov     eax, [rbp+4Fh+var_80]
0x18006f887  jmp     short loc_18006F891
0x18006f889  mov     eax, 2
0x18006f88e  mov     [rbp+4Fh+var_80], eax
0x18006f891  sub     eax, 2
0x18006f894  jz      short loc_18006F8A4
0x18006f896  sub     eax, 1
0x18006f899  jz      short loc_18006F8A4
0x18006f89b  cmp     eax, 3
0x18006f89e  jnz     loc_18006F961
0x18006f8a4  mov     ecx, 11D0h; unsigned __int64
0x18006f8a9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006f8ae  mov     [rbp+4Fh+var_70], rax
0x18006f8b2  test    rax, rax
0x18006f8b5  jz      short loc_18006F8E1
0x18006f8b7  movaps  xmm0, [rbp+4Fh+var_50]
0x18006f8bb  movdqa  xmmword ptr [rbp+4Fh+var_60.Data1], xmm0
0x18006f8c0  mov     [rsp+0C0h+var_98], rbx; struct CDragDropState *
0x18006f8c5  lea     rcx, [rbp+4Fh+var_60]
0x18006f8c9  mov     [rsp+0C0h+var_A0], rcx; struct _GUID *
0x18006f8ce  mov     r8d, [r14]; unsigned int
0x18006f8d1  mov     rdx, r15; struct CBaseDropTarget *
0x18006f8d4  mov     rcx, rax; this
0x18006f8d7  call    ??0COPY_THREAD_DATA@@QEAA@PEAVCBaseDropTarget@@KKU_GUID@@PEAVCDragDropState@@@Z; COPY_THREAD_DATA::COPY_THREAD_DATA(CBaseDropTarget *,ulong,ulong,_GUID,CDragDropState *)
0x18006f8dc  mov     rbx, rax
0x18006f8df  jmp     short loc_18006F8E3
0x18006f8e1  xor     ebx, ebx
0x18006f8e3  test    rbx, rbx
0x18006f8e6  jnz     short loc_18006F8F2
0x18006f8e8  mov     esi, 8007000Eh
0x18006f8ed  jmp     loc_18006F9CC
0x18006f8f2  lea     r8, [rbx+11C0h]; ppStm
0x18006f8f9  mov     rdx, [r15+40h]; pUnk
0x18006f8fd  lea     rcx, IID_IDataObject; riid
0x18006f904  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18006f90a  test    eax, eax
0x18006f90c  js      short loc_18006F982
0x18006f90e  mov     r12, [r15+38h]
0x18006f912  lea     rdi, [rbx+18h]
0x18006f916  mov     rcx, [rdi]; pidl
0x18006f919  test    rcx, rcx
0x18006f91c  jz      short loc_18006F924
0x18006f91e  call    cs:__imp_ILFree
0x18006f924  mov     qword ptr [rdi], 0
0x18006f92b  test    r12, r12
0x18006f92e  jz      short loc_18006F93F
0x18006f930  mov     rdx, rdi
0x18006f933  mov     rcx, r12
0x18006f936  call    SHILCloneFirst
0x18006f93b  test    eax, eax
0x18006f93d  js      short loc_18006F97B
0x18006f93f  xor     r9d, r9d; pfnCallback
0x18006f942  lea     r8d, [r9+8]; flags
0x18006f946  mov     rdx, rbx; pData
0x18006f949  lea     rcx, ?_DoCopyThreadProc@CBaseDropTarget@@KAKPEAX@Z; pfnThreadProc
0x18006f950  call    cs:__imp_SHCreateThread
0x18006f956  lea     r12, WPP_GLOBAL_Control
0x18006f95d  test    eax, eax
0x18006f95f  jz      short loc_18006F982
0x18006f961  movzx   edx, cs:?g_cfLogicalPerformedDropEffect@@3GA; ushort g_cfLogicalPerformedDropEffect
0x18006f968  mov     r8d, [r14]
0x18006f96b  mov     rcx, r13
0x18006f96e  call    DataObj_SetDWORD
0x18006f973  cmp     dword ptr [r14], 2
0x18006f977  jnz     short loc_18006F9CC
0x18006f979  jmp     short loc_18006F9C5
0x18006f97b  lea     r12, WPP_GLOBAL_Control
0x18006f982  mov     rcx, rbx; this
0x18006f985  call    ??_GCOPY_THREAD_DATA@@QEAAPEAXI@Z; COPY_THREAD_DATA::`scalar deleting destructor'(uint)
0x18006f98a  mov     esi, 80004005h
0x18006f98f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f996  cmp     rcx, r12
0x18006f999  jz      short loc_18006F9CC
0x18006f99b  test    byte ptr [rcx+1Ch], 2
0x18006f99f  jz      short loc_18006F9CC
0x18006f9a1  mov     edx, 15h
0x18006f9a6  mov     r9d, esi
0x18006f9a9  lea     r8, WPP_3117870e9a7032c8e21a47ea31dcd621_Traceguids
0x18006f9b0  mov     rcx, [rcx+10h]
0x18006f9b4  call    WPP_SF_d
0x18006f9b9  jmp     short loc_18006F9CC
0x18006f9bb  mov     esi, 80070057h
0x18006f9c0  test    r14, r14
0x18006f9c3  jz      short loc_18006F9CC
0x18006f9c5  mov     dword ptr [r14], 0
0x18006f9cc  mov     rax, [r15]
0x18006f9cf  mov     rcx, r15
0x18006f9d2  mov     rax, [rax+28h]
0x18006f9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f9db  test    esi, esi
0x18006f9dd  jns     short loc_18006FA0A
0x18006f9df  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f9e6  cmp     rcx, r12
0x18006f9e9  jz      short loc_18006FA0A
0x18006f9eb  test    byte ptr [rcx+1Ch], 2
0x18006f9ef  jz      short loc_18006FA0A
0x18006f9f1  mov     edx, 16h
0x18006f9f6  mov     r9d, esi
0x18006f9f9  lea     r8, WPP_3117870e9a7032c8e21a47ea31dcd621_Traceguids
0x18006fa00  mov     rcx, [rcx+10h]
0x18006fa04  call    WPP_SF_d
0x18006fa09  nop
0x18006fa0a  lea     rcx, [rbp+4Fh+var_78]
0x18006fa0e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006fa13  mov     eax, esi
0x18006fa15  mov     rcx, [rbp+4Fh+var_40]
0x18006fa19  xor     rcx, rsp; StackCookie
0x18006fa1c  call    __security_check_cookie
0x18006fa21  mov     rbx, [rsp+0C0h+arg_10]
0x18006fa29  add     rsp, 90h
0x18006fa30  pop     r15
0x18006fa32  pop     r14
0x18006fa34  pop     r13
0x18006fa36  pop     r12
0x18006fa38  pop     rdi
0x18006fa39  pop     rsi
0x18006fa3a  pop     rbp
0x18006fa3b  retn
```
