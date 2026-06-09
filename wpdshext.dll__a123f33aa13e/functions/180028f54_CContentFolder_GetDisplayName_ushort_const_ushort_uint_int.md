# CContentFolder::_GetDisplayName(ushort const *,ushort *,uint,int *)

- ea: `0x180028f54`
- end: `0x1800292e6`
- name: `?_GetDisplayName@CContentFolder@@AEAAJPEBGPEAGIPEAH@Z`
- size: `914`
- prototype: `int(CContentFolder *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016780`
- `0x18003c074`
- `0x18003cce4`

## callees

- `0x180004110`
- `0x180016260`
- `0x180028f54`
- `0x18002ff5c`
- `0x180035590`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `SHLWAPI!PathRemoveExtensionW` at `0x180029268`
- `SHLWAPI!PathRemoveExtensionW` at `0x180029268`
- `ole32!CoTaskMemFree` at `0x1800291ef`
- `ole32!CoTaskMemFree` at `0x1800291ef`
- `ole32!CoCreateInstance` at `0x18002908d`
- `ole32!CoCreateInstance` at `0x18002908d`
- `SHELL32!SHGetSettings` at `0x180028fca`
- `SHELL32!SHGetSettings` at `0x180028fca`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CContentFolder::_GetDisplayName(
        CContentFolder *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        int *a5)
{
  struct IPortableDeviceProperties *v8; // rbx
  int v9; // r15d
  int v10; // eax
  unsigned int v11; // edi
  PVOID *v12; // rcx
  __int64 v13; // rdx
  HRESULT PortableDeviceProperties; // eax
  __int64 v15; // rdx
  LPVOID ppv; // [rsp+30h] [rbp-50h] BYREF
  SHELLFLAGSTATE psfs; // [rsp+38h] [rbp-48h] BYREF
  struct IPortableDeviceProperties *v19; // [rsp+40h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-38h] BYREF
  __int64 v21; // [rsp+50h] [rbp-30h] BYREF
  struct IPortableDevice *v22; // [rsp+58h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-20h] BYREF

  psfs = 0;
  Buf1 = 0;
  pv = 0;
  v22 = 0;
  v21 = 0;
  v8 = 0;
  v19 = 0;
  ppv = 0;
  *a3 = 0;
  if ( a5 )
    *a5 = 0;
  SHGetSettings(&psfs, 2u);
  v9 = *(_DWORD *)&psfs << 30;
  v10 = (*(__int64 (__fastcall **)(CContentFolder *, _QWORD, struct IPortableDevice **))(*(_QWORD *)this + 136LL))(
          this,
          *((_QWORD *)this + 8),
          &v22);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v13 = 261;
    goto LABEL_21;
  }
  PortableDeviceProperties = GetPortableDeviceProperties(v22, &v19);
  v11 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 262;
LABEL_11:
      WPP_SF_d(v12[2], v15, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)PortableDeviceProperties);
      v8 = v19;
LABEL_22:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_23;
    }
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
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 263;
      goto LABEL_11;
    }
LABEL_16:
    v8 = v19;
LABEL_23:
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      WPP_SF_d(v12[2], 265, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v11);
    goto LABEL_37;
  }
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_NAME);
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_ORIGINAL_FILE_NAME);
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_CONTENT_TYPE);
  v8 = v19;
  v10 = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const unsigned __int16 *, LPVOID, __int64 *))v19->lpVtbl->GetValues)(
          v19,
          a2,
          ppv,
          &v21);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_23;
    v13 = 264;
