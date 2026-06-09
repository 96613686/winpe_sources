# _CreateFrameInfo

- ea: `0x1800117cc`
- end: `0x180011806`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014430`
- `0x180014630`

## callees

- `0x1800117cc`
- `0x180011f98`

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
0x1800117cc  push    rbx
0x1800117ce  sub     rsp, 20h
0x1800117d2  mov     rbx, rcx
0x1800117d5  mov     [rcx], rdx
0x1800117d8  call    __vcrt_getptd
0x1800117dd  cmp     rbx, [rax+58h]
0x1800117e1  jnb     short loc_1800117EE
0x1800117e3  call    __vcrt_getptd
0x1800117e8  mov     rcx, [rax+58h]
0x1800117ec  jmp     short loc_1800117F0
0x1800117ee  xor     ecx, ecx
0x1800117f0  mov     [rbx+8], rcx
0x1800117f4  call    __vcrt_getptd
0x1800117f9  mov     [rax+58h], rbx
0x1800117fd  mov     rax, rbx
0x180011800  add     rsp, 20h
0x180011804  pop     rbx
0x180011805  retn
```
