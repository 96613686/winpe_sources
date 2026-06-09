# CShellContextMenuBase::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x18003c2e0`
- end: `0x18003c501`
- name: `?Initialize@CShellContextMenuBase@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `545`
- prototype: `int(CShellContextMenuBase *__hidden this, const struct _ITEMIDLIST *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180002818`
- `0x18000dd70`
- `0x180013ee4`
- `0x180019280`
- `0x18002efb4`
- `0x18003c2e0`
- `0x18003cf98`
- `0x180093010`

## import_xrefs

- `SHELL32!DragQueryFileW` at `0x18003c3b9`
- `SHELL32!DragQueryFileW` at `0x18003c3f4`
- `SHELL32!DragQueryFileW` at `0x18003c41c`
- `SHELL32!DragQueryFileW` at `0x18003c3b9`
- `SHELL32!DragQueryFileW` at `0x18003c3f4`
- `SHELL32!DragQueryFileW` at `0x18003c41c`
- `SHELL32!__imp_ILClone` at `0x18003c35c`
- `SHELL32!__imp_ILClone` at `0x18003c35c`
- `ole32!ReleaseStgMedium` at `0x18003c4ce`
- `ole32!ReleaseStgMedium` at `0x18003c4ce`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003c401`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003c401`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c43a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c43a`
- `iertutil!__imp_DPA_Create` at `0x18003c3c6`
- `iertutil!__imp_DPA_Create` at `0x18003c3c6`
- `iertutil!__imp_DPA_GetPtr` at `0x18003c46d`
- `iertutil!__imp_DPA_GetPtr` at `0x18003c46d`
- `iertutil!__imp_DPA_SetPtr` at `0x18003c42a`
- `iertutil!__imp_DPA_SetPtr` at `0x18003c42a`

## pseudocode

```c
__int64 __fastcall CShellContextMenuBase::Initialize(
        CShellContextMenuBase *this,
        const struct _ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  LPITEMIDLIST v6; // rsi
  int ExtensionMenus; // ebx
  struct IDataObjectVtbl *lpVtbl; // rax
  UINT FileW; // eax
  UINT v10; // ebx
  struct _DPA *v11; // r15
  UINT v12; // r13d
  WCHAR *v13; // rax
  OLECHAR *v14; // r12
  bool v15; // zf
  unsigned __int16 *Ptr; // rsi
  struct _DPA *v17; // rdx
  unsigned int v18; // r8d
  HDPA v20; // [rsp+20h] [rbp-58h] BYREF
  LPITEMIDLIST v21; // [rsp+28h] [rbp-50h] BYREF
  struct IContact *v22; // [rsp+30h] [rbp-48h] BYREF
  STGMEDIUM hDrop; // [rsp+38h] [rbp-40h] BYREF
  __int16 v24; // [rsp+50h] [rbp-28h] BYREF
  int v25; // [rsp+52h] [rbp-26h]
  __int16 v26; // [rsp+56h] [rbp-22h]
  __int64 v27; // [rsp+58h] [rbp-20h]
  int v28; // [rsp+60h] [rbp-18h]
  int v29; // [rsp+64h] [rbp-14h]
  __int64 v30; // [rsp+68h] [rbp-10h]
  struct IDataObject *v31; // [rsp+D0h] [rbp+58h] BYREF

  v29 = -1;
  v27 = 0;
  v21 = 0;
  v24 = 15;
  v31 = 0;
  v25 = 0;
  v26 = 0;
  v28 = 1;
  v6 = 0;
  v30 = 1;
  v20 = 0;
  v22 = 0;
  memset(&hDrop, 0, sizeof(hDrop));
  if ( a3 )
  {
    if ( a2 )
    {
      v21 = ILClone(a2);
      v6 = v21;
      if ( !v21 )
      {
        ExtensionMenus = -2147024882;
        goto LABEL_22;
      }
    }
    lpVtbl = a3->lpVtbl;
    v31 = a3;
    ((void (__fastcall *)(struct IDataObject *, const struct _ITEMIDLIST *, struct IDataObject *, HKEY, HDPA, LPITEMIDLIST))lpVtbl->AddRef)(
      a3,
      a2,
      a3,
      a4,
      v20,
      v21);
    ExtensionMenus = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))a3->lpVtbl->GetData)(
                       a3,
                       &v24,
                       &hDrop);
    if ( ExtensionMenus < 0 )
      goto LABEL_22;
    FileW = DragQueryFileW((HDROP)hDrop.hBitmap, 0xFFFFFFFF, 0, 0);
    *((_DWORD *)this + 10) = FileW;
    v10 = FileW;
    v20 = DPA_Create(FileW);
    v11 = v20;
    if ( !v20 )
    {
LABEL_8:
      ExtensionMenus = -2147024882;
LABEL_21:
      ReleaseStgMedium(&hDrop);
      goto LABEL_22;
    }
    while ( v10 )
    {
      v12 = DragQueryFileW((HDROP)hDrop.hBitmap, --v10, 0, 0);
      v13 = SysAllocStringLen(0, v12);
      v14 = v13;
      if ( !v13 )
        goto LABEL_8;
      DragQueryFileW((HDROP)hDrop.hBitmap, v10, v13, v12 + 1);
      if ( !DPA_SetPtr(v20, v10, v14) )
      {
        SysFreeString(v14);
        goto LABEL_8;
      }
    }
    v15 = *((_DWORD *)this + 10) == 1;
    *((_QWORD *)this + 2) = v6;
    v21 = 0;
    *((_QWORD *)this + 3) = v11;
    v20 = 0;
    *((_QWORD *)this + 4) = a3;
    v31 = 0;
    *(_QWORD *)((char *)this + 44) = 0;
    if ( v15 )
    {
      Ptr = (unsigned __int16 *)DPA_GetPtr(v11, 0);
      ExtensionMenus = CContactStorage::OpenContactReadOnly(Ptr, &v22);
      if ( ExtensionMenus < 0 )
        goto LABEL_21;
      *((_DWORD *)this + 11) = IsThisMyContact(v22);
      *((_DWORD *)this + 12) = IsPathInAddressBook(Ptr);
    }
    v17 = (struct _DPA *)*((_QWORD *)this + 3);
    if ( v17 && (v18 = *((_DWORD *)this + 10)) != 0 )
    {
      ExtensionMenus = CExtensionContextMenus::_LoadExtensionMenus((struct _DPA **)this + 7, v17, v18);
      if ( ExtensionMenus >= 0 )
        ExtensionMenus = 0;
    }
    else
    {
      ExtensionMenus = -2147024809;
    }
    goto LABEL_21;
  }
  ExtensionMenus = -2147024809;
LABEL_22:
  ClearCachedSelectionInfo(&v21, &v20, &v31, a4);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v22);
  return (unsigned int)ExtensionMenus;
}

```

## disassembly

```asm
0x18003c2e0  push    rbp
0x18003c2e2  push    rbx
0x18003c2e3  push    rsi
0x18003c2e4  push    rdi
0x18003c2e5  push    r12
0x18003c2e7  push    r13
0x18003c2e9  push    r14
0x18003c2eb  push    r15
0x18003c2ed  mov     rbp, rsp
0x18003c2f0  sub     rsp, 78h
0x18003c2f4  xor     r13d, r13d
0x18003c2f7  mov     [rbp+var_14], 0FFFFFFFFh
0x18003c2fe  xor     eax, eax
0x18003c300  mov     [rbp+var_20], r13
0x18003c304  mov     [rbp+var_30], rax
0x18003c308  xorps   xmm0, xmm0
0x18003c30b  mov     eax, 0Fh
0x18003c310  mov     [rbp+var_50], r13
0x18003c314  mov     [rbp+var_28], ax
0x18003c318  mov     r14, r8
0x18003c31b  xor     eax, eax
0x18003c31d  mov     [rbp+arg_10], r13
0x18003c321  mov     [rbp+var_26], eax
0x18003c324  mov     rdi, rcx
0x18003c327  mov     [rbp+var_22], ax
0x18003c32b  lea     eax, [r13+1]
0x18003c32f  mov     [rbp+var_18], eax
0x18003c332  mov     esi, r13d
0x18003c335  mov     [rbp+var_10], rax
0x18003c339  mov     [rbp+var_58], r13
0x18003c33d  mov     [rbp+var_48], r13
0x18003c341  movups  xmmword ptr [rbp+hDrop], xmm0
0x18003c345  test    r8, r8
0x18003c348  jnz     short loc_18003C354
0x18003c34a  mov     ebx, 80070057h
0x18003c34f  jmp     loc_18003C4D4
0x18003c354  test    rdx, rdx
0x18003c357  jz      short loc_18003C378
0x18003c359  mov     rcx, rdx; pidl
0x18003c35c  call    cs:__imp_ILClone
0x18003c362  mov     [rbp+var_50], rax
0x18003c366  mov     rsi, rax
0x18003c369  test    rax, rax
0x18003c36c  jnz     short loc_18003C378
0x18003c36e  mov     ebx, 8007000Eh
0x18003c373  jmp     loc_18003C4D4
0x18003c378  mov     rax, [r14]
0x18003c37b  mov     rcx, r14
0x18003c37e  mov     [rbp+arg_10], r14
0x18003c382  mov     rax, [rax+8]
0x18003c386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c38b  mov     rax, [r14]
0x18003c38e  lea     r8, [rbp+hDrop]
0x18003c392  lea     rdx, [rbp+var_28]
0x18003c396  mov     rcx, r14
0x18003c399  mov     rax, [rax+18h]
0x18003c39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3a2  mov     ebx, eax
0x18003c3a4  test    eax, eax
0x18003c3a6  js      loc_18003C4D4
0x18003c3ac  mov     rcx, [rbp+hDrop+8]; hDrop
0x18003c3b0  xor     r9d, r9d; cch
0x18003c3b3  xor     r8d, r8d; lpszFile
0x18003c3b6  or      edx, 0FFFFFFFFh; iFile
0x18003c3b9  call    cs:__imp_DragQueryFileW
0x18003c3bf  mov     ecx, eax; cItemGrow
0x18003c3c1  mov     [rdi+28h], eax
0x18003c3c4  mov     ebx, eax
0x18003c3c6  call    cs:__imp_DPA_Create
0x18003c3cc  mov     [rbp+var_58], rax
0x18003c3d0  mov     r15, rax
0x18003c3d3  test    rax, rax
0x18003c3d6  jnz     short loc_18003C3E2
0x18003c3d8  mov     ebx, 8007000Eh
0x18003c3dd  jmp     loc_18003C4CA
0x18003c3e2  test    ebx, ebx
0x18003c3e4  jz      short loc_18003C442
0x18003c3e6  mov     rcx, [rbp+hDrop+8]; hDrop
0x18003c3ea  dec     ebx
0x18003c3ec  mov     edx, ebx; iFile
0x18003c3ee  xor     r9d, r9d; cch
0x18003c3f1  xor     r8d, r8d; lpszFile
0x18003c3f4  call    cs:__imp_DragQueryFileW
0x18003c3fa  mov     edx, eax; ui
0x18003c3fc  xor     ecx, ecx; strIn
0x18003c3fe  mov     r13d, eax
0x18003c401  call    cs:__imp_SysAllocStringLen
0x18003c407  mov     r12, rax
0x18003c40a  test    rax, rax
0x18003c40d  jz      short loc_18003C3D8
0x18003c40f  mov     rcx, [rbp+hDrop+8]; hDrop
0x18003c413  lea     r9d, [r13+1]; cch
0x18003c417  mov     r8, rax; lpszFile
0x18003c41a  mov     edx, ebx; iFile
0x18003c41c  call    cs:__imp_DragQueryFileW
0x18003c422  mov     r8, r12; p
0x18003c425  mov     edx, ebx; i
0x18003c427  mov     rcx, r15; hdpa
0x18003c42a  call    cs:__imp_DPA_SetPtr
0x18003c430  xor     r13d, r13d
0x18003c433  test    eax, eax
0x18003c435  jnz     short loc_18003C3E2
0x18003c437  mov     rcx, r12; bstrString
0x18003c43a  call    cs:__imp_SysFreeString
0x18003c440  jmp     short loc_18003C3D8
0x18003c442  cmp     dword ptr [rdi+28h], 1
0x18003c446  mov     [rdi+10h], rsi
0x18003c44a  mov     [rbp+var_50], r13
0x18003c44e  mov     [rdi+18h], r15
0x18003c452  mov     [rbp+var_58], r13
0x18003c456  mov     [rdi+20h], r14
0x18003c45a  mov     [rbp+arg_10], r13
0x18003c45e  mov     qword ptr [rdi+2Ch], 0
0x18003c466  jnz     short loc_18003C49F
0x18003c468  xor     edx, edx; i
0x18003c46a  mov     rcx, r15; hdpa
0x18003c46d  call    cs:__imp_DPA_GetPtr
0x18003c473  mov     rcx, rax; unsigned __int16 *
0x18003c476  lea     rdx, [rbp+var_48]; struct IContact **
0x18003c47a  mov     rsi, rax
0x18003c47d  call    ?OpenContactReadOnly@CContactStorage@@SAJPEBGPEAPEAUIContact@@@Z; CContactStorage::OpenContactReadOnly(ushort const *,IContact * *)
0x18003c482  mov     ebx, eax
0x18003c484  test    eax, eax
0x18003c486  js      short loc_18003C4CA
0x18003c488  mov     rcx, [rbp+var_48]; struct IContact *
0x18003c48c  call    ?IsThisMyContact@@YAHPEAUIContact@@@Z; IsThisMyContact(IContact *)
0x18003c491  mov     rcx, rsi; Path
0x18003c494  mov     [rdi+2Ch], eax
0x18003c497  call    ?IsPathInAddressBook@@YAHPEBG@Z; IsPathInAddressBook(ushort const *)
0x18003c49c  mov     [rdi+30h], eax
0x18003c49f  mov     rdx, [rdi+18h]; struct _DPA *
0x18003c4a3  test    rdx, rdx
0x18003c4a6  jz      short loc_18003C4C5
0x18003c4a8  mov     r8d, [rdi+28h]; unsigned int
0x18003c4ac  test    r8d, r8d
0x18003c4af  jz      short loc_18003C4C5
0x18003c4b1  lea     rcx, [rdi+38h]; this
0x18003c4b5  call    ?_LoadExtensionMenus@CExtensionContextMenus@@AEAAJPEAU_DPA@@I@Z; CExtensionContextMenus::_LoadExtensionMenus(_DPA *,uint)
0x18003c4ba  mov     ebx, eax
0x18003c4bc  test    eax, eax
0x18003c4be  js      short loc_18003C4CA
0x18003c4c0  mov     ebx, r13d
0x18003c4c3  jmp     short loc_18003C4CA
0x18003c4c5  mov     ebx, 80070057h
0x18003c4ca  lea     rcx, [rbp+hDrop]; LPSTGMEDIUM
0x18003c4ce  call    cs:__imp_ReleaseStgMedium
0x18003c4d4  lea     r8, [rbp+arg_10]
0x18003c4d8  lea     rdx, [rbp+var_58]
0x18003c4dc  lea     rcx, [rbp+var_50]
0x18003c4e0  call    _ClearCachedSelectionInfo
0x18003c4e5  lea     rcx, [rbp+var_48]
0x18003c4e9  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18003c4ee  mov     eax, ebx
0x18003c4f0  add     rsp, 78h
0x18003c4f4  pop     r15
0x18003c4f6  pop     r14
0x18003c4f8  pop     r13
0x18003c4fa  pop     r12
0x18003c4fc  pop     rdi
0x18003c4fd  pop     rsi
0x18003c4fe  pop     rbx
0x18003c4ff  pop     rbp
0x18003c500  retn
```
