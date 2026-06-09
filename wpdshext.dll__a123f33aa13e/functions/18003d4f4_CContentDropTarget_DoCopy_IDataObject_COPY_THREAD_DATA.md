# CContentDropTarget::_DoCopy(IDataObject *,COPY_THREAD_DATA *)

- ea: `0x18003d4f4`
- end: `0x18003da0b`
- name: `?_DoCopy@CContentDropTarget@@AEAAJPEAUIDataObject@@PEAVCOPY_THREAD_DATA@@@Z`
- size: `1303`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, struct IDataObject *, struct COPY_THREAD_DATA *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18003f360`

## callees

- `0x18000c180`
- `0x180017c88`
- `0x1800194d8`
- `0x180024aa4`
- `0x1800285c8`
- `0x180028ea8`
- `0x18002ff5c`
- `0x180035590`
- `0x18003d4f4`
- `0x180054524`
- `0x1800545c8`
- `0x1800628cc`
- `0x180062e70`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003d72e`
- `KERNEL32!Sleep` at `0x18003d8a4`
- `KERNEL32!Sleep` at `0x18003d72e`
- `KERNEL32!Sleep` at `0x18003d8a4`
- `KERNEL32!GetCurrentThreadId` at `0x18003d68a`
- `KERNEL32!GetCurrentThreadId` at `0x18003d6d4`
- `KERNEL32!GetCurrentThreadId` at `0x18003d68a`
- `KERNEL32!GetCurrentThreadId` at `0x18003d6d4`
- `SHELL32!__imp_ILFree` at `0x18003d967`
- `SHELL32!__imp_ILFree` at `0x18003d967`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDropTarget::_DoCopy(
        CContentDropTarget *this,
        struct IDataObject *a2,
        struct COPY_THREAD_DATA *a3)
{
  int v6; // eax
  int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  int v11; // ebx
  DWORD v12; // eax
  int v13; // r14d
  int v14; // esi
  int IsDelegateFolder; // ebx
  DWORD CurrentThreadId; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // r14d
  int v20; // esi
  __int64 v21; // rcx
  unsigned int *HIDA; // r14
  unsigned int v23; // esi
  const struct _ITEMIDLIST *v24; // rax
  ITEMIDLIST *v25; // r15
  struct IPortableDevice *v27; // [rsp+50h] [rbp-B0h] BYREF
  struct IPortableDeviceContent *v28; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h]
  unsigned __int16 v31[264]; // [rsp+80h] [rbp-80h] BYREF

  v29 = 0;
  v30 = 0;
  v27 = 0;
  v28 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, __int64))(**((_QWORD **)this + 10) + 144LL))(
         *((_QWORD *)this + 10),
         *(_QWORD *)(*((_QWORD *)this + 10) + 64LL),
         (char *)a3 + 3408,
         260);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_57;
    v9 = 22;
    goto LABEL_5;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)this + 10) + 96LL))(
          *((_QWORD *)this + 10),
          v31,
          260);
  v7 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v10);
    goto LABEL_64;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, struct COPY_THREAD_DATA *, struct IDataObject *, __int64, int, _DWORD, _QWORD, _QWORD))(**((_QWORD **)a3 + 559) + 64LL))(
         *((_QWORD *)a3 + 559),
         a3,
         a2,
         2,
         (*(_DWORD *)a3 & 2) != 0 ? 112 : 110,
         0,
         0,
         0);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_57;
    v9 = 24;
    goto LABEL_5;
  }
  if ( *((_QWORD *)a3 + 557) )
  {
    v13 = 0;
    v14 = 0;
    while ( !*(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
    {
      IsDelegateFolder = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)this + 5));
      CurrentThreadId = GetCurrentThreadId();
      v7 = CDeviceCache::s_BindToPortableDevice(v31, CurrentThreadId, 0, 0, IsDelegateFolder, &v27);
      if ( v7 != -2147024726 )
        goto LABEL_24;
      if ( !v13 )
      {
        v13 = 1;
        v14 = 1;
        CProgressUI::_StartMarquee(*((CProgressUI **)a3 + 557));
      }
      if ( *(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
        break;
      Sleep(0x5DCu);
    }
    v7 = -2147023673;
LABEL_24:
    if ( v14 )
      CProgressUI::_StopMarquee(*((CProgressUI **)a3 + 557));
    if ( *(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
    {
      v7 = -2147023673;
      goto LABEL_29;
    }
  }
  else
  {
    v11 = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)this + 5));
    v12 = GetCurrentThreadId();
    v7 = CDeviceCache::s_BindToPortableDevice(v31, v12, 0, 0, v11, &v27);
  }
  if ( v7 < 0 )
  {
LABEL_29:
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_64;
    v18 = 25;
    goto LABEL_32;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, struct COPY_THREAD_DATA *, struct IPortableDevice *))(**((_QWORD **)a3 + 559)
                                                                                              + 72LL))(
         *((_QWORD *)a3 + 559),
         a3,
         v27);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_57;
    v9 = 26;
