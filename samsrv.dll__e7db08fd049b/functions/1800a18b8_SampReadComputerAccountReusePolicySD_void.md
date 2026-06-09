# SampReadComputerAccountReusePolicySD(void * *)

- ea: `0x1800a18b8`
- end: `0x1800a1ab0`
- name: `?SampReadComputerAccountReusePolicySD@@YAJPEAPEAX@Z`
- size: `504`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a2db4`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x1800a18b8`
- `0x1800b03d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a192c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a192c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1936`
- `ntdll!RtlCopySecurityDescriptor` at `0x1800a19bd`
- `ntdll!RtlCopySecurityDescriptor` at `0x1800a19f0`
- `ntdll!RtlCopySecurityDescriptor` at `0x1800a19bd`
- `ntdll!RtlCopySecurityDescriptor` at `0x1800a19f0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a1a4e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a1a4e`
- `ntdll!RtlEnterCriticalSection` at `0x1800a18e8`
- `ntdll!RtlEnterCriticalSection` at `0x1800a18e8`
- `ntdll!RtlInitUnicodeString` at `0x1800a197b`
- `ntdll!RtlInitUnicodeString` at `0x1800a197b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a19a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1a3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1a5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1a6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a19a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1a3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1a5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1a6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a1918`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a1918`

## pseudocode

```c
__int64 __fastcall SampReadComputerAccountReusePolicySD(void **a1)
{
  unsigned int LastError; // ebx
  __int64 v3; // r9
  PSECURITY_DESCRIPTOR v4; // rcx
  NTSTATUS v5; // eax
  PUNICODE_STRING v6; // rcx
  __int64 v7; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR pDestinationSecurityDescriptor; // [rsp+50h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+18h] BYREF

  LastError = 0;
  *a1 = 0;
  pDestinationSecurityDescriptor = 0;
  SecurityDescriptor = 0;
  DestinationString = 0;
  RtlEnterCriticalSection(&gcsComputerAccountReuseAllowListLock);
  if ( SampComputerAccountReuseAllowListSD )
  {
    if ( !SampComputerAccountReuseAllowListSDDL )
    {
      LocalFree(SampComputerAccountReuseAllowListSD);
      SampComputerAccountReuseAllowListSD = 0;
      goto LABEL_23;
    }
    v5 = RtlCopySecurityDescriptor(SampComputerAccountReuseAllowListSD, &pDestinationSecurityDescriptor);
    LastError = v5;
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
        goto LABEL_23;
      }
      v7 = 372;
LABEL_20:
      WPP_SF_d(v6[3].Buffer, v7, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, (unsigned int)v5);
      goto LABEL_23;
    }
LABEL_21:
    *a1 = pDestinationSecurityDescriptor;
    pDestinationSecurityDescriptor = 0;
    goto LABEL_23;
  }
  if ( !SampComputerAccountReuseAllowListSDDL )
    goto LABEL_23;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         SampComputerAccountReuseAllowListSDDL,
         1u,
         &SecurityDescriptor,
         0) )
  {
    LocalFree(SampComputerAccountReuseAllowListSD);
    v4 = SecurityDescriptor;
    SampComputerAccountReuseAllowListSD = SecurityDescriptor;
    SecurityDescriptor = 0;
    v5 = RtlCopySecurityDescriptor(v4, &pDestinationSecurityDescriptor);
    LastError = v5;
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) == 0
        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      {
        goto LABEL_23;
      }
      v7 = 374;
      goto LABEL_20;
    }
    goto LABEL_21;
  }
  if ( (int)GetLastError() > 0 )
    LastError = (unsigned __int16)GetLastError() | 0xC0070000;
  else
    LastError = GetLastError();
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 373, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, LastError);
  RtlInitUnicodeString(&DestinationString, SampComputerAccountReuseAllowListSDDL);
  SampWriteEventLog(SAMMSG_COMPUTER_ACCOUNT_REUSE_ALLOW_LIST_MALFORMED, L"u", &DestinationString, v3);
