# _CreateFrameInfo

- ea: `0x10041810c`
- end: `0x100418146`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100419610`

## callees

- `0x100417a7c`
- `0x10041810c`

## pseudocode

```c
_QWORD *__fastcall CreateFrameInfo(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rcx

  *a1 = a2;
  if ( (unsigned __int64)a1 >= *(_QWORD *)(_vcrt_getptd() + 88) )
    v3 = 0;
  else
    v3 = *(_QWORD *)(_vcrt_getptd() + 88);
  a1[1] = v3;
  *(_QWORD *)(_vcrt_getptd() + 88) = a1;
  return a1;
}

```

## disassembly

```asm
0x10041810c  push    rbx
0x10041810e  sub     rsp, 20h
0x100418112  mov     rbx, rcx
0x100418115  mov     [rcx], rdx
0x100418118  call    __vcrt_getptd
0x10041811d  cmp     rbx, [rax+58h]
0x100418121  jnb     short loc_10041812E
0x100418123  call    __vcrt_getptd
0x100418128  mov     rcx, [rax+58h]
0x10041812c  jmp     short loc_100418130
0x10041812e  xor     ecx, ecx
0x100418130  mov     [rbx+8], rcx
0x100418134  call    __vcrt_getptd
0x100418139  mov     [rax+58h], rbx
0x10041813d  mov     rax, rbx
0x100418140  add     rsp, 20h
0x100418144  pop     rbx
0x100418145  retn
```
