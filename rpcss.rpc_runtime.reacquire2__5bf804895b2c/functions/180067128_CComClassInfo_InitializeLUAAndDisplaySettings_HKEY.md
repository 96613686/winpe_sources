# CComClassInfo::InitializeLUAAndDisplaySettings(HKEY__ *)

- ea: `0x180067128`
- end: `0x18006770d`
- name: `?InitializeLUAAndDisplaySettings@CComClassInfo@@AEAAJPEAUHKEY__@@@Z`
- size: `1509`
- prototype: `int(CComClassInfo *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180040264`

## callees

- `0x180034260`
- `0x18005bcb0`
- `0x180067128`
- `0x180074d98`
- `0x1800a543c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800674f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800674f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006742a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006742a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006759b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067634`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006765c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006759b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067634`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006765c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800671a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800671e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006753c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067606`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800671a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800671e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006753c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067606`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180067242`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180067242`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180067470`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180067470`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18006716e`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800676e6`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18006716e`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800676e6`

## string_xrefs

- `0x180067202`: `onecore\com\combase\catalog\class.cxx`
- `0x1800676c2`: `onecore\com\combase\catalog\class.cxx`
- `0x1800671f2`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x1800672e6`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x180067378`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x1800674dc`: `CLSID:%ws Value:%ws %!HRESULT!`
- `0x1800676a1`: `CLSID:%ws %!HRESULT!`
- `0x1800671fb`: `CComClassInfo::InitializeLUAAndDisplaySettings`
- `0x1800676ad`: `CComClassInfo::InitializeLUAAndDisplaySettings`

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
      if ( v11 != -2147024894 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
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
      if ( v14 != -2147024894 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
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
          if ( v11 < 0 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
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
              if ( v6 != -2147024894 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
  if ( v6 != -2147024894 && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
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
0x180067128  mov     [rsp-38h+arg_8], rbx
0x18006712d  push    rbp
0x18006712e  push    rsi
0x18006712f  push    rdi
0x180067130  push    r12
0x180067132  push    r13
0x180067134  push    r14
0x180067136  push    r15
0x180067138  mov     rbp, rsp
0x18006713b  sub     rsp, 60h
0x18006713f  cmp     dword ptr [rcx+0ECh], 200h
0x180067149  mov     rbx, rdx
0x18006714c  mov     rsi, rcx
0x18006714f  mov     [rbp+Data], 0
0x180067156  mov     [rbp+hKey], 0
0x18006715e  mov     [rbp+arg_18], 0
0x180067165  jnz     short loc_18006717E
0x180067167  movzx   ecx, word ptr [rcx+0F0h]
0x18006716e  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x180067175  nop     dword ptr [rax+rax+00h]
0x18006717a  mov     word ptr [rbp+arg_18], ax
0x18006717e  mov     r9d, [rsi+0ECh]
0x180067185  lea     rax, [rbp+hKey]
0x180067189  lea     rdi, [rsi+70h]
0x18006718d  mov     [rsp+60h+phkResult], rax; phkResult
0x180067192  mov     r14d, 20019h
0x180067198  mov     rdx, rdi; lpSubKey
0x18006719b  or      r9d, r14d; samDesired
0x18006719e  xor     r8d, r8d; ulOptions
0x1800671a1  mov     rcx, rbx; hKey
0x1800671a4  call    cs:__imp_RegOpenKeyExW
0x1800671ab  nop     dword ptr [rax+rax+00h]
0x1800671b0  mov     ebx, eax
0x1800671b2  test    eax, eax
0x1800671b4  jnz     loc_18006766A
0x1800671ba  mov     r9d, [rsi+0ECh]
0x1800671c1  lea     rax, [rbp+hkey]
0x1800671c5  mov     rcx, [rbp+hKey]; hKey
0x1800671c9  lea     rbx, aElevation; "Elevation"
0x1800671d0  or      r9d, r14d; samDesired
0x1800671d3  mov     [rbp+hkey], 0
0x1800671db  mov     rdx, rbx; lpSubKey
0x1800671de  mov     [rsp+60h+phkResult], rax; phkResult
0x1800671e3  xor     r8d, r8d; ulOptions
0x1800671e6  call    cs:__imp_RegOpenKeyExW
0x1800671ed  nop     dword ptr [rax+rax+00h]
0x1800671f2  lea     r8, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x1800671f9  mov     edi, eax
0x1800671fb  lea     r12, aCcomclassinfoI_2; "CComClassInfo::InitializeLUAAndDisplayS"...
0x180067202  lea     r13, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180067209  test    eax, eax
0x18006720b  jnz     loc_18006739E
0x180067211  mov     rcx, [rbp+hkey]; hKey
0x180067215  lea     rdi, ValueName; "Enabled"
0x18006721c  mov     dword ptr [rbp+Type], eax
0x18006721f  lea     r9, [rbp+Type]; lpType
0x180067223  lea     rax, [rbp+cbData]
0x180067227  mov     [rbp+cbData], 4
0x18006722e  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180067233  xor     r8d, r8d; lpReserved
0x180067236  lea     rax, [rbp+Data]
0x18006723a  mov     rdx, rdi; lpValueName
0x18006723d  mov     [rsp+60h+phkResult], rax; lpData
0x180067242  call    cs:__imp_RegQueryValueExW
0x180067249  nop     dword ptr [rax+rax+00h]
0x18006724e  mov     r15d, 80070000h
0x180067254  mov     ebx, eax
0x180067256  lea     r14d, [r15+2]
0x18006725a  test    eax, eax
0x18006725c  jnz     short loc_18006729E
0x18006725e  cmp     dword ptr [rbp+Type], 4
0x180067262  jnz     short loc_180067274
0x180067264  mov     eax, [rbp+Data]
0x180067267  xor     edi, edi
0x180067269  mov     [rsi+134h], eax
0x18006726f  jmp     loc_180067307
0x180067274  mov     eax, cs:dword_1801574B8
0x18006727a  mov     ebx, 80040153h
0x18006727f  test    eax, eax
0x180067281  jnz     short loc_180067296
0x180067283  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180067289  jz      short loc_1800672F7
0x18006728b  xor     ecx, ecx
0x18006728d  call    IsWppLevelEnabled
0x180067292  test    al, al
0x180067294  jz      short loc_1800672F7
0x180067296  mov     r8d, 1ABh
0x18006729c  jmp     short loc_1800672CE
0x18006729e  jle     short loc_1800672A6
0x1800672a0  movzx   ebx, ax
0x1800672a3  or      ebx, r15d
0x1800672a6  cmp     ebx, r14d
0x1800672a9  jz      short loc_1800672F7
0x1800672ab  mov     eax, cs:dword_1801574B8
0x1800672b1  test    eax, eax
0x1800672b3  jnz     short loc_1800672C8
0x1800672b5  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800672bb  jz      short loc_1800672F7
0x1800672bd  xor     ecx, ecx
0x1800672bf  call    IsWppLevelEnabled
0x1800672c4  test    al, al
0x1800672c6  jz      short loc_1800672F7
0x1800672c8  mov     r8d, 1B4h
0x1800672ce  mov     dword ptr [rsp+60h+var_28], ebx
0x1800672d2  lea     rax, [rsi+70h]
0x1800672d6  mov     [rsp+60h+pszDirectory], rdi
0x1800672db  mov     rdx, r12
0x1800672de  mov     [rsp+60h+lpcbData], rax
0x1800672e3  mov     rcx, r13
0x1800672e6  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x1800672ed  mov     [rsp+60h+phkResult], rax
0x1800672f2  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x1800672f7  xor     edi, edi
0x1800672f9  cmp     ebx, r14d
0x1800672fc  cmovnz  edi, ebx
0x1800672ff  test    edi, edi
0x180067301  js      loc_18006738C
0x180067307  cmp     dword ptr [rsi+134h], 0
0x18006730e  jz      short loc_18006738C
0x180067310  mov     rcx, [rbp+hkey]; hkey
0x180067314  lea     rax, [rsi+150h]
0x18006731b  lea     rbx, aIconreference; "IconReference"
0x180067322  mov     [rsp+60h+phkResult], rax; unsigned __int16 **
0x180067327  mov     r8, rbx; lpValue
0x18006732a  xor     r9d, r9d; unsigned int
0x18006732d  xor     edx, edx; lpSubKey
0x18006732f  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180067334  xor     edi, edi
0x180067336  cmp     eax, r14d
0x180067339  cmovnz  edi, eax
0x18006733c  test    edi, edi
0x18006733e  jns     short loc_18006738C
0x180067340  mov     eax, cs:dword_1801574B8
0x180067346  test    eax, eax
0x180067348  jnz     short loc_18006735D
0x18006734a  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180067350  jz      short loc_18006738C
0x180067352  xor     ecx, ecx
0x180067354  call    IsWppLevelEnabled
0x180067359  test    al, al
0x18006735b  jz      short loc_18006738C
0x18006735d  mov     dword ptr [rsp+60h+var_28], edi
0x180067361  lea     rax, [rsi+70h]
0x180067365  mov     [rsp+60h+pszDirectory], rbx
0x18006736a  mov     r8d, 1C2h
0x180067370  mov     [rsp+60h+lpcbData], rax
0x180067375  mov     rdx, r12
0x180067378  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x18006737f  mov     rcx, r13
0x180067382  mov     [rsp+60h+phkResult], rax
0x180067387  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x18006738c  mov     rcx, [rbp+hkey]; hKey
0x180067390  call    cs:__imp_RegCloseKey
0x180067397  nop     dword ptr [rax+rax+00h]
0x18006739c  jmp     short loc_1800673FE
0x18006739e  mov     r15d, 80070000h
0x1800673a4  test    eax, eax
0x1800673a6  jle     short loc_1800673AE
0x1800673a8  movzx   edi, ax
0x1800673ab  or      edi, r15d
0x1800673ae  mov     r14d, 80070002h
0x1800673b4  cmp     edi, r14d
0x1800673b7  jz      short loc_1800673FE
0x1800673b9  mov     eax, cs:dword_1801574B8
0x1800673bf  test    eax, eax
0x1800673c1  jnz     short loc_1800673D6
0x1800673c3  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800673c9  jz      short loc_1800673FE
0x1800673cb  xor     ecx, ecx
0x1800673cd  call    IsWppLevelEnabled
0x1800673d2  test    al, al
0x1800673d4  jz      short loc_1800673FE
0x1800673d6  mov     dword ptr [rsp+60h+var_28], edi
0x1800673da  lea     rax, [rsi+70h]
0x1800673de  mov     [rsp+60h+pszDirectory], rbx
0x1800673e3  mov     rdx, r12
0x1800673e6  mov     [rsp+60h+lpcbData], rax
0x1800673eb  mov     rcx, r13
0x1800673ee  mov     [rsp+60h+phkResult], r8
0x1800673f3  mov     r8d, 1CDh
0x1800673f9  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x1800673fe  xor     ebx, ebx
0x180067400  cmp     edi, r14d
0x180067403  cmovnz  ebx, edi
0x180067406  test    ebx, ebx
0x180067408  js      loc_180067658
0x18006740e  cmp     dword ptr [rsi+134h], 0
0x180067415  jz      loc_180067658
0x18006741b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180067422  xor     edx, edx; dwFlags
0x180067424  mov     r8d, 200h; dwBytes
0x18006742a  call    cs:__imp_HeapAlloc
0x180067431  nop     dword ptr [rax+rax+00h]
0x180067436  mov     rdi, rax
0x180067439  test    rax, rax
0x18006743c  jz      loc_180067653
0x180067442  mov     rcx, [rbp+hKey]; hKey
0x180067446  lea     rdx, pszValue; "LocalizedString"
0x18006744d  mov     [rsp+60h+pszDirectory], 0; pszDirectory
0x180067456  mov     r9d, 200h; cbOutBuf
0x18006745c  mov     dword ptr [rsp+60h+lpcbData], 1; Flags
0x180067464  mov     r8, rax; pszOutBuf
0x180067467  mov     [rsp+60h+phkResult], 0; pcbData
0x180067470  call    cs:__imp_RegLoadMUIStringW
0x180067477  nop     dword ptr [rax+rax+00h]
0x18006747c  test    eax, eax
0x18006747e  jnz     short loc_180067489
0x180067480  mov     [rsi+140h], rdi
0x180067487  jmp     short loc_180067505
0x180067489  jg      short loc_18006748F
0x18006748b  mov     ebx, eax
0x18006748d  jmp     short loc_180067495
0x18006748f  movzx   ebx, ax
0x180067492  or      ebx, r15d
0x180067495  cmp     ebx, r14d
0x180067498  jz      short loc_1800674ED
0x18006749a  mov     eax, cs:dword_1801574B8
0x1800674a0  test    eax, eax
0x1800674a2  jnz     short loc_1800674B7
0x1800674a4  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800674aa  jz      short loc_1800674ED
0x1800674ac  xor     ecx, ecx
0x1800674ae  call    IsWppLevelEnabled
0x1800674b3  test    al, al
0x1800674b5  jz      short loc_1800674ED
0x1800674b7  mov     dword ptr [rsp+60h+var_28], ebx
0x1800674bb  lea     rax, pszValue; "LocalizedString"
0x1800674c2  mov     [rsp+60h+pszDirectory], rax
0x1800674c7  mov     r8d, 1E1h
0x1800674cd  lea     rax, [rsi+70h]
0x1800674d1  mov     rdx, r12
0x1800674d4  mov     [rsp+60h+lpcbData], rax
0x1800674d9  mov     rcx, r13
0x1800674dc  lea     rax, aClsidWsValueWs_0; "CLSID:%ws Value:%ws %!HRESULT!"
0x1800674e3  mov     [rsp+60h+phkResult], rax
0x1800674e8  call    ??$ComTraceMessageT@PEAGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2J@Z; ComTraceMessageT<ushort *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,long)
0x1800674ed  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800674f4  mov     r8, rdi; lpMem
0x1800674f7  xor     edx, edx; dwFlags
0x1800674f9  call    cs:__imp_HeapFree
0x180067500  nop     dword ptr [rax+rax+00h]
0x180067505  test    ebx, ebx
0x180067507  js      loc_180067658
0x18006750d  mov     r9d, [rsi+0ECh]
0x180067514  lea     rax, [rbp+Type]
0x180067518  mov     rcx, [rbp+hKey]; hKey
0x18006751c  lea     rdx, ?LocalServer32@Constants@Catalog@Com@@3QBGB; "LocalServer32"
0x180067523  mov     r12d, 20019h
0x180067529  mov     [rbp+Type], 0
0x180067531  or      r9d, r12d; samDesired
0x180067534  mov     [rsp+60h+phkResult], rax; phkResult
0x180067539  xor     r8d, r8d; ulOptions
0x18006753c  call    cs:__imp_RegOpenKeyExW
0x180067543  nop     dword ptr [rax+rax+00h]
0x180067548  mov     ebx, eax
0x18006754a  test    eax, eax
0x18006754c  jnz     short loc_1800675A9
0x18006754e  mov     rcx, [rbp+Type]; hkey
0x180067552  lea     rdi, [rsi+148h]
0x180067559  xor     r9d, r9d; unsigned int
0x18006755c  mov     [rsp+60h+phkResult], rdi; unsigned __int16 **
0x180067561  lea     r8, ?ServerExecutable@Constants@Catalog@Com@@3QBGB; "ServerExecutable"
0x180067568  xor     edx, edx; lpSubKey
0x18006756a  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x18006756f  cmp     eax, r14d
0x180067572  cmovnz  ebx, eax
0x180067575  test    ebx, ebx
0x180067577  js      short loc_180067597
0x180067579  cmp     qword ptr [rdi], 0
0x18006757d  jnz     short loc_180067597
0x18006757f  mov     rcx, [rbp+Type]; hkey
0x180067583  xor     r9d, r9d; unsigned int
0x180067586  xor     r8d, r8d; lpValue
0x180067589  mov     [rsp+60h+phkResult], rdi; unsigned __int16 **
0x18006758e  xor     edx, edx; lpSubKey
0x180067590  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEBG1KPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ulong,ushort * *)
0x180067595  mov     ebx, eax
0x180067597  mov     rcx, [rbp+Type]; hKey
0x18006759b  call    cs:__imp_RegCloseKey
0x1800675a2  nop     dword ptr [rax+rax+00h]
0x1800675a7  jmp     short loc_1800675B8
0x1800675a9  jle     short loc_1800675B1
0x1800675ab  movzx   ebx, ax
0x1800675ae  or      ebx, r15d
0x1800675b1  lea     rdi, [rsi+148h]
0x1800675b8  mov     ecx, 80000000h
0x1800675bd  lea     eax, [rbx+rcx]
0x1800675c0  test    ecx, eax
0x1800675c2  jnz     short loc_1800675CD
0x1800675c4  cmp     ebx, r14d
0x1800675c7  jnz     loc_180067658
0x1800675cd  xor     eax, eax
0x1800675cf  cmp     ebx, r14d
0x1800675d2  cmovnz  eax, ebx
0x1800675d5  cmp     qword ptr [rdi], 0
0x1800675d9  mov     ebx, eax
0x1800675db  jnz     short loc_180067658
0x1800675dd  mov     r9d, [rsi+0ECh]
0x1800675e4  lea     rax, [rbp+Type]
0x1800675e8  mov     rcx, [rbp+hKey]; hKey
  ... truncated ...
```
