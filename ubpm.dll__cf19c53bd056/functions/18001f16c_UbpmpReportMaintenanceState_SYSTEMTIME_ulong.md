# UbpmpReportMaintenanceState(_SYSTEMTIME *,ulong)

- ea: `0x18001f16c`
- end: `0x18001f270`
- name: `?UbpmpReportMaintenanceState@@YAXPEAU_SYSTEMTIME@@K@Z`
- size: `260`
- prototype: `void __fastcall(SYSTEMTIME *lpTime, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002e220`
- `0x18002ea04`
- `0x18002eb98`

## callees

- `0x180007460`
- `0x18000f9a0`
- `0x180019d90`
- `0x18001f16c`
- `0x18001f278`
- `0x18001f374`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f22e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f22e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f265`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f265`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f25a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f25a`

## string_xrefs

- `0x18001f201`: `ReportTaskEvent(0x%x) --> ret=%d`

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
  const unsigned __int16 *v8; // rdx
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  int v11; // eax
  __int64 v12; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  PHKEY phkResulta; // [rsp+20h] [rbp-28h]
  const unsigned __int16 *cbData; // [rsp+28h] [rbp-20h]
  const unsigned __int16 *cbDataa; // [rsp+28h] [rbp-20h]
  unsigned int Data; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v18; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Data = (unsigned int)a2;
  v4 = 0;
  v18 = 0;
  hKey = 0;
  v6 = UbpmUtilsDateTimeToString(lpTime, a2, a3, a4, phkResult, cbData, &v18, 0);
  if ( v6 == 122 )
  {
    v4 = (unsigned __int16 *)UbpmAlloc(2 * v18);
    v6 = UbpmUtilsDateTimeToString(lpTime, v8, v9, v10, (unsigned int)phkResulta, cbDataa, &v18, v4);
  }
  if ( !v6 )
  {
    v11 = EventManager::EvtReport(g_hTaskEventManager, v7, Data, v4, phkResulta, (const struct _GUID *)cbDataa);
    v12 = (unsigned __int16)v11;
    if ( v11 >= 0 )
      v12 = 0;
    TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", MSCHED_MAINTENANCE_STATE_CHANGED, v12);
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
  UBPM_MIDL_user_free(v4);
}

```

## disassembly

```asm
0x18001f16c  mov     rax, rsp
0x18001f16f  mov     [rax+8], rbx
0x18001f173  mov     [rax+10h], edx
0x18001f176  push    rdi
0x18001f177  sub     rsp, 40h
0x18001f17b  xor     ebx, ebx
0x18001f17d  mov     rdi, rcx
0x18001f180  mov     [rax-10h], rbx
0x18001f184  mov     [rax+18h], ebx
0x18001f187  mov     [rax+20h], rbx
0x18001f18b  lea     rax, [rax+18h]
0x18001f18f  mov     [rsp+48h+var_18], rax; unsigned int *
0x18001f194  call    ?UbpmUtilsDateTimeToString@@YAKPEAU_SYSTEMTIME@@PEBGKKK1PEAKPEAG@Z; UbpmUtilsDateTimeToString(_SYSTEMTIME *,ushort const *,ulong,ulong,ulong,ushort const *,ulong *,ushort *)
0x18001f199  cmp     eax, 7Ah ; 'z'
0x18001f19c  jnz     short loc_18001F1C3
0x18001f19e  mov     ecx, [rsp+48h+arg_10]
0x18001f1a2  add     ecx, ecx; Size
0x18001f1a4  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001f1a9  mov     [rsp+48h+var_10], rax; unsigned __int16 *
0x18001f1ae  mov     rbx, rax
0x18001f1b1  lea     rax, [rsp+48h+arg_10]
0x18001f1b6  mov     rcx, rdi; lpTime
0x18001f1b9  mov     [rsp+48h+var_18], rax; unsigned int *
0x18001f1be  call    ?UbpmUtilsDateTimeToString@@YAKPEAU_SYSTEMTIME@@PEBGKKK1PEAKPEAG@Z; UbpmUtilsDateTimeToString(_SYSTEMTIME *,ushort const *,ulong,ulong,ulong,ushort const *,ulong *,ushort *)
0x18001f1c3  test    eax, eax
0x18001f1c5  jz      short loc_18001F1DA
0x18001f1c7  mov     rcx, rbx
0x18001f1ca  call    UBPM_MIDL_user_free
0x18001f1cf  mov     rbx, [rsp+48h+arg_0]
0x18001f1d4  add     rsp, 40h
0x18001f1d8  pop     rdi
0x18001f1d9  retn
0x18001f1da  mov     r8d, [rsp+48h+Data]; unsigned int
0x18001f1df  mov     r9, rbx; unsigned __int16 *
0x18001f1e2  mov     rcx, cs:g_hTaskEventManager; this
0x18001f1e9  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@KPEBGPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ulong,ushort const *,void *,_GUID const *)
0x18001f1ee  xor     ecx, ecx
0x18001f1f0  movzx   r8d, ax
0x18001f1f4  test    eax, eax
0x18001f1f6  lea     rdx, MSCHED_MAINTENANCE_STATE_CHANGED
0x18001f1fd  cmovns  r8d, ecx
0x18001f201  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18001f208  call    TaskEventTrace
0x18001f20d  lea     rcx, [rsp+48h+hKey]
0x18001f212  mov     r9d, 20006h; samDesired
0x18001f218  mov     [rsp+48h+phkResult], rcx; phkResult
0x18001f21d  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001f224  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f22b  xor     r8d, r8d; ulOptions
0x18001f22e  call    cs:__imp_RegOpenKeyExW
0x18001f234  test    eax, eax
0x18001f236  jnz     short loc_18001F1C7
0x18001f238  mov     rcx, [rsp+48h+hKey]; hKey
0x18001f23d  lea     r9d, [rax+4]; dwType
0x18001f241  lea     rax, [rsp+48h+Data]
0x18001f246  mov     dword ptr [rsp+48h+cbData], r9d; cbData
0x18001f24b  xor     r8d, r8d; Reserved
0x18001f24e  mov     [rsp+48h+phkResult], rax; lpData
0x18001f253  lea     rdx, aReportedstate; "ReportedState"
0x18001f25a  call    cs:__imp_RegSetValueExW
0x18001f260  mov     rcx, [rsp+48h+hKey]; hKey
0x18001f265  call    cs:__imp_RegCloseKey
0x18001f26b  jmp     loc_18001F1C7
```
