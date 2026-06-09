# WPP_SF_D_sid_

- ea: `0x1800144a0`
- end: `0x18001454f`
- name: `WPP_SF_D_sid_`
- size: `175`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010cf0`

## callees

- `0x1800144a0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014539`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014539`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800144c7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800144eb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800144c7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800144eb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800144d4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800144d4`

## pseudocode

```c
ULONG __fastcall WPP_SF_D_sid_(TRACEHANDLE LoggerHandle, __int64 a2, __int64 a3, int a4, char *pSid)
{
  char *v5; // rbx
  DWORD LengthSid; // edi
  int v9; // [rsp+78h] [rbp+20h] BYREF

  v9 = a4;
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
               &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
               0x18Du,
               &v9,
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
           &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
           0x18Du,
           &v9,
           4,
           v5,
           LengthSid,
           0);
}

```

## disassembly

```asm
0x1800144a0  mov     [rsp+arg_0], rbx
0x1800144a5  mov     [rsp+arg_8], rsi
0x1800144aa  mov     [rsp+arg_18], r9d
0x1800144af  push    rdi
0x1800144b0  sub     rsp, 50h
0x1800144b4  mov     rbx, [rsp+58h+pSid]
0x1800144bc  mov     rsi, rcx
0x1800144bf  test    rbx, rbx
0x1800144c2  jz      short loc_1800144DE
0x1800144c4  mov     rcx, rbx; pSid
0x1800144c7  call    cs:__imp_IsValidSid
0x1800144cd  test    eax, eax
0x1800144cf  jz      short loc_1800144DE
0x1800144d1  mov     rcx, rbx; pSid
0x1800144d4  call    cs:__imp_GetLengthSid
0x1800144da  mov     edi, eax
0x1800144dc  jmp     short loc_1800144E8
0x1800144de  mov     edi, 5
0x1800144e3  test    rbx, rbx
0x1800144e6  jz      short loc_1800144F5
0x1800144e8  mov     rcx, rbx; pSid
0x1800144eb  call    cs:__imp_IsValidSid
0x1800144f1  test    eax, eax
0x1800144f3  jnz     short loc_1800144FC
0x1800144f5  lea     rbx, aNull; "NULL"
0x1800144fc  mov     [rsp+58h+var_18], 0
0x180014505  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids; MessageGuid
0x18001450c  mov     eax, edi
0x18001450e  mov     r9d, 18Dh; MessageNumber
0x180014514  mov     [rsp+58h+var_20], rax
0x180014519  mov     edx, 2Bh ; '+'; MessageFlags
0x18001451e  mov     [rsp+58h+var_28], rbx
0x180014523  lea     rax, [rsp+58h+arg_18]
0x180014528  mov     [rsp+58h+var_30], 4
0x180014531  mov     rcx, rsi; LoggerHandle
0x180014534  mov     [rsp+58h+var_38], rax
0x180014539  call    cs:__imp_TraceMessage
0x18001453f  mov     rbx, [rsp+58h+arg_0]
0x180014544  mov     rsi, [rsp+58h+arg_8]
0x180014549  add     rsp, 50h
0x18001454d  pop     rdi
0x18001454e  retn
```
