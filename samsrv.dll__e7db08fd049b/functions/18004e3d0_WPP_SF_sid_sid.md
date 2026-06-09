# WPP_SF__sid__sid_

- ea: `0x18004e3d0`
- end: `0x18004e4af`
- name: `WPP_SF__sid__sid_`
- size: `223`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e1b0`
- `0x180090b1c`

## callees

- `0x18004e3d0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18004e49a`
- `ntdll!EtwTraceMessage` at `0x18004e49a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e40e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e448`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e40e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004e448`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e401`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e422`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e43b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e45a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e401`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e422`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e43b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004e45a`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid__sid_(__int64 a1, unsigned __int16 a2, __int64 a3, char *a4, char *pSid)
{
  const char *v5; // rdi
  unsigned int v7; // r15d
  DWORD v10; // esi
  DWORD LengthSid; // ebp

  v5 = pSid;
  v7 = a2;
  v10 = 5;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
  }
  else
  {
    LengthSid = 5;
    if ( !pSid )
    {
LABEL_6:
      v5 = "NULL";
      goto LABEL_7;
    }
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_6;
LABEL_7:
  if ( !a4 )
    goto LABEL_11;
  if ( IsValidSid(a4) )
    v10 = GetLengthSid(a4);
  if ( !IsValidSid(a4) )
LABEL_11:
    a4 = "NULL";
  return EtwTraceMessage(a1, 43, a3, v7, a4, v10, v5, LengthSid, 0);
}

```

## disassembly

```asm
0x18004e3d0  push    rbx
0x18004e3d2  push    rbp
0x18004e3d3  push    rsi
0x18004e3d4  push    rdi
0x18004e3d5  push    r12
0x18004e3d7  push    r14
0x18004e3d9  push    r15
0x18004e3db  sub     rsp, 50h
0x18004e3df  mov     rdi, [rsp+88h+pSid]
0x18004e3e7  mov     rbx, r9
0x18004e3ea  movzx   r15d, dx
0x18004e3ee  mov     r14, r8
0x18004e3f1  mov     r12, rcx
0x18004e3f4  mov     esi, 5
0x18004e3f9  test    rdi, rdi
0x18004e3fc  jz      short loc_18004E418
0x18004e3fe  mov     rcx, rdi; pSid
0x18004e401  call    cs:__imp_IsValidSid
0x18004e407  test    eax, eax
0x18004e409  jz      short loc_18004E418
0x18004e40b  mov     rcx, rdi; pSid
0x18004e40e  call    cs:__imp_GetLengthSid
0x18004e414  mov     ebp, eax
0x18004e416  jmp     short loc_18004E41F
0x18004e418  mov     ebp, esi
0x18004e41a  test    rdi, rdi
0x18004e41d  jz      short loc_18004E42C
0x18004e41f  mov     rcx, rdi; pSid
0x18004e422  call    cs:__imp_IsValidSid
0x18004e428  test    eax, eax
0x18004e42a  jnz     short loc_18004E433
0x18004e42c  lea     rdi, aNull; "NULL"
0x18004e433  test    rbx, rbx
0x18004e436  jz      short loc_18004E464
0x18004e438  mov     rcx, rbx; pSid
0x18004e43b  call    cs:__imp_IsValidSid
0x18004e441  test    eax, eax
0x18004e443  jz      short loc_18004E452
0x18004e445  mov     rcx, rbx; pSid
0x18004e448  call    cs:__imp_GetLengthSid
0x18004e44e  mov     esi, eax
0x18004e450  jmp     short loc_18004E457
0x18004e452  test    rbx, rbx
0x18004e455  jz      short loc_18004E464
0x18004e457  mov     rcx, rbx; pSid
0x18004e45a  call    cs:__imp_IsValidSid
0x18004e460  test    eax, eax
0x18004e462  jnz     short loc_18004E46B
0x18004e464  lea     rbx, aNull; "NULL"
0x18004e46b  mov     [rsp+88h+var_48], 0
0x18004e474  mov     r9d, r15d
0x18004e477  mov     eax, ebp
0x18004e479  mov     r8, r14
0x18004e47c  mov     [rsp+88h+var_50], rax
0x18004e481  mov     edx, 2Bh ; '+'
0x18004e486  mov     ecx, esi
0x18004e488  mov     [rsp+88h+var_58], rdi
0x18004e48d  mov     [rsp+88h+var_60], rcx
0x18004e492  mov     rcx, r12
0x18004e495  mov     [rsp+88h+var_68], rbx
0x18004e49a  call    cs:__imp_EtwTraceMessage
0x18004e4a0  add     rsp, 50h
0x18004e4a4  pop     r15
0x18004e4a6  pop     r14
0x18004e4a8  pop     r12
0x18004e4aa  pop     rdi
0x18004e4ab  pop     rsi
0x18004e4ac  pop     rbp
0x18004e4ad  pop     rbx
0x18004e4ae  retn
```
