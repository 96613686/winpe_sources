# WPP_SF_D_sid_D

- ea: `0x180013004`
- end: `0x1800130bb`
- name: `WPP_SF_D_sid_D`
- size: `183`
- prototype: `__int64 __fastcall(int, int, int, int, PSID pSid, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f64c`

## callees

- `0x180013004`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013027`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001304b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013027`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001304b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013034`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013034`
- `ntdll!EtwTraceMessage` at `0x1800130ac`
- `ntdll!EtwTraceMessage` at `0x1800130ac`

## pseudocode

```c
__int64 WPP_SF_D_sid_D(__int64 a1, unsigned __int16 a2, int a3, int a4, char *pSid, ...)
{
  char *v5; // rbx
  unsigned int v7; // esi
  DWORD LengthSid; // edi
  int v10; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h] BYREF

  va_start(va, pSid);
  v10 = a4;
  v5 = pSid;
  v7 = a2;
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
      return EtwTraceMessage(a1, 43, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v7, &v10, 4, v5, LengthSid, va);
    }
  }
  if ( !IsValidSid(v5) )
    goto LABEL_6;
  return EtwTraceMessage(a1, 43, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v7, &v10, 4, v5, LengthSid, va);
}

```

## disassembly

```asm
0x180013004  mov     [rsp+arg_18], r9d
0x180013009  push    rbx
0x18001300a  push    rbp
0x18001300b  push    rsi
0x18001300c  push    rdi
0x18001300d  sub     rsp, 68h
0x180013011  mov     rbx, [rsp+88h+pSid]
0x180013019  mov     rbp, rcx
0x18001301c  movzx   esi, dx
0x18001301f  test    rbx, rbx
0x180013022  jz      short loc_18001303E
0x180013024  mov     rcx, rbx; pSid
0x180013027  call    cs:__imp_IsValidSid
0x18001302d  test    eax, eax
0x18001302f  jz      short loc_18001303E
0x180013031  mov     rcx, rbx; pSid
0x180013034  call    cs:__imp_GetLengthSid
0x18001303a  mov     edi, eax
0x18001303c  jmp     short loc_180013048
0x18001303e  mov     edi, 5
0x180013043  test    rbx, rbx
0x180013046  jz      short loc_180013055
0x180013048  mov     rcx, rbx; pSid
0x18001304b  call    cs:__imp_IsValidSid
0x180013051  test    eax, eax
0x180013053  jnz     short loc_18001305C
0x180013055  lea     rbx, aNull; "NULL"
0x18001305c  mov     [rsp+88h+var_38], 0
0x180013065  lea     rcx, [rsp+88h+arg_28]
0x18001306d  mov     edx, 4
0x180013072  mov     eax, edi
0x180013074  mov     [rsp+88h+var_40], rdx
0x180013079  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180013080  mov     [rsp+88h+var_48], rcx
0x180013085  mov     r9d, esi
0x180013088  mov     [rsp+88h+var_50], rax
0x18001308d  mov     rcx, rbp
0x180013090  mov     [rsp+88h+var_58], rbx
0x180013095  lea     rax, [rsp+88h+arg_18]
0x18001309d  mov     [rsp+88h+var_60], rdx
0x1800130a2  mov     edx, 2Bh ; '+'
0x1800130a7  mov     [rsp+88h+var_68], rax
0x1800130ac  call    cs:__imp_EtwTraceMessage
0x1800130b2  add     rsp, 68h
0x1800130b6  pop     rdi
0x1800130b7  pop     rsi
0x1800130b8  pop     rbp
0x1800130b9  pop     rbx
0x1800130ba  retn
```
