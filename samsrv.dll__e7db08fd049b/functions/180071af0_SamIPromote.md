# SamIPromote

- ea: `0x180071af0`
- end: `0x180072211`
- name: `SamIPromote`
- size: `1825`
- prototype: `__int64 __fastcall(unsigned int, struct _POLICY_PRIMARY_DOMAIN_INFO *)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18002d170`
- `0x180037284`
- `0x1800372ac`
- `0x180041430`
- `0x180059a74`
- `0x18006ce50`
- `0x18006d850`
- `0x18006fdbc`
- `0x180070910`
- `0x180071af0`
- `0x180072810`
- `0x180073370`
- `0x1800775c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071bc0`
- `ntdll!NtOpenKey` at `0x180071f3e`
- `ntdll!NtOpenKey` at `0x180071f3e`
- `ntdll!NtFlushKey` at `0x180071e41`
- `ntdll!NtFlushKey` at `0x180071e41`
- `ntdll!NtClose` at `0x180071f79`
- `ntdll!NtClose` at `0x180071f79`
- `ntdll!RtlInitUnicodeString` at `0x180071c54`
- `ntdll!RtlInitUnicodeString` at `0x180071cbb`
- `ntdll!RtlInitUnicodeString` at `0x180071eeb`
- `ntdll!RtlInitUnicodeString` at `0x180071c54`
- `ntdll!RtlInitUnicodeString` at `0x180071cbb`
- `ntdll!RtlInitUnicodeString` at `0x180071eeb`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180071bb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180071bb2`
- `LSASRV!LsaILookupWellKnownName` at `0x180071c5f`
- `LSASRV!LsaILookupWellKnownName` at `0x180071cc6`
- `LSASRV!LsaILookupWellKnownName` at `0x180071c5f`
- `LSASRV!LsaILookupWellKnownName` at `0x180071cc6`

## string_xrefs

- `0x180071d90`: `\Registry\Machine\SAMUPGRADE\SAM`
- `0x180071e76`: `\Registry\Machine\SAM\SAM`
- `0x180071edf`: `\Registry\Machine\SAM\NT5`
- `0x18007201c`: `\Registry\Machine\SAM\NT5`
- `0x180072032`: `\Registry\Machine\SAM\NT5\SAM`

## pseudocode

```c
__int64 __fastcall SamIPromote(
        unsigned int a1,
        _POLICY_ACCOUNT_DOMAIN_INFO *a2,
        __int64 a3,
        struct _UNICODE_STRING *a4)
{
  __int64 v7; // r14
  PUNICODE_STRING v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // ecx
  unsigned __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  PUNICODE_STRING v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  NTSTATUS v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  PUNICODE_STRING v22; // rcx
  __int64 v23; // rdx
  struct _UNICODE_STRING *v24; // rax
  int v25; // eax
  int KeyForPostBootPromote; // eax
  DWORD nSize; // [rsp+48h] [rbp-E8h] BYREF
  int v28; // [rsp+4Ch] [rbp-E4h]
  struct _UNICODE_STRING v29; // [rsp+50h] [rbp-E0h] BYREF
  _POLICY_LSA_SERVER_ROLE v30; // [rsp+60h] [rbp-D0h] BYREF
  enum _NT_PRODUCT_TYPE v31; // [rsp+64h] [rbp-CCh] BYREF
  void *KeyHandle; // [rsp+68h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v34; // [rsp+80h] [rbp-B0h] BYREF
  _POLICY_ACCOUNT_DOMAIN_INFO v35; // [rsp+90h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-88h] BYREF
  WCHAR Buffer[20]; // [rsp+D8h] [rbp-58h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v29 = 0;
  KeyHandle = 0;
  v7 = 16;
  nSize = 16;
  DestinationString = 0;
  memset(&v35, 0, sizeof(v35));
  if ( SampServiceState != 2 )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        10,
        WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
        3221225692LL,
        -1073741604);
    return 3221225692LL;
  }
  if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
  {
    if ( GetLastError() == 234 )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          11,
          WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
          2147483653LL,
          -2147483643);
      return 2147483653LL;
    }
    else
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          12,
          WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
          3221225473LL,
          -1073741823);
      return 3221225473LL;
    }
  }
  RtlInitUnicodeString(&DestinationString, Buffer);
  if ( (unsigned __int8)LsaILookupWellKnownName(&DestinationString) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v10 = 13;
LABEL_20:
      WPP_SF_Dd(v9[3].Buffer, v10, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, 3221226500LL, -1073740796);
      return 3221226500LL;
    }
    return 3221226500LL;
  }
  v11 = nSize;
  Buffer[nSize] = 36;
  v12 = v11 + 1;
  if ( v12 >= 17 )
    _report_rangecheckfailure();
  Buffer[v12] = 0;
  RtlInitUnicodeString(&DestinationString, Buffer);
  if ( (unsigned __int8)LsaILookupWellKnownName(&DestinationString) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v10 = 14;
      goto LABEL_20;
    }
    return 3221226500LL;
  }
  v13 = SampCheckPromoteEnvironment(a1);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 15, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v13);
      v15 = WPP_GLOBAL_Control;
    }
    if ( (*(_DWORD *)(&v15[4].MaximumLength + 1) & 0x20000) == 0 )
      return v14;
    v16 = 16;
    goto LABEL_28;
  }
  if ( (a1 & 4) != 0 )
  {
    v14 = 0;
    goto LABEL_79;
  }
  if ( (a1 & 8) != 0 )
  {
    SampNT4UpgradeInProgress = 1;
    v14 = SampExtRegistryToDsUpgradeDs(L"\\Registry\\Machine\\SAMUPGRADE\\SAM");
    SamIUnLoadDownlevelDatabase(0);
    SampNT4UpgradeInProgress = 0;
    if ( (v14 & 0x80000000) != 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 17, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v14);
        v15 = WPP_GLOBAL_Control;
      }
      if ( (*(_DWORD *)(&v15[4].MaximumLength + 1) & 0x20000) == 0 )
        return v14;
      v16 = 18;
      goto LABEL_28;
    }
    goto LABEL_79;
  }
  if ( (a1 & 0x10) != 0 )
  {
    v17 = SampRenameKrbtgtAccount();
    if ( v17 < 0
      && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 19, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v17);
    }
    v18 = NtFlushKey(SampKey);
    if ( v18 < 0
      && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 20, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v18);
    }
    v19 = SampExtRegistryToDsUpgradeDs(L"\\Registry\\Machine\\SAM\\SAM");
    v14 = v19;
    if ( v19 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 21, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v19);
        v15 = WPP_GLOBAL_Control;
      }
      if ( (*(_DWORD *)(&v15[4].MaximumLength + 1) & 0x20000) == 0 )
        return v14;
      v16 = 22;
      goto LABEL_28;
    }
