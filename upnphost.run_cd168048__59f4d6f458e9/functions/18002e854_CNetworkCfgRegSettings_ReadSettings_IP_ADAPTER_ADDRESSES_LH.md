# CNetworkCfgRegSettings::ReadSettings(_IP_ADAPTER_ADDRESSES_LH *)

- ea: `0x18002e854`
- end: `0x18002eb5f`
- name: `?ReadSettings@CNetworkCfgRegSettings@@QEAAXPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `779`
- prototype: `void __fastcall(CNetworkCfgRegSettings *__hidden this, struct _IP_ADAPTER_ADDRESSES_LH *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18002e498`

## callees

- `0x18000c8e0`
- `0x18002e854`
- `0x18002eb68`
- `0x18003b1cc`
- `0x18003bfa8`
- `0x18003c018`
- `0x180049430`
- `0x180056a44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002e9bd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002e9bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eb34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002e8a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002e8a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002e920`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002e957`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002e98f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002e920`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002e957`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18002e98f`

## string_xrefs

- `0x18002e88e`: `System\CurrentControlSet\Services\SSDPSRV\Parameters`

## pseudocode

```c
void __fastcall CNetworkCfgRegSettings::ReadSettings(BYTE *this, struct _IP_ADAPTER_ADDRESSES_LH *a2)
{
  BYTE *v4; // rbx
  STRSAFE_PCNZWCH v5; // rcx
  __int64 v6; // rdx
  int v7; // edi
  LSTATUS v8; // eax
  __int64 v9; // r9
  STRSAFE_PCNZWCH v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  CNetworkCfgRegSettings *v13; // rcx
  int v14; // r8d
  const char *v15; // rax
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
  }
  else
  {
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
        v9 = (unsigned __int16)v8 | 0x80070000;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_36;
        v11 = 16;
LABEL_33:
        v12 = *((_QWORD *)v10 + 2);
        if ( v8 <= 0 )
          v9 = (unsigned int)v8;
        WPP_SF_d(v12, v11, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids, v9);
        goto LABEL_36;
      }
      if ( !cbData )
        goto LABEL_36;
      v4 = (BYTE *)malloc(cbData);
      if ( !v4 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids,
            cbData,
            -2147024882);
        goto LABEL_36;
      }
      v7 = 0;
    }
    if ( Type == 7 )
    {
      if ( !v8 )
        goto LABEL_36;
      v9 = (unsigned __int16)v8 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_36;
      v11 = 18;
      goto LABEL_33;
    }
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids,
        Type,
        -2147024809);
  }
LABEL_36:
  CNetworkCfgRegSettings::ValidateAndCorrectSettings((CNetworkCfgRegSettings *)this);
  CNetworkCfgRegSettings::BuildValidAdapterList(v13, Data, a2, (char *)v4);
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    v15 = "exclusion";
    if ( Data )
      v15 = "inclusion";
    WPP_SF_ds(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)"inclusion", v14, *(_DWORD *)this, (__int64)v15);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    operator delete(v4);
}

