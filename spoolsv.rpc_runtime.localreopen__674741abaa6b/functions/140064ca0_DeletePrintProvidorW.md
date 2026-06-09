# DeletePrintProvidorW

- ea: `0x140064ca0`
- end: `0x140064f8d`
- name: `DeletePrintProvidorW`
- size: `749`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProvidorName)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x14003b7c0`

## callees

- `0x140004790`
- `0x14000e700`
- `0x140015378`
- `0x14005e898`
- `0x140063fe0`
- `0x140064ca0`
- `0x14006914c`
- `0x140069434`
- `0x140069bf0`
- `0x140069cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140064e76`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140064e76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064f65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064f65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064d18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064d18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064f20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064f3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064f20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140064f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064ef0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064cf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064ee1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064f03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064cf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064ee1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064f03`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140064d6b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140064d6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140064dc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140064e07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140064dc0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140064e07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140064e55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140064e55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140064f52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140064f52`

## string_xrefs

- `0x140064ce7`: `DeletePrintProvidorW`
- `0x140064ce0`: `Trying to delete print providor %ws when Windows Protected Print is enabled!`
- `0x140064e6c`: `LanMan Print Services`

## pseudocode

```c
BOOL __stdcall DeletePrintProvidorW(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProvidorName)
{
  BYTE *v5; // rdi
  BYTE *v6; // r14
  LSTATUS v7; // eax
  DWORD v8; // ecx
  struct _PROVIDOR *Providor; // r15
  const BYTE *v10; // rax
  int v11; // esi
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // r8
  struct _PROVIDOR *i; // rcx
  BOOL v17; // ebx
  DWORD v18; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+48h] BYREF

  cbData = 0;
  v18 = 0;
  hKey = 0;
  v19 = 0;
  WaitForSpoolerInitialization(pName, pEnvironment);
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "DeletePrintProvidorW",
      L"Trying to delete print providor %ws when Windows Protected Print is enabled!",
      pPrintProvidorName);
    SetLastError(0x32u);
    return 0;
  }
  v5 = 0;
  v6 = 0;
  EnterCriticalSection(&RouterNotifySection);
  if ( !pPrintProvidorName || !*pPrintProvidorName )
  {
    v8 = 87;
    goto LABEL_25;
  }
  v7 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Print\\Providers",
         0,
         0,
         0,
         0x3001Fu,
         0,
         &hKey,
         0);
  if ( v7 )
    goto LABEL_6;
  Providor = FindProvidor(hKey, pPrintProvidorName);
  if ( !Providor )
    goto LABEL_26;
  cbData = 0;
  v7 = RegQueryValueExW(hKey, L"Order", 0, 0, 0, &cbData);
  if ( v7 )
    goto LABEL_6;
  if ( !cbData || (v5 = (BYTE *)DllAllocSplMem(cbData)) == 0 )
  {
LABEL_26:
    v17 = 0;
    if ( !GetLastError() )
      SetLastError(8u);
    if ( !v5 )
      goto LABEL_30;
    goto LABEL_29;
  }
  v7 = RegQueryValueExW(hKey, L"Order", 0, 0, v5, &cbData);
  if ( v7 )
    goto LABEL_6;
  v10 = (const BYTE *)RemoveOrderEntry((unsigned __int16 *)v5, cbData, pPrintProvidorName, &v18);
  v6 = (BYTE *)v10;
  if ( !v10 )
    goto LABEL_26;
  v7 = RegSetValueExW(hKey, L"Order", 0, 7u, v10, v18);
  if ( v7 )
  {
LABEL_6:
    v8 = v7;
LABEL_25:
    SetLastError(v8);
    goto LABEL_26;
  }
  v11 = 0;
  if ( !(unsigned int)_o__wcsicmp(L"LanMan Print Services", pPrintProvidorName) )
    LOBYTE(v11) = GetAPDPolicy(hKey, v12, v13, &v19) == 0;
  DeleteSubKeyTree(hKey, pPrintProvidorName);
  if ( v11 )
    SetAPDPolicy(hKey, v14, v15, v19);
  for ( i = pLocalProvidor; *(_QWORD *)i; i = *(struct _PROVIDOR **)i )
  {
    if ( *(struct _PROVIDOR **)i == Providor )
    {
      *(_QWORD *)i = *(_QWORD *)Providor;
      break;
    }
  }
  v17 = 1;
LABEL_29:
  HeapFree(g_hSpoolssHeap, 0, v5);
LABEL_30:
  if ( v6 )
    HeapFree(g_hSpoolssHeap, 0, v6);
  if ( hKey )
    RegCloseKey(hKey);
  LeaveCriticalSection(&RouterNotifySection);
  return v17;
}

