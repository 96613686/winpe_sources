# SddlAddScopedPolicyIDAce

- ea: `0x180021b58`
- end: `0x180021ca3`
- name: `SddlAddScopedPolicyIDAce`
- size: `331`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, PSID Sid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180006680`

## callees

- `0x180021b58`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180021c65`
- `ntdll!RtlCopySid` at `0x180021c65`
- `ntdll!RtlValidSid` at `0x180021b9a`
- `ntdll!RtlValidSid` at `0x180021b9a`
- `ntdll!RtlValidAcl` at `0x180021bf7`
- `ntdll!RtlValidAcl` at `0x180021bf7`
- `ntdll!RtlLengthSid` at `0x180021c1a`
- `ntdll!RtlLengthSid` at `0x180021c56`
- `ntdll!RtlLengthSid` at `0x180021c1a`
- `ntdll!RtlLengthSid` at `0x180021c56`
- `ntdll!RtlFirstFreeAce` at `0x180021c0d`
- `ntdll!RtlFirstFreeAce` at `0x180021c0d`

## pseudocode

```c
__int64 __fastcall SddlAddScopedPolicyIDAce(PACL Acl, __int64 a2, int a3, int a4, char *Sid)
{
  __int64 result; // rax
  int v9; // ecx
  BYTE AclRevision; // bp
  __int16 v11; // ax
  PACE v12; // rbx
  __int64 v13; // rdx
  ULONG v14; // eax
  PACE Ace; // [rsp+20h] [rbp-28h] BYREF

  Ace = 0;
  if ( !Acl )
    return 3221225591LL;
  if ( !RtlValidSid(Sid) )
    return 3221225592LL;
  v9 = *(_DWORD *)(Sid + 2);
  if ( !v9 )
    v9 = *((unsigned __int16 *)Sid + 3) - 4352;
  if ( v9 )
    return 3221225485LL;
  if ( Acl->AclRevision > 4u )
    return 3221225561LL;
  AclRevision = 2;
  if ( Acl->AclRevision > 2u )
    AclRevision = Acl->AclRevision;
  if ( (a3 & 0xFFFFFFE0) != 0 || a4 )
    return 3221225485LL;
  if ( !RtlValidAcl(Acl) || !RtlFirstFreeAce(Acl, &Ace) )
    return 3221225591LL;
  v11 = RtlLengthSid(Sid);
  v12 = Ace;
  if ( !Ace )
    return 3221225625LL;
  v13 = (unsigned __int16)(v11 + 8);
  if ( (char *)Ace + v13 > (char *)Acl + Acl->AclSize )
    return 3221225625LL;
  Ace->Header.AceFlags = a3;
  v12->Header.AceType = 19;
  v12->Header.AceSize = v13;
  v12->AccessMask = 0;
  v14 = RtlLengthSid(Sid);
  RtlCopySid(v14, &v12[1], Sid);
  ++Acl->AceCount;
  result = 0;
  Acl->AclRevision = AclRevision;
  return result;
}

```

## disassembly

