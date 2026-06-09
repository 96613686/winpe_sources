# WJRegisterKeyNotification

- ea: `0x18002dde4`
- end: `0x18002e163`
- name: `WJRegisterKeyNotification`
- size: `895`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18001e3bc`
- `0x18001ef0c`

## callees

- `0x18002dde4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002e118`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18002e118`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dea4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002def5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002df74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002def5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002df74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e03d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e03d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002df13`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002df13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002df88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002df88`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002e022`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002e022`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002e0b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002e0e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002e0b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002e0e6`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002ded7`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002df4d`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002dfb5`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e152`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002ded7`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002df4d`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002dfb5`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e152`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002de67`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002dfee`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e0d8`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002de67`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002dfee`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e0d8`

## string_xrefs

- `0x18002de42`: `AutoJoinSvc/%s: started. Key name: "%s". Reg key: "%s\%s". Task: "%s\%s". bInitialState: %s.`
- `0x18002ded0`: `AutoJoinSvc/%s: Failed to open %s registry key "%s\%s" with status 0x%08x.`
- `0x18002df37`: `AutoJoinSvc/%s: Failed to create wait event for %s with status 0x%08x.`
- `0x18002e049`: `AutoJoinSvc/%s: Failed to create thread-pool wait for %s with status 0x%08x.`
- `0x18002e0d1`: `AutoJoinSvc/%s: Successfully queued a thread to set initial state of the task ("%s\%s")`
- `0x18002dfae`: `AutoJoinSvc/%s: Failed to register change notification for %s registry key "%s\%s" with status 0x%08x.`
- `0x18002e14b`: `AutoJoinSvc/%s: Failed to register change notification for %s registry key "%s\%s" with status 0x%08x.`
- `0x18002dfd2`: `AutoJoinSvc/%s: finished - Return code: 0x%08x. Key name: "%s". Reg key: "%s\%s". Task: "%s\%s". bInitialState: %s.`

## pseudocode

```c
__int64 __fastcall WJRegisterKeyNotification(
        struct _FILETIME a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        HKEY a9,
        HKEY a10,
        HKEY a11,
        PVOID pv)
{
  int v12; // r15d
  __int64 v13; // r12
  const wchar_t *v14; // r13
  HKEY v15; // rbp
  HKEY EventW; // rsi
  HKEY *v18; // rdi
  LSTATUS v19; // eax
  DWORD v20; // ebx
  DWORD LastError; // eax
  const wchar_t *v22; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v25; // rcx
  HKEY v26; // rdx
  HKEY v27; // rax
  LSTATUS v28; // eax
  __int64 v29; // [rsp+28h] [rbp-60h]
  struct _FILETIME pftTimeout; // [rsp+90h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+10h] BYREF

  pftTimeout = a1;
  v12 = a6;
  v13 = a8;
  v14 = L"TRUE";
  v15 = a9;
  EventW = 0;
  hKey = 0;
  if ( !a6 )
    v14 = L"FALSE";
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: started. Key name: \"%s\". Reg key: \"%s\\%s\". Task: \"%s\\%s\". bInitialState: %s.",
    L"WJRegisterKeyNotification",
    a9,
    L"HKEY_LOCAL_MACHINE",
    a3,
    g_szTaskFolder,
    a8,
    v14);
  v18 = (HKEY *)pv;
  *(_QWORD *)pv = 0;
  v18[1] = 0;
  v18[2] = 0;
  v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x10u, &hKey);
  v20 = v19;
  if ( v19 )
  {
    LODWORD(v29) = v19;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to open %s registry key \"%s\\%s\" with status 0x%08x.",
      L"WJRegisterKeyNotification",
      v15,
      L"HKEY_LOCAL_MACHINE",
      a3,
      v29);
    if ( !v12 )
      goto LABEL_10;
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
  }
  EventW = (HKEY)CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v22 = L"AutoJoinSvc/%s: Failed to create wait event for %s with status 0x%08x.";
