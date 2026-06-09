# GetFormatFromFileName(IPortableDeviceCapabilities *,ushort const *,_GUID *,_GUID *)

- ea: `0x180025aa4`
- end: `0x180025edd`
- name: `?GetFormatFromFileName@@YAJPEAUIPortableDeviceCapabilities@@PEBGPEAU_GUID@@2@Z`
- size: `1081`
- prototype: `int(struct IPortableDeviceCapabilities *, const unsigned __int16 *, struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025048`

## callees

- `0x180025aa4`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039e80`
- `0x18003a650`
- `0x180051b94`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180025e2b`
- `ADVAPI32!RegCloseKey` at `0x180025e2b`
- `ADVAPI32!RegOpenKeyExW` at `0x180025b80`
- `ADVAPI32!RegOpenKeyExW` at `0x180025b80`
- `SHLWAPI!PathFindExtensionW` at `0x180025b45`
- `SHLWAPI!PathFindExtensionW` at `0x180025b45`
- `SHLWAPI!SHGetValueW` at `0x180025bbd`
- `SHLWAPI!SHGetValueW` at `0x180025c5e`
- `SHLWAPI!SHGetValueW` at `0x180025bbd`
- `SHLWAPI!SHGetValueW` at `0x180025c5e`
- `ole32!CLSIDFromString` at `0x180025bd5`
- `ole32!CLSIDFromString` at `0x180025d7a`
- `ole32!CLSIDFromString` at `0x180025eb8`
- `ole32!CLSIDFromString` at `0x180025bd5`
- `ole32!CLSIDFromString` at `0x180025d7a`
- `ole32!CLSIDFromString` at `0x180025eb8`
- `ole32!PropVariantClear` at `0x180025da8`
- `ole32!PropVariantClear` at `0x180025e36`
- `ole32!PropVariantClear` at `0x180025da8`
- `ole32!PropVariantClear` at `0x180025e36`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetFormatFromFileName(
        struct IPortableDeviceCapabilities *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct _GUID *a4)
{
  int FormatFromFileNameMap; // edi
  const WCHAR *ExtensionW; // r13
  HRESULT v9; // eax
  int v10; // eax
  DWORD v11; // ebx
  int v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  OLECHAR *v15; // r14
  unsigned __int64 v16; // rsi
  unsigned int i; // ebx
  unsigned __int64 v18; // rax
  DWORD pcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwType; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hkey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  struct IPortableDeviceCapabilities *v25; // [rsp+50h] [rbp-B0h]
  PROPVARIANT pvar; // [rsp+58h] [rbp-A8h] BYREF
  CLSID pclsid; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR pvData[56]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[264]; // [rsp+F0h] [rbp-10h] BYREF

