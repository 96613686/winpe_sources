# _CreateFrameInfo

- ea: `0x1400029e4`
- end: `0x140002a1e`
- name: `_CreateFrameInfo`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004670`

## callees

- `0x1400029e4`
- `0x140003008`

## pseudocode

```c
_QWORD *__fastcall CreateFrameInfo(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rcx

  *a1 = a2;
  if ( (unsigned __int64)a1 >= *(_QWORD *)(_vcrt_getptd(a1, a2, a3) + 88) )
    v7 = 0;
  else
    v7 = *(_QWORD *)(_vcrt_getptd(v5, v4, v6) + 88);
  a1[1] = v7;
  *(_QWORD *)(_vcrt_getptd(v7, v4, v6) + 88) = a1;
  return a1;
}

```

## disassembly

```asm
0x1400029e4  push    rbx
0x1400029e6  sub     rsp, 20h
0x1400029ea  mov     rbx, rcx
0x1400029ed  mov     [rcx], rdx
0x1400029f0  call    __vcrt_getptd
0x1400029f5  cmp     rbx, [rax+58h]
0x1400029f9  jnb     short loc_140002A06
0x1400029fb  call    __vcrt_getptd
0x140002a00  mov     rcx, [rax+58h]
0x140002a04  jmp     short loc_140002A08
0x140002a06  xor     ecx, ecx
0x140002a08  mov     [rbx+8], rcx
0x140002a0c  call    __vcrt_getptd
0x140002a11  mov     [rax+58h], rbx
0x140002a15  mov     rax, rbx
0x140002a18  add     rsp, 20h
0x140002a1c  pop     rbx
0x140002a1d  retn
```