LABEL_5:
    WPP_SF_d(v8[2], v9, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v6);
LABEL_57:
    CContentDropTarget::_DisplayErrorMessage(this, v7, 0, a3, 0);
    goto LABEL_64;
  }
  if ( *((_QWORD *)a3 + 557) )
  {
    v19 = 0;
    v20 = 0;
    while ( !*(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
    {
      v7 = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceContent **))v27->lpVtbl->Content)(
             v27,
             &v28);
      if ( v7 != -2147024726 )
        goto LABEL_51;
      if ( !v19 )
      {
        v19 = 1;
        v20 = 1;
        CProgressUI::_StartMarquee(*((CProgressUI **)a3 + 557));
      }
      if ( *(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
        break;
      Sleep(0x5DCu);
    }
    v7 = -2147023673;
LABEL_51:
    if ( v20 )
      CProgressUI::_StopMarquee(*((CProgressUI **)a3 + 557));
    if ( *(_DWORD *)(*((_QWORD *)a3 + 557) + 104LL) )
    {
      v7 = -2147023673;
LABEL_40:
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_64;
      v18 = 27;
LABEL_32:
      WPP_SF_d(v17[2], v18, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v7);
      goto LABEL_64;
    }
  }
  else
  {
    v7 = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceContent **))v27->lpVtbl->Content)(
           v27,
           &v28);
  }
  if ( v7 < 0 )
    goto LABEL_40;
  HIDA = (unsigned int *)DataObj_GetHIDA(a2, &v29);
  if ( !HIDA )
  {
    v7 = -2147418113;
    goto LABEL_57;
  }
  v23 = 0;
  do
  {
    if ( v23 >= *HIDA )
      break;
    v24 = (const struct _ITEMIDLIST *)IDA_ILClone(HIDA, v23);
    v25 = (ITEMIDLIST *)v24;
    if ( v24 )
    {
      v7 = CContentDropTarget::_DoInsert(
             this,
             v24,
             *(struct _ITEMIDLIST **)(*((_QWORD *)this + 10) + 64LL),
             v27,
             v28,
             0,
             0,
             0,
             a3);
      ILFree(v25);
    }
    ++v23;
  }
  while ( v7 >= 0 );
  ReleaseStgMediumHGLOBAL(v21, &v29);
LABEL_64:
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 160LL))(
    *((_QWORD *)this + 10),
    *(_QWORD *)(*((_QWORD *)this + 10) + 64LL));
  if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)v7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003d4f4  mov     [rsp-8+arg_18], rbx
