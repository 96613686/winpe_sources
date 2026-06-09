# LogErrorW(x,x,x,x)

- ea: `0x10009140`
- end: `0x10009190`
- name: `_LogErrorW@16`
- size: `80`
- prototype: `void __stdcall(DWORD dwMessageId, DWORD cNumberOfSubStrings, LPWSTR *plpwsSubStrings, DWORD dwErrorCode)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10009140`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x1000914f`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x1000914f`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x1000917d`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x1000917d`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x10009184`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x10009184`

## string_xrefs

- `0x10009147`: `RemoteAccess`

## pseudocode

```c
void __stdcall LogErrorW(DWORD dwMessageId, DWORD cNumberOfSubStrings, LPWSTR *plpwsSubStrings, DWORD dwErrorCode)
{
  HANDLE v4; // esi

  v4 = RegisterEventSourceW(0, L"RemoteAccess");
  if ( v4 )
  {
    if ( dwErrorCode )
      ReportEventW(v4, 1u, 0, dwMessageId, 0, cNumberOfSubStrings, 4u, (LPCWSTR *)plpwsSubStrings, &dwErrorCode);
    else
      ReportEventW(v4, 1u, 0, dwMessageId, 0, cNumberOfSubStrings, 0, (LPCWSTR *)plpwsSubStrings, 0);
    DeregisterEventSource(v4);
  }
}

```

## disassembly

```asm
0x10009140  mov     edi, edi
0x10009142  push    ebp
0x10009143  mov     ebp, esp
0x10009145  push    esi
0x10009146  push    edi
0x10009147  push    offset aRemoteaccess; "RemoteAccess"
0x1000914c  xor     edi, edi
0x1000914e  push    edi; lpUNCServerName
0x1000914f  call    ds:__imp__RegisterEventSourceW@8; RegisterEventSourceW(x,x)
0x10009155  mov     esi, eax
0x10009157  test    esi, esi
0x10009159  jz      short loc_1000918A
0x1000915b  movzx   eax, word ptr [ebp+cNumberOfSubStrings]
0x1000915f  cmp     [ebp+dwErrorCode], edi
0x10009162  jnz     short loc_1000916B
0x10009164  push    edi
0x10009165  push    [ebp+plpwsSubStrings]
0x10009168  push    edi
0x10009169  jmp     short loc_10009174
0x1000916b  lea     ecx, [ebp+dwErrorCode]
0x1000916e  push    ecx; lpRawData
0x1000916f  push    [ebp+plpwsSubStrings]; lpStrings
0x10009172  push    4; dwDataSize
0x10009174  push    eax; wNumStrings
0x10009175  push    edi; lpUserSid
0x10009176  push    [ebp+dwMessageId]; dwEventID
0x10009179  push    edi; wCategory
0x1000917a  push    1; wType
0x1000917c  push    esi; hEventLog
0x1000917d  call    ds:__imp__ReportEventW@36; ReportEventW(x,x,x,x,x,x,x,x,x)
0x10009183  push    esi; hEventLog
0x10009184  call    ds:__imp__DeregisterEventSource@4; DeregisterEventSource(x)
0x1000918a  pop     edi
0x1000918b  pop     esi
0x1000918c  pop     ebp
0x1000918d  retn    10h
```
