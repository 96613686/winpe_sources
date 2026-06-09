# HasActiveConsoleWindow(bool &)

- ea: `0x180011124`
- end: `0x18001116e`
- name: `?HasActiveConsoleWindow@@YAKAEA_N@Z`
- size: `74`
- prototype: `unsigned int __fastcall(bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800209fc`

## callees

- `0x180011124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001114f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001114f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011138`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011138`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180011157`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180011157`
- `KERNEL32!ProcessIdToSessionId` at `0x180011145`
- `KERNEL32!ProcessIdToSessionId` at `0x180011145`

## pseudocode

```c
DWORD __fastcall HasActiveConsoleWindow(bool *a1)
{
  DWORD CurrentProcessId; // eax
  DWORD pSessionId; // [rsp+30h] [rbp+8h] BYREF

  pSessionId = 0;
  *a1 = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return GetLastError();
  *a1 = WTSGetActiveConsoleSessionId() == pSessionId;
  return 0;
}

```

## disassembly

```asm
0x180011124  push    rbx
0x180011126  sub     rsp, 20h
0x18001112a  mov     rbx, rcx
0x18001112d  mov     [rsp+28h+pSessionId], 0
0x180011135  mov     byte ptr [rcx], 0
0x180011138  call    cs:__imp_GetCurrentProcessId
0x18001113e  mov     ecx, eax; dwProcessId
0x180011140  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x180011145  call    cs:__imp_ProcessIdToSessionId
0x18001114b  test    eax, eax
0x18001114d  jnz     short loc_180011157
0x18001114f  call    cs:__imp_GetLastError
0x180011155  jmp     short loc_180011168
0x180011157  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18001115d  cmp     eax, [rsp+28h+pSessionId]
0x180011161  setz    al
0x180011164  mov     [rbx], al
0x180011166  xor     eax, eax
0x180011168  add     rsp, 20h
0x18001116c  pop     rbx
0x18001116d  retn
```
