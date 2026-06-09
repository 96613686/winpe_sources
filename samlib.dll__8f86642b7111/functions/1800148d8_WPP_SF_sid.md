# WPP_SF__sid_

- ea: `0x1800148d8`
- end: `0x18001495d`
- name: `WPP_SF__sid_`
- size: `133`
- prototype: `__int64 __fastcall(TRACEHANDLE LoggerHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a30`
- `0x180001c50`

## callees

- `0x1800148d8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001494e`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001494e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800148f2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014916`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800148f2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014916`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800148ff`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800148ff`

## pseudocode

```c
ULONG __fastcall WPP_SF__sid_(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, char *a4)
{
  char *v5; // rbx
  DWORD LengthSid; // edi

  v5 = a4;
  if ( a4 && IsValidSid(a4) )
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
      return TraceMessage(LoggerHandle, 0x2Bu, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a2, v5, LengthSid, 0);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return TraceMessage(LoggerHandle, 0x2Bu, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a2, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x1800148d8  push    rbx
0x1800148da  push    rbp
0x1800148db  push    rsi
0x1800148dc  push    rdi
0x1800148dd  sub     rsp, 48h
0x1800148e1  movzx   esi, dx
0x1800148e4  mov     rbx, r9
0x1800148e7  mov     rbp, rcx
0x1800148ea  test    r9, r9
0x1800148ed  jz      short loc_180014909
0x1800148ef  mov     rcx, rbx; pSid
0x1800148f2  call    cs:__imp_IsValidSid
0x1800148f8  test    eax, eax
0x1800148fa  jz      short loc_180014909
0x1800148fc  mov     rcx, rbx; pSid
0x1800148ff  call    cs:__imp_GetLengthSid
0x180014905  mov     edi, eax
0x180014907  jmp     short loc_180014913
0x180014909  mov     edi, 5
0x18001490e  test    rbx, rbx
0x180014911  jz      short loc_180014920
0x180014913  mov     rcx, rbx; pSid
0x180014916  call    cs:__imp_IsValidSid
0x18001491c  test    eax, eax
0x18001491e  jnz     short loc_180014927
0x180014920  lea     rbx, aNull; "NULL"
0x180014927  mov     eax, edi
0x180014929  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids; MessageGuid
0x180014930  mov     [rsp+68h+var_38], 0
0x180014939  mov     r9d, esi; MessageNumber
0x18001493c  mov     [rsp+68h+var_40], rax
0x180014941  mov     edx, 2Bh ; '+'; MessageFlags
0x180014946  mov     rcx, rbp; LoggerHandle
0x180014949  mov     [rsp+68h+var_48], rbx
0x18001494e  call    cs:__imp_TraceMessage
0x180014954  add     rsp, 48h
0x180014958  pop     rdi
0x180014959  pop     rsi
0x18001495a  pop     rbp
0x18001495b  pop     rbx
0x18001495c  retn
```
