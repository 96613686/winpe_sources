# writeIndexTableNull

- ea: `0x180033078`
- end: `0x180033126`
- name: `writeIndexTableNull`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007400`
- `0x180030e10`

## callees

- `0x1800029a4`
- `0x180003830`
- `0x180033078`

## pseudocode

```c
__int64 __fastcall writeIndexTableNull(__int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // r8

  if ( !*(_QWORD *)(a1 + 34480) )
  {
    v2 = *(_QWORD *)(a1 + 34368);
    if ( *(_DWORD *)(a1 + 160) )
    {
      PutVLWordEsc(v2, 0, 4);
      putBit16z(v2, *(unsigned __int8 *)(a1 + 33020), 8);
      putBit16z(v2, *(unsigned __int8 *)(a1 + 33021), v3);
      putBit16z(v2, 0, 15);
      putBit16z(v2, 1, 1);
    }
    else
    {
      PutVLWordEsc(v2, 255, 0);
    }
    putBit16z(v2, 0, -*(_DWORD *)(v2 + 8) & 7);
  }
  return 0;
}

```

## disassembly

```asm
0x180033078  mov     [rsp+arg_0], rbx
0x18003307d  push    rdi
0x18003307e  sub     rsp, 20h
0x180033082  cmp     qword ptr [rcx+86B0h], 0
0x18003308a  mov     rdi, rcx
0x18003308d  jnz     loc_180033118
0x180033093  mov     rbx, [rcx+8640h]
0x18003309a  cmp     dword ptr [rcx+0A0h], 0
0x1800330a1  mov     rcx, rbx
0x1800330a4  jz      short loc_1800330F6
0x1800330a6  xor     edx, edx
0x1800330a8  lea     r8d, [rdx+4]
0x1800330ac  call    PutVLWordEsc
0x1800330b1  movzx   edx, byte ptr [rdi+80FCh]
0x1800330b8  mov     r8d, 8
0x1800330be  mov     rcx, rbx
0x1800330c1  call    putBit16z
0x1800330c6  movzx   edx, byte ptr [rdi+80FDh]
0x1800330cd  mov     rcx, rbx
0x1800330d0  call    putBit16z
0x1800330d5  xor     edx, edx
0x1800330d7  mov     rcx, rbx
0x1800330da  lea     r8d, [rdx+0Fh]
0x1800330de  call    putBit16z
0x1800330e3  mov     r8d, 1
0x1800330e9  mov     rcx, rbx
0x1800330ec  mov     edx, r8d
0x1800330ef  call    putBit16z
0x1800330f4  jmp     short loc_180033103
0x1800330f6  xor     r8d, r8d
0x1800330f9  mov     edx, 0FFh
0x1800330fe  call    PutVLWordEsc
0x180033103  mov     r8d, [rbx+8]
0x180033107  xor     edx, edx
0x180033109  neg     r8d
0x18003310c  mov     rcx, rbx
0x18003310f  and     r8d, 7
0x180033113  call    putBit16z
0x180033118  mov     rbx, [rsp+28h+arg_0]
0x18003311d  xor     eax, eax
0x18003311f  add     rsp, 20h
0x180033123  pop     rdi
0x180033124  retn
```
