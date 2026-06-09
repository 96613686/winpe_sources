# CreateSids(void * *,void * *,void * *,void * *,void * *,void * *)

- ea: `0x1800baeac`
- end: `0x1800bb200`
- name: `?CreateSids@@YAHPEAPEAX00000@Z`
- size: `852`
- prototype: `__int64 __fastcall(PSID *pSid, PSID *, PSID *, PSID *, void **, PSID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bbf08`

## callees

- `0x1800b7ac0`
- `0x1800baeac`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSidEx` at `0x1800bb0fa`
- `ntdll!RtlAllocateAndInitializeSidEx` at `0x1800bb0fa`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bafd4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb048`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb05a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb0b5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb0c7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb0d9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb10d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb11f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb131`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb143`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb19a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb1ac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb1be`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb1d0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb1e2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bafd4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb048`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb05a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb0b5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb0c7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb0d9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb10d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb11f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb131`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb143`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb19a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb1ac`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb1be`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb1d0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bb1e2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800baf81`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bafc1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb035`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb0a2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb187`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800baf81`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bafc1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb035`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb0a2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800bb187`

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
0x1800baeac  push    rbp
0x1800baeae  push    rbx
0x1800baeaf  push    rsi
0x1800baeb0  push    rdi
0x1800baeb1  push    r12
0x1800baeb3  push    r13
0x1800baeb5  push    r14
0x1800baeb7  push    r15
0x1800baeb9  lea     rbp, [rsp-0Fh]
0x1800baebe  sub     rsp, 0B8h
0x1800baec5  mov     rax, cs:__security_cookie
0x1800baecc  xor     rax, rsp
0x1800baecf  mov     [rbp+47h+var_50], rax
0x1800baed3  mov     r15, [rbp+47h+arg_20]
0x1800baed7  xor     r13d, r13d
0x1800baeda  mov     r12, [rbp+47h+arg_28]
0x1800baede  mov     r14, r9
0x1800baee1  mov     [rsp+0F0h+pSid], rcx; pSid
0x1800baee6  mov     rsi, r8
0x1800baee9  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800baeee  mov     rdi, rdx
0x1800baef1  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800baef6  lea     r8d, [r13+20h]; nSubAuthority0
0x1800baefa  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800baeff  mov     rbx, rcx
0x1800baf02  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800baf07  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x1800baf0b  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800baf10  mov     r9d, 220h; nSubAuthority1
0x1800baf16  mov     dl, 2; nSubAuthorityCount
0x1800baf18  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800baf1d  mov     dword ptr [rbp+47h+pIdentifierAuthority.Value], r13d
0x1800baf21  mov     word ptr [rbp+47h+pIdentifierAuthority.Value+4], 500h
0x1800baf27  mov     dword ptr [rbp+47h+var_80.Value], r13d
0x1800baf2b  mov     word ptr [rbp+47h+var_80.Value+4], 100h
0x1800baf31  mov     dword ptr [rbp+47h+var_88.Value], r13d
0x1800baf35  mov     word ptr [rbp+47h+var_88.Value+4], 0F00h
0x1800baf3b  mov     [rbp+47h+var_78], 3
0x1800baf42  mov     [rbp+47h+var_74], 400h
0x1800baf49  mov     [rbp+47h+var_70], 8F6027A1h
0x1800baf50  mov     [rbp+47h+var_6C], 3418BB9Ah
0x1800baf57  mov     [rbp+47h+var_68], 0FF77B663h
0x1800baf5e  mov     [rbp+47h+var_64], 6CB6D59Dh
0x1800baf65  mov     [rbp+47h+var_60], 681A32E7h
0x1800baf6c  mov     [rbp+47h+var_5C], 92435208h
0x1800baf73  mov     [rbp+47h+var_58], 0D81FA686h
0x1800baf7a  mov     [rbp+47h+var_54], 3B1B1798h
0x1800baf81  call    cs:__imp_AllocateAndInitializeSid
0x1800baf88  nop     dword ptr [rax+rax+00h]
0x1800baf8d  test    eax, eax
0x1800baf8f  jz      short loc_1800BAFE3
0x1800baf91  mov     [rsp+0F0h+pSid], rdi; pSid
0x1800baf96  lea     r8d, [r13+12h]; nSubAuthority0
0x1800baf9a  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800baf9f  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x1800bafa3  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800bafa8  xor     r9d, r9d; nSubAuthority1
0x1800bafab  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800bafb0  mov     dl, 1; nSubAuthorityCount
0x1800bafb2  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800bafb7  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800bafbc  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800bafc1  call    cs:__imp_AllocateAndInitializeSid
0x1800bafc8  nop     dword ptr [rax+rax+00h]
0x1800bafcd  test    eax, eax
0x1800bafcf  jnz     short loc_1800BB006
0x1800bafd1  mov     rcx, [rbx]; pSid
0x1800bafd4  call    cs:__imp_FreeSid
0x1800bafdb  nop     dword ptr [rax+rax+00h]
0x1800bafe0  mov     [rbx], r13
0x1800bafe3  xor     eax, eax
0x1800bafe5  mov     rcx, [rbp+47h+var_50]
0x1800bafe9  xor     rcx, rsp; StackCookie
0x1800bafec  call    __security_check_cookie
0x1800baff1  add     rsp, 0B8h
0x1800baff8  pop     r15
0x1800baffa  pop     r14
0x1800baffc  pop     r13
0x1800baffe  pop     r12
0x1800bb000  pop     rdi
0x1800bb001  pop     rsi
0x1800bb002  pop     rbx
0x1800bb003  pop     rbp
0x1800bb004  retn
0x1800bb006  mov     [rsp+0F0h+pSid], rsi; pSid
0x1800bb00b  lea     rcx, [rbp+47h+var_80]; pIdentifierAuthority
0x1800bb00f  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800bb014  xor     r9d, r9d; nSubAuthority1
0x1800bb017  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800bb01c  xor     r8d, r8d; nSubAuthority0
0x1800bb01f  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800bb024  mov     dl, 1; nSubAuthorityCount
0x1800bb026  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800bb02b  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800bb030  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800bb035  call    cs:__imp_AllocateAndInitializeSid
0x1800bb03c  nop     dword ptr [rax+rax+00h]
0x1800bb041  test    eax, eax
0x1800bb043  jnz     short loc_1800BB06E
0x1800bb045  mov     rcx, [rbx]; pSid
0x1800bb048  call    cs:__imp_FreeSid
0x1800bb04f  nop     dword ptr [rax+rax+00h]
0x1800bb054  mov     [rbx], r13
0x1800bb057  mov     rcx, [rdi]; pSid
0x1800bb05a  call    cs:__imp_FreeSid
0x1800bb061  nop     dword ptr [rax+rax+00h]
0x1800bb066  mov     [rdi], r13
0x1800bb069  jmp     loc_1800BAFE3
0x1800bb06e  mov     [rsp+0F0h+pSid], r14; pSid
0x1800bb073  lea     rcx, [rbp+47h+var_88]; pIdentifierAuthority
0x1800bb077  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800bb07c  mov     r9d, 1; nSubAuthority1
0x1800bb082  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800bb087  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800bb08c  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800bb091  lea     r8d, [r9+1]; nSubAuthority0
0x1800bb095  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800bb09a  mov     dl, r8b; nSubAuthorityCount
0x1800bb09d  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800bb0a2  call    cs:__imp_AllocateAndInitializeSid
0x1800bb0a9  nop     dword ptr [rax+rax+00h]
0x1800bb0ae  test    eax, eax
0x1800bb0b0  jnz     short loc_1800BB0ED
0x1800bb0b2  mov     rcx, [rbx]; pSid
0x1800bb0b5  call    cs:__imp_FreeSid
0x1800bb0bc  nop     dword ptr [rax+rax+00h]
0x1800bb0c1  mov     [rbx], r13
0x1800bb0c4  mov     rcx, [rdi]; pSid
0x1800bb0c7  call    cs:__imp_FreeSid
0x1800bb0ce  nop     dword ptr [rax+rax+00h]
0x1800bb0d3  mov     [rdi], r13
0x1800bb0d6  mov     rcx, [rsi]; pSid
0x1800bb0d9  call    cs:__imp_FreeSid
0x1800bb0e0  nop     dword ptr [rax+rax+00h]
0x1800bb0e5  mov     [rsi], r13
0x1800bb0e8  jmp     loc_1800BAFE3
0x1800bb0ed  mov     r9, r15
0x1800bb0f0  lea     r8, [rbp+47h+var_78]
0x1800bb0f4  mov     dl, 0Ah
0x1800bb0f6  lea     rcx, [rbp+47h+var_88]
0x1800bb0fa  call    cs:__imp_RtlAllocateAndInitializeSidEx
0x1800bb101  nop     dword ptr [rax+rax+00h]
0x1800bb106  test    eax, eax
0x1800bb108  jns     short loc_1800BB157
0x1800bb10a  mov     rcx, [rbx]; pSid
0x1800bb10d  call    cs:__imp_FreeSid
0x1800bb114  nop     dword ptr [rax+rax+00h]
0x1800bb119  mov     [rbx], r13
0x1800bb11c  mov     rcx, [rdi]; pSid
0x1800bb11f  call    cs:__imp_FreeSid
0x1800bb126  nop     dword ptr [rax+rax+00h]
0x1800bb12b  mov     [rdi], r13
0x1800bb12e  mov     rcx, [rsi]; pSid
0x1800bb131  call    cs:__imp_FreeSid
0x1800bb138  nop     dword ptr [rax+rax+00h]
0x1800bb13d  mov     [rsi], r13
0x1800bb140  mov     rcx, [r14]; pSid
0x1800bb143  call    cs:__imp_FreeSid
0x1800bb14a  nop     dword ptr [rax+rax+00h]
0x1800bb14f  mov     [r14], r13
0x1800bb152  jmp     loc_1800BAFE3
0x1800bb157  mov     [rsp+0F0h+pSid], r12; pSid
0x1800bb15c  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x1800bb160  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800bb165  xor     r9d, r9d; nSubAuthority1
0x1800bb168  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800bb16d  mov     dl, 1; nSubAuthorityCount
0x1800bb16f  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800bb174  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800bb179  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800bb17e  lea     r8d, [r9+7]; nSubAuthority0
0x1800bb182  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800bb187  call    cs:__imp_AllocateAndInitializeSid
0x1800bb18e  nop     dword ptr [rax+rax+00h]
0x1800bb193  test    eax, eax
0x1800bb195  jnz     short loc_1800BB1F6
0x1800bb197  mov     rcx, [rbx]; pSid
0x1800bb19a  call    cs:__imp_FreeSid
0x1800bb1a1  nop     dword ptr [rax+rax+00h]
0x1800bb1a6  mov     [rbx], r13
0x1800bb1a9  mov     rcx, [rdi]; pSid
0x1800bb1ac  call    cs:__imp_FreeSid
0x1800bb1b3  nop     dword ptr [rax+rax+00h]
0x1800bb1b8  mov     [rdi], r13
0x1800bb1bb  mov     rcx, [rsi]; pSid
0x1800bb1be  call    cs:__imp_FreeSid
0x1800bb1c5  nop     dword ptr [rax+rax+00h]
0x1800bb1ca  mov     [rsi], r13
0x1800bb1cd  mov     rcx, [r14]; pSid
0x1800bb1d0  call    cs:__imp_FreeSid
0x1800bb1d7  nop     dword ptr [rax+rax+00h]
0x1800bb1dc  mov     [r14], r13
0x1800bb1df  mov     rcx, [r15]; pSid
0x1800bb1e2  call    cs:__imp_FreeSid
0x1800bb1e9  nop     dword ptr [rax+rax+00h]
0x1800bb1ee  mov     [r15], r13
0x1800bb1f1  jmp     loc_1800BAFE3
0x1800bb1f6  mov     eax, 1
0x1800bb1fb  jmp     loc_1800BAFE5
```