LABEL_23:
  RtlLeaveCriticalSection(&gcsComputerAccountReuseAllowListLock);
  if ( pDestinationSecurityDescriptor )
    LocalFree(pDestinationSecurityDescriptor);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 375, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, LastError, LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800a18b8  mov     [rsp-8+arg_10], rbx
0x1800a18bd  mov     [rsp-8+arg_18], rdi
0x1800a18c2  push    rbp
0x1800a18c3  mov     rbp, rsp
0x1800a18c6  sub     rsp, 40h
0x1800a18ca  xor     ebx, ebx
0x1800a18cc  mov     rdi, rcx
0x1800a18cf  mov     [rcx], rbx
0x1800a18d2  xorps   xmm0, xmm0
0x1800a18d5  lea     rcx, ?gcsComputerAccountReuseAllowListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800a18dc  mov     [rbp+pDestinationSecurityDescriptor], rbx
0x1800a18e0  mov     [rbp+SecurityDescriptor], rbx
0x1800a18e4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800a18e8  call    cs:__imp_RtlEnterCriticalSection
0x1800a18ee  mov     rcx, cs:?SampComputerAccountReuseAllowListSD@@3PEAXEA; hMem
0x1800a18f5  test    rcx, rcx
0x1800a18f8  jnz     loc_1800A19E3
0x1800a18fe  mov     rcx, cs:?SampComputerAccountReuseAllowListSDDL@@3PEAGEA; StringSecurityDescriptor
0x1800a1905  test    rcx, rcx
0x1800a1908  jz      loc_1800A1A47
0x1800a190e  xor     r9d, r9d; SecurityDescriptorSize
0x1800a1911  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800a1915  lea     edx, [rbx+1]; StringSDRevision
0x1800a1918  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800a191e  test    eax, eax
0x1800a1920  jnz     short loc_1800A199D
0x1800a1922  call    cs:__imp_GetLastError
0x1800a1928  test    eax, eax
0x1800a192a  jg      short loc_1800A1936
0x1800a192c  call    cs:__imp_GetLastError
0x1800a1932  mov     ebx, eax
0x1800a1934  jmp     short loc_1800A1945
0x1800a1936  call    cs:__imp_GetLastError
0x1800a193c  movzx   ebx, ax
0x1800a193f  or      ebx, 0C0070000h
0x1800a1945  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a194c  test    byte ptr [rcx+44h], 20h
0x1800a1950  jz      short loc_1800A1970
0x1800a1952  cmp     byte ptr [rcx+41h], 2
0x1800a1956  jb      short loc_1800A1970
0x1800a1958  mov     rcx, [rcx+38h]
0x1800a195c  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800a1963  mov     edx, 175h
0x1800a1968  mov     r9d, ebx
0x1800a196b  call    WPP_SF_d
0x1800a1970  mov     rdx, cs:?SampComputerAccountReuseAllowListSDDL@@3PEAGEA; SourceString
0x1800a1977  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800a197b  call    cs:__imp_RtlInitUnicodeString
0x1800a1981  lea     r8, [rbp+DestinationString]
0x1800a1985  lea     rdx, aU; "u"
0x1800a198c  lea     rcx, SAMMSG_COMPUTER_ACCOUNT_REUSE_ALLOW_LIST_MALFORMED
0x1800a1993  call    SampWriteEventLog
0x1800a1998  jmp     loc_1800A1A47
0x1800a199d  mov     rcx, cs:?SampComputerAccountReuseAllowListSD@@3PEAXEA; hMem
0x1800a19a4  call    cs:__imp_LocalFree
0x1800a19aa  mov     rcx, [rbp+SecurityDescriptor]; pSourceSecurityDescriptor
0x1800a19ae  lea     rdx, [rbp+pDestinationSecurityDescriptor]; pDestinationSecurityDescriptor
0x1800a19b2  mov     cs:?SampComputerAccountReuseAllowListSD@@3PEAXEA, rcx; void * SampComputerAccountReuseAllowListSD
0x1800a19b9  mov     [rbp+SecurityDescriptor], rbx
0x1800a19bd  call    cs:__imp_RtlCopySecurityDescriptor
0x1800a19c3  mov     ebx, eax
0x1800a19c5  test    eax, eax
0x1800a19c7  jns     short loc_1800A1A29
0x1800a19c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a19d0  test    byte ptr [rcx+44h], 20h
0x1800a19d4  jz      short loc_1800A1A47
0x1800a19d6  cmp     byte ptr [rcx+41h], 2
0x1800a19da  jb      short loc_1800A1A47
0x1800a19dc  mov     edx, 176h
0x1800a19e1  jmp     short loc_1800A1A14
0x1800a19e3  cmp     cs:?SampComputerAccountReuseAllowListSDDL@@3PEAGEA, rbx; ushort * SampComputerAccountReuseAllowListSDDL
0x1800a19ea  jz      short loc_1800A1A3A
0x1800a19ec  lea     rdx, [rbp+pDestinationSecurityDescriptor]; pDestinationSecurityDescriptor
0x1800a19f0  call    cs:__imp_RtlCopySecurityDescriptor
0x1800a19f6  mov     ebx, eax
0x1800a19f8  test    eax, eax
0x1800a19fa  jns     short loc_1800A1A29
0x1800a19fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1a03  test    byte ptr [rcx+44h], 20h
0x1800a1a07  jz      short loc_1800A1A47
0x1800a1a09  cmp     byte ptr [rcx+41h], 2
0x1800a1a0d  jb      short loc_1800A1A47
0x1800a1a0f  mov     edx, 174h
0x1800a1a14  mov     rcx, [rcx+38h]
0x1800a1a18  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800a1a1f  mov     r9d, eax
0x1800a1a22  call    WPP_SF_d
0x1800a1a27  jmp     short loc_1800A1A47
0x1800a1a29  mov     rax, [rbp+pDestinationSecurityDescriptor]
0x1800a1a2d  mov     [rdi], rax
0x1800a1a30  mov     [rbp+pDestinationSecurityDescriptor], 0
0x1800a1a38  jmp     short loc_1800A1A47
0x1800a1a3a  call    cs:__imp_LocalFree
0x1800a1a40  mov     cs:?SampComputerAccountReuseAllowListSD@@3PEAXEA, rbx; void * SampComputerAccountReuseAllowListSD
0x1800a1a47  lea     rcx, ?gcsComputerAccountReuseAllowListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800a1a4e  call    cs:__imp_RtlLeaveCriticalSection
0x1800a1a54  mov     rcx, [rbp+pDestinationSecurityDescriptor]; hMem
0x1800a1a58  test    rcx, rcx
0x1800a1a5b  jz      short loc_1800A1A63
0x1800a1a5d  call    cs:__imp_LocalFree
0x1800a1a63  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800a1a67  test    rcx, rcx
0x1800a1a6a  jz      short loc_1800A1A72
0x1800a1a6c  call    cs:__imp_LocalFree
0x1800a1a72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1a79  test    dword ptr [rcx+44h], 20000h
0x1800a1a80  jz      short loc_1800A1A9E
0x1800a1a82  mov     rcx, [rcx+38h]
0x1800a1a86  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800a1a8d  mov     edx, 177h
0x1800a1a92  mov     [rsp+40h+var_20], ebx
0x1800a1a96  mov     r9d, ebx
0x1800a1a99  call    WPP_SF_Dd
0x1800a1a9e  mov     rdi, [rsp+40h+arg_18]
0x1800a1aa3  mov     eax, ebx
0x1800a1aa5  mov     rbx, [rsp+40h+arg_10]
0x1800a1aaa  add     rsp, 40h
0x1800a1aae  pop     rbp
0x1800a1aaf  retn
```
