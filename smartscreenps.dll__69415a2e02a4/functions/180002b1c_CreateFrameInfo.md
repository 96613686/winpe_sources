# _CreateFrameInfo

- ea: `0x180002b1c`
- end: `0x180002b56`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005670`
- `0x180005890`

## callees

- `0x180002b1c`
- `0x1800033d8`

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
0x180002b1c  push    rbx
0x180002b1e  sub     rsp, 20h
0x180002b22  mov     rbx, rcx
0x180002b25  mov     [rcx], rdx
0x180002b28  call    __vcrt_getptd
0x180002b2d  cmp     rbx, [rax+58h]
0x180002b31  jnb     short loc_180002B3E
0x180002b33  call    __vcrt_getptd
0x180002b38  mov     rcx, [rax+58h]
0x180002b3c  jmp     short loc_180002B40
0x180002b3e  xor     ecx, ecx
0x180002b40  mov     [rbx+8], rcx
0x180002b44  call    __vcrt_getptd
0x180002b49  mov     [rax+58h], rbx
0x180002b4d  mov     rax, rbx
0x180002b50  add     rsp, 20h
0x180002b54  pop     rbx
0x180002b55  retn
```