0x18003d4f9  push    rbp
0x18003d4fa  push    rsi
0x18003d4fb  push    rdi
0x18003d4fc  push    r12
0x18003d4fe  push    r13
0x18003d500  push    r14
0x18003d502  push    r15
0x18003d504  lea     rbp, [rsp-1A0h]
0x18003d50c  sub     rsp, 2A0h
0x18003d513  mov     rax, cs:__security_cookie
0x18003d51a  xor     rax, rsp
0x18003d51d  mov     [rbp+1D0h+var_40], rax
0x18003d524  mov     rdi, r8
0x18003d527  mov     r15, rdx
0x18003d52a  mov     r13, rcx
0x18003d52d  xorps   xmm0, xmm0
0x18003d530  xor     eax, eax
0x18003d532  movups  [rsp+2D0h+var_270], xmm0
0x18003d537  mov     [rsp+2D0h+var_260], rax
0x18003d53c  xor     r12d, r12d
0x18003d53f  mov     [rsp+2D0h+var_280], r12
0x18003d544  mov     [rsp+2D0h+var_278], r12
0x18003d549  mov     rcx, [rcx+50h]
0x18003d54d  mov     rax, [rcx]
0x18003d550  add     r8, 0D50h
0x18003d557  mov     r14d, 104h
0x18003d55d  mov     r9d, r14d
0x18003d560  mov     rdx, [rcx+40h]
0x18003d564  mov     rax, [rax+90h]
0x18003d56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d570  mov     ebx, eax
0x18003d572  lea     rsi, WPP_GLOBAL_Control
0x18003d579  test    eax, eax
0x18003d57b  jns     short loc_18003D5B4
0x18003d57d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d584  cmp     rcx, rsi
0x18003d587  jz      loc_18003D8FB
0x18003d58d  test    byte ptr [rcx+1Ch], 2
0x18003d591  jz      loc_18003D8FB
0x18003d597  lea     edx, [r12+16h]
0x18003d59c  mov     r9d, eax
0x18003d59f  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003d5a6  mov     rcx, [rcx+10h]
0x18003d5aa  call    WPP_SF_d
0x18003d5af  jmp     loc_18003D8FB
0x18003d5b4  mov     rcx, [r13+50h]
0x18003d5b8  mov     rax, [rcx]
0x18003d5bb  mov     r8d, r14d
0x18003d5be  lea     rdx, [rbp+1D0h+var_250]
0x18003d5c2  mov     rax, [rax+60h]
0x18003d5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5cb  mov     ebx, eax
0x18003d5cd  test    eax, eax
0x18003d5cf  jns     short loc_18003D608
0x18003d5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d5d8  cmp     rcx, rsi
0x18003d5db  jz      loc_18003D97D
0x18003d5e1  test    byte ptr [rcx+1Ch], 2
0x18003d5e5  jz      loc_18003D97D
0x18003d5eb  mov     edx, 17h
0x18003d5f0  mov     r9d, eax
0x18003d5f3  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003d5fa  mov     rcx, [rcx+10h]
0x18003d5fe  call    WPP_SF_d
0x18003d603  jmp     loc_18003D97D
0x18003d608  mov     rcx, [rdi+1178h]
0x18003d60f  mov     rdx, [rcx]
0x18003d612  mov     eax, [rdi]
0x18003d614  and     al, 2
0x18003d616  neg     al
0x18003d618  sbb     r8d, r8d
0x18003d61b  and     r8d, 2
0x18003d61f  add     r8d, 6Eh ; 'n'
0x18003d623  mov     rax, [rdx+40h]
0x18003d627  mov     qword ptr [rsp+2D0h+var_298], r12
0x18003d62c  mov     [rsp+2D0h+var_2A0], r12
0x18003d631  mov     dword ptr [rsp+2D0h+var_2A8], r12d
0x18003d636  mov     dword ptr [rsp+2D0h+var_2B0], r8d
0x18003d63b  mov     r9d, 2
0x18003d641  mov     r8, r15
0x18003d644  mov     rdx, rdi
0x18003d647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d64c  mov     ebx, eax
0x18003d64e  test    eax, eax
0x18003d650  jns     short loc_18003D676
0x18003d652  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d659  cmp     rcx, rsi
0x18003d65c  jz      loc_18003D8FB
0x18003d662  test    byte ptr [rcx+1Ch], 2
0x18003d666  jz      loc_18003D8FB
0x18003d66c  mov     edx, 18h
0x18003d671  jmp     loc_18003D59C
0x18003d676  cmp     [rdi+1168h], r12
0x18003d67d  jnz     short loc_18003D6B6
0x18003d67f  mov     rcx, [r13+28h]; this
0x18003d683  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x18003d688  mov     ebx, eax
0x18003d68a  call    cs:__imp_GetCurrentThreadId
0x18003d690  lea     rcx, [rsp+2D0h+var_280]
0x18003d695  mov     [rsp+2D0h+var_2A8], rcx; struct IPortableDevice **
0x18003d69a  mov     dword ptr [rsp+2D0h+var_2B0], ebx; int
0x18003d69e  xor     r9d, r9d; struct _ITEMIDLIST *
0x18003d6a1  xor     r8d, r8d; struct _ITEMIDLIST *
0x18003d6a4  mov     edx, eax; unsigned int
0x18003d6a6  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18003d6aa  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x18003d6af  mov     ebx, eax
0x18003d6b1  jmp     loc_18003D76B
0x18003d6b6  mov     r14d, r12d
0x18003d6b9  mov     esi, r12d
0x18003d6bc  mov     rax, [rdi+1168h]
0x18003d6c3  cmp     [rax+68h], r12d
0x18003d6c7  jnz     short loc_18003D73B
0x18003d6c9  mov     rcx, [r13+28h]; this
0x18003d6cd  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x18003d6d2  mov     ebx, eax
0x18003d6d4  call    cs:__imp_GetCurrentThreadId
0x18003d6da  lea     rcx, [rsp+2D0h+var_280]
0x18003d6df  mov     [rsp+2D0h+var_2A8], rcx; struct IPortableDevice **
0x18003d6e4  mov     dword ptr [rsp+2D0h+var_2B0], ebx; int
0x18003d6e8  xor     r9d, r9d; struct _ITEMIDLIST *
0x18003d6eb  xor     r8d, r8d; struct _ITEMIDLIST *
0x18003d6ee  mov     edx, eax; unsigned int
0x18003d6f0  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18003d6f4  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x18003d6f9  mov     ebx, eax
0x18003d6fb  cmp     eax, 800700AAh
0x18003d700  jnz     short loc_18003D740
0x18003d702  test    r14d, r14d
0x18003d705  jnz     short loc_18003D71C
0x18003d707  lea     eax, [r14+1]
0x18003d70b  mov     r14d, eax
0x18003d70e  mov     esi, eax
0x18003d710  mov     rcx, [rdi+1168h]; this
0x18003d717  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003d71c  mov     rax, [rdi+1168h]
0x18003d723  cmp     [rax+68h], r12d
0x18003d727  jnz     short loc_18003D73B
0x18003d729  mov     ecx, 5DCh; dwMilliseconds
0x18003d72e  call    cs:__imp_Sleep
0x18003d734  test    r14d, r14d
0x18003d737  jz      short loc_18003D740
0x18003d739  jmp     short loc_18003D6BC
0x18003d73b  mov     ebx, 800704C7h
0x18003d740  test    esi, esi
0x18003d742  jz      short loc_18003D750
0x18003d744  mov     rcx, [rdi+1168h]; this
0x18003d74b  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003d750  mov     rax, [rdi+1168h]
0x18003d757  cmp     [rax+68h], r12d
0x18003d75b  jz      short loc_18003D764
0x18003d75d  mov     ebx, 800704C7h
0x18003d762  jmp     short loc_18003D76F
0x18003d764  lea     rsi, WPP_GLOBAL_Control
0x18003d76b  test    ebx, ebx
0x18003d76d  jns     short loc_18003D7AD
0x18003d76f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d776  lea     rdi, WPP_GLOBAL_Control
0x18003d77d  cmp     rcx, rdi
0x18003d780  jz      loc_18003D984
0x18003d786  test    byte ptr [rcx+1Ch], 2
0x18003d78a  jz      loc_18003D984
0x18003d790  mov     edx, 19h
0x18003d795  mov     r9d, ebx
0x18003d798  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003d79f  mov     rcx, [rcx+10h]
0x18003d7a3  call    WPP_SF_d
0x18003d7a8  jmp     loc_18003D984
0x18003d7ad  mov     rcx, [rdi+1178h]
0x18003d7b4  mov     rax, [rcx]
0x18003d7b7  mov     r8, [rsp+2D0h+var_280]
0x18003d7bc  mov     rdx, rdi
0x18003d7bf  mov     rax, [rax+48h]
0x18003d7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7c8  mov     ebx, eax
0x18003d7ca  test    eax, eax
0x18003d7cc  jns     short loc_18003D7F2
0x18003d7ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d7d5  cmp     rcx, rsi
0x18003d7d8  jz      loc_18003D8FB
0x18003d7de  test    byte ptr [rcx+1Ch], 2
0x18003d7e2  jz      loc_18003D8FB
0x18003d7e8  mov     edx, 1Ah
0x18003d7ed  jmp     loc_18003D59C
0x18003d7f2  cmp     [rdi+1168h], r12
0x18003d7f9  jnz     short loc_18003D846
0x18003d7fb  mov     rcx, [rsp+2D0h+var_280]
0x18003d800  mov     rax, [rcx]
0x18003d803  lea     rdx, [rsp+2D0h+var_278]
0x18003d808  mov     rax, [rax+28h]
0x18003d80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d811  mov     ebx, eax
0x18003d813  test    ebx, ebx
0x18003d815  jns     loc_18003D8E1
0x18003d81b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d822  lea     rdi, WPP_GLOBAL_Control
0x18003d829  cmp     rcx, rdi
0x18003d82c  jz      loc_18003D984
0x18003d832  test    byte ptr [rcx+1Ch], 2
0x18003d836  jz      loc_18003D984
0x18003d83c  mov     edx, 1Bh
0x18003d841  jmp     loc_18003D795
0x18003d846  mov     r14d, r12d
0x18003d849  mov     esi, r12d
0x18003d84c  mov     rax, [rdi+1168h]
0x18003d853  cmp     [rax+68h], r12d
0x18003d857  jnz     short loc_18003D8B1
0x18003d859  mov     rcx, [rsp+2D0h+var_280]
0x18003d85e  mov     rax, [rcx]
0x18003d861  lea     rdx, [rsp+2D0h+var_278]
0x18003d866  mov     rax, [rax+28h]
0x18003d86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d86f  mov     ebx, eax
0x18003d871  cmp     eax, 800700AAh
0x18003d876  jnz     short loc_18003D8B6
0x18003d878  test    r14d, r14d
0x18003d87b  jnz     short loc_18003D892
0x18003d87d  lea     eax, [r14+1]
0x18003d881  mov     r14d, eax
0x18003d884  mov     esi, eax
0x18003d886  mov     rcx, [rdi+1168h]; this
0x18003d88d  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003d892  mov     rax, [rdi+1168h]
0x18003d899  cmp     [rax+68h], r12d
0x18003d89d  jnz     short loc_18003D8B1
0x18003d89f  mov     ecx, 5DCh; dwMilliseconds
0x18003d8a4  call    cs:__imp_Sleep
0x18003d8aa  test    r14d, r14d
0x18003d8ad  jz      short loc_18003D8B6
0x18003d8af  jmp     short loc_18003D84C
0x18003d8b1  mov     ebx, 800704C7h
0x18003d8b6  test    esi, esi
0x18003d8b8  jz      short loc_18003D8C6
0x18003d8ba  mov     rcx, [rdi+1168h]; this
0x18003d8c1  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003d8c6  mov     rax, [rdi+1168h]
0x18003d8cd  cmp     [rax+68h], r12d
0x18003d8d1  jz      loc_18003D813
0x18003d8d7  mov     ebx, 800704C7h
0x18003d8dc  jmp     loc_18003D81B
0x18003d8e1  lea     rdx, [rsp+2D0h+var_270]
0x18003d8e6  mov     rcx, r15
0x18003d8e9  call    DataObj_GetHIDA
0x18003d8ee  mov     r14, rax
0x18003d8f1  test    rax, rax
0x18003d8f4  jnz     short loc_18003D912
0x18003d8f6  mov     ebx, 8000FFFFh
0x18003d8fb  mov     dword ptr [rsp+2D0h+var_2B0], r12d; int
0x18003d900  mov     r9, rdi; struct COPY_THREAD_DATA *
0x18003d903  xor     r8d, r8d; unsigned __int16 *
0x18003d906  mov     edx, ebx; int
0x18003d908  mov     rcx, r13; this
0x18003d90b  call    ?_DisplayErrorMessage@CContentDropTarget@@AEAAXJPEBGPEAVCOPY_THREAD_DATA@@H@Z; CContentDropTarget::_DisplayErrorMessage(long,ushort const *,COPY_THREAD_DATA *,int)
0x18003d910  jmp     short loc_18003D97D
0x18003d912  mov     esi, r12d
0x18003d915  cmp     esi, [r14]
0x18003d918  jnb     short loc_18003D973
0x18003d91a  mov     edx, esi
0x18003d91c  mov     rcx, r14
0x18003d91f  call    IDA_ILClone
0x18003d924  mov     r15, rax
0x18003d927  test    rax, rax
0x18003d92a  jz      short loc_18003D96D
0x18003d92c  mov     rcx, [rsp+2D0h+var_278]
0x18003d931  mov     r8, [r13+50h]
0x18003d935  mov     [rsp+2D0h+var_290], rdi; struct COPY_THREAD_DATA *
0x18003d93a  mov     [rsp+2D0h+var_298], r12d; int
0x18003d93f  mov     [rsp+2D0h+var_2A0], r12; unsigned __int16 *
0x18003d944  mov     dword ptr [rsp+2D0h+var_2A8], r12d; int
0x18003d949  mov     [rsp+2D0h+var_2B0], rcx; struct IPortableDeviceContent *
0x18003d94e  mov     r9, [rsp+2D0h+var_280]; struct IPortableDevice *
0x18003d953  mov     r8, [r8+40h]; struct _ITEMIDLIST *
0x18003d957  mov     rdx, rax; struct _ITEMIDLIST *
0x18003d95a  mov     rcx, r13; this
0x18003d95d  call    ?_DoInsert@CContentDropTarget@@AEAAJPEFBU_ITEMIDLIST@@0PEAUIPortableDevice@@PEAUIPortableDeviceContent@@HPEBGHPEAVCOPY_THREAD_DATA@@@Z; CContentDropTarget::_DoInsert(_ITEMIDLIST const *,_ITEMIDLIST const *,IPortableDevice *,IPortableDeviceContent *,int,ushort const *,int,COPY_THREAD_DATA *)
0x18003d962  mov     ebx, eax
0x18003d964  mov     rcx, r15; pidl
0x18003d967  call    cs:__imp_ILFree
0x18003d96d  inc     esi
0x18003d96f  test    ebx, ebx
0x18003d971  jns     short loc_18003D915
0x18003d973  lea     rdx, [rsp+2D0h+var_270]
0x18003d978  call    ReleaseStgMediumHGLOBAL
0x18003d97d  lea     rdi, WPP_GLOBAL_Control
0x18003d984  mov     rcx, [r13+50h]
0x18003d988  mov     rax, [rcx]
0x18003d98b  mov     rdx, [rcx+40h]
0x18003d98f  mov     rax, [rax+0A0h]
0x18003d996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d99b  test    ebx, ebx
0x18003d99d  jns     short loc_18003D9CA
0x18003d99f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d9a6  cmp     rcx, rdi
0x18003d9a9  jz      short loc_18003D9CA
0x18003d9ab  test    byte ptr [rcx+1Ch], 2
0x18003d9af  jz      short loc_18003D9CA
0x18003d9b1  mov     edx, 1Ch
0x18003d9b6  mov     r9d, ebx
0x18003d9b9  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
  ... truncated ...
```
