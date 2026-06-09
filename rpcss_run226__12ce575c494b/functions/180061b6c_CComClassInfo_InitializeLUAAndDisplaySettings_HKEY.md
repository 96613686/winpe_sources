# CComClassInfo::InitializeLUAAndDisplaySettings(HKEY__ *)

- ea: `0x180061b6c`
- end: `0x1800620f8`
- name: `?InitializeLUAAndDisplaySettings@CComClassInfo@@AEAAJPEAUHKEY__@@@Z`
- size: `1420`
- prototype: `int(CComClassInfo *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180038d84`

## callees

- `0x180034540`
- `0x1800566cc`
- `0x180061b6c`
- `0x180070740`
- `0x18009ffc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061f13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061f13`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061e50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061e50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061dbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061fa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062032`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061dbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061fa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062032`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062054`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061be2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061c1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061f50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006200a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061be2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061c1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061f50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006200a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061c74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061c74`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180061e90`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180061e90`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x180061bb2`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800620d8`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x180061bb2`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800620d8`

## string_xrefs

- `0x180061c34`: `onecore\com\combase\catalog\class.cxx`
- `0x1800620b4`: `onecore\com\combase\catalog\class.cxx`
- `0x180061c2d`: `CComClassInfo::InitializeLUAAndDisplaySettings`
- `0x18006209f`: `CComClassInfo::InitializeLUAAndDisplaySettings`
- `0x180061c24`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180061d12`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180061da4`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180061ef6`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180062093`: `CLSID:%ws %!HRESULT!`

## pseudocode

