# LogEventW(x,x,x,x)

- ea: `0x100091a0`
- end: `0x100091df`
- name: `_LogEventW@16`
- size: `63`
- prototype: `void __stdcall(DWORD wEventType, DWORD dwMessageId, DWORD cNumberOfSubStrings, LPWSTR *plpwsSubStrings)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100091a0`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x100091af`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x100091af`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x100091cc`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x100091cc`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x100091d3`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x100091d3`

## string_xrefs

- `0x100091a7`: `RemoteAccess`

## pseudocode

```c
void __stdcall LogEventW(DWORD wEventType, DWORD dwMessageId, DWORD cNumberOfSubStrings, LPWSTR *plpwsSubStrings)
{
  HANDLE v4; // eax
  void *v5; // esi

  v4 = RegisterEventSourceW(0, L"RemoteAccess");
  v5 = v4;
  if ( v4 )
  {
    ReportEventW(v4, wEventType, 0, dwMessageId, 0, cNumberOfSubStrings, 0, (LPCWSTR *)plpwsSubStrings, 0);
    DeregisterEventSource(v5);
  }
}

```

## disassembly

```asm
0x100091a0  mov     edi, edi
0x100091a2  push    ebp
0x100091a3  mov     ebp, esp
0x100091a5  push    esi
0x100091a6  push    edi
0x100091a7  push    offset aRemoteaccess; "RemoteAccess"
0x100091ac  xor     edi, edi
0x100091ae  push    edi; lpUNCServerName
0x100091af  call    ds:__imp__RegisterEventSourceW@8; RegisterEventSourceW(x,x)
0x100091b5  mov     esi, eax
0x100091b7  test    esi, esi
0x100091b9  jz      short loc_100091D9
0x100091bb  push    edi; lpRawData
0x100091bc  push    [ebp+plpwsSubStrings]; lpStrings
0x100091bf  push    edi; dwDataSize
0x100091c0  push    [ebp+cNumberOfSubStrings]; wNumStrings
0x100091c3  push    edi; lpUserSid
0x100091c4  push    [ebp+dwMessageId]; dwEventID
0x100091c7  push    edi; wCategory
0x100091c8  push    [ebp+wEventType]; wType
0x100091cb  push    esi; hEventLog
0x100091cc  call    ds:__imp__ReportEventW@36; ReportEventW(x,x,x,x,x,x,x,x,x)
0x100091d2  push    esi; hEventLog
0x100091d3  call    ds:__imp__DeregisterEventSource@4; DeregisterEventSource(x)
0x100091d9  pop     edi
0x100091da  pop     esi
0x100091db  pop     ebp
0x100091dc  retn    10h
```
