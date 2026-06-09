# SclpCreateDatabaseProtection

- ea: `0x18000c4b4`
- end: `0x18000c683`
- name: `SclpCreateDatabaseProtection`
- size: `463`
- prototype: `int __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b90c`

## callees

- `0x18000c4b4`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000c5c0`
- `ntdll!RtlAllocateHeap` at `0x18000c5c0`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c52c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c571`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c52c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c571`
- `ntdll!RtlLengthSid` at `0x18000c597`
- `ntdll!RtlLengthSid` at `0x18000c5a3`
- `ntdll!RtlLengthSid` at `0x18000c597`
- `ntdll!RtlLengthSid` at `0x18000c5a3`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000c661`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000c661`
- `ntdll!RtlGetAce` at `0x18000c639`
- `ntdll!RtlGetAce` at `0x18000c639`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000c5ff`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000c61b`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000c5ff`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000c61b`
- `ntdll!RtlCreateAcl` at `0x18000c5e3`
- `ntdll!RtlCreateAcl` at `0x18000c5e3`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000c585`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000c585`

## pseudocode

```c
int __fastcall SclpCreateDatabaseProtection(PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  int result; // eax
  ULONG v3; // ebx
  ULONG v4; // edi
  struct _ACL *Heap; // rax
  struct _ACL *v6; // rbx
  WORD v7; // di
  PSID Sid; // [rsp+60h] [rbp-9h] BYREF
  PSID v9; // [rsp+68h] [rbp-1h] BYREF
  PVOID Ace; // [rsp+70h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp+Fh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  Ace = 0;
  Sid = 0;
  v9 = 0;
  result = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( result >= 0 )
  {
    result = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v9);
    if ( result >= 0 )
    {
      result = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( result >= 0 )
      {
        v3 = RtlLengthSid(v9);
        v4 = v3 + RtlLengthSid(Sid) + 40;
        Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
        v6 = Heap;
        if ( Heap )
        {
          result = RtlCreateAcl(Heap, v4, 2u);
          if ( result >= 0 )
          {
            result = RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, Sid);
            if ( result >= 0 )
            {
              result = RtlAddAccessAllowedAce(v6, 2u, 0x60000u, v9);
              if ( result >= 0 )
              {
                v7 = 0;
                if ( v6->AceCount )
                {
                  while ( 1 )
                  {
                    result = RtlGetAce(v6, v7, &Ace);
                    if ( result < 0 )
                      break;
                    ++v7;
                    *((_BYTE *)Ace + 1) |= 2u;
                    if ( v7 >= v6->AceCount )
                      return RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v6, 0);
                  }
                }
                else
                {
                  return RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v6, 0);
                }
              }
            }
          }
        }
        else
        {
          return -1073741801;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c4b4  push    rbp
0x18000c4b6  push    rbx
0x18000c4b7  push    rsi
0x18000c4b8  push    rdi
0x18000c4b9  push    r12
0x18000c4bb  push    r14
0x18000c4bd  lea     rbp, [rsp-2Fh]
0x18000c4c2  sub     rsp, 98h
0x18000c4c9  mov     rax, cs:__security_cookie
0x18000c4d0  xor     rax, rsp
0x18000c4d3  mov     [rbp+57h+var_40], rax
0x18000c4d7  xor     r14d, r14d
0x18000c4da  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18000c4e0  lea     rax, [rbp+57h+var_60]
0x18000c4e4  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x18000c4e8  mov     [rsp+0C0h+Sid], rax; Sid
0x18000c4ed  mov     rsi, rcx
0x18000c4f0  mov     [rsp+0C0h+SubAuthority7], r14d; SubAuthority7
0x18000c4f5  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18000c4f9  mov     [rsp+0C0h+SubAuthority6], r14d; SubAuthority6
0x18000c4fe  lea     r12d, [r14+1]
0x18000c502  mov     [rsp+0C0h+SubAuthority5], r14d; SubAuthority5
0x18000c507  lea     r8d, [r14+12h]; SubAuthority0
0x18000c50b  mov     [rsp+0C0h+SubAuthority4], r14d; SubAuthority4
0x18000c510  mov     dl, r12b; SubAuthorityCount
0x18000c513  mov     [rsp+0C0h+SubAuthority3], r14d; SubAuthority3
0x18000c518  xor     r9d, r9d; SubAuthority1
0x18000c51b  mov     [rsp+0C0h+SubAuthority2], r14d; SubAuthority2
0x18000c520  mov     [rbp+57h+Ace], r14
0x18000c524  mov     [rbp+57h+var_60], r14
0x18000c528  mov     [rbp+57h+var_58], r14
0x18000c52c  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000c532  test    eax, eax
0x18000c534  js      loc_18000C667
0x18000c53a  lea     rax, [rbp+57h+var_58]
0x18000c53e  mov     r9d, 220h; SubAuthority1
0x18000c544  mov     [rsp+0C0h+Sid], rax; Sid
0x18000c549  lea     r8d, [r14+20h]; SubAuthority0
0x18000c54d  mov     [rsp+0C0h+SubAuthority7], r14d; SubAuthority7
0x18000c552  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18000c556  mov     [rsp+0C0h+SubAuthority6], r14d; SubAuthority6
0x18000c55b  mov     dl, 2; SubAuthorityCount
0x18000c55d  mov     [rsp+0C0h+SubAuthority5], r14d; SubAuthority5
0x18000c562  mov     [rsp+0C0h+SubAuthority4], r14d; SubAuthority4
0x18000c567  mov     [rsp+0C0h+SubAuthority3], r14d; SubAuthority3
0x18000c56c  mov     [rsp+0C0h+SubAuthority2], r14d; SubAuthority2
0x18000c571  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000c577  test    eax, eax
0x18000c579  js      loc_18000C667
0x18000c57f  mov     edx, r12d; Revision
0x18000c582  mov     rcx, rsi; SecurityDescriptor
0x18000c585  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000c58b  test    eax, eax
0x18000c58d  js      loc_18000C667
0x18000c593  mov     rcx, [rbp+57h+var_58]; Sid
0x18000c597  call    cs:__imp_RtlLengthSid
0x18000c59d  mov     rcx, [rbp+57h+var_60]; Sid
0x18000c5a1  mov     ebx, eax
0x18000c5a3  call    cs:__imp_RtlLengthSid
0x18000c5a9  mov     rcx, gs:60h
0x18000c5b2  xor     edx, edx; Flags
0x18000c5b4  lea     edi, [rax+28h]
0x18000c5b7  mov     rcx, [rcx+30h]; HeapHandle
0x18000c5bb  add     edi, ebx
0x18000c5bd  mov     r8d, edi; Size
0x18000c5c0  call    cs:__imp_RtlAllocateHeap
0x18000c5c6  mov     rbx, rax
0x18000c5c9  test    rax, rax
0x18000c5cc  jnz     short loc_18000C5D8
0x18000c5ce  mov     eax, 0C0000017h
0x18000c5d3  jmp     loc_18000C667
0x18000c5d8  mov     r8d, 2; AclRevision
0x18000c5de  mov     edx, edi; AclSize
0x18000c5e0  mov     rcx, rbx; Acl
0x18000c5e3  call    cs:__imp_RtlCreateAcl
0x18000c5e9  test    eax, eax
0x18000c5eb  js      short loc_18000C667
0x18000c5ed  mov     r9, [rbp+57h+var_60]; Sid
0x18000c5f1  mov     edx, 2; Revision
0x18000c5f6  mov     r8d, 10000000h; AccessMask
0x18000c5fc  mov     rcx, rbx; Acl
0x18000c5ff  call    cs:__imp_RtlAddAccessAllowedAce
0x18000c605  test    eax, eax
0x18000c607  js      short loc_18000C667
0x18000c609  mov     r9, [rbp+57h+var_58]; Sid
0x18000c60d  mov     edx, 2; Revision
0x18000c612  mov     r8d, 60000h; AccessMask
0x18000c618  mov     rcx, rbx; Acl
0x18000c61b  call    cs:__imp_RtlAddAccessAllowedAce
0x18000c621  test    eax, eax
0x18000c623  js      short loc_18000C667
0x18000c625  mov     edi, r14d
0x18000c628  cmp     r14w, [rbx+4]
0x18000c62d  jnb     short loc_18000C655
0x18000c62f  movzx   edx, di; AceIndex
0x18000c632  lea     r8, [rbp+57h+Ace]; Ace
0x18000c636  mov     rcx, rbx; Acl
0x18000c639  call    cs:__imp_RtlGetAce
0x18000c63f  test    eax, eax
0x18000c641  js      short loc_18000C667
0x18000c643  mov     rax, [rbp+57h+Ace]
0x18000c647  add     di, r12w
0x18000c64b  or      byte ptr [rax+1], 2
0x18000c64f  cmp     di, [rbx+4]
0x18000c653  jb      short loc_18000C62F
0x18000c655  xor     r9d, r9d; DaclDefaulted
0x18000c658  mov     r8, rbx; Dacl
0x18000c65b  mov     dl, r12b; DaclPresent
0x18000c65e  mov     rcx, rsi; SecurityDescriptor
0x18000c661  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000c667  mov     rcx, [rbp+57h+var_40]
0x18000c66b  xor     rcx, rsp; StackCookie
0x18000c66e  call    __security_check_cookie
0x18000c673  add     rsp, 98h
0x18000c67a  pop     r14
0x18000c67c  pop     r12
0x18000c67e  pop     rdi
0x18000c67f  pop     rsi
0x18000c680  pop     rbx
0x18000c681  pop     rbp
0x18000c682  retn
```
