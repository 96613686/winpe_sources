# CStorageFolder::BindToObject(_ITEMIDLIST const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180009af0`
- end: `0x18000a292`
- name: `?BindToObject@CStorageFolder@@UEAAJPEFBU_ITEMIDLIST@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `1954`
- prototype: `int(CStorageFolder *__hidden this, const struct _ITEMIDLIST *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009890`
- `0x180009af0`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18003912c`
- `0x180039e80`
- `0x180066c34`
- `0x1800755a8`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180009bfc`
- `KERNEL32!HeapAlloc` at `0x180009bfc`
- `KERNEL32!GetProcessHeap` at `0x180009be8`
- `KERNEL32!GetProcessHeap` at `0x180009be8`
- `KERNEL32!EnterCriticalSection` at `0x180009c8f`
- `KERNEL32!EnterCriticalSection` at `0x180009c8f`
- `KERNEL32!LeaveCriticalSection` at `0x180009ca3`
- `KERNEL32!LeaveCriticalSection` at `0x180009ca3`
- `ole32!CoTaskMemAlloc` at `0x180009ba3`
- `ole32!CoTaskMemAlloc` at `0x180009ba3`
- `SHELL32!__imp_ILGetSize` at `0x180009b7a`
- `SHELL32!__imp_ILGetSize` at `0x180009b7a`
- `SHELL32!__imp_ILFree` at `0x180009e60`
- `SHELL32!__imp_ILFree` at `0x180009e60`

## string_xrefs

- `0x180009da8`: `prop:System.Size;System.DateModified;System.DateCreated`
- `0x180009d98`: `prop:System.Size;System.DateModified;System.DateCreated`
- `0x18000a071`: `prop:System.Size;System.DateModified;System.DateCreated`
- `0x18000a0d8`: `prop:System.Size;System.DateModified;System.DateCreated`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStorageFolder::BindToObject(
        void **this,
        const struct _ITEMIDLIST *a2,
        struct IBindCtx *a3,
        struct _GUID *a4,
        struct IPropertySetStorage **a5)
{
  const struct STORAGEITEM *v8; // rax
  const struct STORAGEITEM *v9; // r13
  _WORD *v10; // rbp
  UINT v11; // ebx
  SIZE_T v12; // rcx
  ITEMIDLIST *v13; // rax
  ITEMIDLIST *v14; // rdi
  size_t v15; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  void **v19; // r15
  int v20; // esi
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  const wchar_t *v25; // rax
  __int64 *v26; // rcx
  int v27; // esi
  unsigned int v28; // eax
  int v29; // edx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // eax
  int v35; // ebp
  PVOID *v36; // rcx
  __int64 v37; // rdx
  PVOID *v38; // rcx
  __int64 v39; // r9
  void **v40; // [rsp+30h] [rbp-F8h] BYREF
  struct IBindCtx *v41; // [rsp+38h] [rbp-F0h]
  void *Src; // [rsp+40h] [rbp-E8h]
  size_t Size; // [rsp+48h] [rbp-E0h]
  OLECHAR sz[64]; // [rsp+50h] [rbp-D8h] BYREF

  v41 = a3;
  v40 = this;
  if ( !a2 )
    return 2147942487LL;
  if ( !a5 )
    return 2147500035LL;
  *a5 = 0;
  v8 = CStorageFolder::_IsValid((CStorageFolder *)this, a2);
  v9 = v8;
  if ( !v8 )
    return 2147500037LL;
  if ( (*((_BYTE *)v8 + 10) & 2) == 0 )
    return 2147500034LL;
  v10 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb);
  Src = this[6];
  v11 = ILGetSize((LPCITEMIDLIST)Src);
  v12 = (_DWORD)v10 - (_DWORD)a2 + v11;
  if ( v11 > (unsigned int)v12 )
  {
    v27 = -2147418113;
    goto LABEL_54;
  }
  if ( !(_DWORD)v12 )
  {
    v27 = -2147024809;
    goto LABEL_54;
  }
  Size = (unsigned int)v12;
  v13 = (ITEMIDLIST *)CoTaskMemAlloc(v12);
  v14 = v13;
  if ( !v13 )
  {
    v27 = -2147024882;
LABEL_54:
    v18 = 0;
    v38 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
          (unsigned int)v27);
        v38 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 2) != 0 )
        WPP_SF_d(v38[2], 15, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v27);
    }
    goto LABEL_28;
  }
  memset_0(v13, 0, Size);
  v15 = v11 - 2;
  memcpy_0(v14, Src, v15);
  memcpy_0((char *)v14 + v15, a2, (unsigned int)((_DWORD)v10 - (_DWORD)a2));
  ProcessHeap = GetProcessHeap();
  v17 = HeapAlloc(ProcessHeap, 8u, 0xB0u);
  v18 = v17;
  Src = v17;
  v19 = v40;
  if ( v17 )
  {
    v20 = *((_DWORD *)v40 + 157);
    LODWORD(v40) = *(_DWORD *)((char *)v9 + 10);
    *v17 = &CBaseFolder::`vftable'{for `IDelegateFolder'};
    v17[1] = &CBaseFolder::`vftable'{for `IPersistFolder2'};
    v17[2] = &CBaseFolder::`vftable'{for `IShellFolder2'};
    v17[3] = &CBaseFolder::`vftable'{for `IExplorerPaneVisibility'};
    v17[4] = &CBaseFolder::`vftable'{for `IItemNameLimits'};
    *((_DWORD *)v17 + 10) = 1;
    *(GUID *)((char *)v17 + 44) = CLSID_ContentFolder;
    v17[8] = 0;
    v17[9] = v19 - 2;
    *((_DWORD *)v17 + 20) = 0;
    v17[11] = 0;
    v17[12] = 0;
    EnterCriticalSection(&g_csDllRef);
    _InterlockedIncrement(&g_cRefThisDll);
    LeaveCriticalSection(&g_csDllRef);
    v21 = v18[9];
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    *v18 = &CContentFolder::`vftable'{for `IDelegateFolder'};
    v18[1] = &CContentFolder::`vftable'{for `IPersistFolder2'};
    v18[2] = &CContentFolder::`vftable'{for `IShellFolder2'};
    v18[3] = &CContentFolder::`vftable'{for `IExplorerPaneVisibility'};
    v18[4] = &CContentFolder::`vftable'{for `IItemNameLimits'};
    v18[13] = &CContentFolder::`vftable'{for `IShellFolderViewCB'};
    v18[14] = &CContentFolder::`vftable'{for `IFolderViewSettings'};
    v18[15] = &CContentFolder::`vftable'{for `IShellIconOverlay'};
    v18[16] = &CContentFolder::`vftable'{for `IStorage'};
    v18[17] = &CContentFolder::`vftable'{for `IUpdateIDList'};
    *((_DWORD *)v18 + 36) = 0;
    *((_DWORD *)v18 + 37) = v20;
    *((_DWORD *)v18 + 38) = 0;
    *((_DWORD *)v18 + 39) = (_DWORD)v40;
    v18[20] = 0;
    v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(*(_QWORD *)v18[9] + 152LL))(v18[9], v18[8], v18 + 19);
    if ( v22 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_f4dfe53786183352449e3e96734e584d_Traceguids,
        (unsigned int)v22);
    v23 = *((_DWORD *)v18 + 38);
    *((_DWORD *)v18 + 20) = 16;
    if ( v23 == 3 )
    {
      v25 = L"prop:System.Size;System.DateModified;System.DateCreated";
      v26 = qword_180079330;
    }
    else
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        if ( v24 == 1 )
        {
          v25 = L"prop:System.Size;System.DateModified;System.DateCreated";
          v26 = qword_1800797B0;
        }
        else
        {
          v25 = L"prop:System.Size;System.DateModified;System.DateCreated";
          v26 = qword_180079630;
        }
      }
      else
      {
        v25 = L"prop:System.Size;System.DateModified;System.DateCreated";
        v26 = qword_1800794B0;
      }
    }
    v18[11] = v26;
    v18[21] = v25;
  }
  else
  {
    v18 = 0;
  }
  if ( !v18 )
  {
    v27 = -2147024882;
    goto LABEL_27;
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD *, ITEMIDLIST *))(v18[1] + 32LL))(v18 + 1, v14);
  if ( v27 < 0 )
  {
    v36 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_27;
    v37 = 16;
LABEL_75:
    v39 = (unsigned int)v27;
LABEL_76:
    WPP_SF_d(v36[2], v37, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v39);
    goto LABEL_27;
  }
  if ( v10 && *v10 )
  {
    v27 = (*(__int64 (__fastcall **)(_QWORD *, _WORD *, struct IBindCtx *, struct _GUID *, struct IPropertySetStorage **))(v18[2] + 40LL))(
            v18 + 2,
            v10,
            v41,
            a4,
            a5);
    if ( v27 >= 0 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_27;
    v28 = (unsigned int)CGuidToString::CGuidToString(sz, a4);
    v29 = 21;
    goto LABEL_45;
  }
  v40 = 0;
  if ( v41
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, void ***))v41->lpVtbl->GetObjectParam)(
         v41,
         L"WPDNSE Fast Enum",
         &v40) >= 0 )
  {
    (*((void (__fastcall **)(void **))*v40 + 2))(v40);
    *((_DWORD *)v18 + 37) = 1;
  }
  v31 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPortableDevice.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPortableDevice.Data1 )
    v31 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPortableDevice.Data4;
  if ( !v31 )
  {
    v27 = (*((__int64 (__fastcall **)(void **, void *, struct IPropertySetStorage **))*(v19 - 2) + 17))(
            v19 - 2,
            v19[6],
            a5);
    if ( v27 >= 0 )
      goto LABEL_27;
    v36 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_27;
    v37 = 17;
    goto LABEL_75;
  }
  v32 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
    v32 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
  if ( !v32 )
  {
    v34 = (*((__int64 (__fastcall **)(void **, const struct STORAGEITEM *, struct IPropertySetStorage **, __int64))*(v19 - 2)
           + 4))(
            v19 - 2,
            v9,
            a5,
            1);
    v35 = v34;
    if ( v34 < 0 )
    {
      v36 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            145,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v34);
          v36 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 2) != 0 )
        {
          WPP_SF_d(v36[2], 146, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v35);
          v27 = v35;
          v36 = (PVOID *)WPP_GLOBAL_Control;
LABEL_87:
          if ( v36 == &WPP_GLOBAL_Control || (*((_BYTE *)v36 + 28) & 2) == 0 )
            goto LABEL_27;
          v37 = 18;
          v39 = (unsigned int)v35;
          goto LABEL_76;
        }
      }
    }
    else
    {
      v36 = (PVOID *)WPP_GLOBAL_Control;
    }
    v27 = v35;
    if ( v35 >= 0 )
      goto LABEL_27;
    goto LABEL_87;
  }
  v33 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertySetStorage.Data1;
  if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertySetStorage.Data1 )
    v33 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertySetStorage.Data4;
  if ( !v33 )
  {
    v27 = CStorageFolder::_BindToPropertySetStorage((CStorageFolder *)(v19 - 2), v9, a5);
    if ( v27 >= 0 )
      goto LABEL_27;
    v36 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_27;
    v37 = 19;
    goto LABEL_75;
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD *, struct _GUID *, struct IPropertySetStorage **))*v18)(v18, a4, a5);
  if ( v27 >= 0 || WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_27;
  v28 = (unsigned int)CGuidToString::CGuidToString(sz, a4);
  v29 = 20;
LABEL_45:
  WPP_SF_Sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v29,
    (unsigned int)WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
    v28,
    v27);
