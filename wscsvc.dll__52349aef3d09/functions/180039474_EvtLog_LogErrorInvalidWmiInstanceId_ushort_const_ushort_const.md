# EvtLog_LogErrorInvalidWmiInstanceId(ushort const *,ushort const *)

- ea: `0x180039474`
- end: `0x180039538`
- name: `?EvtLog_LogErrorInvalidWmiInstanceId@@YAXPEBG0@Z`
- size: `196`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180036adc`

## callees

- `0x180039474`

## import_xrefs

- `ADVAPI32!RegisterEventSourceW` at `0x180039492`
- `ADVAPI32!RegisterEventSourceW` at `0x180039492`
- `ADVAPI32!DeregisterEventSource` at `0x180039522`
- `ADVAPI32!DeregisterEventSource` at `0x180039522`
- `ADVAPI32!ReportEventW` at `0x180039519`
- `ADVAPI32!ReportEventW` at `0x180039519`

## string_xrefs

- `0x180039489`: `SecurityCenter`

## pseudocode

```c
void __fastcall EvtLog_LogErrorInvalidWmiInstanceId(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HANDLE v4; // rbx
  LPCWSTR lpStrings[3]; // [rsp+50h] [rbp-18h] BYREF
  LPCWSTR Strings; // [rsp+80h] [rbp+18h] BYREF

  v4 = RegisterEventSourceW(0, L"SecurityCenter");
  if ( v4 )
  {
    if ( a2 )
    {
      lpStrings[0] = a2;
      lpStrings[1] = a1;
      ReportEventW(v4, 4u, 0, 0x4000000Bu, 0, 2u, 0, lpStrings, 0);
    }
    else
    {
      Strings = a1;
      ReportEventW(v4, 1u, 0, 0xC0000007, 0, 1u, 0, &Strings, 0);
    }
    DeregisterEventSource(v4);
  }
}

```

## disassembly

```asm
0x180039474  mov     [rsp+arg_0], rbx
0x180039479  mov     [rsp+arg_8], rsi
0x18003947e  push    rdi
0x18003947f  sub     rsp, 60h
0x180039483  mov     rdi, rdx
0x180039486  mov     rsi, rcx
0x180039489  lea     rdx, SourceName; "SecurityCenter"
0x180039490  xor     ecx, ecx; lpUNCServerName
0x180039492  call    cs:__imp_RegisterEventSourceW
0x180039498  xor     r9d, r9d
0x18003949b  mov     rbx, rax
0x18003949e  test    rax, rax
0x1800394a1  jz      loc_180039528
0x1800394a7  xor     r8d, r8d; wCategory
0x1800394aa  mov     [rsp+68h+lpRawData], r9; lpRawData
0x1800394af  test    rdi, rdi
0x1800394b2  jz      short loc_1800394E5
0x1800394b4  lea     rax, [rsp+68h+var_18]
0x1800394b9  mov     [rsp+68h+var_18], rdi
0x1800394be  mov     [rsp+68h+lpStrings], rax
0x1800394c3  lea     edx, [r9+4]
0x1800394c7  mov     [rsp+68h+dwDataSize], r9d
0x1800394cc  mov     [rsp+68h+wNumStrings], 2
0x1800394d3  mov     [rsp+68h+lpUserSid], r9
0x1800394d8  mov     r9d, 4000000Bh
0x1800394de  mov     [rsp+68h+var_10], rsi
0x1800394e3  jmp     short loc_180039516
0x1800394e5  mov     ecx, 1
0x1800394ea  mov     [rsp+68h+Strings], rsi
0x1800394f2  lea     rax, [rsp+68h+Strings]
0x1800394fa  mov     edx, ecx; wType
0x1800394fc  mov     [rsp+68h+lpStrings], rax; lpStrings
0x180039501  mov     [rsp+68h+dwDataSize], r9d; dwDataSize
0x180039506  mov     [rsp+68h+wNumStrings], cx; wNumStrings
0x18003950b  mov     [rsp+68h+lpUserSid], r9; lpUserSid
0x180039510  mov     r9d, 0C0000007h; dwEventID
0x180039516  mov     rcx, rbx; hEventLog
0x180039519  call    cs:__imp_ReportEventW
0x18003951f  mov     rcx, rbx; hEventLog
0x180039522  call    cs:__imp_DeregisterEventSource
0x180039528  mov     rbx, [rsp+68h+arg_0]
0x18003952d  mov     rsi, [rsp+68h+arg_8]
0x180039532  add     rsp, 60h
0x180039536  pop     rdi
0x180039537  retn
```
