# SampCheckRestrictRemoteAccess(HKEY__ *)

- ea: `0x18008d30c`
- end: `0x18008d7f2`
- name: `?SampCheckRestrictRemoteAccess@@YAXPEAUHKEY__@@@Z`
- size: `1254`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180087e50`

## callees

- `0x180037284`
- `0x1800372ac`
- `0x18004d9c0`
- `0x180079238`
- `0x18008d30c`
- `0x18008de64`
- `0x18008deb8`
- `0x18008ef40`
- `0x1800b03d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d509`
- `ntdll!RtlLeaveCriticalSection` at `0x18008d7d1`
- `ntdll!RtlLeaveCriticalSection` at `0x18008d7d1`
- `ntdll!RtlEnterCriticalSection` at `0x18008d351`
- `ntdll!RtlEnterCriticalSection` at `0x18008d351`
- `ntdll!RtlInitUnicodeString` at `0x18008d5c0`
- `ntdll!RtlInitUnicodeString` at `0x18008d5d6`
- `ntdll!RtlInitUnicodeString` at `0x18008d6c7`
- `ntdll!RtlInitUnicodeString` at `0x18008d77b`
- `ntdll!RtlInitUnicodeString` at `0x18008d5c0`
- `ntdll!RtlInitUnicodeString` at `0x18008d5d6`
- `ntdll!RtlInitUnicodeString` at `0x18008d6c7`
- `ntdll!RtlInitUnicodeString` at `0x18008d77b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008d599`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008d6a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008d599`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008d6a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d54f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d583`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d66b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d67d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d7da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d54f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d583`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d66b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d67d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008d7da`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18008d4e8`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18008d4e8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008d63d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008d63d`

## pseudocode

```c
void __fastcall SampCheckRestrictRemoteAccess(HKEY hKey)
{
  int v2; // r15d
  __int64 v3; // r9
  PUNICODE_STRING v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int RegistryString; // eax
  unsigned __int16 *v9; // rbx
  const WCHAR *v10; // r14
  __int64 v11; // rdi
  int v12; // eax
  DWORD LastError; // eax
  HLOCAL v14; // rcx
  unsigned __int16 *v15; // rsi
  unsigned __int64 v16; // rdi
  WCHAR *v17; // rax
  __int64 v18; // r9
  int v19; // edx
  int v20; // r8d
  HLOCAL v21; // rcx
  bool v22; // zf
  unsigned __int64 v23; // rdi
  WCHAR *v24; // rax
  __int64 v25; // r9
  PUNICODE_STRING v26; // rcx
  __int64 v27; // rdx
  void *v28; // r9
  unsigned __int8 v29; // al
  __int64 v30; // r9
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-28h] BYREF
  struct _UNICODE_STRING v33; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v34; // [rsp+C8h] [rbp+48h] BYREF
  unsigned int v35; // [rsp+D0h] [rbp+50h] BYREF
  LPCWCH SourceString; // [rsp+D8h] [rbp+58h] BYREF

  v35 = 0;
  v2 = 0;
  v34 = 0;
  SourceString = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&v33.Length = 0;
  v33.Buffer = 0;
  SecurityDescriptor = 0;
  RtlEnterCriticalSection(&SampRestrictRemoteSessionAccessLock);
  if ( SampGetRegistryDword(hKey, L"RestrictRemoteSamEventThrottlingWindow", &v34) )
  {
    v3 = 900;
    if ( RestrictRemoteSamEventThrottlingWindow != 900 )
    {
      RestrictRemoteSamEventThrottlingWindow = 900;
      v4 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      {
        v5 = 56;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v3 = v34;
    RestrictRemoteSamEventThrottlingWindow = v34;
    v4 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      v5 = 55;
LABEL_9:
      WPP_SF_d(v4[3].Buffer, v5, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, v3);
    }
  }
  if ( SampGetRegistryDword(hKey, L"RestrictRemoteSamAuditOnlyMode", &v35) || !v35 )
  {
    if ( RestrictRemoteSamAuditOnlyMode )
    {
      SampWriteEventLog(SAMMSG_REMOTE_SAM_AUDIT_MODE_DISABLED, 0, v6, v7);
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 58, WPP_5505de3e48bd33375e96ca021b170945_Traceguids);
      }
      RestrictRemoteSamAuditOnlyMode = 0;
    }
  }
  else if ( !RestrictRemoteSamAuditOnlyMode )
  {
    SampWriteEventLog(SAMMSG_REMOTE_SAM_AUDIT_MODE_ENABLED, 0, v6, v7);
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 57, WPP_5505de3e48bd33375e96ca021b170945_Traceguids);
    }
    RestrictRemoteSamAuditOnlyMode = 1;
  }
  RegistryString = SampGetRegistryString(hKey, L"RestrictRemoteSam", (unsigned __int16 **)&SourceString);
  v9 = (unsigned __int16 *)SourceString;
  v10 = (const WCHAR *)&SampDefaultDCRestrictRemoteAccessSDString;
  v11 = -1;
  if ( !RegistryString )
  {
    v2 = 1;
    if ( *SourceString )
    {
      if ( SampCurrentSDDLInAction )
      {
        v12 = CompareStringEx(&Annotation, 1u, SampCurrentSDDLInAction, -1, SourceString, -1, 0, 0, 0);
        if ( !v12 )
        {
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
          {
            LastError = GetLastError();
            WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 59, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, LastError);
          }
          goto LABEL_29;
        }
        if ( v12 == 2 )
          goto LABEL_60;
      }
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v9, 1u, &SecurityDescriptor, 0) )
      {
        v21 = SampRestrictRemoteSessionAccess;
        v22 = SampRestrictRemoteSessionAccess == SampDefaultSecurityDescriptor;
        SampRestrictRemoteSessionAccess = SecurityDescriptor;
        if ( !v22 && v21 )
          LocalFree(v21);
        if ( SampCurrentSDDLInAction )
        {
          LocalFree((HLOCAL)SampCurrentSDDLInAction);
          SampCurrentSDDLInAction = 0;
        }
        do
          ++v11;
        while ( v9[v11] );
        v23 = v11 + 1;
        v24 = (WCHAR *)LocalAlloc(0x40u, 2 * v23);
        SampCurrentSDDLInAction = v24;
        if ( v24 )
          RtlStringCchCopyW(v24, v23, v9);
        RtlInitUnicodeString(&DestinationString, v9);
        SampWriteEventLog(SAMMSG_RESTRICT_REMOTE_SAM_REGISTRY_SD, L"u", &DestinationString, v25);
        v26 = WPP_GLOBAL_Control;
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) == 0
          || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
        {
          goto LABEL_68;
        }
        v27 = 60;
        v28 = v9;
