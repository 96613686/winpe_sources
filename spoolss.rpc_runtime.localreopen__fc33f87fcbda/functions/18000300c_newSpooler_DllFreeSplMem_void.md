# newSpooler::DllFreeSplMem(void *)

- ea: `0x18000300c`
- end: `0x18000302c`
- name: `?DllFreeSplMem@newSpooler@@YAHPEAX@Z`
- size: `32`
- prototype: `__int64 __fastcall(newSpooler *__hidden this, void *)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002a94`
- `0x1800047f8`
- `0x18000ff40`
- `0x18000ff80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003010`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003010`

## pseudocode

```c
_BOOL8 __fastcall newSpooler::DllFreeSplMem(newSpooler *this, void *a2)
{
  return LocalFree(this) != 0;
}

```

## disassembly

```asm
0x18000300c  sub     rsp, 28h
0x180003010  call    cs:__imp_LocalFree
0x180003017  nop     dword ptr [rax+rax+00h]
0x18000301c  xor     ecx, ecx
0x18000301e  test    rax, rax
0x180003021  setnz   cl
0x180003024  mov     eax, ecx
0x180003026  add     rsp, 28h
0x18000302a  retn
```
