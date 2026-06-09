# CIlKernel32::SetFilePointer(void *,long,long *,ulong)

- ea: `0x18000ef80`
- end: `0x18000ef9b`
- name: `?SetFilePointer@CIlKernel32@@UEAAKPEAXJPEAJK@Z`
- size: `27`
- prototype: `unsigned int __fastcall(CIlKernel32 *__hidden this, void *, int, int *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000ef94`

## pseudocode

```c
DWORD __fastcall CIlKernel32::SetFilePointer(CIlKernel32 *this, void *a2, LONG a3, int *a4, DWORD a5)
{
  return SetFilePointer(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000ef80  mov     rax, r9
0x18000ef83  mov     r10d, r8d
0x18000ef86  mov     r9d, [rsp+arg_20]
0x18000ef8b  mov     rcx, rdx
0x18000ef8e  mov     r8, rax
0x18000ef91  mov     edx, r10d
0x18000ef94  jmp     cs:__imp_SetFilePointer
```