LABEL_67:
        WPP_SF_S(v26[3].Buffer, v27, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, v28);
LABEL_68:
        SampLoggedAtLeastOneSDDLEvent = 1;
        goto LABEL_69;
      }
    }
  }
LABEL_29:
  v14 = SampRestrictRemoteSessionAccess;
  if ( SampRestrictRemoteSessionAccess == SampDefaultSecurityDescriptor )
  {
LABEL_60:
    v29 = SampLoggedAtLeastOneSDDLEvent;
    goto LABEL_61;
  }
  SampRestrictRemoteSessionAccess = SampDefaultSecurityDescriptor;
  if ( v14 )
    LocalFree(v14);
  v15 = (unsigned __int16 *)&SampDefaultDCRestrictRemoteAccessSDString;
  if ( SampProductType != NtProductLanManNt )
    v15 = SampDefaultNonDCRestrictRemoteAccessSDString;
  do
    ++v11;
  while ( v15[v11] );
  v16 = v11 + 1;
  if ( SampCurrentSDDLInAction )
  {
    LocalFree((HLOCAL)SampCurrentSDDLInAction);
    SampCurrentSDDLInAction = 0;
  }
  v17 = (WCHAR *)LocalAlloc(0x40u, 2 * v16);
  SampCurrentSDDLInAction = v17;
  if ( v17 )
    RtlStringCchCopyW(v17, v16, v15);
  RtlInitUnicodeString(&DestinationString, v15);
  if ( v2 )
  {
    RtlInitUnicodeString(&v33, v9);
    SampWriteEventLog(SAMMSG_RESTRICT_REMOTE_SAM_REGISTRY_SD_MALFORMED, L"uu", &v33, &DestinationString);
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    {
      WPP_SF_SS(WPP_GLOBAL_Control[3].Buffer, v19, v20, (_DWORD)v9, (__int64)v15);
    }
    goto LABEL_68;
  }
  SampWriteEventLog(SAMMSG_RESTRICT_REMOTE_SAM_DEFAULT_SD, L"u", &DestinationString, v18);
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_S(WPP_GLOBAL_Control[3].Buffer, 62, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, v15);
  v29 = 1;
  SampLoggedAtLeastOneSDDLEvent = 1;
