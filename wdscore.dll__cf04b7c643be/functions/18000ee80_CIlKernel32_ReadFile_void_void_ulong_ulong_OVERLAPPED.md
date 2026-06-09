# CIlKernel32::ReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x18000ee80`
- end: `0x18000eead`
- name: `?ReadFile@CIlKernel32@@UEAAHPEAX0KPEAKPEAU_OVERLAPPED@@@Z`
- size: `45`
- prototype: `__int64 __fastcall(CIlKernel32 *__hidden this, void *, void *, unsigned int, unsigned int *, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000eea1`

## pseudocode

```c
BOOL __fastcall CIlKernel32::ReadFile(
        CIlKernel32 *this,
        void *a2,
        void *a3,
        DWORD a4,
        unsigned int *a5,
        struct _OVERLAPPED *a6)
{
  return ReadFile(a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x18000ee80  push    rbx
0x18000ee82  mov     rax, [rsp+8+arg_28]
0x18000ee87  mov     r10d, r9d
0x18000ee8a  mov     r9, [rsp+8+arg_20]
0x18000ee8f  mov     r11, r8
0x18000ee92  mov     rcx, rdx
0x18000ee95  mov     [rsp+8+arg_20], rax
0x18000ee9a  mov     r8d, r10d
0x18000ee9d  mov     rdx, r11
0x18000eea0  pop     rbx
0x18000eea1  jmp     cs:__imp_ReadFile
```
