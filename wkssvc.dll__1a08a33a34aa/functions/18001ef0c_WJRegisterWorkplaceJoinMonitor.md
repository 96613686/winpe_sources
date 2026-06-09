# WJRegisterWorkplaceJoinMonitor

- ea: `0x18001ef0c`
- end: `0x18001f047`
- name: `WJRegisterWorkplaceJoinMonitor`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012368`

## callees

- `0x18001ef0c`
- `0x18002dde4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f00f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f00f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001ef3e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001ef3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef56`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ef28`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f02c`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001ef28`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f02c`

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
0x18001ef0c  push    rbx
0x18001ef0e  push    rsi
0x18001ef0f  push    rdi
0x18001ef10  push    r14
0x18001ef12  push    r15
0x18001ef14  sub     rsp, 60h
0x18001ef18  lea     rdx, aWjregisterwork; "WJRegisterWorkplaceJoinMonitor"
0x18001ef1f  xor     ebx, ebx
0x18001ef21  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001ef28  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001ef2f  nop     dword ptr [rax+rax+00h]
0x18001ef34  lea     rsi, g_AutoJoinCriticalSection
0x18001ef3b  mov     rcx, rsi; lpCriticalSection
0x18001ef3e  call    cs:__imp_InitializeCriticalSection
0x18001ef45  nop     dword ptr [rax+rax+00h]
0x18001ef4a  lea     edi, [rbx+1]
0x18001ef4d  mov     rcx, rsi; lpCriticalSection
0x18001ef50  mov     cs:g_fAutoJoinCriticalSectionInitialized, edi
0x18001ef56  call    cs:__imp_EnterCriticalSection
0x18001ef5d  nop     dword ptr [rax+rax+00h]
0x18001ef62  lea     rax, g_GlobalPolicyNotification
0x18001ef69  mov     [rsp+88h+var_30], rax
0x18001ef6e  lea     r14, WJComputeWorkplaceJoinTaskState
0x18001ef75  mov     [rsp+88h+var_38], r14
0x18001ef7a  lea     rax, aGlobalPolicy; "Global Policy"
0x18001ef81  mov     [rsp+88h+var_40], rsi
0x18001ef86  lea     r15, g_szAutomaticDeviceJoinTaskName; "Automatic-Device-Join"
0x18001ef8d  mov     [rsp+88h+var_48], rax
0x18001ef92  lea     r8, g_szGlobalWorkplaceJoinKey; "Software\\Policies\\Microsoft\\Windows"...
0x18001ef99  mov     [rsp+88h+var_50], r15
0x18001ef9e  mov     [rsp+88h+var_60], edi
0x18001efa2  call    WJRegisterKeyNotification
0x18001efa7  test    eax, eax
0x18001efa9  jz      short loc_18001EFBA
0x18001efab  jg      short loc_18001EFB1
0x18001efad  mov     ebx, eax
0x18001efaf  jmp     short loc_18001EFBA
0x18001efb1  movzx   ebx, ax
0x18001efb4  or      ebx, 80070000h
0x18001efba  lea     rax, g_LocalPolicyNotification
0x18001efc1  mov     [rsp+88h+var_30], rax
0x18001efc6  lea     r8, g_szLocalWorkplaceJoinKey; "SYSTEM\\CurrentControlSet\\Control\\Wor"...
0x18001efcd  mov     [rsp+88h+var_38], r14
0x18001efd2  lea     rax, aLocalPolicy; "Local Policy"
0x18001efd9  mov     [rsp+88h+var_40], rsi
0x18001efde  mov     [rsp+88h+var_48], rax
0x18001efe3  mov     [rsp+88h+var_50], r15
0x18001efe8  mov     [rsp+88h+var_60], 0
0x18001eff0  call    WJRegisterKeyNotification
0x18001eff5  mov     edi, eax
0x18001eff7  test    eax, eax
0x18001eff9  jz      short loc_18001F00C
0x18001effb  test    eax, eax
0x18001effd  jg      short loc_18001F003
0x18001efff  mov     ebx, eax
0x18001f001  jmp     short loc_18001F00C
0x18001f003  movzx   ebx, di
0x18001f006  or      ebx, 80070000h
0x18001f00c  mov     rcx, rsi; lpCriticalSection
0x18001f00f  call    cs:__imp_LeaveCriticalSection
0x18001f016  nop     dword ptr [rax+rax+00h]
0x18001f01b  mov     r8d, ebx
0x18001f01e  lea     rdx, aWjregisterwork; "WJRegisterWorkplaceJoinMonitor"
0x18001f025  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001f02c  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001f033  nop     dword ptr [rax+rax+00h]
0x18001f038  mov     eax, edi
0x18001f03a  add     rsp, 60h
0x18001f03e  pop     r15
0x18001f040  pop     r14
0x18001f042  pop     rdi
0x18001f043  pop     rsi
0x18001f044  pop     rbx
0x18001f045  retn
```
