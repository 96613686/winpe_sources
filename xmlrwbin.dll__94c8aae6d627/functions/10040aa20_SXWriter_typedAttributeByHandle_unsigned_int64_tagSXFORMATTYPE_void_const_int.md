# SXWriter::typedAttributeByHandle(unsigned __int64,tagSXFORMATTYPE,void const *,int)

- ea: `0x10040aa20`
- end: `0x10040aaa1`
- name: `?typedAttributeByHandle@SXWriter@@UEAAJ_KW4tagSXFORMATTYPE@@PEBXH@Z`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1004093d0`
- `0x100409740`
- `0x100409840`
- `0x10040aa20`
- `0x10040aab0`
- `0x100414090`

## pseudocode

```c
__int64 __fastcall SXWriter::typedAttributeByHandle(
        __int64 a1,
        unsigned __int64 a2,
        int a3,
        unsigned __int64 *a4,
        int a5)
{
  SXWriter *v7; // rdi
  unsigned int v8; // ebx

  *(_BYTE *)(a1 + 192) = 1;
  v7 = (SXWriter *)(a1 - 64);
  v8 = SXWriter::MapHandleToUnitoken((SXWriter *)(a1 - 64), a2);
  SXWriter::WriteByte(v7, 246);
  SXWriter::WriteMb32(v7, v8);
  SXWriter::WriteTypedData((__int64)v7, a3, a4, a5);
  return 0;
}

```

## disassembly

```asm
0x10040aa20  mov     [rsp+arg_0], rbx
0x10040aa25  mov     [rsp+arg_8], rsi
0x10040aa2a  mov     [rsp+arg_10], rdi
0x10040aa2f  mov     [rsp+arg_18], r14
0x10040aa34  push    r15
0x10040aa36  sub     rsp, 40h
0x10040aa3a  mov     r14, r9
0x10040aa3d  mov     r15d, r8d
0x10040aa40  xor     esi, esi
0x10040aa42  mov     byte ptr [rcx+0C0h], 1
0x10040aa49  lea     rdi, [rcx-40h]
0x10040aa4d  mov     rcx, rdi; this
0x10040aa50  call    ?MapHandleToUnitoken@SXWriter@@AEAAK_K@Z; SXWriter::MapHandleToUnitoken(unsigned __int64)
0x10040aa55  mov     ebx, eax
0x10040aa57  mov     dl, 0F6h; unsigned __int8
0x10040aa59  mov     rcx, rdi; this
0x10040aa5c  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x10040aa61  mov     edx, ebx; unsigned int
0x10040aa63  mov     rcx, rdi; this
0x10040aa66  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x10040aa6b  mov     r9d, [rsp+48h+arg_20]
0x10040aa70  mov     r8, r14
0x10040aa73  mov     edx, r15d
0x10040aa76  mov     rcx, rdi
0x10040aa79  call    ?WriteTypedData@SXWriter@@AEAAXW4tagSXFORMATTYPE@@PEBXH@Z; SXWriter::WriteTypedData(tagSXFORMATTYPE,void const *,int)
0x10040aa7e  jmp     short loc_10040AA84
0x10040aa80  mov     esi, [rsp+48h+var_28]
0x10040aa84  mov     eax, esi
0x10040aa86  mov     rbx, [rsp+48h+arg_0]
0x10040aa8b  mov     rsi, [rsp+48h+arg_8]
0x10040aa90  mov     rdi, [rsp+48h+arg_10]
0x10040aa95  mov     r14, [rsp+48h+arg_18]
0x10040aa9a  add     rsp, 40h
0x10040aa9e  pop     r15
0x10040aaa0  retn
0x100424620  push    rbp
0x100424622  sub     rsp, 20h
0x100424626  mov     rbp, rdx
0x100424629  mov     [rbp+38h], rcx
0x10042462d  mov     [rbp+30h], rcx
0x100424631  mov     rax, [rbp+30h]
0x100424635  mov     rcx, [rax]
0x100424638  mov     [rbp+28h], rcx
0x10042463c  mov     rax, [rbp+28h]
0x100424640  mov     eax, [rax]
0x100424642  cmp     eax, 0C0000005h
0x100424647  jz      short loc_100424679
0x100424649  add     eax, 1FFFFFFFh
0x10042464e  cmp     eax, 1
0x100424651  ja      short loc_100424669
0x100424653  mov     rax, [rbp+28h]
0x100424657  cmp     dword ptr [rax+18h], 1
0x10042465b  jnz     short loc_100424669
0x10042465d  mov     rax, [rbp+28h]
0x100424661  mov     ecx, [rax+20h]
0x100424664  mov     [rbp+20h], ecx
0x100424667  jmp     short loc_100424670
0x100424669  mov     dword ptr [rbp+20h], 8000FFFFh
0x100424670  mov     dword ptr [rbp+24h], 1
0x100424677  jmp     short loc_100424680
0x100424679  mov     dword ptr [rbp+24h], 0
0x100424680  mov     eax, [rbp+24h]
0x100424683  add     rsp, 20h
0x100424687  pop     rbp
0x100424688  retn
```