  v25 = a1;
  v24 = 0;
  FormatFromFileNameMap = 0;
  memset_0(pvData, 0, 0x64u);
  memset_0(sz, 0, 0x208u);
  hkey = 0;
  pcbData = 0;
  pdwType = 0;
  v23 = 0;
  memset(&pvar, 0, sizeof(pvar));
  *a3 = WPD_CONTENT_TYPE_UNSPECIFIED;
  *a4 = WPD_OBJECT_FORMAT_UNSPECIFIED;
  ExtensionW = PathFindExtensionW(a2);
  if ( !ExtensionW )
    goto LABEL_38;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Portable Devices\\FormatMap", 0, 1u, &hkey) )
    goto LABEL_9;
  pcbData = 100;
  if ( SHGetValueW(hkey, ExtensionW, L"ContentType", &pdwType, pvData, &pcbData) || pdwType != 1 )
    goto LABEL_9;
  v9 = CLSIDFromString(pvData, a3);
  FormatFromFileNameMap = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
        (unsigned int)pvData,
        v9);
    goto LABEL_9;
  }
  pcbData = 520;
  if ( SHGetValueW(hkey, ExtensionW, L"Format", &pdwType, sz, &pcbData) )
    goto LABEL_9;
  if ( pdwType == 1 )
  {
    pclsid = 0;
    if ( CLSIDFromString(sz, &pclsid) >= 0 )
      *a4 = pclsid;
    goto LABEL_38;
  }
  if ( pdwType != 7 )
  {
LABEL_9:
    FormatFromFileNameMap = GetFormatFromFileNameMap(v25, ExtensionW, a3, a4);
    goto LABEL_38;
  }
  v10 = ((__int64 (__fastcall *)(struct IPortableDeviceCapabilities *, struct _GUID *, __int64 *))v25->lpVtbl->GetSupportedFormats)(
          v25,
          a3,
          &v24);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
        (unsigned int)v10);
    goto LABEL_9;
  }
  v11 = pcbData;
  v12 = StringCbLengthW(sz, pcbData, &v23);
  FormatFromFileNameMap = v12;
  if ( v12 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v14 = 12;
LABEL_21:
      WPP_SF_d(v13[2], v14, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, (unsigned int)v12);
    }
    goto LABEL_9;
  }
  v15 = sz;
  while ( 2 )
  {
    v16 = v23;
    if ( v23 && v11 )
    {
      for ( i = 0;
            !(*(unsigned int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v24 + 32LL))(v24, i, &pvar);
            ++i )
      {
        if ( pvar.vt == 72 )
        {
          pclsid = 0;
          if ( CLSIDFromString(v15, &pclsid) >= 0 )
          {
            v18 = *(_QWORD *)&pclsid.Data1 - (unsigned __int64)*pvar.pbstrVal;
            if ( *(BSTR *)&pclsid.Data1 == *pvar.pbstrVal )
              v18 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)(pvar.hVal.QuadPart + 8);
            if ( !v18 )
            {
              *a4 = pclsid;
              goto LABEL_38;
            }
          }
        }
        PropVariantClear(&pvar);
      }
      v11 = -2 - v16 + pcbData;
      pcbData = v11;
      v15 += (v16 >> 1) + 1;
      v12 = StringCbLengthW(v15, v11, &v23);
      FormatFromFileNameMap = v12;
      if ( v12 >= 0 )
        continue;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v14 = 13;
        goto LABEL_21;
      }
      goto LABEL_9;
    }
    break;
  }
LABEL_38:
  if ( hkey )
    RegCloseKey(hkey);
  PropVariantClear(&pvar);
  if ( FormatFromFileNameMap < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
      (unsigned int)FormatFromFileNameMap);
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)FormatFromFileNameMap;
}