LABEL_61:
  if ( !v29 )
  {
    if ( SampProductType != NtProductLanManNt )
      v10 = SampDefaultNonDCRestrictRemoteAccessSDString;
    RtlInitUnicodeString(&DestinationString, v10);
    SampWriteEventLog(SAMMSG_RESTRICT_REMOTE_SAM_DEFAULT_SD, L"u", &DestinationString, v30);
    v26 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x40) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
      goto LABEL_68;
    v27 = 63;
    v28 = (void *)v10;
    goto LABEL_67;
  }
LABEL_69:
  RtlLeaveCriticalSection(&SampRestrictRemoteSessionAccessLock);
  LocalFree(v9);
}

```

## disassembly

```asm
0x18008d30c  push    rbp
0x18008d30e  push    rbx
0x18008d30f  push    rsi
0x18008d310  push    rdi
0x18008d311  push    r12
0x18008d313  push    r14
0x18008d315  push    r15
0x18008d317  mov     rbp, rsp
0x18008d31a  sub     rsp, 80h
0x18008d321  xor     r12d, r12d
0x18008d324  mov     rbx, rcx
0x18008d327  lea     rcx, ?SampRestrictRemoteSessionAccessLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008d32e  mov     [rbp+arg_10], r12d
0x18008d332  mov     r15d, r12d
0x18008d335  mov     [rbp+arg_8], r12d
0x18008d339  mov     [rbp+SourceString], r12
0x18008d33d  mov     qword ptr [rbp+DestinationString.Length], r12
0x18008d341  mov     [rbp+DestinationString.Buffer], r12
0x18008d345  mov     qword ptr [rbp+var_18.Length], r12
0x18008d349  mov     [rbp+var_18.Buffer], r12
0x18008d34d  mov     [rbp+SecurityDescriptor], r12
0x18008d351  call    cs:__imp_RtlEnterCriticalSection
0x18008d357  lea     r8, [rbp+arg_8]; unsigned int *
0x18008d35b  mov     rcx, rbx; HKEY
0x18008d35e  lea     rdx, aRestrictremote_0; "RestrictRemoteSamEventThrottlingWindow"
0x18008d365  call    ?SampGetRegistryDword@@YAKPEAUHKEY__@@PEBGPEAK@Z; SampGetRegistryDword(HKEY__ *,ushort const *,ulong *)
0x18008d36a  test    eax, eax
0x18008d36c  jnz     short loc_18008D391
0x18008d36e  mov     r9d, [rbp+arg_8]
0x18008d372  mov     cs:?RestrictRemoteSamEventThrottlingWindow@@3KA, r9d; ulong RestrictRemoteSamEventThrottlingWindow
0x18008d379  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d380  test    byte ptr [rcx+44h], 40h
0x18008d384  jz      short loc_18008D3CF
0x18008d386  cmp     byte ptr [rcx+41h], 4
0x18008d38a  jb      short loc_18008D3CF
0x18008d38c  lea     edx, [rax+37h]
0x18008d38f  jmp     short loc_18008D3BF
0x18008d391  mov     r9d, 384h
0x18008d397  cmp     cs:?RestrictRemoteSamEventThrottlingWindow@@3KA, r9d; ulong RestrictRemoteSamEventThrottlingWindow
0x18008d39e  jz      short loc_18008D3CF
0x18008d3a0  mov     cs:?RestrictRemoteSamEventThrottlingWindow@@3KA, r9d; ulong RestrictRemoteSamEventThrottlingWindow
0x18008d3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d3ae  test    byte ptr [rcx+44h], 40h
0x18008d3b2  jz      short loc_18008D3CF
0x18008d3b4  cmp     byte ptr [rcx+41h], 4
0x18008d3b8  jb      short loc_18008D3CF
0x18008d3ba  mov     edx, 38h ; '8'
0x18008d3bf  mov     rcx, [rcx+38h]
0x18008d3c3  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008d3ca  call    WPP_SF_d
0x18008d3cf  lea     r8, [rbp+arg_10]; unsigned int *
0x18008d3d3  mov     rcx, rbx; HKEY
0x18008d3d6  lea     rdx, aRestrictremote_1; "RestrictRemoteSamAuditOnlyMode"
0x18008d3dd  call    ?SampGetRegistryDword@@YAKPEAUHKEY__@@PEBGPEAK@Z; SampGetRegistryDword(HKEY__ *,ushort const *,ulong *)
0x18008d3e2  mov     esi, 1
0x18008d3e7  test    eax, eax
0x18008d3e9  jnz     short loc_18008D43B
0x18008d3eb  cmp     [rbp+arg_10], r12d
0x18008d3ef  jz      short loc_18008D43B
0x18008d3f1  cmp     cs:?RestrictRemoteSamAuditOnlyMode@@3EA, r12b; uchar RestrictRemoteSamAuditOnlyMode
0x18008d3f8  jnz     loc_18008D481
0x18008d3fe  xor     edx, edx
0x18008d400  lea     rcx, SAMMSG_REMOTE_SAM_AUDIT_MODE_ENABLED
0x18008d407  call    SampWriteEventLog
0x18008d40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d413  test    byte ptr [rcx+44h], 40h
0x18008d417  jz      short loc_18008D432
0x18008d419  cmp     byte ptr [rcx+41h], 4
0x18008d41d  jb      short loc_18008D432
0x18008d41f  mov     rcx, [rcx+38h]
0x18008d423  lea     edx, [rsi+38h]
0x18008d426  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008d42d  call    WPP_SF_
0x18008d432  mov     cs:?RestrictRemoteSamAuditOnlyMode@@3EA, sil; uchar RestrictRemoteSamAuditOnlyMode
0x18008d439  jmp     short loc_18008D481
0x18008d43b  cmp     cs:?RestrictRemoteSamAuditOnlyMode@@3EA, r12b; uchar RestrictRemoteSamAuditOnlyMode
0x18008d442  jz      short loc_18008D481
0x18008d444  xor     edx, edx
0x18008d446  lea     rcx, SAMMSG_REMOTE_SAM_AUDIT_MODE_DISABLED
0x18008d44d  call    SampWriteEventLog
0x18008d452  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d459  test    byte ptr [rcx+44h], 40h
0x18008d45d  jz      short loc_18008D47A
0x18008d45f  cmp     byte ptr [rcx+41h], 4
0x18008d463  jb      short loc_18008D47A
0x18008d465  mov     rcx, [rcx+38h]
0x18008d469  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008d470  mov     edx, 3Ah ; ':'
0x18008d475  call    WPP_SF_
0x18008d47a  mov     cs:?RestrictRemoteSamAuditOnlyMode@@3EA, r12b; uchar RestrictRemoteSamAuditOnlyMode
0x18008d481  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x18008d485  mov     rcx, rbx; hKey
0x18008d488  lea     rdx, aRestrictremote; "RestrictRemoteSam"
0x18008d48f  call    ?SampGetRegistryString@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; SampGetRegistryString(HKEY__ *,ushort const *,ushort * *)
0x18008d494  mov     rbx, [rbp+SourceString]
0x18008d498  lea     r14, ?SampDefaultDCRestrictRemoteAccessSDString@@3PAGA; ushort near * SampDefaultDCRestrictRemoteAccessSDString
0x18008d49f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008d4a3  test    eax, eax
0x18008d4a5  jnz     loc_18008D52C
0x18008d4ab  mov     r15d, esi
0x18008d4ae  cmp     [rbx], r12w
0x18008d4b2  jz      short loc_18008D52C
0x18008d4b4  mov     r8, cs:?SampCurrentSDDLInAction@@3PEAGEA; lpString1
0x18008d4bb  test    r8, r8
0x18008d4be  jz      loc_18008D631
0x18008d4c4  mov     [rsp+80h+lParam], r12; lParam
0x18008d4c9  lea     rcx, Annotation; lpLocaleName
0x18008d4d0  mov     [rsp+80h+lpReserved], r12; lpReserved
0x18008d4d5  mov     r9d, edi; cchCount1
0x18008d4d8  mov     [rsp+80h+lpVersionInformation], r12; lpVersionInformation
0x18008d4dd  mov     edx, esi; dwCmpFlags
0x18008d4df  mov     [rsp+80h+cchCount2], edi; cchCount2
0x18008d4e3  mov     [rsp+80h+lpString2], rbx; lpString2
0x18008d4e8  call    cs:__imp_CompareStringEx
0x18008d4ee  test    eax, eax
0x18008d4f0  jnz     loc_18008D628
0x18008d4f6  mov     rax, cs:WPP_GLOBAL_Control
0x18008d4fd  test    byte ptr [rax+44h], 40h
0x18008d501  jz      short loc_18008D52C
0x18008d503  cmp     byte ptr [rax+41h], 3
0x18008d507  jb      short loc_18008D52C
0x18008d509  call    cs:__imp_GetLastError
0x18008d50f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d516  lea     edx, [rdi+3Ch]
0x18008d519  mov     r9d, eax
0x18008d51c  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008d523  mov     rcx, [rcx+38h]
0x18008d527  call    WPP_SF_d
0x18008d52c  mov     rcx, cs:?SampRestrictRemoteSessionAccess@@3PEAXEA; hMem
0x18008d533  mov     rax, cs:?SampDefaultSecurityDescriptor@@3PEAXEA; void * SampDefaultSecurityDescriptor
0x18008d53a  cmp     rcx, rax
0x18008d53d  jz      loc_18008D758
0x18008d543  mov     cs:?SampRestrictRemoteSessionAccess@@3PEAXEA, rax; void * SampRestrictRemoteSessionAccess
0x18008d54a  test    rcx, rcx
0x18008d54d  jz      short loc_18008D555
0x18008d54f  call    cs:__imp_LocalFree
0x18008d555  cmp     cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A, 2; _NT_PRODUCT_TYPE SampProductType
0x18008d55c  lea     rax, ?SampDefaultNonDCRestrictRemoteAccessSDString@@3PAGA; "O:SYG:SYD:(A;;RC;;;BA)"
0x18008d563  mov     rsi, r14
0x18008d566  cmovnz  rsi, rax
0x18008d56a  inc     rdi
0x18008d56d  cmp     [rsi+rdi*2], r12w
0x18008d572  jnz     short loc_18008D56A
0x18008d574  mov     rcx, cs:?SampCurrentSDDLInAction@@3PEAGEA; hMem
0x18008d57b  inc     rdi
0x18008d57e  test    rcx, rcx
0x18008d581  jz      short loc_18008D590
0x18008d583  call    cs:__imp_LocalFree
0x18008d589  mov     cs:?SampCurrentSDDLInAction@@3PEAGEA, r12; ushort * SampCurrentSDDLInAction
0x18008d590  lea     rdx, [rdi+rdi]; uBytes
0x18008d594  mov     ecx, 40h ; '@'; uFlags
0x18008d599  call    cs:__imp_LocalAlloc
0x18008d59f  mov     cs:?SampCurrentSDDLInAction@@3PEAGEA, rax; ushort * SampCurrentSDDLInAction
0x18008d5a6  test    rax, rax
0x18008d5a9  jz      short loc_18008D5B9
0x18008d5ab  mov     r8, rsi; unsigned __int16 *
0x18008d5ae  mov     rdx, rdi; unsigned __int64
0x18008d5b1  mov     rcx, rax; unsigned __int16 *
0x18008d5b4  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008d5b9  mov     rdx, rsi; SourceString
0x18008d5bc  lea     rcx, [rbp+DestinationString]; DestinationString
0x18008d5c0  call    cs:__imp_RtlInitUnicodeString
0x18008d5c6  test    r15d, r15d
0x18008d5c9  jz      loc_18008D70C
0x18008d5cf  mov     rdx, rbx; SourceString
0x18008d5d2  lea     rcx, [rbp+var_18]; DestinationString
0x18008d5d6  call    cs:__imp_RtlInitUnicodeString
0x18008d5dc  lea     r9, [rbp+DestinationString]
0x18008d5e0  lea     r8, [rbp+var_18]
0x18008d5e4  lea     rdx, aUu; "uu"
0x18008d5eb  lea     rcx, SAMMSG_RESTRICT_REMOTE_SAM_REGISTRY_SD_MALFORMED
0x18008d5f2  call    SampWriteEventLog
0x18008d5f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d5fe  test    byte ptr [rcx+44h], 40h
0x18008d602  jz      loc_18008D7C3
0x18008d608  cmp     byte ptr [rcx+41h], 4
0x18008d60c  jb      loc_18008D7C3
0x18008d612  mov     rcx, [rcx+38h]
0x18008d616  mov     r9, rbx
0x18008d619  mov     [rsp+80h+lpString2], rsi
0x18008d61e  call    WPP_SF_SS
0x18008d623  jmp     loc_18008D7C3
0x18008d628  cmp     eax, 2
0x18008d62b  jz      loc_18008D758
0x18008d631  xor     r9d, r9d; SecurityDescriptorSize
0x18008d634  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18008d638  mov     edx, esi; StringSDRevision
0x18008d63a  mov     rcx, rbx; StringSecurityDescriptor
0x18008d63d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18008d643  test    eax, eax
0x18008d645  jz      loc_18008D52C
0x18008d64b  mov     rcx, cs:?SampRestrictRemoteSessionAccess@@3PEAXEA; hMem
0x18008d652  cmp     rcx, cs:?SampDefaultSecurityDescriptor@@3PEAXEA; void * SampDefaultSecurityDescriptor
0x18008d659  mov     rax, [rbp+SecurityDescriptor]
0x18008d65d  mov     cs:?SampRestrictRemoteSessionAccess@@3PEAXEA, rax; void * SampRestrictRemoteSessionAccess
0x18008d664  jz      short loc_18008D671
0x18008d666  test    rcx, rcx
0x18008d669  jz      short loc_18008D671
0x18008d66b  call    cs:__imp_LocalFree
0x18008d671  mov     rcx, cs:?SampCurrentSDDLInAction@@3PEAGEA; hMem
0x18008d678  test    rcx, rcx
0x18008d67b  jz      short loc_18008D68A
0x18008d67d  call    cs:__imp_LocalFree
0x18008d683  mov     cs:?SampCurrentSDDLInAction@@3PEAGEA, r12; ushort * SampCurrentSDDLInAction
0x18008d68a  inc     rdi
0x18008d68d  cmp     [rbx+rdi*2], r12w
0x18008d692  jnz     short loc_18008D68A
0x18008d694  inc     rdi
0x18008d697  mov     ecx, 40h ; '@'; uFlags
0x18008d69c  lea     rdx, [rdi+rdi]; uBytes
0x18008d6a0  call    cs:__imp_LocalAlloc
0x18008d6a6  mov     cs:?SampCurrentSDDLInAction@@3PEAGEA, rax; ushort * SampCurrentSDDLInAction
0x18008d6ad  test    rax, rax
0x18008d6b0  jz      short loc_18008D6C0
0x18008d6b2  mov     r8, rbx; unsigned __int16 *
0x18008d6b5  mov     rdx, rdi; unsigned __int64
0x18008d6b8  mov     rcx, rax; unsigned __int16 *
0x18008d6bb  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008d6c0  mov     rdx, rbx; SourceString
0x18008d6c3  lea     rcx, [rbp+DestinationString]; DestinationString
0x18008d6c7  call    cs:__imp_RtlInitUnicodeString
0x18008d6cd  lea     r8, [rbp+DestinationString]
0x18008d6d1  lea     rdx, aU; "u"
0x18008d6d8  lea     rcx, SAMMSG_RESTRICT_REMOTE_SAM_REGISTRY_SD
0x18008d6df  call    SampWriteEventLog
0x18008d6e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d6eb  test    byte ptr [rcx+44h], 40h
0x18008d6ef  jz      loc_18008D7C3
0x18008d6f5  cmp     byte ptr [rcx+41h], 4
0x18008d6f9  jb      loc_18008D7C3
0x18008d6ff  mov     edx, 3Ch ; '<'
0x18008d704  mov     r9, rbx
0x18008d707  jmp     loc_18008D7B3
0x18008d70c  lea     r8, [rbp+DestinationString]
0x18008d710  lea     rdx, aU; "u"
0x18008d717  lea     rcx, SAMMSG_RESTRICT_REMOTE_SAM_DEFAULT_SD
0x18008d71e  call    SampWriteEventLog
0x18008d723  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d72a  test    byte ptr [rcx+44h], 40h
0x18008d72e  jz      short loc_18008D74E
0x18008d730  cmp     byte ptr [rcx+41h], 4
0x18008d734  jb      short loc_18008D74E
0x18008d736  mov     rcx, [rcx+38h]
0x18008d73a  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008d741  mov     edx, 3Eh ; '>'
0x18008d746  mov     r9, rsi
0x18008d749  call    WPP_SF_S
0x18008d74e  mov     al, 1
0x18008d750  mov     cs:?SampLoggedAtLeastOneSDDLEvent@@3EA, al; uchar SampLoggedAtLeastOneSDDLEvent
0x18008d756  jmp     short loc_18008D75E
0x18008d758  mov     al, cs:?SampLoggedAtLeastOneSDDLEvent@@3EA; uchar SampLoggedAtLeastOneSDDLEvent
0x18008d75e  test    al, al
0x18008d760  jnz     short loc_18008D7CA
0x18008d762  cmp     cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A, 2; _NT_PRODUCT_TYPE SampProductType
0x18008d769  lea     rax, ?SampDefaultNonDCRestrictRemoteAccessSDString@@3PAGA; "O:SYG:SYD:(A;;RC;;;BA)"
0x18008d770  lea     rcx, [rbp+DestinationString]; DestinationString
0x18008d774  cmovnz  r14, rax
0x18008d778  mov     rdx, r14; SourceString
0x18008d77b  call    cs:__imp_RtlInitUnicodeString
0x18008d781  lea     r8, [rbp+DestinationString]
0x18008d785  lea     rdx, aU; "u"
0x18008d78c  lea     rcx, SAMMSG_RESTRICT_REMOTE_SAM_DEFAULT_SD
0x18008d793  call    SampWriteEventLog
0x18008d798  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d79f  test    byte ptr [rcx+44h], 40h
0x18008d7a3  jz      short loc_18008D7C3
0x18008d7a5  cmp     byte ptr [rcx+41h], 4
0x18008d7a9  jb      short loc_18008D7C3
0x18008d7ab  mov     edx, 3Fh ; '?'
0x18008d7b0  mov     r9, r14
0x18008d7b3  mov     rcx, [rcx+38h]
0x18008d7b7  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008d7be  call    WPP_SF_S
0x18008d7c3  mov     cs:?SampLoggedAtLeastOneSDDLEvent@@3EA, 1; uchar SampLoggedAtLeastOneSDDLEvent
0x18008d7ca  lea     rcx, ?SampRestrictRemoteSessionAccessLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18008d7d1  call    cs:__imp_RtlLeaveCriticalSection
0x18008d7d7  mov     rcx, rbx; hMem
0x18008d7da  call    cs:__imp_LocalFree
0x18008d7e0  add     rsp, 80h
0x18008d7e7  pop     r15
0x18008d7e9  pop     r14
0x18008d7eb  pop     r12
0x18008d7ed  pop     rdi
0x18008d7ee  pop     rsi
0x18008d7ef  pop     rbx
0x18008d7f0  pop     rbp
0x18008d7f1  retn
```
