# AddPrintProvidorW

- ea: `0x1400647d0`
- end: `0x1400649b5`
- name: `AddPrintProvidorW`
- size: `485`
- prototype: `BOOL __stdcall(LPWSTR pName, DWORD Level, LPBYTE pProvidorInfo)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14003a864`

## callees

- `0x14000e700`
- `0x140015378`
- `0x14005c12c`
- `0x14005e898`
- `0x140063c38`
- `0x14006457c`
- `0x1400647d0`
- `0x1400797d8`
- `0x14007993c`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x14006497a`
- `ntdll!WinSqmAddToStreamEx` at `0x14006497a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064923`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064832`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400648fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400648fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064816`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400648d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064910`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064816`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400648d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064910`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140064882`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140064882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400648ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400648ed`

## string_xrefs

- `0x1400647fe`: `Trying to install print providor %ws when Windows Protected Print is enabled!`

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
0x1400647d0  mov     rax, rsp
0x1400647d3  mov     [rax+8], rbx
0x1400647d7  mov     [rax+10h], rsi
0x1400647db  push    rdi
0x1400647dc  sub     rsp, 60h
0x1400647e0  mov     rdi, r8
0x1400647e3  mov     qword ptr [rax+20h], 0
0x1400647eb  mov     esi, edx
0x1400647ed  call    WaitForSpoolerInitialization
0x1400647f2  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1400647f7  test    eax, eax
0x1400647f9  jz      short loc_140064829
0x1400647fb  mov     r8, [rdi]
0x1400647fe  lea     rdx, aTryingToInstal_5; "Trying to install print providor %ws wh"...
0x140064805  lea     rcx, aAddprintprovid; "AddPrintProvidorW"
0x14006480c  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140064811  mov     ecx, 32h ; '2'; dwErrCode
0x140064816  call    cs:__imp_SetLastError
0x14006481d  nop     dword ptr [rax+rax+00h]
0x140064822  xor     eax, eax
0x140064824  jmp     loc_1400649A4
0x140064829  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140064830  xor     ebx, ebx
0x140064832  call    cs:__imp_EnterCriticalSection
0x140064839  nop     dword ptr [rax+rax+00h]
0x14006483e  test    rdi, rdi
0x140064841  jnz     short loc_14006484B
0x140064843  lea     ecx, [rbx+57h]
0x140064846  jmp     loc_1400648D4
0x14006484b  mov     [rsp+68h+lpdwDisposition], rbx; lpdwDisposition
0x140064850  lea     rax, [rsp+68h+hKey]
0x140064858  mov     [rsp+68h+phkResult], rax; phkResult
0x14006485d  lea     rdx, szRegistryProvidors; "System\\CurrentControlSet\\Control\\Pri"...
0x140064864  mov     [rsp+68h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x140064869  xor     r9d, r9d; lpClass
0x14006486c  mov     [rsp+68h+samDesired], 3001Fh; samDesired
0x140064874  xor     r8d, r8d; Reserved
0x140064877  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006487e  mov     [rsp+68h+dwOptions], ebx; dwOptions
0x140064882  call    cs:__imp_RegCreateKeyExW
0x140064889  nop     dword ptr [rax+rax+00h]
0x14006488e  test    eax, eax
0x140064890  jnz     short loc_1400648D2
0x140064892  mov     eax, esi
0x140064894  sub     eax, 1
0x140064897  jz      short loc_1400648B9
0x140064899  cmp     eax, 1
0x14006489c  jz      short loc_1400648A5
0x14006489e  mov     ecx, 7Ch ; '|'
0x1400648a3  jmp     short loc_1400648D4
0x1400648a5  mov     rdx, [rdi]; unsigned __int16 *
0x1400648a8  mov     rcx, [rsp+68h+hKey]; HKEY
0x1400648b0  call    ?UpdateProvidorOrder@@YAHPEAUHKEY__@@PEAG@Z; UpdateProvidorOrder(HKEY__ *,ushort *)
0x1400648b5  mov     ebx, eax
0x1400648b7  jmp     short loc_1400648E0
0x1400648b9  mov     rcx, [rsp+68h+hKey]; hKey
0x1400648c1  mov     rdx, rdi; struct _PROVIDOR_INFO_1W *
0x1400648c4  call    ?AddNewProvidor@@YAKPEAUHKEY__@@PEAU_PROVIDOR_INFO_1W@@@Z; AddNewProvidor(HKEY__ *,_PROVIDOR_INFO_1W *)
0x1400648c9  test    eax, eax
0x1400648cb  jnz     short loc_1400648D2
0x1400648cd  lea     ebx, [rax+1]
0x1400648d0  jmp     short loc_1400648E0
0x1400648d2  mov     ecx, eax; dwErrCode
0x1400648d4  call    cs:__imp_SetLastError
0x1400648db  nop     dword ptr [rax+rax+00h]
0x1400648e0  mov     rcx, [rsp+68h+hKey]; hKey
0x1400648e8  test    rcx, rcx
0x1400648eb  jz      short loc_1400648F9
0x1400648ed  call    cs:__imp_RegCloseKey
0x1400648f4  nop     dword ptr [rax+rax+00h]
0x1400648f9  test    ebx, ebx
0x1400648fb  jnz     short loc_14006491C
0x1400648fd  call    cs:__imp_GetLastError
0x140064904  nop     dword ptr [rax+rax+00h]
0x140064909  test    eax, eax
0x14006490b  jnz     short loc_14006491C
0x14006490d  lea     ecx, [rbx+8]; dwErrCode
0x140064910  call    cs:__imp_SetLastError
0x140064917  nop     dword ptr [rax+rax+00h]
0x14006491c  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140064923  call    cs:__imp_LeaveCriticalSection
0x14006492a  nop     dword ptr [rax+rax+00h]
0x14006492f  test    ebx, ebx
0x140064931  jz      short loc_1400649A2
0x140064933  cmp     esi, 1
0x140064936  jnz     short loc_1400649A2
0x140064938  mov     rdi, [rdi]
0x14006493b  xorps   xmm0, xmm0
0x14006493e  movups  [rsp+68h+var_18], xmm0
0x140064943  call    ?SplSqmIsOptedIn@@YAHXZ; SplSqmIsOptedIn(void)
0x140064948  test    eax, eax
0x14006494a  jnz     short loc_140064955
0x14006494c  lea     rdx, aSqmDataPointUD_0; "SQM data-point %u disabled, stream entr"...
0x140064953  jmp     short loc_14006498D
0x140064955  mov     rdx, rdi; unsigned __int16 *
0x140064958  lea     rcx, [rsp+68h+var_18]; struct _SQM_STREAM_ENTRY_EX *
0x14006495d  call    ?WinSqmCreateStringStreamEntryEx@@YAXPEAU_SQM_STREAM_ENTRY_EX@@PEBG@Z; WinSqmCreateStringStreamEntryEx(_SQM_STREAM_ENTRY_EX *,ushort const *)
0x140064962  xor     ecx, ecx
0x140064964  mov     [rsp+68h+dwOptions], 0
0x14006496c  lea     r9, [rsp+68h+var_18]
0x140064971  mov     edx, 1A77h
0x140064976  lea     r8d, [rcx+1]
0x14006497a  call    cs:__imp_WinSqmAddToStreamEx
0x140064981  nop     dword ptr [rax+rax+00h]
0x140064986  lea     rdx, aSqmDataPointUC; "SQM data-point %u, collected stream ent"...
0x14006498d  mov     r9, rdi
0x140064990  lea     rcx, aSplsqmaddtostr; "SplSqmAddToStream"
0x140064997  mov     r8d, 1A77h
0x14006499d  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400649a2  mov     eax, ebx
0x1400649a4  mov     rbx, [rsp+68h+arg_0]
0x1400649a9  mov     rsi, [rsp+68h+arg_8]
0x1400649ae  add     rsp, 60h
0x1400649b2  pop     rdi
0x1400649b3  retn
```
