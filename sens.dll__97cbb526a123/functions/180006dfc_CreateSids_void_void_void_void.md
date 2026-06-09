# CreateSids(void * *,void * *,void * *,void * *)

- ea: `0x180006dfc`
- end: `0x180006f93`
- name: `?CreateSids@@YAHPEAPEAX000@Z`
- size: `407`
- prototype: `__int64 __fastcall(void **, void **, void **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006c28`

## callees

- `0x180006dfc`
- `0x18000a7a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006ec3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006f26`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006f32`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006f7e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006ec3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006f26`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006f32`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006f7e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006e7c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006eb6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006f19`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006f71`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006e7c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006eb6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006f19`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006f71`

## pseudocode

```c
__int64 __fastcall CreateSids(void **a1, void **a2, void **a3, void **a4)
{
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v10; // [rsp+70h] [rbp+Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v11; // [rsp+78h] [rbp+17h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v10.Value = 0;
  *(_WORD *)&v10.Value[4] = 256;
  *(_DWORD *)v11.Value = 0;
  *(_WORD *)&v11.Value[4] = 3840;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, a1) )
    return 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, a2) )
  {
    FreeSid(*a1);
    *a1 = 0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&v10, 1u, 0, 0, 0, 0, 0, 0, 0, 0, a3) )
  {
LABEL_6:
    FreeSid(*a1);
    *a1 = 0;
    FreeSid(*a2);
    *a2 = 0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&v11, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, a4) )
  {
    FreeSid(*a3);
    *a3 = 0;
    goto LABEL_6;
  }
  return 1;
}

