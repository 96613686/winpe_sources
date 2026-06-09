# CDeviceFolder::BindToObject(_ITEMIDLIST const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x1800064e0`
- end: `0x180006cbf`
- name: `?BindToObject@CDeviceFolder@@UEAAJPEFBU_ITEMIDLIST@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `2015`
- prototype: `__int64 __fastcall(CDeviceFolder *__hidden this, const struct _ITEMIDLIST *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800064e0`
- `0x180007860`
- `0x18000c180`
- `0x180028ea8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18003912c`
- `0x180039e80`
- `0x180058784`
- `0x1800755a8`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180006658`
- `KERNEL32!HeapAlloc` at `0x180006658`
- `KERNEL32!GetProcessHeap` at `0x180006644`
- `KERNEL32!GetProcessHeap` at `0x180006644`
- `KERNEL32!EnterCriticalSection` at `0x1800066d6`
- `KERNEL32!EnterCriticalSection` at `0x1800066d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800066ea`
- `KERNEL32!LeaveCriticalSection` at `0x1800066ea`
- `KERNEL32!GetCurrentThreadId` at `0x180006b2f`
- `KERNEL32!GetCurrentThreadId` at `0x180006b2f`
- `ole32!CoTaskMemAlloc` at `0x1800065fc`
- `ole32!CoTaskMemAlloc` at `0x1800065fc`
- `SHELL32!__imp_ILGetSize` at `0x1800065d7`
- `SHELL32!__imp_ILGetSize` at `0x1800065d7`
- `SHELL32!__imp_ILFree` at `0x1800068e5`
- `SHELL32!__imp_ILFree` at `0x1800068e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeviceFolder::BindToObject(
        CDeviceFolder *this,
        struct _ITEMIDLIST *a2,
        struct IBindCtx *a3,
        struct _GUID *a4,
        void **a5)
{
  const struct DEVICEITEM *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rdx
  unsigned __int16 *v10; // r8
  __int64 v11; // rsi
  __int64 v12; // r10
  unsigned __int16 *v13; // r9
  unsigned __int16 v14; // ax
  unsigned __int16 *v15; // rcx
  _WORD *v16; // r12
  CDeviceFolder *v17; // r13
  const ITEMIDLIST *v18; // rbp
  UINT v19; // ebx
  unsigned int v20; // r14d
  SIZE_T v21; // rcx
  UINT v22; // r15d
  ITEMIDLIST *v23; // rax
  size_t v24; // r8
  ITEMIDLIST *v25; // r15
  size_t v26; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v28; // rax
  _QWORD *v29; // r14
  __int64 v30; // rcx
  unsigned __int16 *v31; // rcx
  unsigned __int16 *v32; // rdx
  unsigned __int16 v33; // ax
  unsigned __int16 *v34; // rcx
  int v35; // eax
  int v36; // ebx
  GUID *v37; // rsi
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  unsigned int v41; // eax
  int v42; // edx
  int v44; // eax
  int v45; // esi
  PVOID *v46; // rcx
  PVOID *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r9
  struct IPortableDevice **v50; // rdi
  int IsDelegateFolder; // ebx
  DWORD CurrentThreadId; // eax
  int v53; // eax
  int v54; // esi
  ITEMIDLIST *v55; // [rsp+30h] [rbp-318h] BYREF
  struct IPropertySetStorage **v56; // [rsp+38h] [rbp-310h]
  struct IBindCtx *v57; // [rsp+40h] [rbp-308h]
  GUID *rguid; // [rsp+48h] [rbp-300h]
  struct DEVICEITEM *v59; // [rsp+50h] [rbp-2F8h]
  void *Src; // [rsp+58h] [rbp-2F0h]
  OLECHAR sz[64]; // [rsp+60h] [rbp-2E8h] BYREF
  unsigned __int16 v62[264]; // [rsp+E0h] [rbp-268h] BYREF

  rguid = a4;
  v57 = a3;
  Src = a2;
  v56 = (struct IPropertySetStorage **)a5;
  if ( !a2 )
    return 2147942487LL;
  if ( !a5 )
    return 2147500035LL;
  *a5 = 0;
  v7 = CDeviceFolder::_IsValid(this, a2);
  v59 = v7;
  if ( !v7 )
    return 2147500037LL;
  if ( (*((_BYTE *)v7 + 10) & 2) == 0 )
    return 2147500034LL;
  v55 = 0;
  v8 = 2147483646;
  v9 = 2147483646;
  v10 = (unsigned __int16 *)((char *)v7
                           + 2 * *(unsigned int *)((char *)v7 + 26)
                           + 2 * (unsigned __int64)*(unsigned int *)((char *)v7 + 30)
                           + 38);
  v11 = 260;
  v12 = 260;
  v13 = v62;
  do
  {
    if ( !v9 )
      break;
    v14 = *v10;
    if ( !*v10 )
      break;
    ++v10;
    *v13++ = v14;
    --v9;
    --v12;
  }
  while ( v12 );
  v15 = v13 - 1;
  if ( v12 )
    v15 = v13;
  *v15 = 0;
  v16 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb);
  v17 = (CDeviceFolder *)((char *)this - 16);
  v18 = (const ITEMIDLIST *)*((_QWORD *)v17 + 8);
  v19 = ILGetSize(v18);
  v20 = (_DWORD)v16 - (_DWORD)a2;
  v21 = (_DWORD)v16 - (_DWORD)a2 + v19;
  if ( v19 > (unsigned int)v21 )
  {
    v36 = -2147418113;
    goto LABEL_56;
  }
  if ( !(_DWORD)v21 )
  {
    v36 = -2147024809;
    goto LABEL_56;
  }
  v22 = (_DWORD)v16 - (_DWORD)a2 + v19;
  v23 = (ITEMIDLIST *)CoTaskMemAlloc(v21);
  v55 = v23;
  if ( !v23 )
  {
    v36 = -2147024882;
LABEL_56:
    v29 = 0;
    v47 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
          (unsigned int)v36);
        v47 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v47 != &WPP_GLOBAL_Control && (*((_BYTE *)v47 + 28) & 2) != 0 )
        WPP_SF_d(v47[2], 15, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)v36);
    }
    v25 = v55;
    if ( !v55 )
      goto LABEL_47;
    goto LABEL_46;
  }
  v24 = v22;
  v25 = v23;
  memset_0(v23, 0, v24);
  v26 = v19 - 2;
  memcpy_0(v25, v18, v26);
  memcpy_0((char *)v25 + v26, Src, v20);
  ProcessHeap = GetProcessHeap();
  v28 = HeapAlloc(ProcessHeap, 8u, 0x288u);
  v29 = v28;
  Src = v28;
  if ( v28 )
  {
    *v28 = &CBaseFolder::`vftable'{for `IDelegateFolder'};
    v28[1] = &CBaseFolder::`vftable'{for `IPersistFolder2'};
    v28[2] = &CBaseFolder::`vftable'{for `IShellFolder2'};
    v28[3] = &CBaseFolder::`vftable'{for `IExplorerPaneVisibility'};
    v28[4] = &CBaseFolder::`vftable'{for `IItemNameLimits'};
    *((_DWORD *)v28 + 10) = 1;
    *(GUID *)((char *)v28 + 44) = CLSID_StorageFolder;
    v28[8] = 0;
    v28[9] = v17;
    *((_DWORD *)v28 + 20) = 0;
    v28[11] = 0;
    v28[12] = 0;
    EnterCriticalSection(&g_csDllRef);
    _InterlockedIncrement(&g_cRefThisDll);
    LeaveCriticalSection(&g_csDllRef);
    v30 = v29[9];
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
    *v29 = &CStorageFolder::`vftable'{for `IDelegateFolder'};
    v29[1] = &CStorageFolder::`vftable'{for `IPersistFolder2'};
    v29[2] = &CStorageFolder::`vftable'{for `IShellFolder2'};
    v29[3] = &CStorageFolder::`vftable'{for `IExplorerPaneVisibility'};
    v29[4] = &CStorageFolder::`vftable'{for `IItemNameLimits'};
    v29[13] = &CStorageFolder::`vftable'{for `IShellFolderViewCB'};
    v29[14] = &CStorageFolder::`vftable'{for `IFolderViewSettings'};
    *((_DWORD *)v29 + 160) = -1;
    *((_DWORD *)v29 + 161) = 0;
    v31 = v62;
    v32 = (unsigned __int16 *)(v29 + 15);
    do
    {
      if ( !v8 )
        break;
      v33 = *v31;
      if ( !*v31 )
        break;
      ++v31;
      *v32++ = v33;
      --v8;
      --v11;
    }
    while ( v11 );
    v34 = v32 - 1;
    if ( v11 )
      v34 = v32;
    *v34 = 0;
    *((_DWORD *)v29 + 20) = 6;
    v29[11] = &c_aStorageColumns;
  }
  else
  {
    v29 = 0;
  }
  if ( !v29 )
  {
    v36 = -2147024882;
    goto LABEL_46;
  }
  v35 = (*(__int64 (__fastcall **)(_QWORD *, ITEMIDLIST *))(v29[1] + 32LL))(v29 + 1, v25);
  v36 = v35;
  if ( v35 < 0 )
  {
    v46 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_46;
    v48 = 16;
LABEL_74:
    v49 = (unsigned int)v35;
LABEL_75:
    WPP_SF_d(v46[2], v48, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v49);
    goto LABEL_46;
  }
  if ( !v16 || !*v16 )
  {
    v55 = 0;
    if ( v57
      && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, ITEMIDLIST **))v57->lpVtbl->GetObjectParam)(
           v57,
           L"WPDNSE Fast Enum",
           &v55) >= 0 )
    {
      (*(void (__fastcall **)(ITEMIDLIST *))(*(_QWORD *)&v55->mkid.cb + 16LL))(v55);
      *((_DWORD *)v29 + 161) = 1;
    }
    v37 = rguid;
    v38 = *(_QWORD *)&rguid->Data1 - *(_QWORD *)&IID_IPortableDevice.Data1;
    if ( *(_QWORD *)&rguid->Data1 == *(_QWORD *)&IID_IPortableDevice.Data1 )
      v38 = *(_QWORD *)rguid->Data4 - *(_QWORD *)IID_IPortableDevice.Data4;
    if ( v38 )
    {
      v39 = *(_QWORD *)&rguid->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
      if ( *(_QWORD *)&rguid->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
        v39 = *(_QWORD *)rguid->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
      if ( v39 )
      {
        v40 = *(_QWORD *)&rguid->Data1 - *(_QWORD *)&IID_IPropertySetStorage.Data1;
        if ( *(_QWORD *)&rguid->Data1 == *(_QWORD *)&IID_IPropertySetStorage.Data1 )
          v40 = *(_QWORD *)rguid->Data4 - *(_QWORD *)IID_IPropertySetStorage.Data4;
        if ( v40 )
        {
          v36 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IPropertySetStorage **))*v29)(v29, rguid, v56);
          if ( v36 >= 0 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_46;
          v41 = (unsigned int)CGuidToString::CGuidToString(sz, v37);
          v42 = 20;
          goto LABEL_42;
        }
        v35 = CDeviceFolder::_BindToPropertySetStorage(v17, v59, v56);
        v36 = v35;
        if ( v35 >= 0 )
          goto LABEL_46;
        v46 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_46;
        v48 = 19;
        goto LABEL_74;
      }
      v44 = (*(__int64 (__fastcall **)(CDeviceFolder *, struct DEVICEITEM *, struct IPropertySetStorage **, __int64))(*(_QWORD *)v17 + 32LL))(
              v17,
              v59,
              v56,
              1);
      v45 = v44;
      if ( v44 < 0 )
      {
        v46 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              121,
              WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
              (unsigned int)v44);
            v46 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v46 != &WPP_GLOBAL_Control && (*((_BYTE *)v46 + 28) & 2) != 0 )
          {
            WPP_SF_d(v46[2], 122, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)v45);
            v36 = v45;
            v46 = (PVOID *)WPP_GLOBAL_Control;
