# ATL::CAcl::CAce::ObjectType(void)

- ea: `0x1400097e0`
- end: `0x1400097ef`
- name: `?ObjectType@CAce@CAcl@ATL@@UEBA?AU_GUID@@XZ`
- size: `15`
- prototype: `struct _GUID *__fastcall(ATL::CAcl::CAce *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
struct _GUID *__fastcall ATL::CAcl::CAce::ObjectType(ATL::CAcl::CAce *this, struct _GUID *__return_ptr retstr)
{
  struct _GUID *result; // rax

  result = retstr;
  *retstr = GUID_NULL;
  return result;
}

```

## disassembly

```asm
0x1400097e0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400097e7  mov     rax, rdx
0x1400097ea  movdqu  xmmword ptr [rdx], xmm0
0x1400097ee  retn
```
