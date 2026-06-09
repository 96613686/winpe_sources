# WsUnloadRedir

- ea: `0x18000c628`
- end: `0x18000c728`
- name: `WsUnloadRedir`
- size: `256`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x180025bf8`

## callees

- `0x18000b43c`
- `0x18000b4f0`
- `0x18000c5a4`
- `0x18000c628`
- `0x180028c40`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000c70b`
- `ntdll!RtlNtStatusToDosError` at `0x18000c70b`
- `ntdll!NtClose` at `0x18000c694`
- `ntdll!NtClose` at `0x18000c694`
- `ntdll!NtSetInformationThread` at `0x18000c6ff`
- `ntdll!NtSetInformationThread` at `0x18000c6ff`
- `ntdll!RtlInitUnicodeString` at `0x18000c6d1`
- `ntdll!RtlInitUnicodeString` at `0x18000c6d1`
- `KERNEL32!LocalFree` at `0x18000c67a`
- `KERNEL32!LocalFree` at `0x18000c6da`
- `KERNEL32!LocalFree` at `0x18000c67a`
- `KERNEL32!LocalFree` at `0x18000c6da`
- `KERNEL32!LocalAlloc` at `0x18000c649`
- `KERNEL32!LocalAlloc` at `0x18000c649`

## string_xrefs

- `0x18000c6a5`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c
__int64 WsUnloadRedir()
{
  __int64 v0; // rcx
  HLOCAL v1; // rbx
  DWORD Privilege; // edi
  int v4; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp+8h] BYREF

  DestinationString = 0;
  v1 = LocalAlloc(0x40u, 0x78u);
  if ( !v1 )
    return 8;
  LODWORD(ThreadInformation) = 10;
  Privilege = NetpGetPrivilege(v0, (unsigned int *)&ThreadInformation);
  if ( Privilege )
  {
    LocalFree(v1);
    return Privilege;
  }
  else
  {
    if ( DavRedirDeviceHandle != (HANDLE)-1LL )
    {
      NtClose(DavRedirDeviceHandle);
      DavRedirDeviceHandle = (HANDLE)-1LL;
    }
    StringCbCopyW((STRSAFE_LPWSTR)v1, 0x78u, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\");
    StringCbCatW((STRSAFE_LPWSTR)v1, 0x78u, L"MRxDAV");
    RtlInitUnicodeString(&DestinationString, (PCWSTR)v1);
    LocalFree(v1);
    ThreadInformation = 0;
    v4 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v4 < 0 )
      RtlNtStatusToDosError(v4);
    return WsMapStatus(0);
  }
}

```

## disassembly

```asm
0x18000c628  mov     [rsp+arg_8], rbx
0x18000c62d  mov     [rsp+arg_10], rsi
0x18000c632  push    rdi
0x18000c633  sub     rsp, 30h
0x18000c637  mov     esi, 78h ; 'x'
0x18000c63c  xorps   xmm0, xmm0
0x18000c63f  mov     edx, esi; uBytes
0x18000c641  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x18000c646  lea     ecx, [rsi-38h]; uFlags
0x18000c649  call    cs:__imp_LocalAlloc
0x18000c64f  mov     rbx, rax
0x18000c652  test    rax, rax
0x18000c655  jnz     short loc_18000C65F
0x18000c657  lea     eax, [rsi-70h]
0x18000c65a  jmp     loc_18000C718
0x18000c65f  lea     rdx, [rsp+38h+ThreadInformation]
0x18000c664  mov     dword ptr [rsp+38h+ThreadInformation], 0Ah
0x18000c66c  call    NetpGetPrivilege
0x18000c671  mov     edi, eax
0x18000c673  test    eax, eax
0x18000c675  jz      short loc_18000C687
0x18000c677  mov     rcx, rbx; hMem
0x18000c67a  call    cs:__imp_LocalFree
0x18000c680  mov     eax, edi
0x18000c682  jmp     loc_18000C718
0x18000c687  mov     rcx, cs:DavRedirDeviceHandle; Handle
0x18000c68e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c692  jz      short loc_18000C6A5
0x18000c694  call    cs:__imp_NtClose
0x18000c69a  mov     cs:DavRedirDeviceHandle, 0FFFFFFFFFFFFFFFFh
0x18000c6a5  lea     r8, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000c6ac  mov     rdx, rsi; cbDest
0x18000c6af  mov     rcx, rbx; pszDest
0x18000c6b2  call    StringCbCopyW
0x18000c6b7  lea     r8, aMrxdav_0; "MRxDAV"
0x18000c6be  mov     rdx, rsi; cbDest
0x18000c6c1  mov     rcx, rbx; pszDest
0x18000c6c4  call    StringCbCatW
0x18000c6c9  mov     rdx, rbx; SourceString
0x18000c6cc  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x18000c6d1  call    cs:__imp_RtlInitUnicodeString
0x18000c6d7  mov     rcx, rbx; hMem
0x18000c6da  call    cs:__imp_LocalFree
0x18000c6e0  mov     r9d, 8; ThreadInformationLength
0x18000c6e6  mov     [rsp+38h+ThreadInformation], 0
0x18000c6ef  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x18000c6f4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000c6fb  lea     edx, [r9-3]; ThreadInformationClass
0x18000c6ff  call    cs:__imp_NtSetInformationThread
0x18000c705  test    eax, eax
0x18000c707  jns     short loc_18000C711
0x18000c709  mov     ecx, eax; Status
0x18000c70b  call    cs:__imp_RtlNtStatusToDosError
0x18000c711  xor     ecx, ecx
0x18000c713  call    WsMapStatus
0x18000c718  mov     rbx, [rsp+38h+arg_8]
0x18000c71d  mov     rsi, [rsp+38h+arg_10]
0x18000c722  add     rsp, 30h
0x18000c726  pop     rdi
0x18000c727  retn
```
