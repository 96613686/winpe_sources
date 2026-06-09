# std::default_delete<CSrEventContext>::operator()(CSrEventContext *)

- ea: `0x180004cfc`
- end: `0x180004d20`
- name: `??R?$default_delete@VCSrEventContext@@@std@@QEBAXPEAVCSrEventContext@@@Z`
- size: `36`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall ***)(_QWORD, __int64))`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c24`
- `0x180004c9c`
- `0x180004d70`
- `0x180004f00`
- `0x180005000`
- `0x180005190`
- `0x180005290`
- `0x180005420`

## callees

- `0x180004cfc`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall std::default_delete<CSrEventContext>::operator()(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64))
{
  __int64 result; // rax

  if ( a2 )
    return (**a2)(a2, 1);
  return result;
}

```

## disassembly

```asm
0x180004cfc  sub     rsp, 28h
0x180004d00  mov     r8, rdx
0x180004d03  test    rdx, rdx
0x180004d06  jz      short loc_180004D1B
0x180004d08  mov     rax, [rdx]
0x180004d0b  mov     rcx, r8
0x180004d0e  mov     edx, 1
0x180004d13  mov     rax, [rax]
0x180004d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d1b  add     rsp, 28h
0x180004d1f  retn
```
