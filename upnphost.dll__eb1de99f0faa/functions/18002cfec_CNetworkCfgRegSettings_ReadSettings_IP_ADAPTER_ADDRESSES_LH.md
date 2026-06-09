# CNetworkCfgRegSettings::ReadSettings(_IP_ADAPTER_ADDRESSES_LH *)

- ea: `0x18002cfec`
- end: `0x18002d2d2`
- name: `?ReadSettings@CNetworkCfgRegSettings@@QEAAXPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `742`
- prototype: `void __fastcall(CNetworkCfgRegSettings *__hidden this, struct _IP_ADAPTER_ADDRESSES_LH *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18002cc38`

## callees

- `0x180018738`
- `0x18002cfec`
- `0x18002d2d8`
- `0x180038ce4`
- `0x1800399fc`
- `0x180039a84`
- `0x180046704`
- `0x180053104`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002d13d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002d13d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002d040`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002d040`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002d0b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002d0e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002d115`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002d0b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002d0e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002d115`

## string_xrefs

- `0x18002d026`: `System\CurrentControlSet\Services\SSDPSRV\Parameters`

## pseudocode

```c
void __fastcall CNetworkCfgRegSettings::ReadSettings(BYTE *this, struct _IP_ADAPTER_ADDRESSES_LH *a2)
{
  BYTE *v4; // rbx
  STRSAFE_PCNZWCH v5; // rcx
  __int64 v6; // rdx
  int v7; // edi
  LSTATUS v8; // eax
  STRSAFE_PCNZWCH v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  STRSAFE_PCNZWCH v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  CNetworkCfgRegSettings *v15; // rcx
  int v16; // r8d
  const char *v17; // rax
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  unsigned int Data; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  v4 = 0;
  Data = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\SSDPSRV\\Parameters", 0, 0x20019u, &hKey) )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v6 = 13;
LABEL_5:
      WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids);
    }
    goto LABEL_36;
  }
  cbData = 4;
  v7 = 1;
  RegQueryValueExA(hKey, "AdditionalIPv6Scope", 0, &Type, this, &cbData);
  cbData = 4;
  RegQueryValueExA(hKey, "IncludeOnlyListedAddresses", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( Data >= 2 )
    Data = 0;
  cbData = 0;
  while ( 1 )
  {
    v8 = RegQueryValueExA(hKey, "AddressList", 0, &Type, v4, &cbData);
    if ( !v7 )
      break;
    if ( v8 == 2 )
    {
      Data = 0;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v6 = 15;
        goto LABEL_5;
      }
      goto LABEL_36;
    }
    if ( v8 )
    {
      v11 = (unsigned __int16)v8 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_36;
      v13 = 16;
LABEL_33:
      v14 = *((_QWORD *)v12 + 2);
      if ( v8 <= 0 )
        v11 = (unsigned int)v8;
      WPP_SF_d(v14, v13, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, v11);
      goto LABEL_36;
    }
    if ( !cbData )
      goto LABEL_36;
    v4 = (BYTE *)malloc(cbData);
    if ( !v4 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = 17;
LABEL_28:
        WPP_SF_dd(*((_QWORD *)v9 + 2), v10, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids);
        goto LABEL_36;
      }
      goto LABEL_36;
    }
    v7 = 0;
  }
  if ( Type == 7 )
  {
    if ( !v8 )
      goto LABEL_36;
    v11 = (unsigned __int16)v8 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_36;
    v13 = 18;
    goto LABEL_33;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v10 = 14;
    goto LABEL_28;
  }
LABEL_36:
  CNetworkCfgRegSettings::ValidateAndCorrectSettings((CNetworkCfgRegSettings *)this);
  CNetworkCfgRegSettings::BuildValidAdapterList(v15, Data, a2, (char *)v4);
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    v17 = "exclusion";
    if ( Data )
      v17 = "inclusion";
    WPP_SF_ds(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)"inclusion", v16, *(_DWORD *)this, (__int64)v17);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    operator delete(v4);
}

