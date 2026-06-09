# CDeviceFolder::_ParseShServiceObjectEvent(_ITEMIDLIST *,ushort const *,ushort *,uint)

- ea: `0x180023c34`
- end: `0x180024414`
- name: `?_ParseShServiceObjectEvent@CDeviceFolder@@AEAAJPEFAU_ITEMIDLIST@@PEBGPEAGI@Z`
- size: `2016`
- prototype: `__int64 __fastcall(CDeviceFolder *__hidden this, struct _ITEMIDLIST *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d9b0`

## callees

- `0x180004110`
- `0x180007860`
- `0x1800177dc`
- `0x180023c34`
- `0x18002ab58`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180075530`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x180023d2e`
- `SHLWAPI!StrCmpW` at `0x180024131`
- `SHLWAPI!StrCmpW` at `0x180023d2e`
- `SHLWAPI!StrCmpW` at `0x180024131`
- `ole32!CoTaskMemFree` at `0x1800240b7`
- `ole32!CoTaskMemFree` at `0x1800240f3`
- `ole32!CoTaskMemFree` at `0x1800241e2`
- `ole32!CoTaskMemFree` at `0x1800241f7`
- `ole32!CoTaskMemFree` at `0x1800240b7`
- `ole32!CoTaskMemFree` at `0x1800240f3`
- `ole32!CoTaskMemFree` at `0x1800241e2`
- `ole32!CoTaskMemFree` at `0x1800241f7`
- `ole32!PropVariantClear` at `0x1800241d2`
- `ole32!PropVariantClear` at `0x1800241d2`
- `ole32!CoCreateInstance` at `0x180023e6b`
- `ole32!CoCreateInstance` at `0x180023f6d`
- `ole32!CoCreateInstance` at `0x180023e6b`
- `ole32!CoCreateInstance` at `0x180023f6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CDeviceFolder::_ParseShServiceObjectEvent(
        CDeviceFolder *this,
        struct _ITEMIDLIST *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int v8; // ebx
  int v9; // edi
  const unsigned __int16 *v10; // rsi
  CDeviceFolder *v11; // rcx
  const struct DEVICEITEM *v12; // rax
  HRESULT v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  LARGE_INTEGER hVal; // rdx
  struct IUnknown *v19; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v21; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  __int128 v28; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+88h] [rbp-78h]
  PROPVARIANT pvar; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v31[2080]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v32[2080]; // [rsp+10F0h] [rbp+FF0h] BYREF

  v27 = 0;
  v19 = 0;
  v25 = 0;
  v23 = 0;
  ppv = 0;
  v24 = 0;
  v26 = 0;
  pv = 0;
  v21 = 0;
  memset_0(v31, 0, sizeof(v31));
  memset_0(v32, 0, sizeof(v32));
  memset(&pvar, 0, sizeof(pvar));
  v28 = 0;
  v29 = 0;
  if ( !a2 || !a3 || !*a3 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_72;
  }
  if ( *a3 == 79 )
  {
    v9 = 1;
  }
  else
  {
    if ( *a3 != 80 )
    {
      v8 = -2147024809;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_72;
      v15 = 149;
      v16 = 2147942487LL;
LABEL_112:
      WPP_SF_d(v14[2], v15, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v16);
      goto LABEL_72;
    }
    v9 = 0;
  }
  v10 = a3 + 1;
  if ( !StrCmpW(a3 + 1, L"DEVICE") )
  {
    v8 = 0;
    v12 = CDeviceFolder::_IsValid(v11, a2);
    if ( v12 && (*((_BYTE *)v12 + 14) & 1) != 0 )
      v8 = -2147467259;
    goto LABEL_72;
  }
  v13 = (*(__int64 (__fastcall **)(char *, struct _ITEMIDLIST *, _QWORD, GUID *, __int64 *))(*((_QWORD *)this + 2) + 40LL))(
          (char *)this + 16,
          a2,
          0,
          &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c,
          &v27);
  v8 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_72;
    v15 = 150;
LABEL_18:
    v16 = (unsigned int)v13;
    goto LABEL_112;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 40LL))(v27, &v25);
  v8 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_72;
    v15 = 151;
    goto LABEL_18;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 32LL))(v25, &v23);
  v8 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_72;
    v15 = 152;
    goto LABEL_18;
  }
  v13 = CoCreateInstance(&CLSID_PortableDeviceKeyCollection, 0, 1u, &GUID_dada2357_e0ad_492e_98db_dd61c53ba353, &ppv);
  v8 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_72;
    v15 = 153;
    goto LABEL_18;
  }
  v13 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_PARENT_ID);
  v8 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_72;
    v15 = 154;
    goto LABEL_18;
  }
  v13 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(
          ppv,
          &WPD_OBJECT_PERSISTENT_UNIQUE_ID);
  v8 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_72;
    v15 = 155;
    goto LABEL_18;
  }
  LOWORD(v28) = 31;
  *((_QWORD *)&v28 + 1) = v10;
  if ( v9 == 1 )
  {
    hVal.QuadPart = (LONGLONG)v10;
  }
  else
  {
    v13 = CoCreateInstance(
            &CLSID_PortableDevicePropVariantCollection,
            0,
            1u,
            &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
            &v24);
    v8 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_72;
      v15 = 156;
      goto LABEL_18;
    }
    v13 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)v24 + 40LL))(v24, &v28);
    v8 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_72;
      v15 = 157;
      goto LABEL_18;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)v25 + 72LL))(v25, v24, &v26);
    v8 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_72;
      v15 = 158;
      goto LABEL_18;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v26 + 32LL))(v26, 0, &pvar);
    v8 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_72;
      v15 = 159;
      goto LABEL_18;
    }
    hVal = pvar.hVal;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, LARGE_INTEGER, LPVOID, struct IUnknown **))(*(_QWORD *)v23 + 40LL))(
         v23,
         hVal,
         ppv,
         &v19);
  do
  {
    if ( v8 < 0 )
      break;
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, LPVOID *))v19->lpVtbl[2].Release)(
           v19,
           &WPD_OBJECT_PARENT_ID,
           &pv);
    if ( v8 < 0 )
      break;
    if ( v21 )
    {
      CoTaskMemFree(v21);
      v21 = 0;
    }
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, LPVOID *))v19->lpVtbl[2].Release)(
           v19,
           &WPD_OBJECT_PERSISTENT_UNIQUE_ID,
           &v21);
    if ( v8 < 0 )
      break;
    if ( !StrCmpW(L"DEVICE", (PCWSTR)pv) )
    {
      v13 = StringCchPrintfW(v31, 0x820u, L"%s\\%s", v21, v32);
      v8 = v13;
      if ( v13 >= 0 )
      {
        v13 = StringCchCopyW(a4, 0x820u, v31);
        v8 = v13;
        if ( v13 < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v15 = 163;
            goto LABEL_18;
          }
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v15 = 160;
          goto LABEL_18;
        }
      }
      break;
    }
    v13 = StringCchPrintfW(v32, 0x820u, L"%s\\%s", v21, v31);
    v8 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 161;
        goto LABEL_18;
      }
      break;
    }
    v13 = StringCchCopyW(v31, 0x820u, v32);
    v8 = v13;
    if ( v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 162;
        goto LABEL_18;
      }
      break;
    }
    if ( v19 )
      ATL::AtlComPtrAssign(&v19, 0);
    v8 = (*(__int64 (__fastcall **)(__int64, LPVOID, LPVOID, struct IUnknown **))(*(_QWORD *)v23 + 40LL))(
           v23,
           pv,
           ppv,
           &v19);
  }
  while ( v8 >= 0 );
LABEL_72:
  PropVariantClear(&pvar);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v21 )
  {
    CoTaskMemFree(v21);
    v21 = 0;
  }
  if ( v8 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      164,
      WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
      (unsigned int)v8);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v24 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v19 )
    ((void (__fastcall *)(struct IUnknown *))v19->lpVtbl->Release)(v19);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180023c34  push    rbp
0x180023c36  push    rbx
0x180023c37  push    rsi
0x180023c38  push    rdi
0x180023c39  push    r12
0x180023c3b  push    r13
0x180023c3d  push    r14
0x180023c3f  push    r15
0x180023c41  lea     rbp, [rsp-2048h]
0x180023c49  mov     eax, 2148h
0x180023c4e  call    _alloca_probe
0x180023c53  sub     rsp, rax
0x180023c56  mov     rax, cs:__security_cookie
0x180023c5d  xor     rax, rsp
0x180023c60  mov     [rbp+2080h+var_50], rax
0x180023c67  mov     r12, r9
0x180023c6a  mov     rbx, r8
0x180023c6d  mov     r14, rdx
0x180023c70  mov     r15, rcx
0x180023c73  xor     r13d, r13d
0x180023c76  mov     [rsp+2180h+var_2110], r13
0x180023c7b  mov     [rsp+2180h+var_2150], r13
0x180023c80  mov     [rsp+2180h+var_2120], r13
0x180023c85  mov     [rsp+2180h+var_2130], r13
0x180023c8a  mov     [rsp+2180h+var_2138], r13
0x180023c8f  mov     [rsp+2180h+var_2128], r13
0x180023c94  mov     [rsp+2180h+var_2118], r13
0x180023c99  mov     [rsp+2180h+pv], r13
0x180023c9e  mov     [rsp+2180h+var_2140], r13
0x180023ca3  mov     edi, 1040h
0x180023ca8  mov     r8d, edi; Size
0x180023cab  xor     edx, edx; Val
0x180023cad  lea     rcx, [rbp+2080h+var_20D0]; void *
0x180023cb1  call    memset_0
0x180023cb6  mov     r8d, edi; Size
0x180023cb9  xor     edx, edx; Val
0x180023cbb  lea     rcx, [rbp+2080h+var_1090]; void *
0x180023cc2  call    memset_0
0x180023cc7  xorps   xmm0, xmm0
0x180023cca  xor     eax, eax
0x180023ccc  movups  xmmword ptr [rbp+2080h+pvar], xmm0
0x180023cd0  mov     qword ptr [rbp+2080h+pvar+10h], rax
0x180023cd4  xorps   xmm1, xmm1
0x180023cd7  movups  [rsp+2180h+var_2108], xmm1
0x180023cdc  mov     [rbp+2080h+var_20F8], rax
0x180023ce0  lea     rdi, WPP_GLOBAL_Control
0x180023ce7  test    r14, r14
0x180023cea  jnz     short loc_180023CF6
0x180023cec  mov     ebx, 80070057h
0x180023cf1  jmp     loc_1800241CE
0x180023cf6  test    rbx, rbx
0x180023cf9  jz      short loc_180023CEC
0x180023cfb  cmp     [rbx], r13w
0x180023cff  jz      short loc_180023CEC
0x180023d01  test    r12, r12
0x180023d04  jz      short loc_180023CEC
0x180023d06  cmp     word ptr [rbx], 4Fh ; 'O'
0x180023d0a  jnz     short loc_180023D13
0x180023d0c  mov     edi, 1
0x180023d11  jmp     short loc_180023D20
0x180023d13  cmp     word ptr [rbx], 50h ; 'P'
0x180023d17  jnz     loc_1800243D7
0x180023d1d  mov     edi, r13d
0x180023d20  lea     rsi, [rbx+2]
0x180023d24  lea     rdx, aDevice_0; "DEVICE"
0x180023d2b  mov     rcx, rsi; psz1
0x180023d2e  call    cs:__imp_StrCmpW
0x180023d34  test    eax, eax
0x180023d36  jnz     short loc_180023D67
0x180023d38  mov     ebx, r13d
0x180023d3b  mov     rdx, r14; struct _ITEMIDLIST *
0x180023d3e  call    ?_IsValid@CDeviceFolder@@AEAAPEFBUDEVICEITEM@@PEFBU_ITEMIDLIST@@@Z; CDeviceFolder::_IsValid(_ITEMIDLIST const *)
0x180023d43  test    rax, rax
0x180023d46  jz      loc_1800241C7
0x180023d4c  lea     rdi, WPP_GLOBAL_Control
0x180023d53  test    byte ptr [rax+0Eh], 1
0x180023d57  jz      loc_1800241CE
0x180023d5d  mov     ebx, 80004005h
0x180023d62  jmp     loc_1800241CE
0x180023d67  lea     rcx, [r15+10h]
0x180023d6b  mov     rax, [rcx]
0x180023d6e  lea     rdx, [rsp+2180h+var_2110]
0x180023d73  mov     [rsp+2180h+ppv], rdx
0x180023d78  lea     r9, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x180023d7f  xor     r8d, r8d
0x180023d82  mov     rdx, r14
0x180023d85  mov     rax, [rax+28h]
0x180023d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d8e  mov     ebx, eax
0x180023d90  test    eax, eax
0x180023d92  jns     short loc_180023DC2
0x180023d94  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d9b  lea     rdi, WPP_GLOBAL_Control
0x180023da2  cmp     rcx, rdi
0x180023da5  jz      loc_1800241CE
0x180023dab  test    byte ptr [rcx+1Ch], 2
0x180023daf  jz      loc_1800241CE
0x180023db5  mov     edx, 96h
0x180023dba  mov     r9d, eax
0x180023dbd  jmp     loc_1800243FE
0x180023dc2  mov     rcx, [rsp+2180h+var_2110]
0x180023dc7  mov     rax, [rcx]
0x180023dca  lea     rdx, [rsp+2180h+var_2120]
0x180023dcf  mov     rax, [rax+28h]
0x180023dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dd8  mov     ebx, eax
0x180023dda  test    eax, eax
0x180023ddc  jns     short loc_180023E06
0x180023dde  mov     rcx, cs:WPP_GLOBAL_Control
0x180023de5  lea     rdi, WPP_GLOBAL_Control
0x180023dec  cmp     rcx, rdi
0x180023def  jz      loc_1800241CE
0x180023df5  test    byte ptr [rcx+1Ch], 2
0x180023df9  jz      loc_1800241CE
0x180023dff  mov     edx, 97h
0x180023e04  jmp     short loc_180023DBA
0x180023e06  mov     rcx, [rsp+2180h+var_2120]
0x180023e0b  mov     rax, [rcx]
0x180023e0e  lea     rdx, [rsp+2180h+var_2130]
0x180023e13  mov     rax, [rax+20h]
0x180023e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e1c  mov     ebx, eax
0x180023e1e  test    eax, eax
0x180023e20  jns     short loc_180023E4D
0x180023e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e29  lea     rdi, WPP_GLOBAL_Control
0x180023e30  cmp     rcx, rdi
0x180023e33  jz      loc_1800241CE
0x180023e39  test    byte ptr [rcx+1Ch], 2
0x180023e3d  jz      loc_1800241CE
0x180023e43  mov     edx, 98h
0x180023e48  jmp     loc_180023DBA
0x180023e4d  lea     rax, [rsp+2180h+var_2138]
0x180023e52  mov     [rsp+2180h+ppv], rax; ppv
0x180023e57  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x180023e5e  xor     edx, edx; pUnkOuter
0x180023e60  lea     r8d, [rdx+1]; dwClsContext
0x180023e64  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x180023e6b  call    cs:__imp_CoCreateInstance
0x180023e71  mov     ebx, eax
0x180023e73  test    eax, eax
0x180023e75  jns     short loc_180023EA2
0x180023e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e7e  lea     rdi, WPP_GLOBAL_Control
0x180023e85  cmp     rcx, rdi
0x180023e88  jz      loc_1800241CE
0x180023e8e  test    byte ptr [rcx+1Ch], 2
0x180023e92  jz      loc_1800241CE
0x180023e98  mov     edx, 99h
0x180023e9d  jmp     loc_180023DBA
0x180023ea2  mov     rcx, [rsp+2180h+var_2138]
0x180023ea7  mov     rax, [rcx]
0x180023eaa  lea     rdx, WPD_OBJECT_PARENT_ID
0x180023eb1  mov     rax, [rax+28h]
0x180023eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eba  mov     ebx, eax
0x180023ebc  test    eax, eax
0x180023ebe  jns     short loc_180023EEB
0x180023ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ec7  lea     rdi, WPP_GLOBAL_Control
0x180023ece  cmp     rcx, rdi
0x180023ed1  jz      loc_1800241CE
0x180023ed7  test    byte ptr [rcx+1Ch], 2
0x180023edb  jz      loc_1800241CE
0x180023ee1  mov     edx, 9Ah
0x180023ee6  jmp     loc_180023DBA
0x180023eeb  mov     rcx, [rsp+2180h+var_2138]
0x180023ef0  mov     rax, [rcx]
0x180023ef3  lea     rdx, WPD_OBJECT_PERSISTENT_UNIQUE_ID
0x180023efa  mov     rax, [rax+28h]
0x180023efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f03  mov     ebx, eax
0x180023f05  test    eax, eax
0x180023f07  jns     short loc_180023F34
0x180023f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f10  lea     rdi, WPP_GLOBAL_Control
0x180023f17  cmp     rcx, rdi
0x180023f1a  jz      loc_1800241CE
0x180023f20  test    byte ptr [rcx+1Ch], 2
0x180023f24  jz      loc_1800241CE
0x180023f2a  mov     edx, 9Bh
0x180023f2f  jmp     loc_180023DBA
0x180023f34  mov     eax, 1Fh
0x180023f39  mov     word ptr [rsp+2180h+var_2108], ax
0x180023f3e  mov     qword ptr [rbp+2080h+var_2108+8], rsi
0x180023f42  cmp     edi, 1
0x180023f45  jnz     short loc_180023F4F
0x180023f47  mov     rdx, rsi
0x180023f4a  jmp     loc_180024083
0x180023f4f  lea     rax, [rsp+2180h+var_2128]
0x180023f54  mov     [rsp+2180h+ppv], rax; ppv
0x180023f59  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x180023f60  xor     edx, edx; pUnkOuter
0x180023f62  lea     r8d, [rdx+1]; dwClsContext
0x180023f66  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x180023f6d  call    cs:__imp_CoCreateInstance
0x180023f73  mov     ebx, eax
0x180023f75  test    eax, eax
0x180023f77  jns     short loc_180023FA4
0x180023f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f80  lea     rdi, WPP_GLOBAL_Control
0x180023f87  cmp     rcx, rdi
0x180023f8a  jz      loc_1800241CE
0x180023f90  test    byte ptr [rcx+1Ch], 2
0x180023f94  jz      loc_1800241CE
0x180023f9a  mov     edx, 9Ch
0x180023f9f  jmp     loc_180023DBA
0x180023fa4  mov     rcx, [rsp+2180h+var_2128]
0x180023fa9  mov     rax, [rcx]
0x180023fac  lea     rdx, [rsp+2180h+var_2108]
0x180023fb1  mov     rax, [rax+28h]
0x180023fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fba  mov     ebx, eax
0x180023fbc  test    eax, eax
0x180023fbe  jns     short loc_180023FEB
0x180023fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fc7  lea     rdi, WPP_GLOBAL_Control
0x180023fce  cmp     rcx, rdi
0x180023fd1  jz      loc_1800241CE
0x180023fd7  test    byte ptr [rcx+1Ch], 2
0x180023fdb  jz      loc_1800241CE
0x180023fe1  mov     edx, 9Dh
0x180023fe6  jmp     loc_180023DBA
0x180023feb  mov     rcx, [rsp+2180h+var_2120]
0x180023ff0  mov     rax, [rcx]
0x180023ff3  lea     r8, [rsp+2180h+var_2118]
0x180023ff8  mov     rdx, [rsp+2180h+var_2128]
0x180023ffd  mov     rax, [rax+48h]
0x180024001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024006  mov     ebx, eax
0x180024008  test    eax, eax
0x18002400a  jns     short loc_180024037
0x18002400c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024013  lea     rdi, WPP_GLOBAL_Control
0x18002401a  cmp     rcx, rdi
0x18002401d  jz      loc_1800241CE
0x180024023  test    byte ptr [rcx+1Ch], 2
0x180024027  jz      loc_1800241CE
0x18002402d  mov     edx, 9Eh
0x180024032  jmp     loc_180023DBA
0x180024037  mov     rcx, [rsp+2180h+var_2118]
0x18002403c  mov     rax, [rcx]
0x18002403f  lea     r8, [rbp+2080h+pvar]
0x180024043  xor     edx, edx
0x180024045  mov     rax, [rax+20h]
0x180024049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002404e  mov     ebx, eax
0x180024050  test    eax, eax
0x180024052  jns     short loc_18002407F
0x180024054  mov     rcx, cs:WPP_GLOBAL_Control
0x18002405b  lea     rdi, WPP_GLOBAL_Control
0x180024062  cmp     rcx, rdi
0x180024065  jz      loc_1800241CE
0x18002406b  test    byte ptr [rcx+1Ch], 2
0x18002406f  jz      loc_1800241CE
0x180024075  mov     edx, 9Fh
0x18002407a  jmp     loc_180023DBA
0x18002407f  mov     rdx, qword ptr [rbp+2080h+pvar+8]
0x180024083  mov     rcx, [rsp+2180h+var_2130]
0x180024088  mov     rax, [rcx]
0x18002408b  lea     r9, [rsp+2180h+var_2150]
0x180024090  mov     r8, [rsp+2180h+var_2138]
0x180024095  mov     rax, [rax+28h]
0x180024099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002409e  mov     ebx, eax
0x1800240a0  mov     edi, 820h
0x1800240a5  test    ebx, ebx
0x1800240a7  js      loc_1800241C7
0x1800240ad  mov     rcx, [rsp+2180h+pv]; pv
0x1800240b2  test    rcx, rcx
0x1800240b5  jz      short loc_1800240C2
0x1800240b7  call    cs:__imp_CoTaskMemFree
0x1800240bd  mov     [rsp+2180h+pv], r13
0x1800240c2  mov     rcx, [rsp+2180h+var_2150]
0x1800240c7  mov     rax, [rcx]
0x1800240ca  lea     r8, [rsp+2180h+pv]
0x1800240cf  lea     rdx, WPD_OBJECT_PARENT_ID
0x1800240d6  mov     rax, [rax+40h]
0x1800240da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240df  mov     ebx, eax
0x1800240e1  test    eax, eax
0x1800240e3  js      loc_1800241C7
0x1800240e9  mov     rcx, [rsp+2180h+var_2140]; pv
0x1800240ee  test    rcx, rcx
0x1800240f1  jz      short loc_1800240FE
0x1800240f3  call    cs:__imp_CoTaskMemFree
0x1800240f9  mov     [rsp+2180h+var_2140], r13
0x1800240fe  mov     rcx, [rsp+2180h+var_2150]
0x180024103  mov     rax, [rcx]
0x180024106  lea     r8, [rsp+2180h+var_2140]
0x18002410b  lea     rdx, WPD_OBJECT_PERSISTENT_UNIQUE_ID
0x180024112  mov     rax, [rax+40h]
0x180024116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002411b  mov     ebx, eax
0x18002411d  test    eax, eax
0x18002411f  js      loc_1800241C7
0x180024125  mov     rdx, [rsp+2180h+pv]; psz2
0x18002412a  lea     rcx, aDevice_0; "DEVICE"
0x180024131  call    cs:__imp_StrCmpW
0x180024137  mov     r9, [rsp+2180h+var_2140]
  ... truncated ...
```
