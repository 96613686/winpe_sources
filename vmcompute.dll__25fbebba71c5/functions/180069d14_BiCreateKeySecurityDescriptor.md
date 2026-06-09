# BiCreateKeySecurityDescriptor

- ea: `0x180069d14`
- end: `0x18006a016`
- name: `BiCreateKeySecurityDescriptor`
- size: `770`
- prototype: `__int64 __fastcall(ACCESS_MASK AccessMask)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006994c`
- `0x1800699f4`
- `0x18006b024`

## callees

- `0x180002f50`
- `0x180004829`
- `0x180069d14`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180069f19`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180069f48`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180069f19`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180069f48`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180069f81`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180069f81`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180069f04`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180069f04`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180069e96`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180069ec5`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180069e96`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180069ec5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180069d8c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180069dd7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180069d8c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180069dd7`
- `ntdll!RtlLengthSid` at `0x180069df1`
- `ntdll!RtlLengthSid` at `0x180069e03`
- `ntdll!RtlLengthSid` at `0x180069e18`
- `ntdll!RtlLengthSid` at `0x180069f2b`
- `ntdll!RtlLengthSid` at `0x180069f5d`
- `ntdll!RtlLengthSid` at `0x180069df1`
- `ntdll!RtlLengthSid` at `0x180069e03`
- `ntdll!RtlLengthSid` at `0x180069e18`
- `ntdll!RtlLengthSid` at `0x180069f2b`
- `ntdll!RtlLengthSid` at `0x180069f5d`
- `ntdll!RtlFreeSid` at `0x180069f9e`
- `ntdll!RtlFreeSid` at `0x180069fb3`
- `ntdll!RtlFreeSid` at `0x180069f9e`
- `ntdll!RtlFreeSid` at `0x180069fb3`
- `ntdll!RtlCreateAcl` at `0x180069e6a`
- `ntdll!RtlCreateAcl` at `0x180069e6a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180069ee3`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180069ee3`
- `ntdll!RtlAllocateHeap` at `0x180069e3d`
- `ntdll!RtlAllocateHeap` at `0x180069e3d`
- `ntdll!RtlFreeHeap` at `0x180069fdf`
- `ntdll!RtlFreeHeap` at `0x180069fdf`

## pseudocode

```c
struct _ACL *__fastcall BiCreateKeySecurityDescriptor(ACCESS_MASK AccessMask)
{
  struct _ACL *v2; // rdi
  NTSTATUS Acl; // ebx
  ULONG v4; // ebx
  ULONG v5; // ebx
  ULONG v6; // r15d
  struct _ACL *Heap; // rax
  struct _ACL *v8; // rsi
  ULONG v9; // ebx
  char *v10; // rbx
  ULONG v11; // eax
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  PSID Sid; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v2 = 0;
  pSid = 0;
  Sid = 0;
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid);
  if ( Acl >= 0 )
  {
    Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( Acl >= 0 )
    {
      v4 = RtlLengthSid(Sid);
      v5 = RtlLengthSid(pSid) + 24 + v4;
      v6 = v5 + RtlLengthSid(pSid) + 40;
      Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      v2 = Heap;
      if ( Heap )
      {
        v8 = Heap + 5;
        Acl = RtlCreateAcl(Heap + 5, v5, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v8, 2u, 0, AccessMask, pSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v8, 2u, 0, 0xF003Fu, Sid);
            if ( Acl >= 0 )
            {
              Acl = RtlCreateSecurityDescriptor(v2, 1u);
              if ( Acl >= 0 )
              {
                Acl = RtlSetDaclSecurityDescriptor(v2, 1u, v8, 0);
                if ( Acl >= 0 )
                {
                  v9 = RtlLengthSecurityDescriptor(v2);
                  if ( RtlLengthSid(pSid) + v9 >= v6 )
                  {
                    v10 = (char *)v2 + RtlLengthSecurityDescriptor(v2);
                    v11 = RtlLengthSid(pSid);
                    memcpy_0(v10, pSid, v11);
                    Acl = RtlSetOwnerSecurityDescriptor(v2, v10, 0);
                    if ( Acl >= 0 )
                      Acl = 0;
                  }
                  else
                  {
                    Acl = -1073741789;
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        Acl = -1073741670;
      }
    }
  }
  if ( pSid )
    RtlFreeSid(pSid);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Acl >= 0 )
    return v2;
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  return 0;
}

```

## disassembly

```asm
0x180069d14  mov     r11, rsp
0x180069d17  mov     [r11+10h], rbx
0x180069d1b  mov     [r11+18h], rsi
0x180069d1f  push    rbp
0x180069d20  push    rdi
0x180069d21  push    r12
0x180069d23  push    r14
0x180069d25  push    r15
0x180069d27  mov     rbp, rsp
0x180069d2a  sub     rsp, 80h
0x180069d31  mov     rax, cs:__security_cookie
0x180069d38  xor     rax, rsp
0x180069d3b  mov     [rbp+var_8], rax
0x180069d3f  xor     r12d, r12d
0x180069d42  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180069d48  lea     rax, [rbp+pSid]
0x180069d4c  mov     dword ptr [rbp+IdentifierAuthority.Value], r12d
0x180069d50  mov     [r11-58h], rax
0x180069d54  mov     r14d, ecx
0x180069d57  mov     [r11-60h], r12d
0x180069d5b  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180069d5f  mov     [r11-68h], r12d
0x180069d63  lea     r8d, [r12+20h]; SubAuthority0
0x180069d68  mov     [r11-70h], r12d
0x180069d6c  mov     r9d, 220h; SubAuthority1
0x180069d72  mov     [r11-78h], r12d
0x180069d76  mov     dl, 2; SubAuthorityCount
0x180069d78  mov     [r11-80h], r12d
0x180069d7c  mov     edi, r12d
0x180069d7f  mov     [rsp+80h+SubAuthority2], r12d; SubAuthority2
0x180069d84  mov     [rbp+pSid], r12
0x180069d88  mov     [rbp+var_18], r12
0x180069d8c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180069d93  nop     dword ptr [rax+rax+00h]
0x180069d98  mov     ebx, eax
0x180069d9a  test    eax, eax
0x180069d9c  js      loc_180069F95
0x180069da2  lea     rax, [rbp+var_18]
0x180069da6  xor     r9d, r9d; SubAuthority1
0x180069da9  mov     [rsp+80h+Sid], rax; Sid
0x180069dae  lea     r8d, [r12+12h]; SubAuthority0
0x180069db3  mov     [rsp+80h+SubAuthority7], r12d; SubAuthority7
0x180069db8  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180069dbc  mov     [rsp+80h+SubAuthority6], r12d; SubAuthority6
0x180069dc1  mov     dl, 1; SubAuthorityCount
0x180069dc3  mov     [rsp+80h+SubAuthority5], r12d; SubAuthority5
0x180069dc8  mov     [rsp+80h+SubAuthority4], r12d; SubAuthority4
0x180069dcd  mov     [rsp+80h+SubAuthority3], r12d; SubAuthority3
0x180069dd2  mov     [rsp+80h+SubAuthority2], r12d; SubAuthority2
0x180069dd7  call    cs:__imp_RtlAllocateAndInitializeSid
0x180069dde  nop     dword ptr [rax+rax+00h]
0x180069de3  mov     ebx, eax
0x180069de5  test    eax, eax
0x180069de7  js      loc_180069F95
0x180069ded  mov     rcx, [rbp+var_18]; Sid
0x180069df1  call    cs:__imp_RtlLengthSid
0x180069df8  nop     dword ptr [rax+rax+00h]
0x180069dfd  mov     rcx, [rbp+pSid]; Sid
0x180069e01  mov     ebx, eax
0x180069e03  call    cs:__imp_RtlLengthSid
0x180069e0a  nop     dword ptr [rax+rax+00h]
0x180069e0f  mov     rcx, [rbp+pSid]; Sid
0x180069e13  add     eax, 18h
0x180069e16  add     ebx, eax
0x180069e18  call    cs:__imp_RtlLengthSid
0x180069e1f  nop     dword ptr [rax+rax+00h]
0x180069e24  mov     rcx, gs:60h
0x180069e2d  xor     edx, edx; Flags
0x180069e2f  lea     r15d, [rax+28h]
0x180069e33  mov     rcx, [rcx+30h]; HeapHandle
0x180069e37  add     r15d, ebx
0x180069e3a  mov     r8d, r15d; Size
0x180069e3d  call    cs:__imp_RtlAllocateHeap
0x180069e44  nop     dword ptr [rax+rax+00h]
0x180069e49  mov     rdi, rax
0x180069e4c  test    rax, rax
0x180069e4f  jnz     short loc_180069E5B
0x180069e51  mov     ebx, 0C000009Ah
0x180069e56  jmp     loc_180069F95
0x180069e5b  lea     rsi, [rax+28h]
0x180069e5f  mov     r8d, 2; AclRevision
0x180069e65  mov     rcx, rsi; Acl
0x180069e68  mov     edx, ebx; AclSize
0x180069e6a  call    cs:__imp_RtlCreateAcl
0x180069e71  nop     dword ptr [rax+rax+00h]
0x180069e76  mov     ebx, eax
0x180069e78  test    eax, eax
0x180069e7a  js      loc_180069F95
0x180069e80  mov     rax, [rbp+pSid]
0x180069e84  xor     r8d, r8d; AceFlags
0x180069e87  mov     r9d, r14d; AccessMask
0x180069e8a  mov     qword ptr [rsp+80h+SubAuthority2], rax; pSid
0x180069e8f  mov     rcx, rsi; pAcl
0x180069e92  lea     edx, [r8+2]; dwAceRevision
0x180069e96  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180069e9d  nop     dword ptr [rax+rax+00h]
0x180069ea2  mov     ebx, eax
0x180069ea4  test    eax, eax
0x180069ea6  js      loc_180069F95
0x180069eac  mov     rax, [rbp+var_18]
0x180069eb0  xor     r8d, r8d; AceFlags
0x180069eb3  mov     r9d, 0F003Fh; AccessMask
0x180069eb9  mov     qword ptr [rsp+80h+SubAuthority2], rax; pSid
0x180069ebe  mov     rcx, rsi; pAcl
0x180069ec1  lea     edx, [r8+2]; dwAceRevision
0x180069ec5  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180069ecc  nop     dword ptr [rax+rax+00h]
0x180069ed1  mov     ebx, eax
0x180069ed3  test    eax, eax
0x180069ed5  js      loc_180069F95
0x180069edb  mov     edx, 1; Revision
0x180069ee0  mov     rcx, rdi; SecurityDescriptor
0x180069ee3  call    cs:__imp_RtlCreateSecurityDescriptor
0x180069eea  nop     dword ptr [rax+rax+00h]
0x180069eef  mov     ebx, eax
0x180069ef1  test    eax, eax
0x180069ef3  js      loc_180069F95
0x180069ef9  xor     r9d, r9d; DaclDefaulted
0x180069efc  mov     r8, rsi; Dacl
0x180069eff  mov     dl, 1; DaclPresent
0x180069f01  mov     rcx, rdi; SecurityDescriptor
0x180069f04  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180069f0b  nop     dword ptr [rax+rax+00h]
0x180069f10  mov     ebx, eax
0x180069f12  test    eax, eax
0x180069f14  js      short loc_180069F95
0x180069f16  mov     rcx, rdi; SecurityDescriptor
0x180069f19  call    cs:__imp_RtlLengthSecurityDescriptor
0x180069f20  nop     dword ptr [rax+rax+00h]
0x180069f25  mov     rcx, [rbp+pSid]; Sid
0x180069f29  mov     ebx, eax
0x180069f2b  call    cs:__imp_RtlLengthSid
0x180069f32  nop     dword ptr [rax+rax+00h]
0x180069f37  add     ebx, eax
0x180069f39  cmp     ebx, r15d
0x180069f3c  jnb     short loc_180069F45
0x180069f3e  mov     ebx, 0C0000023h
0x180069f43  jmp     short loc_180069F95
0x180069f45  mov     rcx, rdi; SecurityDescriptor
0x180069f48  call    cs:__imp_RtlLengthSecurityDescriptor
0x180069f4f  nop     dword ptr [rax+rax+00h]
0x180069f54  mov     rcx, [rbp+pSid]; Sid
0x180069f58  mov     ebx, eax
0x180069f5a  add     rbx, rdi
0x180069f5d  call    cs:__imp_RtlLengthSid
0x180069f64  nop     dword ptr [rax+rax+00h]
0x180069f69  mov     rdx, [rbp+pSid]; Src
0x180069f6d  mov     rcx, rbx; void *
0x180069f70  mov     r8d, eax; Size
0x180069f73  call    memcpy_0
0x180069f78  xor     r8d, r8d; OwnerDefaulted
0x180069f7b  mov     rdx, rbx; Owner
0x180069f7e  mov     rcx, rdi; SecurityDescriptor
0x180069f81  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180069f88  nop     dword ptr [rax+rax+00h]
0x180069f8d  test    eax, eax
0x180069f8f  mov     ebx, eax
0x180069f91  cmovns  ebx, r12d
0x180069f95  mov     rcx, [rbp+pSid]; Sid
0x180069f99  test    rcx, rcx
0x180069f9c  jz      short loc_180069FAA
0x180069f9e  call    cs:__imp_RtlFreeSid
0x180069fa5  nop     dword ptr [rax+rax+00h]
0x180069faa  mov     rcx, [rbp+var_18]; Sid
0x180069fae  test    rcx, rcx
0x180069fb1  jz      short loc_180069FBF
0x180069fb3  call    cs:__imp_RtlFreeSid
0x180069fba  nop     dword ptr [rax+rax+00h]
0x180069fbf  test    ebx, ebx
0x180069fc1  js      short loc_180069FC8
0x180069fc3  mov     rax, rdi
0x180069fc6  jmp     short loc_180069FED
0x180069fc8  test    rdi, rdi
0x180069fcb  jz      short loc_180069FEB
0x180069fcd  mov     rcx, gs:60h
0x180069fd6  mov     r8, rdi; P
0x180069fd9  xor     edx, edx; Flags
0x180069fdb  mov     rcx, [rcx+30h]; HeapHandle
0x180069fdf  call    cs:__imp_RtlFreeHeap
0x180069fe6  nop     dword ptr [rax+rax+00h]
0x180069feb  xor     eax, eax
0x180069fed  mov     rcx, [rbp+var_8]
0x180069ff1  xor     rcx, rsp; StackCookie
0x180069ff4  call    __security_check_cookie
0x180069ff9  lea     r11, [rsp+80h+var_s0]
0x18006a001  mov     rbx, [r11+38h]
0x18006a005  mov     rsi, [r11+40h]
0x18006a009  mov     rsp, r11
0x18006a00c  pop     r15
0x18006a00e  pop     r14
0x18006a010  pop     r12
0x18006a012  pop     rdi
0x18006a013  pop     rbp
0x18006a014  retn
```
