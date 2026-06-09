# CSecDesc::GetDacl(_ACL * *,int *)

- ea: `0x180023200`
- end: `0x18002325e`
- name: `?GetDacl@CSecDesc@@QEAAKPEAPEAU_ACL@@PEAH@Z`
- size: `94`
- prototype: `unsigned int(CSecDesc *__hidden this, struct _ACL **, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180023200`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180023235`
- `KERNEL32!GetLastError` at `0x180023235`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180023225`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180023225`

## pseudocode

```c
__int64 __fastcall CSecDesc::GetDacl(void **this, struct _ACL **a2, int *a3)
{
  void *v3; // rcx
  unsigned int v5; // ebx
  WINBOOL v7; // [rsp+30h] [rbp+8h] BYREF
  WINBOOL v8; // [rsp+48h] [rbp+20h] BYREF

  v3 = *this;
  v5 = 0;
  v7 = 0;
  v8 = 0;
  if ( GetSecurityDescriptorDacl(v3, &v7, a2, &v8) )
  {
    if ( a3 )
      *a3 = v7;
  }
  else
  {
    return GetLastError();
  }
  return v5;
}

```

## disassembly

```asm
0x180023200  mov     rax, rsp
0x180023203  mov     [rax+10h], rbx
0x180023207  push    rdi
0x180023208  sub     rsp, 20h
0x18002320c  mov     rcx, [rcx]; pSecurityDescriptor
0x18002320f  lea     r9, [rax+20h]; lpbDaclDefaulted
0x180023213  mov     rdi, r8
0x180023216  xor     ebx, ebx
0x180023218  mov     r8, rdx; pDacl
0x18002321b  mov     [rax+8], ebx
0x18002321e  lea     rdx, [rax+8]; lpbDaclPresent
0x180023222  mov     [rax+20h], ebx
0x180023225  call    cs:__imp_GetSecurityDescriptorDacl
0x18002322c  nop     dword ptr [rax+rax+00h]
0x180023231  test    eax, eax
0x180023233  jnz     short loc_180023245
0x180023235  call    cs:__imp_GetLastError
0x18002323c  nop     dword ptr [rax+rax+00h]
0x180023241  mov     ebx, eax
0x180023243  jmp     short loc_180023250
0x180023245  test    rdi, rdi
0x180023248  jz      short loc_180023250
0x18002324a  mov     eax, [rsp+28h+arg_0]
0x18002324e  mov     [rdi], eax
0x180023250  mov     eax, ebx
0x180023252  mov     rbx, [rsp+28h+arg_8]
0x180023257  add     rsp, 20h
0x18002325b  pop     rdi
0x18002325c  retn
```
