# WTSCurrentSessionIsDisconnected(void)

- ea: `0x180003348`
- end: `0x1800033af`
- name: `?WTSCurrentSessionIsDisconnected@@YAHXZ`
- size: `103`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180003124`

## callees

- `0x180003348`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x180003365`
- `ntdll!RtlGetActiveConsoleId` at `0x180003365`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000338b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000338b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000337e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000337e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180003374`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180003374`

## pseudocode

```c
_BOOL8 WTSCurrentSessionIsDisconnected(void)
{
  ULONG SessionId; // ebx
  DWORD CurrentProcessId; // eax
  DWORD pSessionId; // [rsp+30h] [rbp+8h] BYREF

  pSessionId = 0;
  SessionId = NtCurrentPeb()->SessionId;
  if ( (unsigned int)RtlGetActiveConsoleId() == SessionId || GetSystemMetrics(4096) )
    return 0;
  CurrentProcessId = GetCurrentProcessId();
  return !ProcessIdToSessionId(CurrentProcessId, &pSessionId) || pSessionId != 0;
}

```

## disassembly

```asm
0x180003348  push    rbx
0x18000334a  sub     rsp, 20h
0x18000334e  mov     [rsp+28h+pSessionId], 0
0x180003356  mov     rax, gs:60h
0x18000335f  mov     ebx, [rax+2C0h]
0x180003365  call    cs:__imp_RtlGetActiveConsoleId
0x18000336b  cmp     eax, ebx
0x18000336d  jz      short loc_1800033A7
0x18000336f  mov     ecx, 1000h; nIndex
0x180003374  call    cs:__imp_GetSystemMetrics
0x18000337a  test    eax, eax
0x18000337c  jnz     short loc_1800033A7
0x18000337e  call    cs:__imp_GetCurrentProcessId
0x180003384  mov     ecx, eax; dwProcessId
0x180003386  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x18000338b  call    cs:__imp_ProcessIdToSessionId
0x180003391  test    eax, eax
0x180003393  jz      short loc_1800033A0
0x180003395  xor     eax, eax
0x180003397  cmp     [rsp+28h+pSessionId], eax
0x18000339b  setnz   al
0x18000339e  jmp     short loc_1800033A9
0x1800033a0  mov     eax, 1
0x1800033a5  jmp     short loc_1800033A9
0x1800033a7  xor     eax, eax
0x1800033a9  add     rsp, 20h
0x1800033ad  pop     rbx
0x1800033ae  retn
```
