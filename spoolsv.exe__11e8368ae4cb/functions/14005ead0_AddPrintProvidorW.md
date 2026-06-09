# AddPrintProvidorW

- ea: `0x14005ead0`
- end: `0x14005ec7e`
- name: `AddPrintProvidorW`
- size: `430`
- prototype: `BOOL __stdcall(LPWSTR pName, DWORD Level, LPBYTE pProvidorInfo)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140037848`

## callees

- `0x14000d520`
- `0x1400140cc`
- `0x140056c24`
- `0x1400590f0`
- `0x14005dfe4`
- `0x14005e8ac`
- `0x14005ead0`
- `0x140072764`
- `0x1400728a4`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x14005ec4a`
- `ntdll!WinSqmAddToStreamEx` at `0x14005ec4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005ebf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005ebf9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005eb2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005eb2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ebdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ebdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005eb16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ebc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ebec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005eb16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ebc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ebec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005eb76`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005eb76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005ebd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005ebd5`

## string_xrefs

- `0x14005eafe`: `Trying to install print providor %ws when Windows Protected Print is enabled!`

## pseudocode

```c
BOOL __stdcall AddPrintProvidorW(LPWSTR pName, DWORD Level, LPBYTE pProvidorInfo)
{
  int updated; // ebx
  DWORD v7; // ecx
  DWORD v8; // eax
  const unsigned __int16 *v9; // rdi
  __int128 v10; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  WaitForSpoolerInitialization();
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "AddPrintProvidorW",
      L"Trying to install print providor %ws when Windows Protected Print is enabled!",
      *(_QWORD *)pProvidorInfo);
    SetLastError(0x32u);
    return 0;
  }
  updated = 0;
  EnterCriticalSection(&RouterNotifySection);
  if ( !pProvidorInfo )
  {
    v7 = 87;
LABEL_13:
    SetLastError(v7);
    goto LABEL_14;
  }
  v8 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Print\\Providers",
         0,
         0,
         0,
         0x3001Fu,
         0,
         &hKey,
         0);
  if ( v8 )
    goto LABEL_12;
  if ( Level == 1 )
  {
    v8 = AddNewProvidor(hKey, (struct _PROVIDOR_INFO_1W *)pProvidorInfo);
    if ( !v8 )
    {
      updated = 1;
      goto LABEL_14;
    }
LABEL_12:
    v7 = v8;
    goto LABEL_13;
  }
  if ( Level != 2 )
  {
    v7 = 124;
    goto LABEL_13;
  }
  updated = UpdateProvidorOrder(hKey, *(unsigned __int16 **)pProvidorInfo);
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  if ( !updated && !GetLastError() )
    SetLastError(8u);
  LeaveCriticalSection(&RouterNotifySection);
  if ( updated && Level == 1 )
  {
    v9 = *(const unsigned __int16 **)pProvidorInfo;
    v10 = 0;
    if ( (unsigned int)SplSqmIsOptedIn() )
    {
      WinSqmCreateStringStreamEntryEx((struct _SQM_STREAM_ENTRY_EX *)&v10, v9);
      WinSqmAddToStreamEx(0, 6775, 1, &v10, 0);
      PerfLibTelemetry::WriteDbgTraceInfo(
        "SplSqmAddToStream",
        L"SQM data-point %u, collected stream entry {%ws}",
        6775,
        v9);
    }
    else
    {
      PerfLibTelemetry::WriteDbgTraceInfo(
        "SplSqmAddToStream",
        L"SQM data-point %u disabled, stream entry {%ws} not collected, out of session",
        6775,
        v9);
    }
  }
  return updated;
}

```

## disassembly