LABEL_94:
            if ( v46 == &WPP_GLOBAL_Control || (*((_BYTE *)v46 + 28) & 2) == 0 )
              goto LABEL_46;
            v48 = 18;
            v49 = (unsigned int)v45;
            goto LABEL_75;
          }
        }
      }
      else
      {
        v46 = (PVOID *)WPP_GLOBAL_Control;
      }
      v36 = v45;
      if ( v45 >= 0 )
        goto LABEL_46;
      goto LABEL_94;
    }
    v50 = (struct IPortableDevice **)v56;
    *v56 = 0;
    IsDelegateFolder = CBaseFolder::_IsDelegateFolder(v17);
    CurrentThreadId = GetCurrentThreadId();
    v53 = CDeviceCache::s_BindToPortableDevice(v62, CurrentThreadId, 0, 0, IsDelegateFolder, v50);
    v54 = v53;
    if ( v53 >= 0 )
    {
      v46 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v46 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            WPP_f4dfe53786183352449e3e96734e584d_Traceguids,
            (unsigned int)v53);
          v46 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v46 != &WPP_GLOBAL_Control && (*((_BYTE *)v46 + 28) & 2) != 0 )
        {
          WPP_SF_d(v46[2], 30, WPP_f4dfe53786183352449e3e96734e584d_Traceguids, (unsigned int)v54);
          v36 = v54;
          v46 = (PVOID *)WPP_GLOBAL_Control;
LABEL_68:
          if ( v46 == &WPP_GLOBAL_Control || (*((_BYTE *)v46 + 28) & 2) == 0 )
            goto LABEL_46;
          v48 = 17;
          v49 = (unsigned int)v54;
          goto LABEL_75;
        }
      }
    }
    v36 = v54;
    if ( v54 >= 0 )
      goto LABEL_46;
    goto LABEL_68;
  }
  v36 = (*(__int64 (__fastcall **)(_QWORD *, _WORD *, struct IBindCtx *, GUID *, struct IPropertySetStorage **))(v29[2] + 40LL))(
          v29 + 2,
          v16,
          v57,
          rguid,
          v56);
  if ( v36 >= 0 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_46;
  v41 = (unsigned int)CGuidToString::CGuidToString(sz, rguid);
  v42 = 21;
LABEL_42:
  WPP_SF_Sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v42,
    (unsigned int)WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
    v41,
    v36);
