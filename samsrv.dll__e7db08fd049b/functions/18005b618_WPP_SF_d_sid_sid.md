# WPP_SF_d_sid__sid_

- ea: `0x18005b618`
- end: `0x18005b71f`
- name: `WPP_SF_d_sid__sid_`
- size: `263`
- prototype: `__int64 __fastcall(int, int, int, int, PSID, PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005afd0`

## callees

- `0x18005b618`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18005b704`
- `ntdll!EtwTraceMessage` at `0x18005b704`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005b654`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005b696`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005b654`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005b696`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005b647`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005b668`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005b689`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005b6a8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005b647`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005b668`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005b689`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005b6a8`

## pseudocode

```c
__int64 __fastcall WPP_SF_d_sid__sid_(__int64 a1, __int64 a2, __int64 a3, int a4, char *a5, char *pSid)
{
  char *v6; // rdi
  DWORD LengthSid; // esi
  char *v9; // rbx
  int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = a4;
  v6 = pSid;
  LengthSid = 5;
  if ( pSid && IsValidSid(pSid) )
  {
    GetLengthSid(v6);
  }
  else if ( !v6 )
  {
LABEL_6:
    v6 = "NULL";
    goto LABEL_7;
  }
  if ( !IsValidSid(v6) )
    goto LABEL_6;
LABEL_7:
  v9 = a5;
  if ( !a5 )
    goto LABEL_12;
  if ( IsValidSid(a5) )
  {
    LengthSid = GetLengthSid(v9);
    goto LABEL_11;
  }
  if ( !v9 )
  {
LABEL_12:
    v9 = "NULL";
    return EtwTraceMessage(a1, 43, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids, 23, &v11, 4, v9, LengthSid, v6);
  }
LABEL_11:
  if ( !IsValidSid(v9) )
    goto LABEL_12;
  return EtwTraceMessage(a1, 43, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids, 23, &v11, 4, v9, LengthSid, v6);
}

```

## disassembly

```asm
0x18005b618  mov     [rsp+arg_0], rbx
0x18005b61d  mov     [rsp+arg_8], rbp
0x18005b622  mov     [rsp+arg_18], r9d
0x18005b627  push    rsi
0x18005b628  push    rdi
0x18005b629  push    r14
0x18005b62b  sub     rsp, 60h
0x18005b62f  mov     rdi, [rsp+78h+pSid]
0x18005b637  mov     r14, rcx
0x18005b63a  mov     esi, 5
0x18005b63f  test    rdi, rdi
0x18005b642  jz      short loc_18005B65E
0x18005b644  mov     rcx, rdi; pSid
0x18005b647  call    cs:__imp_IsValidSid
0x18005b64d  test    eax, eax
0x18005b64f  jz      short loc_18005B65E
0x18005b651  mov     rcx, rdi; pSid
0x18005b654  call    cs:__imp_GetLengthSid
0x18005b65a  mov     ebp, eax
0x18005b65c  jmp     short loc_18005B665
0x18005b65e  mov     ebp, esi
0x18005b660  test    rdi, rdi
0x18005b663  jz      short loc_18005B672
0x18005b665  mov     rcx, rdi; pSid
0x18005b668  call    cs:__imp_IsValidSid
0x18005b66e  test    eax, eax
0x18005b670  jnz     short loc_18005B679
0x18005b672  lea     rdi, aNull; "NULL"
0x18005b679  mov     rbx, [rsp+78h+arg_20]
0x18005b681  test    rbx, rbx
0x18005b684  jz      short loc_18005B6B2
0x18005b686  mov     rcx, rbx; pSid
0x18005b689  call    cs:__imp_IsValidSid
0x18005b68f  test    eax, eax
0x18005b691  jz      short loc_18005B6A0
0x18005b693  mov     rcx, rbx; pSid
0x18005b696  call    cs:__imp_GetLengthSid
0x18005b69c  mov     esi, eax
0x18005b69e  jmp     short loc_18005B6A5
0x18005b6a0  test    rbx, rbx
0x18005b6a3  jz      short loc_18005B6B2
0x18005b6a5  mov     rcx, rbx; pSid
0x18005b6a8  call    cs:__imp_IsValidSid
0x18005b6ae  test    eax, eax
0x18005b6b0  jnz     short loc_18005B6B9
0x18005b6b2  lea     rbx, aNull; "NULL"
0x18005b6b9  mov     [rsp+78h+var_28], 0
0x18005b6c2  lea     r8, WPP_4fe2a72f4b7d39ff2f3b29ec2f08b9d0_Traceguids
0x18005b6c9  mov     eax, ebp
0x18005b6cb  mov     r9d, 17h
0x18005b6d1  mov     [rsp+78h+var_30], rax
0x18005b6d6  lea     rax, [rsp+78h+arg_18]
0x18005b6de  mov     [rsp+78h+var_38], rdi
0x18005b6e3  mov     ecx, esi
0x18005b6e5  mov     [rsp+78h+var_40], rcx
0x18005b6ea  lea     edx, [r9+14h]
0x18005b6ee  mov     [rsp+78h+var_48], rbx
0x18005b6f3  mov     rcx, r14
0x18005b6f6  mov     [rsp+78h+var_50], 4
0x18005b6ff  mov     [rsp+78h+var_58], rax
0x18005b704  call    cs:__imp_EtwTraceMessage
0x18005b70a  lea     r11, [rsp+78h+var_18]
0x18005b70f  mov     rbx, [r11+20h]
0x18005b713  mov     rbp, [r11+28h]
0x18005b717  mov     rsp, r11
0x18005b71a  pop     r14
0x18005b71c  pop     rdi
0x18005b71d  pop     rsi
0x18005b71e  retn
```
