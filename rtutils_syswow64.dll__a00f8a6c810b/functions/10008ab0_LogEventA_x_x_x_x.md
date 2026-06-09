# LogEventA(x,x,x,x)

- ea: `0x10008ab0`
- end: `0x10008aef`
- name: `_LogEventA@16`
- size: `63`
- prototype: `void __stdcall(DWORD wEventType, DWORD dwMessageId, DWORD cNumberOfSubStrings, LPSTR *plpwsSubStrings)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10008ab0`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventA` at `0x10008adc`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventA` at `0x10008adc`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x10008ae3`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x10008ae3`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceA` at `0x10008abf`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceA` at `0x10008abf`

## string_xrefs

- `0x10008ab7`: `RemoteAccess`

## pseudocode

```c
void __stdcall LogEventA(DWORD wEventType, DWORD dwMessageId, DWORD cNumberOfSubStrings, LPSTR *plpwsSubStrings)
{
  HANDLE v4; // eax
  void *v5; // esi

  v4 = RegisterEventSourceA(0, "RemoteAccess");
  v5 = v4;
  if ( v4 )
  {
    ReportEventA(v4, wEventType, 0, dwMessageId, 0, cNumberOfSubStrings, 0, (LPCSTR *)plpwsSubStrings, 0);
    DeregisterEventSource(v5);
  }
}

```

## disassembly

```asm
0x10008ab0  mov     edi, edi
0x10008ab2  push    ebp
0x10008ab3  mov     ebp, esp
0x10008ab5  push    esi
0x10008ab6  push    edi
0x10008ab7  push    offset SourceName; "RemoteAccess"
0x10008abc  xor     edi, edi
0x10008abe  push    edi; lpUNCServerName
0x10008abf  call    ds:__imp__RegisterEventSourceA@8; RegisterEventSourceA(x,x)
0x10008ac5  mov     esi, eax
0x10008ac7  test    esi, esi
0x10008ac9  jz      short loc_10008AE9
0x10008acb  push    edi; lpRawData
0x10008acc  push    [ebp+plpwsSubStrings]; lpStrings
0x10008acf  push    edi; dwDataSize
0x10008ad0  push    [ebp+cNumberOfSubStrings]; wNumStrings
0x10008ad3  push    edi; lpUserSid
0x10008ad4  push    [ebp+dwMessageId]; dwEventID
0x10008ad7  push    edi; wCategory
0x10008ad8  push    [ebp+wEventType]; wType
0x10008adb  push    esi; hEventLog
0x10008adc  call    ds:__imp__ReportEventA@36; ReportEventA(x,x,x,x,x,x,x,x,x)
0x10008ae2  push    esi; hEventLog
0x10008ae3  call    ds:__imp__DeregisterEventSource@4; DeregisterEventSource(x)
0x10008ae9  pop     edi
0x10008aea  pop     esi
0x10008aeb  pop     ebp
0x10008aec  retn    10h
```
