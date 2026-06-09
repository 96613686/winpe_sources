# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140009368`
- end: `0x14000938c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `36`
- prototype: `void *__fastcall(SIZE_T NumberOfBytes, const struct std::nothrow_t *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x14000894c`
- `0x14000899c`
- `0x140008a18`
- `0x140008a8c`
- `0x14000a7a4`
- `0x14000a8c4`
- `0x14000bfb8`
- `0x14000c0c0`
- `0x14000c1d8`
- `0x14000c2bc`
- `0x14000cad0`
- `0x14000ce88`
- `0x14000cfa0`
- `0x14000d5e0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000937a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000937a`

## pseudocode

```c
PVOID __fastcall operator new(SIZE_T NumberOfBytes, const struct std::nothrow_t *a2)
{
  return ExAllocatePoolWithTag(PagedPool, NumberOfBytes, 0x6E6D7377u);
}

```

## disassembly

```asm
0x140009368  sub     rsp, 28h
0x14000936c  mov     rdx, rcx; NumberOfBytes
0x14000936f  mov     r8d, 6E6D7377h; Tag
0x140009375  mov     ecx, 1; PoolType
0x14000937a  call    cs:__imp_ExAllocatePoolWithTag
0x140009381  nop     dword ptr [rax+rax+00h]
0x140009386  add     rsp, 28h
0x14000938a  retn
```
