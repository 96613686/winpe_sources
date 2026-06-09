# CSecDesc::IsValid(void *)

- ea: `0x180024420`
- end: `0x180024470`
- name: `?IsValid@CSecDesc@@SAKPEAX@Z`
- size: `80`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024160`

## callees

- `0x180024420`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x18002442f`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18002442f`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180024449`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180024449`

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
0x180024420  mov     [rsp+arg_0], rbx
0x180024425  push    rdi
0x180024426  sub     rsp, 20h
0x18002442a  mov     rdi, rcx
0x18002442d  xor     ebx, ebx
0x18002442f  call    cs:__imp_IsValidSecurityDescriptor
0x180024436  nop     dword ptr [rax+rax+00h]
0x18002443b  test    eax, eax
0x18002443d  jnz     short loc_180024446
0x18002443f  mov     ecx, 53Ah
0x180024444  jmp     short loc_180024462
0x180024446  mov     rcx, rdi; pSecurityDescriptor
0x180024449  call    cs:__imp_GetSecurityDescriptorLength
0x180024450  nop     dword ptr [rax+rax+00h]
0x180024455  mov     ecx, 53Ah
0x18002445a  cmp     eax, 28h ; '('
0x18002445d  cmovb   ebx, ecx
0x180024460  mov     ecx, ebx
0x180024462  mov     rbx, [rsp+28h+arg_0]
0x180024467  mov     eax, ecx
0x180024469  add     rsp, 20h
0x18002446d  pop     rdi
0x18002446e  retn
```