LABEL_78:
    if ( (v14 & 0x80000000) != 0 )
    {
LABEL_94:
      v15 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return v14;
      v16 = 32;
LABEL_28:
      WPP_SF_Dd(v15[3].Buffer, v16, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v14, v14);
      return v14;
    }
LABEL_79:
    if ( (a1 & 0x800) == 0 )
    {
      v34 = 0;
      if ( a4 )
      {
        v34 = *a4;
      }
      else
      {
        v24 = &v34;
        do
        {
          LOBYTE(v24->Length) = 0;
          v24 = (struct _UNICODE_STRING *)((char *)v24 + 1);
          --v7;
        }
        while ( v7 );
      }
      v25 = SampSetAdminPasswordInRegistry((a1 & 0x80) != 0, &v34);
      v14 = v25;
      if ( v25 < 0 )
      {
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            30,
            WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
            (a1 & 0x80) != 0,
            v25);
        v14 = -1073741717;
      }
    }
    if ( (v14 & 0x80000000) == 0 )
    {
      KeyForPostBootPromote = SampCreateKeyForPostBootPromote(a1);
      v14 = KeyForPostBootPromote;
      if ( KeyForPostBootPromote < 0
        && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          31,
          WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
          a1,
          KeyForPostBootPromote);
      }
    }
    goto LABEL_94;
  }
  if ( (a1 & 0x20) != 0 )
  {
    RtlInitUnicodeString(&v29, L"\\Registry\\Machine\\SAM\\NT5");
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &v29;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) >= 0 )
    {
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 23, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids);
      NtClose(KeyHandle);
      v20 = SampRegistryDelnode(v29.Buffer);
      v14 = v20;
      if ( v20 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          WPP_SF_ZD(
            WPP_GLOBAL_Control[3].Buffer,
            24,
            (unsigned int)WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
            (unsigned int)&v29,
            v20);
          v15 = WPP_GLOBAL_Control;
        }
        if ( (*(_DWORD *)(&v15[4].MaximumLength + 1) & 0x20000) == 0 )
          return v14;
        v16 = 25;
        goto LABEL_28;
      }
    }
    v31 = NtProductLanManNt;
    v30 = PolicyServerRolePrimary;
    v35 = *a2;
    v21 = SampInitializeRegistry(
            L"\\Registry\\Machine\\SAM\\NT5",
            &v31,
            &v30,
            &v35,
            (struct _POLICY_PRIMARY_DOMAIN_INFO *)a2,
            0);
    v14 = v21;
    v28 = v21;
    if ( v21 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        v23 = 27;
        goto LABEL_73;
      }
    }
    else
    {
      v21 = SampExtRegistryToDsUpgradeDs(L"\\Registry\\Machine\\SAM\\NT5\\SAM");
      v14 = v21;
      v28 = v21;
      if ( v21 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          v23 = 26;
LABEL_73:
          WPP_SF_d(v22[3].Buffer, v23, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v21);
        }
      }
    }
    if ( (int)SampRegistryDelnode(v29.Buffer) < 0
      && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_ZD(
        WPP_GLOBAL_Control[3].Buffer,
        28,
        (unsigned int)WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
        (unsigned int)&v29,
        v14);
    }
    goto LABEL_78;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      29,
      WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
      3221225485LL,
      -1073741811);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180071af0  mov     r11, rsp
