# CContentDropTarget::_DoDeviceSideCopy(IDataObject *,COPY_THREAD_DATA *)

- ea: `0x18003da14`
- end: `0x18003e1b7`
- name: `?_DoDeviceSideCopy@CContentDropTarget@@AEAAJPEAUIDataObject@@PEAVCOPY_THREAD_DATA@@@Z`
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
- `0x18003c074`
- `0x18003da14`
- `0x180054524`
- `0x1800545c8`
- `0x1800628cc`
- `0x180062e70`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003dd13`
- `KERNEL32!Sleep` at `0x18003deae`
- `KERNEL32!Sleep` at `0x18003dfe8`
- `KERNEL32!Sleep` at `0x18003e093`
- `KERNEL32!Sleep` at `0x18003dd13`
- `KERNEL32!Sleep` at `0x18003deae`
- `KERNEL32!Sleep` at `0x18003dfe8`
- `KERNEL32!Sleep` at `0x18003e093`
- `KERNEL32!GetCurrentThreadId` at `0x18003dc6c`
- `KERNEL32!GetCurrentThreadId` at `0x18003dcb8`
- `KERNEL32!GetCurrentThreadId` at `0x18003dc6c`
- `KERNEL32!GetCurrentThreadId` at `0x18003dcb8`
- `SHELL32!__imp_ILFindLastID` at `0x18003def3`
- `SHELL32!__imp_ILFindLastID` at `0x18003def3`
- `SHELL32!__imp_ILFree` at `0x18003e145`
- `SHELL32!__imp_ILFree` at `0x18003e145`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDropTarget::_DoDeviceSideCopy(
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
      v11 = 64;
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
        65,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v13);
    goto LABEL_12;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, struct COPY_THREAD_DATA *, struct IDataObject *, __int64, int, int, _QWORD, _QWORD))(**((_QWORD **)a3 + 559) + 64LL))(
         *((_QWORD *)a3 + 559),
         a3,
         a2,
         2,
         110,
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
      v23 = 67;
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
          68,
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
        v23 = 69;
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
          v33 = 70;
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
            v9 = CContentDropTarget::_DeviceSideCopyObject(this, v40, v42, v39, pidl, v46, a3);
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
              v33 = 71;
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
    v11 = 66;
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003da14  mov     [rsp-8+arg_18], rbx
0x18003da19  push    rbp
0x18003da1a  push    rsi
0x18003da1b  push    rdi
0x18003da1c  push    r12
0x18003da1e  push    r13
0x18003da20  push    r14
0x18003da22  push    r15
0x18003da24  lea     rbp, [rsp-5D0h]
0x18003da2c  sub     rsp, 6D0h
0x18003da33  mov     rax, cs:__security_cookie
0x18003da3a  xor     rax, rsp
0x18003da3d  mov     [rbp+600h+var_40], rax
0x18003da44  mov     r14, r8
0x18003da47  mov     rdi, rdx
0x18003da4a  mov     [rsp+700h+var_698], rdx
0x18003da4f  mov     r13, rcx
0x18003da52  xorps   xmm0, xmm0
0x18003da55  xor     eax, eax
0x18003da57  movups  [rsp+700h+var_690], xmm0
0x18003da5c  mov     [rbp+600h+var_680], rax
0x18003da60  xor     r12d, r12d
0x18003da63  mov     [rsp+700h+var_6B0], rax
0x18003da68  mov     [rsp+700h+var_6A0], r12
0x18003da6d  mov     rcx, [rcx+50h]
0x18003da71  mov     rdx, [rcx+40h]
0x18003da75  mov     [rsp+700h+pidl], rdx
0x18003da7a  mov     rax, [rcx]
0x18003da7d  add     r8, 0D50h
0x18003da84  mov     r9d, 104h
0x18003da8a  mov     rax, [rax+90h]
0x18003da91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da96  mov     ebx, eax
0x18003da98  lea     rsi, WPP_GLOBAL_Control
0x18003da9f  test    eax, eax
0x18003daa1  jns     short loc_18003DAF6
0x18003daa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003daaa  cmp     rcx, rsi
0x18003daad  jz      short loc_18003DACD
0x18003daaf  test    byte ptr [rcx+1Ch], 2
0x18003dab3  jz      short loc_18003DACD
0x18003dab5  lea     edx, [r12+40h]
0x18003daba  mov     r9d, eax
0x18003dabd  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003dac4  mov     rcx, [rcx+10h]
0x18003dac8  call    WPP_SF_d
0x18003dacd  lea     rsi, WPP_GLOBAL_Control
0x18003dad4  mov     dword ptr [rsp+700h+var_6E0], 0; int
0x18003dadc  mov     r9, r14; struct COPY_THREAD_DATA *
0x18003dadf  xor     r8d, r8d; unsigned __int16 *
0x18003dae2  mov     edx, ebx; int
0x18003dae4  mov     rcx, r13; this
0x18003dae7  call    ?_DisplayErrorMessage@CContentDropTarget@@AEAAXJPEBGPEAVCOPY_THREAD_DATA@@H@Z; CContentDropTarget::_DisplayErrorMessage(long,ushort const *,COPY_THREAD_DATA *,int)
0x18003daec  test    r12, r12
0x18003daef  jz      short loc_18003DB4E
0x18003daf1  jmp     loc_18003E1A7
0x18003daf6  mov     rcx, [r13+50h]
0x18003dafa  mov     rax, [rcx]
0x18003dafd  mov     r8d, 104h
0x18003db03  lea     rdx, [rbp+600h+var_460]
0x18003db0a  mov     rax, [rax+60h]
0x18003db0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db13  mov     ebx, eax
0x18003db15  test    eax, eax
0x18003db17  jns     loc_18003DBEA
0x18003db1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db24  cmp     rcx, rsi
0x18003db27  jz      short loc_18003DB47
0x18003db29  test    byte ptr [rcx+1Ch], 2
0x18003db2d  jz      short loc_18003DB47
0x18003db2f  mov     edx, 41h ; 'A'
0x18003db34  mov     r9d, eax
0x18003db37  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003db3e  mov     rcx, [rcx+10h]
0x18003db42  call    WPP_SF_d
0x18003db47  lea     rsi, WPP_GLOBAL_Control
0x18003db4e  xor     r9d, r9d; dwItem2
0x18003db51  mov     r8, [rsp+700h+pidl]; dwItem1
0x18003db56  xor     edx, edx; uFlags
0x18003db58  mov     ecx, 1000h; wEventId
0x18003db5d  call    ?ChangeNotify@@YAXJIPEFBU_ITEMIDLIST@@0@Z; ChangeNotify(long,uint,_ITEMIDLIST const *,_ITEMIDLIST const *)
0x18003db62  mov     rcx, [r13+50h]
0x18003db66  mov     rax, [rcx]
0x18003db69  mov     rdx, [rsp+700h+pidl]
0x18003db6e  mov     rax, [rax+0A0h]
0x18003db75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db7a  test    ebx, ebx
0x18003db7c  jns     short loc_18003DBA9
0x18003db7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db85  cmp     rcx, rsi
0x18003db88  jz      short loc_18003DBA9
0x18003db8a  test    byte ptr [rcx+1Ch], 2
0x18003db8e  jz      short loc_18003DBA9
0x18003db90  mov     edx, 48h ; 'H'
0x18003db95  mov     r9d, ebx
0x18003db98  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003db9f  mov     rcx, [rcx+10h]
0x18003dba3  call    WPP_SF_d
0x18003dba8  nop
0x18003dba9  lea     rcx, [rsp+700h+var_6A0]
0x18003dbae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003dbb3  nop
0x18003dbb4  lea     rcx, [rsp+700h+var_6B0]
0x18003dbb9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003dbbe  mov     eax, ebx
0x18003dbc0  mov     rcx, [rbp+600h+var_40]
0x18003dbc7  xor     rcx, rsp; StackCookie
0x18003dbca  call    __security_check_cookie
0x18003dbcf  mov     rbx, [rsp+700h+arg_18]
0x18003dbd7  add     rsp, 6D0h
0x18003dbde  pop     r15
0x18003dbe0  pop     r14
0x18003dbe2  pop     r13
0x18003dbe4  pop     r12
0x18003dbe6  pop     rdi
0x18003dbe7  pop     rsi
0x18003dbe8  pop     rbp
0x18003dbe9  retn
0x18003dbea  mov     rcx, [r14+1178h]
0x18003dbf1  mov     rax, [rcx]
0x18003dbf4  mov     [rsp+700h+var_6C8], 0
0x18003dbfd  mov     [rsp+700h+var_6D0], 0
0x18003dc06  mov     dword ptr [rsp+700h+var_6D8], 1
0x18003dc0e  mov     dword ptr [rsp+700h+var_6E0], 6Eh ; 'n'
0x18003dc16  mov     r9d, 2
0x18003dc1c  mov     r8, rdi
0x18003dc1f  mov     rdx, r14
0x18003dc22  mov     rax, [rax+40h]
0x18003dc26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc2b  mov     ebx, eax
0x18003dc2d  test    eax, eax
0x18003dc2f  jns     short loc_18003DC55
0x18003dc31  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dc38  cmp     rcx, rsi
0x18003dc3b  jz      loc_18003DACD
0x18003dc41  test    byte ptr [rcx+1Ch], 2
0x18003dc45  jz      loc_18003DACD
0x18003dc4b  mov     edx, 42h ; 'B'
0x18003dc50  jmp     loc_18003DABA
0x18003dc55  mov     rdi, [r14+1168h]
0x18003dc5c  test    rdi, rdi
0x18003dc5f  jnz     short loc_18003DC9B
0x18003dc61  mov     rcx, [r13+28h]; this
0x18003dc65  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x18003dc6a  mov     ebx, eax
0x18003dc6c  call    cs:__imp_GetCurrentThreadId
0x18003dc72  lea     rcx, [rsp+700h+var_6B0]
0x18003dc77  mov     [rsp+700h+var_6D8], rcx; struct IPortableDevice **
0x18003dc7c  mov     dword ptr [rsp+700h+var_6E0], ebx; int
0x18003dc80  xor     r9d, r9d; struct _ITEMIDLIST *
0x18003dc83  xor     r8d, r8d; struct _ITEMIDLIST *
0x18003dc86  mov     edx, eax; unsigned int
0x18003dc88  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x18003dc8f  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x18003dc94  mov     ebx, eax
0x18003dc96  jmp     loc_18003DD50
0x18003dc9b  xor     r15d, r15d
0x18003dc9e  xor     esi, esi
0x18003dca0  mov     rax, [r14+1168h]
0x18003dca7  cmp     dword ptr [rax+68h], 0
0x18003dcab  jnz     short loc_18003DD20
0x18003dcad  mov     rcx, [r13+28h]; this
0x18003dcb1  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x18003dcb6  mov     ebx, eax
0x18003dcb8  call    cs:__imp_GetCurrentThreadId
0x18003dcbe  lea     rcx, [rsp+700h+var_6B0]
0x18003dcc3  mov     [rsp+700h+var_6D8], rcx; struct IPortableDevice **
0x18003dcc8  mov     dword ptr [rsp+700h+var_6E0], ebx; int
0x18003dccc  xor     r9d, r9d; struct _ITEMIDLIST *
0x18003dccf  xor     r8d, r8d; struct _ITEMIDLIST *
0x18003dcd2  mov     edx, eax; unsigned int
0x18003dcd4  lea     rcx, [rbp+600h+var_460]; unsigned __int16 *
0x18003dcdb  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x18003dce0  mov     ebx, eax
0x18003dce2  cmp     eax, 800700AAh
0x18003dce7  jnz     short loc_18003DD25
0x18003dce9  test    r15d, r15d
0x18003dcec  jnz     short loc_18003DD01
0x18003dcee  lea     esi, [r15+1]
0x18003dcf2  mov     r15d, esi
0x18003dcf5  mov     rcx, [r14+1168h]; this
0x18003dcfc  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003dd01  mov     rax, [r14+1168h]
0x18003dd08  cmp     dword ptr [rax+68h], 0
0x18003dd0c  jnz     short loc_18003DD20
0x18003dd0e  mov     ecx, 5DCh; dwMilliseconds
0x18003dd13  call    cs:__imp_Sleep
0x18003dd19  test    r15d, r15d
0x18003dd1c  jz      short loc_18003DD25
0x18003dd1e  jmp     short loc_18003DCA0
0x18003dd20  mov     ebx, 800704C7h
0x18003dd25  test    esi, esi
0x18003dd27  jz      short loc_18003DD35
0x18003dd29  mov     rcx, [r14+1168h]; this
0x18003dd30  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003dd35  mov     rax, [r14+1168h]
0x18003dd3c  cmp     dword ptr [rax+68h], 0
0x18003dd40  jz      short loc_18003DD49
0x18003dd42  mov     ebx, 800704C7h
0x18003dd47  jmp     short loc_18003DD54
0x18003dd49  lea     rsi, WPP_GLOBAL_Control
0x18003dd50  test    ebx, ebx
0x18003dd52  jns     short loc_18003DD92
0x18003dd54  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd5b  lea     rsi, WPP_GLOBAL_Control
0x18003dd62  cmp     rcx, rsi
0x18003dd65  jz      loc_18003DB4E
0x18003dd6b  test    byte ptr [rcx+1Ch], 2
0x18003dd6f  jz      loc_18003DB4E
0x18003dd75  mov     edx, 43h ; 'C'
0x18003dd7a  mov     r9d, ebx
0x18003dd7d  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003dd84  mov     rcx, [rcx+10h]
0x18003dd88  call    WPP_SF_d
0x18003dd8d  jmp     loc_18003DB4E
0x18003dd92  mov     rcx, [r14+1178h]
0x18003dd99  mov     rax, [rcx]
0x18003dd9c  mov     r8, [rsp+700h+var_6B0]
0x18003dda1  mov     rdx, r14
0x18003dda4  mov     rax, [rax+48h]
0x18003dda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ddad  mov     ebx, eax
0x18003ddaf  test    eax, eax
0x18003ddb1  jns     short loc_18003DDFE
0x18003ddb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ddba  cmp     rcx, rsi
0x18003ddbd  jz      short loc_18003DDDD
0x18003ddbf  test    byte ptr [rcx+1Ch], 2
0x18003ddc3  jz      short loc_18003DDDD
0x18003ddc5  mov     edx, 44h ; 'D'
0x18003ddca  mov     r9d, eax
0x18003ddcd  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003ddd4  mov     rcx, [rcx+10h]
0x18003ddd8  call    WPP_SF_d
0x18003dddd  lea     rsi, WPP_GLOBAL_Control
0x18003dde4  mov     eax, 800704C7h
0x18003dde9  test    rdi, rdi
0x18003ddec  jz      loc_18003DAD4
0x18003ddf2  cmp     dword ptr [rdi+68h], 0
0x18003ddf6  cmovnz  ebx, eax
0x18003ddf9  jmp     loc_18003DAD4
0x18003ddfe  cmp     qword ptr [r14+1168h], 0
0x18003de06  jnz     short loc_18003DE53
0x18003de08  mov     rcx, [rsp+700h+var_6B0]
0x18003de0d  mov     rax, [rcx]
0x18003de10  lea     rdx, [rsp+700h+var_6A0]
0x18003de15  mov     rax, [rax+28h]
0x18003de19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de1e  mov     ebx, eax
0x18003de20  test    ebx, ebx
0x18003de22  jns     loc_18003DEEB
0x18003de28  mov     rcx, cs:WPP_GLOBAL_Control
0x18003de2f  lea     rsi, WPP_GLOBAL_Control
0x18003de36  cmp     rcx, rsi
0x18003de39  jz      loc_18003DB4E
0x18003de3f  test    byte ptr [rcx+1Ch], 2
0x18003de43  jz      loc_18003DB4E
0x18003de49  mov     edx, 45h ; 'E'
0x18003de4e  jmp     loc_18003DD7A
0x18003de53  xor     r15d, r15d
0x18003de56  xor     esi, esi
0x18003de58  mov     rax, [r14+1168h]
0x18003de5f  cmp     dword ptr [rax+68h], 0
0x18003de63  jnz     short loc_18003DEBB
0x18003de65  mov     rcx, [rsp+700h+var_6B0]
0x18003de6a  mov     rax, [rcx]
0x18003de6d  lea     rdx, [rsp+700h+var_6A0]
0x18003de72  mov     rax, [rax+28h]
0x18003de76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003de7b  mov     ebx, eax
0x18003de7d  cmp     eax, 800700AAh
0x18003de82  jnz     short loc_18003DEC0
0x18003de84  test    r15d, r15d
0x18003de87  jnz     short loc_18003DE9C
0x18003de89  lea     esi, [r15+1]
0x18003de8d  mov     r15d, esi
0x18003de90  mov     rcx, [r14+1168h]; this
0x18003de97  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003de9c  mov     rax, [r14+1168h]
0x18003dea3  cmp     dword ptr [rax+68h], 0
0x18003dea7  jnz     short loc_18003DEBB
0x18003dea9  mov     ecx, 5DCh; dwMilliseconds
0x18003deae  call    cs:__imp_Sleep
0x18003deb4  test    r15d, r15d
0x18003deb7  jz      short loc_18003DEC0
0x18003deb9  jmp     short loc_18003DE58
0x18003debb  mov     ebx, 800704C7h
0x18003dec0  test    esi, esi
0x18003dec2  jz      short loc_18003DED0
0x18003dec4  mov     rcx, [r14+1168h]; this
0x18003decb  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003ded0  mov     rax, [r14+1168h]
0x18003ded7  cmp     dword ptr [rax+68h], 0
0x18003dedb  jz      loc_18003DE20
0x18003dee1  mov     ebx, 800704C7h
0x18003dee6  jmp     loc_18003DE28
0x18003deeb  mov     rbx, [rsp+700h+pidl]
0x18003def0  mov     rcx, rbx; pidl
0x18003def3  call    cs:__imp_ILFindLastID
0x18003def9  mov     rdx, rax; struct _ITEMIDLIST *
  ... truncated ...
```
