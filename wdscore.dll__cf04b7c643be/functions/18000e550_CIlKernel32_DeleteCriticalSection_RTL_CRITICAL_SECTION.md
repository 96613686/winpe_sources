# CIlKernel32::DeleteCriticalSection(_RTL_CRITICAL_SECTION *)

- ea: `0x18000e550`
- end: `0x18000e55a`
- name: `?DeleteCriticalSection@CIlKernel32@@UEAAXPEAU_RTL_CRITICAL_SECTION@@@Z`
- size: `10`
- prototype: `void __fastcall(CIlKernel32 *__hidden this, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e553`

## pseudocode

```c
void __fastcall CIlKernel32::DeleteCriticalSection(CIlKernel32 *this, struct _RTL_CRITICAL_SECTION *a2)
{
  DeleteCriticalSection(a2);
}

```

## disassembly

```asm
0x18000e550  mov     rcx, rdx
0x18000e553  jmp     cs:__imp_DeleteCriticalSection
```
