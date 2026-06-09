# CContentFolder::_GetObjectIDFromDisplayName(ushort *,ushort *,uint)

- ea: `0x180004a80`
- end: `0x1800050c8`
- name: `?_GetObjectIDFromDisplayName@CContentFolder@@QEAAJPEAG0I@Z`
- size: `1608`
- prototype: `__int64 __fastcall(CContentFolder *__hidden this, PCWSTR psz1, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004200`
- `0x18005d2a4`

## callees

- `0x180004110`
- `0x180004a80`
- `0x1800050d0`
- `0x1800082e0`
- `0x180016260`
- `0x1800177dc`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039d74`
- `0x180039e80`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x180004ec1`
- `SHLWAPI!StrCmpIW` at `0x180004ed3`
- `SHLWAPI!StrCmpIW` at `0x180004ec1`
- `SHLWAPI!StrCmpIW` at `0x180004ed3`
- `ole32!CoTaskMemFree` at `0x180004eeb`
- `ole32!CoTaskMemFree` at `0x180004efc`
- `ole32!CoTaskMemFree` at `0x180004f6a`
- `ole32!CoTaskMemFree` at `0x180004eeb`
- `ole32!CoTaskMemFree` at `0x180004efc`
- `ole32!CoTaskMemFree` at `0x180004f6a`
- `ole32!CoCreateInstance` at `0x180004d2f`
- `ole32!CoCreateInstance` at `0x180004d2f`
- `SHELL32!__imp_ILFindLastID` at `0x180004b75`
- `SHELL32!__imp_ILFindLastID` at `0x180004b75`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CContentFolder::_GetObjectIDFromDisplayName(CContentFolder *this, PCWSTR psz1, unsigned __int16 *a3)
{
  __int64 v5; // rcx
  int v6; // eax
  const struct _ITEMIDLIST *ID; // rax
  CContentFolder *v8; // rcx
  const struct CONTENTITEM *v9; // rax
  int ObjectID; // eax
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  HRESULT PortableDeviceProperties; // eax
  __int64 v14; // rdx
  WCHAR *v15; // r14
  WCHAR *v16; // rsi
  int v17; // ebx
  __int64 v18; // rdi
  __int64 v19; // rdi
  void *v20; // rcx
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v23; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR psz2; // [rsp+48h] [rbp-B8h] BYREF
  struct IPortableDevice *v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  struct IPortableDeviceProperties *v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v30; // [rsp+70h] [rbp-90h]
  __int128 v31; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv[10]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v33[264]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v34[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v30 = a3;
  psz2 = 0;
  memset_0(pv, 0, sizeof(pv));
  v22 = 0;
  v31 = 0;
  v26 = 0;
  v29 = 0;
  v28 = 0;
  ppv = 0;
  v23 = 0;
  v27 = 0;
  v5 = *((_QWORD *)this + 9);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)(v5 + 8) + 24LL))(v5 + 8, &v31);
    if ( v6 >= 0 )
      goto LABEL_7;
  }
  else
  {
    v6 = -2147418113;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_f4dfe53786183352449e3e96734e584d_Traceguids, (unsigned int)v6);
