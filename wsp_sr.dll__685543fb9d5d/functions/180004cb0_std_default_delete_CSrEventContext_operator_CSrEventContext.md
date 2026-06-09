# std::default_delete<CSrEventContext>::operator()(CSrEventContext *)

- ea: `0x180004cb0`
- end: `0x180004cd5`
- name: `??R?$default_delete@VCSrEventContext@@@std@@QEBAXPEAVCSrEventContext@@@Z`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c4c`
- `0x180004d1c`

## callees

- `0x180004cb0`
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
0x180004cb0  sub     rsp, 28h
0x180004cb4  mov     r8, rdx
0x180004cb7  test    rdx, rdx
0x180004cba  jz      short loc_180004CCF
0x180004cbc  mov     rax, [rdx]
0x180004cbf  mov     rcx, r8
0x180004cc2  mov     edx, 1
0x180004cc7  mov     rax, [rax]
0x180004cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ccf  add     rsp, 28h
0x180004cd3  retn
```
