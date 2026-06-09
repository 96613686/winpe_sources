# std::unique_ptr<CSrEventListener,std::default_delete<CSrEventListener>>::~unique_ptr<CSrEventListener,std::default_delete<CSrEventListener>>(void)

- ea: `0x1800179d4`
- end: `0x1800179f5`
- name: `??1?$unique_ptr@VCSrEventListener@@U?$default_delete@VCSrEventListener@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002c540`

## callees

- `0x1800179d4`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<CSrEventListener>::~unique_ptr<CSrEventListener>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x1800179d4  sub     rsp, 28h
0x1800179d8  mov     rcx, [rcx]
0x1800179db  test    rcx, rcx
0x1800179de  jz      short loc_1800179F0
0x1800179e0  mov     rax, [rcx]
0x1800179e3  mov     edx, 1
0x1800179e8  mov     rax, [rax]
0x1800179eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179f0  add     rsp, 28h
0x1800179f4  retn
```
