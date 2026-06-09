# _CreateFrameInfo

- ea: `0x14001c49c`
- end: `0x14001c4d6`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001f090`
- `0x14001f290`

## callees

- `0x14001c49c`
- `0x14001cbf8`

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
0x14001c49c  push    rbx
0x14001c49e  sub     rsp, 20h
0x14001c4a2  mov     rbx, rcx
0x14001c4a5  mov     [rcx], rdx
0x14001c4a8  call    __vcrt_getptd
0x14001c4ad  cmp     rbx, [rax+58h]
0x14001c4b1  jnb     short loc_14001C4BE
0x14001c4b3  call    __vcrt_getptd
0x14001c4b8  mov     rcx, [rax+58h]
0x14001c4bc  jmp     short loc_14001C4C0
0x14001c4be  xor     ecx, ecx
0x14001c4c0  mov     [rbx+8], rcx
0x14001c4c4  call    __vcrt_getptd
0x14001c4c9  mov     [rax+58h], rbx
0x14001c4cd  mov     rax, rbx
0x14001c4d0  add     rsp, 20h
0x14001c4d4  pop     rbx
0x14001c4d5  retn
```