```c
__int64 __fastcall CComClassInfo::InitializeLUAAndDisplaySettings(CComClassInfo *this, HKEY a2)
{
  bool v2; // zf
  LSTATUS v5; // eax
  signed int v6; // ebx
  REGSAM v7; // r9d
  LSTATUS v8; // eax
  int v9; // r9d
  const wchar_t *v10; // r8
  signed int v11; // edi
  LSTATUS v12; // eax
  int v13; // r9d
  unsigned int v14; // ebx
  int v15; // r8d
  signed int RegistryStringValue; // eax
  int v17; // r9d
  WCHAR *v18; // rax
  WCHAR *v19; // rdi
  LSTATUS MUIStringW; // eax
  int v21; // r9d
  int v22; // r9d
  LSTATUS v23; // eax
  unsigned __int16 **v24; // rdi
  signed int v25; // eax
  signed int v26; // eax
  REGSAM v27; // r9d
  LSTATUS v28; // eax
  __int64 v30; // [rsp+38h] [rbp-28h]
  DWORD cbData; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-10h] BYREF
  HKEY Type; // [rsp+A0h] [rbp+40h] BYREF
  int Data; // [rsp+B0h] [rbp+50h] BYREF
  int v36; // [rsp+B8h] [rbp+58h]

  v2 = *((_DWORD *)this + 59) == 512;
  Data = 0;
  hKey = 0;
  v36 = 0;
  if ( v2 )
    LOWORD(v36) = Wow64SetThreadDefaultGuestMachine(*((unsigned __int16 *)this + 120));
  v5 = RegOpenKeyExW(a2, (LPCWSTR)this + 56, 0, *((_DWORD *)this + 59) | 0x20019, &hKey);
  v6 = v5;
  if ( !v5 )
  {
    v7 = *((_DWORD *)this + 59) | 0x20019;
    hkey = 0;
    v8 = RegOpenKeyExW(hKey, L"Elevation", 0, v7, &hkey);
    v10 = L"CLSID:%ws Value:%ws %!HRESULT!";
    v11 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v11 = (unsigned __int16)v8 | 0x80070000;
      if ( v11 != -2147024894 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
        ComTraceMessageT<unsigned short *,unsigned short const *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
          (unsigned int)"CComClassInfo::InitializeLUAAndDisplaySettings",
          461,
          v9,
          (__int64)v10,
          (char *)this + 112,
          L"Elevation",
          v11);
      goto LABEL_39;
    }
    LODWORD(Type) = 0;
    cbData = 4;
    v12 = RegQueryValueExW(hkey, L"Enabled", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData);
    v14 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v14 = (unsigned __int16)v12 | 0x80070000;
      if ( v14 != -2147024894 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
      {
        v15 = 436;
        goto LABEL_19;
      }
    }
    else
    {
      if ( (_DWORD)Type == 4 )
      {
        v11 = 0;
        *((_DWORD *)this + 77) = Data;
LABEL_23:
        if ( *((_DWORD *)this + 77) )
        {
          RegistryStringValue = GetRegistryStringValue(hkey, 0, L"IconReference", 0, (unsigned __int16 **)this + 42);
          v11 = 0;
          if ( RegistryStringValue != -2147024894 )
            v11 = RegistryStringValue;
          if ( v11 < 0 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
          {
            LODWORD(v30) = v11;
            ComTraceMessageT<unsigned short *,unsigned short const *,long>(
              (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
              (unsigned int)"CComClassInfo::InitializeLUAAndDisplaySettings",
              450,
              v17,
              (__int64)L"CLSID:%ws Value:%ws %!HRESULT!",
              (char *)this + 112,
              L"IconReference",
              v30);
          }
        }
LABEL_31:
        RegCloseKey(hkey);
LABEL_39:
        v6 = 0;
        if ( v11 != -2147024894 )
          v6 = v11;
        if ( v6 >= 0 && *((_DWORD *)this + 77) )
        {
          v18 = (WCHAR *)HeapAlloc(g_hHeap, 0, 0x200u);
          v19 = v18;
          if ( v18 )
          {
            MUIStringW = RegLoadMUIStringW(hKey, L"LocalizedString", v18, 0x200u, 0, 1u, 0);
            if ( MUIStringW )
            {
              if ( MUIStringW > 0 )
                v6 = (unsigned __int16)MUIStringW | 0x80070000;
              else
                v6 = MUIStringW;
              if ( v6 != -2147024894 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
              {
                LODWORD(v30) = v6;
                ComTraceMessageT<unsigned short *,unsigned short const *,long>(
                  (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
                  (unsigned int)"CComClassInfo::InitializeLUAAndDisplaySettings",
                  481,
                  v21,
                  (__int64)L"CLSID:%ws Value:%ws %!HRESULT!",
                  (char *)this + 112,
                  L"LocalizedString",
                  v30);
              }
              HeapFree(g_hHeap, 0, v19);
            }
            else
            {
              *((_QWORD *)this + 40) = v19;
            }
            if ( v6 >= 0 )
            {
              v22 = *((_DWORD *)this + 59);
              Type = 0;
              v23 = RegOpenKeyExW(hKey, L"LocalServer32", 0, v22 | 0x20019, &Type);
              v6 = v23;
              if ( v23 )
              {
                if ( v23 > 0 )
                  v6 = (unsigned __int16)v23 | 0x80070000;
                v24 = (unsigned __int16 **)((char *)this + 328);
              }
              else
              {
                v24 = (unsigned __int16 **)((char *)this + 328);
                v25 = GetRegistryStringValue(Type, 0, L"ServerExecutable", 0, (unsigned __int16 **)this + 41);
                if ( v25 != -2147024894 )
                  v6 = v25;
                if ( v6 >= 0 && !*v24 )
                  v6 = GetRegistryStringValue(Type, 0, 0, 0, (unsigned __int16 **)this + 41);
                RegCloseKey(Type);
              }
              if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147024894 )
              {
                v26 = 0;
                if ( v6 != -2147024894 )
                  v26 = v6;
                v6 = v26;
                if ( !*v24 )
                {
                  v27 = *((_DWORD *)this + 59) | 0x20019;
                  Type = 0;
                  v28 = RegOpenKeyExW(hKey, L"InprocServer32", 0, v27, &Type);
                  v6 = v28;
                  if ( v28 )
                  {
                    if ( v28 > 0 )
                      v6 = (unsigned __int16)v28 | 0x80070000;
                  }
                  else
                  {
                    v6 = GetRegistryStringValue(Type, 0, 0, 0, v24);
                    RegCloseKey(Type);
                  }
                  if ( v6 == -2147024894 )
                    v6 = 0;
                }
              }
            }
          }
          else
          {
            v6 = -2147024882;
          }
        }
        RegCloseKey(hKey);
        goto LABEL_86;
      }
      v14 = -2147221165;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v15 = 427;
LABEL_19:
        ComTraceMessageT<unsigned short *,unsigned short const *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
          (unsigned int)"CComClassInfo::InitializeLUAAndDisplaySettings",
          v15,
          v13,
          (__int64)L"CLSID:%ws Value:%ws %!HRESULT!",
          (char *)this + 112,
          L"Enabled",
          v14);
      }
    }
    v11 = 0;
    if ( v14 != -2147024894 )
      v11 = v14;
    if ( v11 < 0 )
      goto LABEL_31;
    goto LABEL_23;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 != -2147024894 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
    ComTraceMessageT<unsigned short *,long>(
      (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
      (unsigned int)"CComClassInfo::InitializeLUAAndDisplaySettings",
      545,
      0,
      (__int64)L"CLSID:%ws %!HRESULT!",
      (char *)this + 112,
      v6);
LABEL_86:
  if ( v6 == -2147024894 )
    v6 = 0;
  if ( *((_DWORD *)this + 59) == 512 )
    Wow64SetThreadDefaultGuestMachine((unsigned __int16)v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180061b6c  mov     [rsp-38h+arg_8], rbx
0x180061b71  push    rbp
0x180061b72  push    rsi
0x180061b73  push    rdi
0x180061b74  push    r12
0x180061b76  push    r13
0x180061b78  push    r14
0x180061b7a  push    r15
0x180061b7c  mov     rbp, rsp
0x180061b7f  sub     rsp, 60h
0x180061b83  cmp     dword ptr [rcx+0ECh], 200h
0x180061b8d  mov     rbx, rdx
0x180061b90  mov     rsi, rcx
0x180061b93  mov     [rbp+Data], 0
0x180061b9a  mov     [rbp+hKey], 0
0x180061ba2  mov     [rbp+arg_18], 0
0x180061ba9  jnz     short loc_180061BBC
0x180061bab  movzx   ecx, word ptr [rcx+0F0h]
0x180061bb2  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x180061bb8  mov     word ptr [rbp+arg_18], ax
0x180061bbc  mov     r9d, [rsi+0ECh]
0x180061bc3  lea     rax, [rbp+hKey]
0x180061bc7  lea     rdi, [rsi+70h]
0x180061bcb  mov     [rsp+60h+phkResult], rax; phkResult
0x180061bd0  mov     r14d, 20019h
0x180061bd6  mov     rdx, rdi; lpSubKey
0x180061bd9  or      r9d, r14d; samDesired
0x180061bdc  xor     r8d, r8d; ulOptions
0x180061bdf  mov     rcx, rbx; hKey
0x180061be2  call    cs:__imp_RegOpenKeyExW
0x180061be8  mov     ebx, eax
0x180061bea  test    eax, eax
0x180061bec  jnz     loc_18006205C
0x180061bf2  mov     r9d, [rsi+0ECh]
0x180061bf9  lea     rax, [rbp+hkey]
0x180061bfd  mov     rcx, [rbp+hKey]; hKey
0x180061c01  lea     rbx, aElevation; "Elevation"
0x180061c08  or      r9d, r14d; samDesired
0x180061c0b  mov     [rbp+hkey], 0
0x180061c13  mov     rdx, rbx; lpSubKey
0x180061c16  mov     [rsp+60h+phkResult], rax; phkResult
0x180061c1b  xor     r8d, r8d; ulOptions
0x180061c1e  call    cs:__imp_RegOpenKeyExW
0x180061c24  lea     r8, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180061c2b  mov     edi, eax
0x180061c2d  lea     r12, aCcomclassinfoI_2; "CComClassInfo::InitializeLUAAndDisplayS"...
0x180061c34  lea     r13, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180061c3b  test    eax, eax
0x180061c3d  jnz     loc_180061DC4
0x180061c43  mov     rcx, [rbp+hkey]; hKey
0x180061c47  lea     rdi, ValueName; "Enabled"
0x180061c4e  mov     dword ptr [rbp+Type], eax
0x180061c51  lea     r9, [rbp+Type]; lpType
0x180061c55  lea     rax, [rbp+cbData]
0x180061c59  mov     [rbp+cbData], 4
0x180061c60  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180061c65  xor     r8d, r8d; lpReserved
0x180061c68  lea     rax, [rbp+Data]
0x180061c6c  mov     rdx, rdi; lpValueName
0x180061c6f  mov     [rsp+60h+phkResult], rax; lpData
0x180061c74  call    cs:__imp_RegQueryValueExW
0x180061c7a  mov     r15d, 80070000h
0x180061c80  mov     ebx, eax
0x180061c82  lea     r14d, [r15+2]
0x180061c86  test    eax, eax
0x180061c88  jnz     short loc_180061CCA
0x180061c8a  cmp     dword ptr [rbp+Type], 4
0x180061c8e  jnz     short loc_180061CA0
0x180061c90  mov     eax, [rbp+Data]
0x180061c93  xor     edi, edi
0x180061c95  mov     [rsi+134h], eax
0x180061c9b  jmp     loc_180061D33
0x180061ca0  mov     eax, cs:dword_18014E4B8
0x180061ca6  mov     ebx, 80040153h
0x180061cab  test    eax, eax
0x180061cad  jnz     short loc_180061CC2
0x180061caf  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180061cb5  jz      short loc_180061D23
0x180061cb7  xor     ecx, ecx
0x180061cb9  call    IsWppLevelEnabled
0x180061cbe  test    al, al
0x180061cc0  jz      short loc_180061D23
0x180061cc2  mov     r8d, 1ABh
0x180061cc8  jmp     short loc_180061CFA
0x180061cca  jle     short loc_180061CD2
0x180061ccc  movzx   ebx, ax
0x180061ccf  or      ebx, r15d
0x180061cd2  cmp     ebx, r14d
0x180061cd5  jz      short loc_180061D23
0x180061cd7  mov     eax, cs:dword_18014E4B8
0x180061cdd  test    eax, eax
0x180061cdf  jnz     short loc_180061CF4
0x180061ce1  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180061ce7  jz      short loc_180061D23
0x180061ce9  xor     ecx, ecx
0x180061ceb  call    IsWppLevelEnabled
0x180061cf0  test    al, al
0x180061cf2  jz      short loc_180061D23
0x180061cf4  mov     r8d, 1B4h
0x180061cfa  mov     dword ptr [rsp+60h+var_28], ebx
0x180061cfe  lea     rax, [rsi+70h]
0x180061d02  mov     [rsp+60h+pszDirectory], rdi
0x180061d07  mov     rdx, r12
0x180061d0a  mov     [rsp+60h+lpcbData], rax
0x180061d0f  mov     rcx, r13
0x180061d12  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180061d19  mov     [rsp+60h+phkResult], rax
0x180061d1e  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x180061d23  xor     edi, edi
0x180061d25  cmp     ebx, r14d
0x180061d28  cmovnz  edi, ebx
0x180061d2b  test    edi, edi
0x180061d2d  js      loc_180061DB8
0x180061d33  cmp     dword ptr [rsi+134h], 0
0x180061d3a  jz      short loc_180061DB8
0x180061d3c  mov     rcx, [rbp+hkey]; hkey
0x180061d40  lea     rax, [rsi+150h]
0x180061d47  lea     rbx, aIconreference; "IconReference"
0x180061d4e  mov     [rsp+60h+phkResult], rax; unsigned __int16 **
0x180061d53  mov     r8, rbx; lpValue
0x180061d56  xor     r9d, r9d; unsigned int
0x180061d59  xor     edx, edx; lpSubKey
0x180061d5b  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180061d60  xor     edi, edi
0x180061d62  cmp     eax, r14d
0x180061d65  cmovnz  edi, eax
0x180061d68  test    edi, edi
0x180061d6a  jns     short loc_180061DB8
0x180061d6c  mov     eax, cs:dword_18014E4B8
0x180061d72  test    eax, eax
0x180061d74  jnz     short loc_180061D89
0x180061d76  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180061d7c  jz      short loc_180061DB8
0x180061d7e  xor     ecx, ecx
0x180061d80  call    IsWppLevelEnabled
0x180061d85  test    al, al
0x180061d87  jz      short loc_180061DB8
0x180061d89  mov     dword ptr [rsp+60h+var_28], edi
0x180061d8d  lea     rax, [rsi+70h]
0x180061d91  mov     [rsp+60h+pszDirectory], rbx
0x180061d96  mov     r8d, 1C2h
0x180061d9c  mov     [rsp+60h+lpcbData], rax
0x180061da1  mov     rdx, r12
0x180061da4  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180061dab  mov     rcx, r13
0x180061dae  mov     [rsp+60h+phkResult], rax
0x180061db3  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x180061db8  mov     rcx, [rbp+hkey]; hKey
0x180061dbc  call    cs:__imp_RegCloseKey
0x180061dc2  jmp     short loc_180061E24
0x180061dc4  mov     r15d, 80070000h
0x180061dca  test    eax, eax
0x180061dcc  jle     short loc_180061DD4
0x180061dce  movzx   edi, ax
0x180061dd1  or      edi, r15d
0x180061dd4  mov     r14d, 80070002h
0x180061dda  cmp     edi, r14d
0x180061ddd  jz      short loc_180061E24
0x180061ddf  mov     eax, cs:dword_18014E4B8
0x180061de5  test    eax, eax
0x180061de7  jnz     short loc_180061DFC
0x180061de9  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180061def  jz      short loc_180061E24
0x180061df1  xor     ecx, ecx
0x180061df3  call    IsWppLevelEnabled
0x180061df8  test    al, al
0x180061dfa  jz      short loc_180061E24
0x180061dfc  mov     dword ptr [rsp+60h+var_28], edi
0x180061e00  lea     rax, [rsi+70h]
0x180061e04  mov     [rsp+60h+pszDirectory], rbx
0x180061e09  mov     rdx, r12
0x180061e0c  mov     [rsp+60h+lpcbData], rax
0x180061e11  mov     rcx, r13
0x180061e14  mov     [rsp+60h+phkResult], r8
0x180061e19  mov     r8d, 1CDh
0x180061e1f  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x180061e24  xor     ebx, ebx
0x180061e26  cmp     edi, r14d
0x180061e29  cmovnz  ebx, edi
0x180061e2c  test    ebx, ebx
0x180061e2e  js      loc_180062050
0x180061e34  cmp     dword ptr [rsi+134h], 0
0x180061e3b  jz      loc_180062050
0x180061e41  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180061e48  xor     edx, edx; dwFlags
0x180061e4a  mov     r8d, 200h; dwBytes
0x180061e50  call    cs:__imp_HeapAlloc
0x180061e56  mov     rdi, rax
0x180061e59  test    rax, rax
0x180061e5c  jz      loc_18006204B
0x180061e62  mov     rcx, [rbp+hKey]; hKey
0x180061e66  lea     rdx, pszValue; "LocalizedString"
0x180061e6d  mov     [rsp+60h+pszDirectory], 0; pszDirectory
0x180061e76  mov     r9d, 200h; cbOutBuf
0x180061e7c  mov     dword ptr [rsp+60h+lpcbData], 1; Flags
0x180061e84  mov     r8, rax; pszOutBuf
0x180061e87  mov     [rsp+60h+phkResult], 0; pcbData
0x180061e90  call    cs:__imp_RegLoadMUIStringW
0x180061e96  test    eax, eax
0x180061e98  jnz     short loc_180061EA3
0x180061e9a  mov     [rsi+140h], rdi
0x180061ea1  jmp     short loc_180061F19
0x180061ea3  jg      short loc_180061EA9
0x180061ea5  mov     ebx, eax
0x180061ea7  jmp     short loc_180061EAF
0x180061ea9  movzx   ebx, ax
0x180061eac  or      ebx, r15d
0x180061eaf  cmp     ebx, r14d
0x180061eb2  jz      short loc_180061F07
0x180061eb4  mov     eax, cs:dword_18014E4B8
0x180061eba  test    eax, eax
0x180061ebc  jnz     short loc_180061ED1
0x180061ebe  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180061ec4  jz      short loc_180061F07
0x180061ec6  xor     ecx, ecx
0x180061ec8  call    IsWppLevelEnabled
0x180061ecd  test    al, al
0x180061ecf  jz      short loc_180061F07
0x180061ed1  mov     dword ptr [rsp+60h+var_28], ebx
0x180061ed5  lea     rax, pszValue; "LocalizedString"
0x180061edc  mov     [rsp+60h+pszDirectory], rax
0x180061ee1  mov     r8d, 1E1h
0x180061ee7  lea     rax, [rsi+70h]
0x180061eeb  mov     rdx, r12
0x180061eee  mov     [rsp+60h+lpcbData], rax
0x180061ef3  mov     rcx, r13
0x180061ef6  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x180061efd  mov     [rsp+60h+phkResult], rax
0x180061f02  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x180061f07  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180061f0e  mov     r8, rdi; lpMem
0x180061f11  xor     edx, edx; dwFlags
0x180061f13  call    cs:__imp_HeapFree
0x180061f19  test    ebx, ebx
0x180061f1b  js      loc_180062050
0x180061f21  mov     r9d, [rsi+0ECh]
0x180061f28  lea     rax, [rbp+Type]
0x180061f2c  mov     rcx, [rbp+hKey]; hKey
0x180061f30  lea     rdx, ?LocalServer32@Constants@Catalog@Com@@3QBGB; "LocalServer32"
0x180061f37  mov     r12d, 20019h
0x180061f3d  mov     [rbp+Type], 0
0x180061f45  or      r9d, r12d; samDesired
0x180061f48  mov     [rsp+60h+phkResult], rax; phkResult
0x180061f4d  xor     r8d, r8d; ulOptions
0x180061f50  call    cs:__imp_RegOpenKeyExW
0x180061f56  mov     ebx, eax
0x180061f58  test    eax, eax
0x180061f5a  jnz     short loc_180061FB1
0x180061f5c  mov     rcx, [rbp+Type]; hkey
0x180061f60  lea     rdi, [rsi+148h]
0x180061f67  xor     r9d, r9d; unsigned int
0x180061f6a  mov     [rsp+60h+phkResult], rdi; unsigned __int16 **
0x180061f6f  lea     r8, ?ServerExecutable@Constants@Catalog@Com@@3QBGB; "ServerExecutable"
0x180061f76  xor     edx, edx; lpSubKey
0x180061f78  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180061f7d  cmp     eax, r14d
0x180061f80  cmovnz  ebx, eax
0x180061f83  test    ebx, ebx
0x180061f85  js      short loc_180061FA5
0x180061f87  cmp     qword ptr [rdi], 0
0x180061f8b  jnz     short loc_180061FA5
0x180061f8d  mov     rcx, [rbp+Type]; hkey
0x180061f91  xor     r9d, r9d; unsigned int
0x180061f94  xor     r8d, r8d; lpValue
0x180061f97  mov     [rsp+60h+phkResult], rdi; unsigned __int16 **
0x180061f9c  xor     edx, edx; lpSubKey
0x180061f9e  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180061fa3  mov     ebx, eax
0x180061fa5  mov     rcx, [rbp+Type]; hKey
0x180061fa9  call    cs:__imp_RegCloseKey
0x180061faf  jmp     short loc_180061FC0
0x180061fb1  jle     short loc_180061FB9
0x180061fb3  movzx   ebx, ax
0x180061fb6  or      ebx, r15d
0x180061fb9  lea     rdi, [rsi+148h]
0x180061fc0  mov     ecx, 80000000h
0x180061fc5  lea     eax, [rbx+rcx]
0x180061fc8  test    ecx, eax
0x180061fca  jnz     short loc_180061FD1
0x180061fcc  cmp     ebx, r14d
0x180061fcf  jnz     short loc_180062050
0x180061fd1  xor     eax, eax
0x180061fd3  cmp     ebx, r14d
0x180061fd6  cmovnz  eax, ebx
0x180061fd9  cmp     qword ptr [rdi], 0
0x180061fdd  mov     ebx, eax
0x180061fdf  jnz     short loc_180062050
0x180061fe1  mov     r9d, [rsi+0ECh]
0x180061fe8  lea     rax, [rbp+Type]
0x180061fec  mov     rcx, [rbp+hKey]; hKey
0x180061ff0  lea     rdx, ?InprocServer32@Constants@Catalog@Com@@3QBGB; "InprocServer32"
0x180061ff7  or      r9d, r12d; samDesired
0x180061ffa  mov     [rbp+Type], 0
0x180062002  xor     r8d, r8d; ulOptions
0x180062005  mov     [rsp+60h+phkResult], rax; phkResult
0x18006200a  call    cs:__imp_RegOpenKeyExW
0x180062010  mov     ebx, eax
0x180062012  test    eax, eax
0x180062014  jnz     short loc_18006203A
0x180062016  mov     rcx, [rbp+Type]; hkey
  ... truncated ...
```
