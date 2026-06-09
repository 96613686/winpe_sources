# CContentFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST * *,ulong *)

- ea: `0x180004200`
- end: `0x180004a77`
- name: `?ParseDisplayName@CContentFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEFAU_ITEMIDLIST@@3@Z`
- size: `2167`
- prototype: `int(CContentFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003f20`
- `0x180004110`
- `0x180004200`
- `0x180004a80`
- `0x1800050d0`
- `0x18000ef50`
- `0x18001a5b0`
- `0x18001fd80`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039d74`
- `0x180039e80`
- `0x1800422b0`
- `0x180046d3c`
- `0x180046fc0`
- `0x180048158`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800049f0`
- `ole32!CoTaskMemFree` at `0x1800049fe`
- `ole32!CoTaskMemFree` at `0x1800049f0`
- `ole32!CoTaskMemFree` at `0x1800049fe`
- `ole32!CoTaskMemAlloc` at `0x1800042af`
- `ole32!CoTaskMemAlloc` at `0x1800042bb`
- `ole32!CoTaskMemAlloc` at `0x1800042af`
- `ole32!CoTaskMemAlloc` at `0x1800042bb`
- `SHELL32!__imp_ILFree` at `0x18000490a`
- `SHELL32!__imp_ILFree` at `0x1800049c8`
- `SHELL32!__imp_ILFree` at `0x1800049dd`
- `SHELL32!__imp_ILFree` at `0x18000490a`
- `SHELL32!__imp_ILFree` at `0x1800049c8`
- `SHELL32!__imp_ILFree` at `0x1800049dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CContentFolder::ParseDisplayName(
        CContentFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST **a6,
        unsigned int *a7)
{
  unsigned __int16 *v7; // rbx
  __int64 v10; // rdx
  struct IFileSystemBindData *v11; // rcx
  __int64 v12; // r8
  signed int ObjectIDFromDisplayName; // ebx
  _WORD *v14; // rsi
  _WORD *v15; // rax
  _WORD *v16; // r15
  __int64 v17; // rcx
  unsigned __int16 v18; // ax
  _WORD *v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  unsigned __int64 i; // rax
  _WORD *v24; // r10
  const unsigned __int16 *v25; // rdx
  const struct _GUID *v26; // r8
  _QWORD *v27; // rax
  __int64 v28; // rdx
  struct IPortableDevice *v30; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST v31; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+50h] [rbp-B0h] BYREF
  struct IFileSystemBindData *v33; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  LPITEMIDLIST pidl; // [rsp+68h] [rbp-98h] BYREF
  LPITEMIDLIST v36; // [rsp+70h] [rbp-90h] BYREF
  HWND v37; // [rsp+78h] [rbp-88h]
  struct _ITEMIDLIST **v38; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v39; // [rsp+88h] [rbp-78h]
  unsigned __int16 v40[264]; // [rsp+90h] [rbp-70h] BYREF

  v7 = a4;
  v39 = a4;
  v37 = a2;
  v10 = (__int64)a6;
  v38 = a6;
  v34 = (unsigned __int64)a7;
  v31 = 0;
  v36 = 0;
  pidl = 0;
  v11 = 0;
  v33 = 0;
  v12 = 92;
  if ( !a4 || !*a4 || !a6 )
  {
    ObjectIDFromDisplayName = -2147024809;
LABEL_120:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)ObjectIDFromDisplayName);
      v11 = v33;
    }
    goto LABEL_123;
  }
  *a6 = 0;
  if ( a5 )
    *a5 = 0;
  v14 = CoTaskMemAlloc(0x1040u);
  v15 = CoTaskMemAlloc(0x1040u);
  v16 = v15;
  if ( !v14 || !v15 )
  {
    ObjectIDFromDisplayName = -2147024882;
    goto LABEL_110;
  }
  memset_0(v14, 0, 0x1040u);
  memset_0(v16, 0, 0x1040u);
  v17 = 2147483646;
  a4 = v7;
  v10 = 2080;
  v12 = (__int64)v14;
  do
  {
    if ( !v17 )
      break;
    v18 = *a4;
    if ( !*a4 )
      break;
    ++a4;
    *(_WORD *)v12 = v18;
    v12 += 2;
    --v17;
    --v10;
  }
  while ( v10 );
  ObjectIDFromDisplayName = v10 == 0 ? 0x8007007A : 0;
  v19 = (_WORD *)(v12 - 2);
  if ( v10 )
    v19 = (_WORD *)v12;
  *v19 = 0;
  if ( !v10 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v21 = 79;
LABEL_52:
      WPP_SF_d(v20[2], v21, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)ObjectIDFromDisplayName);
    }
    goto LABEL_110;
  }
  v22 = -1;
  do
    ++v22;
  while ( v14[v22] );
  *v16 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v22 )
      goto LABEL_30;
    if ( v14[i] == 92 )
      break;
  }
  ObjectIDFromDisplayName = StringCchCopyW(v16, 0x820u, &v14[i]);
  if ( ObjectIDFromDisplayName < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v21 = 80;
      goto LABEL_52;
    }
    goto LABEL_110;
  }
  *v24 = 0;
LABEL_30:
  if ( *v14 == 123 && CBaseFolder::_GetObjectID((CContentFolder *)((char *)this - 16), v14, v40, 0x104u) >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_f4dfe53786183352449e3e96734e584d_Traceguids, v14);
    goto LABEL_35;
  }
  v40[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_f4dfe53786183352449e3e96734e584d_Traceguids, v14);
  ObjectIDFromDisplayName = CContentFolder::_GetObjectIDFromDisplayName(
                              (CContentFolder *)((char *)this - 16),
                              v14,
                              v40,
                              0x104u);
  v26 = 0;
  if ( ObjectIDFromDisplayName >= 0 )
  {
LABEL_35:
    if ( v33 )
    {
      ObjectIDFromDisplayName = CContentFolder::_CreateIDListForFileSysSimpleItem(
                                  (CContentFolder *)((char *)this - 16),
                                  v14,
                                  v33,
                                  &v31);
      if ( ObjectIDFromDisplayName < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v21 = 83;
          goto LABEL_52;
        }
        goto LABEL_110;
      }
    }
    else
    {
      v30 = 0;
      ObjectIDFromDisplayName = (*(__int64 (__fastcall **)(char *, _QWORD, struct IPortableDevice **))(*((_QWORD *)this - 2) + 136LL))(
                                  (char *)this - 16,
                                  *((_QWORD *)this + 6),
                                  &v30);
      if ( ObjectIDFromDisplayName < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            84,
            WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
            (unsigned int)ObjectIDFromDisplayName);
        goto LABEL_64;
      }
      if ( (unsigned int)BindCtx_ContainsObject(a3, L"WPDNSE SimpleItem") )
        *((_DWORD *)this + 32) = 1;
      ObjectIDFromDisplayName = CContentFolder::_CreateIDList(
                                  (CContentFolder *)((char *)this - 16),
                                  v30,
                                  v40,
                                  0,
                                  &v31,
                                  &v32);
      *((_DWORD *)this + 32) = 0;
      if ( ObjectIDFromDisplayName < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            85,
            WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
            (unsigned int)ObjectIDFromDisplayName);
        goto LABEL_64;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    }
LABEL_73:
    if ( *v16 && v16[1] )
    {
      v32 = 0;
      v30 = 0;
      ObjectIDFromDisplayName = (*(__int64 (__fastcall **)(CContentFolder *, LPITEMIDLIST, _QWORD, GUID *, struct IPortableDevice **))(*(_QWORD *)this + 40LL))(
                                  this,
                                  v31,
                                  0,
                                  &GUID_000214e6_0000_0000_c000_000000000046,
                                  &v30);
      if ( ObjectIDFromDisplayName < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            86,
            WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
            (unsigned int)ObjectIDFromDisplayName);
LABEL_64:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
        goto LABEL_110;
      }
      ObjectIDFromDisplayName = ((__int64 (__fastcall *)(struct IPortableDevice *, HWND, struct IBindCtx *, _WORD *, int *, LPITEMIDLIST *, unsigned __int64))v30->lpVtbl->Open)(
                                  v30,
                                  v37,
                                  a3,
                                  v16 + 1,
                                  &v32,
                                  &v36,
                                  v34);
      if ( ObjectIDFromDisplayName < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            87,
            WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
            (unsigned int)ObjectIDFromDisplayName);
        goto LABEL_64;
      }
      ObjectIDFromDisplayName = SHILCombine(v31, v36, &pidl);
      if ( ObjectIDFromDisplayName < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            88,
            WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
            (unsigned int)ObjectIDFromDisplayName);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
        goto LABEL_97;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
      goto LABEL_91;
    }
    ObjectIDFromDisplayName = SHILClone(v31, &pidl);
    if ( ObjectIDFromDisplayName >= 0 )
    {
      a4 = (unsigned __int16 *)v34;
      if ( !v34
        || (ObjectIDFromDisplayName = (*(__int64 (__fastcall **)(CContentFolder *, __int64, LPITEMIDLIST *))(*(_QWORD *)this + 72LL))(
                                        this,
                                        1,
                                        &v31),
            ObjectIDFromDisplayName >= 0) )
      {
LABEL_91:
        v10 = (__int64)v38;
        *v38 = pidl;
        if ( !a5 )
          goto LABEL_110;
        v34 = 0;
        ObjectIDFromDisplayName = StringCchLengthW(v39, 0x7FFFFFFFu, &v34);
        if ( ObjectIDFromDisplayName >= 0 )
        {
          *a5 = v34;
          goto LABEL_110;
        }
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_97;
        v28 = 91;
        goto LABEL_96;
      }
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v28 = 90;
        goto LABEL_96;
      }
    }
    else
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v28 = 89;
LABEL_96:
        WPP_SF_d(v27[2], v28, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)ObjectIDFromDisplayName);
      }
    }
LABEL_97:
    if ( pidl )
      ILFree(pidl);
    goto LABEL_110;
  }
  if ( *v16 )
  {
LABEL_55:
    if ( (int)BindCtx_RetrieveObject(a3, v25, v26, (void **)&v33) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (_DWORD)v14,
          ObjectIDFromDisplayName);
      goto LABEL_110;
    }
    goto LABEL_35;
  }
  v30 = 0;
  if ( a3
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, struct IPortableDevice **))a3->lpVtbl->GetObjectParam)(
         a3,
         L"WPDNSE Assume Virtual File",
         &v30) >= 0 )
  {
    ((void (__fastcall *)(struct IPortableDevice *))v30->lpVtbl->Release)(v30);
    goto LABEL_48;
  }
  if ( !(unsigned int)CContentFolder::_HasVirtualFile((CContentFolder *)((char *)this - 16), v14) )
  {
    ObjectIDFromDisplayName = CContentFolder::_GetObjectIDFromDisplayName(
                                (CContentFolder *)((char *)this - 16),
                                v14,
                                v40,
                                0x104u);
    if ( ObjectIDFromDisplayName >= 0 )
      goto LABEL_35;
    goto LABEL_55;
  }
LABEL_48:
  ObjectIDFromDisplayName = CContentFolder::_CreateIDListForVirtualFile(
                              (CContentFolder *)((char *)this - 16),
                              v14,
                              &v31);
  if ( ObjectIDFromDisplayName >= 0 )
    goto LABEL_73;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v21 = 82;
    goto LABEL_52;
  }
LABEL_110:
  if ( v31 )
  {
    ILFree(v31);
    v31 = 0;
  }
  if ( v36 )
  {
    ILFree(v36);
    v36 = 0;
  }
  if ( v14 )
    CoTaskMemFree(v14);
  if ( v16 )
    CoTaskMemFree(v16);
  v11 = v33;
  if ( ObjectIDFromDisplayName < 0 )
  {
    v12 = 92;
    goto LABEL_120;
  }
LABEL_123:
  if ( v11 )
    ((void (__fastcall *)(struct IFileSystemBindData *, __int64, __int64, unsigned __int16 *))v11->lpVtbl->Release)(
      v11,
      v10,
      v12,
      a4);
  return (unsigned int)ObjectIDFromDisplayName;
}

```

