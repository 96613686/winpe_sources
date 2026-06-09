# ATL::CComCriticalSection::Init(void)

- ea: `0x1800038ec`
- end: `0x180003913`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010e0`
- `0x180001120`
- `0x180001160`
- `0x1800034a0`
- `0x18000358c`
- `0x180003680`
- `0x1800050c8`
- `0x180006f84`

## callees

- `0x1800038ec`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800038f0`
- `KERNEL32!InitializeCriticalSection` at `0x1800038f0`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x1800038ec  sub     rsp, 38h
0x1800038f0  call    cs:__imp_InitializeCriticalSection
0x1800038f7  nop     dword ptr [rax+rax+00h]
0x1800038fc  xor     eax, eax
0x1800038fe  mov     [rsp+38h+var_18], eax
0x180003902  jmp     short loc_18000390D
0x180003904  mov     eax, 8007000Eh
0x180003909  mov     [rsp+38h+var_18], eax
0x18000390d  add     rsp, 38h
0x180003911  retn
0x18000cd88  push    rbp
0x18000cd8a  sub     rsp, 20h
0x18000cd8e  mov     rbp, rdx
0x18000cd91  mov     rax, [rcx]
0x18000cd94  xor     ecx, ecx
0x18000cd96  cmp     dword ptr [rax], 0C0000017h
0x18000cd9c  setz    cl
0x18000cd9f  mov     eax, ecx
0x18000cda1  add     rsp, 20h
0x18000cda5  pop     rbp
0x18000cda6  retn
```
