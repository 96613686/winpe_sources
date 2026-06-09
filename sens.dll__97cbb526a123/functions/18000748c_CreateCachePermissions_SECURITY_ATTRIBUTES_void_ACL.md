# CreateCachePermissions(_SECURITY_ATTRIBUTES *,void *,_ACL * *)

- ea: `0x18000748c`
- end: `0x18000763b`
- name: `?CreateCachePermissions@@YAHPEAU_SECURITY_ATTRIBUTES@@PEAXPEAPEAU_ACL@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(struct _SECURITY_ATTRIBUTES *, void *, struct _ACL **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000732c`

## callees

- `0x18000748c`
- `0x18000a7a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007606`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007606`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007541`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007541`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007519`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007528`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007519`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007528`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000755d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000755d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000757b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180007597`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000757b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180007597`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800075eb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800075eb`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800075ad`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800075ad`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800075c5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800075c5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180007505`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180007505`

## pseudocode

```c
__int64 __fastcall CreateCachePermissions(struct _SECURITY_ATTRIBUTES *a1, void *a2, struct _ACL **a3)
{
  struct _ACL *v6; // rbx
  unsigned int v7; // edi
  DWORD LengthSid; // ebx
  signed int v9; // r15d
  struct _ACL *v10; // rax
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  *a3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v6 = 0;
  pSid = 0;
  v7 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid);
  if ( v7 )
  {
    LengthSid = GetLengthSid(pSid);
    v9 = LengthSid + GetLengthSid(qword_18000DE70) + 32;
    v10 = (struct _ACL *)HeapAlloc(ghSensHeap, 0, v9);
    v6 = v10;
    if ( v10 )
    {
      v7 = InitializeAcl(v10, v9, 2u);
      if ( v7 )
      {
        v7 = AddAccessAllowedAce(v6, 2u, 4u, pSid);
        if ( v7 )
        {
          v7 = AddAccessAllowedAce(v6, 2u, 2u, qword_18000DE70);
          if ( v7 )
          {
            v7 = InitializeSecurityDescriptor(a2, 1u);
            if ( v7 )
            {
              v7 = SetSecurityDescriptorDacl(a2, 1, v6, 0);
              if ( v7 )
              {
                a1->nLength = 24;
                v7 = 1;
                a1->lpSecurityDescriptor = a2;
                a1->bInheritHandle = 0;
              }
            }
          }
        }
      }
    }
  }
  if ( pSid )
    FreeSid(pSid);
  if ( v7 )
  {
    *a3 = v6;
  }
  else if ( v6 )
  {
    HeapFree(ghSensHeap, 0, v6);
  }
  return v7;
}

```

## disassembly

