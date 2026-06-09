# CIlKernel32::MoveFileW(ushort const *,ushort const *)

- ea: `0x18000edf0`
- end: `0x18000ee03`
- name: `?MoveFileW@CIlKernel32@@UEAAHPEBG0@Z`
- size: `19`
- prototype: `__int64 __fastcall(CIlKernel32 *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000edfc`

## pseudocode

```c
BOOL __fastcall CIlKernel32::MoveFileW(CIlKernel32 *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  return MoveFileExW(a2, a3, 0);
}

```

## disassembly

```asm
0x18000edf0  mov     rax, r8
0x18000edf3  mov     rcx, rdx
0x18000edf6  mov     rdx, rax
0x18000edf9  xor     r8d, r8d
0x18000edfc  jmp     cs:__imp_MoveFileExW
```