0x180071af3  push    rbx
0x180071af4  push    rsi
0x180071af5  push    rdi
0x180071af6  push    r14
0x180071af8  push    r15
0x180071afa  sub     rsp, 0F0h
0x180071b01  mov     rax, cs:__security_cookie
0x180071b08  xor     rax, rsp
0x180071b0b  mov     [rsp+118h+var_30], rax
0x180071b13  mov     r15, r9
0x180071b16  mov     rdi, rdx
0x180071b19  mov     esi, ecx
0x180071b1b  xorps   xmm0, xmm0
0x180071b1e  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x180071b26  movups  xmmword ptr [r11-78h], xmm0
0x180071b2b  movups  xmmword ptr [r11-68h], xmm0
0x180071b30  movups  xmmword ptr [rsp+118h+var_E0.Length], xmm0
0x180071b35  mov     [rsp+118h+KeyHandle], 0
0x180071b3e  mov     r14d, 10h
0x180071b44  mov     [rsp+118h+nSize], r14d
0x180071b49  movups  xmmword ptr [rsp+118h+DestinationString.Length], xmm0
0x180071b4e  xorps   xmm1, xmm1
0x180071b51  xor     eax, eax
0x180071b53  movups  xmmword ptr [rsp+118h+var_A0.DomainName.Length], xmm1
0x180071b58  mov     [r11-90h], rax
0x180071b5f  cmp     cs:?SampServiceState@@3W4_SAMP_SERVICE_STATE@@A, 2; _SAMP_SERVICE_STATE SampServiceState
0x180071b66  jz      short loc_180071BA3
0x180071b68  mov     rcx, cs:WPP_GLOBAL_Control
0x180071b6f  test    dword ptr [rcx+44h], 20000h
0x180071b76  jz      short loc_180071B99
0x180071b78  lea     edx, [rax+0Ah]
0x180071b7b  mov     dword ptr [rsp+118h+var_F8], 0C00000DCh
0x180071b83  mov     r9d, 0C00000DCh
0x180071b89  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071b90  mov     rcx, [rcx+38h]
0x180071b94  call    WPP_SF_Dd
0x180071b99  mov     eax, 0C00000DCh
0x180071b9e  jmp     loc_1800721EC
0x180071ba3  lea     r8, [rsp+118h+nSize]; nSize
0x180071ba8  lea     rdx, [rsp+118h+Buffer]; lpBuffer
0x180071bb0  xor     ecx, ecx; NameType
0x180071bb2  call    cs:__imp_GetComputerNameExW
0x180071bb8  test    eax, eax
0x180071bba  jnz     loc_180071C47
0x180071bc0  call    cs:__imp_GetLastError
0x180071bc6  cmp     eax, 0EAh
0x180071bcb  jnz     short loc_180071C0A
0x180071bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180071bd4  test    dword ptr [rcx+44h], 20000h
0x180071bdb  jz      short loc_180071C00
0x180071bdd  mov     edx, 0Bh
0x180071be2  mov     dword ptr [rsp+118h+var_F8], 80000005h
0x180071bea  mov     r9d, 80000005h
0x180071bf0  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071bf7  mov     rcx, [rcx+38h]
0x180071bfb  call    WPP_SF_Dd
0x180071c00  mov     eax, 80000005h
0x180071c05  jmp     loc_1800721EC
0x180071c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180071c11  test    dword ptr [rcx+44h], 20000h
0x180071c18  jz      short loc_180071C3D
0x180071c1a  mov     edx, 0Ch
0x180071c1f  mov     dword ptr [rsp+118h+var_F8], 0C0000001h
0x180071c27  mov     r9d, 0C0000001h
0x180071c2d  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071c34  mov     rcx, [rcx+38h]
0x180071c38  call    WPP_SF_Dd
0x180071c3d  mov     eax, 0C0000001h
0x180071c42  jmp     loc_1800721EC
0x180071c47  lea     rdx, [rsp+118h+Buffer]; SourceString
0x180071c4f  lea     rcx, [rsp+118h+DestinationString]; DestinationString
0x180071c54  call    cs:__imp_RtlInitUnicodeString
0x180071c5a  lea     rcx, [rsp+118h+DestinationString]
0x180071c5f  call    cs:__imp_LsaILookupWellKnownName
0x180071c65  test    al, al
0x180071c67  jz      short loc_180071C84
0x180071c69  mov     rcx, cs:WPP_GLOBAL_Control
0x180071c70  test    dword ptr [rcx+44h], 20000h
0x180071c77  jz      loc_180071D03
0x180071c7d  mov     edx, 0Dh
0x180071c82  jmp     short loc_180071CE5
0x180071c84  mov     ecx, [rsp+118h+nSize]
0x180071c88  mov     edx, 24h ; '$'
0x180071c8d  mov     [rsp+rcx*2+118h+Buffer], dx
0x180071c95  inc     ecx
0x180071c97  add     rcx, rcx
0x180071c9a  cmp     rcx, 22h ; '"'
0x180071c9e  jnb     loc_18007220B
0x180071ca4  xor     eax, eax
0x180071ca6  mov     [rsp+rcx+118h+Buffer], ax
0x180071cae  lea     rdx, [rsp+118h+Buffer]; SourceString
0x180071cb6  lea     rcx, [rsp+118h+DestinationString]; DestinationString
0x180071cbb  call    cs:__imp_RtlInitUnicodeString
0x180071cc1  lea     rcx, [rsp+118h+DestinationString]
0x180071cc6  call    cs:__imp_LsaILookupWellKnownName
0x180071ccc  test    al, al
0x180071cce  jz      short loc_180071D0D
0x180071cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180071cd7  test    dword ptr [rcx+44h], 20000h
0x180071cde  jz      short loc_180071D03
0x180071ce0  mov     edx, 0Eh
0x180071ce5  mov     dword ptr [rsp+118h+var_F8], 0C0000404h
0x180071ced  mov     r9d, 0C0000404h
0x180071cf3  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071cfa  mov     rcx, [rcx+38h]
0x180071cfe  call    WPP_SF_Dd
0x180071d03  mov     eax, 0C0000404h
0x180071d08  jmp     loc_1800721EC
0x180071d0d  mov     ecx, esi; unsigned int
0x180071d0f  call    ?SampCheckPromoteEnvironment@@YAJK@Z; SampCheckPromoteEnvironment(ulong)
0x180071d14  mov     ebx, eax
0x180071d16  test    eax, eax
0x180071d18  jns     short loc_180071D76
0x180071d1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180071d21  test    byte ptr [rcx+44h], 80h
0x180071d25  jz      short loc_180071D4C
0x180071d27  cmp     byte ptr [rcx+41h], 2
0x180071d2b  jb      short loc_180071D4C
0x180071d2d  mov     edx, 0Fh
0x180071d32  mov     r9d, eax
0x180071d35  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071d3c  mov     rcx, [rcx+38h]
0x180071d40  call    WPP_SF_d
0x180071d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180071d4c  test    dword ptr [rcx+44h], 20000h
0x180071d53  jz      short loc_180071D6F
0x180071d55  mov     edx, r14d
0x180071d58  mov     dword ptr [rsp+118h+var_F8], ebx
0x180071d5c  mov     r9d, ebx
0x180071d5f  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071d66  mov     rcx, [rcx+38h]
0x180071d6a  call    WPP_SF_Dd
0x180071d6f  mov     eax, ebx
0x180071d71  jmp     loc_1800721EC
0x180071d76  test    sil, 4
0x180071d7a  jz      short loc_180071D83
0x180071d7c  xor     ebx, ebx
0x180071d7e  jmp     loc_1800720D5
0x180071d83  test    sil, 8
0x180071d87  jz      short loc_180071DF9
0x180071d89  mov     cs:?SampNT4UpgradeInProgress@@3EA, 1; uchar SampNT4UpgradeInProgress
0x180071d90  lea     rcx, aRegistryMachin_2; "\\Registry\\Machine\\SAMUPGRADE\\SAM"
0x180071d97  call    ?SampExtRegistryToDsUpgradeDs@@YAJPEBG@Z; SampExtRegistryToDsUpgradeDs(ushort const *)
0x180071d9c  mov     ebx, eax
0x180071d9e  xor     ecx, ecx
0x180071da0  call    SamIUnLoadDownlevelDatabase
0x180071da5  mov     cs:?SampNT4UpgradeInProgress@@3EA, 0; uchar SampNT4UpgradeInProgress
0x180071dac  test    ebx, ebx
0x180071dae  jns     loc_1800720D5
0x180071db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180071dbb  test    byte ptr [rcx+44h], 80h
0x180071dbf  jz      short loc_180071DE6
0x180071dc1  cmp     byte ptr [rcx+41h], 2
0x180071dc5  jb      short loc_180071DE6
0x180071dc7  mov     edx, 11h
0x180071dcc  mov     r9d, ebx
0x180071dcf  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071dd6  mov     rcx, [rcx+38h]
0x180071dda  call    WPP_SF_d
0x180071ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x180071de6  test    dword ptr [rcx+44h], 20000h
0x180071ded  jz      short loc_180071D6F
0x180071def  mov     edx, 12h
0x180071df4  jmp     loc_180071D58
0x180071df9  mov     eax, esi
0x180071dfb  and     eax, r14d
0x180071dfe  test    al, al
0x180071e00  jz      loc_180071ED5
0x180071e06  call    SampRenameKrbtgtAccount
0x180071e0b  test    eax, eax
0x180071e0d  jns     short loc_180071E3A
0x180071e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180071e16  test    byte ptr [rcx+44h], 80h
0x180071e1a  jz      short loc_180071E3A
0x180071e1c  cmp     byte ptr [rcx+41h], 3
0x180071e20  jb      short loc_180071E3A
0x180071e22  mov     edx, 13h
0x180071e27  mov     r9d, eax
0x180071e2a  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071e31  mov     rcx, [rcx+38h]
0x180071e35  call    WPP_SF_d
0x180071e3a  mov     rcx, cs:SampKey; KeyHandle
0x180071e41  call    cs:__imp_NtFlushKey
0x180071e47  test    eax, eax
0x180071e49  jns     short loc_180071E76
0x180071e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180071e52  test    byte ptr [rcx+44h], 80h
0x180071e56  jz      short loc_180071E76
0x180071e58  cmp     byte ptr [rcx+41h], 3
0x180071e5c  jb      short loc_180071E76
0x180071e5e  mov     edx, 14h
0x180071e63  mov     r9d, eax
0x180071e66  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071e6d  mov     rcx, [rcx+38h]
0x180071e71  call    WPP_SF_d
0x180071e76  lea     rcx, aRegistryMachin_3; "\\Registry\\Machine\\SAM\\SAM"
0x180071e7d  call    ?SampExtRegistryToDsUpgradeDs@@YAJPEBG@Z; SampExtRegistryToDsUpgradeDs(ushort const *)
0x180071e82  mov     ebx, eax
0x180071e84  test    eax, eax
0x180071e86  jns     loc_1800720CD
0x180071e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180071e93  test    byte ptr [rcx+44h], 80h
0x180071e97  jz      short loc_180071EBE
0x180071e99  cmp     byte ptr [rcx+41h], 2
0x180071e9d  jb      short loc_180071EBE
0x180071e9f  mov     edx, 15h
0x180071ea4  mov     r9d, eax
0x180071ea7  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071eae  mov     rcx, [rcx+38h]
0x180071eb2  call    WPP_SF_d
0x180071eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180071ebe  test    dword ptr [rcx+44h], 20000h
0x180071ec5  jz      loc_180071D6F
0x180071ecb  mov     edx, 16h
0x180071ed0  jmp     loc_180071D58
0x180071ed5  test    sil, 20h
0x180071ed9  jz      loc_1800721B4
0x180071edf  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SAM\\NT5"
0x180071ee6  lea     rcx, [rsp+118h+var_E0]; DestinationString
0x180071eeb  call    cs:__imp_RtlInitUnicodeString
0x180071ef1  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x180071efc  mov     [rsp+118h+ObjectAttributes.RootDirectory], 0
0x180071f08  mov     [rsp+118h+ObjectAttributes.Attributes], 40h ; '@'
0x180071f13  lea     rax, [rsp+118h+var_E0]
0x180071f18  mov     [rsp+118h+ObjectAttributes.ObjectName], rax
0x180071f20  xorps   xmm0, xmm0
0x180071f23  movdqu  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x180071f2c  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x180071f34  mov     edx, 0F003Fh; DesiredAccess
0x180071f39  lea     rcx, [rsp+118h+KeyHandle]; KeyHandle
0x180071f3e  call    cs:__imp_NtOpenKey
0x180071f44  test    eax, eax
0x180071f46  js      loc_180071FDE
0x180071f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180071f53  test    byte ptr [rcx+44h], 80h
0x180071f57  jz      short loc_180071F74
0x180071f59  cmp     byte ptr [rcx+41h], 4
0x180071f5d  jb      short loc_180071F74
0x180071f5f  mov     edx, 17h
0x180071f64  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071f6b  mov     rcx, [rcx+38h]
0x180071f6f  call    WPP_SF_
0x180071f74  mov     rcx, [rsp+118h+KeyHandle]; Handle
0x180071f79  call    cs:__imp_NtClose
0x180071f7f  mov     rcx, [rsp+118h+var_E0.Buffer]; unsigned __int16 *
0x180071f84  call    ?SampRegistryDelnode@@YAJPEBG@Z; SampRegistryDelnode(ushort const *)
0x180071f89  mov     ebx, eax
0x180071f8b  test    eax, eax
0x180071f8d  jns     short loc_180071FDE
0x180071f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180071f96  test    byte ptr [rcx+44h], 80h
0x180071f9a  jz      short loc_180071FC7
0x180071f9c  cmp     byte ptr [rcx+41h], 2
0x180071fa0  jb      short loc_180071FC7
0x180071fa2  mov     edx, 18h
0x180071fa7  mov     dword ptr [rsp+118h+var_F8], eax
0x180071fab  lea     r9, [rsp+118h+var_E0]
0x180071fb0  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180071fb7  mov     rcx, [rcx+38h]
0x180071fbb  call    WPP_SF_ZD
0x180071fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180071fc7  test    dword ptr [rcx+44h], 20000h
0x180071fce  jz      loc_180071D6F
0x180071fd4  mov     edx, 19h
0x180071fd9  jmp     loc_180071D58
0x180071fde  mov     [rsp+118h+var_CC], 2
0x180071fe6  mov     [rsp+118h+var_D0], 3
0x180071fee  mov     rax, [rdi+10h]
0x180071ff2  mov     [rsp+118h+var_A0.DomainSid], rax
0x180071ffa  movups  xmm0, xmmword ptr [rdi]
0x180071ffd  movdqu  xmmword ptr [rsp+118h+var_A0.DomainName.Length], xmm0
0x180072003  mov     [rsp+118h+var_F0], 0; unsigned __int8
0x180072008  mov     [rsp+118h+var_F8], rdi; struct _POLICY_PRIMARY_DOMAIN_INFO *
0x18007200d  lea     r9, [rsp+118h+var_A0]; struct _POLICY_ACCOUNT_DOMAIN_INFO *
0x180072012  lea     r8, [rsp+118h+var_D0]; enum _POLICY_LSA_SERVER_ROLE *
0x180072017  lea     rdx, [rsp+118h+var_CC]; enum _NT_PRODUCT_TYPE *
0x18007201c  lea     rcx, aRegistryMachin; "\\Registry\\Machine\\SAM\\NT5"
0x180072023  call    ?SampInitializeRegistry@@YAJPEBGPEAW4_NT_PRODUCT_TYPE@@PEAW4_POLICY_LSA_SERVER_ROLE@@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@PEAU_POLICY_PRIMARY_DOMAIN_INFO@@E@Z; SampInitializeRegistry(ushort const *,_NT_PRODUCT_TYPE *,_POLICY_LSA_SERVER_ROLE *,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_PRIMARY_DOMAIN_INFO *,uchar)
0x180072028  mov     ebx, eax
0x18007202a  mov     [rsp+118h+var_E4], eax
0x18007202e  test    eax, eax
0x180072030  js      short loc_180072062
0x180072032  lea     rcx, aRegistryMachin_0; "\\Registry\\Machine\\SAM\\NT5\\SAM"
0x180072039  call    ?SampExtRegistryToDsUpgradeDs@@YAJPEBG@Z; SampExtRegistryToDsUpgradeDs(ushort const *)
0x18007203e  mov     ebx, eax
0x180072040  mov     [rsp+118h+var_E4], eax
0x180072044  test    eax, eax
0x180072046  jns     short loc_18007208E
0x180072048  mov     rcx, cs:WPP_GLOBAL_Control
0x18007204f  test    byte ptr [rcx+44h], 80h
0x180072053  jz      short loc_18007208E
0x180072055  cmp     byte ptr [rcx+41h], 2
0x180072059  jb      short loc_18007208E
0x18007205b  mov     edx, 1Ah
0x180072060  jmp     short loc_18007207A
0x180072062  mov     rcx, cs:WPP_GLOBAL_Control
0x180072069  test    byte ptr [rcx+44h], 80h
0x18007206d  jz      short loc_18007208E
0x18007206f  cmp     byte ptr [rcx+41h], 2
  ... truncated ...
```
