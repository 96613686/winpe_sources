# _CreateFrameInfo

- ea: `0x18001181c`
- end: `0x180011856`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014480`
- `0x180014680`

## callees

- `0x18001181c`
- `0x180011fe8`

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
0x18001181c  push    rbx
0x18001181e  sub     rsp, 20h
0x180011822  mov     rbx, rcx
0x180011825  mov     [rcx], rdx
0x180011828  call    __vcrt_getptd
0x18001182d  cmp     rbx, [rax+58h]
0x180011831  jnb     short loc_18001183E
0x180011833  call    __vcrt_getptd
0x180011838  mov     rcx, [rax+58h]
0x18001183c  jmp     short loc_180011840
0x18001183e  xor     ecx, ecx
0x180011840  mov     [rbx+8], rcx
0x180011844  call    __vcrt_getptd
0x180011849  mov     [rax+58h], rbx
0x18001184d  mov     rax, rbx
0x180011850  add     rsp, 20h
0x180011854  pop     rbx
0x180011855  retn
```
