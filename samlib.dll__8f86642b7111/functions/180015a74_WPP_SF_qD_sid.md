# WPP_SF_qD_sid_

- ea: `0x180015a74`
- end: `0x180015b3b`
- name: `WPP_SF_qD_sid_`
- size: `199`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char, PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a80`

## callees

- `0x180015a74`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015b25`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015b25`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015a9b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015abf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015a9b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180015abf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015aa8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015aa8`

## pseudocode

```c
ULONG WPP_SF_qD_sid_(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, ...)
{
  char *v3; // rbx
  DWORD LengthSid; // edi
  __int64 v7; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v9; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  char *pSid; // [rsp+98h] [rbp+30h]
  va_list va2; // [rsp+A0h] [rbp+38h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v7 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v9 = va_arg(va2, _QWORD);
  pSid = va_arg(va2, char *);
  v3 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(v3);
  }
  else
  {
    LengthSid = 5;
    if ( !v3 )
    {
LABEL_6:
      v3 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids,
               0x1Cu,
               va,
               8,
               va1,
               4,
               v3,
               LengthSid,
               0);
    }
  }
  if ( !IsValidSid(v3) )
    goto LABEL_6;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids,
           0x1Cu,
           va,
           8,
           va1,
           4,
           v3,
           LengthSid,
           0);
}

```

## disassembly

```asm
0x180015a74  mov     [rsp+arg_0], rbx
0x180015a79  mov     [rsp+arg_8], rsi
0x180015a7e  mov     [rsp+arg_18], r9
0x180015a83  push    rdi
0x180015a84  sub     rsp, 60h
0x180015a88  mov     rbx, [rsp+68h+pSid]
0x180015a90  mov     rsi, rcx
0x180015a93  test    rbx, rbx
0x180015a96  jz      short loc_180015AB2
0x180015a98  mov     rcx, rbx; pSid
0x180015a9b  call    cs:__imp_IsValidSid
0x180015aa1  test    eax, eax
0x180015aa3  jz      short loc_180015AB2
0x180015aa5  mov     rcx, rbx; pSid
0x180015aa8  call    cs:__imp_GetLengthSid
0x180015aae  mov     edi, eax
0x180015ab0  jmp     short loc_180015ABC
0x180015ab2  mov     edi, 5
0x180015ab7  test    rbx, rbx
0x180015aba  jz      short loc_180015AC9
0x180015abc  mov     rcx, rbx; pSid
0x180015abf  call    cs:__imp_IsValidSid
0x180015ac5  test    eax, eax
0x180015ac7  jnz     short loc_180015AD0
0x180015ac9  lea     rbx, aNull; "NULL"
0x180015ad0  mov     [rsp+68h+var_18], 0
0x180015ad9  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids; MessageGuid
0x180015ae0  mov     eax, edi
0x180015ae2  mov     r9d, 1Ch; MessageNumber
0x180015ae8  mov     [rsp+68h+var_20], rax
0x180015aed  mov     rcx, rsi; LoggerHandle
0x180015af0  mov     [rsp+68h+var_28], rbx
0x180015af5  lea     rax, [rsp+68h+arg_20]
0x180015afd  mov     [rsp+68h+var_30], 4
0x180015b06  mov     [rsp+68h+var_38], rax
0x180015b0b  lea     edx, [r9+0Fh]; MessageFlags
0x180015b0f  lea     rax, [rsp+68h+arg_18]
0x180015b17  mov     [rsp+68h+var_40], 8
0x180015b20  mov     [rsp+68h+var_48], rax
0x180015b25  call    cs:__imp_TraceMessage
0x180015b2b  mov     rbx, [rsp+68h+arg_0]
0x180015b30  mov     rsi, [rsp+68h+arg_8]
0x180015b35  add     rsp, 60h
0x180015b39  pop     rdi
0x180015b3a  retn
```