LABEL_21:
    WPP_SF_d(v12[2], v13, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v10);
    goto LABEL_22;
  }
  if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPVOID *))(*(_QWORD *)v21 + 64LL))(
         v21,
         &WPD_OBJECT_ORIGINAL_FILE_NAME,
         &pv) >= 0
    || (*(int (__fastcall **)(__int64, const PROPERTYKEY *, LPVOID *))(*(_QWORD *)v21 + 64LL))(
         v21,
         &WPD_OBJECT_NAME,
         &pv) >= 0 )
  {
    StringCchCopyW(a3, 0x104u, (const unsigned __int16 *)pv);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
  }
  if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v21 + 224LL))(
         v21,
         &WPD_OBJECT_CONTENT_TYPE,
         &Buf1) >= 0
    && (!memcmp_0(&Buf1, &WPD_CONTENT_TYPE_FOLDER, 0x10u) || !memcmp_0(
                                                                &Buf1,
                                                                &WPD_CONTENT_TYPE_FUNCTIONAL_OBJECT,
                                                                0x10u)) )
  {
    if ( a5 )
      *a5 = 1;
  }
  else if ( v9 >= 0 )
  {
    PathRemoveExtensionW(a3);
  }
LABEL_37:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 )
    ((void (__fastcall *)(struct IPortableDeviceProperties *))v8->lpVtbl->Release)(v8);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v22 )
    ((void (__fastcall *)(struct IPortableDevice *))v22->lpVtbl->Release)(v22);
  return v11;
}

