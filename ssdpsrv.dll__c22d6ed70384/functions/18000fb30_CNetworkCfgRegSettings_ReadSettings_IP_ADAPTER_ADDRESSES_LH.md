# CNetworkCfgRegSettings::ReadSettings(_IP_ADAPTER_ADDRESSES_LH *)

- ea: `0x18000fb30`
- end: `0x180010077`
- name: `?ReadSettings@CNetworkCfgRegSettings@@QEAAXPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `1351`
- prototype: `void __fastcall(BYTE *this, struct _IP_ADAPTER_ADDRESSES_LH *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18000cd44`
- `0x18000eec0`

## callees

- `0x18000e994`
- `0x18000fb30`
- `0x18001c238`
- `0x1800255a8`
- `0x180026a30`
- `0x180028000`
- `0x18002dcf4`
- `0x18002edf0`
- `0x18002f48c`
- `0x18002f87c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000ff6e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000ff6e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001006c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001006c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000fddd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000fddd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fcc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000fbda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000fc0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000fc40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000fe0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000fbda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000fc0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000fc40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000fe0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000fb9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000fb9e`

## string_xrefs

- `0x18000fb61`: `System\CurrentControlSet\Services\SSDPSRV\Parameters`

## pseudocode

```c
void __fastcall CNetworkCfgRegSettings::ReadSettings(BYTE *this, struct _IP_ADAPTER_ADDRESSES_LH *a2)
{
  __int64 v4; // r9
  int v5; // eax
  LPCSTR v6; // rcx
  BYTE *v7; // rbx
  int v8; // r14d
  const char *v9; // r15
  __int64 v10; // rcx
  DWORD v11; // r14d
  __int64 v12; // rdx
  int v13; // eax
  BYTE v14; // al
  BYTE *i; // r12
  __int64 v16; // r13
  const char *v17; // rdx
  const char *v18; // rax
  PHKEY phkResult; // [rsp+28h] [rbp-29h]
  DWORD cbData; // [rsp+38h] [rbp-19h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-15h] BYREF
  DWORD Type; // [rsp+40h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-9h] BYREF
  char v24[32]; // [rsp+50h] [rbp-1h] BYREF

  cbData = 4;
  hKey = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\SSDPSRV\\Parameters", 0, 0x20019u, &hKey) )
  {
    v7 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_8;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids);
    goto LABEL_24;
  }
  cbData = 4;
  RegQueryValueExA(hKey, "AdditionalIPv6Scope", 0, &Type, this, &cbData);
  cbData = 4;
  RegQueryValueExA(hKey, "IncludeOnlyListedAddresses", 0, &Type, Data, &cbData);
  if ( *(_DWORD *)Data >= 2u )
    *(_DWORD *)Data = 0;
  cbData = 0;
  v5 = RegQueryValueExA(hKey, "AddressList", 0, &Type, 0, &cbData);
  if ( v5 == 2 )
  {
    *(_DWORD *)Data = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_7;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids);
    goto LABEL_31;
  }
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_7;
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, (unsigned int)v5);
    goto LABEL_31;
  }
  v11 = cbData;
  if ( !cbData )
  {
LABEL_31:
    v6 = WPP_GLOBAL_Control;
LABEL_7:
    v7 = 0;
    goto LABEL_8;
  }
  v7 = (BYTE *)malloc(cbData);
  if ( v7 )
  {
    v13 = RegQueryValueExA(hKey, "AddressList", 0, &Type, v7, &cbData);
    v4 = Type;
    if ( Type != 7 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v12 = 14;
        LODWORD(phkResult) = -2147024809;
LABEL_39:
        WPP_SF_Dd(*((_QWORD *)v6 + 2), v12, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, v4, phkResult);
        v6 = WPP_GLOBAL_Control;
        goto LABEL_8;
      }
      goto LABEL_8;
    }
    if ( v13 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids,
          (unsigned int)v13);
        v6 = WPP_GLOBAL_Control;
      }
      goto LABEL_8;
    }
LABEL_24:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    v12 = 17;
    LODWORD(phkResult) = -2147024882;
    v4 = v11;
    goto LABEL_39;
  }