```

## disassembly

```asm
0x180025aa4  push    rbp
0x180025aa6  push    rbx
0x180025aa7  push    rsi
0x180025aa8  push    rdi
0x180025aa9  push    r12
0x180025aab  push    r13
0x180025aad  push    r14
0x180025aaf  push    r15
0x180025ab1  lea     rbp, [rsp-218h]
0x180025ab9  sub     rsp, 318h
0x180025ac0  mov     rax, cs:__security_cookie
0x180025ac7  xor     rax, rsp
0x180025aca  mov     [rbp+250h+var_50], rax
0x180025ad1  mov     r15, r9
0x180025ad4  mov     r12, r8
0x180025ad7  mov     rbx, rdx
0x180025ada  mov     [rsp+350h+var_300], rcx
0x180025adf  xor     esi, esi
0x180025ae1  mov     [rsp+350h+var_308], rsi
0x180025ae6  mov     edi, esi
0x180025ae8  xor     edx, edx; Val
0x180025aea  lea     r8d, [rsi+64h]; Size
0x180025aee  lea     rcx, [rbp+250h+pvData]; void *
0x180025af2  call    memset_0
0x180025af7  xor     edx, edx; Val
0x180025af9  mov     r8d, 208h; Size
0x180025aff  lea     rcx, [rbp+250h+sz]; void *
0x180025b03  call    memset_0
0x180025b08  mov     [rsp+350h+hkey], rsi
0x180025b0d  mov     [rsp+350h+var_320], esi
0x180025b11  mov     [rsp+350h+pdwType], esi
0x180025b15  mov     [rsp+350h+var_310], rsi
0x180025b1a  xorps   xmm0, xmm0
0x180025b1d  xor     eax, eax
0x180025b1f  movups  xmmword ptr [rsp+350h+pvar], xmm0
0x180025b24  mov     qword ptr [rsp+350h+pvar+10h], rax
0x180025b29  movups  xmm1, xmmword ptr cs:WPD_CONTENT_TYPE_UNSPECIFIED.Data1
0x180025b30  movdqu  xmmword ptr [r12], xmm1
0x180025b36  movups  xmm0, xmmword ptr cs:WPD_OBJECT_FORMAT_UNSPECIFIED.Data1
0x180025b3d  movdqu  xmmword ptr [r15], xmm0
0x180025b42  mov     rcx, rbx; pszPath
0x180025b45  call    cs:__imp_PathFindExtensionW
0x180025b4b  mov     r13, rax
0x180025b4e  lea     rbx, WPP_GLOBAL_Control
0x180025b55  mov     r14b, 2
0x180025b58  test    rax, rax
0x180025b5b  jz      loc_180025E1A
0x180025b61  lea     rax, [rsp+350h+hkey]
0x180025b66  mov     [rsp+350h+phkResult], rax; phkResult
0x180025b6b  lea     r9d, [rsi+1]; samDesired
0x180025b6f  xor     r8d, r8d; ulOptions
0x180025b72  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Portable D"...
0x180025b79  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025b80  call    cs:__imp_RegOpenKeyExW
0x180025b86  test    eax, eax
0x180025b88  jnz     loc_180025C0E
0x180025b8e  mov     [rsp+350h+var_320], 64h ; 'd'
0x180025b96  lea     rax, [rsp+350h+var_320]
0x180025b9b  mov     [rsp+350h+pcbData], rax; pcbData
0x180025ba0  lea     rax, [rbp+250h+pvData]
0x180025ba4  mov     [rsp+350h+phkResult], rax; pvData
0x180025ba9  lea     r9, [rsp+350h+pdwType]; pdwType
0x180025bae  lea     r8, pszValue; "ContentType"
0x180025bb5  mov     rdx, r13; pszSubKey
0x180025bb8  mov     rcx, [rsp+350h+hkey]; hkey
0x180025bbd  call    cs:__imp_SHGetValueW
0x180025bc3  test    eax, eax
0x180025bc5  jnz     short loc_180025C0E
0x180025bc7  cmp     [rsp+350h+pdwType], 1
0x180025bcc  jnz     short loc_180025C0E
0x180025bce  mov     rdx, r12; pclsid
0x180025bd1  lea     rcx, [rbp+250h+pvData]; lpsz
0x180025bd5  call    cs:__imp_CLSIDFromString
0x180025bdb  mov     edi, eax
0x180025bdd  test    eax, eax
0x180025bdf  jns     short loc_180025C2F
0x180025be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180025be8  cmp     rcx, rbx
0x180025beb  jz      short loc_180025C0E
0x180025bed  test    [rcx+1Ch], r14b
0x180025bf1  jz      short loc_180025C0E
0x180025bf3  lea     edx, [rsi+0Ah]
0x180025bf6  mov     dword ptr [rsp+350h+phkResult], eax
0x180025bfa  lea     r9, [rbp+250h+pvData]
0x180025bfe  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180025c05  mov     rcx, [rcx+10h]
0x180025c09  call    WPP_SF_Sd
0x180025c0e  lea     rbx, WPP_GLOBAL_Control
0x180025c15  mov     r9, r15; struct _GUID *
0x180025c18  mov     r8, r12; struct _GUID *
0x180025c1b  mov     rdx, r13; unsigned __int16 *
0x180025c1e  mov     rcx, [rsp+350h+var_300]; struct IPortableDeviceCapabilities *
0x180025c23  call    ?GetFormatFromFileNameMap@@YAJPEAUIPortableDeviceCapabilities@@PEBGPEAU_GUID@@2@Z; GetFormatFromFileNameMap(IPortableDeviceCapabilities *,ushort const *,_GUID *,_GUID *)
0x180025c28  mov     edi, eax
0x180025c2a  jmp     loc_180025E21
0x180025c2f  mov     [rsp+350h+var_320], 208h
0x180025c37  lea     rax, [rsp+350h+var_320]
0x180025c3c  mov     [rsp+350h+pcbData], rax; pcbData
0x180025c41  lea     rax, [rbp+250h+sz]
0x180025c45  mov     [rsp+350h+phkResult], rax; pvData
0x180025c4a  lea     r9, [rsp+350h+pdwType]; pdwType
0x180025c4f  lea     r8, aFormat; "Format"
0x180025c56  mov     rdx, r13; pszSubKey
0x180025c59  mov     rcx, [rsp+350h+hkey]; hkey
0x180025c5e  call    cs:__imp_SHGetValueW
0x180025c64  test    eax, eax
0x180025c66  jnz     short loc_180025C0E
0x180025c68  cmp     [rsp+350h+pdwType], 1
0x180025c6d  jz      loc_180025EA7
0x180025c73  cmp     [rsp+350h+pdwType], 7
0x180025c78  jnz     short loc_180025C0E
0x180025c7a  mov     rcx, [rsp+350h+var_300]
0x180025c7f  mov     rax, [rcx]
0x180025c82  lea     r8, [rsp+350h+var_308]
0x180025c87  mov     rdx, r12
0x180025c8a  mov     rax, [rax+40h]
0x180025c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c93  test    eax, eax
0x180025c95  jns     short loc_180025CCE
0x180025c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c9e  cmp     rcx, rbx
0x180025ca1  jz      loc_180025C0E
0x180025ca7  test    [rcx+1Ch], r14b
0x180025cab  jz      loc_180025C0E
0x180025cb1  mov     edx, 0Bh
0x180025cb6  mov     r9d, eax
0x180025cb9  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180025cc0  mov     rcx, [rcx+10h]
0x180025cc4  call    WPP_SF_d
0x180025cc9  jmp     loc_180025C0E
0x180025cce  mov     ebx, [rsp+350h+var_320]
0x180025cd2  mov     edx, ebx; unsigned __int64
0x180025cd4  lea     r8, [rsp+350h+var_310]; unsigned __int64 *
0x180025cd9  lea     rcx, [rbp+250h+sz]; unsigned __int16 *
0x180025cdd  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180025ce2  mov     edi, eax
0x180025ce4  test    eax, eax
0x180025ce6  jns     short loc_180025D26
0x180025ce8  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cef  lea     rbx, WPP_GLOBAL_Control
0x180025cf6  cmp     rcx, rbx
0x180025cf9  jz      loc_180025C15
0x180025cff  test    [rcx+1Ch], r14b
0x180025d03  jz      loc_180025C15
0x180025d09  mov     edx, 0Ch
0x180025d0e  mov     r9d, eax
0x180025d11  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180025d18  mov     rcx, [rcx+10h]
0x180025d1c  call    WPP_SF_d
0x180025d21  jmp     loc_180025C15
0x180025d26  lea     r14, [rbp+250h+sz]
0x180025d2a  mov     rsi, [rsp+350h+var_310]
0x180025d2f  test    rsi, rsi
0x180025d32  jz      loc_180025E1A
0x180025d38  test    ebx, ebx
0x180025d3a  jz      loc_180025E1A
0x180025d40  xor     ebx, ebx
0x180025d42  mov     rcx, [rsp+350h+var_308]
0x180025d47  mov     rax, [rcx]
0x180025d4a  lea     r8, [rsp+350h+pvar]
0x180025d4f  mov     edx, ebx
0x180025d51  mov     rax, [rax+20h]
0x180025d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d5a  test    eax, eax
0x180025d5c  jnz     short loc_180025DB0
0x180025d5e  mov     eax, 48h ; 'H'
0x180025d63  cmp     ax, word ptr [rsp+350h+pvar]
0x180025d68  jnz     short loc_180025DA1
0x180025d6a  xorps   xmm0, xmm0
0x180025d6d  movups  xmmword ptr [rsp+350h+pclsid.Data1], xmm0
0x180025d72  lea     rdx, [rsp+350h+pclsid]; pclsid
0x180025d77  mov     rcx, r14; lpsz
0x180025d7a  call    cs:__imp_CLSIDFromString
0x180025d80  test    eax, eax
0x180025d82  js      short loc_180025DA1
0x180025d84  mov     rcx, qword ptr [rsp+350h+pvar+8]
0x180025d89  mov     rax, qword ptr [rsp+350h+pclsid.Data1]
0x180025d8e  sub     rax, [rcx]
0x180025d91  jnz     short loc_180025D9C
0x180025d93  mov     rax, qword ptr [rsp+350h+pclsid.Data4]
0x180025d98  sub     rax, [rcx+8]
0x180025d9c  test    rax, rax
0x180025d9f  jz      short loc_180025E10
0x180025da1  inc     ebx
0x180025da3  lea     rcx, [rsp+350h+pvar]; pvar
0x180025da8  call    cs:__imp_PropVariantClear
0x180025dae  jmp     short loc_180025D42
0x180025db0  mov     eax, 0FFFFFFFEh
0x180025db5  sub     eax, esi
0x180025db7  mov     ebx, [rsp+350h+var_320]
0x180025dbb  add     ebx, eax
0x180025dbd  mov     [rsp+350h+var_320], ebx
0x180025dc1  mov     edx, ebx; unsigned __int64
0x180025dc3  shr     rsi, 1
0x180025dc6  lea     r14, [r14+rsi*2]
0x180025dca  add     r14, 2
0x180025dce  lea     r8, [rsp+350h+var_310]; unsigned __int64 *
0x180025dd3  mov     rcx, r14; unsigned __int16 *
0x180025dd6  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180025ddb  mov     edi, eax
0x180025ddd  test    eax, eax
0x180025ddf  jns     loc_180025D2A
0x180025de5  mov     rcx, cs:WPP_GLOBAL_Control
0x180025dec  lea     rbx, WPP_GLOBAL_Control
0x180025df3  cmp     rcx, rbx
0x180025df6  jz      loc_180025C15
0x180025dfc  test    byte ptr [rcx+1Ch], 2
0x180025e00  jz      loc_180025C15
0x180025e06  mov     edx, 0Dh
0x180025e0b  jmp     loc_180025D0E
0x180025e10  movups  xmm0, xmmword ptr [rsp+350h+pclsid.Data1]
0x180025e15  movdqu  xmmword ptr [r15], xmm0
0x180025e1a  lea     rbx, WPP_GLOBAL_Control
0x180025e21  mov     rcx, [rsp+350h+hkey]; hKey
0x180025e26  test    rcx, rcx
0x180025e29  jz      short loc_180025E31
0x180025e2b  call    cs:__imp_RegCloseKey
0x180025e31  lea     rcx, [rsp+350h+pvar]; pvar
0x180025e36  call    cs:__imp_PropVariantClear
0x180025e3c  test    edi, edi
0x180025e3e  jns     short loc_180025E6B
0x180025e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e47  cmp     rcx, rbx
0x180025e4a  jz      short loc_180025E6B
0x180025e4c  test    byte ptr [rcx+1Ch], 2
0x180025e50  jz      short loc_180025E6B
0x180025e52  mov     edx, 0Eh
0x180025e57  mov     r9d, edi
0x180025e5a  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180025e61  mov     rcx, [rcx+10h]
0x180025e65  call    WPP_SF_d
0x180025e6a  nop
0x180025e6b  mov     rcx, [rsp+350h+var_308]
0x180025e70  test    rcx, rcx
0x180025e73  jz      short loc_180025E82
0x180025e75  mov     rax, [rcx]
0x180025e78  mov     rax, [rax+10h]
0x180025e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e81  nop
0x180025e82  mov     eax, edi
0x180025e84  mov     rcx, [rbp+250h+var_50]
0x180025e8b  xor     rcx, rsp; StackCookie
0x180025e8e  call    __security_check_cookie
0x180025e93  add     rsp, 318h
0x180025e9a  pop     r15
0x180025e9c  pop     r14
0x180025e9e  pop     r13
0x180025ea0  pop     r12
0x180025ea2  pop     rdi
0x180025ea3  pop     rsi
0x180025ea4  pop     rbx
0x180025ea5  pop     rbp
0x180025ea6  retn
0x180025ea7  xorps   xmm0, xmm0
0x180025eaa  movups  xmmword ptr [rsp+350h+pclsid.Data1], xmm0
0x180025eaf  lea     rdx, [rsp+350h+pclsid]; pclsid
0x180025eb4  lea     rcx, [rbp+250h+sz]; lpsz
0x180025eb8  call    cs:__imp_CLSIDFromString
0x180025ebe  lea     rbx, WPP_GLOBAL_Control
0x180025ec5  test    eax, eax
0x180025ec7  js      loc_180025E21
0x180025ecd  movups  xmm0, xmmword ptr [rsp+350h+pclsid.Data1]
0x180025ed2  movdqu  xmmword ptr [r15], xmm0
0x180025ed7  jmp     loc_180025E21
```
