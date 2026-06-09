# CTSparseBlock<ulong,ulong,20,0>::CreateBlock(CTSparseBlock<ulong,ulong,20,0> * *)

- ea: `0x18000f320`
- end: `0x18000f37d`
- name: `?CreateBlock@?$CTSparseBlock@KK$0BE@$0A@@@MEAAJPEAPEAV1@@Z`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800011a0`
- `0x18000f320`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,unsigned long,20,0>::CreateBlock(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  __int64 result; // rax

  v3 = operator new(0x80u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *v3 = &CTSparseBlock<unsigned long,unsigned long,20,0>::`vftable';
    *((_WORD *)v3 + 10) = 0;
    *((_BYTE *)v3 + 22) = 0;
    v3[13] = 0;
    v3[14] = v3;
    *((_DWORD *)v3 + 30) = 0;
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
0x18000f320  push    rbx
0x18000f322  sub     rsp, 20h
0x18000f326  mov     ecx, 80h; Size
0x18000f32b  mov     rbx, rdx
0x18000f32e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f333  xor     r8d, r8d
0x18000f336  mov     rcx, rax
0x18000f339  test    rax, rax
0x18000f33c  jz      short loc_18000F363
0x18000f33e  lea     rax, ??_7?$CTSparseBlock@KK$0BE@$0A@@@6B@; const CTSparseBlock<ulong,ulong,20,0>::`vftable'
0x18000f345  mov     [rcx+8], r8
0x18000f349  mov     [rcx], rax
0x18000f34c  xor     eax, eax
0x18000f34e  mov     [rcx+14h], ax
0x18000f352  mov     [rcx+16h], al
0x18000f355  mov     [rcx+68h], r8
0x18000f359  mov     [rcx+70h], rcx
0x18000f35d  mov     [rcx+78h], r8d
0x18000f361  jmp     short loc_18000F366
0x18000f363  mov     rcx, r8
0x18000f366  test    rcx, rcx
0x18000f369  mov     [rbx], rcx
0x18000f36c  mov     eax, r8d
0x18000f36f  mov     edx, 8007000Eh
0x18000f374  cmovz   eax, edx
0x18000f377  add     rsp, 20h
0x18000f37b  pop     rbx
0x18000f37c  retn
```
