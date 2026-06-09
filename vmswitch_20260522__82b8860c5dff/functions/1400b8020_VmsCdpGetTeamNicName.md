# VmsCdpGetTeamNicName

- ea: `0x1400b8020`
- end: `0x1400b813e`
- name: `VmsCdpGetTeamNicName`
- size: `286`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PUNICODE_STRING DestinationString)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140035058`
- `0x14003985c`
- `0x1400b62e4`
- `0x14017892c`

## callees

- `0x140066bec`
- `0x1400b8020`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b808d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b80a5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b80c1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b808d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b80a5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b80c1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b8077`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b810a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b8077`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b810a`

## pseudocode

```c
__int64 __fastcall VmsCdpGetTeamNicName(PCUNICODE_STRING Source, PUNICODE_STRING DestinationString)
{
  int v4; // edx
  unsigned int appended; // ebx
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-128h] BYREF
  _BYTE v8[256]; // [rsp+50h] [rbp-118h] BYREF

  memset(v8, 0, 0xFEu);
  *(_QWORD *)&SourceString.Length = 16646144;
  SourceString.Buffer = (wchar_t *)v8;
  RtlCopyUnicodeString(DestinationString, &SourceString);
  appended = RtlAppendUnicodeStringToString(DestinationString, &VmsTeamNicNamePrefix);
  if ( appended
    || (appended = RtlAppendUnicodeStringToString(DestinationString, Source)) != 0
    || (appended = RtlAppendUnicodeStringToString(DestinationString, &VmsTeamNicNameSuffix)) != 0 )
  {
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_Zd(
      VmsIfrLog,
      v4,
      20,
      422,
      (__int64)WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids,
      (__int64)Source,
      appended);
    RtlCopyUnicodeString(DestinationString, &SourceString);
  }
  return appended;
}

```

## disassembly

```asm
0x1400b8020  mov     [rsp+arg_10], rbx
0x1400b8025  mov     [rsp+arg_18], rsi
0x1400b802a  push    rdi
0x1400b802b  sub     rsp, 160h
0x1400b8032  mov     rax, cs:__security_cookie
0x1400b8039  xor     rax, rsp
0x1400b803c  mov     [rsp+168h+var_18], rax
0x1400b8044  mov     rdi, rdx
0x1400b8047  mov     rsi, rcx
0x1400b804a  xor     edx, edx; Val
0x1400b804c  lea     rcx, [rsp+168h+var_118]; void *
0x1400b8051  mov     r8d, 0FEh; Size
0x1400b8057  call    memset
0x1400b805c  lea     rax, [rsp+168h+var_118]
0x1400b8061  mov     qword ptr [rsp+168h+SourceString.Length], 0FE0000h
0x1400b806a  lea     rdx, [rsp+168h+SourceString]; SourceString
0x1400b806f  mov     [rsp+168h+SourceString.Buffer], rax
0x1400b8074  mov     rcx, rdi; DestinationString
0x1400b8077  call    cs:__imp_RtlCopyUnicodeString
0x1400b807e  nop     dword ptr [rax+rax+00h]
0x1400b8083  lea     rdx, VmsTeamNicNamePrefix; Source
0x1400b808a  mov     rcx, rdi; Destination
0x1400b808d  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400b8094  nop     dword ptr [rax+rax+00h]
0x1400b8099  mov     ebx, eax
0x1400b809b  test    eax, eax
0x1400b809d  jnz     short loc_1400B80D3
0x1400b809f  mov     rdx, rsi; Source
0x1400b80a2  mov     rcx, rdi; Destination
0x1400b80a5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400b80ac  nop     dword ptr [rax+rax+00h]
0x1400b80b1  mov     ebx, eax
0x1400b80b3  test    eax, eax
0x1400b80b5  jnz     short loc_1400B80D3
0x1400b80b7  lea     rdx, VmsTeamNicNameSuffix; Source
0x1400b80be  mov     rcx, rdi; Destination
0x1400b80c1  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400b80c8  nop     dword ptr [rax+rax+00h]
0x1400b80cd  mov     ebx, eax
0x1400b80cf  test    eax, eax
0x1400b80d1  jz      short loc_1400B8116
0x1400b80d3  mov     rcx, cs:VmsIfrLog
0x1400b80da  lea     rax, WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids
0x1400b80e1  mov     [rsp+168h+var_138], ebx
0x1400b80e5  mov     r9d, 1A6h
0x1400b80eb  mov     [rsp+168h+var_140], rsi
0x1400b80f0  mov     r8d, 14h
0x1400b80f6  mov     dl, 2
0x1400b80f8  mov     [rsp+168h+var_148], rax
0x1400b80fd  call    WPP_RECORDER_SF_Zd
0x1400b8102  lea     rdx, [rsp+168h+SourceString]; SourceString
0x1400b8107  mov     rcx, rdi; DestinationString
0x1400b810a  call    cs:__imp_RtlCopyUnicodeString
0x1400b8111  nop     dword ptr [rax+rax+00h]
0x1400b8116  mov     eax, ebx
0x1400b8118  mov     rcx, [rsp+168h+var_18]
0x1400b8120  xor     rcx, rsp; StackCookie
0x1400b8123  call    __security_check_cookie
0x1400b8128  lea     r11, [rsp+168h+var_8]
0x1400b8130  mov     rbx, [r11+20h]
0x1400b8134  mov     rsi, [r11+28h]
0x1400b8138  mov     rsp, r11
0x1400b813b  pop     rdi
0x1400b813c  retn
```