```

## disassembly

```asm
0x140064ca0  mov     [rsp-28h+arg_0], rbx
0x140064ca5  mov     [rsp-28h+arg_8], rsi
0x140064caa  push    rbp
0x140064cab  push    rdi
0x140064cac  push    r12
0x140064cae  push    r14
0x140064cb0  push    r15
0x140064cb2  mov     rbp, rsp
0x140064cb5  sub     rsp, 60h
0x140064cb9  xor     r12d, r12d
0x140064cbc  mov     rbx, r8
0x140064cbf  mov     [rbp+cbData], r12d
0x140064cc3  mov     [rbp+var_10], r12d
0x140064cc7  mov     [rbp+hKey], r12
0x140064ccb  mov     [rbp+var_C], r12d
0x140064ccf  call    WaitForSpoolerInitialization
0x140064cd4  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140064cd9  test    eax, eax
0x140064cdb  jz      short loc_140064D0B
0x140064cdd  mov     r8, rbx
0x140064ce0  lea     rdx, aTryingToDelete_1; "Trying to delete print providor %ws whe"...
0x140064ce7  lea     rcx, aDeleteprintpro; "DeletePrintProvidorW"
0x140064cee  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140064cf3  lea     ecx, [r12+32h]; dwErrCode
0x140064cf8  call    cs:__imp_SetLastError
0x140064cff  nop     dword ptr [rax+rax+00h]
0x140064d04  xor     eax, eax
0x140064d06  jmp     loc_140064F73
0x140064d0b  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140064d12  mov     rdi, r12
0x140064d15  mov     r14, r12
0x140064d18  call    cs:__imp_EnterCriticalSection
0x140064d1f  nop     dword ptr [rax+rax+00h]
0x140064d24  test    rbx, rbx
0x140064d27  jz      loc_140064EDC
0x140064d2d  cmp     [rbx], r12w
0x140064d31  jz      loc_140064EDC
0x140064d37  mov     [rsp+60h+lpdwDisposition], r12; lpdwDisposition
0x140064d3c  lea     rax, [rbp+hKey]
0x140064d40  mov     [rsp+60h+phkResult], rax; phkResult
0x140064d45  lea     rdx, szRegistryProvidors; "System\\CurrentControlSet\\Control\\Pri"...
0x140064d4c  mov     [rsp+60h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140064d51  xor     r9d, r9d; lpClass
0x140064d54  mov     [rsp+60h+samDesired], 3001Fh; samDesired
0x140064d5c  xor     r8d, r8d; Reserved
0x140064d5f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140064d66  mov     [rsp+60h+dwOptions], r12d; dwOptions
0x140064d6b  call    cs:__imp_RegCreateKeyExW
0x140064d72  nop     dword ptr [rax+rax+00h]
0x140064d77  test    eax, eax
0x140064d79  jz      short loc_140064D82
0x140064d7b  mov     ecx, eax
0x140064d7d  jmp     loc_140064EE1
0x140064d82  mov     rcx, [rbp+hKey]; HKEY
0x140064d86  mov     rdx, rbx; unsigned __int16 *
0x140064d89  call    ?FindProvidor@@YAPEAU_PROVIDOR@@PEAUHKEY__@@PEAG@Z; FindProvidor(HKEY__ *,ushort *)
0x140064d8e  mov     r15, rax
0x140064d91  test    rax, rax
0x140064d94  jz      loc_140064EED
0x140064d9a  mov     rcx, [rbp+hKey]; hKey
0x140064d9e  lea     rax, [rbp+cbData]
0x140064da2  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x140064da7  lea     rsi, szOrder; "Order"
0x140064dae  mov     rdx, rsi; lpValueName
0x140064db1  mov     qword ptr [rsp+60h+dwOptions], r12; lpData
0x140064db6  xor     r9d, r9d; lpType
0x140064db9  mov     [rbp+cbData], r12d
0x140064dbd  xor     r8d, r8d; lpReserved
0x140064dc0  call    cs:__imp_RegQueryValueExW
0x140064dc7  nop     dword ptr [rax+rax+00h]
0x140064dcc  test    eax, eax
0x140064dce  jnz     short loc_140064D7B
0x140064dd0  mov     ecx, [rbp+cbData]; dwBytes
0x140064dd3  test    ecx, ecx
0x140064dd5  jz      loc_140064EED
0x140064ddb  call    DllAllocSplMem
0x140064de0  mov     rdi, rax
0x140064de3  test    rax, rax
0x140064de6  jz      loc_140064EED
0x140064dec  mov     rcx, [rbp+hKey]; hKey
0x140064df0  lea     rax, [rbp+cbData]
0x140064df4  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x140064df9  xor     r9d, r9d; lpType
0x140064dfc  xor     r8d, r8d; lpReserved
0x140064dff  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x140064e04  mov     rdx, rsi; lpValueName
0x140064e07  call    cs:__imp_RegQueryValueExW
0x140064e0e  nop     dword ptr [rax+rax+00h]
0x140064e13  test    eax, eax
0x140064e15  jnz     loc_140064D7B
0x140064e1b  mov     edx, [rbp+cbData]; dwBytes
0x140064e1e  lea     r9, [rbp+var_10]; unsigned int *
0x140064e22  mov     r8, rbx; lpString2
0x140064e25  mov     rcx, rdi; unsigned __int16 *
0x140064e28  call    ?RemoveOrderEntry@@YAPEAGPEAGK0PEAK@Z; RemoveOrderEntry(ushort *,ulong,ushort *,ulong *)
0x140064e2d  mov     r14, rax
0x140064e30  test    rax, rax
0x140064e33  jz      loc_140064EED
0x140064e39  mov     ecx, [rbp+var_10]
0x140064e3c  mov     r9d, 7; dwType
0x140064e42  mov     [rsp+60h+samDesired], ecx; cbData
0x140064e46  xor     r8d, r8d; Reserved
0x140064e49  mov     rcx, [rbp+hKey]; hKey
0x140064e4d  mov     rdx, rsi; lpValueName
0x140064e50  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x140064e55  call    cs:__imp_RegSetValueExW
0x140064e5c  nop     dword ptr [rax+rax+00h]
0x140064e61  test    eax, eax
0x140064e63  jnz     loc_140064D7B
0x140064e69  mov     rdx, rbx
0x140064e6c  lea     rcx, szLanManProvider; "LanMan Print Services"
0x140064e73  mov     esi, r12d
0x140064e76  call    cs:__imp__o__wcsicmp
0x140064e7d  nop     dword ptr [rax+rax+00h]
0x140064e82  test    eax, eax
0x140064e84  jnz     short loc_140064E99
0x140064e86  mov     rcx, [rbp+hKey]; HKEY
0x140064e8a  lea     r9, [rbp+var_C]; unsigned int *
0x140064e8e  call    ?GetAPDPolicy@@YAKPEAUHKEY__@@PEBG1PEAK@Z; GetAPDPolicy(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140064e93  test    eax, eax
0x140064e95  setz    sil
0x140064e99  mov     rcx, [rbp+hKey]; hKey
0x140064e9d  mov     rdx, rbx; lpSubKey
0x140064ea0  call    ?DeleteSubKeyTree@@YAHPEAUHKEY__@@PEAG@Z; DeleteSubKeyTree(HKEY__ *,ushort *)
0x140064ea5  test    esi, esi
0x140064ea7  jz      short loc_140064EB6
0x140064ea9  mov     r9d, [rbp+var_C]; unsigned int
0x140064ead  mov     rcx, [rbp+hKey]; HKEY
0x140064eb1  call    ?SetAPDPolicy@@YAKPEAUHKEY__@@PEBG1K@Z; SetAPDPolicy(HKEY__ *,ushort const *,ushort const *,ulong)
0x140064eb6  mov     rcx, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x140064ebd  mov     rax, [rcx]
0x140064ec0  test    rax, rax
0x140064ec3  jz      short loc_140064ED5
0x140064ec5  cmp     rax, r15
0x140064ec8  jz      short loc_140064ECF
0x140064eca  mov     rcx, rax
0x140064ecd  jmp     short loc_140064EBD
0x140064ecf  mov     rax, [r15]
0x140064ed2  mov     [rcx], rax
0x140064ed5  mov     ebx, 1
0x140064eda  jmp     short loc_140064F14
0x140064edc  mov     ecx, 57h ; 'W'; dwErrCode
0x140064ee1  call    cs:__imp_SetLastError
0x140064ee8  nop     dword ptr [rax+rax+00h]
0x140064eed  mov     ebx, r12d
0x140064ef0  call    cs:__imp_GetLastError
0x140064ef7  nop     dword ptr [rax+rax+00h]
0x140064efc  test    eax, eax
0x140064efe  jnz     short loc_140064F0F
0x140064f00  lea     ecx, [rax+8]; dwErrCode
0x140064f03  call    cs:__imp_SetLastError
0x140064f0a  nop     dword ptr [rax+rax+00h]
0x140064f0f  test    rdi, rdi
0x140064f12  jz      short loc_140064F2C
0x140064f14  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140064f1b  mov     r8, rdi; lpMem
0x140064f1e  xor     edx, edx; dwFlags
0x140064f20  call    cs:__imp_HeapFree
0x140064f27  nop     dword ptr [rax+rax+00h]
0x140064f2c  test    r14, r14
0x140064f2f  jz      short loc_140064F49
0x140064f31  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140064f38  mov     r8, r14; lpMem
0x140064f3b  xor     edx, edx; dwFlags
0x140064f3d  call    cs:__imp_HeapFree
0x140064f44  nop     dword ptr [rax+rax+00h]
0x140064f49  mov     rcx, [rbp+hKey]; hKey
0x140064f4d  test    rcx, rcx
0x140064f50  jz      short loc_140064F5E
0x140064f52  call    cs:__imp_RegCloseKey
0x140064f59  nop     dword ptr [rax+rax+00h]
0x140064f5e  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140064f65  call    cs:__imp_LeaveCriticalSection
0x140064f6c  nop     dword ptr [rax+rax+00h]
0x140064f71  mov     eax, ebx
0x140064f73  lea     r11, [rsp+60h+var_s0]
0x140064f78  mov     rbx, [r11+30h]
0x140064f7c  mov     rsi, [r11+38h]
0x140064f80  mov     rsp, r11
0x140064f83  pop     r15
0x140064f85  pop     r14
0x140064f87  pop     r12
0x140064f89  pop     rdi
0x140064f8a  pop     rbp
0x140064f8b  retn
```
