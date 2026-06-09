# WsLoadRedir

- ea: `0x18000c350`
- end: `0x18000c59e`
- name: `WsLoadRedir`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025f10`

## callees

- `0x18000b43c`
- `0x18000b4f0`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000c350`
- `0x18000c5a4`
- `0x180028c40`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000c539`
- `ntdll!NtOpenFile` at `0x18000c539`
- `ntdll!RtlNtStatusToDosError` at `0x18000c486`
- `ntdll!RtlNtStatusToDosError` at `0x18000c57c`
- `ntdll!RtlNtStatusToDosError` at `0x18000c486`
- `ntdll!RtlNtStatusToDosError` at `0x18000c57c`
- `ntdll!NtSetInformationThread` at `0x18000c47a`
- `ntdll!NtSetInformationThread` at `0x18000c47a`
- `ntdll!RtlInitUnicodeString` at `0x18000c457`
- `ntdll!RtlInitUnicodeString` at `0x18000c4e9`
- `ntdll!RtlInitUnicodeString` at `0x18000c457`
- `ntdll!RtlInitUnicodeString` at `0x18000c4e9`
- `KERNEL32!LocalFree` at `0x18000c424`
- `KERNEL32!LocalFree` at `0x18000c48f`
- `KERNEL32!LocalFree` at `0x18000c424`
- `KERNEL32!LocalFree` at `0x18000c48f`
- `KERNEL32!LocalAlloc` at `0x18000c392`
- `KERNEL32!LocalAlloc` at `0x18000c392`

## string_xrefs

- `0x18000c42c`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c
ULONG WsLoadRedir()
{
  __int64 v0; // rcx
  HLOCAL v1; // r14
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  DWORD Privilege; // esi
  int v5; // eax
  unsigned int v7; // eax
  NTSTATUS v8; // ebx
  struct _UNICODE_STRING v9; // [rsp+30h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  __int64 ThreadInformation; // [rsp+B0h] [rbp+67h] BYREF

  v9 = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v1 = LocalAlloc(0x40u, 0x78u);
  if ( !v1 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_00942ebad62f32576d66ff82ff952e11_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    v3 = 8;
    goto LABEL_18;
  }
  LODWORD(ThreadInformation) = 10;
  Privilege = NetpGetPrivilege(v0, (unsigned int *)&ThreadInformation);
  if ( Privilege )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_00942ebad62f32576d66ff82ff952e11_Traceguids);
    LocalFree(v1);
  }
  else
  {
    StringCbCopyW((STRSAFE_LPWSTR)v1, 0x78u, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\");
    StringCbCatW((STRSAFE_LPWSTR)v1, 0x78u, L"MRxDAV");
    RtlInitUnicodeString(&DestinationString, (PCWSTR)v1);
    ThreadInformation = 0;
    v5 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v5 < 0 )
      RtlNtStatusToDosError(v5);
    LocalFree(v1);
    Privilege = WsMapStatus(0);
  }
  v3 = 0;
  if ( Privilege != 1056 )
    v3 = Privilege;
  if ( v3 )
  {
    v2 = WPP_GLOBAL_Control;
LABEL_18:
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
      WPP_SF_d(v2[2], 10, WPP_00942ebad62f32576d66ff82ff952e11_Traceguids, v3);
    return v3;
  }
  RtlInitUnicodeString(&v9, L"\\Device\\WebDavRedirector");
  ObjectAttributes.ObjectName = &v9;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&DavRedirDeviceHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  v8 = v7;
  if ( !v7 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_00942ebad62f32576d66ff82ff952e11_Traceguids, v7);
  DavRedirDeviceHandle = (HANDLE)-1LL;
  return RtlNtStatusToDosError(v8);
}

```

## disassembly

