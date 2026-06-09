# SC_ENV_ALLOCATOR::operator delete[](void *)

- ea: `0x14001e4a0`
- end: `0x14001e4b8`
- name: `??_VSC_ENV_ALLOCATOR@@SAXPEAX@Z`
- size: `24`
- prototype: `void __fastcall(void *)`
- caller_count: `55`
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
- `0x14009cb78`
- `0x14009d1fc`
- `0x14009e404`
- `0x14009f82c`
- `0x14009fd68`
- `0x1400a0b40`
- `0x1400a1d08`
- `0x1400a22cc`
- `0x1400a2870`
- `0x1400a3a88`
- `0x1400a4504`
- `0x1400a4fd4`
- `0x1400a57e0`
- `0x1400a5c5c`
- `0x1400a71e4`
- `0x1400a8650`
- `0x1400aa840`
- `0x1400aa914`
- `0x1400aa964`
- `0x1400aac78`
- `0x1400ab0f4`
- `0x1400ab4e0`
- `0x1400ab590`
- `0x1400abcc8`
- `0x1400ac1b8`
- `0x1400ac890`
- `0x1400ad5c4`
- `0x1400adc34`
- `0x1400afca4`
- `0x1400b055c`
- `0x1400b1c98`
- `0x1400b25c0`
- `0x1400b32a8`
- `0x1400b35d0`

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
