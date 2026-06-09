# WPP_SF_q_sid_

- ea: `0x180014f80`
- end: `0x180015024`
- name: `WPP_SF_q_sid_`
- size: `164`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c650`
- `0x1800110c0`
- `0x1800112c0`

## callees

- `0x180014f80`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015015`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015015`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014fa3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014fc7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014fa3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014fc7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014fb0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014fb0`

## pseudocode

```c
ULONG WPP_SF_q_sid_(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, ...)
{
  char *v3; // rbx
  DWORD LengthSid; // edi
  __int64 v8; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  char *pSid; // [rsp+A0h] [rbp+28h]
  va_list va1; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, _QWORD);
  pSid = va_arg(va1, char *);
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
               &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
               a2,
               va,
               8,
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
           &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
           a2,
           va,
           8,
           v3,
           LengthSid,
           0);
}

```

## disassembly

```asm
0x180014f80  mov     [rsp+arg_18], r9
0x180014f85  push    rbx
0x180014f86  push    rbp
0x180014f87  push    rsi
0x180014f88  push    rdi
0x180014f89  sub     rsp, 58h
0x180014f8d  mov     rbx, [rsp+78h+pSid]
0x180014f95  mov     rbp, rcx
0x180014f98  movzx   esi, dx
0x180014f9b  test    rbx, rbx
0x180014f9e  jz      short loc_180014FBA
0x180014fa0  mov     rcx, rbx; pSid
0x180014fa3  call    cs:__imp_IsValidSid
0x180014fa9  test    eax, eax
0x180014fab  jz      short loc_180014FBA
0x180014fad  mov     rcx, rbx; pSid
0x180014fb0  call    cs:__imp_GetLengthSid
0x180014fb6  mov     edi, eax
0x180014fb8  jmp     short loc_180014FC4
0x180014fba  mov     edi, 5
0x180014fbf  test    rbx, rbx
0x180014fc2  jz      short loc_180014FD1
0x180014fc4  mov     rcx, rbx; pSid
0x180014fc7  call    cs:__imp_IsValidSid
0x180014fcd  test    eax, eax
0x180014fcf  jnz     short loc_180014FD8
0x180014fd1  lea     rbx, aNull; "NULL"
0x180014fd8  mov     [rsp+78h+var_38], 0
0x180014fe1  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids; MessageGuid
0x180014fe8  mov     eax, edi
0x180014fea  mov     r9d, esi; MessageNumber
0x180014fed  mov     [rsp+78h+var_40], rax
0x180014ff2  mov     edx, 2Bh ; '+'; MessageFlags
0x180014ff7  mov     [rsp+78h+var_48], rbx
0x180014ffc  lea     rax, [rsp+78h+arg_18]
0x180015004  mov     [rsp+78h+var_50], 8
0x18001500d  mov     rcx, rbp; LoggerHandle
0x180015010  mov     [rsp+78h+var_58], rax
0x180015015  call    cs:__imp_TraceMessage
0x18001501b  add     rsp, 58h
0x18001501f  pop     rdi
0x180015020  pop     rsi
0x180015021  pop     rbp
0x180015022  pop     rbx
0x180015023  retn
```