```

## disassembly

```asm
0x18002cfec  mov     [rsp-28h+arg_0], rbx
0x18002cff1  push    rbp
0x18002cff2  push    rsi
0x18002cff3  push    rdi
0x18002cff4  push    r12
0x18002cff6  push    r14
0x18002cff8  mov     rbp, rsp
0x18002cffb  sub     rsp, 40h
0x18002cfff  mov     r14, rdx
0x18002d002  mov     [rbp+hKey], 0
0x18002d00a  mov     rsi, rcx
0x18002d00d  mov     [rbp+Type], 0
0x18002d014  lea     rax, [rbp+hKey]
0x18002d018  mov     [rbp+cbData], 4
0x18002d01f  xor     ebx, ebx
0x18002d021  mov     [rsp+40h+phkResult], rax; phkResult
0x18002d026  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\SS"...
0x18002d02d  mov     [rbp+Data], ebx
0x18002d030  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d037  mov     r9d, 20019h; samDesired
0x18002d03d  xor     r8d, r8d; ulOptions
0x18002d040  call    cs:__imp_RegOpenKeyExA
0x18002d046  lea     r12, WPP_GLOBAL_Control
0x18002d04d  test    eax, eax
0x18002d04f  jz      short loc_18002D086
0x18002d051  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d058  cmp     rcx, r12
0x18002d05b  jz      loc_18002D253
0x18002d061  test    dword ptr [rcx+1Ch], 200h
0x18002d068  jz      loc_18002D253
0x18002d06e  lea     edx, [rbx+0Dh]
0x18002d071  mov     rcx, [rcx+10h]
0x18002d075  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18002d07c  call    WPP_SF_
0x18002d081  jmp     loc_18002D253
0x18002d086  mov     rcx, [rbp+hKey]; hKey
0x18002d08a  lea     rax, [rbp+cbData]
0x18002d08e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002d093  lea     r9, [rbp+Type]; lpType
0x18002d097  xor     r8d, r8d; lpReserved
0x18002d09a  mov     [rsp+40h+phkResult], rsi; lpData
0x18002d09f  lea     rdx, aAdditionalipv6; "AdditionalIPv6Scope"
0x18002d0a6  mov     [rbp+cbData], 4
0x18002d0ad  mov     edi, 1
0x18002d0b2  call    cs:__imp_RegQueryValueExA
0x18002d0b8  mov     rcx, [rbp+hKey]; hKey
0x18002d0bc  lea     rax, [rbp+cbData]
0x18002d0c0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002d0c5  lea     r9, [rbp+Type]; lpType
0x18002d0c9  lea     rax, [rbp+Data]
0x18002d0cd  mov     [rbp+cbData], 4
0x18002d0d4  xor     r8d, r8d; lpReserved
0x18002d0d7  mov     [rsp+40h+phkResult], rax; lpData
0x18002d0dc  lea     rdx, aIncludeonlylis; "IncludeOnlyListedAddresses"
0x18002d0e3  call    cs:__imp_RegQueryValueExA
0x18002d0e9  cmp     [rbp+Data], 2
0x18002d0ed  jb      short loc_18002D0F2
0x18002d0ef  mov     [rbp+Data], ebx
0x18002d0f2  mov     [rbp+cbData], ebx
0x18002d0f5  mov     rcx, [rbp+hKey]; hKey
0x18002d0f9  lea     rax, [rbp+cbData]
0x18002d0fd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002d102  lea     r9, [rbp+Type]; lpType
0x18002d106  xor     r8d, r8d; lpReserved
0x18002d109  mov     [rsp+40h+phkResult], rbx; lpData
0x18002d10e  lea     rdx, aAddresslist; "AddressList"
0x18002d115  call    cs:__imp_RegQueryValueExA
0x18002d11b  test    edi, edi
0x18002d11d  jz      loc_18002D1DC
0x18002d123  cmp     eax, 2
0x18002d126  jz      loc_18002D1AE
0x18002d12c  test    eax, eax
0x18002d12e  jnz     short loc_18002D17F
0x18002d130  mov     eax, [rbp+cbData]
0x18002d133  test    eax, eax
0x18002d135  jz      loc_18002D253
0x18002d13b  mov     ecx, eax; Size
0x18002d13d  call    cs:__imp_malloc
0x18002d143  mov     rbx, rax
0x18002d146  test    rax, rax
0x18002d149  jz      short loc_18002D14F
0x18002d14b  xor     edi, edi
0x18002d14d  jmp     short loc_18002D0F5
0x18002d14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d156  cmp     rcx, r12
0x18002d159  jz      loc_18002D253
0x18002d15f  test    byte ptr [rcx+1Ch], 1
0x18002d163  jz      loc_18002D253
0x18002d169  mov     r9d, [rbp+cbData]
0x18002d16d  mov     edx, 11h
0x18002d172  mov     dword ptr [rsp+40h+phkResult], 8007000Eh
0x18002d17a  jmp     loc_18002D205
0x18002d17f  movzx   r9d, ax
0x18002d183  or      r9d, 80070000h
0x18002d18a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d191  cmp     rcx, r12
0x18002d194  jz      loc_18002D253
0x18002d19a  test    byte ptr [rcx+1Ch], 1
0x18002d19e  jz      loc_18002D253
0x18002d1a4  mov     edx, 10h
0x18002d1a9  jmp     loc_18002D23D
0x18002d1ae  mov     [rbp+Data], 0
0x18002d1b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1bc  cmp     rcx, r12
0x18002d1bf  jz      loc_18002D253
0x18002d1c5  test    dword ptr [rcx+1Ch], 200h
0x18002d1cc  jz      loc_18002D253
0x18002d1d2  mov     edx, 0Fh
0x18002d1d7  jmp     loc_18002D071
0x18002d1dc  mov     r9d, [rbp+Type]
0x18002d1e0  cmp     r9d, 7
0x18002d1e4  jz      short loc_18002D217
0x18002d1e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1ed  cmp     rcx, r12
0x18002d1f0  jz      short loc_18002D253
0x18002d1f2  test    byte ptr [rcx+1Ch], 1
0x18002d1f6  jz      short loc_18002D253
0x18002d1f8  mov     edx, 0Eh
0x18002d1fd  mov     dword ptr [rsp+40h+phkResult], 80070057h
0x18002d205  mov     rcx, [rcx+10h]
0x18002d209  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18002d210  call    WPP_SF_dd
0x18002d215  jmp     short loc_18002D253
0x18002d217  test    eax, eax
0x18002d219  jz      short loc_18002D253
0x18002d21b  movzx   r9d, ax
0x18002d21f  or      r9d, 80070000h
0x18002d226  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d22d  cmp     rcx, r12
0x18002d230  jz      short loc_18002D253
0x18002d232  test    byte ptr [rcx+1Ch], 1
0x18002d236  jz      short loc_18002D253
0x18002d238  mov     edx, 12h
0x18002d23d  mov     rcx, [rcx+10h]
0x18002d241  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18002d248  test    eax, eax
0x18002d24a  cmovle  r9d, eax
0x18002d24e  call    WPP_SF_d
0x18002d253  mov     rcx, rsi; this
0x18002d256  call    ?ValidateAndCorrectSettings@CNetworkCfgRegSettings@@AEAAXXZ; CNetworkCfgRegSettings::ValidateAndCorrectSettings(void)
0x18002d25b  mov     edx, [rbp+Data]; unsigned int
0x18002d25e  mov     r9, rbx; char *
0x18002d261  mov     r8, r14; struct _IP_ADAPTER_ADDRESSES_LH *
0x18002d264  call    ?BuildValidAdapterList@CNetworkCfgRegSettings@@AEAAXKPEBU_IP_ADAPTER_ADDRESSES_LH@@PEAD@Z; CNetworkCfgRegSettings::BuildValidAdapterList(ulong,_IP_ADAPTER_ADDRESSES_LH const *,char *)
0x18002d269  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d270  cmp     rcx, r12
0x18002d273  jz      short loc_18002D2A5
0x18002d275  test    dword ptr [rcx+1Ch], 200h
0x18002d27c  jz      short loc_18002D2A5
0x18002d27e  cmp     [rbp+Data], 0
0x18002d282  lea     rdx, aInclusion; "inclusion"
0x18002d289  mov     r9d, [rsi]
0x18002d28c  lea     rax, aExclusion; "exclusion"
0x18002d293  mov     rcx, [rcx+10h]
0x18002d297  cmovnz  rax, rdx
0x18002d29b  mov     [rsp+40h+phkResult], rax
0x18002d2a0  call    WPP_SF_ds
0x18002d2a5  mov     rcx, [rbp+hKey]; hKey
0x18002d2a9  test    rcx, rcx
0x18002d2ac  jz      short loc_18002D2B4
0x18002d2ae  call    cs:__imp_RegCloseKey
0x18002d2b4  test    rbx, rbx
0x18002d2b7  jz      short loc_18002D2C1
0x18002d2b9  mov     rcx, rbx; void *
0x18002d2bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d2c1  mov     rbx, [rsp+40h+arg_0]
0x18002d2c6  add     rsp, 40h
0x18002d2ca  pop     r14
0x18002d2cc  pop     r12
0x18002d2ce  pop     rdi
0x18002d2cf  pop     rsi
0x18002d2d0  pop     rbp
0x18002d2d1  retn
```