LABEL_8:
  if ( (unsigned int)(*(_DWORD *)this - 3) > 2 )
  {
    *(_DWORD *)this = 0;
    v6 = WPP_GLOBAL_Control;
  }
  v8 = *(_DWORD *)Data;
  v9 = "exclusion";
  if ( a2 )
  {
    while ( a2->OperStatus != IfOperStatusUp )
    {
LABEL_76:
      a2 = a2->Next;
      if ( !a2 )
        goto LABEL_11;
    }
    BuildAdapterPhysicalAddressString(a2->PhysicalAddress, a2->PhysicalAddressLength, v24, v4);
    if ( v7 && (v14 = *v7) != 0 )
    {
      for ( i = v7; ; v14 = *i )
      {
        if ( !v14 )
        {
          if ( !v8 )
            goto LABEL_71;
          goto LABEL_75;
        }
        v16 = -1;
        do
          ++v16;
        while ( i[v16] );
        if ( !(unsigned int)_o__stricmp(i, v24) )
          break;
        i += v16 + 1;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v17 = "ignoring";
        if ( v8 )
          v17 = "including";
        v18 = "exclusion";
        if ( v8 )
          v18 = "inclusion";
        WPP_SF_sss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v17,
          (unsigned int)"inclusion",
          (_DWORD)i,
          (__int64)v18,
          (__int64)v17);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v8 != 1 )
        goto LABEL_76;
    }
    else if ( v8 )
    {
LABEL_75:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_76;
    }
LABEL_71:
    if ( (int)CNetworkCfgRegSettings::AddAdapterToValidList((CNetworkCfgRegSettings *)this, v24) < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_76;
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, v24);
    }
    goto LABEL_75;
  }
LABEL_11:
  if ( v6 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x200) != 0 )
  {
    v10 = *((_QWORD *)v6 + 2);
    if ( *(_DWORD *)Data )
      v9 = "inclusion";
    WPP_SF_ds(v10, 19, (unsigned int)WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, *(_DWORD *)this, (__int64)v9);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v7 )
    free(v7);
}

