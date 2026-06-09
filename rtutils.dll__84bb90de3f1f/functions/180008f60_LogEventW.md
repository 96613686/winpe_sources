# LogEventW

- ea: `0x180008f60`
- end: `0x180008fce`
- name: `LogEventW`
- size: `110`
- prototype: `void __stdcall(DWORD wEventType, DWORD dwMessageId, DWORD cNumberOfSubStrings, LPWSTR *plpwsSubStrings)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008f60`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180008f7f`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180008f7f`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180008fb4`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180008fb4`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180008fbd`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180008fbd`

## string_xrefs

- `0x180008f70`: `RemoteAccess`

## pseudocode

```c
void __stdcall LogEventW(DWORD wEventType, DWORD dwMessageId, DWORD cNumberOfSubStrings, LPWSTR *plpwsSubStrings)
{
  WORD v5; // r14
  WORD wNumStrings; // si
  HANDLE v8; // rbx

  v5 = wEventType;
  wNumStrings = cNumberOfSubStrings;
  v8 = RegisterEventSourceW(0, L"RemoteAccess");
  if ( v8 )
  {
    ReportEventW(v8, v5, 0, dwMessageId, 0, wNumStrings, 0, (LPCWSTR *)plpwsSubStrings, 0);
    DeregisterEventSource(v8);
  }
}

```

## disassembly

```asm
0x180008f60  push    rbx
0x180008f62  push    rbp
0x180008f63  push    rsi
0x180008f64  push    rdi
0x180008f65  push    r14
0x180008f67  sub     rsp, 50h
0x180008f6b  mov     ebp, edx
0x180008f6d  mov     r14d, ecx
0x180008f70  lea     rdx, aRemoteaccess; "RemoteAccess"
0x180008f77  xor     ecx, ecx; lpUNCServerName
0x180008f79  mov     rdi, r9
0x180008f7c  mov     esi, r8d
0x180008f7f  call    cs:__imp_RegisterEventSourceW
0x180008f85  mov     rbx, rax
0x180008f88  xor     eax, eax
0x180008f8a  test    rbx, rbx
0x180008f8d  jz      short loc_180008FC3
0x180008f8f  mov     [rsp+78h+lpRawData], rax; lpRawData
0x180008f94  xor     r8d, r8d; wCategory
0x180008f97  mov     [rsp+78h+lpStrings], rdi; lpStrings
0x180008f9c  movzx   edx, r14w; wType
0x180008fa0  mov     [rsp+78h+dwDataSize], eax; dwDataSize
0x180008fa4  mov     r9d, ebp; dwEventID
0x180008fa7  mov     [rsp+78h+wNumStrings], si; wNumStrings
0x180008fac  mov     rcx, rbx; hEventLog
0x180008faf  mov     [rsp+78h+lpUserSid], rax; lpUserSid
0x180008fb4  call    cs:__imp_ReportEventW
0x180008fba  mov     rcx, rbx; hEventLog
0x180008fbd  call    cs:__imp_DeregisterEventSource
0x180008fc3  add     rsp, 50h
0x180008fc7  pop     r14
0x180008fc9  pop     rdi
0x180008fca  pop     rsi
0x180008fcb  pop     rbp
0x180008fcc  pop     rbx
0x180008fcd  retn
```
