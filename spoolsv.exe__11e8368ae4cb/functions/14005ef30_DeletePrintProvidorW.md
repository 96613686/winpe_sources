# DeletePrintProvidorW

- ea: `0x14005ef30`
- end: `0x14005f1c8`
- name: `DeletePrintProvidorW`
- size: `664`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProvidorName)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x140032fc0`

## callees

- `0x1400041c0`
- `0x14000d520`
- `0x1400140cc`
- `0x1400590f0`
- `0x14005e334`
- `0x14005ef30`
- `0x140063090`
- `0x140063334`
- `0x140063a38`
- `0x140063afc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005f0e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005f0e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005f1a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14005f1a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005efa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14005efa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005f174`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005f18b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005f174`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005f18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005f150`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ef88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005f147`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005f15d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ef88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005f147`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005f15d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005efef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14005efef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005f03e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005f07f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005f03e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005f07f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005f0c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14005f0c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005f19a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005f19a`

## string_xrefs

- `0x14005ef70`: `Trying to delete print providor %ws when Windows Protected Print is enabled!`
- `0x14005ef77`: `DeletePrintProvidorW`
- `0x14005f0d8`: `LanMan Print Services`

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
0x14005ef30  mov     [rsp-28h+arg_0], rbx
0x14005ef35  mov     [rsp-28h+arg_8], rsi
0x14005ef3a  push    rbp
0x14005ef3b  push    rdi
0x14005ef3c  push    r12
0x14005ef3e  push    r14
0x14005ef40  push    r15
0x14005ef42  mov     rbp, rsp
0x14005ef45  sub     rsp, 60h
0x14005ef49  xor     r12d, r12d
0x14005ef4c  mov     rbx, r8
0x14005ef4f  mov     [rbp+cbData], r12d
0x14005ef53  mov     [rbp+var_10], r12d
0x14005ef57  mov     [rbp+hKey], r12
0x14005ef5b  mov     [rbp+var_C], r12d
0x14005ef5f  call    WaitForSpoolerInitialization
0x14005ef64  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14005ef69  test    eax, eax
0x14005ef6b  jz      short loc_14005EF95
0x14005ef6d  mov     r8, rbx
0x14005ef70  lea     rdx, aTryingToDelete_1; "Trying to delete print providor %ws whe"...
0x14005ef77  lea     rcx, aDeleteprintpro; "DeletePrintProvidorW"
0x14005ef7e  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14005ef83  lea     ecx, [r12+32h]; dwErrCode
0x14005ef88  call    cs:__imp_SetLastError
0x14005ef8e  xor     eax, eax
0x14005ef90  jmp     loc_14005F1AF
0x14005ef95  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005ef9c  mov     rdi, r12
0x14005ef9f  mov     r14, r12
0x14005efa2  call    cs:__imp_EnterCriticalSection
0x14005efa8  test    rbx, rbx
0x14005efab  jz      loc_14005F142
0x14005efb1  cmp     [rbx], r12w
0x14005efb5  jz      loc_14005F142
0x14005efbb  mov     [rsp+60h+lpdwDisposition], r12; lpdwDisposition
0x14005efc0  lea     rax, [rbp+hKey]
0x14005efc4  mov     [rsp+60h+phkResult], rax; phkResult
0x14005efc9  lea     rdx, szRegistryProvidors; "System\\CurrentControlSet\\Control\\Pri"...
0x14005efd0  mov     [rsp+60h+lpSecurityAttributes], r12; lpSecurityAttributes
0x14005efd5  xor     r9d, r9d; lpClass
0x14005efd8  mov     [rsp+60h+samDesired], 3001Fh; samDesired
0x14005efe0  xor     r8d, r8d; Reserved
0x14005efe3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005efea  mov     [rsp+60h+dwOptions], r12d; dwOptions
0x14005efef  call    cs:__imp_RegCreateKeyExW
0x14005eff5  test    eax, eax
0x14005eff7  jz      short loc_14005F000
0x14005eff9  mov     ecx, eax
0x14005effb  jmp     loc_14005F147
0x14005f000  mov     rcx, [rbp+hKey]; HKEY
0x14005f004  mov     rdx, rbx; unsigned __int16 *
0x14005f007  call    ?FindProvidor@@YAPEAU_PROVIDOR@@PEAUHKEY__@@PEAG@Z; FindProvidor(HKEY__ *,ushort *)
0x14005f00c  mov     r15, rax
0x14005f00f  test    rax, rax
0x14005f012  jz      loc_14005F14D
0x14005f018  mov     rcx, [rbp+hKey]; hKey
0x14005f01c  lea     rax, [rbp+cbData]
0x14005f020  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x14005f025  lea     rsi, szOrder; "Order"
0x14005f02c  mov     rdx, rsi; lpValueName
0x14005f02f  mov     qword ptr [rsp+60h+dwOptions], r12; lpData
0x14005f034  xor     r9d, r9d; lpType
0x14005f037  mov     [rbp+cbData], r12d
0x14005f03b  xor     r8d, r8d; lpReserved
0x14005f03e  call    cs:__imp_RegQueryValueExW
0x14005f044  test    eax, eax
0x14005f046  jnz     short loc_14005EFF9
0x14005f048  mov     ecx, [rbp+cbData]; dwBytes
0x14005f04b  test    ecx, ecx
0x14005f04d  jz      loc_14005F14D
0x14005f053  call    DllAllocSplMem
0x14005f058  mov     rdi, rax
0x14005f05b  test    rax, rax
0x14005f05e  jz      loc_14005F14D
0x14005f064  mov     rcx, [rbp+hKey]; hKey
0x14005f068  lea     rax, [rbp+cbData]
0x14005f06c  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x14005f071  xor     r9d, r9d; lpType
0x14005f074  xor     r8d, r8d; lpReserved
0x14005f077  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x14005f07c  mov     rdx, rsi; lpValueName
0x14005f07f  call    cs:__imp_RegQueryValueExW
0x14005f085  test    eax, eax
0x14005f087  jnz     loc_14005EFF9
0x14005f08d  mov     edx, [rbp+cbData]; dwBytes
0x14005f090  lea     r9, [rbp+var_10]; unsigned int *
0x14005f094  mov     r8, rbx; lpString2
0x14005f097  mov     rcx, rdi; unsigned __int16 *
0x14005f09a  call    ?RemoveOrderEntry@@YAPEAGPEAGK0PEAK@Z; RemoveOrderEntry(ushort *,ulong,ushort *,ulong *)
0x14005f09f  mov     r14, rax
0x14005f0a2  test    rax, rax
0x14005f0a5  jz      loc_14005F14D
0x14005f0ab  mov     ecx, [rbp+var_10]
0x14005f0ae  mov     r9d, 7; dwType
0x14005f0b4  mov     [rsp+60h+samDesired], ecx; cbData
0x14005f0b8  xor     r8d, r8d; Reserved
0x14005f0bb  mov     rcx, [rbp+hKey]; hKey
0x14005f0bf  mov     rdx, rsi; lpValueName
0x14005f0c2  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x14005f0c7  call    cs:__imp_RegSetValueExW
0x14005f0cd  test    eax, eax
0x14005f0cf  jnz     loc_14005EFF9
0x14005f0d5  mov     rdx, rbx
0x14005f0d8  lea     rcx, szLanManProvider; "LanMan Print Services"
0x14005f0df  mov     esi, r12d
0x14005f0e2  call    cs:__imp__o__wcsicmp
0x14005f0e8  test    eax, eax
0x14005f0ea  jnz     short loc_14005F0FF
0x14005f0ec  mov     rcx, [rbp+hKey]; HKEY
0x14005f0f0  lea     r9, [rbp+var_C]; unsigned int *
0x14005f0f4  call    ?GetAPDPolicy@@YAKPEAUHKEY__@@PEBG1PEAK@Z; GetAPDPolicy(HKEY__ *,ushort const *,ushort const *,ulong *)
0x14005f0f9  test    eax, eax
0x14005f0fb  setz    sil
0x14005f0ff  mov     rcx, [rbp+hKey]; hKey
0x14005f103  mov     rdx, rbx; lpSubKey
0x14005f106  call    ?DeleteSubKeyTree@@YAHPEAUHKEY__@@PEAG@Z; DeleteSubKeyTree(HKEY__ *,ushort *)
0x14005f10b  test    esi, esi
0x14005f10d  jz      short loc_14005F11C
0x14005f10f  mov     r9d, [rbp+var_C]; unsigned int
0x14005f113  mov     rcx, [rbp+hKey]; HKEY
0x14005f117  call    ?SetAPDPolicy@@YAKPEAUHKEY__@@PEBG1K@Z; SetAPDPolicy(HKEY__ *,ushort const *,ushort const *,ulong)
0x14005f11c  mov     rcx, cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA; _PROVIDOR * pLocalProvidor
0x14005f123  mov     rax, [rcx]
0x14005f126  test    rax, rax
0x14005f129  jz      short loc_14005F13B
0x14005f12b  cmp     rax, r15
0x14005f12e  jz      short loc_14005F135
0x14005f130  mov     rcx, rax
0x14005f133  jmp     short loc_14005F123
0x14005f135  mov     rax, [r15]
0x14005f138  mov     [rcx], rax
0x14005f13b  mov     ebx, 1
0x14005f140  jmp     short loc_14005F168
0x14005f142  mov     ecx, 57h ; 'W'; dwErrCode
0x14005f147  call    cs:__imp_SetLastError
0x14005f14d  mov     ebx, r12d
0x14005f150  call    cs:__imp_GetLastError
0x14005f156  test    eax, eax
0x14005f158  jnz     short loc_14005F163
0x14005f15a  lea     ecx, [rax+8]; dwErrCode
0x14005f15d  call    cs:__imp_SetLastError
0x14005f163  test    rdi, rdi
0x14005f166  jz      short loc_14005F17A
0x14005f168  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14005f16f  mov     r8, rdi; lpMem
0x14005f172  xor     edx, edx; dwFlags
0x14005f174  call    cs:__imp_HeapFree
0x14005f17a  test    r14, r14
0x14005f17d  jz      short loc_14005F191
0x14005f17f  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14005f186  mov     r8, r14; lpMem
0x14005f189  xor     edx, edx; dwFlags
0x14005f18b  call    cs:__imp_HeapFree
0x14005f191  mov     rcx, [rbp+hKey]; hKey
0x14005f195  test    rcx, rcx
0x14005f198  jz      short loc_14005F1A0
0x14005f19a  call    cs:__imp_RegCloseKey
0x14005f1a0  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005f1a7  call    cs:__imp_LeaveCriticalSection
0x14005f1ad  mov     eax, ebx
0x14005f1af  lea     r11, [rsp+60h+var_s0]
0x14005f1b4  mov     rbx, [r11+30h]
0x14005f1b8  mov     rsi, [r11+38h]
0x14005f1bc  mov     rsp, r11
0x14005f1bf  pop     r15
0x14005f1c1  pop     r14
0x14005f1c3  pop     r12
0x14005f1c5  pop     rdi
0x14005f1c6  pop     rbp
0x14005f1c7  retn
```
