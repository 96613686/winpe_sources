# WPP_SF_dSl_sid__sid_

- ea: `0x1800cf6cc`
- end: `0x1800cf836`
- name: `WPP_SF_dSl_sid__sid_`
- size: `362`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, char, PSID, PSID pSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180075f7c`

## callees

- `0x1800908c8`
- `0x1800a1d10`
- `0x1800cf6cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800cf718`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800cf73b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800cf754`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800cf773`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800cf718`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800cf73b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800cf754`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800cf773`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cf725`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cf761`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cf725`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cf761`

## pseudocode

```c
__int64 __fastcall WPP_SF_dSl_sid__sid_(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        const wchar_t *a5,
        char a6,
        char *a7,
        char *pSid)
{
  char *v8; // rdi
  const wchar_t *v9; // rsi
  DWORD v10; // ebp
  char *v11; // rbx
  DWORD LengthSid; // r14d
  __int64 v13; // rax
  __int64 v14; // rdx
  int v16; // [rsp+70h] [rbp-48h] BYREF

  v8 = pSid;
  v9 = a5;
  v10 = 5;
  v11 = a7;
  v16 = a4;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(v8);
  }
  else
  {
    LengthSid = 5;
    if ( !v8 )
    {
LABEL_6:
      v8 = "NULL";
      goto LABEL_7;
    }
  }
  if ( !IsValidSid(v8) )
    goto LABEL_6;
LABEL_7:
  if ( !v11 )
    goto LABEL_11;
  if ( IsValidSid(v11) )
    v10 = GetLengthSid(v11);
  if ( !IsValidSid(v11) )
LABEL_11:
    v11 = "NULL";
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] );
    v14 = 2 * v13 + 2;
  }
  else
  {
    v14 = 10;
  }
  if ( !a5 )
    v9 = L"NULL";
  return FastWppTraceMessage(
           1025,
           10,
           WPP_026a94d4aff03fd8cf9d6f3b3fa4d2ef_Traceguids,
           &v16,
           4,
           v9,
           v14,
           &a6,
           4,
           v11,
           v10,
           v8,
           LengthSid,
           0,
           v16);
}

```

## disassembly

```asm
0x1800cf6cc  push    rbx
0x1800cf6ce  push    rbp
0x1800cf6cf  push    rsi
0x1800cf6d0  push    rdi
0x1800cf6d1  push    r14
0x1800cf6d3  push    r15
0x1800cf6d5  sub     rsp, 88h
0x1800cf6dc  mov     rax, cs:__security_cookie
0x1800cf6e3  xor     rax, rsp
0x1800cf6e6  mov     [rsp+0B8h+var_40], rax
0x1800cf6eb  mov     rdi, [rsp+0B8h+pSid]
0x1800cf6f3  xor     r15d, r15d
0x1800cf6f6  mov     rsi, [rsp+0B8h+arg_20]
0x1800cf6fe  mov     ebp, 5
0x1800cf703  mov     rbx, [rsp+0B8h+arg_30]
0x1800cf70b  mov     [rsp+0B8h+var_48], r9d
0x1800cf710  test    rdi, rdi
0x1800cf713  jz      short loc_1800CF730
0x1800cf715  mov     rcx, rdi; pSid
0x1800cf718  call    cs:__imp_IsValidSid
0x1800cf71e  test    eax, eax
0x1800cf720  jz      short loc_1800CF730
0x1800cf722  mov     rcx, rdi; pSid
0x1800cf725  call    cs:__imp_GetLengthSid
0x1800cf72b  mov     r14d, eax
0x1800cf72e  jmp     short loc_1800CF738
0x1800cf730  mov     r14d, ebp
0x1800cf733  test    rdi, rdi
0x1800cf736  jz      short loc_1800CF745
0x1800cf738  mov     rcx, rdi; pSid
0x1800cf73b  call    cs:__imp_IsValidSid
0x1800cf741  test    eax, eax
0x1800cf743  jnz     short loc_1800CF74C
0x1800cf745  lea     rdi, aNull_0; "NULL"
0x1800cf74c  test    rbx, rbx
0x1800cf74f  jz      short loc_1800CF77D
0x1800cf751  mov     rcx, rbx; pSid
0x1800cf754  call    cs:__imp_IsValidSid
0x1800cf75a  test    eax, eax
0x1800cf75c  jz      short loc_1800CF76B
0x1800cf75e  mov     rcx, rbx; pSid
0x1800cf761  call    cs:__imp_GetLengthSid
0x1800cf767  mov     ebp, eax
0x1800cf769  jmp     short loc_1800CF770
0x1800cf76b  test    rbx, rbx
0x1800cf76e  jz      short loc_1800CF77D
0x1800cf770  mov     rcx, rbx; pSid
0x1800cf773  call    cs:__imp_IsValidSid
0x1800cf779  test    eax, eax
0x1800cf77b  jnz     short loc_1800CF784
0x1800cf77d  lea     rbx, aNull_0; "NULL"
0x1800cf784  mov     r11d, 0Ah
0x1800cf78a  test    rsi, rsi
0x1800cf78d  jz      short loc_1800CF7A7
0x1800cf78f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cf793  inc     rax
0x1800cf796  cmp     [rsi+rax*2], r15w
0x1800cf79b  jnz     short loc_1800CF793
0x1800cf79d  lea     rdx, ds:2[rax*2]
0x1800cf7a5  jmp     short loc_1800CF7AA
0x1800cf7a7  mov     rdx, r11
0x1800cf7aa  mov     [rsp+0B8h+var_50], r15
0x1800cf7af  lea     r8, aNull_1; "NULL"
0x1800cf7b6  mov     eax, r14d
0x1800cf7b9  lea     r9, [rsp+0B8h+var_48]
0x1800cf7be  mov     [rsp+0B8h+var_58], rax
0x1800cf7c3  test    rsi, rsi
0x1800cf7c6  mov     [rsp+0B8h+var_60], rdi
0x1800cf7cb  lea     rax, [rsp+0B8h+arg_28]
0x1800cf7d3  cmovz   rsi, r8
0x1800cf7d7  mov     ecx, ebp
0x1800cf7d9  mov     [rsp+0B8h+var_68], rcx
0x1800cf7de  lea     r8, WPP_026a94d4aff03fd8cf9d6f3b3fa4d2ef_Traceguids
0x1800cf7e5  mov     [rsp+0B8h+var_70], rbx
0x1800cf7ea  mov     ecx, 4
0x1800cf7ef  mov     [rsp+0B8h+var_78], rcx
0x1800cf7f4  mov     r10d, 401h
0x1800cf7fa  mov     [rsp+0B8h+var_80], rax
0x1800cf7ff  mov     [rsp+0B8h+var_88], rdx
0x1800cf804  mov     edx, r11d
0x1800cf807  mov     [rsp+0B8h+var_90], rsi
0x1800cf80c  mov     [rsp+0B8h+var_98], rcx
0x1800cf811  mov     ecx, r10d
0x1800cf814  call    FastWppTraceMessage
0x1800cf819  mov     rcx, [rsp+0B8h+var_40]
0x1800cf81e  xor     rcx, rsp; StackCookie
0x1800cf821  call    __security_check_cookie
0x1800cf826  add     rsp, 88h
0x1800cf82d  pop     r15
0x1800cf82f  pop     r14
0x1800cf831  pop     rdi
0x1800cf832  pop     rsi
0x1800cf833  pop     rbp
0x1800cf834  pop     rbx
0x1800cf835  retn
```