```asm
0x14005ead0  mov     rax, rsp
0x14005ead3  mov     [rax+8], rbx
0x14005ead7  mov     [rax+10h], rsi
0x14005eadb  push    rdi
0x14005eadc  sub     rsp, 60h
0x14005eae0  mov     rdi, r8
0x14005eae3  mov     qword ptr [rax+20h], 0
0x14005eaeb  mov     esi, edx
0x14005eaed  call    WaitForSpoolerInitialization
0x14005eaf2  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14005eaf7  test    eax, eax
0x14005eaf9  jz      short loc_14005EB23
0x14005eafb  mov     r8, [rdi]
0x14005eafe  lea     rdx, aTryingToInstal_5; "Trying to install print providor %ws wh"...
0x14005eb05  lea     rcx, aAddprintprovid; "AddPrintProvidorW"
0x14005eb0c  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14005eb11  mov     ecx, 32h ; '2'; dwErrCode
0x14005eb16  call    cs:__imp_SetLastError
0x14005eb1c  xor     eax, eax
0x14005eb1e  jmp     loc_14005EC6E
0x14005eb23  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005eb2a  xor     ebx, ebx
0x14005eb2c  call    cs:__imp_EnterCriticalSection
0x14005eb32  test    rdi, rdi
0x14005eb35  jnz     short loc_14005EB3F
0x14005eb37  lea     ecx, [rbx+57h]
0x14005eb3a  jmp     loc_14005EBC2
0x14005eb3f  mov     [rsp+68h+lpdwDisposition], rbx; lpdwDisposition
0x14005eb44  lea     rax, [rsp+68h+hKey]
0x14005eb4c  mov     [rsp+68h+phkResult], rax; phkResult
0x14005eb51  lea     rdx, szRegistryProvidors; "System\\CurrentControlSet\\Control\\Pri"...
0x14005eb58  mov     [rsp+68h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x14005eb5d  xor     r9d, r9d; lpClass
0x14005eb60  mov     [rsp+68h+samDesired], 3001Fh; samDesired
0x14005eb68  xor     r8d, r8d; Reserved
0x14005eb6b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005eb72  mov     [rsp+68h+dwOptions], ebx; dwOptions
0x14005eb76  call    cs:__imp_RegCreateKeyExW
0x14005eb7c  test    eax, eax
0x14005eb7e  jnz     short loc_14005EBC0
0x14005eb80  mov     eax, esi
0x14005eb82  sub     eax, 1
0x14005eb85  jz      short loc_14005EBA7
0x14005eb87  cmp     eax, 1
0x14005eb8a  jz      short loc_14005EB93
0x14005eb8c  mov     ecx, 7Ch ; '|'
0x14005eb91  jmp     short loc_14005EBC2
0x14005eb93  mov     rdx, [rdi]; unsigned __int16 *
0x14005eb96  mov     rcx, [rsp+68h+hKey]; HKEY
0x14005eb9e  call    ?UpdateProvidorOrder@@YAHPEAUHKEY__@@PEAG@Z; UpdateProvidorOrder(HKEY__ *,ushort *)
0x14005eba3  mov     ebx, eax
0x14005eba5  jmp     short loc_14005EBC8
0x14005eba7  mov     rcx, [rsp+68h+hKey]; hKey
0x14005ebaf  mov     rdx, rdi; struct _PROVIDOR_INFO_1W *
0x14005ebb2  call    ?AddNewProvidor@@YAKPEAUHKEY__@@PEAU_PROVIDOR_INFO_1W@@@Z; AddNewProvidor(HKEY__ *,_PROVIDOR_INFO_1W *)
0x14005ebb7  test    eax, eax
0x14005ebb9  jnz     short loc_14005EBC0
0x14005ebbb  lea     ebx, [rax+1]
0x14005ebbe  jmp     short loc_14005EBC8
0x14005ebc0  mov     ecx, eax; dwErrCode
0x14005ebc2  call    cs:__imp_SetLastError
0x14005ebc8  mov     rcx, [rsp+68h+hKey]; hKey
0x14005ebd0  test    rcx, rcx
0x14005ebd3  jz      short loc_14005EBDB
0x14005ebd5  call    cs:__imp_RegCloseKey
0x14005ebdb  test    ebx, ebx
0x14005ebdd  jnz     short loc_14005EBF2
0x14005ebdf  call    cs:__imp_GetLastError
0x14005ebe5  test    eax, eax
0x14005ebe7  jnz     short loc_14005EBF2
0x14005ebe9  lea     ecx, [rbx+8]; dwErrCode
0x14005ebec  call    cs:__imp_SetLastError
0x14005ebf2  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005ebf9  call    cs:__imp_LeaveCriticalSection
0x14005ebff  test    ebx, ebx
0x14005ec01  jz      short loc_14005EC6C
0x14005ec03  cmp     esi, 1
0x14005ec06  jnz     short loc_14005EC6C
0x14005ec08  mov     rdi, [rdi]
0x14005ec0b  xorps   xmm0, xmm0
0x14005ec0e  movups  [rsp+68h+var_18], xmm0
0x14005ec13  call    ?SplSqmIsOptedIn@@YAHXZ; SplSqmIsOptedIn(void)
0x14005ec18  test    eax, eax
0x14005ec1a  jnz     short loc_14005EC25
0x14005ec1c  lea     rdx, aSqmDataPointUD_0; "SQM data-point %u disabled, stream entr"...
0x14005ec23  jmp     short loc_14005EC57
0x14005ec25  mov     rdx, rdi; unsigned __int16 *
0x14005ec28  lea     rcx, [rsp+68h+var_18]; struct _SQM_STREAM_ENTRY_EX *
0x14005ec2d  call    ?WinSqmCreateStringStreamEntryEx@@YAXPEAU_SQM_STREAM_ENTRY_EX@@PEBG@Z; WinSqmCreateStringStreamEntryEx(_SQM_STREAM_ENTRY_EX *,ushort const *)
0x14005ec32  xor     ecx, ecx
0x14005ec34  mov     [rsp+68h+dwOptions], 0
0x14005ec3c  lea     r9, [rsp+68h+var_18]
0x14005ec41  mov     edx, 1A77h
0x14005ec46  lea     r8d, [rcx+1]
0x14005ec4a  call    cs:__imp_WinSqmAddToStreamEx
0x14005ec50  lea     rdx, aSqmDataPointUC; "SQM data-point %u, collected stream ent"...
0x14005ec57  mov     r9, rdi
0x14005ec5a  lea     rcx, aSplsqmaddtostr; "SplSqmAddToStream"
0x14005ec61  mov     r8d, 1A77h
0x14005ec67  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14005ec6c  mov     eax, ebx
0x14005ec6e  mov     rbx, [rsp+68h+arg_0]
0x14005ec73  mov     rsi, [rsp+68h+arg_8]
0x14005ec78  add     rsp, 60h
0x14005ec7c  pop     rdi
0x14005ec7d  retn
```
