# EvtLog_LogErrorWithHresult(ulong,long)

- ea: `0x180039540`
- end: `0x18003960c`
- name: `?EvtLog_LogErrorWithHresult@@YAXKJ@Z`
- size: `204`
- prototype: `void __fastcall(DWORD dwEventID, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d9e0`
- `0x180023e18`
- `0x180025520`
- `0x180036370`

## callees

- `0x180016ae8`
- `0x180039540`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800395db`
- `ADVAPI32!RegisterEventSourceW` at `0x18003956e`
- `ADVAPI32!RegisterEventSourceW` at `0x18003956e`
- `ADVAPI32!DeregisterEventSource` at `0x1800395e4`
- `ADVAPI32!DeregisterEventSource` at `0x1800395e4`
- `ADVAPI32!ReportEventW` at `0x1800395d1`
- `ADVAPI32!ReportEventW` at `0x1800395d1`

## string_xrefs

- `0x180039565`: `SecurityCenter`

## pseudocode

```c
void __fastcall EvtLog_LogErrorWithHresult(DWORD dwEventID, unsigned int a2)
{
  HANDLE v4; // rbx
  LPCWSTR Strings; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int16 v6[12]; // [rsp+58h] [rbp-30h] BYREF

  v4 = RegisterEventSourceW(0, L"SecurityCenter");
  if ( v4 )
  {
    if ( (int)StringCchPrintfW(v6, 9u, L"%08x", a2) >= 0 )
    {
      Strings = v6;
      if ( !ReportEventW(v4, 1u, 0, dwEventID, 0, 1u, 0, &Strings, 0) )
        GetLastError();
    }
    DeregisterEventSource(v4);
  }
}

```

## disassembly

```asm
0x180039540  mov     [rsp+arg_10], rbx
0x180039545  mov     [rsp+arg_18], rsi
0x18003954a  push    rdi
0x18003954b  sub     rsp, 80h
0x180039552  mov     rax, cs:__security_cookie
0x180039559  xor     rax, rsp
0x18003955c  mov     [rsp+88h+var_18], rax
0x180039561  mov     edi, edx
0x180039563  mov     esi, ecx
0x180039565  lea     rdx, SourceName; "SecurityCenter"
0x18003956c  xor     ecx, ecx; lpUNCServerName
0x18003956e  call    cs:__imp_RegisterEventSourceW
0x180039574  mov     rbx, rax
0x180039577  test    rax, rax
0x18003957a  jz      short loc_1800395EA
0x18003957c  mov     r9d, edi
0x18003957f  lea     r8, a08x; "%08x"
0x180039586  mov     edx, 9; unsigned __int64
0x18003958b  lea     rcx, [rsp+88h+var_30]; unsigned __int16 *
0x180039590  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039595  test    eax, eax
0x180039597  js      short loc_1800395E1
0x180039599  xor     r8d, r8d; wCategory
0x18003959c  lea     rax, [rsp+88h+var_30]
0x1800395a1  mov     [rsp+88h+lpRawData], r8; lpRawData
0x1800395a6  mov     ecx, 1
0x1800395ab  mov     [rsp+88h+Strings], rax
0x1800395b0  mov     edx, ecx; wType
0x1800395b2  lea     rax, [rsp+88h+Strings]
0x1800395b7  mov     r9d, esi; dwEventID
0x1800395ba  mov     [rsp+88h+lpStrings], rax; lpStrings
0x1800395bf  mov     [rsp+88h+dwDataSize], r8d; dwDataSize
0x1800395c4  mov     [rsp+88h+wNumStrings], cx; wNumStrings
0x1800395c9  mov     rcx, rbx; hEventLog
0x1800395cc  mov     [rsp+88h+lpUserSid], r8; lpUserSid
0x1800395d1  call    cs:__imp_ReportEventW
0x1800395d7  test    eax, eax
0x1800395d9  jnz     short loc_1800395E1
0x1800395db  call    cs:__imp_GetLastError
0x1800395e1  mov     rcx, rbx; hEventLog
0x1800395e4  call    cs:__imp_DeregisterEventSource
0x1800395ea  mov     rcx, [rsp+88h+var_18]
0x1800395ef  xor     rcx, rsp; StackCookie
0x1800395f2  call    __security_check_cookie
0x1800395f7  lea     r11, [rsp+88h+var_8]
0x1800395ff  mov     rbx, [r11+20h]
0x180039603  mov     rsi, [r11+28h]
0x180039607  mov     rsp, r11
0x18003960a  pop     rdi
0x18003960b  retn
```
