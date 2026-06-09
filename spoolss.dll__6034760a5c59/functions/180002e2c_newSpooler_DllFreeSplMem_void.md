# newSpooler::DllFreeSplMem(void *)

- ea: `0x180002e2c`
- end: `0x180002e45`
- name: `?DllFreeSplMem@newSpooler@@YAHPEAX@Z`
- size: `25`
- prototype: `__int64 __fastcall(newSpooler *__hidden this, void *)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002e18`
- `0x180004588`
- `0x18000eee0`
- `0x18000ef20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e30`

## pseudocode

```c
_BOOL8 __fastcall newSpooler::DllFreeSplMem(newSpooler *this, void *a2)
{
  return LocalFree(this) != 0;
}

```

## disassembly

```asm
0x180002e2c  sub     rsp, 28h
0x180002e30  call    cs:__imp_LocalFree
0x180002e36  xor     ecx, ecx
0x180002e38  test    rax, rax
0x180002e3b  setnz   cl
0x180002e3e  mov     eax, ecx
0x180002e40  add     rsp, 28h
0x180002e44  retn
```
