# CIlKernel32::HeapCreate(ulong,unsigned __int64,unsigned __int64)

- ea: `0x18000ec60`
- end: `0x18000ec72`
- name: `?HeapCreate@CIlKernel32@@UEAAPEAXK_K0@Z`
- size: `18`
- prototype: `void *__fastcall(CIlKernel32 *__hidden this, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000ec6b`

## pseudocode

```c
HANDLE __fastcall CIlKernel32::HeapCreate(CIlKernel32 *this, DWORD a2, SIZE_T a3, SIZE_T a4)
{
  return HeapCreate(a2, a3, a4);
}

```

## disassembly

```asm
0x18000ec60  mov     rax, r8
0x18000ec63  mov     ecx, edx
0x18000ec65  mov     rdx, rax
0x18000ec68  mov     r8, r9
0x18000ec6b  jmp     cs:__imp_HeapCreate
```
