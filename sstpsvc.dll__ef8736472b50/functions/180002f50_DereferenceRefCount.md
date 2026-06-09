# DereferenceRefCount

- ea: `0x180002f50`
- end: `0x180002f73`
- name: `DereferenceRefCount`
- size: `35`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012b0`
- `0x180002320`
- `0x180002aac`
- `0x180003620`
- `0x18000a300`
- `0x18000afb0`
- `0x18000b9c8`
- `0x18000c4c4`
- `0x18000c768`
- `0x18000ca68`
- `0x18000da7c`
- `0x18000dd70`
- `0x18000ebd0`
- `0x18000f6e0`

## callees

- `0x180002f50`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall DereferenceRefCount(__int64 a1)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return (*(__int64 (**)(void))(a1 + 8))();
  return result;
}

```

## disassembly

```asm
0x180002f50  sub     rsp, 28h
0x180002f54  mov     eax, 0FFFFFFFFh
0x180002f59  lock xadd [rcx], eax
0x180002f5d  cmp     eax, 1
0x180002f60  jz      short loc_180002F68
0x180002f62  add     rsp, 28h
0x180002f66  retn
0x180002f68  mov     rax, [rcx+8]
0x180002f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f71  jmp     short loc_180002F62
```
