# CIlKernel32::HeapCompact(void *,ulong)

- ea: `0x18000ec40`
- end: `0x18000ec4d`
- name: `?HeapCompact@CIlKernel32@@UEAA_KPEAXK@Z`
- size: `13`
- prototype: `unsigned __int64 __fastcall(CIlKernel32 *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCompact` at `0x18000ec46`

## pseudocode

```c
SIZE_T __fastcall CIlKernel32::HeapCompact(CIlKernel32 *this, void *a2, DWORD a3)
{
  return HeapCompact(a2, a3);
}

```

## disassembly

```asm
0x18000ec40  mov     rcx, rdx
0x18000ec43  mov     edx, r8d
0x18000ec46  jmp     cs:__imp_HeapCompact
```