LABEL_27:
  ILFree(v14);
LABEL_28:
  if ( v18 )
    (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x180009af0  push    rbx
0x180009af2  push    rbp
0x180009af3  push    rsi
0x180009af4  push    rdi
0x180009af5  push    r12
0x180009af7  push    r13
0x180009af9  push    r14
0x180009afb  push    r15
0x180009afd  sub     rsp, 0E8h
0x180009b04  mov     rax, cs:__security_cookie
0x180009b0b  xor     rax, rsp
0x180009b0e  mov     [rsp+128h+var_58], rax
0x180009b16  mov     r14, r9
0x180009b19  mov     [rsp+128h+var_F0], r8
0x180009b1e  mov     rsi, rdx
0x180009b21  mov     rbx, rcx
0x180009b24  mov     [rsp+128h+var_F8], rcx
0x180009b29  mov     r12, [rsp+128h+arg_20]
0x180009b31  test    rdx, rdx
0x180009b34  jz      loc_18000A0EB
0x180009b3a  test    r12, r12
0x180009b3d  jz      loc_18000A0F5
0x180009b43  mov     qword ptr [r12], 0
0x180009b4b  call    ?_IsValid@CStorageFolder@@AEAAPEFBUSTORAGEITEM@@PEFBU_ITEMIDLIST@@@Z; CStorageFolder::_IsValid(_ITEMIDLIST const *)
0x180009b50  mov     r13, rax
0x180009b53  test    rax, rax
0x180009b56  jz      loc_18000A0FF
0x180009b5c  test    byte ptr [rax+0Ah], 2
0x180009b60  jz      loc_180009E51
0x180009b66  xor     edi, edi
0x180009b68  movzx   ebp, word ptr [rsi]
0x180009b6b  add     rbp, rsi
0x180009b6e  mov     rax, [rbx+30h]
0x180009b72  mov     [rsp+128h+Src], rax
0x180009b77  mov     rcx, rax; pidl
0x180009b7a  call    cs:__imp_ILGetSize
0x180009b80  mov     ebx, eax
0x180009b82  mov     r15d, ebp
0x180009b85  sub     r15d, esi
0x180009b88  lea     ecx, [r15+rax]; cb
0x180009b8c  cmp     eax, ecx
0x180009b8e  ja      loc_180009FF9
0x180009b94  test    ecx, ecx
0x180009b96  jz      loc_18000A084
0x180009b9c  mov     eax, ecx
0x180009b9e  mov     [rsp+128h+Size], rax
0x180009ba3  call    cs:__imp_CoTaskMemAlloc
0x180009ba9  mov     rdi, rax
0x180009bac  test    rax, rax
0x180009baf  jz      loc_18000A109
0x180009bb5  mov     r8, [rsp+128h+Size]; Size
0x180009bba  xor     edx, edx; Val
0x180009bbc  mov     rcx, rax; void *
0x180009bbf  call    memset_0
0x180009bc4  lea     eax, [rbx-2]
0x180009bc7  mov     ebx, eax
0x180009bc9  mov     r8d, eax; Size
0x180009bcc  mov     rdx, [rsp+128h+Src]; Src
0x180009bd1  mov     rcx, rdi; void *
0x180009bd4  call    memcpy_0
0x180009bd9  mov     r8d, r15d; Size
0x180009bdc  lea     rcx, [rdi+rbx]; void *
0x180009be0  mov     rdx, rsi; Src
0x180009be3  call    memcpy_0
0x180009be8  call    cs:__imp_GetProcessHeap
0x180009bee  mov     rcx, rax; hHeap
0x180009bf1  mov     edx, 8; dwFlags
0x180009bf6  mov     r8d, 0B0h; dwBytes
0x180009bfc  call    cs:__imp_HeapAlloc
0x180009c02  mov     rbx, rax
0x180009c05  mov     [rsp+128h+Src], rax
0x180009c0a  mov     r15, [rsp+128h+var_F8]
0x180009c0f  test    rax, rax
0x180009c12  jz      loc_18000A08E
0x180009c18  mov     esi, [r15+274h]
0x180009c1f  mov     eax, [r13+0Ah]
0x180009c23  mov     dword ptr [rsp+128h+var_F8], eax
0x180009c27  lea     rcx, ??_7CBaseFolder@@6BIDelegateFolder@@@; const CBaseFolder::`vftable'{for `IDelegateFolder'}
0x180009c2e  mov     [rbx], rcx
0x180009c31  lea     rax, ??_7CBaseFolder@@6BIPersistFolder2@@@; const CBaseFolder::`vftable'{for `IPersistFolder2'}
0x180009c38  mov     [rbx+8], rax
0x180009c3c  lea     rax, ??_7CBaseFolder@@6BIShellFolder2@@@; const CBaseFolder::`vftable'{for `IShellFolder2'}
0x180009c43  mov     [rbx+10h], rax
0x180009c47  lea     rax, ??_7CBaseFolder@@6BIExplorerPaneVisibility@@@; const CBaseFolder::`vftable'{for `IExplorerPaneVisibility'}
0x180009c4e  mov     [rbx+18h], rax
0x180009c52  lea     rax, ??_7CBaseFolder@@6BIItemNameLimits@@@; const CBaseFolder::`vftable'{for `IItemNameLimits'}
0x180009c59  mov     [rbx+20h], rax
0x180009c5d  mov     dword ptr [rbx+28h], 1
0x180009c64  movups  xmm0, xmmword ptr cs:CLSID_ContentFolder.Data1
0x180009c6b  movups  xmmword ptr [rbx+2Ch], xmm0
0x180009c6f  xor     ecx, ecx
0x180009c71  mov     [rbx+40h], rcx
0x180009c75  lea     rax, [r15-10h]
0x180009c79  mov     [rbx+48h], rax
0x180009c7d  mov     [rbx+50h], ecx
0x180009c80  mov     [rbx+58h], rcx
0x180009c84  mov     [rbx+60h], rcx
0x180009c88  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009c8f  call    cs:__imp_EnterCriticalSection
0x180009c95  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180009c9c  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180009ca3  call    cs:__imp_LeaveCriticalSection
0x180009ca9  mov     rcx, [rbx+48h]
0x180009cad  test    rcx, rcx
0x180009cb0  jz      short loc_180009CBF
0x180009cb2  mov     rax, [rcx]
0x180009cb5  mov     rax, [rax+8]
0x180009cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cbe  nop
0x180009cbf  lea     rax, ??_7CContentFolder@@6BIDelegateFolder@@@; const CContentFolder::`vftable'{for `IDelegateFolder'}
0x180009cc6  mov     [rbx], rax
0x180009cc9  lea     rax, ??_7CContentFolder@@6BIPersistFolder2@@@; const CContentFolder::`vftable'{for `IPersistFolder2'}
0x180009cd0  mov     [rbx+8], rax
0x180009cd4  lea     rax, ??_7CContentFolder@@6BIShellFolder2@@@; const CContentFolder::`vftable'{for `IShellFolder2'}
0x180009cdb  mov     [rbx+10h], rax
0x180009cdf  lea     rax, ??_7CContentFolder@@6BIExplorerPaneVisibility@@@; const CContentFolder::`vftable'{for `IExplorerPaneVisibility'}
0x180009ce6  mov     [rbx+18h], rax
0x180009cea  lea     rax, ??_7CContentFolder@@6BIItemNameLimits@@@; const CContentFolder::`vftable'{for `IItemNameLimits'}
0x180009cf1  mov     [rbx+20h], rax
0x180009cf5  lea     rax, ??_7CContentFolder@@6BIShellFolderViewCB@@@; const CContentFolder::`vftable'{for `IShellFolderViewCB'}
0x180009cfc  mov     [rbx+68h], rax
0x180009d00  lea     rax, ??_7CContentFolder@@6BIFolderViewSettings@@@; const CContentFolder::`vftable'{for `IFolderViewSettings'}
0x180009d07  mov     [rbx+70h], rax
0x180009d0b  lea     rax, ??_7CContentFolder@@6BIShellIconOverlay@@@; const CContentFolder::`vftable'{for `IShellIconOverlay'}
0x180009d12  mov     [rbx+78h], rax
0x180009d16  lea     rax, ??_7CContentFolder@@6BIStorage@@@; const CContentFolder::`vftable'{for `IStorage'}
0x180009d1d  mov     [rbx+80h], rax
0x180009d24  lea     rax, ??_7CContentFolder@@6BIUpdateIDList@@@; const CContentFolder::`vftable'{for `IUpdateIDList'}
0x180009d2b  mov     [rbx+88h], rax
0x180009d32  xor     ecx, ecx
0x180009d34  mov     [rbx+90h], ecx
0x180009d3a  mov     [rbx+94h], esi
0x180009d40  mov     [rbx+98h], ecx
0x180009d46  mov     eax, dword ptr [rsp+128h+var_F8]
0x180009d4a  mov     [rbx+9Ch], eax
0x180009d50  mov     [rbx+0A0h], rcx
0x180009d57  mov     rcx, [rbx+48h]
0x180009d5b  mov     rax, [rcx]
0x180009d5e  lea     r8, [rbx+98h]
0x180009d65  mov     rdx, [rbx+40h]
0x180009d69  mov     rax, [rax+98h]
0x180009d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d75  test    eax, eax
0x180009d77  js      loc_18000A113
0x180009d7d  mov     eax, [rbx+98h]
0x180009d83  mov     dword ptr [rbx+50h], 10h
0x180009d8a  cmp     eax, 3
0x180009d8d  jz      short loc_180009DA8
0x180009d8f  sub     eax, 1
0x180009d92  jnz     loc_18000A06C
0x180009d98  lea     rax, aPropSystemSize; "prop:System.Size;System.DateModified;Sy"...
0x180009d9f  lea     rcx, qword_1800794B0
0x180009da6  jmp     short loc_180009DB6
0x180009da8  lea     rax, aPropSystemSize_0; "prop:System.Size;System.DateModified;Sy"...
0x180009daf  lea     rcx, qword_180079330
0x180009db6  mov     [rbx+58h], rcx
0x180009dba  mov     [rbx+0A8h], rax
0x180009dc1  test    rbx, rbx
0x180009dc4  jz      loc_18000A151
0x180009dca  lea     rcx, [rbx+8]
0x180009dce  mov     rax, [rcx]
0x180009dd1  mov     rdx, rdi
0x180009dd4  mov     rax, [rax+20h]
0x180009dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ddd  mov     esi, eax
0x180009ddf  test    eax, eax
0x180009de1  js      loc_180009FCE
0x180009de7  test    rbp, rbp
0x180009dea  jz      loc_180009EA0
0x180009df0  cmp     word ptr [rbp+0], 0
0x180009df5  jz      loc_180009EA0
0x180009dfb  lea     rcx, [rbx+10h]
0x180009dff  mov     rax, [rcx]
0x180009e02  mov     [rsp+128h+var_108], r12
0x180009e07  mov     r9, r14
0x180009e0a  mov     r8, [rsp+128h+var_F0]
0x180009e0f  mov     rdx, rbp
0x180009e12  mov     rax, [rax+28h]
0x180009e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e1b  mov     esi, eax
0x180009e1d  test    eax, eax
0x180009e1f  jns     short loc_180009E5D
0x180009e21  mov     rax, cs:WPP_GLOBAL_Control
0x180009e28  lea     rcx, WPP_GLOBAL_Control
0x180009e2f  cmp     rax, rcx
0x180009e32  jz      short loc_180009E5D
0x180009e34  test    byte ptr [rax+1Ch], 2
0x180009e38  jz      short loc_180009E5D
0x180009e3a  mov     rdx, r14; rguid
0x180009e3d  lea     rcx, [rsp+128h+sz]; lpsz
0x180009e42  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x180009e47  mov     edx, 15h
0x180009e4c  jmp     loc_180009F68
0x180009e51  mov     eax, 80004002h
0x180009e56  jmp     short loc_180009E7C
0x180009e58  test    rdi, rdi
0x180009e5b  jz      short loc_180009E66
0x180009e5d  mov     rcx, rdi; pidl
0x180009e60  call    cs:__imp_ILFree
0x180009e66  test    rbx, rbx
0x180009e69  jz      short loc_180009E7A
0x180009e6b  mov     rax, [rbx]
0x180009e6e  mov     rcx, rbx
0x180009e71  mov     rax, [rax+10h]
0x180009e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e7a  mov     eax, esi
0x180009e7c  mov     rcx, [rsp+128h+var_58]
0x180009e84  xor     rcx, rsp; StackCookie
0x180009e87  call    __security_check_cookie
0x180009e8c  add     rsp, 0E8h
0x180009e93  pop     r15
0x180009e95  pop     r14
0x180009e97  pop     r13
0x180009e99  pop     r12
0x180009e9b  pop     rdi
0x180009e9c  pop     rsi
0x180009e9d  pop     rbp
0x180009e9e  pop     rbx
0x180009e9f  retn
0x180009ea0  mov     [rsp+128h+var_F8], 0
0x180009ea9  mov     r10, [rsp+128h+var_F0]
0x180009eae  test    r10, r10
0x180009eb1  jnz     loc_18000A095
0x180009eb7  mov     rax, [r14]
0x180009eba  sub     rax, qword ptr cs:IID_IPortableDevice.Data1
0x180009ec1  jnz     short loc_180009ECE
0x180009ec3  mov     rax, [r14+8]
0x180009ec7  sub     rax, qword ptr cs:IID_IPortableDevice.Data4
0x180009ece  test    rax, rax
0x180009ed1  jz      loc_18000A182
0x180009ed7  mov     rax, [r14]
0x180009eda  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x180009ee1  jnz     short loc_180009EEE
0x180009ee3  mov     rax, [r14+8]
0x180009ee7  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x180009eee  test    rax, rax
0x180009ef1  jz      loc_180009F8B
0x180009ef7  mov     rax, [r14]
0x180009efa  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data1
0x180009f01  jnz     short loc_180009F0E
0x180009f03  mov     rax, [r14+8]
0x180009f07  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data4
0x180009f0e  mov     r8, r12; struct IPropertySetStorage **
0x180009f11  test    rax, rax
0x180009f14  jz      loc_18000A256
0x180009f1a  mov     rax, [rbx]
0x180009f1d  mov     rdx, r14
0x180009f20  mov     rcx, rbx
0x180009f23  mov     rax, [rax]
0x180009f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f2b  mov     esi, eax
0x180009f2d  test    eax, eax
0x180009f2f  jns     loc_180009E5D
0x180009f35  mov     rax, cs:WPP_GLOBAL_Control
0x180009f3c  lea     rcx, WPP_GLOBAL_Control
0x180009f43  cmp     rax, rcx
0x180009f46  jz      loc_180009E5D
0x180009f4c  test    byte ptr [rax+1Ch], 2
0x180009f50  jz      loc_180009E5D
0x180009f56  mov     rdx, r14; rguid
0x180009f59  lea     rcx, [rsp+128h+sz]; lpsz
0x180009f5e  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x180009f63  mov     edx, 14h
0x180009f68  mov     dword ptr [rsp+128h+var_108], esi
0x180009f6c  mov     r9, rax
0x180009f6f  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180009f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f7d  mov     rcx, [rcx+10h]
0x180009f81  call    WPP_SF_Sd
0x180009f86  jmp     loc_180009E5D
0x180009f8b  lea     rcx, [r15-10h]
0x180009f8f  mov     rax, [rcx]
0x180009f92  mov     r9d, 1
0x180009f98  mov     r8, r12
0x180009f9b  mov     rdx, r13
0x180009f9e  mov     rax, [rax+20h]
0x180009fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fa7  mov     ebp, eax
0x180009fa9  test    eax, eax
0x180009fab  js      loc_18000A1CE
0x180009fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fb8  lea     r14, WPP_GLOBAL_Control
0x180009fbf  mov     esi, ebp
0x180009fc1  test    ebp, ebp
0x180009fc3  jns     loc_180009E5D
0x180009fc9  jmp     loc_18000A23E
0x180009fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fd5  lea     rax, WPP_GLOBAL_Control
0x180009fdc  cmp     rcx, rax
0x180009fdf  jz      loc_180009E5D
0x180009fe5  test    byte ptr [rcx+1Ch], 2
0x180009fe9  jz      loc_180009E5D
0x180009fef  mov     edx, 10h
0x180009ff4  jmp     loc_18000A160
0x180009ff9  mov     esi, 8000FFFFh
0x180009ffe  xor     ebx, ebx
0x18000a000  lea     rbp, WPP_GLOBAL_Control
0x18000a007  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a00e  cmp     rcx, rbp
0x18000a011  jz      loc_180009E58
  ... truncated ...
```
