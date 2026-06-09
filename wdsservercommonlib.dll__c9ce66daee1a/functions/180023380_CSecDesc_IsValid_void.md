# CSecDesc::IsValid(void *)

- ea: `0x180023380`
- end: `0x1800233d0`
- name: `?IsValid@CSecDesc@@SAKPEAX@Z`
- size: `80`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800230d0`

## callees

- `0x180023380`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x18002338f`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18002338f`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800233a9`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800233a9`

## pseudocode

```c
__int64 __fastcall CSecDesc::IsValid(PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( IsValidSecurityDescriptor(pSecurityDescriptor) )
  {
    if ( GetSecurityDescriptorLength(pSecurityDescriptor) < 0x28 )
      return 1338;
    return v2;
  }
  else
  {
    return 1338;
  }
}

```

## disassembly

```asm
0x180023380  mov     [rsp+arg_0], rbx
0x180023385  push    rdi
0x180023386  sub     rsp, 20h
0x18002338a  mov     rdi, rcx
0x18002338d  xor     ebx, ebx
0x18002338f  call    cs:__imp_IsValidSecurityDescriptor
0x180023396  nop     dword ptr [rax+rax+00h]
0x18002339b  test    eax, eax
0x18002339d  jnz     short loc_1800233A6
0x18002339f  mov     ecx, 53Ah
0x1800233a4  jmp     short loc_1800233C2
0x1800233a6  mov     rcx, rdi; pSecurityDescriptor
0x1800233a9  call    cs:__imp_GetSecurityDescriptorLength
0x1800233b0  nop     dword ptr [rax+rax+00h]
0x1800233b5  mov     ecx, 53Ah
0x1800233ba  cmp     eax, 28h ; '('
0x1800233bd  cmovb   ebx, ecx
0x1800233c0  mov     ecx, ebx
0x1800233c2  mov     rbx, [rsp+28h+arg_0]
0x1800233c7  mov     eax, ecx
0x1800233c9  add     rsp, 20h
0x1800233cd  pop     rdi
0x1800233ce  retn
```
