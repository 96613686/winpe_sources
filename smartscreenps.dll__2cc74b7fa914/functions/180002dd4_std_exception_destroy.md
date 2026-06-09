# __std_exception_destroy

- ea: `0x180002dd4`
- end: `0x180002dfc`
- name: `__std_exception_destroy`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fa8`
- `0x180001fd0`
- `0x180007734`
- `0x180007800`

## callees

- `0x180002dd4`
- `0x18000691a`

## pseudocode

```c
void __fastcall _std_exception_destroy(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    free_0(*(void **)a1);
  *(_BYTE *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x180002dd4  push    rbx
0x180002dd6  sub     rsp, 20h
0x180002dda  cmp     byte ptr [rcx+8], 0
0x180002dde  mov     rbx, rcx
0x180002de1  jz      short loc_180002DEB
0x180002de3  mov     rcx, [rcx]; Block
0x180002de6  call    free_0
0x180002deb  mov     byte ptr [rbx+8], 0
0x180002def  mov     qword ptr [rbx], 0
0x180002df6  add     rsp, 20h
0x180002dfa  pop     rbx
0x180002dfb  retn
```
