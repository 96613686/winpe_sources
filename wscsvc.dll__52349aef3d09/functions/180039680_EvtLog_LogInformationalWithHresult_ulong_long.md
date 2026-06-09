# EvtLog_LogInformationalWithHresult(ulong,long)

- ea: `0x180039680`
- end: `0x180039743`
- name: `?EvtLog_LogInformationalWithHresult@@YAXKJ@Z`
- size: `195`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023e18`

## callees

- `0x180016ae8`
- `0x180039680`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039716`
- `ADVAPI32!RegisterEventSourceW` at `0x1800396a7`
- `ADVAPI32!RegisterEventSourceW` at `0x1800396a7`
- `ADVAPI32!DeregisterEventSource` at `0x18003971f`
- `ADVAPI32!DeregisterEventSource` at `0x18003971f`
- `ADVAPI32!ReportEventW` at `0x18003970c`
- `ADVAPI32!ReportEventW` at `0x18003970c`

## string_xrefs

- `0x1800396a0`: `SecurityCenter`

## pseudocode

```c
void __fastcall EvtLog_LogInformationalWithHresult(__int64 a1, unsigned int a2)
{
  HANDLE v3; // rbx
  LPCWSTR Strings; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int16 v5[12]; // [rsp+58h] [rbp-30h] BYREF

  v3 = RegisterEventSourceW(0, L"SecurityCenter");
  if ( v3 )
  {
    if ( (int)StringCchPrintfW(v5, 9u, L"%08x", a2) >= 0 )
    {
      Strings = v5;
      if ( !ReportEventW(v3, 4u, 0, 0xC0000011, 0, 1u, 0, &Strings, 0) )
        GetLastError();
    }
    DeregisterEventSource(v3);
  }
}

```

## disassembly

```asm
0x180039680  mov     [rsp+arg_0], rbx
0x180039685  push    rdi
0x180039686  sub     rsp, 80h
0x18003968d  mov     rax, cs:__security_cookie
0x180039694  xor     rax, rsp
0x180039697  mov     [rsp+88h+var_18], rax
0x18003969c  mov     edi, edx
0x18003969e  xor     ecx, ecx; lpUNCServerName
0x1800396a0  lea     rdx, SourceName; "SecurityCenter"
0x1800396a7  call    cs:__imp_RegisterEventSourceW
0x1800396ad  mov     rbx, rax
0x1800396b0  test    rax, rax
0x1800396b3  jz      short loc_180039725
0x1800396b5  mov     r9d, edi
0x1800396b8  lea     r8, a08x; "%08x"
0x1800396bf  mov     edx, 9; unsigned __int64
0x1800396c4  lea     rcx, [rsp+88h+var_30]; unsigned __int16 *
0x1800396c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800396ce  test    eax, eax
0x1800396d0  js      short loc_18003971C
0x1800396d2  xor     r8d, r8d; wCategory
0x1800396d5  lea     rax, [rsp+88h+var_30]
0x1800396da  mov     [rsp+88h+lpRawData], r8; lpRawData
0x1800396df  mov     r9d, 0C0000011h; dwEventID
0x1800396e5  mov     [rsp+88h+Strings], rax
0x1800396ea  mov     rcx, rbx; hEventLog
0x1800396ed  lea     rax, [rsp+88h+Strings]
0x1800396f2  mov     [rsp+88h+lpStrings], rax; lpStrings
0x1800396f7  lea     edx, [r8+4]; wType
0x1800396fb  mov     [rsp+88h+dwDataSize], r8d; dwDataSize
0x180039700  mov     [rsp+88h+wNumStrings], 1; wNumStrings
0x180039707  mov     [rsp+88h+lpUserSid], r8; lpUserSid
0x18003970c  call    cs:__imp_ReportEventW
0x180039712  test    eax, eax
0x180039714  jnz     short loc_18003971C
0x180039716  call    cs:__imp_GetLastError
0x18003971c  mov     rcx, rbx; hEventLog
0x18003971f  call    cs:__imp_DeregisterEventSource
0x180039725  mov     rcx, [rsp+88h+var_18]
0x18003972a  xor     rcx, rsp; StackCookie
0x18003972d  call    __security_check_cookie
0x180039732  mov     rbx, [rsp+88h+arg_0]
0x18003973a  add     rsp, 80h
0x180039741  pop     rdi
0x180039742  retn
```
