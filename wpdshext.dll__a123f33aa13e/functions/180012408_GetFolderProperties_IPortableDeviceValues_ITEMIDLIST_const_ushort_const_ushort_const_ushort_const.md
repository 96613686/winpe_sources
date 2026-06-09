# GetFolderProperties(IPortableDeviceValues *,_ITEMIDLIST const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180012408`
- end: `0x18001296d`
- name: `?GetFolderProperties@@YAJPEAUIPortableDeviceValues@@PEFBU_ITEMIDLIST@@PEBG22@Z`
- size: `1381`
- prototype: `__int64 __usercall@<rax>(struct IPortableDeviceValues *@<rcx>, const struct _ITEMIDLIST *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800118d4`
- `0x180042af0`
- `0x18004673c`

## callees

- `0x180012408`
- `0x180019d90`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180052c80`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001253b`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18001253b`
- `KERNEL32!GetFileAttributesW` at `0x1800126c3`
- `KERNEL32!GetFileAttributesW` at `0x1800126c3`
- `KERNEL32!GetSystemTime` at `0x1800127f2`
- `KERNEL32!GetSystemTime` at `0x1800127f2`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180012802`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x180012802`
- `ole32!PropVariantClear` at `0x180012864`
- `ole32!PropVariantClear` at `0x180012918`
- `ole32!PropVariantClear` at `0x180012864`
- `ole32!PropVariantClear` at `0x180012918`
- `OLEAUT32!__imp_VariantInit` at `0x1800126e1`
- `OLEAUT32!__imp_VariantInit` at `0x1800126e1`
- `OLEAUT32!__imp_VariantClear` at `0x18001277a`
- `OLEAUT32!__imp_VariantClear` at `0x18001277a`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180012815`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180012815`
- `SHELL32!SHBindToParent` at `0x180012618`
- `SHELL32!SHBindToParent` at `0x180012618`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetFolderProperties(
        struct IPortableDeviceValues *a1,
        const struct _ITEMIDLIST *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  const wchar_t *v9; // r15
  int v10; // ebx
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  HRESULT v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // ebx
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT pvtime; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Filename[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Ext[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v9 = a5;
  SystemTime = 0;
  LocalTime = 0;
  memset_0(Filename, 0, 0x208u);
  memset_0(Ext, 0, 0x208u);
  memset(&pvtime, 0, sizeof(pvtime));
  if ( !a1 || !a3 || !a4 )
  {
    v10 = -2147024809;
    goto LABEL_59;
  }
  v11 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, const unsigned __int16 *))a1->lpVtbl->SetStringValue)(
          a1,
          &WPD_OBJECT_PARENT_ID,
          a3);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v13 = 74;
LABEL_9:
      WPP_SF_d(v12[2], v13, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, (unsigned int)v11);
      goto LABEL_59;
    }
    goto LABEL_59;
  }
  if ( !a5 )
    v9 = a4;
  _wsplitpath_s(v9, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u);
  StringCchCatW(Filename, 0x104u, Ext);
  v11 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, wchar_t *))a1->lpVtbl->SetStringValue)(
          a1,
          &WPD_OBJECT_ORIGINAL_FILE_NAME,
          Filename);
  v10 = v11;
  if ( v11 >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, wchar_t *))a1->lpVtbl->SetStringValue)(
            a1,
            &WPD_OBJECT_NAME,
            Filename);
    v10 = v11;
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v13 = 76;
        goto LABEL_9;
      }
      goto LABEL_59;
    }
    if ( a2 )
    {
      ppidlLast = 0;
      ppv = 0;
      v14 = SHBindToParent(a2, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &ppv, &ppidlLast);
      v10 = v14;
      if ( v14 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_26;
        v16 = 77;
LABEL_25:
        WPP_SF_d(v15[2], v16, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, (unsigned int)v14);
LABEL_26:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
        goto LABEL_59;
      }
      v20 = 0x40000000;
      v14 = (*(__int64 (__fastcall **)(void *, __int64, LPCITEMIDLIST *, int *))(*(_QWORD *)ppv + 72LL))(
              ppv,
              1,
              &ppidlLast,
              &v20);
      v10 = v14;
      if ( v14 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_26;
        v16 = 78;
        goto LABEL_25;
      }
      if ( (v20 & 0x40000000) != 0 )
      {
        LOBYTE(v17) = GetFileAttributesW(a4);
      }
      else
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v14 = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, __int64 *, VARIANTARG *))(*(_QWORD *)ppv + 136LL))(
                ppv,
                ppidlLast,
                &PKEY_WPDNSE_Attributes,
                &pvarg);
        v10 = v14;
        if ( v14 < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_26;
          v16 = 79;
          goto LABEL_25;
        }
        LOBYTE(v17) = 0;
        if ( pvarg.vt == 19 )
          v17 = ((pvarg.bVal & 2) != 0 ? 16 : 128)
              | ((pvarg.iVal & 0x100 | ((pvarg.iVal & 0x400 | ((unsigned int)pvarg.lVal >> 1) & 0x100) >> 1)) >> 7);
        VariantClear(&pvarg);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      if ( (v17 & 2) != 0 )
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))a1->lpVtbl->SetBoolValue)(
          a1,
          &WPD_OBJECT_ISHIDDEN,
          1);
      if ( (v17 & 1) != 0 )
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, _QWORD))a1->lpVtbl->SetBoolValue)(
          a1,
          &WPD_OBJECT_CAN_DELETE,
          0);
      if ( (v17 & 4) != 0 )
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))a1->lpVtbl->SetBoolValue)(
          a1,
          &WPD_OBJECT_ISSYSTEM,
          1);
    }
    GetSystemTime(&SystemTime);
    if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime)
      && SystemTimeToVariantTime(&LocalTime, &pvtime.dblVal) )
    {
      pvtime.vt = 7;
      ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->SetValue)(
        a1,
        &WPD_OBJECT_DATE_CREATED,
        &pvtime);
      ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->SetValue)(
        a1,
        &WPD_OBJECT_DATE_MODIFIED,
        &pvtime);
    }
    PropVariantClear(&pvtime);
    v11 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, const GUID *))a1->lpVtbl->SetGuidValue)(
            a1,
            &WPD_OBJECT_CONTENT_TYPE,
            &WPD_CONTENT_TYPE_FOLDER);
    v10 = v11;
    if ( v11 >= 0 )
    {
      v11 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, const GUID *))a1->lpVtbl->SetGuidValue)(
              a1,
              &WPD_OBJECT_FORMAT,
              &WPD_OBJECT_FORMAT_PROPERTIES_ONLY);
      v10 = v11;
      if ( v11 >= 0 )
      {
        if ( a2 )
          SearchForMetaData(a2, a1);
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v13 = 81;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v13 = 80;
        goto LABEL_9;
      }
    }
    goto LABEL_59;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v13 = 75;
    goto LABEL_9;
  }
LABEL_59:
  PropVariantClear(&pvtime);
  if ( v10 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
      (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180012408  push    rbp
0x18001240a  push    rbx
0x18001240b  push    rsi
0x18001240c  push    rdi
0x18001240d  push    r14
0x18001240f  push    r15
0x180012411  lea     rbp, [rsp-3F8h]
0x180012419  sub     rsp, 4F8h
0x180012420  mov     rax, cs:__security_cookie
0x180012427  xor     rax, rsp
0x18001242a  mov     [rbp+420h+var_40], rax
0x180012431  mov     r14, r9
0x180012434  mov     rbx, r8
0x180012437  mov     rsi, rdx
0x18001243a  mov     rdi, rcx
0x18001243d  mov     r15, [rbp+420h+arg_20]
0x180012444  xorps   xmm0, xmm0
0x180012447  movups  xmmword ptr [rbp+420h+SystemTime.wYear], xmm0
0x18001244b  xorps   xmm1, xmm1
0x18001244e  movups  xmmword ptr [rbp+420h+LocalTime.wYear], xmm1
0x180012452  xor     edx, edx; Val
0x180012454  mov     r8d, 208h; Size
0x18001245a  lea     rcx, [rbp+420h+var_460]; void *
0x18001245e  call    memset_0
0x180012463  xor     edx, edx; Val
0x180012465  mov     r8d, 208h; Size
0x18001246b  lea     rcx, [rbp+420h+var_250]; void *
0x180012472  call    memset_0
0x180012477  xorps   xmm0, xmm0
0x18001247a  xor     eax, eax
0x18001247c  movups  xmmword ptr [rsp+520h+pvtime], xmm0
0x180012481  mov     [rsp+520h+var_4A8], rax
0x180012486  test    rdi, rdi
0x180012489  jnz     short loc_180012495
0x18001248b  mov     ebx, 80070057h
0x180012490  jmp     loc_18001290C
0x180012495  test    rbx, rbx
0x180012498  jz      short loc_18001248B
0x18001249a  test    r14, r14
0x18001249d  jz      short loc_18001248B
0x18001249f  mov     rax, [rdi]
0x1800124a2  mov     r8, rbx
0x1800124a5  lea     rdx, WPD_OBJECT_PARENT_ID
0x1800124ac  mov     rcx, rdi
0x1800124af  mov     rax, [rax+38h]
0x1800124b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124b8  mov     ebx, eax
0x1800124ba  test    eax, eax
0x1800124bc  jns     short loc_1800124FC
0x1800124be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124c5  lea     rdi, WPP_GLOBAL_Control
0x1800124cc  cmp     rcx, rdi
0x1800124cf  jz      loc_180012913
0x1800124d5  test    byte ptr [rcx+1Ch], 2
0x1800124d9  jz      loc_180012913
0x1800124df  mov     edx, 4Ah ; 'J'
0x1800124e4  mov     r9d, eax
0x1800124e7  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x1800124ee  mov     rcx, [rcx+10h]
0x1800124f2  call    WPP_SF_d
0x1800124f7  jmp     loc_180012913
0x1800124fc  test    r15, r15
0x1800124ff  cmovz   r15, r14
0x180012503  mov     ebx, 104h
0x180012508  mov     [rsp+520h+ExtCount], rbx; ExtCount
0x18001250d  lea     rax, [rbp+420h+var_250]
0x180012514  mov     [rsp+520h+Ext], rax; Ext
0x180012519  mov     [rsp+520h+FilenameCount], rbx; FilenameCount
0x18001251e  lea     rax, [rbp+420h+var_460]
0x180012522  mov     [rsp+520h+Filename], rax; Filename
0x180012527  mov     [rsp+520h+DirCount], 0; DirCount
0x180012530  xor     r9d, r9d; Dir
0x180012533  xor     r8d, r8d; DriveCount
0x180012536  xor     edx, edx; Drive
0x180012538  mov     rcx, r15; FullPath
0x18001253b  call    cs:__imp__wsplitpath_s
0x180012541  lea     r8, [rbp+420h+var_250]; unsigned __int16 *
0x180012548  mov     edx, ebx; unsigned __int64
0x18001254a  lea     rcx, [rbp+420h+var_460]; unsigned __int16 *
0x18001254e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012553  mov     rax, [rdi]
0x180012556  lea     r8, [rbp+420h+var_460]
0x18001255a  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x180012561  mov     rcx, rdi
0x180012564  mov     rax, [rax+38h]
0x180012568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001256d  mov     ebx, eax
0x18001256f  test    eax, eax
0x180012571  jns     short loc_18001259E
0x180012573  mov     rcx, cs:WPP_GLOBAL_Control
0x18001257a  lea     rdi, WPP_GLOBAL_Control
0x180012581  cmp     rcx, rdi
0x180012584  jz      loc_180012913
0x18001258a  test    byte ptr [rcx+1Ch], 2
0x18001258e  jz      loc_180012913
0x180012594  mov     edx, 4Bh ; 'K'
0x180012599  jmp     loc_1800124E4
0x18001259e  mov     rax, [rdi]
0x1800125a1  lea     r8, [rbp+420h+var_460]
0x1800125a5  lea     rdx, WPD_OBJECT_NAME
0x1800125ac  mov     rcx, rdi
0x1800125af  mov     rax, [rax+38h]
0x1800125b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b8  mov     ebx, eax
0x1800125ba  test    eax, eax
0x1800125bc  jns     short loc_1800125E9
0x1800125be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125c5  lea     rdi, WPP_GLOBAL_Control
0x1800125cc  cmp     rcx, rdi
0x1800125cf  jz      loc_180012913
0x1800125d5  test    byte ptr [rcx+1Ch], 2
0x1800125d9  jz      loc_180012913
0x1800125df  mov     edx, 4Ch ; 'L'
0x1800125e4  jmp     loc_1800124E4
0x1800125e9  test    rsi, rsi
0x1800125ec  jz      loc_1800127EE
0x1800125f2  mov     [rsp+520h+ppidlLast], 0
0x1800125fb  mov     [rsp+520h+ppv], 0
0x180012604  lea     r9, [rsp+520h+ppidlLast]; ppidlLast
0x180012609  lea     r8, [rsp+520h+ppv]; ppv
0x18001260e  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; riid
0x180012615  mov     rcx, rsi; pidl
0x180012618  call    cs:__imp_SHBindToParent
0x18001261e  mov     ebx, eax
0x180012620  test    eax, eax
0x180012622  jns     short loc_180012665
0x180012624  mov     rcx, cs:WPP_GLOBAL_Control
0x18001262b  lea     rdi, WPP_GLOBAL_Control
0x180012632  cmp     rcx, rdi
0x180012635  jz      short loc_180012656
0x180012637  test    byte ptr [rcx+1Ch], 2
0x18001263b  jz      short loc_180012656
0x18001263d  mov     edx, 4Dh ; 'M'
0x180012642  mov     r9d, eax
0x180012645  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x18001264c  mov     rcx, [rcx+10h]
0x180012650  call    WPP_SF_d
0x180012655  nop
0x180012656  lea     rcx, [rsp+520h+ppv]
0x18001265b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180012660  jmp     loc_180012913
0x180012665  mov     [rsp+520h+var_4C8], 40000000h
0x18001266d  mov     rcx, [rsp+520h+ppv]
0x180012672  mov     rax, [rcx]
0x180012675  lea     r9, [rsp+520h+var_4C8]
0x18001267a  lea     r8, [rsp+520h+ppidlLast]
0x18001267f  mov     r15d, 1
0x180012685  mov     edx, r15d
0x180012688  mov     rax, [rax+48h]
0x18001268c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012691  mov     ebx, eax
0x180012693  test    eax, eax
0x180012695  jns     short loc_1800126B6
0x180012697  mov     rcx, cs:WPP_GLOBAL_Control
0x18001269e  lea     rdi, WPP_GLOBAL_Control
0x1800126a5  cmp     rcx, rdi
0x1800126a8  jz      short loc_180012656
0x1800126aa  test    byte ptr [rcx+1Ch], 2
0x1800126ae  jz      short loc_180012656
0x1800126b0  lea     edx, [r15+4Dh]
0x1800126b4  jmp     short loc_180012642
0x1800126b6  test    [rsp+520h+var_4C8], 40000000h
0x1800126be  jz      short loc_1800126D0
0x1800126c0  mov     rcx, r14; lpFileName
0x1800126c3  call    cs:__imp_GetFileAttributesW
0x1800126c9  mov     ebx, eax
0x1800126cb  jmp     loc_180012781
0x1800126d0  xorps   xmm0, xmm0
0x1800126d3  xor     eax, eax
0x1800126d5  movups  xmmword ptr [rbp+420h+pvarg], xmm0
0x1800126d9  mov     qword ptr [rbp+420h+pvarg+10h], rax
0x1800126dd  lea     rcx, [rbp+420h+pvarg]; pvarg
0x1800126e1  call    cs:__imp_VariantInit
0x1800126e7  mov     rcx, [rsp+520h+ppv]
0x1800126ec  mov     rax, [rcx]
0x1800126ef  lea     r9, [rbp+420h+pvarg]
0x1800126f3  lea     r8, PKEY_WPDNSE_Attributes
0x1800126fa  mov     rdx, [rsp+520h+ppidlLast]
0x1800126ff  mov     rax, [rax+88h]
0x180012706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001270b  mov     ebx, eax
0x18001270d  test    eax, eax
0x18001270f  jns     short loc_18001273C
0x180012711  mov     rcx, cs:WPP_GLOBAL_Control
0x180012718  lea     rdi, WPP_GLOBAL_Control
0x18001271f  cmp     rcx, rdi
0x180012722  jz      loc_180012656
0x180012728  test    byte ptr [rcx+1Ch], 2
0x18001272c  jz      loc_180012656
0x180012732  mov     edx, 4Fh ; 'O'
0x180012737  jmp     loc_180012642
0x18001273c  xor     ebx, ebx
0x18001273e  cmp     word ptr [rbp+420h+pvarg], 13h
0x180012743  jnz     short loc_180012776
0x180012745  mov     ecx, dword ptr [rbp+420h+pvarg+8]
0x180012748  mov     ebx, ecx
0x18001274a  shr     ebx, 1
0x18001274c  mov     edx, 100h
0x180012751  and     ebx, edx
0x180012753  mov     eax, ecx
0x180012755  and     eax, 400h
0x18001275a  or      ebx, eax
0x18001275c  shr     ebx, 1
0x18001275e  mov     eax, ecx
0x180012760  and     eax, edx
0x180012762  or      ebx, eax
0x180012764  shr     ebx, 7
0x180012767  and     cl, 2
0x18001276a  neg     cl
0x18001276c  sbb     eax, eax
0x18001276e  and     eax, 0FFFFFF90h
0x180012771  sub     eax, 0FFFFFF80h
0x180012774  or      ebx, eax
0x180012776  lea     rcx, [rbp+420h+pvarg]; pvarg
0x18001277a  call    cs:__imp_VariantClear
0x180012780  nop
0x180012781  lea     rcx, [rsp+520h+ppv]
0x180012786  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001278b  test    bl, 2
0x18001278e  jz      short loc_1800127AC
0x180012790  mov     rax, [rdi]
0x180012793  mov     r8d, r15d
0x180012796  lea     rdx, WPD_OBJECT_ISHIDDEN
0x18001279d  mov     rcx, rdi
0x1800127a0  mov     rax, [rax+0B8h]
0x1800127a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ac  test    r15b, bl
0x1800127af  jz      short loc_1800127CD
0x1800127b1  mov     rax, [rdi]
0x1800127b4  xor     r8d, r8d
0x1800127b7  lea     rdx, WPD_OBJECT_CAN_DELETE
0x1800127be  mov     rcx, rdi
0x1800127c1  mov     rax, [rax+0B8h]
0x1800127c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127cd  test    bl, 4
0x1800127d0  jz      short loc_1800127EE
0x1800127d2  mov     rax, [rdi]
0x1800127d5  mov     r8d, r15d
0x1800127d8  lea     rdx, WPD_OBJECT_ISSYSTEM
0x1800127df  mov     rcx, rdi
0x1800127e2  mov     rax, [rax+0B8h]
0x1800127e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ee  lea     rcx, [rbp+420h+SystemTime]; lpSystemTime
0x1800127f2  call    cs:__imp_GetSystemTime
0x1800127f8  lea     r8, [rbp+420h+LocalTime]; lpLocalTime
0x1800127fc  lea     rdx, [rbp+420h+SystemTime]; lpUniversalTime
0x180012800  xor     ecx, ecx; lpTimeZoneInformation
0x180012802  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180012808  test    eax, eax
0x18001280a  jz      short loc_18001285F
0x18001280c  lea     rdx, [rsp+520h+pvtime+8]; pvtime
0x180012811  lea     rcx, [rbp+420h+LocalTime]; lpSystemTime
0x180012815  call    cs:__imp_SystemTimeToVariantTime
0x18001281b  test    eax, eax
0x18001281d  jz      short loc_18001285F
0x18001281f  mov     eax, 7
0x180012824  mov     word ptr [rsp+520h+pvtime], ax
0x180012829  mov     rax, [rdi]
0x18001282c  lea     r8, [rsp+520h+pvtime]
0x180012831  lea     rdx, WPD_OBJECT_DATE_CREATED
0x180012838  mov     rcx, rdi
0x18001283b  mov     rax, [rax+28h]
0x18001283f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012844  mov     rax, [rdi]
0x180012847  lea     r8, [rsp+520h+pvtime]
0x18001284c  lea     rdx, WPD_OBJECT_DATE_MODIFIED
0x180012853  mov     rcx, rdi
0x180012856  mov     rax, [rax+28h]
0x18001285a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001285f  lea     rcx, [rsp+520h+pvtime]; pvar
0x180012864  call    cs:__imp_PropVariantClear
0x18001286a  mov     rax, [rdi]
0x18001286d  lea     r8, WPD_CONTENT_TYPE_FOLDER
0x180012874  lea     rdx, WPD_OBJECT_CONTENT_TYPE
0x18001287b  mov     rcx, rdi
0x18001287e  mov     rax, [rax+0D8h]
0x180012885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001288a  mov     ebx, eax
0x18001288c  test    eax, eax
0x18001288e  jns     short loc_1800128B3
0x180012890  mov     rcx, cs:WPP_GLOBAL_Control
0x180012897  lea     rdi, WPP_GLOBAL_Control
0x18001289e  cmp     rcx, rdi
0x1800128a1  jz      short loc_180012913
0x1800128a3  test    byte ptr [rcx+1Ch], 2
0x1800128a7  jz      short loc_180012913
0x1800128a9  mov     edx, 50h ; 'P'
0x1800128ae  jmp     loc_1800124E4
0x1800128b3  mov     rax, [rdi]
0x1800128b6  lea     r8, WPD_OBJECT_FORMAT_PROPERTIES_ONLY
0x1800128bd  lea     rdx, WPD_OBJECT_FORMAT
0x1800128c4  mov     rcx, rdi
0x1800128c7  mov     rax, [rax+0D8h]
0x1800128ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128d3  mov     ebx, eax
0x1800128d5  test    eax, eax
0x1800128d7  jns     short loc_1800128FC
0x1800128d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128e0  lea     rdi, WPP_GLOBAL_Control
0x1800128e7  cmp     rcx, rdi
  ... truncated ...
```
