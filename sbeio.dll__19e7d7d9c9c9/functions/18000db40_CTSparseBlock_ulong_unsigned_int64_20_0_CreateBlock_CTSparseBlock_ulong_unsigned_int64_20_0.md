# CTSparseBlock<ulong,unsigned __int64,20,0>::CreateBlock(CTSparseBlock<ulong,unsigned __int64,20,0> * *)

- ea: `0x18000db40`
- end: `0x18000dba6`
- name: `?CreateBlock@?$CTSparseBlock@K_K$0BE@$0A@@@MEAAJPEAPEAV1@@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800011a0`
- `0x18000db40`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,unsigned __int64,20,0>::CreateBlock(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  __int64 result; // rax

  v3 = operator new(0xD8u);
  v4 = v3;
  if ( v3 )
  {
    v3[1] = 0;
    *v3 = &CTSparseBlock<unsigned long,unsigned __int64,20,0>::`vftable';
    *((_WORD *)v3 + 12) = 0;
    *((_BYTE *)v3 + 26) = 0;
    v3[24] = 0;
    v3[25] = v3;
    *((_DWORD *)v3 + 52) = 0;
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
0x18000db40  push    rbx
0x18000db42  sub     rsp, 20h
0x18000db46  mov     ecx, 0D8h; Size
0x18000db4b  mov     rbx, rdx
0x18000db4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000db53  xor     r8d, r8d
0x18000db56  mov     rcx, rax
0x18000db59  test    rax, rax
0x18000db5c  jz      short loc_18000DB8C
0x18000db5e  lea     rax, ??_7?$CTSparseBlock@K_K$0BE@$0A@@@6B@; const CTSparseBlock<ulong,unsigned __int64,20,0>::`vftable'
0x18000db65  mov     [rcx+8], r8
0x18000db69  mov     [rcx], rax
0x18000db6c  xor     eax, eax
0x18000db6e  mov     [rcx+18h], ax
0x18000db72  mov     [rcx+1Ah], al
0x18000db75  mov     [rcx+0C0h], r8
0x18000db7c  mov     [rcx+0C8h], rcx
0x18000db83  mov     [rcx+0D0h], r8d
0x18000db8a  jmp     short loc_18000DB8F
0x18000db8c  mov     rcx, r8
0x18000db8f  test    rcx, rcx
0x18000db92  mov     [rbx], rcx
0x18000db95  mov     eax, r8d
0x18000db98  mov     edx, 8007000Eh
0x18000db9d  cmovz   eax, edx
0x18000dba0  add     rsp, 20h
0x18000dba4  pop     rbx
0x18000dba5  retn
```