LABEL_7:
  ID = ILFindLastID(*((LPCITEMIDLIST *)this + 8));
  v9 = CContentFolder::_IsValid(v8, ID);
  if ( v9 )
  {
    StringCchCopyW(
      v33,
      0x104u,
      (const unsigned __int16 *)v9 + *(unsigned int *)((char *)v9 + 62) + *(unsigned int *)((char *)v9 + 66) + 37);
    ObjectID = CBaseFolder::_GetObjectID(this, v33, v34, 0x104u);
    v11 = ObjectID;
    if ( ObjectID < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_83;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_80;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        226,
        (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        (unsigned int)v33,
        ObjectID);
      goto LABEL_79;
    }
  }
  else
  {
    PortableDeviceProperties = (*(__int64 (__fastcall **)(CContentFolder *, _QWORD, unsigned __int16 *, __int64))(*(_QWORD *)this + 88LL))(
                                 this,
                                 *((_QWORD *)this + 8),
                                 v34,
                                 260);
    v11 = PortableDeviceProperties;
    if ( PortableDeviceProperties < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_83;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_80;
      v14 = 227;
      goto LABEL_16;
    }
  }
  PortableDeviceProperties = (*(__int64 (__fastcall **)(CContentFolder *, _QWORD, struct IPortableDevice **))(*(_QWORD *)this + 136LL))(
                               this,
                               *((_QWORD *)this + 8),
                               &v26);
  v11 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_83;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_80;
    v14 = 228;
    goto LABEL_16;
  }
  PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v26->lpVtbl->Content)(
                               v26,
                               &v29);
  v11 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_83;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_80;
    v14 = 229;
    goto LABEL_16;
  }
  PortableDeviceProperties = GetPortableDeviceProperties(v26, &v28);
  v11 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_83;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_80;
    v14 = 230;
    goto LABEL_16;
  }
  PortableDeviceProperties = CoCreateInstance(
                               &CLSID_PortableDeviceKeyCollection,
                               0,
                               1u,
                               &GUID_dada2357_e0ad_492e_98db_dd61c53ba353,
                               &ppv);
  v11 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_83;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_80;
    v14 = 231;
    goto LABEL_16;
  }
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_NAME);
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_ORIGINAL_FILE_NAME);
  PortableDeviceProperties = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, _QWORD, __int64 *))(*(_QWORD *)v29 + 24LL))(
                               v29,
                               0,
                               v34,
                               0,
                               &v27);
  v11 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_83;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_80;
    v14 = 232;
LABEL_16:
    WPP_SF_d(v12[2], v14, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)PortableDeviceProperties);
    goto LABEL_79;
  }
  v15 = 0;
  v16 = 0;
  v17 = 0;
  while ( 1 )
  {
    if ( (*(int (__fastcall **)(__int64, __int64, LPVOID *, unsigned int *))(*(_QWORD *)v27 + 24LL))(v27, 10, pv, &v22) < 0 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_76;
    }
    if ( !v22 )
      break;
    v18 = 0;
    while ( 1 )
    {
      if ( pv[v18] )
      {
        if ( v23 )
          ATL::AtlComPtrAssign(&v23, 0);
        if ( ((int (__fastcall *)(struct IPortableDeviceProperties *, LPVOID, LPVOID, struct IUnknown **))v28->lpVtbl->GetValues)(
               v28,
               pv[v18],
               ppv,
               &v23) >= 0 )
        {
          if ( ((int (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, PCWSTR *))v23->lpVtbl[2].Release)(
                 v23,
                 &WPD_OBJECT_NAME,
                 &psz2) >= 0 )
            v15 = (WCHAR *)psz2;
          if ( ((int (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, PCWSTR *))v23->lpVtbl[2].Release)(
                 v23,
                 &WPD_OBJECT_ORIGINAL_FILE_NAME,
                 &psz2) >= 0 )
            v16 = (WCHAR *)psz2;
          if ( v16 )
          {
            if ( !StrCmpIW(psz1, v16) )
              v17 = 1;
          }
          else if ( !StrCmpIW(psz1, v15) )
          {
            v17 = 1;
          }
          if ( v15 )
          {
            CoTaskMemFree(v15);
            v15 = 0;
          }
          if ( v16 )
          {
            CoTaskMemFree(v16);
            v16 = 0;
          }
          if ( v17 )
            break;
        }
      }
      v18 = (unsigned int)(v18 + 1);
      if ( (unsigned int)v18 >= v22 )
        goto LABEL_62;
    }
    StringCchCopyW(v30, 0x104u, (const unsigned __int16 *)pv[v18]);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, psz1);
LABEL_62:
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    v19 = 0;
    if ( v22 )
    {
      do
      {
        v20 = pv[v19];
        if ( v20 )
        {
          CoTaskMemFree(v20);
          pv[v19] = 0;
        }
        v19 = (unsigned int)(v19 + 1);
      }
      while ( (unsigned int)v19 < v22 );
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v17 )
      goto LABEL_73;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_73:
  if ( v17 == 1 )
  {
    v11 = 0;
    goto LABEL_83;
  }
