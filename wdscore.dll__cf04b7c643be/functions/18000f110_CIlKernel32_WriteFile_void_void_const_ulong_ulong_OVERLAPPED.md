# CIlKernel32::WriteFile(void *,void const *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x18000f110`
- end: `0x18000f13d`
- name: `?WriteFile@CIlKernel32@@UEAAHPEAXPEBXKPEAKPEAU_OVERLAPPED@@@Z`
- size: `45`
- prototype: `__int64 __fastcall(CIlKernel32 *__hidden this, void *, const void *, unsigned int, unsigned int *, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000f131`

## pseudocode

```c
BOOL __fastcall CIlKernel32::WriteFile(
        CIlKernel32 *this,
        void *a2,
        const void *a3,
        DWORD a4,
        unsigned int *a5,
        struct _OVERLAPPED *a6)
{
  return WriteFile(a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x18000f110  push    rbx
0x18000f112  mov     rax, [rsp+8+arg_28]
0x18000f117  mov     r10d, r9d
0x18000f11a  mov     r9, [rsp+8+arg_20]
0x18000f11f  mov     r11, r8
0x18000f122  mov     rcx, rdx
0x18000f125  mov     [rsp+8+arg_20], rax
0x18000f12a  mov     r8d, r10d
0x18000f12d  mov     rdx, r11
0x18000f130  pop     rbx
0x18000f131  jmp     cs:__imp_WriteFile
```
