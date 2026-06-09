# CStorageFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST * *,ulong *)

- ea: `0x1800660d0`
- end: `0x1800666c1`
- name: `?ParseDisplayName@CStorageFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEFAU_ITEMIDLIST@@3@Z`
- size: `1521`
- prototype: `int(CStorageFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003f20`
- `0x180004110`
- `0x180017834`
- `0x18001a5b0`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002e790`
- `0x18002eda4`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039e80`
- `0x1800660d0`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18006664f`
- `ole32!CoTaskMemFree` at `0x18006665d`
- `ole32!CoTaskMemFree` at `0x18006664f`
- `ole32!CoTaskMemFree` at `0x18006665d`
- `ole32!CoTaskMemAlloc` at `0x180066178`
- `ole32!CoTaskMemAlloc` at `0x180066183`
- `ole32!CoTaskMemAlloc` at `0x180066178`
- `ole32!CoTaskMemAlloc` at `0x180066183`
- `SHELL32!__imp_ILFree` at `0x18006655f`
- `SHELL32!__imp_ILFree` at `0x18006661f`
- `SHELL32!__imp_ILFree` at `0x180066638`
- `SHELL32!__imp_ILFree` at `0x18006655f`
- `SHELL32!__imp_ILFree` at `0x18006661f`
- `SHELL32!__imp_ILFree` at `0x180066638`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStorageFolder::ParseDisplayName(
        CStorageFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST **a6,
        unsigned int *a7)
{
  int v9; // ebx
  void *v10; // r15
  _WORD *v11; // rax
  _WORD *v12; // rsi
  int v13; // eax
  unsigned int v14; // r9d
  unsigned __int64 v15; // r11
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  unsigned __int64 i; // rax
  _WORD *v20; // r10
  CStorageFolder *v21; // rdi
  unsigned int v22; // r9d
  int ObjectIDFromDisplayName; // eax
  int v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r9
  int v32; // eax
  LPITEMIDLIST v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST pidl; // [rsp+58h] [rbp-A8h] BYREF
  LPITEMIDLIST v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+6Ch] [rbp-94h] BYREF
  CStorageFolder *v41; // [rsp+70h] [rbp-90h]
  struct IPortableDevice *v42; // [rsp+78h] [rbp-88h] BYREF
  struct IBindCtx *v43; // [rsp+80h] [rbp-80h]
  HWND v44; // [rsp+88h] [rbp-78h]
  unsigned __int16 v45[264]; // [rsp+90h] [rbp-70h] BYREF

  v43 = a3;
  v44 = a2;
  v41 = this;
  v36 = (unsigned __int64)a7;
  v39 = 0;
  v34 = 0;
  v38 = 0;
  pidl = 0;
  v42 = 0;
  if ( !a4 || !*a4 || !a6 )
  {
    v9 = -2147024809;
LABEL_85:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
        (unsigned int)v9);
    goto LABEL_88;
  }
  *a6 = 0;
  if ( a5 )
    *a5 = 0;
  v10 = CoTaskMemAlloc(0x1040u);
  v11 = CoTaskMemAlloc(0x1040u);
  v12 = v11;
  if ( !v10 || !v11 )
  {
    v9 = -2147024882;
    goto LABEL_76;
  }
  memset_0(v10, 0, 0x1040u);
  memset_0(v12, 0, 0x1040u);
  v13 = StringCchCopyW((unsigned __int16 *)v10, 0x820u, a4);
  v9 = v13;
  if ( v13 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v17 = 58;
LABEL_33:
      WPP_SF_d(v16[2], v17, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v13);
    }
    goto LABEL_76;
  }
  v18 = -1;
  do
    ++v18;
  while ( *((_WORD *)v10 + v18) );
  *v12 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v18 )
      goto LABEL_24;
    if ( *((_WORD *)v10 + i) == 92 )
      break;
  }
  v13 = StringCchCopyW(v12, v15, (const unsigned __int16 *)v10 + i);
  v9 = v13;
  if ( v13 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v17 = 59;
      goto LABEL_33;
    }
    goto LABEL_76;
  }
  *v20 = 0;
LABEL_24:
  v21 = (CStorageFolder *)((char *)this - 16);
  if ( !(unsigned int)CBaseFolder::_IsKnownPersistentUniqueID(v21, (const unsigned __int16 *)v10, v45, v14) )
  {
    ObjectIDFromDisplayName = CStorageFolder::_GetObjectIDFromDisplayName(v21, (unsigned __int16 *)v10, v45, v22);
    v9 = ObjectIDFromDisplayName;
    if ( ObjectIDFromDisplayName < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          (unsigned int)WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
          (_DWORD)a4,
          ObjectIDFromDisplayName);
      goto LABEL_76;
    }
  }
  v13 = (*(__int64 (__fastcall **)(CStorageFolder *, _QWORD, struct IPortableDevice **))(*(_QWORD *)v21 + 136LL))(
          v21,
          *((_QWORD *)v41 + 6),
          &v42);
  v9 = v13;
  if ( v13 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v17 = 61;
      goto LABEL_33;
    }
    goto LABEL_76;
  }
  v13 = CStorageFolder::_CreateIDList(v21, v42, v45, &v34, &v39);
  v9 = v13;
  if ( v13 >= 0 )
  {
    if ( *v12 && v12[1] )
    {
      v40 = 0;
      v35 = 0;
      v24 = (*(__int64 (__fastcall **)(CStorageFolder *, LPITEMIDLIST, _QWORD, GUID *, __int64 *))(*(_QWORD *)v41 + 40LL))(
              v41,
              v34,
              0,
              &GUID_000214e6_0000_0000_c000_000000000046,
              &v35);
      v9 = v24;
      if ( v24 < 0 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_45;
        v26 = 63;
LABEL_44:
        WPP_SF_d(v25[2], v26, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v24);
LABEL_45:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        goto LABEL_76;
      }
      v24 = (*(__int64 (__fastcall **)(__int64, HWND, struct IBindCtx *, _WORD *, int *, LPITEMIDLIST *, unsigned __int64))(*(_QWORD *)v35 + 24LL))(
              v35,
              v44,
              v43,
              v12 + 1,
              &v40,
              &v38,
              v36);
      v9 = v24;
      if ( v24 < 0 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_45;
        v26 = 64;
        goto LABEL_44;
      }
      v27 = SHILCombine(v34, v38, &pidl);
      v9 = v27;
      if ( v27 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v27);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        goto LABEL_63;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      goto LABEL_56;
    }
    v32 = SHILClone(v34, &pidl);
    v9 = v32;
    if ( v32 >= 0 )
    {
      if ( !v36
        || (v28 = (*(__int64 (__fastcall **)(CStorageFolder *, __int64, LPITEMIDLIST *))(*(_QWORD *)v41 + 72LL))(
                    v41,
                    1,
                    &v34),
            v9 = v28,
            v28 >= 0) )
      {
LABEL_56:
        *a6 = pidl;
        if ( !a5 )
          goto LABEL_76;
        v36 = 0;
        v28 = StringCchLengthW(a4, 0x7FFFFFFFu, &v36);
        v9 = v28;
        if ( v28 >= 0 )
        {
          *a5 = v36;
          goto LABEL_76;
        }
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_63;
        v30 = 68;
        goto LABEL_61;
      }
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v30 = 67;
LABEL_61:
        v31 = (unsigned int)v28;
LABEL_62:
        WPP_SF_d(v29[2], v30, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v31);
      }
    }
    else
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v30 = 66;
        v31 = (unsigned int)v32;
        goto LABEL_62;
      }
    }
LABEL_63:
    if ( pidl )
      ILFree(pidl);
    goto LABEL_76;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v17 = 62;
    goto LABEL_33;
  }
LABEL_76:
  if ( v34 )
  {
    ILFree(v34);
    v34 = 0;
  }
  if ( v38 )
  {
    ILFree(v38);
    v38 = 0;
  }
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v9 < 0 )
    goto LABEL_85;
LABEL_88:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800660d0  push    rbp
0x1800660d2  push    rbx
0x1800660d3  push    rsi
0x1800660d4  push    rdi
0x1800660d5  push    r12
0x1800660d7  push    r13
0x1800660d9  push    r14
0x1800660db  push    r15
0x1800660dd  lea     rbp, [rsp-1B8h]
0x1800660e5  sub     rsp, 2B8h
0x1800660ec  mov     rax, cs:__security_cookie
0x1800660f3  xor     rax, rsp
0x1800660f6  mov     [rbp+1F0h+var_50], rax
0x1800660fd  mov     r12, r9
0x180066100  mov     [rbp+1F0h+var_270], r8
0x180066104  mov     [rbp+1F0h+var_268], rdx
0x180066108  mov     rdi, rcx
0x18006610b  mov     [rsp+2F0h+var_280], rcx
0x180066110  mov     r14, [rbp+1F0h+arg_20]
0x180066117  mov     r13, [rbp+1F0h+arg_28]
0x18006611e  mov     rax, [rbp+1F0h+arg_30]
0x180066125  mov     [rsp+2F0h+var_2A0], rax
0x18006612a  xor     ebx, ebx
0x18006612c  mov     [rsp+2F0h+var_288], ebx
0x180066130  mov     [rsp+2F0h+var_2B0], rbx
0x180066135  mov     [rsp+2F0h+var_290], rbx
0x18006613a  mov     [rsp+2F0h+pidl], rbx
0x18006613f  mov     [rsp+2F0h+var_278], rbx
0x180066144  test    r9, r9
0x180066147  jnz     short loc_18006615A
0x180066149  mov     ebx, 80070057h
0x18006614e  lea     rdi, WPP_GLOBAL_Control
0x180066155  jmp     loc_180066667
0x18006615a  cmp     bx, [r9]
0x18006615e  jz      short loc_180066149
0x180066160  test    r13, r13
0x180066163  jz      short loc_180066149
0x180066165  mov     [r13+0], rbx
0x180066169  test    r14, r14
0x18006616c  jz      short loc_180066171
0x18006616e  mov     [r14], ebx
0x180066171  mov     esi, 1040h
0x180066176  mov     ecx, esi; cb
0x180066178  call    cs:__imp_CoTaskMemAlloc
0x18006617e  mov     r15, rax
0x180066181  mov     ecx, esi; cb
0x180066183  call    cs:__imp_CoTaskMemAlloc
0x180066189  mov     rsi, rax
0x18006618c  test    r15, r15
0x18006618f  jz      loc_180066609
0x180066195  test    rax, rax
0x180066198  jz      loc_180066609
0x18006619e  mov     ebx, 1040h
0x1800661a3  mov     r8d, ebx; Size
0x1800661a6  xor     edx, edx; Val
0x1800661a8  mov     rcx, r15; void *
0x1800661ab  call    memset_0
0x1800661b0  mov     r8d, ebx; Size
0x1800661b3  xor     edx, edx; Val
0x1800661b5  mov     rcx, rsi; void *
0x1800661b8  call    memset_0
0x1800661bd  mov     r8, r12; unsigned __int16 *
0x1800661c0  mov     r11d, 820h
0x1800661c6  mov     edx, r11d; unsigned __int64
0x1800661c9  mov     rcx, r15; unsigned __int16 *
0x1800661cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800661d1  mov     ebx, eax
0x1800661d3  test    eax, eax
0x1800661d5  jns     short loc_180066202
0x1800661d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800661de  lea     rdi, WPP_GLOBAL_Control
0x1800661e5  cmp     rcx, rdi
0x1800661e8  jz      loc_180066615
0x1800661ee  test    byte ptr [rcx+1Ch], 2
0x1800661f2  jz      loc_180066615
0x1800661f8  mov     edx, 3Ah ; ':'
0x1800661fd  jmp     loc_180066330
0x180066202  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180066206  xor     ebx, ebx
0x180066208  inc     rcx
0x18006620b  cmp     [r15+rcx*2], bx
0x180066210  jnz     short loc_180066208
0x180066212  mov     [rsi], bx
0x180066215  mov     rax, rbx
0x180066218  cmp     rax, rcx
0x18006621b  jnb     short loc_180066276
0x18006621d  lea     r10, [r15+rax*2]
0x180066221  mov     edx, 5Ch ; '\'
0x180066226  cmp     dx, [r10]
0x18006622a  jz      short loc_180066231
0x18006622c  inc     rax
0x18006622f  jmp     short loc_180066218
0x180066231  mov     r8, r10; unsigned __int16 *
0x180066234  mov     rdx, r11; unsigned __int64
0x180066237  mov     rcx, rsi; unsigned __int16 *
0x18006623a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006623f  mov     ebx, eax
0x180066241  test    eax, eax
0x180066243  jns     short loc_180066270
0x180066245  mov     rcx, cs:WPP_GLOBAL_Control
0x18006624c  lea     rdi, WPP_GLOBAL_Control
0x180066253  cmp     rcx, rdi
0x180066256  jz      loc_180066615
0x18006625c  test    byte ptr [rcx+1Ch], 2
0x180066260  jz      loc_180066615
0x180066266  mov     edx, 3Bh ; ';'
0x18006626b  jmp     loc_180066330
0x180066270  xor     ebx, ebx
0x180066272  mov     [r10], bx
0x180066276  add     rdi, 0FFFFFFFFFFFFFFF0h
0x18006627a  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x18006627e  mov     rdx, r15; unsigned __int16 *
0x180066281  mov     rcx, rdi; this
0x180066284  call    ?_IsKnownPersistentUniqueID@CBaseFolder@@IEAAHPEBGPEAGI@Z; CBaseFolder::_IsKnownPersistentUniqueID(ushort const *,ushort *,uint)
0x180066289  test    eax, eax
0x18006628b  jnz     short loc_1800662E4
0x18006628d  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x180066291  mov     rdx, r15; unsigned __int16 *
0x180066294  mov     rcx, rdi; this
0x180066297  call    ?_GetObjectIDFromDisplayName@CStorageFolder@@AEAAJPEAG0I@Z; CStorageFolder::_GetObjectIDFromDisplayName(ushort *,ushort *,uint)
0x18006629c  mov     ebx, eax
0x18006629e  test    eax, eax
0x1800662a0  jns     short loc_1800662E4
0x1800662a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800662a9  lea     rdi, WPP_GLOBAL_Control
0x1800662b0  cmp     rcx, rdi
0x1800662b3  jz      loc_180066615
0x1800662b9  test    byte ptr [rcx+1Ch], 2
0x1800662bd  jz      loc_180066615
0x1800662c3  mov     edx, 3Ch ; '<'
0x1800662c8  mov     dword ptr [rsp+2F0h+var_2D0], eax
0x1800662cc  mov     r9, r12
0x1800662cf  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x1800662d6  mov     rcx, [rcx+10h]
0x1800662da  call    WPP_SF_Sd
0x1800662df  jmp     loc_180066615
0x1800662e4  mov     rax, [rdi]
0x1800662e7  lea     r8, [rsp+2F0h+var_278]
0x1800662ec  mov     rdx, [rsp+2F0h+var_280]
0x1800662f1  mov     rdx, [rdx+30h]
0x1800662f5  mov     rcx, rdi
0x1800662f8  mov     rax, [rax+88h]
0x1800662ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066304  mov     ebx, eax
0x180066306  test    eax, eax
0x180066308  jns     short loc_180066348
0x18006630a  mov     rcx, cs:WPP_GLOBAL_Control
0x180066311  lea     rdi, WPP_GLOBAL_Control
0x180066318  cmp     rcx, rdi
0x18006631b  jz      loc_180066615
0x180066321  test    byte ptr [rcx+1Ch], 2
0x180066325  jz      loc_180066615
0x18006632b  mov     edx, 3Dh ; '='
0x180066330  mov     r9d, eax
0x180066333  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18006633a  mov     rcx, [rcx+10h]
0x18006633e  call    WPP_SF_d
0x180066343  jmp     loc_180066615
0x180066348  lea     rax, [rsp+2F0h+var_288]
0x18006634d  mov     [rsp+2F0h+var_2D0], rax; int *
0x180066352  lea     r9, [rsp+2F0h+var_2B0]; struct _ITEMIDLIST **
0x180066357  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x18006635b  mov     rdx, [rsp+2F0h+var_278]; struct IPortableDevice *
0x180066360  mov     rcx, rdi; this
0x180066363  call    ?_CreateIDList@CStorageFolder@@AEAAJPEAUIPortableDevice@@PEBGPEAPEFAU_ITEMIDLIST@@PEAH@Z; CStorageFolder::_CreateIDList(IPortableDevice *,ushort const *,_ITEMIDLIST * *,int *)
0x180066368  mov     ebx, eax
0x18006636a  xor     ecx, ecx
0x18006636c  test    eax, eax
0x18006636e  jns     short loc_180066398
0x180066370  mov     rcx, cs:WPP_GLOBAL_Control
0x180066377  lea     rdi, WPP_GLOBAL_Control
0x18006637e  cmp     rcx, rdi
0x180066381  jz      loc_180066615
0x180066387  test    byte ptr [rcx+1Ch], 2
0x18006638b  jz      loc_180066615
0x180066391  mov     edx, 3Eh ; '>'
0x180066396  jmp     short loc_180066330
0x180066398  cmp     [rsi], cx
0x18006639b  jz      loc_18006656A
0x1800663a1  cmp     [rsi+2], cx
0x1800663a5  jz      loc_18006656A
0x1800663ab  mov     [rsp+2F0h+var_284], ecx
0x1800663af  mov     [rsp+2F0h+var_2A8], rcx
0x1800663b4  mov     rcx, [rsp+2F0h+var_280]
0x1800663b9  mov     rax, [rcx]
0x1800663bc  lea     rdx, [rsp+2F0h+var_2A8]
0x1800663c1  mov     [rsp+2F0h+var_2D0], rdx
0x1800663c6  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x1800663cd  xor     r8d, r8d
0x1800663d0  mov     rdx, [rsp+2F0h+var_2B0]
0x1800663d5  mov     rax, [rax+28h]
0x1800663d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663de  mov     ebx, eax
0x1800663e0  test    eax, eax
0x1800663e2  jns     short loc_180066425
0x1800663e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800663eb  lea     rdi, WPP_GLOBAL_Control
0x1800663f2  cmp     rcx, rdi
0x1800663f5  jz      short loc_180066416
0x1800663f7  test    byte ptr [rcx+1Ch], 2
0x1800663fb  jz      short loc_180066416
0x1800663fd  mov     edx, 3Fh ; '?'
0x180066402  mov     r9d, eax
0x180066405  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18006640c  mov     rcx, [rcx+10h]
0x180066410  call    WPP_SF_d
0x180066415  nop
0x180066416  lea     rcx, [rsp+2F0h+var_2A8]
0x18006641b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180066420  jmp     loc_180066615
0x180066425  mov     rcx, [rsp+2F0h+var_2A8]
0x18006642a  mov     rax, [rcx]
0x18006642d  mov     r9, [rsp+2F0h+var_2A0]
0x180066432  mov     [rsp+2F0h+var_2C0], r9
0x180066437  lea     r9, [rsp+2F0h+var_290]
0x18006643c  mov     [rsp+2F0h+var_2C8], r9
0x180066441  lea     r9, [rsp+2F0h+var_284]
0x180066446  mov     [rsp+2F0h+var_2D0], r9
0x18006644b  lea     r9, [rsi+2]
0x18006644f  mov     r8, [rbp+1F0h+var_270]
0x180066453  mov     rdx, [rbp+1F0h+var_268]
0x180066457  mov     rax, [rax+18h]
0x18006645b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066460  mov     ebx, eax
0x180066462  test    eax, eax
0x180066464  jns     short loc_180066489
0x180066466  mov     rcx, cs:WPP_GLOBAL_Control
0x18006646d  lea     rdi, WPP_GLOBAL_Control
0x180066474  cmp     rcx, rdi
0x180066477  jz      short loc_180066416
0x180066479  test    byte ptr [rcx+1Ch], 2
0x18006647d  jz      short loc_180066416
0x18006647f  mov     edx, 40h ; '@'
0x180066484  jmp     loc_180066402
0x180066489  lea     r8, [rsp+2F0h+pidl]
0x18006648e  mov     rdx, [rsp+2F0h+var_290]
0x180066493  mov     rcx, [rsp+2F0h+var_2B0]
0x180066498  call    SHILCombine
0x18006649d  mov     ebx, eax
0x18006649f  test    eax, eax
0x1800664a1  jns     short loc_1800664E1
0x1800664a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800664aa  lea     rdi, WPP_GLOBAL_Control
0x1800664b1  cmp     rcx, rdi
0x1800664b4  jz      short loc_1800664D5
0x1800664b6  test    byte ptr [rcx+1Ch], 2
0x1800664ba  jz      short loc_1800664D5
0x1800664bc  mov     edx, 41h ; 'A'
0x1800664c1  mov     r9d, eax
0x1800664c4  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x1800664cb  mov     rcx, [rcx+10h]
0x1800664cf  call    WPP_SF_d
0x1800664d4  nop
0x1800664d5  lea     rcx, [rsp+2F0h+var_2A8]
0x1800664da  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800664df  jmp     short loc_180066551
0x1800664e1  lea     rcx, [rsp+2F0h+var_2A8]
0x1800664e6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800664eb  mov     rax, [rsp+2F0h+pidl]
0x1800664f0  mov     [r13+0], rax
0x1800664f4  xor     ecx, ecx
0x1800664f6  test    r14, r14
0x1800664f9  jz      loc_18006660E
0x1800664ff  mov     [rsp+2F0h+var_2A0], rcx
0x180066504  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x180066509  mov     edx, 7FFFFFFFh; unsigned __int64
0x18006650e  mov     rcx, r12; unsigned __int16 *
0x180066511  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180066516  mov     ebx, eax
0x180066518  test    eax, eax
0x18006651a  jns     loc_180066600
0x180066520  mov     rcx, cs:WPP_GLOBAL_Control
0x180066527  lea     rdi, WPP_GLOBAL_Control
0x18006652e  cmp     rcx, rdi
0x180066531  jz      short loc_180066551
0x180066533  test    byte ptr [rcx+1Ch], 2
0x180066537  jz      short loc_180066551
0x180066539  mov     edx, 44h ; 'D'
0x18006653e  mov     r9d, eax
0x180066541  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180066548  mov     rcx, [rcx+10h]
0x18006654c  call    WPP_SF_d
0x180066551  mov     rcx, [rsp+2F0h+pidl]; pidl
0x180066556  test    rcx, rcx
0x180066559  jz      loc_180066615
0x18006655f  call    cs:__imp_ILFree
0x180066565  jmp     loc_180066615
0x18006656a  lea     rdx, [rsp+2F0h+pidl]
0x18006656f  mov     rcx, [rsp+2F0h+var_2B0]
0x180066574  call    SHILClone
0x180066579  mov     ebx, eax
0x18006657b  test    eax, eax
0x18006657d  jns     short loc_1800665A2
0x18006657f  mov     rcx, cs:WPP_GLOBAL_Control
0x180066586  lea     rdi, WPP_GLOBAL_Control
0x18006658d  cmp     rcx, rdi
0x180066590  jz      short loc_180066551
0x180066592  test    byte ptr [rcx+1Ch], 2
0x180066596  jz      short loc_180066551
0x180066598  mov     edx, 42h ; 'B'
  ... truncated ...
```
