# CSecDesc::GetDacl(_ACL * *,int *)

- ea: `0x1800242a0`
- end: `0x1800242fe`
- name: `?GetDacl@CSecDesc@@QEAAKPEAPEAU_ACL@@PEAH@Z`
- size: `94`
- prototype: `unsigned int(CSecDesc *__hidden this, struct _ACL **, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800242a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800242d5`
- `KERNEL32!GetLastError` at `0x1800242d5`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800242c5`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800242c5`

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
0x1800242a0  mov     rax, rsp
0x1800242a3  mov     [rax+10h], rbx
0x1800242a7  push    rdi
0x1800242a8  sub     rsp, 20h
0x1800242ac  mov     rcx, [rcx]; pSecurityDescriptor
0x1800242af  lea     r9, [rax+20h]; lpbDaclDefaulted
0x1800242b3  mov     rdi, r8
0x1800242b6  xor     ebx, ebx
0x1800242b8  mov     r8, rdx; pDacl
0x1800242bb  mov     [rax+8], ebx
0x1800242be  lea     rdx, [rax+8]; lpbDaclPresent
0x1800242c2  mov     [rax+20h], ebx
0x1800242c5  call    cs:__imp_GetSecurityDescriptorDacl
0x1800242cc  nop     dword ptr [rax+rax+00h]
0x1800242d1  test    eax, eax
0x1800242d3  jnz     short loc_1800242E5
0x1800242d5  call    cs:__imp_GetLastError
0x1800242dc  nop     dword ptr [rax+rax+00h]
0x1800242e1  mov     ebx, eax
0x1800242e3  jmp     short loc_1800242F0
0x1800242e5  test    rdi, rdi
0x1800242e8  jz      short loc_1800242F0
0x1800242ea  mov     eax, [rsp+28h+arg_0]
0x1800242ee  mov     [rdi], eax
0x1800242f0  mov     eax, ebx
0x1800242f2  mov     rbx, [rsp+28h+arg_8]
0x1800242f7  add     rsp, 20h
0x1800242fb  pop     rdi
0x1800242fc  retn
```