```asm
0x18000c350  mov     [rsp-8+arg_8], rbx
0x18000c355  mov     [rsp-8+arg_10], rsi
0x18000c35a  push    rbp
0x18000c35b  push    rdi
0x18000c35c  push    r14
0x18000c35e  lea     rbp, [rsp-47h]
0x18000c363  sub     rsp, 90h
0x18000c36a  xorps   xmm0, xmm0
0x18000c36d  xor     eax, eax
0x18000c36f  xorps   xmm1, xmm1
0x18000c372  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000c376  lea     ebx, [rax+78h]
0x18000c379  mov     edx, ebx; uBytes
0x18000c37b  lea     ecx, [rax+40h]; uFlags
0x18000c37e  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x18000c382  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x18000c386  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000c38a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000c38e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000c392  call    cs:__imp_LocalAlloc
0x18000c398  mov     r14, rax
0x18000c39b  test    rax, rax
0x18000c39e  jnz     short loc_18000C3DD
0x18000c3a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3a7  lea     rdi, WPP_GLOBAL_Control
0x18000c3ae  cmp     rcx, rdi
0x18000c3b1  jz      short loc_18000C3D3
0x18000c3b3  test    byte ptr [rcx+1Ch], 1
0x18000c3b7  jz      short loc_18000C3D3
0x18000c3b9  mov     rcx, [rcx+10h]
0x18000c3bd  lea     edx, [rbx-6Ch]
0x18000c3c0  lea     r8, WPP_00942ebad62f32576d66ff82ff952e11_Traceguids
0x18000c3c7  call    WPP_SF_
0x18000c3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3d3  mov     ebx, 8
0x18000c3d8  jmp     loc_18000C4B4
0x18000c3dd  lea     rdx, [rbp+57h+ThreadInformation]
0x18000c3e1  mov     dword ptr [rbp+57h+ThreadInformation], 0Ah
0x18000c3e8  call    NetpGetPrivilege
0x18000c3ed  lea     rdi, WPP_GLOBAL_Control
0x18000c3f4  mov     esi, eax
0x18000c3f6  test    eax, eax
0x18000c3f8  jz      short loc_18000C42C
0x18000c3fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c401  cmp     rcx, rdi
0x18000c404  jz      short loc_18000C421
0x18000c406  test    byte ptr [rcx+1Ch], 1
0x18000c40a  jz      short loc_18000C421
0x18000c40c  mov     rcx, [rcx+10h]
0x18000c410  lea     r8, WPP_00942ebad62f32576d66ff82ff952e11_Traceguids
0x18000c417  mov     edx, 0Dh
0x18000c41c  call    WPP_SF_
0x18000c421  mov     rcx, r14; hMem
0x18000c424  call    cs:__imp_LocalFree
0x18000c42a  jmp     short loc_18000C49E
0x18000c42c  lea     r8, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000c433  mov     rdx, rbx; cbDest
0x18000c436  mov     rcx, r14; pszDest
0x18000c439  call    StringCbCopyW
0x18000c43e  lea     r8, aMrxdav_0; "MRxDAV"
0x18000c445  mov     rdx, rbx; cbDest
0x18000c448  mov     rcx, r14; pszDest
0x18000c44b  call    StringCbCatW
0x18000c450  mov     rdx, r14; SourceString
0x18000c453  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000c457  call    cs:__imp_RtlInitUnicodeString
0x18000c45d  mov     r9d, 8; ThreadInformationLength
0x18000c463  mov     [rbp+57h+ThreadInformation], 0
0x18000c46b  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18000c46f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000c476  lea     edx, [r9-3]; ThreadInformationClass
0x18000c47a  call    cs:__imp_NtSetInformationThread
0x18000c480  test    eax, eax
0x18000c482  jns     short loc_18000C48C
0x18000c484  mov     ecx, eax; Status
0x18000c486  call    cs:__imp_RtlNtStatusToDosError
0x18000c48c  mov     rcx, r14; hMem
0x18000c48f  call    cs:__imp_LocalFree
0x18000c495  xor     ecx, ecx
0x18000c497  call    WsMapStatus
0x18000c49c  mov     esi, eax
0x18000c49e  xor     ebx, ebx
0x18000c4a0  cmp     esi, 420h
0x18000c4a6  cmovnz  ebx, esi
0x18000c4a9  test    ebx, ebx
0x18000c4ab  jz      short loc_18000C4DE
0x18000c4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4b4  cmp     rcx, rdi
0x18000c4b7  jz      short loc_18000C4D7
0x18000c4b9  test    byte ptr [rcx+1Ch], 1
0x18000c4bd  jz      short loc_18000C4D7
0x18000c4bf  mov     rcx, [rcx+10h]
0x18000c4c3  lea     r8, WPP_00942ebad62f32576d66ff82ff952e11_Traceguids
0x18000c4ca  mov     edx, 0Ah
0x18000c4cf  mov     r9d, ebx
0x18000c4d2  call    WPP_SF_d
0x18000c4d7  mov     eax, ebx
0x18000c4d9  jmp     loc_18000C586
0x18000c4de  lea     rdx, aDeviceWebdavre_1; "\\Device\\WebDavRedirector"
0x18000c4e5  lea     rcx, [rbp+57h+var_70]; DestinationString
0x18000c4e9  call    cs:__imp_RtlInitUnicodeString
0x18000c4ef  lea     rax, [rbp+57h+var_70]
0x18000c4f3  mov     [rsp+0A0h+OpenOptions], 20h ; ' '; OpenOptions
0x18000c4fb  xorps   xmm0, xmm0
0x18000c4fe  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000c502  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000c506  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000c50d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000c511  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000c519  mov     edx, 100000h; DesiredAccess
0x18000c51e  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000c525  lea     rcx, DavRedirDeviceHandle; FileHandle
0x18000c52c  mov     [rsp+0A0h+ShareAccess], 7; ShareAccess
0x18000c534  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c539  call    cs:__imp_NtOpenFile
0x18000c53f  mov     ebx, eax
0x18000c541  test    eax, eax
0x18000c543  jz      short loc_18000C584
0x18000c545  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c54c  cmp     rcx, rdi
0x18000c54f  jz      short loc_18000C56F
0x18000c551  test    byte ptr [rcx+1Ch], 1
0x18000c555  jz      short loc_18000C56F
0x18000c557  mov     rcx, [rcx+10h]
0x18000c55b  lea     r8, WPP_00942ebad62f32576d66ff82ff952e11_Traceguids
0x18000c562  mov     edx, 0Bh
0x18000c567  mov     r9d, eax
0x18000c56a  call    WPP_SF_d
0x18000c56f  mov     ecx, ebx; Status
0x18000c571  mov     cs:DavRedirDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x18000c57c  call    cs:__imp_RtlNtStatusToDosError
0x18000c582  jmp     short loc_18000C586
0x18000c584  xor     eax, eax
0x18000c586  lea     r11, [rsp+0A0h+var_10]
0x18000c58e  mov     rbx, [r11+28h]
0x18000c592  mov     rsi, [r11+30h]
0x18000c596  mov     rsp, r11
0x18000c599  pop     r14
0x18000c59b  pop     rdi
0x18000c59c  pop     rbp
0x18000c59d  retn
```
