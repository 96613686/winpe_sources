# std::unique_ptr<CSrEventContext,std::default_delete<CSrEventContext>>::reset(CSrEventContext *)

- ea: `0x180004d1c`
- end: `0x180004d39`
- name: `?reset@?$unique_ptr@VCSrEventContext@@U?$default_delete@VCSrEventContext@@@std@@@std@@QEAAXPEAVCSrEventContext@@@Z`
- size: `29`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180004bd4`
- `0x180004d40`
- `0x180004f10`
- `0x180005010`
- `0x1800051b0`
- `0x1800052b0`
- `0x180005450`

## callees

- `0x180004cb0`
- `0x180004d1c`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<CSrEventContext>::reset(__int64 *a1, __int64 a2)
{
  __int64 result; // rax

  result = *a1;
  *a1 = a2;
  if ( result )
    return std::default_delete<CSrEventContext>::operator()(a1, result);
  return result;
}

```

## disassembly

```asm
0x180004d1c  sub     rsp, 28h
0x180004d20  mov     rax, [rcx]
0x180004d23  mov     [rcx], rdx
0x180004d26  test    rax, rax
0x180004d29  jz      short loc_180004D33
0x180004d2b  mov     rdx, rax
0x180004d2e  call    ??R?$default_delete@VCSrEventContext@@@std@@QEBAXPEAVCSrEventContext@@@Z; std::default_delete<CSrEventContext>::operator()(CSrEventContext *)
0x180004d33  add     rsp, 28h
0x180004d37  retn
```
