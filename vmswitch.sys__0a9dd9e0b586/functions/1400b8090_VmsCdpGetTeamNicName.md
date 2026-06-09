# VmsCdpGetTeamNicName

- ea: `0x1400b8090`
- end: `0x1400b81ae`
- name: `VmsCdpGetTeamNicName`
- size: `286`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PUNICODE_STRING DestinationString)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140035058`
- `0x14003985c`
- `0x1400b6354`
- `0x14017899c`

## callees

- `0x140066bec`
- `0x1400b8090`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b80fd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b8115`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b8131`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b80fd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b8115`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400b8131`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b80e7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b817a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b80e7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b817a`

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
0x1400b8090  mov     [rsp+arg_10], rbx
0x1400b8095  mov     [rsp+arg_18], rsi
0x1400b809a  push    rdi
0x1400b809b  sub     rsp, 160h
0x1400b80a2  mov     rax, cs:__security_cookie
0x1400b80a9  xor     rax, rsp
0x1400b80ac  mov     [rsp+168h+var_18], rax
0x1400b80b4  mov     rdi, rdx
0x1400b80b7  mov     rsi, rcx
0x1400b80ba  xor     edx, edx; Val
0x1400b80bc  lea     rcx, [rsp+168h+var_118]; void *
0x1400b80c1  mov     r8d, 0FEh; Size
0x1400b80c7  call    memset
0x1400b80cc  lea     rax, [rsp+168h+var_118]
0x1400b80d1  mov     qword ptr [rsp+168h+SourceString.Length], 0FE0000h
0x1400b80da  lea     rdx, [rsp+168h+SourceString]; SourceString
0x1400b80df  mov     [rsp+168h+SourceString.Buffer], rax
0x1400b80e4  mov     rcx, rdi; DestinationString
0x1400b80e7  call    cs:__imp_RtlCopyUnicodeString
0x1400b80ee  nop     dword ptr [rax+rax+00h]
0x1400b80f3  lea     rdx, VmsTeamNicNamePrefix; Source
0x1400b80fa  mov     rcx, rdi; Destination
0x1400b80fd  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400b8104  nop     dword ptr [rax+rax+00h]
0x1400b8109  mov     ebx, eax
0x1400b810b  test    eax, eax
0x1400b810d  jnz     short loc_1400B8143
0x1400b810f  mov     rdx, rsi; Source
0x1400b8112  mov     rcx, rdi; Destination
0x1400b8115  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400b811c  nop     dword ptr [rax+rax+00h]
0x1400b8121  mov     ebx, eax
0x1400b8123  test    eax, eax
0x1400b8125  jnz     short loc_1400B8143
0x1400b8127  lea     rdx, VmsTeamNicNameSuffix; Source
0x1400b812e  mov     rcx, rdi; Destination
0x1400b8131  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400b8138  nop     dword ptr [rax+rax+00h]
0x1400b813d  mov     ebx, eax
0x1400b813f  test    eax, eax
0x1400b8141  jz      short loc_1400B8186
0x1400b8143  mov     rcx, cs:VmsIfrLog
0x1400b814a  lea     rax, WPP_7a8fadac4d893e575a01306db05fafbf_Traceguids
0x1400b8151  mov     [rsp+168h+var_138], ebx
0x1400b8155  mov     r9d, 1A6h
0x1400b815b  mov     [rsp+168h+var_140], rsi
0x1400b8160  mov     r8d, 14h
0x1400b8166  mov     dl, 2
0x1400b8168  mov     [rsp+168h+var_148], rax
0x1400b816d  call    WPP_RECORDER_SF_Zd
0x1400b8172  lea     rdx, [rsp+168h+SourceString]; SourceString
0x1400b8177  mov     rcx, rdi; DestinationString
0x1400b817a  call    cs:__imp_RtlCopyUnicodeString
0x1400b8181  nop     dword ptr [rax+rax+00h]
0x1400b8186  mov     eax, ebx
0x1400b8188  mov     rcx, [rsp+168h+var_18]
0x1400b8190  xor     rcx, rsp; StackCookie
0x1400b8193  call    __security_check_cookie
0x1400b8198  lea     r11, [rsp+168h+var_8]
0x1400b81a0  mov     rbx, [r11+20h]
0x1400b81a4  mov     rsi, [r11+28h]
0x1400b81a8  mov     rsp, r11
0x1400b81ab  pop     rdi
0x1400b81ac  retn
```