```

## disassembly

```asm
0x180028f54  push    rbp
0x180028f56  push    rbx
0x180028f57  push    rsi
0x180028f58  push    rdi
0x180028f59  push    r12
0x180028f5b  push    r14
0x180028f5d  push    r15
0x180028f5f  mov     rbp, rsp
0x180028f62  sub     rsp, 80h
0x180028f69  mov     rax, cs:__security_cookie
0x180028f70  xor     rax, rsp
0x180028f73  mov     [rbp+var_10], rax
0x180028f77  mov     r14, r8
0x180028f7a  mov     r12, rdx
0x180028f7d  mov     rdi, rcx
0x180028f80  mov     rsi, [rbp+arg_20]
0x180028f84  mov     dword ptr [rbp+psfs.fShowAllObjects], 0
0x180028f8b  xorps   xmm0, xmm0
0x180028f8e  movups  [rbp+Buf1], xmm0
0x180028f92  mov     [rbp+pv], 0
0x180028f9a  mov     [rbp+var_28], 0
0x180028fa2  mov     [rbp+var_30], 0
0x180028faa  xor     ebx, ebx
0x180028fac  mov     [rbp+var_40], rbx
0x180028fb0  mov     [rbp+var_50], rbx
0x180028fb4  xor     eax, eax
0x180028fb6  mov     [r8], ax
0x180028fba  test    rsi, rsi
0x180028fbd  jz      short loc_180028FC1
0x180028fbf  mov     [rsi], eax
0x180028fc1  mov     edx, 2; dwMask
0x180028fc6  lea     rcx, [rbp+psfs]; psfs
0x180028fca  call    cs:__imp_SHGetSettings
0x180028fd0  mov     r15d, dword ptr [rbp+psfs.fShowAllObjects]
0x180028fd4  shl     r15d, 1Eh
0x180028fd8  mov     rax, [rdi]
0x180028fdb  lea     r8, [rbp+var_28]
0x180028fdf  mov     rdx, [rdi+40h]
0x180028fe3  mov     rcx, rdi
0x180028fe6  mov     rax, [rax+88h]
0x180028fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ff2  mov     edi, eax
0x180028ff4  test    eax, eax
0x180028ff6  jns     short loc_180029023
0x180028ff8  lea     rsi, WPP_GLOBAL_Control
0x180028fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180029006  cmp     rcx, rsi
0x180029009  jz      loc_18002926F
0x18002900f  test    byte ptr [rcx+1Ch], 2
0x180029013  jz      loc_180029167
0x180029019  mov     edx, 105h
0x18002901e  jmp     loc_18002914D
0x180029023  lea     rdx, [rbp+var_40]; struct IPortableDeviceProperties **
0x180029027  mov     rcx, [rbp+var_28]; struct IPortableDevice *
0x18002902b  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180029030  mov     edi, eax
0x180029032  test    eax, eax
0x180029034  jns     short loc_180029070
0x180029036  lea     rsi, WPP_GLOBAL_Control
0x18002903d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029044  cmp     rcx, rsi
0x180029047  jz      short loc_1800290B9
0x180029049  test    byte ptr [rcx+1Ch], 2
0x18002904d  jz      short loc_1800290B9
0x18002904f  mov     edx, 106h
0x180029054  mov     r9d, eax
0x180029057  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18002905e  mov     rcx, [rcx+10h]
0x180029062  call    WPP_SF_d
0x180029067  mov     rbx, [rbp+var_40]
0x18002906b  jmp     loc_180029160
0x180029070  lea     rax, [rbp+var_50]
0x180029074  mov     [rsp+80h+ppv], rax; ppv
0x180029079  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x180029080  xor     edx, edx; pUnkOuter
0x180029082  lea     r8d, [rdx+1]; dwClsContext
0x180029086  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x18002908d  call    cs:__imp_CoCreateInstance
0x180029093  mov     edi, eax
0x180029095  test    eax, eax
0x180029097  jns     short loc_1800290C2
0x180029099  lea     rsi, WPP_GLOBAL_Control
0x1800290a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290a7  cmp     rcx, rsi
0x1800290aa  jz      short loc_1800290B9
0x1800290ac  test    byte ptr [rcx+1Ch], 2
0x1800290b0  jz      short loc_1800290B9
0x1800290b2  mov     edx, 107h
0x1800290b7  jmp     short loc_180029054
0x1800290b9  mov     rbx, [rbp+var_40]
0x1800290bd  jmp     loc_180029167
0x1800290c2  mov     rcx, [rbp+var_50]
0x1800290c6  mov     rax, [rcx]
0x1800290c9  lea     rdx, WPD_OBJECT_NAME
0x1800290d0  mov     rax, [rax+28h]
0x1800290d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290d9  mov     rcx, [rbp+var_50]
0x1800290dd  mov     rax, [rcx]
0x1800290e0  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x1800290e7  mov     rax, [rax+28h]
0x1800290eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290f0  mov     rcx, [rbp+var_50]
0x1800290f4  mov     rax, [rcx]
0x1800290f7  lea     rdx, WPD_OBJECT_CONTENT_TYPE
0x1800290fe  mov     rax, [rax+28h]
0x180029102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029107  mov     rbx, [rbp+var_40]
0x18002910b  mov     rax, [rbx]
0x18002910e  lea     r9, [rbp+var_30]
0x180029112  mov     r8, [rbp+var_50]
0x180029116  mov     rdx, r12
0x180029119  mov     rcx, rbx
0x18002911c  mov     rax, [rax+28h]
0x180029120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029125  mov     edi, eax
0x180029127  test    eax, eax
0x180029129  jns     short loc_180029197
0x18002912b  lea     rsi, WPP_GLOBAL_Control
0x180029132  mov     rcx, cs:WPP_GLOBAL_Control
0x180029139  cmp     rcx, rsi
0x18002913c  jz      loc_18002926F
0x180029142  test    byte ptr [rcx+1Ch], 2
0x180029146  jz      short loc_180029167
0x180029148  mov     edx, 108h
0x18002914d  mov     r9d, eax
0x180029150  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180029157  mov     rcx, [rcx+10h]
0x18002915b  call    WPP_SF_d
0x180029160  mov     rcx, cs:WPP_GLOBAL_Control
0x180029167  cmp     rcx, rsi
0x18002916a  jz      loc_18002926F
0x180029170  test    byte ptr [rcx+1Ch], 2
0x180029174  jz      loc_18002926F
0x18002917a  mov     edx, 109h
0x18002917f  mov     r9d, edi
0x180029182  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180029189  mov     rcx, [rcx+10h]
0x18002918d  call    WPP_SF_d
0x180029192  jmp     loc_18002926F
0x180029197  mov     rcx, [rbp+var_30]
0x18002919b  mov     rax, [rcx]
0x18002919e  lea     r8, [rbp+pv]
0x1800291a2  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x1800291a9  mov     rax, [rax+40h]
0x1800291ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291b2  test    eax, eax
0x1800291b4  jns     short loc_1800291D5
0x1800291b6  mov     rcx, [rbp+var_30]
0x1800291ba  mov     rax, [rcx]
0x1800291bd  lea     r8, [rbp+pv]
0x1800291c1  lea     rdx, WPD_OBJECT_NAME
0x1800291c8  mov     rax, [rax+40h]
0x1800291cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291d1  test    eax, eax
0x1800291d3  js      short loc_1800291FD
0x1800291d5  mov     r8, [rbp+pv]; unsigned __int16 *
0x1800291d9  mov     edx, 104h; unsigned __int64
0x1800291de  mov     rcx, r14; unsigned __int16 *
0x1800291e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800291e6  mov     rcx, [rbp+pv]; pv
0x1800291ea  test    rcx, rcx
0x1800291ed  jz      short loc_1800291FD
0x1800291ef  call    cs:__imp_CoTaskMemFree
0x1800291f5  mov     [rbp+pv], 0
0x1800291fd  mov     rcx, [rbp+var_30]
0x180029201  mov     rax, [rcx]
0x180029204  lea     r8, [rbp+Buf1]
0x180029208  lea     rdx, WPD_OBJECT_CONTENT_TYPE
0x18002920f  mov     rax, [rax+0E0h]
0x180029216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002921b  test    eax, eax
0x18002921d  js      short loc_180029260
0x18002921f  mov     r12d, 10h
0x180029225  mov     r8d, r12d; Size
0x180029228  lea     rdx, WPD_CONTENT_TYPE_FOLDER; Buf2
0x18002922f  lea     rcx, [rbp+Buf1]; Buf1
0x180029233  call    memcmp_0
0x180029238  test    eax, eax
0x18002923a  jz      short loc_180029253
0x18002923c  mov     r8d, r12d; Size
0x18002923f  lea     rdx, WPD_CONTENT_TYPE_FUNCTIONAL_OBJECT; Buf2
0x180029246  lea     rcx, [rbp+Buf1]; Buf1
0x18002924a  call    memcmp_0
0x18002924f  test    eax, eax
0x180029251  jnz     short loc_180029260
0x180029253  test    rsi, rsi
0x180029256  jz      short loc_18002926F
0x180029258  mov     dword ptr [rsi], 1
0x18002925e  jmp     short loc_18002926F
0x180029260  test    r15d, r15d
0x180029263  js      short loc_18002926F
0x180029265  mov     rcx, r14; pszPath
0x180029268  call    cs:__imp_PathRemoveExtensionW
0x18002926e  nop
0x18002926f  mov     rcx, [rbp+var_50]
0x180029273  test    rcx, rcx
0x180029276  jz      short loc_180029285
0x180029278  mov     rax, [rcx]
0x18002927b  mov     rax, [rax+10h]
0x18002927f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029284  nop
0x180029285  test    rbx, rbx
0x180029288  jz      short loc_18002929A
0x18002928a  mov     rax, [rbx]
0x18002928d  mov     rcx, rbx
0x180029290  mov     rax, [rax+10h]
0x180029294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029299  nop
0x18002929a  mov     rcx, [rbp+var_30]
0x18002929e  test    rcx, rcx
0x1800292a1  jz      short loc_1800292B0
0x1800292a3  mov     rax, [rcx]
0x1800292a6  mov     rax, [rax+10h]
0x1800292aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292af  nop
0x1800292b0  mov     rcx, [rbp+var_28]
0x1800292b4  test    rcx, rcx
0x1800292b7  jz      short loc_1800292C6
0x1800292b9  mov     rax, [rcx]
0x1800292bc  mov     rax, [rax+10h]
0x1800292c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292c5  nop
0x1800292c6  mov     eax, edi
0x1800292c8  mov     rcx, [rbp+var_10]
0x1800292cc  xor     rcx, rsp; StackCookie
0x1800292cf  call    __security_check_cookie
0x1800292d4  add     rsp, 80h
0x1800292db  pop     r15
0x1800292dd  pop     r14
0x1800292df  pop     r12
0x1800292e1  pop     rdi
0x1800292e2  pop     rsi
0x1800292e3  pop     rbx
0x1800292e4  pop     rbp
0x1800292e5  retn
```