```

## disassembly

```asm
0x18000fb30  mov     r11, rsp
0x18000fb33  push    rbp
0x18000fb34  push    rbx
0x18000fb35  lea     rbp, [r11-5Fh]
0x18000fb39  sub     rsp, 98h
0x18000fb40  mov     rax, cs:__security_cookie
0x18000fb47  xor     rax, rsp
0x18000fb4a  mov     [rbp+57h+var_38], rax
0x18000fb4e  mov     [r11+18h], rsi
0x18000fb52  lea     rax, [rbp+57h+hKey]
0x18000fb56  mov     [r11-18h], rdi
0x18000fb5a  mov     rsi, rdx
0x18000fb5d  mov     [r11-20h], r12
0x18000fb61  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\SS"...
0x18000fb68  mov     [r11-30h], r14
0x18000fb6c  mov     rdi, rcx
0x18000fb6f  mov     [r11-38h], r15
0x18000fb73  mov     r9d, 20019h; samDesired
0x18000fb79  xor     r15d, r15d
0x18000fb7c  mov     [rbp+57h+cbData], 4
0x18000fb83  xor     r8d, r8d; ulOptions
0x18000fb86  mov     [rbp+57h+hKey], r15
0x18000fb8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fb91  mov     [rbp+57h+Type], r15d
0x18000fb95  mov     dword ptr [rbp+57h+Data], r15d
0x18000fb99  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18000fb9e  call    cs:__imp_RegOpenKeyExA
0x18000fba4  lea     r12, WPP_GLOBAL_Control
0x18000fbab  test    eax, eax
0x18000fbad  jnz     loc_18000FD1D
0x18000fbb3  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fbb7  lea     rax, [rbp+57h+cbData]
0x18000fbbb  mov     [rsp+28h], rax; lpcbData
0x18000fbc0  lea     r9, [rbp+57h+Type]; lpType
0x18000fbc4  xor     r8d, r8d; lpReserved
0x18000fbc7  mov     [rsp+0A0h+phkResult], rdi; lpData
0x18000fbcc  lea     rdx, aAdditionalipv6; "AdditionalIPv6Scope"
0x18000fbd3  mov     [rbp+57h+cbData], 4
0x18000fbda  call    cs:__imp_RegQueryValueExA
0x18000fbe0  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fbe4  lea     rax, [rbp+57h+cbData]
0x18000fbe8  mov     [rsp+28h], rax; lpcbData
0x18000fbed  lea     r9, [rbp+57h+Type]; lpType
0x18000fbf1  lea     rax, [rbp+57h+Data]
0x18000fbf5  mov     [rbp+57h+cbData], 4
0x18000fbfc  xor     r8d, r8d; lpReserved
0x18000fbff  mov     [rsp+0A0h+phkResult], rax; lpData
0x18000fc04  lea     rdx, aIncludeonlylis; "IncludeOnlyListedAddresses"
0x18000fc0b  call    cs:__imp_RegQueryValueExA
0x18000fc11  cmp     dword ptr [rbp+57h+Data], 2
0x18000fc15  jnb     loc_18000FDC0
0x18000fc1b  mov     [rbp+57h+cbData], r15d
0x18000fc1f  nop
0x18000fc20  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fc24  lea     rax, [rbp+57h+cbData]
0x18000fc28  mov     [rsp+28h], rax; lpcbData
0x18000fc2d  lea     r9, [rbp+57h+Type]; lpType
0x18000fc31  xor     r8d, r8d; lpReserved
0x18000fc34  mov     [rsp+0A0h+phkResult], r15; lpData
0x18000fc39  lea     rdx, aAddresslist; "AddressList"
0x18000fc40  call    cs:__imp_RegQueryValueExA
0x18000fc46  cmp     eax, 2
0x18000fc49  jnz     loc_18000FDC9
0x18000fc4f  mov     dword ptr [rbp+57h+Data], r15d
0x18000fc53  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc5a  cmp     rcx, r12
0x18000fc5d  jz      short loc_18000FC6C
0x18000fc5f  test    dword ptr [rcx+1Ch], 200h
0x18000fc66  jnz     loc_18000FEEC
0x18000fc6c  mov     rbx, r15
0x18000fc6f  mov     eax, [rdi]
0x18000fc71  sub     eax, 3
0x18000fc74  cmp     eax, 2
0x18000fc77  ja      loc_18000FF06
0x18000fc7d  mov     r14d, dword ptr [rbp+57h+Data]
0x18000fc81  lea     rax, aInclusion; "inclusion"
0x18000fc88  lea     r15, aExclusion; "exclusion"
0x18000fc8f  test    rsi, rsi
0x18000fc92  jnz     loc_18000FF15
0x18000fc98  mov     r14, [rsp+0A0h+var_28]
0x18000fc9d  mov     rsi, [rsp+0A0h+arg_10]
0x18000fca5  cmp     rcx, r12
0x18000fca8  mov     r12, [rsp+0A0h+var_18]
0x18000fcb0  jnz     short loc_18000FCED
0x18000fcb2  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fcb6  mov     r15, [rsp+0A0h+var_30]
0x18000fcbb  mov     rdi, [rsp+90h]
0x18000fcc3  test    rcx, rcx
0x18000fcc6  jz      short loc_18000FCCE
0x18000fcc8  call    cs:__imp_RegCloseKey
0x18000fcce  test    rbx, rbx
0x18000fcd1  jnz     loc_180010069
0x18000fcd7  mov     rcx, [rbp+57h+var_38]
0x18000fcdb  xor     rcx, rsp; StackCookie
0x18000fcde  call    __security_check_cookie
0x18000fce3  add     rsp, 98h
0x18000fcea  pop     rbx
0x18000fceb  pop     rbp
0x18000fcec  retn
0x18000fced  test    dword ptr [rcx+1Ch], 200h
0x18000fcf4  jz      short loc_18000FCB2
0x18000fcf6  cmp     dword ptr [rbp+57h+Data], 0
0x18000fcfa  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000fd01  mov     r9d, [rdi]
0x18000fd04  mov     edx, 13h
0x18000fd09  mov     rcx, [rcx+10h]
0x18000fd0d  cmovnz  r15, rax
0x18000fd11  mov     [rsp+0A0h+phkResult], r15
0x18000fd16  call    WPP_SF_ds
0x18000fd1b  jmp     short loc_18000FCB2
0x18000fd1d  mov     rbx, r15
0x18000fd20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd27  cmp     rcx, r12
0x18000fd2a  jz      loc_18000FC6F
0x18000fd30  test    dword ptr [rcx+1Ch], 200h
0x18000fd37  jz      loc_18000FC6F
0x18000fd3d  mov     rcx, [rcx+10h]
0x18000fd41  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000fd48  mov     edx, 0Dh
0x18000fd4d  call    WPP_SF_
0x18000fd52  jmp     short loc_18000FD5C
0x18000fd54  test    eax, eax
0x18000fd56  jnz     loc_18000FE78
0x18000fd5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd63  jmp     loc_18000FC6F
0x18000fd68  test    eax, eax
0x18000fd6a  jg      loc_18000FE97
0x18000fd70  mov     rcx, [rcx+10h]
0x18000fd74  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000fd7b  mov     edx, 12h
0x18000fd80  mov     r9d, eax
0x18000fd83  call    WPP_SF_d
0x18000fd88  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd8f  jmp     loc_18000FC6F
0x18000fd94  test    eax, eax
0x18000fd96  jg      loc_18000FEDF
0x18000fd9c  mov     rcx, [rcx+10h]
0x18000fda0  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000fda7  mov     edx, 10h
0x18000fdac  mov     r9d, eax
0x18000fdaf  call    WPP_SF_d
0x18000fdb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdbb  jmp     loc_18000FC6C
0x18000fdc0  mov     dword ptr [rbp+57h+Data], r15d
0x18000fdc4  jmp     loc_18000FC1B
0x18000fdc9  test    eax, eax
0x18000fdcb  jnz     loc_18000FEC0
0x18000fdd1  mov     r14d, [rbp+57h+cbData]
0x18000fdd5  test    r14d, r14d
0x18000fdd8  jz      short loc_18000FDB4
0x18000fdda  mov     ecx, r14d; Size
0x18000fddd  call    cs:__imp_malloc
0x18000fde3  mov     rbx, rax
0x18000fde6  test    rax, rax
0x18000fde9  jz      loc_18000FEA4
0x18000fdef  mov     rcx, [rbp+57h+hKey]; hKey
0x18000fdf3  lea     rax, [rbp+57h+cbData]
0x18000fdf7  mov     [rsp+28h], rax; lpcbData
0x18000fdfc  lea     r9, [rbp+57h+Type]; lpType
0x18000fe00  xor     r8d, r8d; lpReserved
0x18000fe03  mov     [rsp+0A0h+phkResult], rbx; lpData
0x18000fe08  lea     rdx, aAddresslist; "AddressList"
0x18000fe0f  call    cs:__imp_RegQueryValueExA
0x18000fe15  mov     r9d, [rbp+57h+Type]
0x18000fe19  cmp     r9d, 7
0x18000fe1d  jz      loc_18000FD54
0x18000fe23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe2a  cmp     rcx, r12
0x18000fe2d  jz      loc_18000FC6F
0x18000fe33  test    byte ptr [rcx+1Ch], 1
0x18000fe37  jz      loc_18000FC6F
0x18000fe3d  mov     edx, 0Eh
0x18000fe42  mov     dword ptr [rsp+0A0h+phkResult], 80070057h
0x18000fe4a  jmp     short loc_18000FE5C
0x18000fe4c  mov     edx, 11h
0x18000fe51  mov     dword ptr [rsp+0A0h+phkResult], 8007000Eh
0x18000fe59  mov     r9d, r14d
0x18000fe5c  mov     rcx, [rcx+10h]
0x18000fe60  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000fe67  call    WPP_SF_Dd
0x18000fe6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe73  jmp     loc_18000FC6F
0x18000fe78  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe7f  cmp     rcx, r12
0x18000fe82  jz      loc_18000FC6F
0x18000fe88  test    byte ptr [rcx+1Ch], 1
0x18000fe8c  jz      loc_18000FC6F
0x18000fe92  jmp     loc_18000FD68
0x18000fe97  movzx   eax, ax
0x18000fe9a  or      eax, 80070000h
0x18000fe9f  jmp     loc_18000FD70
0x18000fea4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000feab  cmp     rcx, r12
0x18000feae  jz      loc_18000FC6F
0x18000feb4  test    byte ptr [rcx+1Ch], 1
0x18000feb8  jz      loc_18000FC6F
0x18000febe  jmp     short loc_18000FE4C
0x18000fec0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fec7  cmp     rcx, r12
0x18000feca  jz      loc_18000FC6C
0x18000fed0  test    byte ptr [rcx+1Ch], 1
0x18000fed4  jz      loc_18000FC6C
0x18000feda  jmp     loc_18000FD94
0x18000fedf  movzx   eax, ax
0x18000fee2  or      eax, 80070000h
0x18000fee7  jmp     loc_18000FD9C
0x18000feec  mov     rcx, [rcx+10h]
0x18000fef0  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18000fef7  mov     edx, 0Fh
0x18000fefc  call    WPP_SF_
0x18000ff01  jmp     loc_18000FDB4
0x18000ff06  mov     [rdi], r15d
0x18000ff09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff10  jmp     loc_18000FC7D
0x18000ff15  mov     [rsp+0A0h+var_20], r13
0x18000ff1d  cmp     dword ptr [rsi+68h], 1
0x18000ff21  jnz     loc_180010045
0x18000ff27  mov     edx, [rsi+58h]; unsigned int
0x18000ff2a  lea     rcx, [rsi+50h]; unsigned __int8 *
0x18000ff2e  lea     r8, [rbp+57h+var_58]; char *
0x18000ff32  call    ?BuildAdapterPhysicalAddressString@@YAXPEBEKPEADK@Z; BuildAdapterPhysicalAddressString(uchar const *,ulong,char *,ulong)
0x18000ff37  test    rbx, rbx
0x18000ff3a  jz      loc_18000FFFE
0x18000ff40  movzx   eax, byte ptr [rbx]
0x18000ff43  test    al, al
0x18000ff45  jz      loc_18000FFFE
0x18000ff4b  mov     r12, rbx
0x18000ff4e  test    al, al
0x18000ff50  jz      loc_18000FFF0
0x18000ff56  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000ff5d  inc     r13
0x18000ff60  cmp     byte ptr [r12+r13], 0
0x18000ff65  jnz     short loc_18000FF5D
0x18000ff67  lea     rdx, [rbp+57h+var_58]
0x18000ff6b  mov     rcx, r12
0x18000ff6e  call    cs:__imp__o__stricmp
0x18000ff74  test    eax, eax
0x18000ff76  jz      short loc_18000FF85
0x18000ff78  inc     r12
0x18000ff7b  add     r12, r13
0x18000ff7e  movzx   eax, byte ptr [r12]
0x18000ff83  jmp     short loc_18000FF4E
0x18000ff85  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff8c  lea     rax, WPP_GLOBAL_Control
0x18000ff93  cmp     rcx, rax
0x18000ff96  jz      short loc_18000FFE1
0x18000ff98  test    dword ptr [rcx+1Ch], 200h
0x18000ff9f  jz      short loc_18000FFE1
0x18000ffa1  mov     rcx, [rcx+10h]
0x18000ffa5  lea     rax, aIncluding; "including"
0x18000ffac  test    r14d, r14d
0x18000ffaf  lea     r8, aInclusion; "inclusion"
0x18000ffb6  lea     rdx, aIgnoring; "ignoring"
0x18000ffbd  mov     r9, r12
0x18000ffc0  cmovnz  rdx, rax
0x18000ffc4  mov     rax, r15
0x18000ffc7  cmovnz  rax, r8
0x18000ffcb  mov     [rsp+28h], rdx
0x18000ffd0  mov     [rsp+0A0h+phkResult], rax
0x18000ffd5  call    WPP_SF_sss
0x18000ffda  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffe1  lea     r12, WPP_GLOBAL_Control
0x18000ffe8  cmp     r14d, 1
0x18000ffec  jnz     short loc_180010045
0x18000ffee  jmp     short loc_180010003
0x18000fff0  lea     r12, WPP_GLOBAL_Control
0x18000fff7  test    r14d, r14d
0x18000fffa  jz      short loc_180010003
0x18000fffc  jmp     short loc_18001003E
0x18000fffe  test    r14d, r14d
0x180010001  jnz     short loc_18001003E
0x180010003  lea     rdx, [rbp+57h+var_58]; char *
0x180010007  mov     rcx, rdi; this
0x18001000a  call    ?AddAdapterToValidList@CNetworkCfgRegSettings@@QEAAJPEAD@Z; CNetworkCfgRegSettings::AddAdapterToValidList(char *)
0x18001000f  test    eax, eax
0x180010011  jns     short loc_18001003E
0x180010013  mov     rcx, cs:WPP_GLOBAL_Control
0x18001001a  cmp     rcx, r12
0x18001001d  jz      short loc_180010045
0x18001001f  test    byte ptr [rcx+1Ch], 1
0x180010023  jz      short loc_180010045
0x180010025  mov     rcx, [rcx+10h]
0x180010029  lea     r9, [rbp+57h+var_58]
0x18001002d  mov     edx, 15h
0x180010032  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x180010039  call    WPP_SF_s
0x18001003e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010045  mov     rax, [rsi+8]
0x180010049  mov     rsi, rax
0x18001004c  test    rax, rax
0x18001004f  jnz     loc_18000FF1D
0x180010055  mov     r13, [rsp+0A0h+var_20]
0x18001005d  lea     rax, aInclusion; "inclusion"
0x180010064  jmp     loc_18000FC98
0x180010069  mov     rcx, rbx; Block
0x18001006c  call    cs:__imp_free
0x180010072  jmp     loc_18000FCD7
```
