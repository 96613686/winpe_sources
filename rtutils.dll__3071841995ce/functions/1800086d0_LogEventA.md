# LogEventA

- ea: `0x1800086d0`
- end: `0x18000873e`
- name: `LogEventA`
- size: `110`
- prototype: `void __stdcall(DWORD wEventType, DWORD dwMessageId, DWORD cNumberOfSubStrings, LPSTR *plpwsSubStrings)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800086d0`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventA` at `0x180008724`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventA` at `0x180008724`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18000872d`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x18000872d`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceA` at `0x1800086ef`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceA` at `0x1800086ef`

## string_xrefs

- `0x1800086e0`: `RemoteAccess`

## pseudocode

```c
void __stdcall LogEventA(DWORD wEventType, DWORD dwMessageId, DWORD cNumberOfSubStrings, LPSTR *plpwsSubStrings)
{
  WORD v5; // r14
  WORD wNumStrings; // si
  HANDLE v8; // rbx

  v5 = wEventType;
  wNumStrings = cNumberOfSubStrings;
  v8 = RegisterEventSourceA(0, "RemoteAccess");
  if ( v8 )
  {
    ReportEventA(v8, v5, 0, dwMessageId, 0, wNumStrings, 0, (LPCSTR *)plpwsSubStrings, 0);
    DeregisterEventSource(v8);
  }
}

```

## disassembly

```asm
0x1800086d0  push    rbx
0x1800086d2  push    rbp
0x1800086d3  push    rsi
0x1800086d4  push    rdi
0x1800086d5  push    r14
0x1800086d7  sub     rsp, 50h
0x1800086db  mov     ebp, edx
0x1800086dd  mov     r14d, ecx
0x1800086e0  lea     rdx, SourceName; "RemoteAccess"
0x1800086e7  xor     ecx, ecx; lpUNCServerName
0x1800086e9  mov     rdi, r9
0x1800086ec  mov     esi, r8d
0x1800086ef  call    cs:__imp_RegisterEventSourceA
0x1800086f5  mov     rbx, rax
0x1800086f8  xor     eax, eax
0x1800086fa  test    rbx, rbx
0x1800086fd  jz      short loc_180008733
0x1800086ff  mov     [rsp+78h+lpRawData], rax; lpRawData
0x180008704  xor     r8d, r8d; wCategory
0x180008707  mov     [rsp+78h+lpStrings], rdi; lpStrings
0x18000870c  movzx   edx, r14w; wType
0x180008710  mov     [rsp+78h+dwDataSize], eax; dwDataSize
0x180008714  mov     r9d, ebp; dwEventID
0x180008717  mov     [rsp+78h+wNumStrings], si; wNumStrings
0x18000871c  mov     rcx, rbx; hEventLog
0x18000871f  mov     [rsp+78h+lpUserSid], rax; lpUserSid
0x180008724  call    cs:__imp_ReportEventA
0x18000872a  mov     rcx, rbx; hEventLog
0x18000872d  call    cs:__imp_DeregisterEventSource
0x180008733  add     rsp, 50h
0x180008737  pop     r14
0x180008739  pop     rdi
0x18000873a  pop     rsi
0x18000873b  pop     rbp
0x18000873c  pop     rbx
0x18000873d  retn
```