```asm
0x180021b58  mov     rax, rsp
0x180021b5b  mov     [rax+10h], rbx
0x180021b5f  mov     [rax+18h], rbp
0x180021b63  push    rsi
0x180021b64  push    rdi
0x180021b65  push    r14
0x180021b67  sub     rsp, 30h
0x180021b6b  mov     qword ptr [rax-28h], 0
0x180021b73  mov     ebx, r9d
0x180021b76  mov     dword ptr [rax+8], 0
0x180021b7d  mov     r14d, r8d
0x180021b80  mov     word ptr [rax+0Ch], 1100h
0x180021b86  mov     rdi, rcx
0x180021b89  test    rcx, rcx
0x180021b8c  jz      loc_180021C8B
0x180021b92  mov     rsi, [rsp+48h+Sid]
0x180021b97  mov     rcx, rsi; Sid
0x180021b9a  call    cs:__imp_RtlValidSid
0x180021ba0  test    al, al
0x180021ba2  jnz     short loc_180021BAE
0x180021ba4  mov     eax, 0C0000078h
0x180021ba9  jmp     loc_180021C90
0x180021bae  mov     ecx, [rsi+2]
0x180021bb1  sub     ecx, [rsp+48h+arg_0]
0x180021bb5  jnz     short loc_180021BC2
0x180021bb7  movzx   ecx, word ptr [rsi+6]
0x180021bbb  movzx   eax, [rsp+48h+arg_4]
0x180021bc0  sub     ecx, eax
0x180021bc2  test    ecx, ecx
0x180021bc4  jnz     loc_180021C84
0x180021bca  cmp     byte ptr [rdi], 4
0x180021bcd  ja      loc_180021C7D
0x180021bd3  movzx   eax, byte ptr [rdi]
0x180021bd6  lea     ebp, [rcx+2]
0x180021bd9  cmp     [rdi], bpl
0x180021bdc  cmova   ebp, eax
0x180021bdf  test    r14d, 0FFFFFFE0h
0x180021be6  jnz     loc_180021C84
0x180021bec  test    ebx, ebx
0x180021bee  jnz     loc_180021C84
0x180021bf4  mov     rcx, rdi; Acl
0x180021bf7  call    cs:__imp_RtlValidAcl
0x180021bfd  test    al, al
0x180021bff  jz      loc_180021C8B
0x180021c05  lea     rdx, [rsp+48h+Ace]; Ace
0x180021c0a  mov     rcx, rdi; Acl
0x180021c0d  call    cs:__imp_RtlFirstFreeAce
0x180021c13  test    al, al
0x180021c15  jz      short loc_180021C8B
0x180021c17  mov     rcx, rsi; Sid
0x180021c1a  call    cs:__imp_RtlLengthSid
0x180021c20  mov     rbx, [rsp+48h+Ace]
0x180021c25  test    rbx, rbx
0x180021c28  jz      short loc_180021C76
0x180021c2a  movzx   ecx, word ptr [rdi+2]
0x180021c2e  add     ax, 8
0x180021c32  movzx   edx, ax
0x180021c35  add     rcx, rdi
0x180021c38  lea     rax, [rbx+rdx]
0x180021c3c  cmp     rax, rcx
0x180021c3f  ja      short loc_180021C76
0x180021c41  mov     rcx, rsi; Sid
0x180021c44  mov     [rbx+1], r14b
0x180021c48  mov     byte ptr [rbx], 13h
0x180021c4b  mov     [rbx+2], dx
0x180021c4f  mov     dword ptr [rbx+4], 0
0x180021c56  call    cs:__imp_RtlLengthSid
0x180021c5c  mov     r8, rsi; SourceSid
0x180021c5f  lea     rdx, [rbx+8]; DestinationSid
0x180021c63  mov     ecx, eax; DestinationSidLength
0x180021c65  call    cs:__imp_RtlCopySid
0x180021c6b  inc     word ptr [rdi+4]
0x180021c6f  xor     eax, eax
0x180021c71  mov     [rdi], bpl
0x180021c74  jmp     short loc_180021C90
0x180021c76  mov     eax, 0C0000099h
0x180021c7b  jmp     short loc_180021C90
0x180021c7d  mov     eax, 0C0000059h
0x180021c82  jmp     short loc_180021C90
0x180021c84  mov     eax, 0C000000Dh
0x180021c89  jmp     short loc_180021C90
0x180021c8b  mov     eax, 0C0000077h
0x180021c90  mov     rbx, [rsp+48h+arg_8]
0x180021c95  mov     rbp, [rsp+48h+arg_10]
0x180021c9a  add     rsp, 30h
0x180021c9e  pop     r14
0x180021ca0  pop     rdi
0x180021ca1  pop     rsi
0x180021ca2  retn
```
