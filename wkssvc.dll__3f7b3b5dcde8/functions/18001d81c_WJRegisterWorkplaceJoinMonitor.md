# WJRegisterWorkplaceJoinMonitor

- ea: `0x18001d81c`
- end: `0x18001d938`
- name: `WJRegisterWorkplaceJoinMonitor`
- size: `284`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011438`

## callees

- `0x18001d81c`
- `0x18002b6fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d90d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d90d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001d848`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001d848`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d85a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d85a`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d838`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d924`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d838`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001d924`

## pseudocode

```c
__int64 WJRegisterWorkplaceJoinMonitor()
{
  unsigned int v0; // ebx
  __int64 v1; // rdx
  struct _FILETIME v2; // rcx
  __int64 v3; // r9
  int v4; // eax
  __int64 v5; // rdx
  struct _FILETIME v6; // rcx
  __int64 v7; // r9
  int v8; // eax
  unsigned int v9; // edi
  __int64 v11; // [rsp+20h] [rbp-68h]
  __int64 v12; // [rsp+20h] [rbp-68h]
  __int64 v13; // [rsp+30h] [rbp-58h]
  __int64 v14; // [rsp+30h] [rbp-58h]

  v0 = 0;
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJRegisterWorkplaceJoinMonitor");
  InitializeCriticalSection(&g_AutoJoinCriticalSection);
  g_fAutoJoinCriticalSectionInitialized = 1;
  EnterCriticalSection(&g_AutoJoinCriticalSection);
  v4 = WJRegisterKeyNotification(
         v2,
         v1,
         g_szGlobalWorkplaceJoinKey,
         v3,
         v11,
         1,
         v13,
         (__int64)g_szAutomaticDeviceJoinTaskName,
         (HKEY)L"Global Policy",
         (HKEY)&g_AutoJoinCriticalSection,
         (HKEY)WJComputeWorkplaceJoinTaskState,
         g_GlobalPolicyNotification);
  if ( v4 )
  {
    if ( v4 > 0 )
      v0 = (unsigned __int16)v4 | 0x80070000;
    else
      v0 = v4;
  }
  v8 = WJRegisterKeyNotification(
         v6,
         v5,
         g_szLocalWorkplaceJoinKey,
         v7,
         v12,
         0,
         v14,
         (__int64)g_szAutomaticDeviceJoinTaskName,
         (HKEY)L"Local Policy",
         (HKEY)&g_AutoJoinCriticalSection,
         (HKEY)WJComputeWorkplaceJoinTaskState,
         g_LocalPolicyNotification);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v0 = (unsigned __int16)v8 | 0x80070000;
    else
      v0 = v8;
  }
  LeaveCriticalSection(&g_AutoJoinCriticalSection);
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished - hr: 0x%08x", L"WJRegisterWorkplaceJoinMonitor", v0);
  return v9;
}

```

## disassembly

```asm
0x18001d81c  push    rbx
0x18001d81e  push    rsi
0x18001d81f  push    rdi
0x18001d820  push    r14
0x18001d822  push    r15
0x18001d824  sub     rsp, 60h
0x18001d828  lea     rdx, aWjregisterwork; "WJRegisterWorkplaceJoinMonitor"
0x18001d82f  xor     ebx, ebx
0x18001d831  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001d838  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d83e  lea     rsi, g_AutoJoinCriticalSection
0x18001d845  mov     rcx, rsi; lpCriticalSection
0x18001d848  call    cs:__imp_InitializeCriticalSection
0x18001d84e  lea     edi, [rbx+1]
0x18001d851  mov     rcx, rsi; lpCriticalSection
0x18001d854  mov     cs:g_fAutoJoinCriticalSectionInitialized, edi
0x18001d85a  call    cs:__imp_EnterCriticalSection
0x18001d860  lea     rax, g_GlobalPolicyNotification
0x18001d867  mov     [rsp+88h+var_30], rax
0x18001d86c  lea     r14, WJComputeWorkplaceJoinTaskState
0x18001d873  mov     [rsp+88h+var_38], r14
0x18001d878  lea     rax, aGlobalPolicy; "Global Policy"
0x18001d87f  mov     [rsp+88h+var_40], rsi
0x18001d884  lea     r15, g_szAutomaticDeviceJoinTaskName; "Automatic-Device-Join"
0x18001d88b  mov     [rsp+88h+var_48], rax
0x18001d890  lea     r8, g_szGlobalWorkplaceJoinKey; "Software\\Policies\\Microsoft\\Windows"...
0x18001d897  mov     [rsp+88h+var_50], r15
0x18001d89c  mov     [rsp+88h+var_60], edi
0x18001d8a0  call    WJRegisterKeyNotification
0x18001d8a5  test    eax, eax
0x18001d8a7  jz      short loc_18001D8B8
0x18001d8a9  jg      short loc_18001D8AF
0x18001d8ab  mov     ebx, eax
0x18001d8ad  jmp     short loc_18001D8B8
0x18001d8af  movzx   ebx, ax
0x18001d8b2  or      ebx, 80070000h
0x18001d8b8  lea     rax, g_LocalPolicyNotification
0x18001d8bf  mov     [rsp+88h+var_30], rax
0x18001d8c4  lea     r8, g_szLocalWorkplaceJoinKey; "SYSTEM\\CurrentControlSet\\Control\\Wor"...
0x18001d8cb  mov     [rsp+88h+var_38], r14
0x18001d8d0  lea     rax, aLocalPolicy; "Local Policy"
0x18001d8d7  mov     [rsp+88h+var_40], rsi
0x18001d8dc  mov     [rsp+88h+var_48], rax
0x18001d8e1  mov     [rsp+88h+var_50], r15
0x18001d8e6  mov     [rsp+88h+var_60], 0
0x18001d8ee  call    WJRegisterKeyNotification
0x18001d8f3  mov     edi, eax
0x18001d8f5  test    eax, eax
0x18001d8f7  jz      short loc_18001D90A
0x18001d8f9  test    eax, eax
0x18001d8fb  jg      short loc_18001D901
0x18001d8fd  mov     ebx, eax
0x18001d8ff  jmp     short loc_18001D90A
0x18001d901  movzx   ebx, di
0x18001d904  or      ebx, 80070000h
0x18001d90a  mov     rcx, rsi; lpCriticalSection
0x18001d90d  call    cs:__imp_LeaveCriticalSection
0x18001d913  mov     r8d, ebx
0x18001d916  lea     rdx, aWjregisterwork; "WJRegisterWorkplaceJoinMonitor"
0x18001d91d  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001d924  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001d92a  mov     eax, edi
0x18001d92c  add     rsp, 60h
0x18001d930  pop     r15
0x18001d932  pop     r14
0x18001d934  pop     rdi
0x18001d935  pop     rsi
0x18001d936  pop     rbx
0x18001d937  retn
```
