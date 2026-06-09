# UbpmpReportMaintenanceState(_SYSTEMTIME *,ulong)

- ea: `0x18001b74c`
- end: `0x18001b863`
- name: `?UbpmpReportMaintenanceState@@YAXPEAU_SYSTEMTIME@@K@Z`
- size: `279`
- prototype: `void __fastcall(SYSTEMTIME *lpTime, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030390`
- `0x180030bb4`
- `0x180030d58`

## callees

- `0x180007e9c`
- `0x18000fbf0`
- `0x1800150c0`
- `0x18001b74c`
- `0x18001b86c`
- `0x18001b98c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b80f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b80f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b852`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b852`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b841`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b841`

## string_xrefs

- `0x18001b7e2`: `ReportTaskEvent(0x%x) --> ret=%d`

## pseudocode

```c
void __fastcall UbpmpReportMaintenanceState(
        SYSTEMTIME *lpTime,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned __int16 *v4; // rbx
  unsigned int v6; // eax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // r8d
  unsigned int v12; // r9d
  int v13; // eax
  __int64 v14; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  PHKEY phkResulta; // [rsp+20h] [rbp-28h]
  const unsigned __int16 *cbData; // [rsp+28h] [rbp-20h]
  const unsigned __int16 *cbDataa; // [rsp+28h] [rbp-20h]
  unsigned int Data; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v20; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Data = (unsigned int)a2;
  v4 = 0;
  v20 = 0;
  hKey = 0;
  v6 = UbpmUtilsDateTimeToString(lpTime, a2, a3, a4, phkResult, cbData, &v20, 0);
  if ( v6 == 122 )
  {
    v4 = (unsigned __int16 *)UbpmAlloc(2 * v20);
    v6 = UbpmUtilsDateTimeToString(lpTime, v10, v11, v12, (unsigned int)phkResulta, cbDataa, &v20, v4);
  }
  if ( !v6 )
  {
    v13 = EventManager::EvtReport(g_hTaskEventManager, v7, Data, v4, phkResulta, (const struct _GUID *)cbDataa);
    v14 = (unsigned __int16)v13;
    if ( v13 >= 0 )
      v14 = 0;
    TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", MSCHED_MAINTENANCE_STATE_CHANGED, v14);
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Maintenance\\State",
            0,
            0x20006u,
            &hKey) )
    {
      RegSetValueExW(hKey, L"ReportedState", 0, 4u, (const BYTE *)&Data, 4u);
      RegCloseKey(hKey);
    }
  }
  UBPM_MIDL_user_free(v4, v7, v8, v9);
}

```

## disassembly

```asm
0x18001b74c  mov     rax, rsp
0x18001b74f  mov     [rax+8], rbx
0x18001b753  mov     [rax+10h], edx
0x18001b756  push    rdi
0x18001b757  sub     rsp, 40h
0x18001b75b  xor     ebx, ebx
0x18001b75d  mov     rdi, rcx
0x18001b760  mov     [rax-10h], rbx
0x18001b764  mov     [rax+18h], ebx
0x18001b767  mov     [rax+20h], rbx
0x18001b76b  lea     rax, [rax+18h]
0x18001b76f  mov     [rsp+48h+var_18], rax; unsigned int *
0x18001b774  call    ?UbpmUtilsDateTimeToString@@YAKPEAU_SYSTEMTIME@@PEBGKKK1PEAKPEAG@Z; UbpmUtilsDateTimeToString(_SYSTEMTIME *,ushort const *,ulong,ulong,ulong,ushort const *,ulong *,ushort *)
0x18001b779  cmp     eax, 7Ah ; 'z'
0x18001b77c  jnz     short loc_18001B7A3
0x18001b77e  mov     ecx, [rsp+48h+arg_10]
0x18001b782  add     ecx, ecx; Size
0x18001b784  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001b789  mov     [rsp+48h+var_10], rax; unsigned __int16 *
0x18001b78e  mov     rbx, rax
0x18001b791  lea     rax, [rsp+48h+arg_10]
0x18001b796  mov     rcx, rdi; lpTime
0x18001b799  mov     [rsp+48h+var_18], rax; unsigned int *
0x18001b79e  call    ?UbpmUtilsDateTimeToString@@YAKPEAU_SYSTEMTIME@@PEBGKKK1PEAKPEAG@Z; UbpmUtilsDateTimeToString(_SYSTEMTIME *,ushort const *,ulong,ulong,ulong,ushort const *,ulong *,ushort *)
0x18001b7a3  test    eax, eax
0x18001b7a5  jz      short loc_18001B7BB
0x18001b7a7  mov     rcx, rbx
0x18001b7aa  call    UBPM_MIDL_user_free
0x18001b7af  mov     rbx, [rsp+48h+arg_0]
0x18001b7b4  add     rsp, 40h
0x18001b7b8  pop     rdi
0x18001b7b9  retn
0x18001b7bb  mov     r8d, [rsp+48h+Data]; unsigned int
0x18001b7c0  mov     r9, rbx; unsigned __int16 *
0x18001b7c3  mov     rcx, cs:g_hTaskEventManager; this
0x18001b7ca  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEBGPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ushort const *,void *,_GUID const *)
0x18001b7cf  xor     ecx, ecx
0x18001b7d1  movzx   r8d, ax
0x18001b7d5  test    eax, eax
0x18001b7d7  lea     rdx, MSCHED_MAINTENANCE_STATE_CHANGED
0x18001b7de  cmovns  r8d, ecx
0x18001b7e2  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18001b7e9  call    TaskEventTrace
0x18001b7ee  lea     rcx, [rsp+48h+hKey]
0x18001b7f3  mov     r9d, 20006h; samDesired
0x18001b7f9  mov     [rsp+48h+phkResult], rcx; phkResult
0x18001b7fe  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001b805  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b80c  xor     r8d, r8d; ulOptions
0x18001b80f  call    cs:__imp_RegOpenKeyExW
0x18001b816  nop     dword ptr [rax+rax+00h]
0x18001b81b  test    eax, eax
0x18001b81d  jnz     short loc_18001B7A7
0x18001b81f  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b824  lea     r9d, [rax+4]; dwType
0x18001b828  lea     rax, [rsp+48h+Data]
0x18001b82d  mov     dword ptr [rsp+48h+cbData], r9d; cbData
0x18001b832  xor     r8d, r8d; Reserved
0x18001b835  mov     [rsp+48h+phkResult], rax; lpData
0x18001b83a  lea     rdx, aReportedstate; "ReportedState"
0x18001b841  call    cs:__imp_RegSetValueExW
0x18001b848  nop     dword ptr [rax+rax+00h]
0x18001b84d  mov     rcx, [rsp+48h+hKey]; hKey
0x18001b852  call    cs:__imp_RegCloseKey
0x18001b859  nop     dword ptr [rax+rax+00h]
0x18001b85e  jmp     loc_18001B7A7
```
