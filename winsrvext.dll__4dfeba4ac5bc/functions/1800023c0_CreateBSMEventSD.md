# CreateBSMEventSD

- ea: `0x1800023c0`
- end: `0x1800025ef`
- name: `CreateBSMEventSD`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003650`

## callees

- `0x1800023c0`
- `0x1800138f0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x1800024cf`
- `KERNELBASE!LocalAlloc` at `0x1800024cf`
- `ntdll!RtlFreeSid` at `0x180002594`
- `ntdll!RtlFreeSid` at `0x1800025a9`
- `ntdll!RtlFreeSid` at `0x180002594`
- `ntdll!RtlFreeSid` at `0x1800025a9`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180002579`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180002579`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180002559`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180002559`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000251a`
- `ntdll!RtlAddAccessAllowedAce` at `0x180002540`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000251a`
- `ntdll!RtlAddAccessAllowedAce` at `0x180002540`
- `ntdll!RtlCreateAcl` at `0x1800024f7`
- `ntdll!RtlCreateAcl` at `0x1800024f7`
- `ntdll!RtlLengthSid` at `0x1800024a1`
- `ntdll!RtlLengthSid` at `0x1800024b3`
- `ntdll!RtlLengthSid` at `0x1800024a1`
- `ntdll!RtlLengthSid` at `0x1800024b3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002441`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000248d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180002441`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000248d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800025c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800025c1`

## pseudocode

```c
_BOOL8 __fastcall CreateBSMEventSD(PSECURITY_DESCRIPTOR *a1)
{
  BOOL v2; // edi
  ULONG v3; // ebx
  ULONG v4; // r14d
  struct _ACL *v5; // rax
  struct _ACL *v6; // rbx
  PSID v8; // [rsp+60h] [rbp-9h] BYREF
  PSID Sid; // [rsp+68h] [rbp-1h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v11; // [rsp+78h] [rbp+Fh] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *a1 = 0;
  v8 = 0;
  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v11.Value = 0;
  *(_WORD *)&v11.Value[4] = 256;
  v2 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid) >= 0
    && RtlAllocateAndInitializeSid(&v11, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v8) >= 0
    && (v3 = RtlLengthSid(Sid),
        v4 = v3 + RtlLengthSid(v8) + 40,
        v5 = (struct _ACL *)LocalAlloc(0, v4 + 40LL),
        (*a1 = v5) != 0)
    && (v6 = v5 + 5, RtlCreateAcl(v5 + 5, v4, 2u) >= 0)
    && RtlAddAccessAllowedAce(v6, 2u, 2u, v8) >= 0
    && RtlAddAccessAllowedAce(v6, 2u, 0x1F0003u, Sid) >= 0
    && RtlCreateSecurityDescriptor(*a1, 1u) >= 0
    && RtlSetDaclSecurityDescriptor(*a1, 1u, v6, 0) >= 0;
  if ( v8 )
    RtlFreeSid(v8);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( !v2 && *a1 )
  {
    LocalFree(*a1);
    *a1 = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800023c0  push    rbp
0x1800023c2  push    rbx
0x1800023c3  push    rsi
0x1800023c4  push    rdi
0x1800023c5  push    r14
0x1800023c7  push    r15
0x1800023c9  lea     rbp, [rsp-2Fh]
0x1800023ce  sub     rsp, 98h
0x1800023d5  mov     rax, cs:__security_cookie
0x1800023dc  xor     rax, rsp
0x1800023df  mov     [rbp+57h+var_40], rax
0x1800023e3  xor     r15d, r15d
0x1800023e6  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x1800023ec  lea     rax, [rbp+57h+var_58]
0x1800023f0  mov     [rcx], r15
0x1800023f3  mov     [rsp+0C0h+Sid], rax; Sid
0x1800023f8  mov     rsi, rcx
0x1800023fb  mov     [rsp+0C0h+SubAuthority7], r15d; SubAuthority7
0x180002400  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180002404  mov     [rsp+0C0h+SubAuthority6], r15d; SubAuthority6
0x180002409  lea     edi, [r15+1]
0x18000240d  mov     [rsp+0C0h+SubAuthority5], r15d; SubAuthority5
0x180002412  lea     r8d, [r15+12h]; SubAuthority0
0x180002416  mov     [rsp+0C0h+SubAuthority4], r15d; SubAuthority4
0x18000241b  mov     dl, dil; SubAuthorityCount
0x18000241e  mov     [rsp+0C0h+SubAuthority3], r15d; SubAuthority3
0x180002423  xor     r9d, r9d; SubAuthority1
0x180002426  mov     [rsp+0C0h+SubAuthority2], r15d; SubAuthority2
0x18000242b  mov     [rbp+57h+var_60], r15
0x18000242f  mov     [rbp+57h+var_58], r15
0x180002433  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r15d
0x180002437  mov     dword ptr [rbp+57h+var_48.Value], r15d
0x18000243b  mov     word ptr [rbp+57h+var_48.Value+4], 100h
0x180002441  call    cs:__imp_RtlAllocateAndInitializeSid
0x180002448  nop     dword ptr [rax+rax+00h]
0x18000244d  test    eax, eax
0x18000244f  jns     short loc_180002459
0x180002451  mov     edi, r15d
0x180002454  jmp     loc_18000258B
0x180002459  lea     rax, [rbp+57h+var_60]
0x18000245d  xor     r9d, r9d; SubAuthority1
0x180002460  mov     [rsp+0C0h+Sid], rax; Sid
0x180002465  lea     rcx, [rbp+57h+var_48]; IdentifierAuthority
0x180002469  mov     [rsp+0C0h+SubAuthority7], r15d; SubAuthority7
0x18000246e  xor     r8d, r8d; SubAuthority0
0x180002471  mov     [rsp+0C0h+SubAuthority6], r15d; SubAuthority6
0x180002476  mov     dl, dil; SubAuthorityCount
0x180002479  mov     [rsp+0C0h+SubAuthority5], r15d; SubAuthority5
0x18000247e  mov     [rsp+0C0h+SubAuthority4], r15d; SubAuthority4
0x180002483  mov     [rsp+0C0h+SubAuthority3], r15d; SubAuthority3
0x180002488  mov     [rsp+0C0h+SubAuthority2], r15d; SubAuthority2
0x18000248d  call    cs:__imp_RtlAllocateAndInitializeSid
0x180002494  nop     dword ptr [rax+rax+00h]
0x180002499  test    eax, eax
0x18000249b  js      short loc_180002451
0x18000249d  mov     rcx, [rbp+57h+var_58]; Sid
0x1800024a1  call    cs:__imp_RtlLengthSid
0x1800024a8  nop     dword ptr [rax+rax+00h]
0x1800024ad  mov     rcx, [rbp+57h+var_60]; Sid
0x1800024b1  mov     ebx, eax
0x1800024b3  call    cs:__imp_RtlLengthSid
0x1800024ba  nop     dword ptr [rax+rax+00h]
0x1800024bf  xor     ecx, ecx; uFlags
0x1800024c1  lea     r14d, [rax+28h]
0x1800024c5  add     r14d, ebx
0x1800024c8  mov     edx, r14d
0x1800024cb  add     rdx, 28h ; '('; uBytes
0x1800024cf  call    cs:__imp_LocalAlloc
0x1800024d6  nop     dword ptr [rax+rax+00h]
0x1800024db  mov     [rsi], rax
0x1800024de  test    rax, rax
0x1800024e1  jz      loc_180002451
0x1800024e7  lea     rbx, [rax+28h]
0x1800024eb  mov     r8d, 2; AclRevision
0x1800024f1  mov     rcx, rbx; Acl
0x1800024f4  mov     edx, r14d; AclSize
0x1800024f7  call    cs:__imp_RtlCreateAcl
0x1800024fe  nop     dword ptr [rax+rax+00h]
0x180002503  test    eax, eax
0x180002505  js      loc_180002451
0x18000250b  mov     r9, [rbp+57h+var_60]; Sid
0x18000250f  mov     edx, 2; Revision
0x180002514  mov     r8d, edx; AccessMask
0x180002517  mov     rcx, rbx; Acl
0x18000251a  call    cs:__imp_RtlAddAccessAllowedAce
0x180002521  nop     dword ptr [rax+rax+00h]
0x180002526  test    eax, eax
0x180002528  js      loc_180002451
0x18000252e  mov     r9, [rbp+57h+var_58]; Sid
0x180002532  mov     edx, 2; Revision
0x180002537  mov     r8d, 1F0003h; AccessMask
0x18000253d  mov     rcx, rbx; Acl
0x180002540  call    cs:__imp_RtlAddAccessAllowedAce
0x180002547  nop     dword ptr [rax+rax+00h]
0x18000254c  test    eax, eax
0x18000254e  js      loc_180002451
0x180002554  mov     rcx, [rsi]; SecurityDescriptor
0x180002557  mov     edx, edi; Revision
0x180002559  call    cs:__imp_RtlCreateSecurityDescriptor
0x180002560  nop     dword ptr [rax+rax+00h]
0x180002565  test    eax, eax
0x180002567  js      loc_180002451
0x18000256d  mov     rcx, [rsi]; SecurityDescriptor
0x180002570  xor     r9d, r9d; DaclDefaulted
0x180002573  mov     r8, rbx; Dacl
0x180002576  mov     dl, dil; DaclPresent
0x180002579  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180002580  nop     dword ptr [rax+rax+00h]
0x180002585  test    eax, eax
0x180002587  cmovs   edi, r15d
0x18000258b  mov     rcx, [rbp+57h+var_60]; Sid
0x18000258f  test    rcx, rcx
0x180002592  jz      short loc_1800025A0
0x180002594  call    cs:__imp_RtlFreeSid
0x18000259b  nop     dword ptr [rax+rax+00h]
0x1800025a0  mov     rcx, [rbp+57h+var_58]; Sid
0x1800025a4  test    rcx, rcx
0x1800025a7  jz      short loc_1800025B5
0x1800025a9  call    cs:__imp_RtlFreeSid
0x1800025b0  nop     dword ptr [rax+rax+00h]
0x1800025b5  test    edi, edi
0x1800025b7  jnz     short loc_1800025D0
0x1800025b9  mov     rcx, [rsi]; hMem
0x1800025bc  test    rcx, rcx
0x1800025bf  jz      short loc_1800025D0
0x1800025c1  call    cs:__imp_LocalFree
0x1800025c8  nop     dword ptr [rax+rax+00h]
0x1800025cd  mov     [rsi], r15
0x1800025d0  mov     eax, edi
0x1800025d2  mov     rcx, [rbp+57h+var_40]
0x1800025d6  xor     rcx, rsp; StackCookie
0x1800025d9  call    __security_check_cookie
0x1800025de  add     rsp, 98h
0x1800025e5  pop     r15
0x1800025e7  pop     r14
0x1800025e9  pop     rdi
0x1800025ea  pop     rsi
0x1800025eb  pop     rbx
0x1800025ec  pop     rbp
0x1800025ed  retn
```
