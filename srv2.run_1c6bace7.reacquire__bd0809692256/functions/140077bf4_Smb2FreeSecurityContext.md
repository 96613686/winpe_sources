# Smb2FreeSecurityContext

- ea: `0x140077bf4`
- end: `0x140077c56`
- name: `Smb2FreeSecurityContext`
- size: `98`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140077390`

## callees

- `0x140077bf4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140077c19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077c19`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140077c3a`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140077c3a`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140097802`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140097802`
- `ksecdd!DeleteSecurityContext` at `0x140077c48`
- `ksecdd!DeleteSecurityContext` at `0x140077c48`

## pseudocode

```c
void __fastcall Smb2FreeSecurityContext(struct _SecHandle *P)
{
  void *dwLower; // rcx

  if ( LOBYTE(P[1].dwUpper) )
  {
    dwLower = (void *)P[3].dwLower;
    if ( LODWORD(P[3].dwUpper) == 1 )
      PsDereferencePrimaryToken(dwLower);
    else
      PsDereferenceImpersonationToken(dwLower);
  }
  if ( P[2].dwLower || P[2].dwUpper )
    DeleteSecurityContext(P + 2);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140077bf4  push    rbx
0x140077bf6  sub     rsp, 20h
0x140077bfa  cmp     byte ptr [rcx+18h], 0
0x140077bfe  mov     rbx, rcx
0x140077c01  jnz     short loc_140077C2C
0x140077c03  lea     rcx, [rbx+20h]; phContext
0x140077c07  cmp     qword ptr [rcx], 0
0x140077c0b  jnz     short loc_140077C48
0x140077c0d  cmp     qword ptr [rbx+28h], 0
0x140077c12  jnz     short loc_140077C48
0x140077c14  xor     edx, edx; Tag
0x140077c16  mov     rcx, rbx; P
0x140077c19  call    cs:__imp_ExFreePoolWithTag
0x140077c20  nop     dword ptr [rax+rax+00h]
0x140077c25  add     rsp, 20h
0x140077c29  pop     rbx
0x140077c2a  retn
0x140077c2c  cmp     dword ptr [rbx+38h], 1
0x140077c30  mov     rcx, [rcx+30h]; ImpersonationToken
0x140077c34  jnz     loc_140097802
0x140077c3a  call    cs:__imp_PsDereferencePrimaryToken
0x140077c41  nop     dword ptr [rax+rax+00h]
0x140077c46  jmp     short loc_140077C03
0x140077c48  call    cs:__imp_DeleteSecurityContext
0x140077c4f  nop     dword ptr [rax+rax+00h]
0x140077c54  jmp     short loc_140077C14
0x140097802  call    cs:__imp_PsDereferenceImpersonationToken
0x140097809  nop     dword ptr [rax+rax+00h]
0x14009780e  nop
0x14009780f  jmp     loc_140077C03
```
