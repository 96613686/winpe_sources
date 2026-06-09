# CVistaInterfaceSettings::LoadUnnamedProfileMetadata(HKEY__ *,_GUID,ulong *,ulong *,bool *,_SE_SID *)

- ea: `0x1801c1b14`
- end: `0x1801c1f05`
- name: `?LoadUnnamedProfileMetadata@CVistaInterfaceSettings@@QEAAJPEAUHKEY__@@U_GUID@@PEAK2PEA_NPEAT_SE_SID@@@Z`
- size: `1009`
- prototype: `int(CVistaInterfaceSettings *__hidden this, HKEY, struct _GUID *__struct_ptr, unsigned int *, unsigned int *, bool *, union _SE_SID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801c1500`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180036110`
- `0x1800c6774`
- `0x180106340`
- `0x180107330`
- `0x18014899c`
- `0x1801c1b14`
- `0x18020b330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1801c1c47`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1801c1c47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801c1cf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801c1d98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801c1e39`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801c1cf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801c1d98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801c1e39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801c1c67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801c1c67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801c1e9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801c1e9a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801c1e80`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801c1e80`

## pseudocode

```c
__int64 __fastcall CVistaInterfaceSettings::LoadUnnamedProfileMetadata(
        CVistaInterfaceSettings *this,
        HKEY a2,
        struct _GUID *a3,
        unsigned int *a4,
        unsigned int *a5,
        bool *a6,
        union _SE_SID *pDestinationSid)
{
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int64 v12; // r8
  LSTATUS v13; // eax
  int v14; // ebx
  PVOID *v15; // rcx
  bool v16; // sf
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  unsigned int v19; // eax
  BYTE v21[4]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD lpcbData; // [rsp+48h] [rbp-B8h] BYREF
  BYTE pSourceSid; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[79]; // [rsp+51h] [rbp-AFh] BYREF
  unsigned __int16 v28[56]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[10]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v30[508]; // [rsp+124h] [rbp+24h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids);
  *(_DWORD *)Data = 0;
  *(_DWORD *)v21 = 0;
  cbData = 4;
  lpcbData = 68;
  pSourceSid = 0;
  memset_0(v27, 0, 0x43u);
  wcscpy(SubKey, L"Profiles\\");
  memset_0(v30, 0, 0x1F4u);
  hKey = 0;
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
  if ( !pDestinationSid )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  if ( GuidToString(a3, v28, v12) < 0 )
    goto LABEL_45;
  _o_wcscat_s(SubKey, 260, v28);
  v13 = RegOpenKeyExW(a2, SubKey, 0, 0x20019u, &hKey);
  v14 = v13;
  if ( !v13 )
    goto LABEL_20;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_52a1f548083e30a540d04b5cd764f693_Traceguids,
      (unsigned int)v28,
      v13);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  v16 = v14 < 0;
  if ( v14 > 0 )
    v16 = 1;
  if ( !v16 )
  {
LABEL_20:
    v17 = RegQueryValueExW(hKey, L"ProfileIndex", 0, 0, Data, &cbData);
    if ( v17 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids, 2);
      *(_DWORD *)Data = 0;
    }
    else if ( v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_52a1f548083e30a540d04b5cd764f693_Traceguids,
          (unsigned int)L"ProfileIndex",
          v17);
    }
    else
    {
      *a4 = *(_DWORD *)Data;
    }
    v18 = RegQueryValueExW(hKey, L"Flags", 0, 0, v21, &cbData);
    if ( v18 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids, 2);
      *(_DWORD *)v21 = 0;
    }
    else if ( v18 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)WPP_52a1f548083e30a540d04b5cd764f693_Traceguids,
          (unsigned int)L"Flags",
          v18);
    }
    else
    {
      *a5 = *(_DWORD *)v21;
    }
    v19 = RegQueryValueExW(hKey, L"SID", 0, 0, &pSourceSid, &lpcbData);
    if ( !v19 )
    {
      *a6 = 1;
      CopySid(0x44u, pDestinationSid, &pSourceSid);
      goto LABEL_45;
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids, v19);
LABEL_45:
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x10) != 0 )
    WPP_SF_Sdd(
      (unsigned int)v15[2],
      23,
      (unsigned int)WPP_52a1f548083e30a540d04b5cd764f693_Traceguids,
      (unsigned int)SubKey,
      Data[0],
      v21[0]);
  return 0;
}

```

## disassembly

