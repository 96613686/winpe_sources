# _CreateFrameInfo

- ea: `0x180011914`
- end: `0x18001194e`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013600`

## callees

- `0x180011914`
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
0x180011914  push    rbx
0x180011916  sub     rsp, 20h
0x18001191a  mov     rbx, rcx
0x18001191d  mov     [rcx], rdx
0x180011920  call    __vcrt_getptd
0x180011925  cmp     rbx, [rax+58h]
0x180011929  jnb     short loc_180011936
0x18001192b  call    __vcrt_getptd
0x180011930  mov     rcx, [rax+58h]
0x180011934  jmp     short loc_180011938
0x180011936  xor     ecx, ecx
0x180011938  mov     [rbx+8], rcx
0x18001193c  call    __vcrt_getptd
0x180011941  mov     [rax+58h], rbx
0x180011945  mov     rax, rbx
0x180011948  add     rsp, 20h
0x18001194c  pop     rbx
0x18001194d  retn
```
