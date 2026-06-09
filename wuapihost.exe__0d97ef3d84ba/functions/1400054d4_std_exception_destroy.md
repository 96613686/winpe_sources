# __std_exception_destroy

- ea: `0x1400054d4`
- end: `0x1400054fc`
- name: `__std_exception_destroy`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400045f8`
- `0x140004620`

## callees

- `0x1400054d4`
- `0x1400056d6`

## pseudocode

```c
void __fastcall _std_exception_destroy(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    free(*(void **)a1);
  *(_BYTE *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x1400054d4  push    rbx
0x1400054d6  sub     rsp, 20h
0x1400054da  cmp     byte ptr [rcx+8], 0
0x1400054de  mov     rbx, rcx
0x1400054e1  jz      short loc_1400054EB
0x1400054e3  mov     rcx, [rcx]; Block
0x1400054e6  call    free
0x1400054eb  mov     byte ptr [rbx+8], 0
0x1400054ef  mov     qword ptr [rbx], 0
0x1400054f6  add     rsp, 20h
0x1400054fa  pop     rbx
0x1400054fb  retn
```