```asm
0x1801c1b14  push    rbp
0x1801c1b16  push    rbx
0x1801c1b17  push    rsi
0x1801c1b18  push    rdi
0x1801c1b19  push    r12
0x1801c1b1b  push    r14
0x1801c1b1d  push    r15
0x1801c1b1f  lea     rbp, [rsp-230h]
0x1801c1b27  sub     rsp, 330h
0x1801c1b2e  mov     rax, cs:__security_cookie
0x1801c1b35  xor     rax, rsp
0x1801c1b38  mov     [rbp+260h+var_40], rax
0x1801c1b3f  mov     rsi, [rbp+260h+arg_20]
0x1801c1b46  mov     rdi, r9
0x1801c1b49  mov     r15, [rbp+260h+arg_28]
0x1801c1b50  mov     rbx, r8
0x1801c1b53  mov     r12, [rbp+260h+pDestinationSid]
0x1801c1b5a  mov     r14, rdx
0x1801c1b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1b64  lea     rax, WPP_GLOBAL_Control
0x1801c1b6b  cmp     rcx, rax
0x1801c1b6e  jz      short loc_1801C1B8B
0x1801c1b70  test    byte ptr [rcx+1Ch], 10h
0x1801c1b74  jz      short loc_1801C1B8B
0x1801c1b76  mov     rcx, [rcx+10h]
0x1801c1b7a  lea     r8, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids
0x1801c1b81  mov     edx, 10h
0x1801c1b86  call    WPP_SF_
0x1801c1b8b  xor     edx, edx; Val
0x1801c1b8d  mov     dword ptr [rsp+360h+Data], 0
0x1801c1b95  lea     rcx, [rsp+360h+var_30F]; void *
0x1801c1b9a  mov     dword ptr [rsp+360h+var_330], 0
0x1801c1ba2  mov     [rsp+360h+cbData], 4
0x1801c1baa  mov     [rsp+360h+var_318], 44h ; 'D'
0x1801c1bb2  lea     r8d, [rdx+43h]; Size
0x1801c1bb6  mov     [rsp+360h+pSourceSid], 0
0x1801c1bbb  call    memset_0
0x1801c1bc0  movups  xmm0, xmmword ptr cs:aProfiles_0; "Profiles\\"
0x1801c1bc7  mov     eax, dword ptr cs:aProfiles_0+10h; "\\"
0x1801c1bcd  lea     rcx, [rbp+260h+var_23C]; void *
0x1801c1bd1  xor     edx, edx; Val
0x1801c1bd3  mov     [rbp+260h+var_240], eax
0x1801c1bd6  mov     r8d, 1F4h; Size
0x1801c1bdc  movaps  xmmword ptr [rbp+260h+SubKey], xmm0
0x1801c1be0  call    memset_0
0x1801c1be5  mov     [rsp+360h+hKey], 0
0x1801c1bee  test    rdi, rdi
0x1801c1bf1  jnz     short loc_1801C1BF8
0x1801c1bf3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pdwProfileIndex")
0x1801c1bf8  test    rsi, rsi
0x1801c1bfb  jnz     short loc_1801C1C02
0x1801c1bfd  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pdwFlags")
0x1801c1c02  test    r15, r15
0x1801c1c05  jnz     short loc_1801C1C0C
0x1801c1c07  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pIsPerUser")
0x1801c1c0c  test    r12, r12
0x1801c1c0f  jnz     short loc_1801C1C16
0x1801c1c11  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "ownerSid")
0x1801c1c16  mov     dword ptr [rdi], 0
0x1801c1c1c  lea     rdx, [rbp+260h+var_2C0]; unsigned __int16 *
0x1801c1c20  mov     dword ptr [rsi], 0
0x1801c1c26  mov     rcx, rbx; struct _GUID *
0x1801c1c29  mov     byte ptr [r15], 0
0x1801c1c2d  call    ?GuidToString@@YAJAEAU_GUID@@PEAG_K@Z; GuidToString(_GUID &,ushort *,unsigned __int64)
0x1801c1c32  test    eax, eax
0x1801c1c34  js      loc_1801C1E86
0x1801c1c3a  lea     r8, [rbp+260h+var_2C0]
0x1801c1c3e  mov     edx, 104h
0x1801c1c43  lea     rcx, [rbp+260h+SubKey]
0x1801c1c47  call    cs:__imp__o_wcscat_s
0x1801c1c4d  lea     rax, [rsp+360h+hKey]
0x1801c1c52  mov     r9d, 20019h; samDesired
0x1801c1c58  xor     r8d, r8d; ulOptions
0x1801c1c5b  mov     [rsp+360h+phkResult], rax; phkResult
0x1801c1c60  lea     rdx, [rbp+260h+SubKey]; lpSubKey
0x1801c1c64  mov     rcx, r14; hKey
0x1801c1c67  call    cs:__imp_RegOpenKeyExW
0x1801c1c6d  mov     ebx, eax
0x1801c1c6f  test    eax, eax
0x1801c1c71  jz      short loc_1801C1CC7
0x1801c1c73  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1c7a  lea     r14, WPP_GLOBAL_Control
0x1801c1c81  cmp     rcx, r14
0x1801c1c84  jz      short loc_1801C1CB0
0x1801c1c86  test    byte ptr [rcx+1Ch], 2
0x1801c1c8a  jz      short loc_1801C1CB0
0x1801c1c8c  mov     rcx, [rcx+10h]
0x1801c1c90  lea     r9, [rbp+260h+var_2C0]
0x1801c1c94  mov     edx, 11h
0x1801c1c99  mov     dword ptr [rsp+360h+phkResult], eax
0x1801c1c9d  lea     r8, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids
0x1801c1ca4  call    WPP_SF_SD
0x1801c1ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1cb0  test    ebx, ebx
0x1801c1cb2  jle     short loc_1801C1CBF
0x1801c1cb4  movzx   ebx, bx
0x1801c1cb7  or      ebx, 80070000h
0x1801c1cbd  test    ebx, ebx
0x1801c1cbf  js      loc_1801C1E8D
0x1801c1cc5  jmp     short loc_1801C1CCE
0x1801c1cc7  lea     r14, WPP_GLOBAL_Control
0x1801c1cce  mov     rcx, [rsp+360h+hKey]; hKey
0x1801c1cd3  lea     rax, [rsp+360h+cbData]
0x1801c1cd8  mov     [rsp+360h+lpcbData], rax; lpcbData
0x1801c1cdd  lea     rdx, aProfileindex_1; "ProfileIndex"
0x1801c1ce4  lea     rax, [rsp+360h+Data]
0x1801c1ce9  xor     r9d, r9d; lpType
0x1801c1cec  xor     r8d, r8d; lpReserved
0x1801c1cef  mov     [rsp+360h+phkResult], rax; lpData
0x1801c1cf4  call    cs:__imp_RegQueryValueExW
0x1801c1cfa  mov     ebx, 2
0x1801c1cff  cmp     eax, ebx
0x1801c1d01  jnz     short loc_1801C1D35
0x1801c1d03  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1d0a  cmp     rcx, r14
0x1801c1d0d  jz      short loc_1801C1D2B
0x1801c1d0f  test    byte ptr [rcx+1Ch], 10h
0x1801c1d13  jz      short loc_1801C1D2B
0x1801c1d15  mov     rcx, [rcx+10h]
0x1801c1d19  lea     edx, [rbx+10h]
0x1801c1d1c  mov     r9d, ebx
0x1801c1d1f  lea     r8, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids
0x1801c1d26  call    WPP_SF_d
0x1801c1d2b  mov     dword ptr [rsp+360h+Data], 0
0x1801c1d33  jmp     short loc_1801C1D72
0x1801c1d35  test    eax, eax
0x1801c1d37  jz      short loc_1801C1D6C
0x1801c1d39  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1d40  cmp     rcx, r14
0x1801c1d43  jz      short loc_1801C1D72
0x1801c1d45  test    [rcx+1Ch], bl
0x1801c1d48  jz      short loc_1801C1D72
0x1801c1d4a  mov     rcx, [rcx+10h]
0x1801c1d4e  lea     r9, aProfileindex_1; "ProfileIndex"
0x1801c1d55  mov     edx, 13h
0x1801c1d5a  mov     dword ptr [rsp+360h+phkResult], eax
0x1801c1d5e  lea     r8, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids
0x1801c1d65  call    WPP_SF_SD
0x1801c1d6a  jmp     short loc_1801C1D72
0x1801c1d6c  mov     eax, dword ptr [rsp+360h+Data]
0x1801c1d70  mov     [rdi], eax
0x1801c1d72  mov     rcx, [rsp+360h+hKey]; hKey
0x1801c1d77  lea     rax, [rsp+360h+cbData]
0x1801c1d7c  mov     [rsp+360h+lpcbData], rax; lpcbData
0x1801c1d81  lea     rdx, aFlags_2; "Flags"
0x1801c1d88  lea     rax, [rsp+360h+var_330]
0x1801c1d8d  xor     r9d, r9d; lpType
0x1801c1d90  xor     r8d, r8d; lpReserved
0x1801c1d93  mov     [rsp+360h+phkResult], rax; lpData
0x1801c1d98  call    cs:__imp_RegQueryValueExW
0x1801c1d9e  cmp     eax, ebx
0x1801c1da0  jnz     short loc_1801C1DD6
0x1801c1da2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1da9  cmp     rcx, r14
0x1801c1dac  jz      short loc_1801C1DCC
0x1801c1dae  test    byte ptr [rcx+1Ch], 10h
0x1801c1db2  jz      short loc_1801C1DCC
0x1801c1db4  mov     rcx, [rcx+10h]
0x1801c1db8  lea     r8, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids
0x1801c1dbf  mov     edx, 14h
0x1801c1dc4  mov     r9d, ebx
0x1801c1dc7  call    WPP_SF_d
0x1801c1dcc  mov     dword ptr [rsp+360h+var_330], 0
0x1801c1dd4  jmp     short loc_1801C1E13
0x1801c1dd6  test    eax, eax
0x1801c1dd8  jz      short loc_1801C1E0D
0x1801c1dda  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1de1  cmp     rcx, r14
0x1801c1de4  jz      short loc_1801C1E13
0x1801c1de6  test    [rcx+1Ch], bl
0x1801c1de9  jz      short loc_1801C1E13
0x1801c1deb  mov     rcx, [rcx+10h]
0x1801c1def  lea     r9, aFlags_2; "Flags"
0x1801c1df6  mov     edx, 15h
0x1801c1dfb  mov     dword ptr [rsp+360h+phkResult], eax
0x1801c1dff  lea     r8, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids
0x1801c1e06  call    WPP_SF_SD
0x1801c1e0b  jmp     short loc_1801C1E13
0x1801c1e0d  mov     eax, dword ptr [rsp+360h+var_330]
0x1801c1e11  mov     [rsi], eax
0x1801c1e13  mov     rcx, [rsp+360h+hKey]; hKey
0x1801c1e18  lea     rax, [rsp+360h+var_318]
0x1801c1e1d  mov     [rsp+360h+lpcbData], rax; lpcbData
0x1801c1e22  lea     rdx, aSid_0; "SID"
0x1801c1e29  lea     rax, [rsp+360h+pSourceSid]
0x1801c1e2e  xor     r9d, r9d; lpType
0x1801c1e31  xor     r8d, r8d; lpReserved
0x1801c1e34  mov     [rsp+360h+phkResult], rax; lpData
0x1801c1e39  call    cs:__imp_RegQueryValueExW
0x1801c1e3f  test    eax, eax
0x1801c1e41  jz      short loc_1801C1E6F
0x1801c1e43  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1e4a  cmp     rcx, r14
0x1801c1e4d  jz      short loc_1801C1E8D
0x1801c1e4f  test    byte ptr [rcx+1Ch], 10h
0x1801c1e53  jz      short loc_1801C1E8D
0x1801c1e55  mov     rcx, [rcx+10h]
0x1801c1e59  lea     r8, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids
0x1801c1e60  mov     edx, 16h
0x1801c1e65  mov     r9d, eax
0x1801c1e68  call    WPP_SF_d
0x1801c1e6d  jmp     short loc_1801C1E86
0x1801c1e6f  lea     r8, [rsp+360h+pSourceSid]; pSourceSid
0x1801c1e74  mov     byte ptr [r15], 1
0x1801c1e78  mov     rdx, r12; pDestinationSid
0x1801c1e7b  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1801c1e80  call    cs:__imp_CopySid
0x1801c1e86  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1e8d  mov     rax, [rsp+360h+hKey]
0x1801c1e92  test    rax, rax
0x1801c1e95  jz      short loc_1801C1EA7
0x1801c1e97  mov     rcx, rax; hKey
0x1801c1e9a  call    cs:__imp_RegCloseKey
0x1801c1ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c1ea7  lea     rax, WPP_GLOBAL_Control
0x1801c1eae  cmp     rcx, rax
0x1801c1eb1  jz      short loc_1801C1EE2
0x1801c1eb3  test    byte ptr [rcx+1Ch], 10h
0x1801c1eb7  jz      short loc_1801C1EE2
0x1801c1eb9  mov     eax, dword ptr [rsp+360h+var_330]
0x1801c1ebd  lea     r9, [rbp+260h+SubKey]
0x1801c1ec1  mov     rcx, [rcx+10h]
0x1801c1ec5  lea     r8, WPP_52a1f548083e30a540d04b5cd764f693_Traceguids
0x1801c1ecc  mov     dword ptr [rsp+360h+lpcbData], eax
0x1801c1ed0  mov     edx, 17h
0x1801c1ed5  mov     eax, dword ptr [rsp+360h+Data]
0x1801c1ed9  mov     dword ptr [rsp+360h+phkResult], eax
0x1801c1edd  call    WPP_SF_Sdd
0x1801c1ee2  xor     eax, eax
0x1801c1ee4  mov     rcx, [rbp+260h+var_40]
0x1801c1eeb  xor     rcx, rsp; StackCookie
0x1801c1eee  call    __security_check_cookie
0x1801c1ef3  add     rsp, 330h
0x1801c1efa  pop     r15
0x1801c1efc  pop     r14
0x1801c1efe  pop     r12
0x1801c1f00  pop     rdi
0x1801c1f01  pop     rsi
0x1801c1f02  pop     rbx
0x1801c1f03  pop     rbp
0x1801c1f04  retn
```
