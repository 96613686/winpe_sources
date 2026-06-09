# CNetworkCfgRegSettings::ReadSettings(_IP_ADAPTER_ADDRESSES_LH *)

- ea: `0x180011540`
- end: `0x180011abd`
- name: `?ReadSettings@CNetworkCfgRegSettings@@QEAAXPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `1405`
- prototype: `void __fastcall(CNetworkCfgRegSettings *__hidden this, struct _IP_ADAPTER_ADDRESSES_LH *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18000e064`
- `0x180010390`

## callees

- `0x18000fe08`
- `0x180011540`
- `0x18001d688`
- `0x1800271fc`
- `0x1800287d0`
- `0x180029df0`
- `0x18002fe28`
- `0x180031018`
- `0x18003174c`
- `0x180031b70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800119a8`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800119a8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011aac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011aac`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001180b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001180b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800115f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011627`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011661`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011843`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800115f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011627`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011661`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011843`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800115ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800115ae`

## string_xrefs

- `0x180011571`: `System\CurrentControlSet\Services\SSDPSRV\Parameters`

## pseudocode

```c
void __fastcall CNetworkCfgRegSettings::ReadSettings(BYTE *this, struct _IP_ADAPTER_ADDRESSES_LH *a2)
{
  DWORD v4; // r9d
  int v5; // eax
  LPCSTR v6; // rcx
  BYTE *v7; // rbx
  int v8; // r14d
  const char *v9; // r15
  __int64 v10; // rcx
  DWORD v11; // r14d
  int v12; // eax
  BYTE v13; // al
  BYTE *i; // r12
  __int64 v15; // r13
  const char *v16; // rdx
  const char *v17; // rax
  DWORD cbData; // [rsp+38h] [rbp-19h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-15h] BYREF
  DWORD Type; // [rsp+40h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-9h] BYREF
  char v22[32]; // [rsp+50h] [rbp-1h] BYREF

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
    v12 = RegQueryValueExA(hKey, "AddressList", 0, &Type, v7, &cbData);
    v4 = Type;
    if ( Type != 7 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids,
          Type,
          -2147024809);
LABEL_39:
        v6 = WPP_GLOBAL_Control;
        goto LABEL_8;
      }
      goto LABEL_8;
    }
    if ( v12 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids,
          (unsigned int)v12);
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
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids,
      v11,
      -2147024882);
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
    BuildAdapterPhysicalAddressString(a2->PhysicalAddress, a2->PhysicalAddressLength, v22, v4);
    if ( v7 && (v13 = *v7) != 0 )
    {
      for ( i = v7; ; v13 = *i )
      {
        if ( !v13 )
        {
          if ( !v8 )
            goto LABEL_71;
          goto LABEL_75;
        }
        v15 = -1;
        do
          ++v15;
        while ( i[v15] );
        if ( !(unsigned int)_o__stricmp(i, v22) )
          break;
        i += v15 + 1;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v16 = "ignoring";
        if ( v8 )
          v16 = "including";
        v17 = "exclusion";
        if ( v8 )
          v17 = "inclusion";
        WPP_SF_sss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v16,
          (unsigned int)"inclusion",
          (_DWORD)i,
          (__int64)v17,
          (__int64)v16);
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
    if ( (int)CNetworkCfgRegSettings::AddAdapterToValidList((CNetworkCfgRegSettings *)this, v22) < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_76;
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, v22);
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
0x180011540  mov     r11, rsp
0x180011543  push    rbp
0x180011544  push    rbx
0x180011545  lea     rbp, [r11-5Fh]
0x180011549  sub     rsp, 98h
0x180011550  mov     rax, cs:__security_cookie
0x180011557  xor     rax, rsp
0x18001155a  mov     [rbp+57h+var_38], rax
0x18001155e  mov     [r11+18h], rsi
0x180011562  lea     rax, [rbp+57h+hKey]
0x180011566  mov     [r11-18h], rdi
0x18001156a  mov     rsi, rdx
0x18001156d  mov     [r11-20h], r12
0x180011571  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\SS"...
0x180011578  mov     [r11-30h], r14
0x18001157c  mov     rdi, rcx
0x18001157f  mov     [r11-38h], r15
0x180011583  mov     r9d, 20019h; samDesired
0x180011589  xor     r15d, r15d
0x18001158c  mov     [rbp+57h+cbData], 4
0x180011593  xor     r8d, r8d; ulOptions
0x180011596  mov     [rbp+57h+hKey], r15
0x18001159a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800115a1  mov     [rbp+57h+Type], r15d
0x1800115a5  mov     dword ptr [rbp+57h+Data], r15d
0x1800115a9  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800115ae  call    cs:__imp_RegOpenKeyExA
0x1800115b5  nop     dword ptr [rax+rax+00h]
0x1800115ba  lea     r12, WPP_GLOBAL_Control
0x1800115c1  test    eax, eax
0x1800115c3  jnz     loc_18001174B
0x1800115c9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800115cd  lea     rax, [rbp+57h+cbData]
0x1800115d1  mov     [rsp+28h], rax; lpcbData
0x1800115d6  lea     r9, [rbp+57h+Type]; lpType
0x1800115da  xor     r8d, r8d; lpReserved
0x1800115dd  mov     [rsp+0A0h+phkResult], rdi; lpData
0x1800115e2  lea     rdx, aAdditionalipv6; "AdditionalIPv6Scope"
0x1800115e9  mov     [rbp+57h+cbData], 4
0x1800115f0  call    cs:__imp_RegQueryValueExA
0x1800115f7  nop     dword ptr [rax+rax+00h]
0x1800115fc  mov     rcx, [rbp+57h+hKey]; hKey
0x180011600  lea     rax, [rbp+57h+cbData]
0x180011604  mov     [rsp+28h], rax; lpcbData
0x180011609  lea     r9, [rbp+57h+Type]; lpType
0x18001160d  lea     rax, [rbp+57h+Data]
0x180011611  mov     [rbp+57h+cbData], 4
0x180011618  xor     r8d, r8d; lpReserved
0x18001161b  mov     [rsp+0A0h+phkResult], rax; lpData
0x180011620  lea     rdx, aIncludeonlylis; "IncludeOnlyListedAddresses"
0x180011627  call    cs:__imp_RegQueryValueExA
0x18001162e  nop     dword ptr [rax+rax+00h]
0x180011633  cmp     dword ptr [rbp+57h+Data], 2
0x180011637  jnb     loc_1800117EE
0x18001163d  mov     [rbp+57h+cbData], r15d
0x180011641  mov     rcx, [rbp+57h+hKey]; hKey
0x180011645  lea     rax, [rbp+57h+cbData]
0x180011649  mov     [rsp+28h], rax; lpcbData
0x18001164e  lea     r9, [rbp+57h+Type]; lpType
0x180011652  xor     r8d, r8d; lpReserved
0x180011655  mov     [rsp+0A0h+phkResult], r15; lpData
0x18001165a  lea     rdx, aAddresslist; "AddressList"
0x180011661  call    cs:__imp_RegQueryValueExA
0x180011668  nop     dword ptr [rax+rax+00h]
0x18001166d  cmp     eax, 2
0x180011670  jnz     loc_1800117F7
0x180011676  mov     dword ptr [rbp+57h+Data], r15d
0x18001167a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011681  cmp     rcx, r12
0x180011684  jz      short loc_180011693
0x180011686  test    dword ptr [rcx+1Ch], 200h
0x18001168d  jnz     loc_180011926
0x180011693  mov     rbx, r15
0x180011696  mov     eax, [rdi]
0x180011698  sub     eax, 3
0x18001169b  cmp     eax, 2
0x18001169e  ja      loc_180011940
0x1800116a4  mov     r14d, dword ptr [rbp+57h+Data]
0x1800116a8  lea     rax, aInclusion; "inclusion"
0x1800116af  lea     r15, aExclusion; "exclusion"
0x1800116b6  test    rsi, rsi
0x1800116b9  jnz     loc_18001194F
0x1800116bf  mov     r14, [rsp+0A0h+var_28]
0x1800116c4  mov     rsi, [rsp+0A0h+arg_10]
0x1800116cc  cmp     rcx, r12
0x1800116cf  mov     r12, [rsp+0A0h+var_18]
0x1800116d7  jnz     short loc_18001171B
0x1800116d9  mov     rcx, [rbp+57h+hKey]; hKey
0x1800116dd  mov     r15, [rsp+0A0h+var_30]
0x1800116e2  mov     rdi, [rsp+90h]
0x1800116ea  test    rcx, rcx
0x1800116ed  jz      short loc_1800116FB
0x1800116ef  call    cs:__imp_RegCloseKey
0x1800116f6  nop     dword ptr [rax+rax+00h]
0x1800116fb  test    rbx, rbx
0x1800116fe  jnz     loc_180011AA9
0x180011704  mov     rcx, [rbp+57h+var_38]
0x180011708  xor     rcx, rsp; StackCookie
0x18001170b  call    __security_check_cookie
0x180011710  add     rsp, 98h
0x180011717  pop     rbx
0x180011718  pop     rbp
0x180011719  retn
0x18001171b  test    dword ptr [rcx+1Ch], 200h
0x180011722  jz      short loc_1800116D9
0x180011724  cmp     dword ptr [rbp+57h+Data], 0
0x180011728  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18001172f  mov     r9d, [rdi]
0x180011732  mov     edx, 13h
0x180011737  mov     rcx, [rcx+10h]
0x18001173b  cmovnz  r15, rax
0x18001173f  mov     [rsp+0A0h+phkResult], r15
0x180011744  call    WPP_SF_ds
0x180011749  jmp     short loc_1800116D9
0x18001174b  mov     rbx, r15
0x18001174e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011755  cmp     rcx, r12
0x180011758  jz      loc_180011696
0x18001175e  test    dword ptr [rcx+1Ch], 200h
0x180011765  jz      loc_180011696
0x18001176b  mov     rcx, [rcx+10h]
0x18001176f  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x180011776  mov     edx, 0Dh
0x18001177b  call    WPP_SF_
0x180011780  jmp     short loc_18001178A
0x180011782  test    eax, eax
0x180011784  jnz     loc_1800118B2
0x18001178a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011791  jmp     loc_180011696
0x180011796  test    eax, eax
0x180011798  jg      loc_1800118D1
0x18001179e  mov     rcx, [rcx+10h]
0x1800117a2  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x1800117a9  mov     edx, 12h
0x1800117ae  mov     r9d, eax
0x1800117b1  call    WPP_SF_d
0x1800117b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117bd  jmp     loc_180011696
0x1800117c2  test    eax, eax
0x1800117c4  jg      loc_180011919
0x1800117ca  mov     rcx, [rcx+10h]
0x1800117ce  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x1800117d5  mov     edx, 10h
0x1800117da  mov     r9d, eax
0x1800117dd  call    WPP_SF_d
0x1800117e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117e9  jmp     loc_180011693
0x1800117ee  mov     dword ptr [rbp+57h+Data], r15d
0x1800117f2  jmp     loc_18001163D
0x1800117f7  test    eax, eax
0x1800117f9  jnz     loc_1800118FA
0x1800117ff  mov     r14d, [rbp+57h+cbData]
0x180011803  test    r14d, r14d
0x180011806  jz      short loc_1800117E2
0x180011808  mov     ecx, r14d; Size
0x18001180b  call    cs:__imp_malloc
0x180011812  nop     dword ptr [rax+rax+00h]
0x180011817  mov     rbx, rax
0x18001181a  test    rax, rax
0x18001181d  jz      loc_1800118DE
0x180011823  mov     rcx, [rbp+57h+hKey]; hKey
0x180011827  lea     rax, [rbp+57h+cbData]
0x18001182b  mov     [rsp+28h], rax; lpcbData
0x180011830  lea     r9, [rbp+57h+Type]; lpType
0x180011834  xor     r8d, r8d; lpReserved
0x180011837  mov     [rsp+0A0h+phkResult], rbx; lpData
0x18001183c  lea     rdx, aAddresslist; "AddressList"
0x180011843  call    cs:__imp_RegQueryValueExA
0x18001184a  nop     dword ptr [rax+rax+00h]
0x18001184f  mov     r9d, [rbp+57h+Type]
0x180011853  cmp     r9d, 7
0x180011857  jz      loc_180011782
0x18001185d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011864  cmp     rcx, r12
0x180011867  jz      loc_180011696
0x18001186d  test    byte ptr [rcx+1Ch], 1
0x180011871  jz      loc_180011696
0x180011877  mov     edx, 0Eh
0x18001187c  mov     dword ptr [rsp+0A0h+phkResult], 80070057h
0x180011884  jmp     short loc_180011896
0x180011886  mov     edx, 11h
0x18001188b  mov     dword ptr [rsp+0A0h+phkResult], 8007000Eh
0x180011893  mov     r9d, r14d
0x180011896  mov     rcx, [rcx+10h]
0x18001189a  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x1800118a1  call    WPP_SF_Dd
0x1800118a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118ad  jmp     loc_180011696
0x1800118b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118b9  cmp     rcx, r12
0x1800118bc  jz      loc_180011696
0x1800118c2  test    byte ptr [rcx+1Ch], 1
0x1800118c6  jz      loc_180011696
0x1800118cc  jmp     loc_180011796
0x1800118d1  movzx   eax, ax
0x1800118d4  or      eax, 80070000h
0x1800118d9  jmp     loc_18001179E
0x1800118de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118e5  cmp     rcx, r12
0x1800118e8  jz      loc_180011696
0x1800118ee  test    byte ptr [rcx+1Ch], 1
0x1800118f2  jz      loc_180011696
0x1800118f8  jmp     short loc_180011886
0x1800118fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180011901  cmp     rcx, r12
0x180011904  jz      loc_180011693
0x18001190a  test    byte ptr [rcx+1Ch], 1
0x18001190e  jz      loc_180011693
0x180011914  jmp     loc_1800117C2
0x180011919  movzx   eax, ax
0x18001191c  or      eax, 80070000h
0x180011921  jmp     loc_1800117CA
0x180011926  mov     rcx, [rcx+10h]
0x18001192a  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x180011931  mov     edx, 0Fh
0x180011936  call    WPP_SF_
0x18001193b  jmp     loc_1800117E2
0x180011940  mov     [rdi], r15d
0x180011943  mov     rcx, cs:WPP_GLOBAL_Control
0x18001194a  jmp     loc_1800116A4
0x18001194f  mov     [rsp+0A0h+var_20], r13
0x180011957  cmp     dword ptr [rsi+68h], 1
0x18001195b  jnz     loc_180011A85
0x180011961  mov     edx, [rsi+58h]; unsigned int
0x180011964  lea     rcx, [rsi+50h]; unsigned __int8 *
0x180011968  lea     r8, [rbp+57h+var_58]; char *
0x18001196c  call    ?BuildAdapterPhysicalAddressString@@YAXPEBEKPEADK@Z; BuildAdapterPhysicalAddressString(uchar const *,ulong,char *,ulong)
0x180011971  test    rbx, rbx
0x180011974  jz      loc_180011A3E
0x18001197a  movzx   eax, byte ptr [rbx]
0x18001197d  test    al, al
0x18001197f  jz      loc_180011A3E
0x180011985  mov     r12, rbx
0x180011988  test    al, al
0x18001198a  jz      loc_180011A30
0x180011990  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180011997  inc     r13
0x18001199a  cmp     byte ptr [r12+r13], 0
0x18001199f  jnz     short loc_180011997
0x1800119a1  lea     rdx, [rbp+57h+var_58]
0x1800119a5  mov     rcx, r12
0x1800119a8  call    cs:__imp__o__stricmp
0x1800119af  nop     dword ptr [rax+rax+00h]
0x1800119b4  test    eax, eax
0x1800119b6  jz      short loc_1800119C5
0x1800119b8  inc     r12
0x1800119bb  add     r12, r13
0x1800119be  movzx   eax, byte ptr [r12]
0x1800119c3  jmp     short loc_180011988
0x1800119c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119cc  lea     rax, WPP_GLOBAL_Control
0x1800119d3  cmp     rcx, rax
0x1800119d6  jz      short loc_180011A21
0x1800119d8  test    dword ptr [rcx+1Ch], 200h
0x1800119df  jz      short loc_180011A21
0x1800119e1  mov     rcx, [rcx+10h]
0x1800119e5  lea     rax, aIncluding; "including"
0x1800119ec  test    r14d, r14d
0x1800119ef  lea     r8, aInclusion; "inclusion"
0x1800119f6  lea     rdx, aIgnoring; "ignoring"
0x1800119fd  mov     r9, r12
0x180011a00  cmovnz  rdx, rax
0x180011a04  mov     rax, r15
0x180011a07  cmovnz  rax, r8
0x180011a0b  mov     [rsp+28h], rdx
0x180011a10  mov     [rsp+0A0h+phkResult], rax
0x180011a15  call    WPP_SF_sss
0x180011a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a21  lea     r12, WPP_GLOBAL_Control
0x180011a28  cmp     r14d, 1
0x180011a2c  jnz     short loc_180011A85
0x180011a2e  jmp     short loc_180011A43
0x180011a30  lea     r12, WPP_GLOBAL_Control
0x180011a37  test    r14d, r14d
0x180011a3a  jz      short loc_180011A43
0x180011a3c  jmp     short loc_180011A7E
0x180011a3e  test    r14d, r14d
0x180011a41  jnz     short loc_180011A7E
0x180011a43  lea     rdx, [rbp+57h+var_58]; char *
0x180011a47  mov     rcx, rdi; this
0x180011a4a  call    ?AddAdapterToValidList@CNetworkCfgRegSettings@@QEAAJPEAD@Z; CNetworkCfgRegSettings::AddAdapterToValidList(char *)
0x180011a4f  test    eax, eax
0x180011a51  jns     short loc_180011A7E
0x180011a53  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a5a  cmp     rcx, r12
0x180011a5d  jz      short loc_180011A85
0x180011a5f  test    byte ptr [rcx+1Ch], 1
0x180011a63  jz      short loc_180011A85
0x180011a65  mov     rcx, [rcx+10h]
0x180011a69  lea     r9, [rbp+57h+var_58]
0x180011a6d  mov     edx, 15h
0x180011a72  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x180011a79  call    WPP_SF_s
0x180011a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a85  mov     rax, [rsi+8]
0x180011a89  mov     rsi, rax
0x180011a8c  test    rax, rax
0x180011a8f  jnz     loc_180011957
0x180011a95  mov     r13, [rsp+0A0h+var_20]
0x180011a9d  lea     rax, aInclusion; "inclusion"
  ... truncated ...
```
