# LogErrorA(x,x,x,x)

- ea: `0x10008a50`
- end: `0x10008aa0`
- name: `_LogErrorA@16`
- size: `80`
- prototype: `void __stdcall(DWORD dwMessageId, DWORD cNumberOfSubStrings, LPSTR *plpwsSubStrings, DWORD dwErrorCode)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10008a50`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventA` at `0x10008a8d`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventA` at `0x10008a8d`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x10008a94`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x10008a94`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceA` at `0x10008a5f`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceA` at `0x10008a5f`

## string_xrefs

- `0x10008a57`: `RemoteAccess`

## pseudocode

```c
void __stdcall LogErrorA(DWORD dwMessageId, DWORD cNumberOfSubStrings, LPSTR *plpwsSubStrings, DWORD dwErrorCode)
{
  HANDLE v4; // esi

  v4 = RegisterEventSourceA(0, "RemoteAccess");
  if ( v4 )
  {
    if ( dwErrorCode )
      ReportEventA(v4, 1u, 0, dwMessageId, 0, cNumberOfSubStrings, 4u, (LPCSTR *)plpwsSubStrings, &dwErrorCode);
    else
      ReportEventA(v4, 1u, 0, dwMessageId, 0, cNumberOfSubStrings, 0, (LPCSTR *)plpwsSubStrings, 0);
    DeregisterEventSource(v4);
  }
}

```

## disassembly

```asm
0x10008a50  mov     edi, edi
0x10008a52  push    ebp
0x10008a53  mov     ebp, esp
0x10008a55  push    esi
0x10008a56  push    edi
0x10008a57  push    offset SourceName; "RemoteAccess"
0x10008a5c  xor     edi, edi
0x10008a5e  push    edi; lpUNCServerName
0x10008a5f  call    ds:__imp__RegisterEventSourceA@8; RegisterEventSourceA(x,x)
0x10008a65  mov     esi, eax
0x10008a67  test    esi, esi
0x10008a69  jz      short loc_10008A9A
0x10008a6b  movzx   eax, word ptr [ebp+cNumberOfSubStrings]
0x10008a6f  cmp     [ebp+dwErrorCode], edi
0x10008a72  jnz     short loc_10008A7B
0x10008a74  push    edi
0x10008a75  push    [ebp+plpwsSubStrings]
0x10008a78  push    edi
0x10008a79  jmp     short loc_10008A84
0x10008a7b  lea     ecx, [ebp+dwErrorCode]
0x10008a7e  push    ecx; lpRawData
0x10008a7f  push    [ebp+plpwsSubStrings]; lpStrings
0x10008a82  push    4; dwDataSize
0x10008a84  push    eax; wNumStrings
0x10008a85  push    edi; lpUserSid
0x10008a86  push    [ebp+dwMessageId]; dwEventID
0x10008a89  push    edi; wCategory
0x10008a8a  push    1; wType
0x10008a8c  push    esi; hEventLog
0x10008a8d  call    ds:__imp__ReportEventA@36; ReportEventA(x,x,x,x,x,x,x,x,x)
0x10008a93  push    esi; hEventLog
0x10008a94  call    ds:__imp__DeregisterEventSource@4; DeregisterEventSource(x)
0x10008a9a  pop     edi
0x10008a9b  pop     esi
0x10008a9c  pop     ebp
0x10008a9d  retn    10h
```