LABEL_76:
  v11 = -2147024894;
  if ( v12 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v12 + 28) & 2) == 0 )
    {
LABEL_80:
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
        WPP_SF_d(v12[2], 236, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v11);
      goto LABEL_83;
    }
    WPP_SF_Sd((unsigned int)v12[2], 235, (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (_DWORD)psz1, 2);
LABEL_79:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_80;
  }
LABEL_83:
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v23 )
    ((void (__fastcall *)(struct IUnknown *))v23->lpVtbl->Release)(v23);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v28 )
    ((void (__fastcall *)(struct IPortableDeviceProperties *))v28->lpVtbl->Release)(v28);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v26 )
    ((void (__fastcall *)(struct IPortableDevice *))v26->lpVtbl->Release)(v26);
  return v11;
}

```

## disassembly

```asm
0x180004a80  push    rbp
0x180004a82  push    rbx
0x180004a83  push    rsi
0x180004a84  push    rdi
0x180004a85  push    r13
0x180004a87  push    r14
0x180004a89  push    r15
0x180004a8b  lea     rbp, [rsp-410h]
0x180004a93  sub     rsp, 510h
0x180004a9a  mov     rax, cs:__security_cookie
0x180004aa1  xor     rax, rsp
0x180004aa4  mov     [rbp+440h+var_40], rax
0x180004aab  mov     [rsp+540h+var_4D0], r8
0x180004ab0  mov     r13, rdx
0x180004ab3  mov     rdi, rcx
0x180004ab6  mov     [rsp+540h+psz2], 0
0x180004abf  xor     edx, edx; Val
0x180004ac1  lea     r8d, [rdx+50h]; Size
0x180004ac5  lea     rcx, [rbp+440h+pv]; void *
0x180004ac9  call    memset_0
0x180004ace  mov     [rsp+540h+var_510], 0
0x180004ad6  xorps   xmm0, xmm0
0x180004ad9  movups  [rsp+540h+var_4C8], xmm0
0x180004ade  mov     [rsp+540h+var_4F0], 0
0x180004ae7  mov     [rsp+540h+var_4D8], 0
0x180004af0  mov     [rsp+540h+var_4E0], 0
0x180004af9  mov     [rsp+540h+var_500], 0
0x180004b02  mov     [rsp+540h+var_508], 0
0x180004b0b  mov     [rsp+540h+var_4E8], 0
0x180004b14  mov     rcx, [rdi+48h]
0x180004b18  mov     sil, 2
0x180004b1b  lea     r15, WPP_GLOBAL_Control
0x180004b22  test    rcx, rcx
0x180004b25  jnz     short loc_180004B2E
0x180004b27  mov     eax, 8000FFFFh
0x180004b2c  jmp     short loc_180004B47
0x180004b2e  add     rcx, 8
0x180004b32  mov     rax, [rcx]
0x180004b35  lea     rdx, [rsp+540h+var_4C8]
0x180004b3a  mov     rax, [rax+18h]
0x180004b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b43  test    eax, eax
0x180004b45  jns     short loc_180004B71
0x180004b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b4e  cmp     rcx, r15
0x180004b51  jz      short loc_180004B71
0x180004b53  test    [rcx+1Ch], sil
0x180004b57  jz      short loc_180004B71
0x180004b59  mov     edx, 31h ; '1'
0x180004b5e  mov     r9d, eax
0x180004b61  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x180004b68  mov     rcx, [rcx+10h]
0x180004b6c  call    WPP_SF_d
0x180004b71  mov     rcx, [rdi+40h]; pidl
0x180004b75  call    cs:__imp_ILFindLastID
0x180004b7b  mov     rdx, rax; struct _ITEMIDLIST *
0x180004b7e  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180004b83  lea     r14, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180004b8a  test    rax, rax
0x180004b8d  jz      short loc_180004BFD
0x180004b8f  mov     edx, [rax+42h]
0x180004b92  mov     ecx, [rax+3Eh]
0x180004b95  add     rcx, 25h ; '%'
0x180004b99  add     rdx, rcx
0x180004b9c  lea     r8, [rax+rdx*2]; unsigned __int16 *
0x180004ba0  mov     edx, 104h; unsigned __int64
0x180004ba5  lea     rcx, [rbp+440h+var_460]; unsigned __int16 *
0x180004ba9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004bae  mov     r9d, 104h; unsigned int
0x180004bb4  lea     r8, [rbp+440h+var_250]; unsigned __int16 *
0x180004bbb  lea     rdx, [rbp+440h+var_460]; unsigned __int16 *
0x180004bbf  mov     rcx, rdi; this
0x180004bc2  call    ?_GetObjectID@CBaseFolder@@QEAAJPEBGPEAGI@Z; CBaseFolder::_GetObjectID(ushort const *,ushort *,uint)
0x180004bc7  mov     ebx, eax
0x180004bc9  test    eax, eax
0x180004bcb  jns     loc_180004C56
0x180004bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bd8  cmp     rcx, r15
0x180004bdb  jz      loc_18000501B
0x180004be1  test    [rcx+1Ch], sil
0x180004be5  jz      loc_180004FFB
0x180004beb  mov     edx, 0E2h
0x180004bf0  mov     dword ptr [rsp+540h+ppv], eax
0x180004bf4  lea     r9, [rbp+440h+var_460]
0x180004bf8  jmp     loc_180004FE8
0x180004bfd  mov     rax, [rdi]
0x180004c00  mov     r9d, 104h
0x180004c06  lea     r8, [rbp+440h+var_250]
0x180004c0d  mov     rdx, [rdi+40h]
0x180004c11  mov     rcx, rdi
0x180004c14  mov     rax, [rax+58h]
0x180004c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1d  mov     ebx, eax
0x180004c1f  test    eax, eax
0x180004c21  jns     short loc_180004C56
0x180004c23  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c2a  cmp     rcx, r15
0x180004c2d  jz      loc_18000501B
0x180004c33  test    [rcx+1Ch], sil
0x180004c37  jz      loc_180004FFB
0x180004c3d  mov     edx, 0E3h
0x180004c42  mov     r9d, eax
0x180004c45  mov     r8, r14
0x180004c48  mov     rcx, [rcx+10h]
0x180004c4c  call    WPP_SF_d
0x180004c51  jmp     loc_180004FF4
0x180004c56  mov     rax, [rdi]
0x180004c59  lea     r8, [rsp+540h+var_4F0]
0x180004c5e  mov     rdx, [rdi+40h]
0x180004c62  mov     rcx, rdi
0x180004c65  mov     rax, [rax+88h]
0x180004c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c71  mov     ebx, eax
0x180004c73  test    eax, eax
0x180004c75  jns     short loc_180004C98
0x180004c77  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c7e  cmp     rcx, r15
0x180004c81  jz      loc_18000501B
0x180004c87  test    [rcx+1Ch], sil
0x180004c8b  jz      loc_180004FFB
0x180004c91  mov     edx, 0E4h
0x180004c96  jmp     short loc_180004C42
0x180004c98  mov     rcx, [rsp+540h+var_4F0]
0x180004c9d  mov     rax, [rcx]
0x180004ca0  lea     rdx, [rsp+540h+var_4D8]
0x180004ca5  mov     rax, [rax+28h]
0x180004ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cae  mov     ebx, eax
0x180004cb0  test    eax, eax
0x180004cb2  jns     short loc_180004CD8
0x180004cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cbb  cmp     rcx, r15
0x180004cbe  jz      loc_18000501B
0x180004cc4  test    [rcx+1Ch], sil
0x180004cc8  jz      loc_180004FFB
0x180004cce  mov     edx, 0E5h
0x180004cd3  jmp     loc_180004C42
0x180004cd8  lea     rdx, [rsp+540h+var_4E0]; struct IPortableDeviceProperties **
0x180004cdd  mov     rcx, [rsp+540h+var_4F0]; struct IPortableDevice *
0x180004ce2  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180004ce7  mov     ebx, eax
0x180004ce9  test    eax, eax
0x180004ceb  jns     short loc_180004D11
0x180004ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cf4  cmp     rcx, r15
0x180004cf7  jz      loc_18000501B
0x180004cfd  test    [rcx+1Ch], sil
0x180004d01  jz      loc_180004FFB
0x180004d07  mov     edx, 0E6h
0x180004d0c  jmp     loc_180004C42
0x180004d11  lea     rax, [rsp+540h+var_500]
0x180004d16  mov     [rsp+540h+ppv], rax; ppv
0x180004d1b  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x180004d22  xor     edx, edx; pUnkOuter
0x180004d24  lea     r8d, [rdx+1]; dwClsContext
0x180004d28  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x180004d2f  call    cs:__imp_CoCreateInstance
0x180004d35  mov     ebx, eax
0x180004d37  test    eax, eax
0x180004d39  jns     short loc_180004D5F
0x180004d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d42  cmp     rcx, r15
0x180004d45  jz      loc_18000501B
0x180004d4b  test    [rcx+1Ch], sil
0x180004d4f  jz      loc_180004FFB
0x180004d55  mov     edx, 0E7h
0x180004d5a  jmp     loc_180004C42
0x180004d5f  mov     rcx, [rsp+540h+var_500]
0x180004d64  mov     rax, [rcx]
0x180004d67  lea     rdx, WPD_OBJECT_NAME
0x180004d6e  mov     rax, [rax+28h]
0x180004d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d77  mov     rcx, [rsp+540h+var_500]
0x180004d7c  mov     rax, [rcx]
0x180004d7f  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x180004d86  mov     rax, [rax+28h]
0x180004d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d8f  mov     rcx, [rsp+540h+var_4D8]
0x180004d94  mov     rax, [rcx]
0x180004d97  lea     rdx, [rsp+540h+var_4E8]
0x180004d9c  mov     [rsp+540h+ppv], rdx
0x180004da1  xor     r9d, r9d
0x180004da4  lea     r8, [rbp+440h+var_250]
0x180004dab  xor     edx, edx
0x180004dad  mov     rax, [rax+18h]
0x180004db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db6  mov     ebx, eax
0x180004db8  test    eax, eax
0x180004dba  jns     short loc_180004DE0
0x180004dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dc3  cmp     rcx, r15
0x180004dc6  jz      loc_18000501B
0x180004dcc  test    [rcx+1Ch], sil
0x180004dd0  jz      loc_180004FFB
0x180004dd6  mov     edx, 0E8h
0x180004ddb  jmp     loc_180004C42
0x180004de0  xor     r14d, r14d
0x180004de3  xor     esi, esi
0x180004de5  xor     ebx, ebx
0x180004de7  mov     rcx, [rsp+540h+var_4E8]
0x180004dec  mov     rax, [rcx]
0x180004def  lea     r9, [rsp+540h+var_510]
0x180004df4  lea     r8, [rbp+440h+pv]
0x180004df8  mov     edx, 0Ah
0x180004dfd  mov     rax, [rax+18h]
0x180004e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e06  test    eax, eax
0x180004e08  js      loc_180004FB4
0x180004e0e  mov     eax, [rsp+540h+var_510]
0x180004e12  test    eax, eax
0x180004e14  jz      loc_180004FA4
0x180004e1a  xor     edi, edi
0x180004e1c  test    eax, eax
0x180004e1e  jz      loc_180004F51
0x180004e24  cmp     [rbp+rdi*8+440h+pv], 0
0x180004e2a  jz      loc_180004F92
0x180004e30  cmp     [rsp+540h+var_508], 0
0x180004e36  jz      short loc_180004E44
0x180004e38  xor     edx, edx; struct IUnknown *
0x180004e3a  lea     rcx, [rsp+540h+var_508]; struct IUnknown **
0x180004e3f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180004e44  mov     rcx, [rsp+540h+var_4E0]
0x180004e49  mov     rax, [rcx]
0x180004e4c  lea     r9, [rsp+540h+var_508]
0x180004e51  mov     r8, [rsp+540h+var_500]
0x180004e56  mov     rdx, [rbp+rdi*8+440h+pv]
0x180004e5b  mov     rax, [rax+28h]
0x180004e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e64  test    eax, eax
0x180004e66  js      loc_180004F92
0x180004e6c  mov     rcx, [rsp+540h+var_508]
0x180004e71  mov     rax, [rcx]
0x180004e74  lea     r8, [rsp+540h+psz2]
0x180004e79  lea     rdx, WPD_OBJECT_NAME
0x180004e80  mov     rax, [rax+40h]
0x180004e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e89  test    eax, eax
0x180004e8b  cmovns  r14, [rsp+540h+psz2]
0x180004e91  mov     rcx, [rsp+540h+var_508]
0x180004e96  mov     rax, [rcx]
0x180004e99  lea     r8, [rsp+540h+psz2]
0x180004e9e  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x180004ea5  mov     rax, [rax+40h]
0x180004ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eae  test    eax, eax
0x180004eb0  cmovns  rsi, [rsp+540h+psz2]
0x180004eb6  mov     rcx, r13; psz1
0x180004eb9  test    rsi, rsi
0x180004ebc  jz      short loc_180004ED0
0x180004ebe  mov     rdx, rsi; psz2
0x180004ec1  call    cs:__imp_StrCmpIW
0x180004ec7  test    eax, eax
0x180004ec9  jnz     short loc_180004EE3
0x180004ecb  lea     ebx, [rax+1]
0x180004ece  jmp     short loc_180004EE3
0x180004ed0  mov     rdx, r14; psz2
0x180004ed3  call    cs:__imp_StrCmpIW
0x180004ed9  test    eax, eax
0x180004edb  mov     eax, 1
0x180004ee0  cmovz   ebx, eax
0x180004ee3  test    r14, r14
0x180004ee6  jz      short loc_180004EF4
0x180004ee8  mov     rcx, r14; pv
0x180004eeb  call    cs:__imp_CoTaskMemFree
0x180004ef1  xor     r14d, r14d
0x180004ef4  test    rsi, rsi
0x180004ef7  jz      short loc_180004F04
0x180004ef9  mov     rcx, rsi; pv
0x180004efc  call    cs:__imp_CoTaskMemFree
0x180004f02  xor     esi, esi
0x180004f04  test    ebx, ebx
0x180004f06  jz      loc_180004F96
0x180004f0c  mov     r8, [rbp+rdi*8+440h+pv]; unsigned __int16 *
0x180004f11  mov     edx, 104h; unsigned __int64
0x180004f16  mov     rcx, [rsp+540h+var_4D0]; unsigned __int16 *
0x180004f1b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f27  lea     rax, WPP_GLOBAL_Control
0x180004f2e  cmp     rcx, rax
0x180004f31  jz      short loc_180004F58
0x180004f33  test    byte ptr [rcx+1Ch], 40h
0x180004f37  jz      short loc_180004F58
0x180004f39  mov     edx, 0E9h
0x180004f3e  mov     r9, r13
0x180004f41  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180004f48  mov     rcx, [rcx+10h]
0x180004f4c  call    WPP_SF_S
0x180004f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f58  xor     edi, edi
0x180004f5a  cmp     [rsp+540h+var_510], edi
0x180004f5e  jbe     short loc_180004F88
0x180004f60  mov     rcx, [rbp+rdi*8+440h+pv]; pv
0x180004f65  test    rcx, rcx
0x180004f68  jz      short loc_180004F79
0x180004f6a  call    cs:__imp_CoTaskMemFree
0x180004f70  mov     [rbp+rdi*8+440h+pv], 0
0x180004f79  inc     edi
0x180004f7b  cmp     edi, [rsp+540h+var_510]
0x180004f7f  jb      short loc_180004F60
0x180004f81  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
