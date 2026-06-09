# ATL::CComCriticalSection::Init(void)

- ea: `0x18000819c`
- end: `0x1800081c3`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010a0`
- `0x180001310`
- `0x180001340`

## callees

- `0x18000819c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800081a0`
- `KERNEL32!InitializeCriticalSection` at `0x1800081a0`

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
0x18000819c  sub     rsp, 38h
0x1800081a0  call    cs:__imp_InitializeCriticalSection
0x1800081a7  nop     dword ptr [rax+rax+00h]
0x1800081ac  xor     eax, eax
0x1800081ae  mov     [rsp+38h+var_18], eax
0x1800081b2  jmp     short loc_1800081BD
0x1800081b4  mov     eax, 8007000Eh
0x1800081b9  mov     [rsp+38h+var_18], eax
0x1800081bd  add     rsp, 38h
0x1800081c1  retn
```