LABEL_9:
    v20 = LastError;
    DsrWriteAutoJoinSvcAdminEvent(v22, L"WJRegisterKeyNotification", v15, LastError);
    goto LABEL_10;
  }
  ThreadpoolWait = CreateThreadpoolWait(WJRegistryKeyChangedCallback, v18, 0);
  v18[2] = (HKEY)ThreadpoolWait;
  v25 = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = GetLastError();
    v22 = L"AutoJoinSvc/%s: Failed to create thread-pool wait for %s with status 0x%08x.";
    goto LABEL_9;
  }
  *v18 = hKey;
  v26 = EventW;
  v18[5] = a10;
  v27 = a11;
  v18[1] = EventW;
  EventW = 0;
  v18[6] = v27;
  hKey = 0;
  *((_DWORD *)v18 + 6) = 0;
  *((_DWORD *)v18 + 7) = 268435460;
  v18[4] = v15;
  if ( v12 )
  {
    pftTimeout = 0;
    SetThreadpoolWait(v25, v26, &pftTimeout);
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Successfully queued a thread to set initial state of the task (\"%s\\%s\")",
      L"WJRegisterKeyNotification",
      g_szTaskFolder,
      v13);
  }
  else
  {
    SetThreadpoolWait(v25, v26, 0);
  }
  if ( *v18 )
  {
    v28 = RegNotifyChangeKeyValue(*v18, *((_DWORD *)v18 + 6), *((_DWORD *)v18 + 7), v18[1], 1);
    v20 = v28;
    if ( v28 )
    {
      LODWORD(v29) = v28;
      DsrWriteAutoJoinSvcAdminEvent(
        L"AutoJoinSvc/%s: Failed to register change notification for %s registry key \"%s\\%s\" with status 0x%08x.",
        L"WJRegisterKeyNotification",
        v15,
        L"HKEY_LOCAL_MACHINE",
        a3,
        v29);
    }
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  if ( EventW )
    CloseHandle(EventW);
  if ( v20 )
  {
    LODWORD(v29) = v20;
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to register change notification for %s registry key \"%s\\%s\" with status 0x%08x.",
      L"WJRegisterKeyNotification",
      v15,
      L"HKEY_LOCAL_MACHINE",
      a3,
      v29);
  }
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: finished - Return code: 0x%08x. Key name: \"%s\". Reg key: \"%s\\%s\". Task: \"%s\\%s\". bInitialState: %s.",
    L"WJRegisterKeyNotification",
    v20,
    v15,
    L"HKEY_LOCAL_MACHINE",
    a3,
    g_szTaskFolder,
    v13,
    v14);
  return v20;
}

