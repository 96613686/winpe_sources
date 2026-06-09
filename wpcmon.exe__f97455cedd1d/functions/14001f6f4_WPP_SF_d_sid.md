# WPP_SF_d_sid_

- ea: `0x14001f6f4`
- end: `0x14001f798`
- name: `WPP_SF_d_sid_`
- size: `164`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001af50`
- `0x14001b1a0`

## callees

- `0x14001f6f4`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x14001f724`
- `ADVAPI32!GetLengthSid` at `0x14001f724`
- `ADVAPI32!IsValidSid` at `0x14001f717`
- `ADVAPI32!IsValidSid` at `0x14001f73b`
- `ADVAPI32!IsValidSid` at `0x14001f717`
- `ADVAPI32!IsValidSid` at `0x14001f73b`
- `ADVAPI32!TraceMessage` at `0x14001f789`
- `ADVAPI32!TraceMessage` at `0x14001f789`

## pseudocode

```c
ULONG __fastcall WPP_SF_d_sid_(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, int a4, char *pSid)
{
  char *v5; // rbx
  DWORD LengthSid; // edi
  int v10; // [rsp+98h] [rbp+20h] BYREF

  v10 = a4;
  v5 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(v5);
  }
  else
  {
    LengthSid = 5;
    if ( !v5 )
    {
LABEL_6:
      v5 = "NULL";
      return TraceMessage(
               LoggerHandle,
               0x2Bu,
               &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids,
               a2,
               &v10,
               4,
               v5,
               LengthSid,
               0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids,
           a2,
           &v10,
           4,
           v5,
           LengthSid,
           0);
}

```

## disassembly

```asm
0x14001f6f4  mov     [rsp+arg_18], r9d
0x14001f6f9  push    rbx
0x14001f6fa  push    rbp
0x14001f6fb  push    rsi
0x14001f6fc  push    rdi
0x14001f6fd  sub     rsp, 58h
0x14001f701  mov     rbx, [rsp+78h+pSid]
0x14001f709  mov     rbp, rcx
0x14001f70c  movzx   esi, dx
0x14001f70f  test    rbx, rbx
0x14001f712  jz      short loc_14001F72E
0x14001f714  mov     rcx, rbx; pSid
0x14001f717  call    cs:__imp_IsValidSid
0x14001f71d  test    eax, eax
0x14001f71f  jz      short loc_14001F72E
0x14001f721  mov     rcx, rbx; pSid
0x14001f724  call    cs:__imp_GetLengthSid
0x14001f72a  mov     edi, eax
0x14001f72c  jmp     short loc_14001F738
0x14001f72e  mov     edi, 5
0x14001f733  test    rbx, rbx
0x14001f736  jz      short loc_14001F745
0x14001f738  mov     rcx, rbx; pSid
0x14001f73b  call    cs:__imp_IsValidSid
0x14001f741  test    eax, eax
0x14001f743  jnz     short loc_14001F74C
0x14001f745  lea     rbx, aNull; "NULL"
0x14001f74c  mov     [rsp+78h+var_38], 0
0x14001f755  lea     r8, WPP_a6cd8b416fde3d696d6e4fad87c378e4_Traceguids; MessageGuid
0x14001f75c  mov     eax, edi
0x14001f75e  mov     r9d, esi; MessageNumber
0x14001f761  mov     [rsp+78h+var_40], rax
0x14001f766  mov     edx, 2Bh ; '+'; MessageFlags
0x14001f76b  mov     [rsp+78h+var_48], rbx
0x14001f770  lea     rax, [rsp+78h+arg_18]
0x14001f778  mov     [rsp+78h+var_50], 4
0x14001f781  mov     rcx, rbp; LoggerHandle
0x14001f784  mov     [rsp+78h+var_58], rax
0x14001f789  call    cs:__imp_TraceMessage
0x14001f78f  add     rsp, 58h
0x14001f793  pop     rdi
0x14001f794  pop     rsi
0x14001f795  pop     rbp
0x14001f796  pop     rbx
0x14001f797  retn
```
