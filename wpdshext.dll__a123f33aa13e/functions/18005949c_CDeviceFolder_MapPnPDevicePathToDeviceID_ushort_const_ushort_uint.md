# CDeviceFolder::_MapPnPDevicePathToDeviceID(ushort const *,ushort *,uint)

- ea: `0x18005949c`
- end: `0x1800598da`
- name: `?_MapPnPDevicePathToDeviceID@CDeviceFolder@@CAJPEBGPEAGI@Z`
- size: `1086`
- prototype: `__int64 __fastcall(PCWSTR psz1, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180059b60`

## callees

- `0x180004110`
- `0x18000d610`
- `0x180015700`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18005949c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180059593`
- `KERNEL32!GetLastError` at `0x18005960d`
- `KERNEL32!GetLastError` at `0x180059655`
- `KERNEL32!GetLastError` at `0x180059682`
- `KERNEL32!GetLastError` at `0x180059734`
- `KERNEL32!GetLastError` at `0x1800597b4`
- `KERNEL32!GetLastError` at `0x180059593`
- `KERNEL32!GetLastError` at `0x18005960d`
- `KERNEL32!GetLastError` at `0x180059655`
- `KERNEL32!GetLastError` at `0x180059682`
- `KERNEL32!GetLastError` at `0x180059734`
- `KERNEL32!GetLastError` at `0x1800597b4`
- `ADVAPI32!RegCloseKey` at `0x1800597a2`
- `ADVAPI32!RegCloseKey` at `0x1800597a2`
- `ADVAPI32!RegQueryValueExW` at `0x18005977a`
- `ADVAPI32!RegQueryValueExW` at `0x18005977a`
- `SHLWAPI!StrCmpW` at `0x1800596f2`
- `SHLWAPI!StrCmpW` at `0x1800596f2`
- `ole32!CLSIDFromString` at `0x180059522`
- `ole32!CLSIDFromString` at `0x180059522`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18005964b`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800596dc`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18005964b`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800596dc`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18005971e`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18005971e`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180059810`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180059810`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180059584`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180059584`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180059602`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180059602`

## pseudocode

```c
__int64 __fastcall CDeviceFolder::_MapPnPDevicePathToDeviceID(PCWSTR psz1, unsigned __int16 *a2)
{
  const WCHAR *v3; // rdi
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v4; // r15
  HRESULT v5; // eax
  signed int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  HDEVINFO ClassDevs; // r14
  signed int LastError; // eax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v12; // rsi
  DWORD v13; // r13d
  signed int v14; // eax
  const struct std::nothrow_t *v15; // rdx
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v16; // rax
  signed int v17; // eax
  HKEY v18; // rdi
  signed int v19; // eax
  signed int v20; // eax
  DWORD v21; // eax
  __int64 v22; // rdx
  DWORD RequiredSize; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR v27; // [rsp+50h] [rbp-B0h]
  CLSID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+68h] [rbp-98h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 Data[264]; // [rsp+B0h] [rbp-50h] BYREF

  v27 = psz1;
  v3 = psz1;
  memset_0(Data, 0, 0x208u);
  v4 = 0;
  RequiredSize = 0;
  Type = 0;
  pclsid = 0;
  if ( !v3 || !a2 )
  {
    v6 = -2147024809;
    goto LABEL_62;
  }
  v5 = CLSIDFromString(L"{6ac27878-a6fa-4155-ba85-f98f491d4f33}", &pclsid);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_63;
    v8 = 144;
    v9 = (unsigned int)v5;
LABEL_7:
    WPP_SF_d(v7[2], v8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v9);
LABEL_62:
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_63:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 )
      WPP_SF_d(v7[2], 148, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)v6);
    return (unsigned int)v6;
  }
  ClassDevs = SetupDiGetClassDevsExW(&pclsid, 0, 0, 0x12u, 0, 0, 0);
  if ( ClassDevs == (HDEVINFO)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_63;
      v8 = 145;
      v9 = (unsigned int)v6;
      goto LABEL_7;
    }
  }
  v12 = 0;
  v13 = 0;
  while ( 1 )
  {
    memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
    DeviceInterfaceData.cbSize = 32;
    if ( !SetupDiEnumDeviceInterfaces(ClassDevs, 0, &pclsid, v13, &DeviceInterfaceData) )
    {
      v14 = GetLastError();
      v6 = v14;
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      if ( v6 < 0 )
        break;
    }
    if ( !SetupDiGetDeviceInterfaceDetailW(ClassDevs, &DeviceInterfaceData, 0, 0, &RequiredSize, 0) )
    {
      if ( GetLastError() == 122 )
      {
        v16 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)operator new(RequiredSize, v15);
        v12 = v16;
        if ( !v16 )
        {
          v6 = -2147024882;
LABEL_58:
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v22 = 147;
            goto LABEL_56;
          }
          goto LABEL_49;
        }
        v4 = v16;
        v16->cbSize = 8;
        v6 = 0;
      }
      else
      {
        v17 = GetLastError();
        v6 = v17;
        if ( v17 > 0 )
          v6 = (unsigned __int16)v17 | 0x80070000;
        if ( v6 < 0 )
          goto LABEL_58;
      }
    }
    if ( v12 )
    {
      memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
      DeviceInfoData.cbSize = 32;
      if ( SetupDiGetDeviceInterfaceDetailW(ClassDevs, &DeviceInterfaceData, v12, RequiredSize, 0, &DeviceInfoData) )
      {
        if ( !StrCmpW(v3, v12->DevicePath) )
        {
          v18 = SetupDiOpenDevRegKey(ClassDevs, &DeviceInfoData, 1u, 0, 2u, 0x20019u);
          if ( (((unsigned __int64)v18 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          {
            v19 = GetLastError();
            v6 = v19;
            if ( v19 > 0 )
              v6 = (unsigned __int16)v19 | 0x80070000;
          }
          if ( !v6 )
          {
            cbData = 520;
            if ( !RegQueryValueExW(v18, L"DeviceID", 0, &Type, (LPBYTE)Data, &cbData) )
              StringCchCopyW(a2, 0x104u, Data);
          }
          if ( (unsigned __int64)v18 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            RegCloseKey(v18);
          v3 = v27;
          v6 = -2147024637;
        }
      }
      else
      {
        v20 = GetLastError();
        v6 = v20;
        if ( v20 > 0 )
          v6 = (unsigned __int16)v20 | 0x80070000;
      }
    }
    if ( v4 )
    {
      operator delete(v4);
      v4 = 0;
      v12 = 0;
    }
    v21 = v13 + 1;
    if ( v6 )
      v21 = v13;
    v13 = v21;
    if ( v6 )
    {
      if ( v6 == -2147024637 )
        v6 = 0;
      goto LABEL_48;
    }
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v22 = 146;
LABEL_56:
    WPP_SF_d(v7[2], v22, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)v6);
LABEL_48:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_49:
  if ( ClassDevs != (HDEVINFO)-1LL )
  {
    SetupDiDestroyDeviceInfoList(ClassDevs);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 < 0 )
    goto LABEL_63;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005949c  mov     [rsp-8+arg_10], rbx
0x1800594a1  push    rbp
0x1800594a2  push    rsi
0x1800594a3  push    rdi
0x1800594a4  push    r12
0x1800594a6  push    r13
0x1800594a8  push    r14
0x1800594aa  push    r15
0x1800594ac  lea     rbp, [rsp-1D0h]
0x1800594b4  sub     rsp, 2D0h
0x1800594bb  mov     rax, cs:__security_cookie
0x1800594c2  xor     rax, rsp
0x1800594c5  mov     [rbp+200h+var_40], rax
0x1800594cc  mov     r12, rdx
0x1800594cf  mov     [rsp+300h+var_2B0], rcx
0x1800594d4  mov     rdi, rcx
0x1800594d7  xor     edx, edx; Val
0x1800594d9  lea     rcx, [rbp+200h+Data]; void *
0x1800594dd  mov     r8d, 208h; Size
0x1800594e3  call    memset_0
0x1800594e8  xor     r15d, r15d
0x1800594eb  lea     rsi, WPP_GLOBAL_Control
0x1800594f2  mov     [rsp+300h+RequiredSize], r15d
0x1800594f7  xorps   xmm0, xmm0
0x1800594fa  mov     [rsp+300h+Type], r15d
0x1800594ff  movups  xmmword ptr [rsp+300h+pclsid.Data1], xmm0
0x180059504  test    rdi, rdi
0x180059507  jz      loc_18005987F
0x18005950d  test    r12, r12
0x180059510  jz      loc_18005987F
0x180059516  lea     rdx, [rsp+300h+pclsid]; pclsid
0x18005951b  lea     rcx, sz; "{6ac27878-a6fa-4155-ba85-f98f491d4f33}"
0x180059522  call    cs:__imp_CLSIDFromString
0x180059528  mov     ebx, eax
0x18005952a  test    eax, eax
0x18005952c  jns     short loc_180059565
0x18005952e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059535  cmp     rcx, rsi
0x180059538  jz      loc_1800598AE
0x18005953e  test    byte ptr [rcx+1Ch], 2
0x180059542  jz      loc_18005988B
0x180059548  mov     edx, 90h
0x18005954d  mov     r9d, eax
0x180059550  mov     rcx, [rcx+10h]
0x180059554  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x18005955b  call    WPP_SF_d
0x180059560  jmp     loc_180059884
0x180059565  mov     [rsp+300h+Reserved], r15; Reserved
0x18005956a  lea     rcx, [rsp+300h+pclsid]; ClassGuid
0x18005956f  mov     [rsp+300h+MachineName], r15; MachineName
0x180059574  mov     r9d, 12h; Flags
0x18005957a  xor     r8d, r8d; hwndParent
0x18005957d  mov     [rsp+300h+DeviceInfoSet], r15; DeviceInfoSet
0x180059582  xor     edx, edx; Enumerator
0x180059584  call    cs:__imp_SetupDiGetClassDevsExW
0x18005958a  mov     r14, rax
0x18005958d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180059591  jnz     short loc_1800595D0
0x180059593  call    cs:__imp_GetLastError
0x180059599  mov     ebx, eax
0x18005959b  test    eax, eax
0x18005959d  jle     short loc_1800595A8
0x18005959f  movzx   ebx, ax
0x1800595a2  or      ebx, 80070000h
0x1800595a8  test    ebx, ebx
0x1800595aa  jns     short loc_1800595D0
0x1800595ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800595b3  cmp     rcx, rsi
0x1800595b6  jz      loc_1800598AE
0x1800595bc  test    byte ptr [rcx+1Ch], 2
0x1800595c0  jz      loc_18005988B
0x1800595c6  mov     edx, 91h
0x1800595cb  mov     r9d, ebx
0x1800595ce  jmp     short loc_180059550
0x1800595d0  mov     rsi, r15
0x1800595d3  mov     r13d, r15d
0x1800595d6  xorps   xmm0, xmm0
0x1800595d9  lea     rax, [rsp+300h+DeviceInterfaceData]
0x1800595de  movups  xmmword ptr [rsp+300h+DeviceInterfaceData.cbSize], xmm0
0x1800595e3  mov     r9d, r13d; MemberIndex
0x1800595e6  mov     [rsp+300h+DeviceInterfaceData.cbSize], 20h ; ' '
0x1800595ee  lea     r8, [rsp+300h+pclsid]; InterfaceClassGuid
0x1800595f3  mov     [rsp+300h+DeviceInfoSet], rax; DeviceInterfaceData
0x1800595f8  xor     edx, edx; DeviceInfoData
0x1800595fa  mov     rcx, r14; DeviceInfoSet
0x1800595fd  movups  xmmword ptr [rsp+300h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x180059602  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x180059608  cmp     eax, 1
0x18005960b  jz      short loc_18005962A
0x18005960d  call    cs:__imp_GetLastError
0x180059613  mov     ebx, eax
0x180059615  test    eax, eax
0x180059617  jle     short loc_180059622
0x180059619  movzx   ebx, ax
0x18005961c  or      ebx, 80070000h
0x180059622  test    ebx, ebx
0x180059624  js      loc_180059827
0x18005962a  lea     rax, [rsp+300h+RequiredSize]
0x18005962f  mov     [rsp+300h+MachineName], 0; DeviceInfoData
0x180059638  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x18005963b  mov     [rsp+300h+DeviceInfoSet], rax; RequiredSize
0x180059640  xor     r8d, r8d; DeviceInterfaceDetailData
0x180059643  lea     rdx, [rsp+300h+DeviceInterfaceData]; DeviceInterfaceData
0x180059648  mov     rcx, r14; DeviceInfoSet
0x18005964b  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180059651  test    eax, eax
0x180059653  jnz     short loc_18005969F
0x180059655  call    cs:__imp_GetLastError
0x18005965b  cmp     eax, 7Ah ; 'z'
0x18005965e  jnz     short loc_180059682
0x180059660  mov     ecx, [rsp+300h+RequiredSize]; unsigned __int64
0x180059664  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180059669  mov     rsi, rax
0x18005966c  test    rax, rax
0x18005966f  jz      loc_18005985A
0x180059675  mov     r15, rax
0x180059678  mov     dword ptr [rax], 8
0x18005967e  xor     ebx, ebx
0x180059680  jmp     short loc_18005969F
0x180059682  call    cs:__imp_GetLastError
0x180059688  mov     ebx, eax
0x18005968a  test    eax, eax
0x18005968c  jle     short loc_180059697
0x18005968e  movzx   ebx, ax
0x180059691  or      ebx, 80070000h
0x180059697  test    ebx, ebx
0x180059699  js      loc_18005985F
0x18005969f  test    rsi, rsi
0x1800596a2  jz      loc_1800597C9
0x1800596a8  mov     r9d, [rsp+300h+RequiredSize]; DeviceInterfaceDetailDataSize
0x1800596ad  lea     rax, [rbp+200h+DeviceInfoData]
0x1800596b1  xorps   xmm0, xmm0
0x1800596b4  mov     [rsp+300h+MachineName], rax; DeviceInfoData
0x1800596b9  movups  xmmword ptr [rbp+200h+DeviceInfoData.cbSize], xmm0
0x1800596bd  mov     r8, rsi; DeviceInterfaceDetailData
0x1800596c0  mov     [rbp+200h+DeviceInfoData.cbSize], 20h ; ' '
0x1800596c7  lea     rdx, [rsp+300h+DeviceInterfaceData]; DeviceInterfaceData
0x1800596cc  mov     [rsp+300h+DeviceInfoSet], 0; RequiredSize
0x1800596d5  mov     rcx, r14; DeviceInfoSet
0x1800596d8  movups  xmmword ptr [rbp+200h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x1800596dc  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1800596e2  cmp     eax, 1
0x1800596e5  jnz     loc_1800597B4
0x1800596eb  lea     rdx, [rsi+4]; psz2
0x1800596ef  mov     rcx, rdi; psz1
0x1800596f2  call    cs:__imp_StrCmpW
0x1800596f8  test    eax, eax
0x1800596fa  jnz     loc_1800597C9
0x180059700  mov     dword ptr [rsp+300h+MachineName], 20019h; samDesired
0x180059708  lea     r8d, [rax+1]; Scope
0x18005970c  xor     r9d, r9d; HwProfile
0x18005970f  mov     dword ptr [rsp+300h+DeviceInfoSet], 2; KeyType
0x180059717  lea     rdx, [rbp+200h+DeviceInfoData]; DeviceInfoData
0x18005971b  mov     rcx, r14; DeviceInfoSet
0x18005971e  call    cs:__imp_SetupDiOpenDevRegKey
0x180059724  mov     rdi, rax
0x180059727  lea     rcx, [rax+1]
0x18005972b  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180059732  jnz     short loc_180059749
0x180059734  call    cs:__imp_GetLastError
0x18005973a  mov     ebx, eax
0x18005973c  test    eax, eax
0x18005973e  jle     short loc_180059749
0x180059740  movzx   ebx, ax
0x180059743  or      ebx, 80070000h
0x180059749  test    ebx, ebx
0x18005974b  jnz     short loc_180059795
0x18005974d  lea     rax, [rsp+300h+cbData]
0x180059752  mov     [rsp+300h+cbData], 208h
0x18005975a  mov     [rsp+300h+MachineName], rax; lpcbData
0x18005975f  lea     r9, [rsp+300h+Type]; lpType
0x180059764  lea     rax, [rbp+200h+Data]
0x180059768  xor     r8d, r8d; lpReserved
0x18005976b  lea     rdx, ValueName; "DeviceID"
0x180059772  mov     [rsp+300h+DeviceInfoSet], rax; lpData
0x180059777  mov     rcx, rdi; hKey
0x18005977a  call    cs:__imp_RegQueryValueExW
0x180059780  test    eax, eax
0x180059782  jnz     short loc_180059795
0x180059784  lea     r8, [rbp+200h+Data]; unsigned __int16 *
0x180059788  mov     edx, 104h; unsigned __int64
0x18005978d  mov     rcx, r12; unsigned __int16 *
0x180059790  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180059795  lea     rax, [rdi-1]
0x180059799  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005979d  ja      short loc_1800597A8
0x18005979f  mov     rcx, rdi; hKey
0x1800597a2  call    cs:__imp_RegCloseKey
0x1800597a8  mov     rdi, [rsp+300h+var_2B0]
0x1800597ad  mov     ebx, 80070103h
0x1800597b2  jmp     short loc_1800597C9
0x1800597b4  call    cs:__imp_GetLastError
0x1800597ba  mov     ebx, eax
0x1800597bc  test    eax, eax
0x1800597be  jle     short loc_1800597C9
0x1800597c0  movzx   ebx, ax
0x1800597c3  or      ebx, 80070000h
0x1800597c9  test    r15, r15
0x1800597cc  jz      short loc_1800597DB
0x1800597ce  mov     rcx, r15; lpMem
0x1800597d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800597d6  xor     r15d, r15d
0x1800597d9  xor     esi, esi
0x1800597db  lea     eax, [r13+1]
0x1800597df  test    ebx, ebx
0x1800597e1  cmovnz  eax, r13d
0x1800597e5  mov     r13d, eax
0x1800597e8  jz      loc_1800595D6
0x1800597ee  xor     eax, eax
0x1800597f0  lea     rsi, WPP_GLOBAL_Control
0x1800597f7  cmp     ebx, 80070103h
0x1800597fd  cmovz   ebx, eax
0x180059800  mov     rcx, cs:WPP_GLOBAL_Control
0x180059807  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18005980b  jz      short loc_18005981D
0x18005980d  mov     rcx, r14; DeviceInfoSet
0x180059810  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180059816  mov     rcx, cs:WPP_GLOBAL_Control
0x18005981d  test    ebx, ebx
0x18005981f  jns     loc_1800598AE
0x180059825  jmp     short loc_18005988B
0x180059827  mov     rcx, cs:WPP_GLOBAL_Control
0x18005982e  lea     rsi, WPP_GLOBAL_Control
0x180059835  cmp     rcx, rsi
0x180059838  jz      short loc_180059807
0x18005983a  test    byte ptr [rcx+1Ch], 2
0x18005983e  jz      short loc_180059807
0x180059840  mov     edx, 92h
0x180059845  mov     rcx, [rcx+10h]
0x180059849  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x180059850  mov     r9d, ebx
0x180059853  call    WPP_SF_d
0x180059858  jmp     short loc_180059800
0x18005985a  mov     ebx, 8007000Eh
0x18005985f  mov     rcx, cs:WPP_GLOBAL_Control
0x180059866  lea     rsi, WPP_GLOBAL_Control
0x18005986d  cmp     rcx, rsi
0x180059870  jz      short loc_180059807
0x180059872  test    byte ptr [rcx+1Ch], 2
0x180059876  jz      short loc_180059807
0x180059878  mov     edx, 93h
0x18005987d  jmp     short loc_180059845
0x18005987f  mov     ebx, 80070057h
0x180059884  mov     rcx, cs:WPP_GLOBAL_Control
0x18005988b  cmp     rcx, rsi
0x18005988e  jz      short loc_1800598AE
0x180059890  test    byte ptr [rcx+1Ch], 2
0x180059894  jz      short loc_1800598AE
0x180059896  mov     rcx, [rcx+10h]
0x18005989a  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x1800598a1  mov     edx, 94h
0x1800598a6  mov     r9d, ebx
0x1800598a9  call    WPP_SF_d
0x1800598ae  mov     eax, ebx
0x1800598b0  mov     rcx, [rbp+200h+var_40]
0x1800598b7  xor     rcx, rsp; StackCookie
0x1800598ba  call    __security_check_cookie
0x1800598bf  mov     rbx, [rsp+300h+arg_10]
0x1800598c7  add     rsp, 2D0h
0x1800598ce  pop     r15
0x1800598d0  pop     r14
0x1800598d2  pop     r13
0x1800598d4  pop     r12
0x1800598d6  pop     rdi
0x1800598d7  pop     rsi
0x1800598d8  pop     rbp
0x1800598d9  retn
```
