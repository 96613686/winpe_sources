# WARMUP_APPLICATION_CONTEXT::QueryRemapRequestsDuringWarmup(void)

- ea: `0x180004590`
- end: `0x180004599`
- name: `?QueryRemapRequestsDuringWarmup@WARMUP_APPLICATION_CONTEXT@@UEAAHXZ`
- size: `9`
- prototype: `_BOOL8 __fastcall(WARMUP_APPLICATION_CONTEXT *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
_BOOL8 __fastcall WARMUP_APPLICATION_CONTEXT::QueryRemapRequestsDuringWarmup(WARMUP_APPLICATION_CONTEXT *this)
{
  return *((_DWORD *)this + 18) != 0;
}

```

## disassembly

```asm
0x180004590  xor     eax, eax
0x180004592  cmp     [rcx+48h], eax
0x180004595  setnz   al
0x180004598  retn
```