LABEL_46:
  ILFree(v25);
LABEL_47:
  if ( v29 )
    (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x1800064e0  push    rbx
0x1800064e2  push    rbp
0x1800064e3  push    rsi
0x1800064e4  push    rdi
0x1800064e5  push    r12
0x1800064e7  push    r13
0x1800064e9  push    r14
0x1800064eb  push    r15
0x1800064ed  sub     rsp, 308h
0x1800064f4  mov     rax, cs:__security_cookie
0x1800064fb  xor     rax, rsp
0x1800064fe  mov     [rsp+348h+var_58], rax
0x180006506  mov     [rsp+348h+rguid], r9
0x18000650b  mov     [rsp+348h+var_308], r8
0x180006510  mov     r15, rdx
0x180006513  mov     [rsp+348h+Src], rdx
0x180006518  mov     r13, rcx
0x18000651b  mov     rax, [rsp+348h+arg_20]
0x180006523  mov     [rsp+348h+var_310], rax
0x180006528  test    rdx, rdx
0x18000652b  jz      loc_180006A6C
0x180006531  test    rax, rax
0x180006534  jz      loc_180006A3B
0x18000653a  mov     qword ptr [rax], 0
0x180006541  call    ?_IsValid@CDeviceFolder@@AEAAPEFBUDEVICEITEM@@PEFBU_ITEMIDLIST@@@Z; CDeviceFolder::_IsValid(_ITEMIDLIST const *)
0x180006546  mov     r8, rax
0x180006549  mov     [rsp+348h+var_2F8], rax
0x18000654e  test    rax, rax
0x180006551  jz      loc_180006A76
0x180006557  test    byte ptr [rax+0Ah], 2
0x18000655b  jz      loc_1800068C8
0x180006561  xor     eax, eax
0x180006563  mov     [rsp+348h+var_318], rax
0x180006568  mov     edi, 7FFFFFFEh
0x18000656d  mov     edx, edi
0x18000656f  mov     ecx, [r8+1Eh]
0x180006573  mov     eax, [r8+1Ah]
0x180006577  add     rcx, rax
0x18000657a  lea     r8, [r8+rcx*2]
0x18000657e  add     r8, 26h ; '&'
0x180006582  mov     esi, 104h
0x180006587  mov     r10d, esi
0x18000658a  lea     r9, [rsp+348h+var_268]
0x180006592  test    rdx, rdx
0x180006595  jz      short loc_1800065B5
0x180006597  movzx   eax, word ptr [r8]
0x18000659b  test    ax, ax
0x18000659e  jz      short loc_1800065B5
0x1800065a0  add     r8, 2
0x1800065a4  mov     [r9], ax
0x1800065a8  add     r9, 2
0x1800065ac  dec     rdx
0x1800065af  sub     r10, 1
0x1800065b3  jnz     short loc_180006592
0x1800065b5  lea     rcx, [r9-2]
0x1800065b9  test    r10, r10
0x1800065bc  cmovnz  rcx, r9
0x1800065c0  xor     eax, eax
0x1800065c2  mov     [rcx], ax
0x1800065c5  movzx   r12d, word ptr [r15]
0x1800065c9  add     r12, r15
0x1800065cc  add     r13, 0FFFFFFFFFFFFFFF0h
0x1800065d0  mov     rbp, [r13+40h]
0x1800065d4  mov     rcx, rbp; pidl
0x1800065d7  call    cs:__imp_ILGetSize
0x1800065dd  mov     ebx, eax
0x1800065df  mov     r14d, r12d
0x1800065e2  sub     r14d, r15d
0x1800065e5  lea     ecx, [r14+rax]; cb
0x1800065e9  cmp     eax, ecx
0x1800065eb  ja      loc_180006973
0x1800065f1  test    ecx, ecx
0x1800065f3  jz      loc_1800069C0
0x1800065f9  mov     r15d, ecx
0x1800065fc  call    cs:__imp_CoTaskMemAlloc
0x180006602  mov     [rsp+348h+var_318], rax
0x180006607  test    rax, rax
0x18000660a  jz      loc_180006A80
0x180006610  mov     r8d, r15d; Size
0x180006613  xor     edx, edx; Val
0x180006615  mov     r15, rax
0x180006618  mov     rcx, rax; void *
0x18000661b  call    memset_0
0x180006620  lea     eax, [rbx-2]
0x180006623  mov     ebx, eax
0x180006625  mov     r8d, eax; Size
0x180006628  mov     rdx, rbp; Src
0x18000662b  mov     rcx, r15; void *
0x18000662e  call    memcpy_0
0x180006633  mov     r8d, r14d; Size
0x180006636  lea     rcx, [r15+rbx]; void *
0x18000663a  mov     rdx, [rsp+348h+Src]; Src
0x18000663f  call    memcpy_0
0x180006644  call    cs:__imp_GetProcessHeap
0x18000664a  mov     rcx, rax; hHeap
0x18000664d  mov     edx, 8; dwFlags
0x180006652  mov     r8d, 288h; dwBytes
0x180006658  call    cs:__imp_HeapAlloc
0x18000665e  mov     r14, rax
0x180006661  mov     [rsp+348h+Src], rax
0x180006666  xor     ebp, ebp
0x180006668  test    rax, rax
0x18000666b  jz      loc_1800069C7
0x180006671  lea     rax, ??_7CBaseFolder@@6BIDelegateFolder@@@; const CBaseFolder::`vftable'{for `IDelegateFolder'}
0x180006678  mov     [r14], rax
0x18000667b  lea     rax, ??_7CBaseFolder@@6BIPersistFolder2@@@; const CBaseFolder::`vftable'{for `IPersistFolder2'}
0x180006682  mov     [r14+8], rax
0x180006686  lea     rax, ??_7CBaseFolder@@6BIShellFolder2@@@; const CBaseFolder::`vftable'{for `IShellFolder2'}
0x18000668d  mov     [r14+10h], rax
0x180006691  lea     rax, ??_7CBaseFolder@@6BIExplorerPaneVisibility@@@; const CBaseFolder::`vftable'{for `IExplorerPaneVisibility'}
0x180006698  mov     [r14+18h], rax
0x18000669c  lea     rax, ??_7CBaseFolder@@6BIItemNameLimits@@@; const CBaseFolder::`vftable'{for `IItemNameLimits'}
0x1800066a3  mov     [r14+20h], rax
0x1800066a7  mov     dword ptr [r14+28h], 1
0x1800066af  movups  xmm0, xmmword ptr cs:CLSID_StorageFolder.Data1
0x1800066b6  movups  xmmword ptr [r14+2Ch], xmm0
0x1800066bb  mov     [r14+40h], rbp
0x1800066bf  mov     [r14+48h], r13
0x1800066c3  mov     [r14+50h], ebp
0x1800066c7  mov     [r14+58h], rbp
0x1800066cb  mov     [r14+60h], rbp
0x1800066cf  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800066d6  call    cs:__imp_EnterCriticalSection
0x1800066dc  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x1800066e3  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800066ea  call    cs:__imp_LeaveCriticalSection
0x1800066f0  mov     rcx, [r14+48h]
0x1800066f4  test    rcx, rcx
0x1800066f7  jz      short loc_180006705
0x1800066f9  mov     rax, [rcx]
0x1800066fc  mov     rax, [rax+8]
0x180006700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006705  lea     rax, ??_7CStorageFolder@@6BIDelegateFolder@@@; const CStorageFolder::`vftable'{for `IDelegateFolder'}
0x18000670c  mov     [r14], rax
0x18000670f  lea     rax, ??_7CStorageFolder@@6BIPersistFolder2@@@; const CStorageFolder::`vftable'{for `IPersistFolder2'}
0x180006716  mov     [r14+8], rax
0x18000671a  lea     rax, ??_7CStorageFolder@@6BIShellFolder2@@@; const CStorageFolder::`vftable'{for `IShellFolder2'}
0x180006721  mov     [r14+10h], rax
0x180006725  lea     rax, ??_7CStorageFolder@@6BIExplorerPaneVisibility@@@; const CStorageFolder::`vftable'{for `IExplorerPaneVisibility'}
0x18000672c  mov     [r14+18h], rax
0x180006730  lea     rax, ??_7CStorageFolder@@6BIItemNameLimits@@@; const CStorageFolder::`vftable'{for `IItemNameLimits'}
0x180006737  mov     [r14+20h], rax
0x18000673b  lea     rax, ??_7CStorageFolder@@6BIShellFolderViewCB@@@; const CStorageFolder::`vftable'{for `IShellFolderViewCB'}
0x180006742  mov     [r14+68h], rax
0x180006746  lea     rax, ??_7CStorageFolder@@6BIFolderViewSettings@@@; const CStorageFolder::`vftable'{for `IFolderViewSettings'}
0x18000674d  mov     [r14+70h], rax
0x180006751  mov     dword ptr [r14+280h], 0FFFFFFFFh
0x18000675c  mov     [r14+284h], ebp
0x180006763  lea     rcx, [rsp+348h+var_268]
0x18000676b  lea     rdx, [r14+78h]
0x18000676f  nop
0x180006770  test    rdi, rdi
0x180006773  jz      short loc_180006791
0x180006775  movzx   eax, word ptr [rcx]
0x180006778  test    ax, ax
0x18000677b  jz      short loc_180006791
0x18000677d  add     rcx, 2
0x180006781  mov     [rdx], ax
0x180006784  add     rdx, 2
0x180006788  dec     rdi
0x18000678b  sub     rsi, 1
0x18000678f  jnz     short loc_180006770
0x180006791  lea     rcx, [rdx-2]
0x180006795  test    rsi, rsi
0x180006798  cmovnz  rcx, rdx
0x18000679c  mov     [rcx], bp
0x18000679f  mov     dword ptr [r14+50h], 6
0x1800067a7  lea     rax, ?c_aStorageColumns@@3PAUWPDSHEXT_COLUMN_INFO@@A; WPDSHEXT_COLUMN_INFO near * c_aStorageColumns
0x1800067ae  mov     [r14+58h], rax
0x1800067b2  test    r14, r14
0x1800067b5  jz      loc_180006925
0x1800067bb  lea     rcx, [r14+8]
0x1800067bf  mov     rax, [rcx]
0x1800067c2  mov     rdx, r15
0x1800067c5  mov     rax, [rax+20h]
0x1800067c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ce  mov     ebx, eax
0x1800067d0  test    eax, eax
0x1800067d2  js      loc_180006A13
0x1800067d8  test    r12, r12
0x1800067db  jz      short loc_1800067E9
0x1800067dd  cmp     word ptr [r12], 0
0x1800067e3  jnz     loc_180006AB1
0x1800067e9  mov     [rsp+348h+var_318], rbp
0x1800067ee  mov     r10, [rsp+348h+var_308]
0x1800067f3  test    r10, r10
0x1800067f6  jnz     loc_1800069CF
0x1800067fc  mov     rsi, [rsp+348h+rguid]
0x180006801  mov     rax, [rsi]
0x180006804  sub     rax, qword ptr cs:IID_IPortableDevice.Data1
0x18000680b  jnz     short loc_180006818
0x18000680d  mov     rax, [rsi+8]
0x180006811  sub     rax, qword ptr cs:IID_IPortableDevice.Data4
0x180006818  test    rax, rax
0x18000681b  jz      loc_180006B1D
0x180006821  mov     rax, [rsi]
0x180006824  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x18000682b  jnz     short loc_180006838
0x18000682d  mov     rax, [rsi+8]
0x180006831  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x180006838  test    rax, rax
0x18000683b  jz      loc_18000692C
0x180006841  mov     rax, [rsi]
0x180006844  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data1
0x18000684b  jnz     short loc_180006858
0x18000684d  mov     rax, [rsi+8]
0x180006851  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data4
0x180006858  mov     r8, [rsp+348h+var_310]; struct IPropertySetStorage **
0x18000685d  test    rax, rax
0x180006860  jz      loc_180006C5B
0x180006866  mov     rax, [r14]
0x180006869  mov     rdx, rsi
0x18000686c  mov     rcx, r14
0x18000686f  mov     rax, [rax]
0x180006872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006877  mov     ebx, eax
0x180006879  test    eax, eax
0x18000687b  jns     short loc_1800068E2
0x18000687d  lea     rdi, WPP_GLOBAL_Control
0x180006884  mov     rax, cs:WPP_GLOBAL_Control
0x18000688b  cmp     rax, rdi
0x18000688e  jz      short loc_1800068E2
0x180006890  test    byte ptr [rax+1Ch], 2
0x180006894  jz      short loc_1800068E2
0x180006896  mov     rdx, rsi; rguid
0x180006899  lea     rcx, [rsp+348h+sz]; lpsz
0x18000689e  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x1800068a3  mov     edx, 14h
0x1800068a8  mov     [rsp+348h+var_328], ebx
0x1800068ac  mov     r9, rax
0x1800068af  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x1800068b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068bd  mov     rcx, [rcx+10h]
0x1800068c1  call    WPP_SF_Sd
0x1800068c6  jmp     short loc_1800068E2
0x1800068c8  mov     eax, 80004002h
0x1800068cd  jmp     short loc_180006901
0x1800068cf  cmp     rcx, rdi
0x1800068d2  jnz     loc_180006C98
0x1800068d8  mov     r15, [rsp+348h+var_318]
0x1800068dd  test    r15, r15
0x1800068e0  jz      short loc_1800068EB
0x1800068e2  mov     rcx, r15; pidl
0x1800068e5  call    cs:__imp_ILFree
0x1800068eb  test    r14, r14
0x1800068ee  jz      short loc_1800068FF
0x1800068f0  mov     rax, [r14]
0x1800068f3  mov     rcx, r14
0x1800068f6  mov     rax, [rax+10h]
0x1800068fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ff  mov     eax, ebx
0x180006901  mov     rcx, [rsp+348h+var_58]
0x180006909  xor     rcx, rsp; StackCookie
0x18000690c  call    __security_check_cookie
0x180006911  add     rsp, 308h
0x180006918  pop     r15
0x18000691a  pop     r14
0x18000691c  pop     r13
0x18000691e  pop     r12
0x180006920  pop     rdi
0x180006921  pop     rsi
0x180006922  pop     rbp
0x180006923  pop     rbx
0x180006924  retn
0x180006925  mov     ebx, 8007000Eh
0x18000692a  jmp     short loc_1800068E2
0x18000692c  mov     rax, [r13+0]
0x180006930  mov     r9d, 1
0x180006936  mov     r8, [rsp+348h+var_310]
0x18000693b  mov     rdx, [rsp+348h+var_2F8]
0x180006940  mov     rcx, r13
0x180006943  mov     rax, [rax+20h]
0x180006947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000694c  mov     esi, eax
0x18000694e  lea     rdi, WPP_GLOBAL_Control
0x180006955  test    eax, eax
0x180006957  js      loc_180006BDA
0x18000695d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006964  mov     ebx, esi
0x180006966  test    esi, esi
0x180006968  jns     loc_1800068E2
0x18000696e  jmp     loc_180006C43
0x180006973  mov     ebx, 8000FFFFh
0x180006978  xor     r14d, r14d
0x18000697b  lea     rdi, WPP_GLOBAL_Control
0x180006982  mov     rcx, cs:WPP_GLOBAL_Control
0x180006989  cmp     rcx, rdi
0x18000698c  jz      loc_1800068D8
0x180006992  test    byte ptr [rcx+1Ch], 2
0x180006996  jz      loc_1800068CF
0x18000699c  mov     edx, 0Fh
0x1800069a1  mov     r9d, ebx
0x1800069a4  lea     r8, WPP_d7637b305d8b3afba9326780f352c02a_Traceguids
0x1800069ab  mov     rcx, [rcx+10h]
0x1800069af  call    WPP_SF_d
0x1800069b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069bb  jmp     loc_1800068CF
0x1800069c0  mov     ebx, 80070057h
0x1800069c5  jmp     short loc_180006978
0x1800069c7  mov     r14, rbp
  ... truncated ...
```
