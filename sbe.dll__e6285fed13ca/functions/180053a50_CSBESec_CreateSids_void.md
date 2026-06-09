# CSBESec::CreateSids(void)

- ea: `0x180053a50`
- end: `0x180053b30`
- name: `?CreateSids@CSBESec@@AEAAJXZ`
- size: `224`
- prototype: `__int64 __fastcall(CSBESec *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000a90c`
- `0x18000aadc`
- `0x18000eb30`
- `0x180014f20`

## callees

- `0x180001c00`
- `0x180053a50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180053ac2`
- `KERNEL32!GetLastError` at `0x180053ac2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180053ab8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180053b03`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180053ab8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180053b03`

## pseudocode

```c
signed int __fastcall CSBESec::CreateSids(CSBESec *this)
{
  BYTE v1; // dl
  signed int result; // eax
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v5; // [rsp+68h] [rbp-18h] BYREF

  v1 = *((_BYTE *)this + 56);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  *(_DWORD *)v5.Value = 0;
  *(_WORD *)&v5.Value[4] = 768;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, v1, 0, 0, 0, 0, 0, 0, 0, 0, (PSID *)this + 6)
    && AllocateAndInitializeSid(&v5, 1u, 0, 0, 0, 0, 0, 0, 0, 0, (PSID *)this + 8) )
  {
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180053a50  mov     [rsp-8+arg_8], rbx
0x180053a55  mov     [rsp-8+arg_10], rdi
0x180053a5a  push    rbp
0x180053a5b  mov     rbp, rsp
0x180053a5e  sub     rsp, 80h
0x180053a65  mov     rax, cs:__security_cookie
0x180053a6c  xor     rax, rsp
0x180053a6f  mov     [rbp+var_10], rax
0x180053a73  mov     dl, [rcx+38h]; nSubAuthorityCount
0x180053a76  lea     rax, [rcx+30h]
0x180053a7a  xor     edi, edi
0x180053a7c  mov     [rsp+80h+pSid], rax; pSid
0x180053a81  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180053a85  mov     rbx, rcx
0x180053a88  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180053a8c  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180053a90  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180053a94  xor     r9d, r9d; nSubAuthority1
0x180053a97  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180053a9b  xor     r8d, r8d; nSubAuthority0
0x180053a9e  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180053aa2  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180053aa6  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x180053aa9  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 100h
0x180053aaf  mov     dword ptr [rbp+var_18.Value], edi
0x180053ab2  mov     word ptr [rbp+var_18.Value+4], 300h
0x180053ab8  call    cs:__imp_AllocateAndInitializeSid
0x180053abe  test    eax, eax
0x180053ac0  jnz     short loc_180053AD6
0x180053ac2  call    cs:__imp_GetLastError
0x180053ac8  test    eax, eax
0x180053aca  jle     short loc_180053B0F
0x180053acc  movzx   eax, ax
0x180053acf  or      eax, 80070000h
0x180053ad4  jmp     short loc_180053B0F
0x180053ad6  lea     rax, [rbx+40h]
0x180053ada  xor     r9d, r9d; nSubAuthority1
0x180053add  mov     [rsp+80h+pSid], rax; pSid
0x180053ae2  lea     rcx, [rbp+var_18]; pIdentifierAuthority
0x180053ae6  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180053aea  xor     r8d, r8d; nSubAuthority0
0x180053aed  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180053af1  mov     dl, 1; nSubAuthorityCount
0x180053af3  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x180053af7  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180053afb  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180053aff  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x180053b03  call    cs:__imp_AllocateAndInitializeSid
0x180053b09  test    eax, eax
0x180053b0b  jz      short loc_180053AC2
0x180053b0d  mov     eax, edi
0x180053b0f  mov     rcx, [rbp+var_10]
0x180053b13  xor     rcx, rsp; StackCookie
0x180053b16  call    __security_check_cookie
0x180053b1b  lea     r11, [rsp+80h+var_s0]
0x180053b23  mov     rbx, [r11+18h]
0x180053b27  mov     rdi, [r11+20h]
0x180053b2b  mov     rsp, r11
0x180053b2e  pop     rbp
0x180053b2f  retn
```