```asm
0x18000748c  mov     r11, rsp
0x18000748f  mov     [r11+20h], rbx
0x180007493  push    rbp
0x180007494  push    rsi
0x180007495  push    rdi
0x180007496  push    r12
0x180007498  push    r13
0x18000749a  push    r14
0x18000749c  push    r15
0x18000749e  mov     rbp, rsp
0x1800074a1  sub     rsp, 80h
0x1800074a8  mov     rax, cs:__security_cookie
0x1800074af  xor     rax, rsp
0x1800074b2  mov     [rbp+var_10], rax
0x1800074b6  xor     r13d, r13d
0x1800074b9  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 100h
0x1800074bf  lea     rax, [rbp+pSid]
0x1800074c3  mov     [r8], r13
0x1800074c6  mov     [r11-68h], rax
0x1800074ca  mov     r12, r8
0x1800074cd  mov     [r11-70h], r13d
0x1800074d1  mov     r14, rdx
0x1800074d4  mov     [r11-78h], r13d
0x1800074d8  mov     rsi, rcx
0x1800074db  mov     [r11-80h], r13d
0x1800074df  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800074e3  mov     [rsp+80h+nSubAuthority4], r13d; nSubAuthority4
0x1800074e8  xor     r9d, r9d; nSubAuthority1
0x1800074eb  mov     [rsp+80h+nSubAuthority3], r13d; nSubAuthority3
0x1800074f0  xor     r8d, r8d; nSubAuthority0
0x1800074f3  mov     dl, 1; nSubAuthorityCount
0x1800074f5  mov     [rsp+80h+nSubAuthority2], r13d; nSubAuthority2
0x1800074fa  mov     dword ptr [rbp+pIdentifierAuthority.Value], r13d
0x1800074fe  mov     ebx, r13d
0x180007501  mov     [rbp+pSid], r13
0x180007505  call    cs:__imp_AllocateAndInitializeSid
0x18000750b  mov     edi, eax
0x18000750d  test    eax, eax
0x18000750f  jz      loc_1800075E2
0x180007515  mov     rcx, [rbp+pSid]; pSid
0x180007519  call    cs:__imp_GetLengthSid
0x18000751f  lea     rcx, qword_18000DE70; pSid
0x180007526  mov     ebx, eax
0x180007528  call    cs:__imp_GetLengthSid
0x18000752e  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180007535  xor     edx, edx; dwFlags
0x180007537  lea     r15d, [rax+20h]
0x18000753b  add     r15d, ebx
0x18000753e  movsxd  r8, r15d; dwBytes
0x180007541  call    cs:__imp_HeapAlloc
0x180007547  mov     rbx, rax
0x18000754a  test    rax, rax
0x18000754d  jz      loc_1800075E2
0x180007553  lea     r8d, [r13+2]; dwAclRevision
0x180007557  mov     edx, r15d; nAclLength
0x18000755a  mov     rcx, rax; pAcl
0x18000755d  call    cs:__imp_InitializeAcl
0x180007563  mov     edi, eax
0x180007565  test    eax, eax
0x180007567  jz      short loc_1800075E2
0x180007569  mov     r9, [rbp+pSid]; pSid
0x18000756d  lea     r15d, [r13+2]
0x180007571  mov     edx, r15d; dwAceRevision
0x180007574  lea     r8d, [r13+4]; AccessMask
0x180007578  mov     rcx, rbx; pAcl
0x18000757b  call    cs:__imp_AddAccessAllowedAce
0x180007581  mov     edi, eax
0x180007583  test    eax, eax
0x180007585  jz      short loc_1800075E2
0x180007587  lea     r9, qword_18000DE70; pSid
0x18000758e  mov     r8d, r15d; AccessMask
0x180007591  mov     edx, r15d; dwAceRevision
0x180007594  mov     rcx, rbx; pAcl
0x180007597  call    cs:__imp_AddAccessAllowedAce
0x18000759d  mov     edi, eax
0x18000759f  test    eax, eax
0x1800075a1  jz      short loc_1800075E2
0x1800075a3  lea     r15d, [r13+1]
0x1800075a7  mov     rcx, r14; pSecurityDescriptor
0x1800075aa  mov     edx, r15d; dwRevision
0x1800075ad  call    cs:__imp_InitializeSecurityDescriptor
0x1800075b3  mov     edi, eax
0x1800075b5  test    eax, eax
0x1800075b7  jz      short loc_1800075E2
0x1800075b9  xor     r9d, r9d; bDaclDefaulted
0x1800075bc  mov     r8, rbx; pDacl
0x1800075bf  mov     edx, r15d; bDaclPresent
0x1800075c2  mov     rcx, r14; pSecurityDescriptor
0x1800075c5  call    cs:__imp_SetSecurityDescriptorDacl
0x1800075cb  mov     edi, eax
0x1800075cd  test    eax, eax
0x1800075cf  jz      short loc_1800075E2
0x1800075d1  mov     dword ptr [rsi], 18h
0x1800075d7  mov     edi, r15d
0x1800075da  mov     [rsi+8], r14
0x1800075de  mov     [rsi+10h], r13d
0x1800075e2  mov     rcx, [rbp+pSid]; pSid
0x1800075e6  test    rcx, rcx
0x1800075e9  jz      short loc_1800075F1
0x1800075eb  call    cs:__imp_FreeSid
0x1800075f1  test    edi, edi
0x1800075f3  jnz     short loc_18000760E
0x1800075f5  test    rbx, rbx
0x1800075f8  jz      short loc_180007612
0x1800075fa  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180007601  mov     r8, rbx; lpMem
0x180007604  xor     edx, edx; dwFlags
0x180007606  call    cs:__imp_HeapFree
0x18000760c  jmp     short loc_180007612
0x18000760e  mov     [r12], rbx
0x180007612  mov     eax, edi
0x180007614  mov     rcx, [rbp+var_10]
0x180007618  xor     rcx, rsp; StackCookie
0x18000761b  call    __security_check_cookie
0x180007620  mov     rbx, [rsp+80h+arg_18]
0x180007628  add     rsp, 80h
0x18000762f  pop     r15
0x180007631  pop     r14
0x180007633  pop     r13
0x180007635  pop     r12
0x180007637  pop     rdi
0x180007638  pop     rsi
0x180007639  pop     rbp
0x18000763a  retn
```
