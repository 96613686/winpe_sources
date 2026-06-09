# Smb2FreeSecurityContext

- ea: `0x140077ba4`
- end: `0x140077c06`
- name: `Smb2FreeSecurityContext`
- size: `98`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140077340`

## callees

- `0x140077ba4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140077bc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140077bc9`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140077bea`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140077bea`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400977b2`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1400977b2`
- `ksecdd!DeleteSecurityContext` at `0x140077bf8`
- `ksecdd!DeleteSecurityContext` at `0x140077bf8`

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
0x140077ba4  push    rbx
0x140077ba6  sub     rsp, 20h
0x140077baa  cmp     byte ptr [rcx+18h], 0
0x140077bae  mov     rbx, rcx
0x140077bb1  jnz     short loc_140077BDC
0x140077bb3  lea     rcx, [rbx+20h]; phContext
0x140077bb7  cmp     qword ptr [rcx], 0
0x140077bbb  jnz     short loc_140077BF8
0x140077bbd  cmp     qword ptr [rbx+28h], 0
0x140077bc2  jnz     short loc_140077BF8
0x140077bc4  xor     edx, edx; Tag
0x140077bc6  mov     rcx, rbx; P
0x140077bc9  call    cs:__imp_ExFreePoolWithTag
0x140077bd0  nop     dword ptr [rax+rax+00h]
0x140077bd5  add     rsp, 20h
0x140077bd9  pop     rbx
0x140077bda  retn
0x140077bdc  cmp     dword ptr [rbx+38h], 1
0x140077be0  mov     rcx, [rcx+30h]; ImpersonationToken
0x140077be4  jnz     loc_1400977B2
0x140077bea  call    cs:__imp_PsDereferencePrimaryToken
0x140077bf1  nop     dword ptr [rax+rax+00h]
0x140077bf6  jmp     short loc_140077BB3
0x140077bf8  call    cs:__imp_DeleteSecurityContext
0x140077bff  nop     dword ptr [rax+rax+00h]
0x140077c04  jmp     short loc_140077BC4
0x1400977b2  call    cs:__imp_PsDereferenceImpersonationToken
0x1400977b9  nop     dword ptr [rax+rax+00h]
0x1400977be  nop
0x1400977bf  jmp     loc_140077BB3
```
