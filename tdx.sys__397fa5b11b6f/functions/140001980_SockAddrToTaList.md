# SockAddrToTaList

- ea: `0x140001980`
- end: `0x140001a62`
- name: `SockAddrToTaList`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001ce0`
- `0x140002fb0`
- `0x140007b90`
- `0x1400159f0`

## callees

- `0x140001980`
- `0x140002250`
- `0x140018600`

## pseudocode

```c
__int64 __fastcall SockAddrToTaList(__int16 *a1, char a2, __int64 a3, int *a4)
{
  int *v4; // r10
  __int16 v5; // ax
  unsigned __int16 v6; // r9
  int v7; // eax
  int v8; // ebx
  __int64 v10; // rax

  v4 = a4;
  if ( a2 && !(unsigned __int8)INETADDR_ISV4MAPPED(a1) )
    a2 = 0;
  v5 = *a1;
  if ( *a1 == 35 || v5 == 2 )
  {
    v6 = 14;
  }
  else
  {
    if ( v5 != 23 )
      return 0;
    v6 = 14;
    if ( !a2 )
      v6 = 26;
  }
  v7 = v6 + 8;
  if ( *v4 < v7 )
  {
    *v4 = v7;
    return 0;
  }
  v8 = v6;
  *(_DWORD *)a3 = 1;
  *(_WORD *)(a3 + 4) = v6;
  if ( a2 )
  {
    *(_WORD *)(a3 + 6) = 2;
    *(_WORD *)(a3 + 8) = a1[1];
    v10 = 10;
    if ( *a1 != 23 )
      v10 = 8;
    *(_DWORD *)(a3 + 10) = *(_DWORD *)&a1[v10];
    *(_QWORD *)(a3 + 14) = 0;
    return (unsigned int)v6 + 8;
  }
  else
  {
    *(_WORD *)(a3 + 6) = *a1;
    memmove((void *)(a3 + 8), a1 + 1, v6);
    return (unsigned int)(v8 + 8);
  }
}

```

## disassembly

```asm
0x140001980  sub     rsp, 28h
0x140001984  mov     r10, r9
0x140001987  test    dl, dl
0x140001989  jnz     loc_140001A15
0x14000198f  movzx   eax, word ptr [rcx]
0x140001992  cmp     ax, 23h ; '#'
0x140001996  jnz     short loc_1400019E8
0x140001998  mov     r9d, 0Eh
0x14000199e  movzx   eax, r9w
0x1400019a2  add     eax, 8
0x1400019a5  cmp     [r10], eax
0x1400019a8  jl      short loc_1400019FC
0x1400019aa  mov     [rsp+28h+var_8], rbx
0x1400019af  lea     r10, [r8+8]
0x1400019b3  movzx   ebx, r9w
0x1400019b7  mov     dword ptr [r8], 1
0x1400019be  mov     [r8+4], r9w
0x1400019c3  test    dl, dl
0x1400019c5  jnz     short loc_140001A2B
0x1400019c7  movzx   eax, word ptr [rcx]
0x1400019ca  lea     rdx, [rcx+2]; Src
0x1400019ce  mov     [r8+6], ax
0x1400019d3  mov     rcx, r10; void *
0x1400019d6  mov     r8d, ebx; Size
0x1400019d9  call    memmove
0x1400019de  lea     eax, [rbx+8]
0x1400019e1  mov     rbx, [rsp+28h+var_8]
0x1400019e6  jmp     short loc_1400019F6
0x1400019e8  cmp     ax, 2
0x1400019ec  jz      short loc_140001998
0x1400019ee  cmp     ax, 17h
0x1400019f2  jz      short loc_140001A01
0x1400019f4  xor     eax, eax
0x1400019f6  add     rsp, 28h
0x1400019fa  retn
0x1400019fc  mov     [r10], eax
0x1400019ff  jmp     short loc_1400019F4
0x140001a01  test    dl, dl
0x140001a03  mov     eax, 1Ah
0x140001a08  mov     r9d, 0Eh
0x140001a0e  cmovz   r9w, ax
0x140001a13  jmp     short loc_14000199E
0x140001a15  call    INETADDR_ISV4MAPPED
0x140001a1a  xor     r9d, r9d
0x140001a1d  movzx   edx, dl
0x140001a20  test    al, al
0x140001a22  cmovz   edx, r9d
0x140001a26  jmp     loc_14000198F
0x140001a2b  mov     word ptr [r8+6], 2
0x140001a32  mov     edx, 10h
0x140001a37  movzx   eax, word ptr [rcx+2]
0x140001a3b  mov     [r10], ax
0x140001a3f  mov     eax, 14h
0x140001a44  cmp     word ptr [rcx], 17h
0x140001a48  cmovnz  eax, edx
0x140001a4b  mov     eax, [rax+rcx]
0x140001a4e  mov     [r10+2], eax
0x140001a52  xor     eax, eax
0x140001a54  mov     [r10+6], rax
0x140001a58  lea     eax, [rbx+8]
0x140001a5b  mov     rbx, [rsp+28h+var_8]
0x140001a60  jmp     short loc_1400019F6
```
