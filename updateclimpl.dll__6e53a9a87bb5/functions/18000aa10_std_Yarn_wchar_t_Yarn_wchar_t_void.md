# std::_Yarn<wchar_t>::~_Yarn<wchar_t>(void)

- ea: `0x18000aa10`
- end: `0x18000aa33`
- name: `??1?$_Yarn@_W@std@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(void **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180015d5d`
- `0x180015d73`
- `0x180015d89`
- `0x180015d9f`
- `0x180015db5`
- `0x180015dcb`

## callees

- `0x18000aa10`
- `0x18001028c`

## pseudocode

```c
void __fastcall std::_Yarn<wchar_t>::~_Yarn<wchar_t>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    free(v2);
  *a1 = 0;
}

```

## disassembly

```asm
0x18000aa10  push    rbx
0x18000aa12  sub     rsp, 20h
0x18000aa16  mov     rbx, rcx
0x18000aa19  mov     rcx, [rcx]; Block
0x18000aa1c  test    rcx, rcx
0x18000aa1f  jz      short loc_18000AA26
0x18000aa21  call    free
0x18000aa26  mov     qword ptr [rbx], 0
0x18000aa2d  add     rsp, 20h
0x18000aa31  pop     rbx
0x18000aa32  retn
```