## disassembly

```asm
0x180004200  push    rbp
0x180004202  push    rbx
0x180004203  push    rsi
0x180004204  push    rdi
0x180004205  push    r12
0x180004207  push    r13
0x180004209  push    r14
0x18000420b  push    r15
0x18000420d  lea     rbp, [rsp-1B8h]
0x180004215  sub     rsp, 2B8h
0x18000421c  mov     rax, cs:__security_cookie
0x180004223  xor     rax, rsp
0x180004226  mov     [rbp+1F0h+var_50], rax
0x18000422d  mov     rbx, r9
0x180004230  mov     [rbp+1F0h+var_268], rbx
0x180004234  mov     r13, r8
0x180004237  mov     [rsp+2F0h+var_278], rdx
0x18000423c  mov     r14, rcx
0x18000423f  mov     r12, [rbp+1F0h+arg_20]
0x180004246  mov     rdx, [rbp+1F0h+arg_28]
0x18000424d  mov     [rbp+1F0h+var_270], rdx
0x180004251  mov     rax, [rbp+1F0h+arg_30]
0x180004258  mov     [rsp+2F0h+var_290], rax
0x18000425d  xor     edi, edi
0x18000425f  mov     [rsp+2F0h+var_2A8], rdi
0x180004264  mov     [rsp+2F0h+var_280], rdi
0x180004269  mov     [rsp+2F0h+pidl], rdi
0x18000426e  mov     ecx, edi
0x180004270  mov     [rsp+2F0h+var_298], rcx
0x180004275  lea     r8d, [rdi+5Ch]
0x180004279  test    r9, r9
0x18000427c  jnz     short loc_18000428F
0x18000427e  mov     ebx, 80070057h
0x180004283  lea     r14, WPP_GLOBAL_Control
0x18000428a  jmp     loc_180004A13
0x18000428f  cmp     di, [r9]
0x180004293  jz      short loc_18000427E
0x180004295  test    rdx, rdx
0x180004298  jz      short loc_18000427E
0x18000429a  mov     [rdx], rdi
0x18000429d  test    r12, r12
0x1800042a0  jz      short loc_1800042A6
0x1800042a2  mov     [r12], edi
0x1800042a6  mov     r15d, 1040h
0x1800042ac  mov     ecx, r15d; cb
0x1800042af  call    cs:__imp_CoTaskMemAlloc
0x1800042b5  mov     rsi, rax
0x1800042b8  mov     ecx, r15d; cb
0x1800042bb  call    cs:__imp_CoTaskMemAlloc
0x1800042c1  mov     r15, rax
0x1800042c4  test    rsi, rsi
0x1800042c7  jz      loc_1800049B2
0x1800042cd  test    rax, rax
0x1800042d0  jz      loc_1800049B2
0x1800042d6  xor     edx, edx; Val
0x1800042d8  mov     r8d, 1040h; Size
0x1800042de  mov     rcx, rsi; void *
0x1800042e1  call    memset_0
0x1800042e6  xor     edx, edx; Val
0x1800042e8  mov     r8d, 1040h; Size
0x1800042ee  mov     rcx, r15; void *
0x1800042f1  call    memset_0
0x1800042f6  mov     ecx, 7FFFFFFEh
0x1800042fb  mov     r9, rbx
0x1800042fe  mov     r11d, 820h
0x180004304  mov     edx, r11d
0x180004307  mov     r8, rsi
0x18000430a  test    rcx, rcx
0x18000430d  jz      short loc_18000432D
0x18000430f  movzx   eax, word ptr [r9]
0x180004313  test    ax, ax
0x180004316  jz      short loc_18000432D
0x180004318  add     r9, 2
0x18000431c  mov     [r8], ax
0x180004320  add     r8, 2
0x180004324  dec     rcx
0x180004327  sub     rdx, 1
0x18000432b  jnz     short loc_18000430A
0x18000432d  mov     rax, rdx
0x180004330  neg     rax
0x180004333  sbb     ebx, ebx
0x180004335  not     ebx
0x180004337  and     ebx, 8007007Ah
0x18000433d  lea     rcx, [r8-2]
0x180004341  test    rdx, rdx
0x180004344  cmovnz  rcx, r8
0x180004348  mov     [rcx], di
0x18000434b  jnz     short loc_180004378
0x18000434d  mov     rax, cs:WPP_GLOBAL_Control
0x180004354  lea     r14, WPP_GLOBAL_Control
0x18000435b  cmp     rax, r14
0x18000435e  jz      loc_1800049BE
0x180004364  test    byte ptr [rax+1Ch], 2
0x180004368  jz      loc_1800049BE
0x18000436e  mov     edx, 4Fh ; 'O'
0x180004373  jmp     loc_180004578
0x180004378  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000437c  inc     rcx
0x18000437f  cmp     [rsi+rcx*2], di
0x180004383  jnz     short loc_18000437C
0x180004385  mov     [r15], di
0x180004389  mov     rax, rdi
0x18000438c  mov     edx, 5Ch ; '\'
0x180004391  cmp     rax, rcx
0x180004394  jnb     short loc_1800043E8
0x180004396  lea     r10, [rsi+rax*2]
0x18000439a  cmp     dx, [r10]
0x18000439e  jz      short loc_1800043A5
0x1800043a0  inc     rax
0x1800043a3  jmp     short loc_180004391
0x1800043a5  mov     r8, r10; unsigned __int16 *
0x1800043a8  mov     rdx, r11; unsigned __int64
0x1800043ab  mov     rcx, r15; unsigned __int16 *
0x1800043ae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800043b3  mov     ebx, eax
0x1800043b5  test    eax, eax
0x1800043b7  jns     short loc_1800043E4
0x1800043b9  mov     rax, cs:WPP_GLOBAL_Control
0x1800043c0  lea     r14, WPP_GLOBAL_Control
0x1800043c7  cmp     rax, r14
0x1800043ca  jz      loc_1800049BE
0x1800043d0  test    byte ptr [rax+1Ch], 2
0x1800043d4  jz      loc_1800049BE
0x1800043da  mov     edx, 50h ; 'P'
0x1800043df  jmp     loc_180004578
0x1800043e4  mov     [r10], di
0x1800043e8  lea     rdi, [r14-10h]
0x1800043ec  mov     ebx, 104h
0x1800043f1  cmp     word ptr [rsi], 7Bh ; '{'
0x1800043f5  jnz     loc_180004499
0x1800043fb  mov     r9d, ebx; unsigned int
0x1800043fe  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x180004402  mov     rdx, rsi; unsigned __int16 *
0x180004405  mov     rcx, rdi; this
0x180004408  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x18000440d  test    eax, eax
0x18000440f  js      loc_180004499
0x180004415  mov     rcx, cs:WPP_GLOBAL_Control
0x18000441c  lea     rax, WPP_GLOBAL_Control
0x180004423  cmp     rcx, rax
0x180004426  jz      short loc_180004446
0x180004428  test    byte ptr [rcx+1Ch], 40h
0x18000442c  jz      short loc_180004446
0x18000442e  mov     edx, 36h ; '6'
0x180004433  mov     r9, rsi
0x180004436  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x18000443d  mov     rcx, [rcx+10h]
0x180004441  call    WPP_SF_S
0x180004446  mov     r8, [rsp+2F0h+var_298]; struct IFileSystemBindData *
0x18000444b  test    r8, r8
0x18000444e  jz      loc_18000460F
0x180004454  lea     r9, [rsp+2F0h+var_2A8]; struct _ITEMIDLIST **
0x180004459  mov     rdx, rsi; unsigned __int16 *
0x18000445c  mov     rcx, rdi; this
0x18000445f  call    ?_CreateIDListForFileSysSimpleItem@CContentFolder@@AEAAJPEBGPEAUIFileSystemBindData@@PEAPEFAU_ITEMIDLIST@@@Z; CContentFolder::_CreateIDListForFileSysSimpleItem(ushort const *,IFileSystemBindData *,_ITEMIDLIST * *)
0x180004464  mov     ebx, eax
0x180004466  xor     edi, edi
0x180004468  test    eax, eax
0x18000446a  jns     loc_18000471A
0x180004470  mov     rax, cs:WPP_GLOBAL_Control
0x180004477  lea     r14, WPP_GLOBAL_Control
0x18000447e  cmp     rax, r14
0x180004481  jz      loc_1800049BE
0x180004487  test    byte ptr [rax+1Ch], 2
0x18000448b  jz      loc_1800049BE
0x180004491  lea     edx, [rdi+53h]
0x180004494  jmp     loc_180004578
0x180004499  xor     eax, eax
0x18000449b  mov     [rbp+1F0h+var_260], ax
0x18000449f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044a6  lea     rax, WPP_GLOBAL_Control
0x1800044ad  cmp     rcx, rax
0x1800044b0  jz      short loc_1800044D0
0x1800044b2  test    byte ptr [rcx+1Ch], 40h
0x1800044b6  jz      short loc_1800044D0
0x1800044b8  mov     edx, 37h ; '7'
0x1800044bd  mov     r9, rsi
0x1800044c0  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x1800044c7  mov     rcx, [rcx+10h]
0x1800044cb  call    WPP_SF_S
0x1800044d0  mov     r9d, ebx; unsigned int
0x1800044d3  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x1800044d7  mov     rdx, rsi; psz1
0x1800044da  mov     rcx, rdi; this
0x1800044dd  call    ?_GetObjectIDFromDisplayName@CContentFolder@@QEAAJPEAG0I@Z; CContentFolder::_GetObjectIDFromDisplayName(ushort *,ushort *,uint)
0x1800044e2  mov     ebx, eax
0x1800044e4  xor     r8d, r8d
0x1800044e7  test    eax, eax
0x1800044e9  jns     loc_180004446
0x1800044ef  cmp     [r15], r8w
0x1800044f3  jnz     loc_1800045BE
0x1800044f9  mov     [rsp+2F0h+var_2B0], r8
0x1800044fe  test    r13, r13
0x180004501  jz      loc_180004590
0x180004507  mov     rax, [r13+0]
0x18000450b  lea     r8, [rsp+2F0h+var_2B0]
0x180004510  lea     rdx, aWpdnseAssumeVi; "WPDNSE Assume Virtual File"
0x180004517  mov     rcx, r13
0x18000451a  mov     rax, [rax+50h]
0x18000451e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004523  test    eax, eax
0x180004525  js      short loc_180004590
0x180004527  mov     rcx, [rsp+2F0h+var_2B0]
0x18000452c  mov     rax, [rcx]
0x18000452f  mov     rax, [rax+10h]
0x180004533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004538  lea     r8, [rsp+2F0h+var_2A8]; struct _ITEMIDLIST **
0x18000453d  mov     rdx, rsi; unsigned __int16 *
0x180004540  mov     rcx, rdi; this
0x180004543  call    ?_CreateIDListForVirtualFile@CContentFolder@@AEAAJPEBGPEAPEFAU_ITEMIDLIST@@@Z; CContentFolder::_CreateIDListForVirtualFile(ushort const *,_ITEMIDLIST * *)
0x180004548  mov     ebx, eax
0x18000454a  xor     edi, edi
0x18000454c  test    eax, eax
0x18000454e  jns     loc_18000471A
0x180004554  mov     rax, cs:WPP_GLOBAL_Control
0x18000455b  lea     r14, WPP_GLOBAL_Control
0x180004562  cmp     rax, r14
0x180004565  jz      loc_1800049BE
0x18000456b  test    byte ptr [rax+1Ch], 2
0x18000456f  jz      loc_1800049BE
0x180004575  lea     edx, [rdi+52h]
0x180004578  mov     r9d, ebx
0x18000457b  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180004582  mov     rcx, [rax+10h]
0x180004586  call    WPP_SF_d
0x18000458b  jmp     loc_1800049BE
0x180004590  mov     rdx, rsi; unsigned __int16 *
0x180004593  mov     rcx, rdi; this
0x180004596  call    ?_HasVirtualFile@CContentFolder@@AEAAHPEBG@Z; CContentFolder::_HasVirtualFile(ushort const *)
0x18000459b  test    eax, eax
0x18000459d  jnz     short loc_180004538
0x18000459f  mov     r9d, 104h; unsigned int
0x1800045a5  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x1800045a9  mov     rdx, rsi; psz1
0x1800045ac  mov     rcx, rdi; this
0x1800045af  call    ?_GetObjectIDFromDisplayName@CContentFolder@@QEAAJPEAG0I@Z; CContentFolder::_GetObjectIDFromDisplayName(ushort *,ushort *,uint)
0x1800045b4  mov     ebx, eax
0x1800045b6  test    eax, eax
0x1800045b8  jns     loc_180004446
0x1800045be  lea     r9, [rsp+2F0h+var_298]; void **
0x1800045c3  mov     rcx, r13; struct IBindCtx *
0x1800045c6  call    ?BindCtx_RetrieveObject@@YAJPEAUIBindCtx@@PEBGAEBU_GUID@@PEAPEAX@Z; BindCtx_RetrieveObject(IBindCtx *,ushort const *,_GUID const &,void * *)
0x1800045cb  test    eax, eax
0x1800045cd  jns     loc_180004446
0x1800045d3  mov     rax, cs:WPP_GLOBAL_Control
0x1800045da  lea     r14, WPP_GLOBAL_Control
0x1800045e1  cmp     rax, r14
0x1800045e4  jz      short loc_180004608
0x1800045e6  test    byte ptr [rax+1Ch], 2
0x1800045ea  jz      short loc_180004608
0x1800045ec  mov     edx, 51h ; 'Q'
0x1800045f1  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x1800045f5  mov     r9, rsi
0x1800045f8  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800045ff  mov     rcx, [rax+10h]
0x180004603  call    WPP_SF_Sd
0x180004608  xor     edi, edi
0x18000460a  jmp     loc_1800049BE
0x18000460f  mov     [rsp+2F0h+var_2B0], 0
0x180004618  mov     rax, [rdi]
0x18000461b  lea     r8, [rsp+2F0h+var_2B0]
0x180004620  mov     rdx, [r14+30h]
0x180004624  mov     rcx, rdi
0x180004627  mov     rax, [rax+88h]
0x18000462e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004633  mov     ebx, eax
0x180004635  test    eax, eax
0x180004637  jns     short loc_18000467C
0x180004639  mov     rcx, cs:WPP_GLOBAL_Control
0x180004640  lea     rax, WPP_GLOBAL_Control
0x180004647  cmp     rcx, rax
0x18000464a  jz      short loc_18000466B
0x18000464c  test    byte ptr [rcx+1Ch], 2
0x180004650  jz      short loc_18000466B
0x180004652  mov     edx, 54h ; 'T'
0x180004657  mov     r9d, ebx
0x18000465a  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180004661  mov     rcx, [rcx+10h]
0x180004665  call    WPP_SF_d
0x18000466a  nop
0x18000466b  lea     rcx, [rsp+2F0h+var_2B0]
0x180004670  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004675  xor     edi, edi
0x180004677  jmp     loc_1800049B7
0x18000467c  lea     rdx, aWpdnseSimpleit; "WPDNSE SimpleItem"
0x180004683  mov     rcx, r13
0x180004686  call    BindCtx_ContainsObject
0x18000468b  test    eax, eax
0x18000468d  jz      short loc_18000469A
0x18000468f  mov     dword ptr [r14+80h], 1
0x18000469a  lea     rax, [rsp+2F0h+var_2A0]
0x18000469f  mov     [rsp+2F0h+var_2C8], rax; int *
0x1800046a4  lea     rax, [rsp+2F0h+var_2A8]
0x1800046a9  mov     [rsp+2F0h+var_2D0], rax; struct _ITEMIDLIST **
0x1800046ae  xor     r9d, r9d; int
0x1800046b1  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x1800046b5  mov     rdx, [rsp+2F0h+var_2B0]; struct IPortableDevice *
0x1800046ba  mov     rcx, rdi; this
0x1800046bd  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x1800046c2  mov     ebx, eax
  ... truncated ...
```
