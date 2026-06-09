# SampRefreshRegistry(void)

- ea: `0x1800ad17c`
- end: `0x1800ad5ea`
- name: `?SampRefreshRegistry@@YAJXZ`
- size: `1134`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800aae28`

## callees

- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x18004df1c`
- `0x180054de0`
- `0x1800ad17c`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x1800ad28c`
- `ntdll!RtlAdjustPrivilege` at `0x1800ad2fc`
- `ntdll!RtlAdjustPrivilege` at `0x1800ad28c`
- `ntdll!RtlAdjustPrivilege` at `0x1800ad2fc`
- `ntdll!RtlAbortRXact` at `0x1800ad534`
- `ntdll!RtlAbortRXact` at `0x1800ad534`
- `ntdll!NtRestoreKey` at `0x1800ad2e8`
- `ntdll!NtRestoreKey` at `0x1800ad2e8`
- `ntdll!RtlInitializeRXact` at `0x1800ad55b`
- `ntdll!RtlInitializeRXact` at `0x1800ad55b`
- `ntdll!NtClose` at `0x1800ad2c1`
- `ntdll!NtClose` at `0x1800ad306`
- `ntdll!NtClose` at `0x1800ad35c`
- `ntdll!NtClose` at `0x1800ad39d`
- `ntdll!NtClose` at `0x1800ad545`
- `ntdll!NtClose` at `0x1800ad2c1`
- `ntdll!NtClose` at `0x1800ad306`
- `ntdll!NtClose` at `0x1800ad35c`
- `ntdll!NtClose` at `0x1800ad39d`
- `ntdll!NtClose` at `0x1800ad545`
- `ntdll!RtlpNtOpenKey` at `0x1800ad21b`
- `ntdll!RtlpNtOpenKey` at `0x1800ad446`
- `ntdll!RtlpNtOpenKey` at `0x1800ad21b`
- `ntdll!RtlpNtOpenKey` at `0x1800ad446`
- `ntdll!RtlInitUnicodeString` at `0x1800ad1e0`
- `ntdll!RtlInitUnicodeString` at `0x1800ad407`
- `ntdll!RtlInitUnicodeString` at `0x1800ad1e0`
- `ntdll!RtlInitUnicodeString` at `0x1800ad407`

## string_xrefs

- `0x1800ad3fc`: `\Registry\Machine\Security\SAM`
- `0x1800ad1d5`: `\Registry\Machine\SAM`

## pseudocode

```c
__int64 SampRefreshRegistry(void)
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  PUNICODE_STRING v2; // rcx
  __int64 v3; // rdx
  NTSTATUS v5; // eax
  unsigned int v6; // edx
  unsigned int v7; // ebx
  struct _PSAMP_DEFINED_DOMAINS *v8; // r8
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  NTSTATUS v14; // eax
  unsigned int i; // ebx
  int v16; // eax
  unsigned int v17; // edi
  PUNICODE_STRING v18; // rcx
  NTSTATUS v19; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 OldValue; // [rsp+90h] [rbp+20h] BYREF
  HANDLE KeyHandle; // [rsp+98h] [rbp+28h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  OldValue = 0;
  DestinationString = 0;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 45, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\SAM");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = RtlpNtOpenKey(&KeyHandle, 1u, &ObjectAttributes, 0);
  v1 = v0;
  if ( v0 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 46, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v0);
      v2 = WPP_GLOBAL_Control;
    }
    if ( (*(_DWORD *)(&v2[4].MaximumLength + 1) & 0x20000) == 0 )
      return v1;
    v3 = 47;
