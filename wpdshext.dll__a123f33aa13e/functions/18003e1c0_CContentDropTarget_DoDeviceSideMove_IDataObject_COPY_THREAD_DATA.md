# CContentDropTarget::_DoDeviceSideMove(IDataObject *,COPY_THREAD_DATA *)

- ea: `0x18003e1c0`
- end: `0x18003e963`
- name: `?_DoDeviceSideMove@CContentDropTarget@@AEAAJPEAUIDataObject@@PEAVCOPY_THREAD_DATA@@@Z`
- size: `1955`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, struct IDataObject *, struct COPY_THREAD_DATA *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f360`

## callees

- `0x180004110`
- `0x1800050d0`
- `0x1800082e0`
- `0x18000c180`
- `0x180015484`
- `0x1800194d8`
- `0x180024aa4`
- `0x1800285c8`
- `0x180028ea8`
- `0x18002ff5c`
- `0x180035590`
- `0x18003cce4`
- `0x18003e1c0`
- `0x180054524`
- `0x1800545c8`
- `0x1800628cc`
- `0x180062e70`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003e4bf`
- `KERNEL32!Sleep` at `0x18003e65a`
- `KERNEL32!Sleep` at `0x18003e794`
- `KERNEL32!Sleep` at `0x18003e83f`
- `KERNEL32!Sleep` at `0x18003e4bf`
- `KERNEL32!Sleep` at `0x18003e65a`
- `KERNEL32!Sleep` at `0x18003e794`
- `KERNEL32!Sleep` at `0x18003e83f`
- `KERNEL32!GetCurrentThreadId` at `0x18003e418`
- `KERNEL32!GetCurrentThreadId` at `0x18003e464`
- `KERNEL32!GetCurrentThreadId` at `0x18003e418`
- `KERNEL32!GetCurrentThreadId` at `0x18003e464`
- `SHELL32!__imp_ILFindLastID` at `0x18003e69f`
- `SHELL32!__imp_ILFindLastID` at `0x18003e69f`
- `SHELL32!__imp_ILFree` at `0x18003e8f1`
- `SHELL32!__imp_ILFree` at `0x18003e8f1`

## pseudocode