```

## disassembly

```asm
0x180006dfc  mov     r11, rsp
0x180006dff  push    rbp
0x180006e00  push    rbx
0x180006e01  push    rsi
0x180006e02  push    rdi
0x180006e03  push    r14
0x180006e05  push    r15
0x180006e07  lea     rbp, [r11-5Fh]
0x180006e0b  sub     rsp, 88h
0x180006e12  mov     rax, cs:__security_cookie
0x180006e19  xor     rax, rsp
0x180006e1c  mov     [rbp+57h+var_38], rax
0x180006e20  xor     r15d, r15d
0x180006e23  mov     [r11-68h], rcx
0x180006e27  mov     [r11-70h], r15d
0x180006e2b  mov     r14, r9
0x180006e2e  mov     [r11-78h], r15d
0x180006e32  mov     rsi, r8
0x180006e35  mov     [r11-80h], r15d
0x180006e39  mov     rdi, rdx
0x180006e3c  mov     [rsp+0B0h+nSubAuthority4], r15d; nSubAuthority4
0x180006e41  lea     r8d, [r15+20h]; nSubAuthority0
0x180006e45  mov     rbx, rcx
0x180006e48  mov     [rsp+0B0h+nSubAuthority3], r15d; nSubAuthority3
0x180006e4d  mov     r9d, 220h; nSubAuthority1
0x180006e53  mov     [rsp+0B0h+nSubAuthority2], r15d; nSubAuthority2
0x180006e58  mov     dl, 2; nSubAuthorityCount
0x180006e5a  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x180006e5e  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180006e62  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180006e68  mov     dword ptr [rbp+57h+var_48.Value], r15d
0x180006e6c  mov     word ptr [rbp+57h+var_48.Value+4], 100h
0x180006e72  mov     dword ptr [rbp+57h+var_40.Value], r15d
0x180006e76  mov     word ptr [rbp+57h+var_40.Value+4], 0F00h
0x180006e7c  call    cs:__imp_AllocateAndInitializeSid
0x180006e82  test    eax, eax
0x180006e84  jz      short loc_180006ECC
0x180006e86  mov     [rsp+50h], rdi; pSid
0x180006e8b  lea     r8d, [r15+12h]; nSubAuthority0
0x180006e8f  mov     [rsp+0B0h+nSubAuthority7], r15d; nSubAuthority7
0x180006e94  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180006e98  mov     [rsp+0B0h+nSubAuthority6], r15d; nSubAuthority6
0x180006e9d  xor     r9d, r9d; nSubAuthority1
0x180006ea0  mov     [rsp+0B0h+nSubAuthority5], r15d; nSubAuthority5
0x180006ea5  mov     dl, 1; nSubAuthorityCount
0x180006ea7  mov     [rsp+0B0h+nSubAuthority4], r15d; nSubAuthority4
0x180006eac  mov     [rsp+0B0h+nSubAuthority3], r15d; nSubAuthority3
0x180006eb1  mov     [rsp+0B0h+nSubAuthority2], r15d; nSubAuthority2
0x180006eb6  call    cs:__imp_AllocateAndInitializeSid
0x180006ebc  test    eax, eax
0x180006ebe  jnz     short loc_180006EEA
0x180006ec0  mov     rcx, [rbx]; pSid
0x180006ec3  call    cs:__imp_FreeSid
0x180006ec9  mov     [rbx], r15
0x180006ecc  xor     eax, eax
0x180006ece  mov     rcx, [rbp+57h+var_38]
0x180006ed2  xor     rcx, rsp; StackCookie
0x180006ed5  call    __security_check_cookie
0x180006eda  add     rsp, 88h
0x180006ee1  pop     r15
0x180006ee3  pop     r14
0x180006ee5  pop     rdi
0x180006ee6  pop     rsi
0x180006ee7  pop     rbx
0x180006ee8  pop     rbp
0x180006ee9  retn
0x180006eea  mov     [rsp+50h], rsi; pSid
0x180006eef  lea     rcx, [rbp+57h+var_48]; pIdentifierAuthority
0x180006ef3  mov     [rsp+0B0h+nSubAuthority7], r15d; nSubAuthority7
0x180006ef8  xor     r9d, r9d; nSubAuthority1
0x180006efb  mov     [rsp+0B0h+nSubAuthority6], r15d; nSubAuthority6
0x180006f00  xor     r8d, r8d; nSubAuthority0
0x180006f03  mov     [rsp+0B0h+nSubAuthority5], r15d; nSubAuthority5
0x180006f08  mov     dl, 1; nSubAuthorityCount
0x180006f0a  mov     [rsp+0B0h+nSubAuthority4], r15d; nSubAuthority4
0x180006f0f  mov     [rsp+0B0h+nSubAuthority3], r15d; nSubAuthority3
0x180006f14  mov     [rsp+0B0h+nSubAuthority2], r15d; nSubAuthority2
0x180006f19  call    cs:__imp_AllocateAndInitializeSid
0x180006f1f  test    eax, eax
0x180006f21  jnz     short loc_180006F3D
0x180006f23  mov     rcx, [rbx]; pSid
0x180006f26  call    cs:__imp_FreeSid
0x180006f2c  mov     [rbx], r15
0x180006f2f  mov     rcx, [rdi]; pSid
0x180006f32  call    cs:__imp_FreeSid
0x180006f38  mov     [rdi], r15
0x180006f3b  jmp     short loc_180006ECC
0x180006f3d  mov     [rsp+50h], r14; pSid
0x180006f42  lea     rcx, [rbp+57h+var_40]; pIdentifierAuthority
0x180006f46  mov     [rsp+0B0h+nSubAuthority7], r15d; nSubAuthority7
0x180006f4b  mov     r9d, 1; nSubAuthority1
0x180006f51  mov     [rsp+0B0h+nSubAuthority6], r15d; nSubAuthority6
0x180006f56  mov     [rsp+0B0h+nSubAuthority5], r15d; nSubAuthority5
0x180006f5b  mov     [rsp+0B0h+nSubAuthority4], r15d; nSubAuthority4
0x180006f60  lea     r8d, [r9+1]; nSubAuthority0
0x180006f64  mov     [rsp+0B0h+nSubAuthority3], r15d; nSubAuthority3
0x180006f69  mov     dl, r8b; nSubAuthorityCount
0x180006f6c  mov     [rsp+0B0h+nSubAuthority2], r15d; nSubAuthority2
0x180006f71  call    cs:__imp_AllocateAndInitializeSid
0x180006f77  test    eax, eax
0x180006f79  jnz     short loc_180006F89
0x180006f7b  mov     rcx, [rsi]; pSid
0x180006f7e  call    cs:__imp_FreeSid
0x180006f84  mov     [rsi], r15
0x180006f87  jmp     short loc_180006F23
0x180006f89  mov     eax, 1
0x180006f8e  jmp     loc_180006ECE
```