LABEL_10:
    WPP_SF_Dd(v2[3].Buffer, v3, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v1, v1);
    return v1;
  }
  v5 = RtlAdjustPrivilege(0x12u, 1u, 0, &OldValue);
  v1 = v5;
  if ( v5 < 0 )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 48, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v5);
    NtClose(KeyHandle);
    v2 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return v1;
    v3 = 49;
    goto LABEL_10;
  }
  v1 = NtRestoreKey(KeyHandle, 0, 2u);
  RtlAdjustPrivilege(0x12u, OldValue, 0, &OldValue);
  NtClose(KeyHandle);
  if ( (v1 & 0x80000000) != 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 50, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v1);
      v2 = WPP_GLOBAL_Control;
    }
    if ( (*(_DWORD *)(&v2[4].MaximumLength + 1) & 0x20000) == 0 )
      return v1;
    v3 = 51;
    goto LABEL_10;
  }
  NtClose(SampKey);
  v6 = SampDefinedDomainsCount;
  v7 = 0;
  SampKey = (HANDLE)-1LL;
  if ( SampDefinedDomainsCount )
  {
    v8 = SampDefinedDomains;
    do
    {
      v9 = 1360LL * v7;
      v10 = *(_QWORD *)((char *)v8 + v9);
      if ( (*(_BYTE *)(v10 + 192) & 2) == 0 )
      {
        NtClose(*(HANDLE *)(v10 + 152));
        v8 = SampDefinedDomains;
        v6 = SampDefinedDomainsCount;
        *(_QWORD *)(*(_QWORD *)((char *)SampDefinedDomains + v9) + 152LL) = -1;
      }
      ++v7;
    }
    while ( v7 < v6 );
  }
  SampInvalidateContextListKeysByObjectType(0, 0);
  SampInvalidateContextListKeysByObjectType(1, 0);
  LOBYTE(v11) = 1;
  SampInvalidateContextListKeysByObjectType(4, v11);
  LOBYTE(v12) = 1;
  SampInvalidateContextListKeysByObjectType(2, v12);
  LOBYTE(v13) = 1;
  SampInvalidateContextListKeysByObjectType(3, v13);
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Security\\SAM");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v14 = RtlpNtOpenKey(&SampKey, 0x2001Fu, &ObjectAttributes, 0);
  v1 = v14;
  if ( v14 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 52, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v14);
      v2 = WPP_GLOBAL_Control;
    }
    if ( (*(_DWORD *)(&v2[4].MaximumLength + 1) & 0x20000) == 0 )
      return v1;
    v3 = 53;
    goto LABEL_10;
  }
  for ( i = 0; i < SampDefinedDomainsCount; ++i )
  {
    if ( (*(_BYTE *)(*((_QWORD *)SampDefinedDomains + 170 * i) + 192LL) & 2) == 0 )
    {
      v16 = SampReInitializeSingleDomain(i);
      v17 = v16;
      if ( v16 < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 54, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, i, v16);
          v18 = WPP_GLOBAL_Control;
        }
        if ( (*(_DWORD *)(&v18[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(v18[3].Buffer, 55, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v17, v17);
        return v17;
      }
    }
  }
  RtlAbortRXact(SampRXactContext);
  NtClose(SampRXactContext->KeyHandle);
  v19 = RtlInitializeRXact(SampKey, 0, &SampRXactContext);
  v1 = v19;
  if ( v19 < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 4) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 56, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, (unsigned int)v19);
      v2 = WPP_GLOBAL_Control;
    }
    if ( (*(_DWORD *)(&v2[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v3 = 57;
      goto LABEL_10;
    }
    return v1;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 58, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800ad17c  mov     [rsp-18h+arg_10], rbx
0x1800ad181  push    rbp
0x1800ad182  push    rsi
0x1800ad183  push    rdi
0x1800ad184  mov     rbp, rsp
0x1800ad187  sub     rsp, 70h
0x1800ad18b  xorps   xmm0, xmm0
0x1800ad18e  mov     [rbp+KeyHandle], 0
0x1800ad196  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800ad19a  mov     [rbp+OldValue], 0
0x1800ad19e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800ad1a2  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ad1a6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800ad1aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad1b1  lea     rsi, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800ad1b8  test    byte ptr [rcx+44h], 4
0x1800ad1bc  jz      short loc_1800AD1D5
0x1800ad1be  cmp     byte ptr [rcx+41h], 4
0x1800ad1c2  jb      short loc_1800AD1D5
0x1800ad1c4  mov     rcx, [rcx+38h]
0x1800ad1c8  mov     edx, 2Dh ; '-'
0x1800ad1cd  mov     r8, rsi
0x1800ad1d0  call    WPP_SF_
0x1800ad1d5  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\SAM"
0x1800ad1dc  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800ad1e0  call    cs:__imp_RtlInitUnicodeString
0x1800ad1e6  xor     r9d, r9d; Unused
0x1800ad1e9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800ad1f0  lea     rax, [rbp+DestinationString]
0x1800ad1f4  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800ad1fc  xorps   xmm0, xmm0
0x1800ad1ff  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800ad206  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800ad20a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800ad20e  lea     edx, [r9+1]; DesiredAccess
0x1800ad212  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800ad216  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ad21b  call    cs:__imp_RtlpNtOpenKey
0x1800ad221  mov     ebx, eax
0x1800ad223  test    eax, eax
0x1800ad225  jns     short loc_1800AD27D
0x1800ad227  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad22e  test    byte ptr [rcx+44h], 4
0x1800ad232  jz      short loc_1800AD255
0x1800ad234  cmp     byte ptr [rcx+41h], 2
0x1800ad238  jb      short loc_1800AD255
0x1800ad23a  mov     rcx, [rcx+38h]
0x1800ad23e  mov     edx, 2Eh ; '.'
0x1800ad243  mov     r9d, eax
0x1800ad246  mov     r8, rsi
0x1800ad249  call    WPP_SF_d
0x1800ad24e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad255  test    dword ptr [rcx+44h], 20000h
0x1800ad25c  jz      short loc_1800AD276
0x1800ad25e  mov     edx, 2Fh ; '/'
0x1800ad263  mov     rcx, [rcx+38h]
0x1800ad267  mov     r9d, ebx
0x1800ad26a  mov     r8, rsi
0x1800ad26d  mov     [rsp+70h+var_50], ebx
0x1800ad271  call    WPP_SF_Dd
0x1800ad276  mov     eax, ebx
0x1800ad278  jmp     loc_1800AD5DA
0x1800ad27d  xor     r8d, r8d; ForThread
0x1800ad280  lea     r9, [rbp+OldValue]; OldValue
0x1800ad284  mov     dl, 1; NewValue
0x1800ad286  lea     edi, [r8+12h]
0x1800ad28a  mov     ecx, edi; Privilege
0x1800ad28c  call    cs:__imp_RtlAdjustPrivilege
0x1800ad292  mov     ebx, eax
0x1800ad294  test    eax, eax
0x1800ad296  jns     short loc_1800AD2DE
0x1800ad298  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad29f  test    byte ptr [rcx+44h], 4
0x1800ad2a3  jz      short loc_1800AD2BD
0x1800ad2a5  cmp     byte ptr [rcx+41h], 2
0x1800ad2a9  jb      short loc_1800AD2BD
0x1800ad2ab  mov     rcx, [rcx+38h]
0x1800ad2af  lea     edx, [rdi+1Eh]
0x1800ad2b2  mov     r9d, eax
0x1800ad2b5  mov     r8, rsi
0x1800ad2b8  call    WPP_SF_d
0x1800ad2bd  mov     rcx, [rbp+KeyHandle]; Handle
0x1800ad2c1  call    cs:__imp_NtClose
0x1800ad2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad2ce  test    dword ptr [rcx+44h], 20000h
0x1800ad2d5  jz      short loc_1800AD276
0x1800ad2d7  mov     edx, 31h ; '1'
0x1800ad2dc  jmp     short loc_1800AD263
0x1800ad2de  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800ad2e2  xor     edx, edx; FileHandle
0x1800ad2e4  lea     r8d, [rdx+2]; RestoreFlags
0x1800ad2e8  call    cs:__imp_NtRestoreKey
0x1800ad2ee  mov     dl, [rbp+OldValue]; NewValue
0x1800ad2f1  lea     r9, [rbp+OldValue]; OldValue
0x1800ad2f5  xor     r8d, r8d; ForThread
0x1800ad2f8  mov     ecx, edi; Privilege
0x1800ad2fa  mov     ebx, eax
0x1800ad2fc  call    cs:__imp_RtlAdjustPrivilege
0x1800ad302  mov     rcx, [rbp+KeyHandle]; Handle
0x1800ad306  call    cs:__imp_NtClose
0x1800ad30c  test    ebx, ebx
0x1800ad30e  jns     short loc_1800AD355
0x1800ad310  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad317  test    byte ptr [rcx+44h], 4
0x1800ad31b  jz      short loc_1800AD33E
0x1800ad31d  cmp     byte ptr [rcx+41h], 2
0x1800ad321  jb      short loc_1800AD33E
0x1800ad323  mov     rcx, [rcx+38h]
0x1800ad327  mov     edx, 32h ; '2'
0x1800ad32c  mov     r9d, ebx
0x1800ad32f  mov     r8, rsi
0x1800ad332  call    WPP_SF_d
0x1800ad337  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad33e  test    dword ptr [rcx+44h], 20000h
0x1800ad345  jz      loc_1800AD276
0x1800ad34b  mov     edx, 33h ; '3'
0x1800ad350  jmp     loc_1800AD263
0x1800ad355  mov     rcx, cs:SampKey; Handle
0x1800ad35c  call    cs:__imp_NtClose
0x1800ad362  mov     edx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x1800ad368  xor     ebx, ebx
0x1800ad36a  mov     cs:SampKey, 0FFFFFFFFFFFFFFFFh
0x1800ad375  test    edx, edx
0x1800ad377  jz      short loc_1800AD3C5
0x1800ad379  mov     r8, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800ad380  mov     eax, ebx
0x1800ad382  imul    rdi, rax, 550h
0x1800ad389  mov     rcx, [rdi+r8]
0x1800ad38d  test    byte ptr [rcx+0C0h], 2
0x1800ad394  jnz     short loc_1800AD3BF
0x1800ad396  mov     rcx, [rcx+98h]; Handle
0x1800ad39d  call    cs:__imp_NtClose
0x1800ad3a3  mov     r8, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800ad3aa  mov     edx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x1800ad3b0  mov     rax, [rdi+r8]
0x1800ad3b4  mov     qword ptr [rax+98h], 0FFFFFFFFFFFFFFFFh
0x1800ad3bf  inc     ebx
0x1800ad3c1  cmp     ebx, edx
0x1800ad3c3  jb      short loc_1800AD380
0x1800ad3c5  xor     edx, edx
0x1800ad3c7  xor     ecx, ecx
0x1800ad3c9  call    ?SampInvalidateContextListKeysByObjectType@@YAXW4_SAMP_OBJECT_TYPE@@E@Z; SampInvalidateContextListKeysByObjectType(_SAMP_OBJECT_TYPE,uchar)
0x1800ad3ce  xor     edx, edx
0x1800ad3d0  lea     ecx, [rdx+1]
0x1800ad3d3  call    ?SampInvalidateContextListKeysByObjectType@@YAXW4_SAMP_OBJECT_TYPE@@E@Z; SampInvalidateContextListKeysByObjectType(_SAMP_OBJECT_TYPE,uchar)
0x1800ad3d8  mov     dl, 1
0x1800ad3da  mov     ecx, 4
0x1800ad3df  call    ?SampInvalidateContextListKeysByObjectType@@YAXW4_SAMP_OBJECT_TYPE@@E@Z; SampInvalidateContextListKeysByObjectType(_SAMP_OBJECT_TYPE,uchar)
0x1800ad3e4  mov     dl, 1
0x1800ad3e6  mov     ecx, 2
0x1800ad3eb  call    ?SampInvalidateContextListKeysByObjectType@@YAXW4_SAMP_OBJECT_TYPE@@E@Z; SampInvalidateContextListKeysByObjectType(_SAMP_OBJECT_TYPE,uchar)
0x1800ad3f0  mov     dl, 1
0x1800ad3f2  mov     ecx, 3
0x1800ad3f7  call    ?SampInvalidateContextListKeysByObjectType@@YAXW4_SAMP_OBJECT_TYPE@@E@Z; SampInvalidateContextListKeysByObjectType(_SAMP_OBJECT_TYPE,uchar)
0x1800ad3fc  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\Security\\SAM"
0x1800ad403  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800ad407  call    cs:__imp_RtlInitUnicodeString
0x1800ad40d  lea     rax, [rbp+DestinationString]
0x1800ad411  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800ad418  xorps   xmm0, xmm0
0x1800ad41b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800ad41f  xor     r9d, r9d; Unused
0x1800ad422  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800ad42a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800ad42e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800ad435  mov     edx, 2001Fh; DesiredAccess
0x1800ad43a  lea     rcx, SampKey; KeyHandle
0x1800ad441  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ad446  call    cs:__imp_RtlpNtOpenKey
0x1800ad44c  mov     ebx, eax
0x1800ad44e  test    eax, eax
0x1800ad450  jns     short loc_1800AD497
0x1800ad452  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad459  test    byte ptr [rcx+44h], 4
0x1800ad45d  jz      short loc_1800AD480
0x1800ad45f  cmp     byte ptr [rcx+41h], 2
0x1800ad463  jb      short loc_1800AD480
0x1800ad465  mov     rcx, [rcx+38h]
0x1800ad469  mov     edx, 34h ; '4'
0x1800ad46e  mov     r9d, eax
0x1800ad471  mov     r8, rsi
0x1800ad474  call    WPP_SF_d
0x1800ad479  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad480  test    dword ptr [rcx+44h], 20000h
0x1800ad487  jz      loc_1800AD276
0x1800ad48d  mov     edx, 35h ; '5'
0x1800ad492  jmp     loc_1800AD263
0x1800ad497  xor     ebx, ebx
0x1800ad499  cmp     ebx, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x1800ad49f  jnb     loc_1800AD52D
0x1800ad4a5  mov     eax, ebx
0x1800ad4a7  imul    rcx, rax, 550h
0x1800ad4ae  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800ad4b5  mov     rcx, [rcx+rax]
0x1800ad4b9  test    byte ptr [rcx+0C0h], 2
0x1800ad4c0  jnz     short loc_1800AD4CF
0x1800ad4c2  mov     ecx, ebx; unsigned int
0x1800ad4c4  call    ?SampReInitializeSingleDomain@@YAJK@Z; SampReInitializeSingleDomain(ulong)
0x1800ad4c9  mov     edi, eax
0x1800ad4cb  test    eax, eax
0x1800ad4cd  js      short loc_1800AD4D3
0x1800ad4cf  inc     ebx
0x1800ad4d1  jmp     short loc_1800AD499
0x1800ad4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad4da  test    byte ptr [rcx+44h], 4
0x1800ad4de  jz      short loc_1800AD505
0x1800ad4e0  cmp     byte ptr [rcx+41h], 2
0x1800ad4e4  jb      short loc_1800AD505
0x1800ad4e6  mov     rcx, [rcx+38h]
0x1800ad4ea  mov     edx, 36h ; '6'
0x1800ad4ef  mov     r9d, ebx
0x1800ad4f2  mov     [rsp+70h+var_50], edi
0x1800ad4f6  mov     r8, rsi
0x1800ad4f9  call    WPP_SF_Dd
0x1800ad4fe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad505  test    dword ptr [rcx+44h], 20000h
0x1800ad50c  jz      short loc_1800AD526
0x1800ad50e  mov     rcx, [rcx+38h]
0x1800ad512  mov     edx, 37h ; '7'
0x1800ad517  mov     r9d, edi
0x1800ad51a  mov     [rsp+70h+var_50], edi
0x1800ad51e  mov     r8, rsi
0x1800ad521  call    WPP_SF_Dd
0x1800ad526  mov     eax, edi
0x1800ad528  jmp     loc_1800AD5DA
0x1800ad52d  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; Context
0x1800ad534  call    cs:__imp_RtlAbortRXact
0x1800ad53a  mov     rcx, cs:?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; _RTL_RXACT_CONTEXT * SampRXactContext
0x1800ad541  mov     rcx, [rcx+8]; Handle
0x1800ad545  call    cs:__imp_NtClose
0x1800ad54b  mov     rcx, cs:SampKey; RootDirectory
0x1800ad552  lea     r8, ?SampRXactContext@@3PEAU_RTL_RXACT_CONTEXT@@EA; OutContext
0x1800ad559  xor     edx, edx; Commit
0x1800ad55b  call    cs:__imp_RtlInitializeRXact
0x1800ad561  mov     ebx, eax
0x1800ad563  test    eax, eax
0x1800ad565  jns     short loc_1800AD5AC
0x1800ad567  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad56e  test    byte ptr [rcx+44h], 4
0x1800ad572  jz      short loc_1800AD595
0x1800ad574  cmp     byte ptr [rcx+41h], 2
0x1800ad578  jb      short loc_1800AD595
0x1800ad57a  mov     rcx, [rcx+38h]
0x1800ad57e  mov     edx, 38h ; '8'
0x1800ad583  mov     r9d, eax
0x1800ad586  mov     r8, rsi
0x1800ad589  call    WPP_SF_d
0x1800ad58e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad595  test    dword ptr [rcx+44h], 20000h
0x1800ad59c  jz      loc_1800AD276
0x1800ad5a2  mov     edx, 39h ; '9'
0x1800ad5a7  jmp     loc_1800AD263
0x1800ad5ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad5b3  test    dword ptr [rcx+44h], 20000h
0x1800ad5ba  jz      short loc_1800AD5D8
0x1800ad5bc  mov     rcx, [rcx+38h]
0x1800ad5c0  mov     edx, 3Ah ; ':'
0x1800ad5c5  xor     r9d, r9d
0x1800ad5c8  mov     [rsp+70h+var_50], 0
0x1800ad5d0  mov     r8, rsi
0x1800ad5d3  call    WPP_SF_Dd
0x1800ad5d8  xor     eax, eax
0x1800ad5da  mov     rbx, [rsp+70h+arg_10]
0x1800ad5e2  add     rsp, 70h
0x1800ad5e6  pop     rdi
0x1800ad5e7  pop     rsi
0x1800ad5e8  pop     rbp
0x1800ad5e9  retn
```
