# SC_ENV_ALLOCATOR::operator delete[](void *)

- ea: `0x14001e4a0`
- end: `0x14001e4b8`
- name: `??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z`
- size: `24`
- prototype: `void __fastcall(void *)`
- caller_count: `54`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x14008c1c0`
- `0x14008c8f0`
- `0x14008e850`
- `0x140090394`
- `0x140090ab0`
- `0x140090be8`
- `0x140091018`
- `0x1400911c4`
- `0x140091320`
- `0x140091da4`
- `0x14009256c`
- `0x1400927e0`
- `0x140092fbc`
- `0x14009ad44`
- `0x14009bf7c`
- `0x14009c40c`
- `0x14009cb5c`
- `0x14009d1dc`
- `0x14009e3e4`
- `0x14009f818`
- `0x1400a0a10`
- `0x1400a1bd8`
- `0x1400a219c`
- `0x1400a2740`
- `0x1400a3958`
- `0x1400a43d4`
- `0x1400a4ea4`
- `0x1400a56b0`
- `0x1400a5b2c`
- `0x1400a70b4`
- `0x1400a84c0`
- `0x1400aa6a0`
- `0x1400aa774`
- `0x1400aa7c4`
- `0x1400aaad8`
- `0x1400aaf54`
- `0x1400ab340`
- `0x1400ab3f0`
- `0x1400abb28`
- `0x1400ac018`
- `0x1400ac6f0`
- `0x1400ad424`
- `0x1400ada94`
- `0x1400afb04`
- `0x1400b03bc`
- `0x1400b1af8`
- `0x1400b2420`
- `0x1400b3108`
- `0x1400b3430`
- `0x1400b4000`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4a6`

## pseudocode

```c
void __fastcall SC_ENV_ALLOCATOR::operator delete[](void *a1)
{
  ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x14001e4a0  sub     rsp, 28h
0x14001e4a4  xor     edx, edx; Tag
0x14001e4a6  call    cs:__imp_ExFreePoolWithTag
0x14001e4ad  nop     dword ptr [rax+rax+00h]
0x14001e4b2  add     rsp, 28h
0x14001e4b6  retn
```
