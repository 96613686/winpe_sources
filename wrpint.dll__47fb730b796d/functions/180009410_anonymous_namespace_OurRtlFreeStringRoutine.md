# _anonymous_namespace_::OurRtlFreeStringRoutine

- ea: `0x180009410`
- end: `0x180009429`
- name: `_anonymous_namespace_::OurRtlFreeStringRoutine`
- size: `25`
- prototype: `BOOLEAN __fastcall(void *)`
- caller_count: `7`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002500`
- `0x180004abc`
- `0x180008e30`
- `0x180015e00`
- `0x180016478`
- `0x18001a260`
- `0x18001b30c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180009422`

## pseudocode

```c
BOOLEAN __fastcall anonymous_namespace_::OurRtlFreeStringRoutine(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180009410  mov     rax, gs:60h
0x180009419  mov     r8, rcx
0x18000941c  xor     edx, edx
0x18000941e  mov     rcx, [rax+30h]
0x180009422  jmp     cs:__imp_RtlFreeHeap
```
