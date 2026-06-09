# CIlKernel32::SetFileTime(void *,_FILETIME const *,_FILETIME const *,_FILETIME const *)

- ea: `0x18000efb0`
- end: `0x18000efcb`
- name: `?SetFileTime@CIlKernel32@@UEAAHPEAXPEBU_FILETIME@@11@Z`
- size: `27`
- prototype: `__int64 __fastcall(CIlKernel32 *__hidden this, void *, const struct _FILETIME *, const struct _FILETIME *, const struct _FILETIME *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000efc4`

## pseudocode

```c
BOOL __fastcall CIlKernel32::SetFileTime(
        CIlKernel32 *this,
        void *a2,
        const struct _FILETIME *a3,
        const struct _FILETIME *a4,
        const struct _FILETIME *a5)
{
  return SetFileTime(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000efb0  mov     rax, r9
0x18000efb3  mov     r10, r8
0x18000efb6  mov     r9, [rsp+arg_20]
0x18000efbb  mov     rcx, rdx
0x18000efbe  mov     r8, rax
0x18000efc1  mov     rdx, r10
0x18000efc4  jmp     cs:__imp_SetFileTime
```
