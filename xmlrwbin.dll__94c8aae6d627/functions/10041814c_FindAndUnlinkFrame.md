# _FindAndUnlinkFrame

- ea: `0x10041814c`
- end: `0x10041819f`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100419610`

## callees

- `0x100417a7c`
- `0x10041814c`
- `0x10041b1a4`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort();
  while ( 1 )
  {
    v3 = *(_QWORD *)(v2 + 8);
    if ( a1 == v2 )
      break;
    v2 = *(_QWORD *)(v2 + 8);
    if ( !v3 )
      goto LABEL_7;
  }
  result = _vcrt_getptd();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x10041814c  mov     [rsp+arg_0], rbx
0x100418151  push    rdi
0x100418152  sub     rsp, 20h
0x100418156  mov     rdi, rcx
0x100418159  call    __vcrt_getptd
0x10041815e  cmp     rdi, [rax+58h]
0x100418162  jnz     short loc_100418199
0x100418164  call    __vcrt_getptd
0x100418169  mov     rdx, [rax+58h]
0x10041816d  test    rdx, rdx
0x100418170  jz      short loc_100418199
0x100418172  mov     rbx, [rdx+8]
0x100418176  cmp     rdi, rdx
0x100418179  jz      short loc_100418185
0x10041817b  mov     rdx, rbx
0x10041817e  test    rbx, rbx
0x100418181  jz      short loc_100418199
0x100418183  jmp     short loc_100418172
0x100418185  call    __vcrt_getptd
0x10041818a  mov     [rax+58h], rbx
0x10041818e  mov     rbx, [rsp+28h+arg_0]
0x100418193  add     rsp, 20h
0x100418197  pop     rdi
0x100418198  retn
0x100418199  call    abort
```