```

## disassembly

```asm
0x18002dde4  mov     r11, rsp
0x18002dde7  mov     [r11+18h], rbx
0x18002ddeb  mov     [r11+10h], rdx
0x18002ddef  mov     [r11+8], rcx
0x18002ddf3  push    rbp
0x18002ddf4  push    rsi
0x18002ddf5  push    rdi
0x18002ddf6  push    r12
0x18002ddf8  push    r13
0x18002ddfa  push    r14
0x18002ddfc  push    r15
0x18002ddfe  sub     rsp, 50h
0x18002de02  mov     r15d, [rsp+88h+arg_28]
0x18002de0a  lea     rax, aFalse_0; "FALSE"
0x18002de11  mov     r12, [rsp+88h+arg_38]
0x18002de19  lea     r13, aTrue_0; "TRUE"
0x18002de20  mov     rbp, [rsp+88h+arg_40]
0x18002de28  lea     r9, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18002de2f  xor     esi, esi
0x18002de31  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002de38  mov     r14, r8
0x18002de3b  mov     [r11+10h], rsi
0x18002de3f  test    r15d, r15d
0x18002de42  lea     rcx, aAutojoinsvcSSt_0; "AutoJoinSvc/%s: started. Key name: \"%s"...
0x18002de49  cmovz   r13, rax
0x18002de4d  lea     rax, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18002de54  mov     [r11-50h], r13
0x18002de58  mov     [r11-58h], r12
0x18002de5c  mov     [r11-60h], rax
0x18002de60  mov     [r11-68h], r8
0x18002de64  mov     r8, rbp
0x18002de67  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002de6e  nop     dword ptr [rax+rax+00h]
0x18002de73  mov     rdi, [rsp+88h+pv]
0x18002de7b  lea     rax, [rsp+88h+hKey]
0x18002de83  lea     r9d, [rsi+10h]; samDesired
0x18002de87  mov     [rsp+88h+phkResult], rax; phkResult
0x18002de8c  xor     r8d, r8d; ulOptions
0x18002de8f  mov     rdx, r14; lpSubKey
0x18002de92  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002de99  mov     [rdi], rsi
0x18002de9c  mov     [rdi+8], rsi
0x18002dea0  mov     [rdi+10h], rsi
0x18002dea4  call    cs:__imp_RegOpenKeyExW
0x18002deab  nop     dword ptr [rax+rax+00h]
0x18002deb0  mov     ebx, eax
0x18002deb2  test    eax, eax
0x18002deb4  jz      short loc_18002DF09
0x18002deb6  mov     dword ptr [rsp+88h+var_60], eax
0x18002deba  lea     r9, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18002dec1  mov     r8, rbp
0x18002dec4  mov     [rsp+88h+phkResult], r14
0x18002dec9  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002ded0  lea     rcx, aAutojoinsvcSFa_9; "AutoJoinSvc/%s: Failed to open %s regis"...
0x18002ded7  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002dede  nop     dword ptr [rax+rax+00h]
0x18002dee3  test    r15d, r15d
0x18002dee6  jz      short loc_18002DF59
0x18002dee8  mov     rcx, [rsp+88h+hKey]; hKey
0x18002def0  test    rcx, rcx
0x18002def3  jz      short loc_18002DF09
0x18002def5  call    cs:__imp_RegCloseKey
0x18002defc  nop     dword ptr [rax+rax+00h]
0x18002df01  mov     [rsp+88h+hKey], rsi
0x18002df09  xor     r9d, r9d; lpName
0x18002df0c  xor     r8d, r8d; bInitialState
0x18002df0f  xor     edx, edx; bManualReset
0x18002df11  xor     ecx, ecx; lpEventAttributes
0x18002df13  call    cs:__imp_CreateEventW
0x18002df1a  nop     dword ptr [rax+rax+00h]
0x18002df1f  mov     rsi, rax
0x18002df22  test    rax, rax
0x18002df25  jnz     loc_18002E015
0x18002df2b  call    cs:__imp_GetLastError
0x18002df32  nop     dword ptr [rax+rax+00h]
0x18002df37  lea     rcx, aAutojoinsvcSFa_18; "AutoJoinSvc/%s: Failed to create wait e"...
0x18002df3e  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002df45  mov     r8, rbp
0x18002df48  mov     r9d, eax
0x18002df4b  mov     ebx, eax
0x18002df4d  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002df54  nop     dword ptr [rax+rax+00h]
0x18002df59  lea     r15, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18002df60  lea     rdi, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18002df67  mov     rcx, [rsp+88h+hKey]; hKey
0x18002df6f  test    rcx, rcx
0x18002df72  jz      short loc_18002DF80
0x18002df74  call    cs:__imp_RegCloseKey
0x18002df7b  nop     dword ptr [rax+rax+00h]
0x18002df80  test    rsi, rsi
0x18002df83  jz      short loc_18002DF94
0x18002df85  mov     rcx, rsi; hObject
0x18002df88  call    cs:__imp_CloseHandle
0x18002df8f  nop     dword ptr [rax+rax+00h]
0x18002df94  test    ebx, ebx
0x18002df96  jz      short loc_18002DFC1
0x18002df98  mov     dword ptr [rsp+88h+var_60], ebx
0x18002df9c  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002dfa3  mov     r9, rdi
0x18002dfa6  mov     [rsp+88h+phkResult], r14
0x18002dfab  mov     r8, rbp
0x18002dfae  lea     rcx, aAutojoinsvcSFa_21; "AutoJoinSvc/%s: Failed to register chan"...
0x18002dfb5  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002dfbc  nop     dword ptr [rax+rax+00h]
0x18002dfc1  mov     [rsp+88h+var_48], r13
0x18002dfc6  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002dfcd  mov     [rsp+88h+var_50], r12
0x18002dfd2  lea     rcx, aAutojoinsvcSFi_0; "AutoJoinSvc/%s: finished - Return code:"...
0x18002dfd9  mov     [rsp+88h+var_58], r15
0x18002dfde  mov     r9, rbp
0x18002dfe1  mov     [rsp+88h+var_60], r14
0x18002dfe6  mov     r8d, ebx
0x18002dfe9  mov     [rsp+88h+phkResult], rdi
0x18002dfee  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002dff5  nop     dword ptr [rax+rax+00h]
0x18002dffa  mov     eax, ebx
0x18002dffc  mov     rbx, [rsp+88h+arg_10]
0x18002e004  add     rsp, 50h
0x18002e008  pop     r15
0x18002e00a  pop     r14
0x18002e00c  pop     r13
0x18002e00e  pop     r12
0x18002e010  pop     rdi
0x18002e011  pop     rsi
0x18002e012  pop     rbp
0x18002e013  retn
0x18002e015  xor     r8d, r8d; pcbe
0x18002e018  lea     rcx, WJRegistryKeyChangedCallback; pfnwa
0x18002e01f  mov     rdx, rdi; pv
0x18002e022  call    cs:__imp_CreateThreadpoolWait
0x18002e029  nop     dword ptr [rax+rax+00h]
0x18002e02e  xor     r8d, r8d; pftTimeout
0x18002e031  mov     [rdi+10h], rax
0x18002e035  mov     rcx, rax; pwa
0x18002e038  test    rax, rax
0x18002e03b  jnz     short loc_18002E055
0x18002e03d  call    cs:__imp_GetLastError
0x18002e044  nop     dword ptr [rax+rax+00h]
0x18002e049  lea     rcx, aAutojoinsvcSFa_14; "AutoJoinSvc/%s: Failed to create thread"...
0x18002e050  jmp     loc_18002DF3E
0x18002e055  mov     rax, [rsp+88h+hKey]
0x18002e05d  mov     r9, rsi
0x18002e060  mov     [rdi], rax
0x18002e063  mov     rdx, rsi; h
0x18002e066  mov     rax, [rsp+88h+arg_48]
0x18002e06e  mov     [rdi+28h], rax
0x18002e072  mov     rax, [rsp+88h+arg_50]
0x18002e07a  mov     [rdi+8], rsi
0x18002e07e  mov     rsi, r8
0x18002e081  mov     [rdi+30h], rax
0x18002e085  mov     [rsp+88h+hKey], r8
0x18002e08d  mov     [rdi+18h], r8d
0x18002e091  mov     dword ptr [rdi+1Ch], 10000004h
0x18002e098  mov     [rdi+20h], rbp
0x18002e09c  test    r15d, r15d
0x18002e09f  jz      short loc_18002E0E6
0x18002e0a1  mov     qword ptr [rsp+88h+pftTimeout.dwLowDateTime], r8
0x18002e0a9  lea     r8, [rsp+88h+pftTimeout]; pftTimeout
0x18002e0b1  call    cs:__imp_SetThreadpoolWait
0x18002e0b8  nop     dword ptr [rax+rax+00h]
0x18002e0bd  lea     r15, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18002e0c4  mov     r9, r12
0x18002e0c7  mov     r8, r15
0x18002e0ca  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002e0d1  lea     rcx, aAutojoinsvcSSu; "AutoJoinSvc/%s: Successfully queued a t"...
0x18002e0d8  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e0df  nop     dword ptr [rax+rax+00h]
0x18002e0e4  jmp     short loc_18002E0F9
0x18002e0e6  call    cs:__imp_SetThreadpoolWait
0x18002e0ed  nop     dword ptr [rax+rax+00h]
0x18002e0f2  lea     r15, g_szTaskFolder; "\\Microsoft\\Windows\\Workplace Join"
0x18002e0f9  mov     rcx, [rdi]; hKey
0x18002e0fc  test    rcx, rcx
0x18002e0ff  jz      loc_18002DF60
0x18002e105  mov     r9, [rdi+8]; hEvent
0x18002e109  mov     r8d, [rdi+1Ch]; dwNotifyFilter
0x18002e10d  mov     edx, [rdi+18h]; bWatchSubtree
0x18002e110  mov     dword ptr [rsp+88h+phkResult], 1; fAsynchronous
0x18002e118  call    cs:__imp_RegNotifyChangeKeyValue
0x18002e11f  nop     dword ptr [rax+rax+00h]
0x18002e124  mov     ebx, eax
0x18002e126  test    eax, eax
0x18002e128  jz      loc_18002DF60
0x18002e12e  mov     dword ptr [rsp+88h+var_60], eax
0x18002e132  lea     rdi, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18002e139  mov     r9, rdi
0x18002e13c  mov     [rsp+88h+phkResult], r14
0x18002e141  mov     r8, rbp
0x18002e144  lea     rdx, aWjregisterkeyn; "WJRegisterKeyNotification"
0x18002e14b  lea     rcx, aAutojoinsvcSFa_21; "AutoJoinSvc/%s: Failed to register chan"...
0x18002e152  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e159  nop     dword ptr [rax+rax+00h]
0x18002e15e  jmp     loc_18002DF67
```
