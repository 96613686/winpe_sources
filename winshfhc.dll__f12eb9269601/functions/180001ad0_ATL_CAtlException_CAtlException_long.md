# ATL::CAtlException::CAtlException(long)

- ea: `0x180001ad0`
- end: `0x180001ada`
- name: `??0CAtlException@ATL@@QEAA@J@Z`
- size: `10`
- prototype: `__int64 __fastcall(ATL::CAtlException *__hidden this, int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b24`

## pseudocode

```c
ATL::CAtlException *__fastcall ATL::CAtlException::CAtlException(ATL::CAtlException *this)
{
  *(_DWORD *)this = -2147024882;
  return this;
}

```

## disassembly

```asm
0x180001ad0  mov     dword ptr [rcx], 8007000Eh
0x180001ad6  mov     rax, rcx
0x180001ad9  retn
```
