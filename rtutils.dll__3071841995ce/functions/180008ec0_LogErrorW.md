# LogErrorW

- ea: `0x180008ec0`
- end: `0x180008f4e`
- name: `LogErrorW`
- size: `142`
- prototype: `void __stdcall(DWORD dwMessageId, DWORD cNumberOfSubStrings, LPWSTR *plpwsSubStrings, DWORD dwErrorCode)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008ec0`

## import_xrefs

- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180008edd`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x180008edd`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180008f36`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180008f36`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180008f3f`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180008f3f`

## string_xrefs

- `0x180008ed1`: `RemoteAccess`

## pseudocode

```c
void __stdcall LogErrorW(DWORD dwMessageId, DWORD cNumberOfSubStrings, LPWSTR *plpwsSubStrings, DWORD dwErrorCode)
{
  WORD wNumStrings; // si
  HANDLE v7; // rbx
  DWORD RawData; // [rsp+98h] [rbp+20h] BYREF

  RawData = dwErrorCode;
  wNumStrings = cNumberOfSubStrings;
  v7 = RegisterEventSourceW(0, L"RemoteAccess");
  if ( v7 )
  {
    if ( RawData )
      ReportEventW(v7, 1u, 0, dwMessageId, 0, wNumStrings, 4u, (LPCWSTR *)plpwsSubStrings, &RawData);
    else
      ReportEventW(v7, 1u, 0, dwMessageId, 0, wNumStrings, 0, (LPCWSTR *)plpwsSubStrings, 0);
    DeregisterEventSource(v7);
  }
}

```

## disassembly

```asm
0x180008ec0  mov     [rsp+RawData], r9d
0x180008ec5  push    rbx
0x180008ec6  push    rbp
0x180008ec7  push    rsi
0x180008ec8  push    rdi
0x180008ec9  sub     rsp, 58h
0x180008ecd  mov     esi, edx
0x180008ecf  mov     ebp, ecx
0x180008ed1  lea     rdx, aRemoteaccess; "RemoteAccess"
0x180008ed8  xor     ecx, ecx; lpUNCServerName
0x180008eda  mov     rdi, r8
0x180008edd  call    cs:__imp_RegisterEventSourceW
0x180008ee3  xor     ecx, ecx
0x180008ee5  mov     rbx, rax
0x180008ee8  test    rax, rax
0x180008eeb  jz      short loc_180008F45
0x180008eed  xor     r8d, r8d; wCategory
0x180008ef0  lea     edx, [rcx+1]; wType
0x180008ef3  mov     r9d, ebp; dwEventID
0x180008ef6  cmp     [rsp+78h+RawData], ecx
0x180008efd  jnz     short loc_180008F0F
0x180008eff  mov     [rsp+78h+lpRawData], rcx
0x180008f04  mov     [rsp+78h+lpStrings], rdi
0x180008f09  mov     [rsp+78h+dwDataSize], ecx
0x180008f0d  jmp     short loc_180008F29
0x180008f0f  lea     rax, [rsp+78h+RawData]
0x180008f17  mov     [rsp+78h+lpRawData], rax; lpRawData
0x180008f1c  mov     [rsp+78h+lpStrings], rdi; lpStrings
0x180008f21  mov     [rsp+78h+dwDataSize], 4; dwDataSize
0x180008f29  mov     [rsp+78h+wNumStrings], si; wNumStrings
0x180008f2e  mov     [rsp+78h+lpUserSid], rcx; lpUserSid
0x180008f33  mov     rcx, rbx; hEventLog
0x180008f36  call    cs:__imp_ReportEventW
0x180008f3c  mov     rcx, rbx; hEventLog
0x180008f3f  call    cs:__imp_DeregisterEventSource
0x180008f45  add     rsp, 58h
0x180008f49  pop     rdi
0x180008f4a  pop     rsi
0x180008f4b  pop     rbp
0x180008f4c  pop     rbx
0x180008f4d  retn
```
