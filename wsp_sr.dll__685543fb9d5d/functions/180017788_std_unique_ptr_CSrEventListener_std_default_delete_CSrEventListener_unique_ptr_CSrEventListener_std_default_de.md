# std::unique_ptr<CSrEventListener,std::default_delete<CSrEventListener>>::~unique_ptr<CSrEventListener,std::default_delete<CSrEventListener>>(void)

- ea: `0x180017788`
- end: `0x1800177aa`
- name: `??1?$unique_ptr@VCSrEventListener@@U?$default_delete@VCSrEventListener@@@std@@@std@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ca50`

## callees

- `0x180017788`
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
0x180017788  sub     rsp, 28h
0x18001778c  mov     rcx, [rcx]
0x18001778f  test    rcx, rcx
0x180017792  jz      short loc_1800177A4
0x180017794  mov     rax, [rcx]
0x180017797  mov     edx, 1
0x18001779c  mov     rax, [rax]
0x18001779f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177a4  add     rsp, 28h
0x1800177a8  retn
```