```c
__int64 __fastcall CContentDropTarget::_DoDeviceSideMove(
        CContentDropTarget *this,
        struct IDataObject *a2,
        struct COPY_THREAD_DATA *a3)
{
  unsigned int *HIDA; // r12
  LPCITEMIDLIST *v7; // rcx
  int v8; // eax
  int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  CProgressUI *v15; // rdi
  int v16; // ebx
  DWORD v17; // eax
  int v18; // r15d
  int v19; // esi
  int IsDelegateFolder; // ebx
  DWORD CurrentThreadId; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // r15d
  int v26; // esi
  LPCITEMIDLIST v27; // rbx
  const struct _ITEMIDLIST *ID; // rax
  CContentFolder *v29; // rcx
  const struct CONTENTITEM *v30; // rax
  int ObjectID; // eax
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  int v34; // r15d
  int v35; // esi
  int v36; // r15d
  int v37; // esi
  unsigned int i; // esi
  ITEMIDLIST *v39; // r15
  struct IPortableDevice *v40; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST pidl; // [rsp+58h] [rbp-A8h]
  struct IPortableDeviceContent *v42; // [rsp+60h] [rbp-A0h] BYREF
  struct IDataObject *v43; // [rsp+68h] [rbp-98h]
  __int128 v44; // [rsp+70h] [rbp-90h] BYREF
  __int64 v45; // [rsp+80h] [rbp-80h]
  unsigned __int16 v46[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v47[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v48[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v43 = a2;
  v44 = 0;
  v45 = 0;
  HIDA = 0;
  v40 = 0;
  v42 = 0;
  v7 = (LPCITEMIDLIST *)*((_QWORD *)this + 10);
  pidl = v7[8];
  v8 = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, LPCITEMIDLIST, char *, __int64))&(*v7)[48].mkid.cb)(
         v7,
         pidl,
         (char *)a3 + 3408,
         260);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 36;
LABEL_5:
      WPP_SF_d(v10[2], v11, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v8);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 10) + 96LL))(
          *((_QWORD *)this + 10),
          v47,
          260);
  v9 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v13);
    goto LABEL_12;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, struct COPY_THREAD_DATA *, struct IDataObject *, __int64, int, int, _QWORD, _QWORD))(**((_QWORD **)a3 + 559) + 64LL))(
         *((_QWORD *)a3 + 559),
         a3,
         a2,
         1,
         112,
         1,
         0,
         0);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v15 = (CProgressUI *)*((_QWORD *)a3 + 557);
    if ( v15 )
    {
      v18 = 0;
      v19 = 0;
      while ( !*(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
      {
        IsDelegateFolder = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)this + 5));
        CurrentThreadId = GetCurrentThreadId();
        v9 = CDeviceCache::s_BindToPortableDevice(v47, CurrentThreadId, 0, 0, IsDelegateFolder, &v40);
        if ( v9 != -2147024726 )
          goto LABEL_31;
        if ( !v18 )
        {
          v19 = 1;
          v18 = 1;
          CProgressUI::_StartMarquee(*((CProgressUI **)a3 + 557));
        }
        if ( *(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
          break;
        Sleep(0x5DCu);
      }
      v9 = -2147023673;
LABEL_31:
      if ( v19 )
        CProgressUI::_StopMarquee(*((CProgressUI **)a3 + 557));
      if ( *(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
      {
        v9 = -2147023673;
        goto LABEL_36;
      }
    }
    else
    {
      v16 = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)this + 5));
      v17 = GetCurrentThreadId();
      v9 = CDeviceCache::s_BindToPortableDevice(v47, v17, 0, 0, v16, &v40);
    }
    if ( v9 < 0 )
    {
LABEL_36:
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_12;
      v23 = 39;
      goto LABEL_39;
    }
    v24 = (*(__int64 (__fastcall **)(_QWORD, struct COPY_THREAD_DATA *, struct IPortableDevice *))(**((_QWORD **)a3 + 559)
                                                                                                 + 72LL))(
            *((_QWORD *)a3 + 559),
            a3,
            v40);
    v9 = v24;
    if ( v24 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
          (unsigned int)v24);
LABEL_44:
      if ( v15 && *((_DWORD *)v15 + 26) )
        v9 = -2147023673;
      goto LABEL_6;
    }
    if ( *((_QWORD *)a3 + 557) )
    {
      v25 = 0;
      v26 = 0;
      while ( !*(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
      {
        v9 = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceContent **))v40->lpVtbl->Content)(
               v40,
               &v42);
        if ( v9 != -2147024726 )
          goto LABEL_62;
        if ( !v25 )
        {
          v26 = 1;
          v25 = 1;
          CProgressUI::_StartMarquee(*((CProgressUI **)a3 + 557));
        }
        if ( *(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
          break;
        Sleep(0x5DCu);
      }
      v9 = -2147023673;
LABEL_62:
      if ( v26 )
        CProgressUI::_StopMarquee(*((CProgressUI **)a3 + 557));
      if ( *(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
      {
        v9 = -2147023673;
LABEL_51:
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_12;
        v23 = 41;
LABEL_39:
        WPP_SF_d(v22[2], v23, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v9);
        goto LABEL_12;
      }
    }
    else
    {
      v9 = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceContent **))v40->lpVtbl->Content)(
             v40,
             &v42);
    }
    if ( v9 < 0 )
      goto LABEL_51;
    v27 = pidl;
    ID = ILFindLastID(pidl);
    v30 = CContentFolder::_IsValid(v29, ID);
    if ( v30 )
    {
      StringCchCopyW(
        v48,
        0x104u,
        (const unsigned __int16 *)v30 + *(unsigned int *)((char *)v30 + 62) + *(unsigned int *)((char *)v30 + 66) + 37);
      if ( !v15 )
      {
        ObjectID = CBaseFolder::_GetObjectID(*((CBaseFolder **)this + 10), v48, v46, 0x104u);
LABEL_69:
        v9 = ObjectID;
        goto LABEL_70;
      }
      v34 = 0;
      v35 = 0;
      while ( !*((_DWORD *)v15 + 26) )
      {
        v9 = CBaseFolder::_GetObjectID(*((CBaseFolder **)this + 10), v48, v46, 0x104u);
        if ( v9 != -2147024726 )
          goto LABEL_83;
        if ( !v34 )
        {
          v35 = 1;
          v34 = 1;
          CProgressUI::_StartMarquee(v15);
        }
        if ( *((_DWORD *)v15 + 26) )
          break;
        Sleep(0x5DCu);
      }
      v9 = -2147023673;
LABEL_83:
      if ( v35 )
        CProgressUI::_StopMarquee(v15);
      if ( *((_DWORD *)v15 + 26) )
        v9 = -2147023673;
    }
    else
    {
      if ( !v15 )
      {
        ObjectID = (*(__int64 (__fastcall **)(_QWORD, LPCITEMIDLIST, unsigned __int16 *, __int64))(**((_QWORD **)this + 10)
                                                                                                 + 88LL))(
                     *((_QWORD *)this + 10),
                     v27,
                     v46,
                     260);
        goto LABEL_69;
      }
      v36 = 0;
      v37 = 0;
      while ( !*((_DWORD *)v15 + 26) )
      {
        v9 = (*(__int64 (__fastcall **)(_QWORD, LPCITEMIDLIST, unsigned __int16 *, __int64))(**((_QWORD **)this + 10)
                                                                                           + 88LL))(
               *((_QWORD *)this + 10),
               v27,
               v46,
               260);
        if ( v9 != -2147024726 )
          goto LABEL_97;
        if ( !v36 )
        {
          v37 = 1;
          v36 = 1;
          CProgressUI::_StartMarquee(v15);
        }
        if ( *((_DWORD *)v15 + 26) )
          break;
        Sleep(0x5DCu);
        v27 = pidl;
      }
      v9 = -2147023673;
LABEL_97:
      if ( v37 )
        CProgressUI::_StopMarquee(v15);
      if ( *((_DWORD *)v15 + 26) )
      {
        v9 = -2147023673;
LABEL_71:
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v33 = 42;
LABEL_74:
          WPP_SF_d(v32[2], v33, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v9);
        }
        goto LABEL_44;
      }
    }
LABEL_70:
    if ( v9 >= 0 )
    {
      HIDA = (unsigned int *)DataObj_GetHIDA(v43, &v44);
      if ( HIDA )
      {
        for ( i = 0; v9 >= 0 && i < *HIDA; ++i )
        {
          v39 = (ITEMIDLIST *)IDA_ILClone(HIDA, i);
          if ( v39 )
          {
            v9 = CContentDropTarget::_DeviceSideMoveObject(this, v40, v42, v39, pidl, v46, a3);
            ILFree(v39);
            if ( v9 < 0 )
              continue;
          }
          v9 = CProgressUI::_IncrementProgress(v15, 1u);
          if ( v9 < 0 )
          {
            v32 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v33 = 43;
              goto LABEL_74;
            }
            goto LABEL_44;
          }
          if ( *((_DWORD *)v15 + 26) )
            v9 = -2147023673;
        }
        goto LABEL_115;
      }
      v9 = -2147418113;
      goto LABEL_44;
    }
    goto LABEL_71;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v11 = 38;
    goto LABEL_5;
  }
LABEL_6:
  CContentDropTarget::_DisplayErrorMessage(this, v9, 0, a3, 0);
  if ( HIDA )
LABEL_115:
    ReleaseStgMediumHGLOBAL(v12, &v44);
LABEL_12:
  ChangeNotify(4096, 0, pidl, 0);
  (*(void (__fastcall **)(_QWORD, LPCITEMIDLIST))(**((_QWORD **)this + 10) + 160LL))(*((_QWORD *)this + 10), pidl);
  if ( v9 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003e1c0  mov     [rsp-8+arg_18], rbx
0x18003e1c5  push    rbp
0x18003e1c6  push    rsi
0x18003e1c7  push    rdi
0x18003e1c8  push    r12
0x18003e1ca  push    r13
0x18003e1cc  push    r14
0x18003e1ce  push    r15
0x18003e1d0  lea     rbp, [rsp-5D0h]
0x18003e1d8  sub     rsp, 6D0h
0x18003e1df  mov     rax, cs:__security_cookie
0x18003e1e6  xor     rax, rsp
0x18003e1e9  mov     [rbp+600h+var_40], rax
0x18003e1f0  mov     r14, r8
0x18003e1f3  mov     rdi, rdx
0x18003e1f6  mov     [rsp+700h+var_698], rdx
0x18003e1fb  mov     r13, rcx
0x18003e1fe  xorps   xmm0, xmm0
0x18003e201  xor     eax, eax
0x18003e203  movups  [rsp+700h+var_690], xmm0
0x18003e208  mov     [rbp+600h+var_680], rax
0x18003e20c  xor     r12d, r12d
0x18003e20f  mov     [rsp+700h+var_6B0], rax
0x18003e214  mov     [rsp+700h+var_6A0], r12
0x18003e219  mov     rcx, [rcx+50h]
0x18003e21d  mov     rdx, [rcx+40h]
0x18003e221  mov     [rsp+700h+pidl], rdx
0x18003e226  mov     rax, [rcx]
0x18003e229  add     r8, 0D50h
0x18003e230  mov     r9d, 104h
0x18003e236  mov     rax, [rax+90h]
0x18003e23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e242  mov     ebx, eax
0x18003e244  lea     rsi, WPP_GLOBAL_Control
0x18003e24b  test    eax, eax
0x18003e24d  jns     short loc_18003E2A2
0x18003e24f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e256  cmp     rcx, rsi
0x18003e259  jz      short loc_18003E279
0x18003e25b  test    byte ptr [rcx+1Ch], 2
0x18003e25f  jz      short loc_18003E279
0x18003e261  lea     edx, [r12+24h]
0x18003e266  mov     r9d, eax
0x18003e269  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003e270  mov     rcx, [rcx+10h]
0x18003e274  call    WPP_SF_d
0x18003e279  lea     rsi, WPP_GLOBAL_Control
0x18003e280  mov     dword ptr [rsp+700h+var_6E0], 0; int
0x18003e288  mov     r9, r14; struct COPY_THREAD_DATA *
0x18003e28b  xor     r8d, r8d; unsigned __int16 *
0x18003e28e  mov     edx, ebx; int
0x18003e290  mov     rcx, r13; this
0x18003e293  call    ?_DisplayErrorMessage@CContentDropTarget@@AEAAXJPEBGPEAVCOPY_THREAD_DATA@@H@Z; CContentDropTarget::_DisplayErrorMessage(long,ushort const *,COPY_THREAD_DATA *,int)
0x18003e298  test    r12, r12
0x18003e29b  jz      short loc_18003E2FA
0x18003e29d  jmp     loc_18003E953
0x18003e2a2  mov     rcx, [r13+50h]
0x18003e2a6  mov     rax, [rcx]
0x18003e2a9  mov     r8d, 104h
0x18003e2af  lea     rdx, [rbp+600h+var_460]
0x18003e2b6  mov     rax, [rax+60h]
0x18003e2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2bf  mov     ebx, eax
0x18003e2c1  test    eax, eax
0x18003e2c3  jns     loc_18003E396
0x18003e2c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e2d0  cmp     rcx, rsi
0x18003e2d3  jz      short loc_18003E2F3
0x18003e2d5  test    byte ptr [rcx+1Ch], 2
0x18003e2d9  jz      short loc_18003E2F3
0x18003e2db  mov     edx, 25h ; '%'
0x18003e2e0  mov     r9d, eax
0x18003e2e3  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003e2ea  mov     rcx, [rcx+10h]
0x18003e2ee  call    WPP_SF_d
0x18003e2f3  lea     rsi, WPP_GLOBAL_Control
0x18003e2fa  xor     r9d, r9d; dwItem2
0x18003e2fd  mov     r8, [rsp+700h+pidl]; dwItem1
0x18003e302  xor     edx, edx; uFlags
0x18003e304  mov     ecx, 1000h; wEventId
0x18003e309  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18003e30e  mov     rcx, [r13+50h]
0x18003e312  mov     rax, [rcx]
0x18003e315  mov     rdx, [rsp+700h+pidl]
0x18003e31a  mov     rax, [rax+0A0h]
0x18003e321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e326  test    ebx, ebx
0x18003e328  jns     short loc_18003E355
0x18003e32a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e331  cmp     rcx, rsi
0x18003e334  jz      short loc_18003E355
0x18003e336  test    byte ptr [rcx+1Ch], 2
0x18003e33a  jz      short loc_18003E355
0x18003e33c  mov     edx, 2Ch ; ','
0x18003e341  mov     r9d, ebx
0x18003e344  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003e34b  mov     rcx, [rcx+10h]
0x18003e34f  call    WPP_SF_d
0x18003e354  nop
0x18003e355  lea     rcx, [rsp+700h+var_6A0]
0x18003e35a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003e35f  nop
0x18003e360  lea     rcx, [rsp+700h+var_6B0]
0x18003e365  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003e36a  mov     eax, ebx
0x18003e36c  mov     rcx, [rbp+600h+var_40]
0x18003e373  xor     rcx, rsp; StackCookie
0x18003e376  call    __security_check_cookie
0x18003e37b  mov     rbx, [rsp+700h+arg_18]
0x18003e383  add     rsp, 6D0h
0x18003e38a  pop     r15
0x18003e38c  pop     r14
0x18003e38e  pop     r13
0x18003e390  pop     r12
0x18003e392  pop     rdi
0x18003e393  pop     rsi
0x18003e394  pop     rbp
0x18003e395  retn
0x18003e396  mov     rcx, [r14+1178h]
0x18003e39d  mov     rax, [rcx]
0x18003e3a0  mov     [rsp+700h+var_6C8], 0
0x18003e3a9  mov     [rsp+700h+var_6D0], 0
0x18003e3b2  mov     dword ptr [rsp+700h+var_6D8], 1
0x18003e3ba  mov     dword ptr [rsp+700h+var_6E0], 70h ; 'p'
0x18003e3c2  mov     r9d, 1
0x18003e3c8  mov     r8, rdi
0x18003e3cb  mov     rdx, r14
0x18003e3ce  mov     rax, [rax+40h]
0x18003e3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3d7  mov     ebx, eax
0x18003e3d9  test    eax, eax
0x18003e3db  jns     short loc_18003E401
0x18003e3dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3e4  cmp     rcx, rsi
0x18003e3e7  jz      loc_18003E279
0x18003e3ed  test    byte ptr [rcx+1Ch], 2
0x18003e3f1  jz      loc_18003E279
0x18003e3f7  mov     edx, 26h ; '&'
0x18003e3fc  jmp     loc_18003E266
0x18003e401  mov     rdi, [r14+1168h]
0x18003e408  test    rdi, rdi
0x18003e40b  jnz     short loc_18003E447
0x18003e40d  mov     rcx, [r13+28h]; this
0x18003e411  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x18003e416  mov     ebx, eax
0x18003e418  call    cs:__imp_GetCurrentThreadId
0x18003e41e  lea     rcx, [rsp+700h+var_6B0]
0x18003e423  mov     [rsp+700h+var_6D8], rcx; struct IPortableDevice **
0x18003e428  mov     dword ptr [rsp+700h+var_6E0], ebx; int
0x18003e42c  xor     r9d, r9d; struct _ITEMIDLIST *
0x18003e42f  xor     r8d, r8d; struct _ITEMIDLIST *
0x18003e432  mov     edx, eax; unsigned int
0x18003e434  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x18003e43b  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x18003e440  mov     ebx, eax
0x18003e442  jmp     loc_18003E4FC
0x18003e447  xor     r15d, r15d
0x18003e44a  xor     esi, esi
0x18003e44c  mov     rax, [r14+1168h]
0x18003e453  cmp     dword ptr [rax+68h], 0
0x18003e457  jnz     short loc_18003E4CC
0x18003e459  mov     rcx, [r13+28h]; this
0x18003e45d  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x18003e462  mov     ebx, eax
0x18003e464  call    cs:__imp_GetCurrentThreadId
0x18003e46a  lea     rcx, [rsp+700h+var_6B0]
0x18003e46f  mov     [rsp+700h+var_6D8], rcx; struct IPortableDevice **
0x18003e474  mov     dword ptr [rsp+700h+var_6E0], ebx; int
0x18003e478  xor     r9d, r9d; struct _ITEMIDLIST *
0x18003e47b  xor     r8d, r8d; struct _ITEMIDLIST *
0x18003e47e  mov     edx, eax; unsigned int
0x18003e480  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x18003e487  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x18003e48c  mov     ebx, eax
0x18003e48e  cmp     eax, 800700AAh
0x18003e493  jnz     short loc_18003E4D1
0x18003e495  test    r15d, r15d
0x18003e498  jnz     short loc_18003E4AD
0x18003e49a  lea     esi, [r15+1]
0x18003e49e  mov     r15d, esi
0x18003e4a1  mov     rcx, [r14+1168h]; this
0x18003e4a8  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003e4ad  mov     rax, [r14+1168h]
0x18003e4b4  cmp     dword ptr [rax+68h], 0
0x18003e4b8  jnz     short loc_18003E4CC
0x18003e4ba  mov     ecx, 5DCh; dwMilliseconds
0x18003e4bf  call    cs:__imp_Sleep
0x18003e4c5  test    r15d, r15d
0x18003e4c8  jz      short loc_18003E4D1
0x18003e4ca  jmp     short loc_18003E44C
0x18003e4cc  mov     ebx, 800704C7h
0x18003e4d1  test    esi, esi
0x18003e4d3  jz      short loc_18003E4E1
0x18003e4d5  mov     rcx, [r14+1168h]; this
0x18003e4dc  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003e4e1  mov     rax, [r14+1168h]
0x18003e4e8  cmp     dword ptr [rax+68h], 0
0x18003e4ec  jz      short loc_18003E4F5
0x18003e4ee  mov     ebx, 800704C7h
0x18003e4f3  jmp     short loc_18003E500
0x18003e4f5  lea     rsi, WPP_GLOBAL_Control
0x18003e4fc  test    ebx, ebx
0x18003e4fe  jns     short loc_18003E53E
0x18003e500  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e507  lea     rsi, WPP_GLOBAL_Control
0x18003e50e  cmp     rcx, rsi
0x18003e511  jz      loc_18003E2FA
0x18003e517  test    byte ptr [rcx+1Ch], 2
0x18003e51b  jz      loc_18003E2FA
0x18003e521  mov     edx, 27h ; '''
0x18003e526  mov     r9d, ebx
0x18003e529  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003e530  mov     rcx, [rcx+10h]
0x18003e534  call    WPP_SF_d
0x18003e539  jmp     loc_18003E2FA
0x18003e53e  mov     rcx, [r14+1178h]
0x18003e545  mov     rax, [rcx]
0x18003e548  mov     r8, [rsp+700h+var_6B0]
0x18003e54d  mov     rdx, r14
0x18003e550  mov     rax, [rax+48h]
0x18003e554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e559  mov     ebx, eax
0x18003e55b  test    eax, eax
0x18003e55d  jns     short loc_18003E5AA
0x18003e55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e566  cmp     rcx, rsi
0x18003e569  jz      short loc_18003E589
0x18003e56b  test    byte ptr [rcx+1Ch], 2
0x18003e56f  jz      short loc_18003E589
0x18003e571  mov     edx, 28h ; '('
0x18003e576  mov     r9d, eax
0x18003e579  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003e580  mov     rcx, [rcx+10h]
0x18003e584  call    WPP_SF_d
0x18003e589  lea     rsi, WPP_GLOBAL_Control
0x18003e590  mov     eax, 800704C7h
0x18003e595  test    rdi, rdi
0x18003e598  jz      loc_18003E280
0x18003e59e  cmp     dword ptr [rdi+68h], 0
0x18003e5a2  cmovnz  ebx, eax
0x18003e5a5  jmp     loc_18003E280
0x18003e5aa  cmp     qword ptr [r14+1168h], 0
0x18003e5b2  jnz     short loc_18003E5FF
0x18003e5b4  mov     rcx, [rsp+700h+var_6B0]
0x18003e5b9  mov     rax, [rcx]
0x18003e5bc  lea     rdx, [rsp+700h+var_6A0]
0x18003e5c1  mov     rax, [rax+28h]
0x18003e5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5ca  mov     ebx, eax
0x18003e5cc  test    ebx, ebx
0x18003e5ce  jns     loc_18003E697
0x18003e5d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5db  lea     rsi, WPP_GLOBAL_Control
0x18003e5e2  cmp     rcx, rsi
0x18003e5e5  jz      loc_18003E2FA
0x18003e5eb  test    byte ptr [rcx+1Ch], 2
0x18003e5ef  jz      loc_18003E2FA
0x18003e5f5  mov     edx, 29h ; ')'
0x18003e5fa  jmp     loc_18003E526
0x18003e5ff  xor     r15d, r15d
0x18003e602  xor     esi, esi
0x18003e604  mov     rax, [r14+1168h]
0x18003e60b  cmp     dword ptr [rax+68h], 0
0x18003e60f  jnz     short loc_18003E667
0x18003e611  mov     rcx, [rsp+700h+var_6B0]
0x18003e616  mov     rax, [rcx]
0x18003e619  lea     rdx, [rsp+700h+var_6A0]
0x18003e61e  mov     rax, [rax+28h]
0x18003e622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e627  mov     ebx, eax
0x18003e629  cmp     eax, 800700AAh
0x18003e62e  jnz     short loc_18003E66C
0x18003e630  test    r15d, r15d
0x18003e633  jnz     short loc_18003E648
0x18003e635  lea     esi, [r15+1]
0x18003e639  mov     r15d, esi
0x18003e63c  mov     rcx, [r14+1168h]; this
0x18003e643  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003e648  mov     rax, [r14+1168h]
0x18003e64f  cmp     dword ptr [rax+68h], 0
0x18003e653  jnz     short loc_18003E667
0x18003e655  mov     ecx, 5DCh; dwMilliseconds
0x18003e65a  call    cs:__imp_Sleep
0x18003e660  test    r15d, r15d
0x18003e663  jz      short loc_18003E66C
0x18003e665  jmp     short loc_18003E604
0x18003e667  mov     ebx, 800704C7h
0x18003e66c  test    esi, esi
0x18003e66e  jz      short loc_18003E67C
0x18003e670  mov     rcx, [r14+1168h]; this
0x18003e677  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003e67c  mov     rax, [r14+1168h]
0x18003e683  cmp     dword ptr [rax+68h], 0
0x18003e687  jz      loc_18003E5CC
0x18003e68d  mov     ebx, 800704C7h
0x18003e692  jmp     loc_18003E5D4
0x18003e697  mov     rbx, [rsp+700h+pidl]
0x18003e69c  mov     rcx, rbx; pidl
0x18003e69f  call    cs:__imp_ILFindLastID
0x18003e6a5  mov     rdx, rax; struct _ITEMIDLIST *
  ... truncated ...
```
