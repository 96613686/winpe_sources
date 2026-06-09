# CreateSids(void * *,void * *,void * *,void * *,void * *,void * *)

- ea: `0x1800b5b5c`
- end: `0x1800b5e2e`
- name: `?CreateSids@@YAHPEAPEAX00000@Z`
- size: `722`
- prototype: `__int64 __fastcall(PSID *pSid, PSID *, PSID *, PSID *, void **, PSID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b6a88`

## callees

- `0x1800b27e0`
- `0x1800b5b5c`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSidEx` at `0x1800b5d6a`
- `ntdll!RtlAllocateAndInitializeSidEx` at `0x1800b5d6a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5c78`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5cdf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5ceb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d37`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d43`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d4f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d77`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d83`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d8f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d9b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5de6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5df2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5dfe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5e0a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5e16`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5c78`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5cdf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5ceb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d37`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d43`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d4f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d77`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d83`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d8f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5d9b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5de6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5df2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5dfe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5e0a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b5e16`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5c31`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5c6b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5cd2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5d2a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5dd9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5c31`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5c6b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5cd2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5d2a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b5dd9`

## pseudocode

```c
__int64 __fastcall CreateSids(PSID *pSid, PSID *a2, PSID *a3, PSID *a4, void **a5, PSID *a6)
{
  __int64 v11; // rdx
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-49h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v13; // [rsp+68h] [rbp-41h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v14; // [rsp+70h] [rbp-39h] BYREF
  _DWORD v15[10]; // [rsp+78h] [rbp-31h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v14.Value = 0;
  *(_WORD *)&v14.Value[4] = 256;
  *(_DWORD *)v13.Value = 0;
  *(_WORD *)&v13.Value[4] = 3840;
  v15[0] = 3;
  v15[1] = 1024;
  v15[2] = -1889523807;
  v15[3] = 874036122;
  v15[4] = -8931741;
  v15[5] = 1823921565;
  v15[6] = 1746547431;
  v15[7] = -1841081848;
  v15[8] = -669014394;
  v15[9] = 991631256;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, pSid) )
    return 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, a2) )
  {
    FreeSid(*pSid);
    *pSid = 0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&v14, 1u, 0, 0, 0, 0, 0, 0, 0, 0, a3) )
  {
    FreeSid(*pSid);
    *pSid = 0;
    FreeSid(*a2);
    *a2 = 0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&v13, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, a4) )
  {
    FreeSid(*pSid);
    *pSid = 0;
    FreeSid(*a2);
    *a2 = 0;
    FreeSid(*a3);
    *a3 = 0;
    return 0;
  }
  LOBYTE(v11) = 10;
  if ( (int)RtlAllocateAndInitializeSidEx(&v13, v11, v15, a5) < 0 )
  {
    FreeSid(*pSid);
    *pSid = 0;
    FreeSid(*a2);
    *a2 = 0;
    FreeSid(*a3);
    *a3 = 0;
    FreeSid(*a4);
    *a4 = 0;
    return 0;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 7u, 0, 0, 0, 0, 0, 0, 0, a6) )
  {
    FreeSid(*pSid);
    *pSid = 0;
    FreeSid(*a2);
    *a2 = 0;
    FreeSid(*a3);
    *a3 = 0;
    FreeSid(*a4);
    *a4 = 0;
    FreeSid(*a5);
    *a5 = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800b5b5c  push    rbp
0x1800b5b5e  push    rbx
0x1800b5b5f  push    rsi
0x1800b5b60  push    rdi
0x1800b5b61  push    r12
0x1800b5b63  push    r13
0x1800b5b65  push    r14
0x1800b5b67  push    r15
0x1800b5b69  lea     rbp, [rsp-0Fh]
0x1800b5b6e  sub     rsp, 0B8h
0x1800b5b75  mov     rax, cs:__security_cookie
0x1800b5b7c  xor     rax, rsp
0x1800b5b7f  mov     [rbp+47h+var_50], rax
0x1800b5b83  mov     r15, [rbp+47h+arg_20]
0x1800b5b87  xor     r13d, r13d
0x1800b5b8a  mov     r12, [rbp+47h+arg_28]
0x1800b5b8e  mov     r14, r9
0x1800b5b91  mov     [rsp+0F0h+pSid], rcx; pSid
0x1800b5b96  mov     rsi, r8
0x1800b5b99  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800b5b9e  mov     rdi, rdx
0x1800b5ba1  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800b5ba6  lea     r8d, [r13+20h]; nSubAuthority0
0x1800b5baa  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800b5baf  mov     rbx, rcx
0x1800b5bb2  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800b5bb7  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x1800b5bbb  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800b5bc0  mov     r9d, 220h; nSubAuthority1
0x1800b5bc6  mov     dl, 2; nSubAuthorityCount
0x1800b5bc8  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800b5bcd  mov     dword ptr [rbp+47h+pIdentifierAuthority.Value], r13d
0x1800b5bd1  mov     word ptr [rbp+47h+pIdentifierAuthority.Value+4], 500h
0x1800b5bd7  mov     dword ptr [rbp+47h+var_80.Value], r13d
0x1800b5bdb  mov     word ptr [rbp+47h+var_80.Value+4], 100h
0x1800b5be1  mov     dword ptr [rbp+47h+var_88.Value], r13d
0x1800b5be5  mov     word ptr [rbp+47h+var_88.Value+4], 0F00h
0x1800b5beb  mov     [rbp+47h+var_78], 3
0x1800b5bf2  mov     [rbp+47h+var_74], 400h
0x1800b5bf9  mov     [rbp+47h+var_70], 8F6027A1h
0x1800b5c00  mov     [rbp+47h+var_6C], 3418BB9Ah
0x1800b5c07  mov     [rbp+47h+var_68], 0FF77B663h
0x1800b5c0e  mov     [rbp+47h+var_64], 6CB6D59Dh
0x1800b5c15  mov     [rbp+47h+var_60], 681A32E7h
0x1800b5c1c  mov     [rbp+47h+var_5C], 92435208h
0x1800b5c23  mov     [rbp+47h+var_58], 0D81FA686h
0x1800b5c2a  mov     [rbp+47h+var_54], 3B1B1798h
0x1800b5c31  call    cs:__imp_AllocateAndInitializeSid
0x1800b5c37  test    eax, eax
0x1800b5c39  jz      short loc_1800B5C81
0x1800b5c3b  mov     [rsp+0F0h+pSid], rdi; pSid
0x1800b5c40  lea     r8d, [r13+12h]; nSubAuthority0
0x1800b5c44  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800b5c49  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x1800b5c4d  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800b5c52  xor     r9d, r9d; nSubAuthority1
0x1800b5c55  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800b5c5a  mov     dl, 1; nSubAuthorityCount
0x1800b5c5c  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800b5c61  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800b5c66  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800b5c6b  call    cs:__imp_AllocateAndInitializeSid
0x1800b5c71  test    eax, eax
0x1800b5c73  jnz     short loc_1800B5CA3
0x1800b5c75  mov     rcx, [rbx]; pSid
0x1800b5c78  call    cs:__imp_FreeSid
0x1800b5c7e  mov     [rbx], r13
0x1800b5c81  xor     eax, eax
0x1800b5c83  mov     rcx, [rbp+47h+var_50]
0x1800b5c87  xor     rcx, rsp; StackCookie
0x1800b5c8a  call    __security_check_cookie
0x1800b5c8f  add     rsp, 0B8h
0x1800b5c96  pop     r15
0x1800b5c98  pop     r14
0x1800b5c9a  pop     r13
0x1800b5c9c  pop     r12
0x1800b5c9e  pop     rdi
0x1800b5c9f  pop     rsi
0x1800b5ca0  pop     rbx
0x1800b5ca1  pop     rbp
0x1800b5ca2  retn
0x1800b5ca3  mov     [rsp+0F0h+pSid], rsi; pSid
0x1800b5ca8  lea     rcx, [rbp+47h+var_80]; pIdentifierAuthority
0x1800b5cac  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800b5cb1  xor     r9d, r9d; nSubAuthority1
0x1800b5cb4  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800b5cb9  xor     r8d, r8d; nSubAuthority0
0x1800b5cbc  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800b5cc1  mov     dl, 1; nSubAuthorityCount
0x1800b5cc3  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800b5cc8  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800b5ccd  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800b5cd2  call    cs:__imp_AllocateAndInitializeSid
0x1800b5cd8  test    eax, eax
0x1800b5cda  jnz     short loc_1800B5CF6
0x1800b5cdc  mov     rcx, [rbx]; pSid
0x1800b5cdf  call    cs:__imp_FreeSid
0x1800b5ce5  mov     [rbx], r13
0x1800b5ce8  mov     rcx, [rdi]; pSid
0x1800b5ceb  call    cs:__imp_FreeSid
0x1800b5cf1  mov     [rdi], r13
0x1800b5cf4  jmp     short loc_1800B5C81
0x1800b5cf6  mov     [rsp+0F0h+pSid], r14; pSid
0x1800b5cfb  lea     rcx, [rbp+47h+var_88]; pIdentifierAuthority
0x1800b5cff  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800b5d04  mov     r9d, 1; nSubAuthority1
0x1800b5d0a  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800b5d0f  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800b5d14  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800b5d19  lea     r8d, [r9+1]; nSubAuthority0
0x1800b5d1d  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800b5d22  mov     dl, r8b; nSubAuthorityCount
0x1800b5d25  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800b5d2a  call    cs:__imp_AllocateAndInitializeSid
0x1800b5d30  test    eax, eax
0x1800b5d32  jnz     short loc_1800B5D5D
0x1800b5d34  mov     rcx, [rbx]; pSid
0x1800b5d37  call    cs:__imp_FreeSid
0x1800b5d3d  mov     [rbx], r13
0x1800b5d40  mov     rcx, [rdi]; pSid
0x1800b5d43  call    cs:__imp_FreeSid
0x1800b5d49  mov     [rdi], r13
0x1800b5d4c  mov     rcx, [rsi]; pSid
0x1800b5d4f  call    cs:__imp_FreeSid
0x1800b5d55  mov     [rsi], r13
0x1800b5d58  jmp     loc_1800B5C81
0x1800b5d5d  mov     r9, r15
0x1800b5d60  lea     r8, [rbp+47h+var_78]
0x1800b5d64  mov     dl, 0Ah
0x1800b5d66  lea     rcx, [rbp+47h+var_88]
0x1800b5d6a  call    cs:__imp_RtlAllocateAndInitializeSidEx
0x1800b5d70  test    eax, eax
0x1800b5d72  jns     short loc_1800B5DA9
0x1800b5d74  mov     rcx, [rbx]; pSid
0x1800b5d77  call    cs:__imp_FreeSid
0x1800b5d7d  mov     [rbx], r13
0x1800b5d80  mov     rcx, [rdi]; pSid
0x1800b5d83  call    cs:__imp_FreeSid
0x1800b5d89  mov     [rdi], r13
0x1800b5d8c  mov     rcx, [rsi]; pSid
0x1800b5d8f  call    cs:__imp_FreeSid
0x1800b5d95  mov     [rsi], r13
0x1800b5d98  mov     rcx, [r14]; pSid
0x1800b5d9b  call    cs:__imp_FreeSid
0x1800b5da1  mov     [r14], r13
0x1800b5da4  jmp     loc_1800B5C81
0x1800b5da9  mov     [rsp+0F0h+pSid], r12; pSid
0x1800b5dae  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x1800b5db2  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800b5db7  xor     r9d, r9d; nSubAuthority1
0x1800b5dba  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800b5dbf  mov     dl, 1; nSubAuthorityCount
0x1800b5dc1  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800b5dc6  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800b5dcb  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800b5dd0  lea     r8d, [r9+7]; nSubAuthority0
0x1800b5dd4  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800b5dd9  call    cs:__imp_AllocateAndInitializeSid
0x1800b5ddf  test    eax, eax
0x1800b5de1  jnz     short loc_1800B5E24
0x1800b5de3  mov     rcx, [rbx]; pSid
0x1800b5de6  call    cs:__imp_FreeSid
0x1800b5dec  mov     [rbx], r13
0x1800b5def  mov     rcx, [rdi]; pSid
0x1800b5df2  call    cs:__imp_FreeSid
0x1800b5df8  mov     [rdi], r13
0x1800b5dfb  mov     rcx, [rsi]; pSid
0x1800b5dfe  call    cs:__imp_FreeSid
0x1800b5e04  mov     [rsi], r13
0x1800b5e07  mov     rcx, [r14]; pSid
0x1800b5e0a  call    cs:__imp_FreeSid
0x1800b5e10  mov     [r14], r13
0x1800b5e13  mov     rcx, [r15]; pSid
0x1800b5e16  call    cs:__imp_FreeSid
0x1800b5e1c  mov     [r15], r13
0x1800b5e1f  jmp     loc_1800B5C81
0x1800b5e24  mov     eax, 1
0x1800b5e29  jmp     loc_1800B5C83
```