```

## disassembly

```asm
0x18002e854  mov     [rsp-28h+arg_0], rbx
0x18002e859  push    rbp
0x18002e85a  push    rsi
0x18002e85b  push    rdi
0x18002e85c  push    r12
0x18002e85e  push    r14
0x18002e860  mov     rbp, rsp
0x18002e863  sub     rsp, 40h
0x18002e867  mov     r14, rdx
0x18002e86a  mov     [rbp+hKey], 0
0x18002e872  mov     rsi, rcx
0x18002e875  mov     [rbp+Type], 0
0x18002e87c  lea     rax, [rbp+hKey]
0x18002e880  mov     [rbp+cbData], 4
0x18002e887  xor     ebx, ebx
0x18002e889  mov     [rsp+40h+phkResult], rax; phkResult
0x18002e88e  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\SS"...
0x18002e895  mov     [rbp+Data], ebx
0x18002e898  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e89f  mov     r9d, 20019h; samDesired
0x18002e8a5  xor     r8d, r8d; ulOptions
0x18002e8a8  call    cs:__imp_RegOpenKeyExA
0x18002e8af  nop     dword ptr [rax+rax+00h]
0x18002e8b4  lea     r12, WPP_GLOBAL_Control
0x18002e8bb  test    eax, eax
0x18002e8bd  jz      short loc_18002E8F4
0x18002e8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8c6  cmp     rcx, r12
0x18002e8c9  jz      loc_18002EAD9
0x18002e8cf  test    dword ptr [rcx+1Ch], 200h
0x18002e8d6  jz      loc_18002EAD9
0x18002e8dc  lea     edx, [rbx+0Dh]
0x18002e8df  mov     rcx, [rcx+10h]
0x18002e8e3  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18002e8ea  call    WPP_SF_
0x18002e8ef  jmp     loc_18002EAD9
0x18002e8f4  mov     rcx, [rbp+hKey]; hKey
0x18002e8f8  lea     rax, [rbp+cbData]
0x18002e8fc  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002e901  lea     r9, [rbp+Type]; lpType
0x18002e905  xor     r8d, r8d; lpReserved
0x18002e908  mov     [rsp+40h+phkResult], rsi; lpData
0x18002e90d  lea     rdx, aAdditionalipv6; "AdditionalIPv6Scope"
0x18002e914  mov     [rbp+cbData], 4
0x18002e91b  mov     edi, 1
0x18002e920  call    cs:__imp_RegQueryValueExA
0x18002e927  nop     dword ptr [rax+rax+00h]
0x18002e92c  mov     rcx, [rbp+hKey]; hKey
0x18002e930  lea     rax, [rbp+cbData]
0x18002e934  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002e939  lea     r9, [rbp+Type]; lpType
0x18002e93d  lea     rax, [rbp+Data]
0x18002e941  mov     [rbp+cbData], 4
0x18002e948  xor     r8d, r8d; lpReserved
0x18002e94b  mov     [rsp+40h+phkResult], rax; lpData
0x18002e950  lea     rdx, aIncludeonlylis; "IncludeOnlyListedAddresses"
0x18002e957  call    cs:__imp_RegQueryValueExA
0x18002e95e  nop     dword ptr [rax+rax+00h]
0x18002e963  cmp     [rbp+Data], 2
0x18002e967  jb      short loc_18002E96C
0x18002e969  mov     [rbp+Data], ebx
0x18002e96c  mov     [rbp+cbData], ebx
0x18002e96f  mov     rcx, [rbp+hKey]; hKey
0x18002e973  lea     rax, [rbp+cbData]
0x18002e977  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002e97c  lea     r9, [rbp+Type]; lpType
0x18002e980  xor     r8d, r8d; lpReserved
0x18002e983  mov     [rsp+40h+phkResult], rbx; lpData
0x18002e988  lea     rdx, aAddresslist; "AddressList"
0x18002e98f  call    cs:__imp_RegQueryValueExA
0x18002e996  nop     dword ptr [rax+rax+00h]
0x18002e99b  test    edi, edi
0x18002e99d  jz      loc_18002EA62
0x18002e9a3  cmp     eax, 2
0x18002e9a6  jz      loc_18002EA34
0x18002e9ac  test    eax, eax
0x18002e9ae  jnz     short loc_18002EA05
0x18002e9b0  mov     eax, [rbp+cbData]
0x18002e9b3  test    eax, eax
0x18002e9b5  jz      loc_18002EAD9
0x18002e9bb  mov     ecx, eax; Size
0x18002e9bd  call    cs:__imp_malloc
0x18002e9c4  nop     dword ptr [rax+rax+00h]
0x18002e9c9  mov     rbx, rax
0x18002e9cc  test    rax, rax
0x18002e9cf  jz      short loc_18002E9D5
0x18002e9d1  xor     edi, edi
0x18002e9d3  jmp     short loc_18002E96F
0x18002e9d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9dc  cmp     rcx, r12
0x18002e9df  jz      loc_18002EAD9
0x18002e9e5  test    byte ptr [rcx+1Ch], 1
0x18002e9e9  jz      loc_18002EAD9
0x18002e9ef  mov     r9d, [rbp+cbData]
0x18002e9f3  mov     edx, 11h
0x18002e9f8  mov     dword ptr [rsp+40h+phkResult], 8007000Eh
0x18002ea00  jmp     loc_18002EA8B
0x18002ea05  movzx   r9d, ax
0x18002ea09  or      r9d, 80070000h
0x18002ea10  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea17  cmp     rcx, r12
0x18002ea1a  jz      loc_18002EAD9
0x18002ea20  test    byte ptr [rcx+1Ch], 1
0x18002ea24  jz      loc_18002EAD9
0x18002ea2a  mov     edx, 10h
0x18002ea2f  jmp     loc_18002EAC3
0x18002ea34  mov     [rbp+Data], 0
0x18002ea3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea42  cmp     rcx, r12
0x18002ea45  jz      loc_18002EAD9
0x18002ea4b  test    dword ptr [rcx+1Ch], 200h
0x18002ea52  jz      loc_18002EAD9
0x18002ea58  mov     edx, 0Fh
0x18002ea5d  jmp     loc_18002E8DF
0x18002ea62  mov     r9d, [rbp+Type]
0x18002ea66  cmp     r9d, 7
0x18002ea6a  jz      short loc_18002EA9D
0x18002ea6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea73  cmp     rcx, r12
0x18002ea76  jz      short loc_18002EAD9
0x18002ea78  test    byte ptr [rcx+1Ch], 1
0x18002ea7c  jz      short loc_18002EAD9
0x18002ea7e  mov     edx, 0Eh
0x18002ea83  mov     dword ptr [rsp+40h+phkResult], 80070057h
0x18002ea8b  mov     rcx, [rcx+10h]
0x18002ea8f  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18002ea96  call    WPP_SF_dd
0x18002ea9b  jmp     short loc_18002EAD9
0x18002ea9d  test    eax, eax
0x18002ea9f  jz      short loc_18002EAD9
0x18002eaa1  movzx   r9d, ax
0x18002eaa5  or      r9d, 80070000h
0x18002eaac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eab3  cmp     rcx, r12
0x18002eab6  jz      short loc_18002EAD9
0x18002eab8  test    byte ptr [rcx+1Ch], 1
0x18002eabc  jz      short loc_18002EAD9
0x18002eabe  mov     edx, 12h
0x18002eac3  mov     rcx, [rcx+10h]
0x18002eac7  lea     r8, WPP_14d9553e55fd31ac47e89992682bf9d2_Traceguids
0x18002eace  test    eax, eax
0x18002ead0  cmovle  r9d, eax
0x18002ead4  call    WPP_SF_d
0x18002ead9  mov     rcx, rsi; this
0x18002eadc  call    ?ValidateAndCorrectSettings@CNetworkCfgRegSettings@@AEAAXXZ; CNetworkCfgRegSettings::ValidateAndCorrectSettings(void)
0x18002eae1  mov     edx, [rbp+Data]; unsigned int
0x18002eae4  mov     r9, rbx; char *
0x18002eae7  mov     r8, r14; struct _IP_ADAPTER_ADDRESSES_LH *
0x18002eaea  call    ?BuildValidAdapterList@CNetworkCfgRegSettings@@AEAAXKPEBU_IP_ADAPTER_ADDRESSES_LH@@PEAD@Z; CNetworkCfgRegSettings::BuildValidAdapterList(ulong,_IP_ADAPTER_ADDRESSES_LH const *,char *)
0x18002eaef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eaf6  cmp     rcx, r12
0x18002eaf9  jz      short loc_18002EB2B
0x18002eafb  test    dword ptr [rcx+1Ch], 200h
0x18002eb02  jz      short loc_18002EB2B
0x18002eb04  cmp     [rbp+Data], 0
0x18002eb08  lea     rdx, aInclusion; "inclusion"
0x18002eb0f  mov     r9d, [rsi]
0x18002eb12  lea     rax, aExclusion; "exclusion"
0x18002eb19  mov     rcx, [rcx+10h]
0x18002eb1d  cmovnz  rax, rdx
0x18002eb21  mov     [rsp+40h+phkResult], rax
0x18002eb26  call    WPP_SF_ds
0x18002eb2b  mov     rcx, [rbp+hKey]; hKey
0x18002eb2f  test    rcx, rcx
0x18002eb32  jz      short loc_18002EB40
0x18002eb34  call    cs:__imp_RegCloseKey
0x18002eb3b  nop     dword ptr [rax+rax+00h]
0x18002eb40  test    rbx, rbx
0x18002eb43  jz      short loc_18002EB4D
0x18002eb45  mov     rcx, rbx; void *
0x18002eb48  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002eb4d  mov     rbx, [rsp+40h+arg_0]
0x18002eb52  add     rsp, 40h
0x18002eb56  pop     r14
0x18002eb58  pop     r12
0x18002eb5a  pop     rdi
0x18002eb5b  pop     rsi
0x18002eb5c  pop     rbp
0x18002eb5d  retn
```
