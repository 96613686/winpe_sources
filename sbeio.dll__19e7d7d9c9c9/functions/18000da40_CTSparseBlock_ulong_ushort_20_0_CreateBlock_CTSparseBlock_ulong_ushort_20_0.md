# CTSparseBlock<ulong,ushort,20,0>::CreateBlock(CTSparseBlock<ulong,ushort,20,0> * *)

- ea: `0x18000da40`
- end: `0x18000da9d`
- name: `?CreateBlock@?$CTSparseBlock@KG$0BE@$0A@@@MEAAJPEAPEAV1@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800011a0`
- `0x18000da40`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,unsigned short,20,0>::CreateBlock(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  __int64 result; // rax

  v3 = operator new(0x58u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *v3 = &CTDynArray<unsigned short,20>::`vftable';
    *((_WORD *)v3 + 9) = 0;
    *((_BYTE *)v3 + 20) = 0;
    v3[8] = 0;
    v3[9] = v3;
    *((_DWORD *)v3 + 20) = 0;
  }
  else
  {
    v4 = 0;
  }
  *a2 = v4;
  result = 0;
  if ( !v4 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x18000da40  push    rbx
0x18000da42  sub     rsp, 20h
0x18000da46  mov     ecx, 58h ; 'X'; Size
0x18000da4b  mov     rbx, rdx
0x18000da4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000da53  xor     r8d, r8d
0x18000da56  mov     rcx, rax
0x18000da59  test    rax, rax
0x18000da5c  jz      short loc_18000DA83
0x18000da5e  lea     rax, ??_7?$CTDynArray@G$0BE@@@6B@; const CTDynArray<ushort,20>::`vftable'
0x18000da65  mov     [rcx+8], r8
0x18000da69  mov     [rcx], rax
0x18000da6c  xor     eax, eax
0x18000da6e  mov     [rcx+12h], ax
0x18000da72  mov     [rcx+14h], al
0x18000da75  mov     [rcx+40h], r8
0x18000da79  mov     [rcx+48h], rcx
0x18000da7d  mov     [rcx+50h], r8d
0x18000da81  jmp     short loc_18000DA86
0x18000da83  mov     rcx, r8
0x18000da86  test    rcx, rcx
0x18000da89  mov     [rbx], rcx
0x18000da8c  mov     eax, r8d
0x18000da8f  mov     edx, 8007000Eh
0x18000da94  cmovz   eax, edx
0x18000da97  add     rsp, 20h
0x18000da9b  pop     rbx
0x18000da9c  retn
```
