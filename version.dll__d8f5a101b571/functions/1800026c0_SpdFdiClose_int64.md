# SpdFdiClose(__int64)

- ea: `0x1800026c0`
- end: `0x1800026d1`
- name: `?SpdFdiClose@@YAH_J@Z`
- size: `17`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!_lclose` at `0x1800026c4`
- `KERNEL32!_lclose` at `0x1800026c4`

## pseudocode

```c
__int64 __fastcall SpdFdiClose(HFILE a1)
{
  _lclose(a1);
  return 0;
}

```

## disassembly

```asm
0x1800026c0  sub     rsp, 28h
0x1800026c4  call    cs:__imp__lclose
0x1800026ca  xor     eax, eax
0x1800026cc  add     rsp, 28h
0x1800026d0  retn
```
