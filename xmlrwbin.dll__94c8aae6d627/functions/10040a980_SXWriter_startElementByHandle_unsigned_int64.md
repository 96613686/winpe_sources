# SXWriter::startElementByHandle(unsigned __int64)

- ea: `0x10040a980`
- end: `0x10040a9d9`
- name: `?startElementByHandle@SXWriter@@UEAAJ_K@Z`
- size: `89`
- prototype: `int(SXWriter *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x100409740`
- `0x100409840`
- `0x10040a980`
- `0x10040aab0`
- `0x10040adb0`
- `0x100414090`

## pseudocode

```c
__int64 __fastcall SXWriter::startElementByHandle(SXWriter *this, unsigned __int64 a2)
{
  SXWriter *v3; // rdi

  v3 = (SXWriter *)((char *)this - 64);
  SXWriter::endAttributesCheck((SXWriter *)((char *)this - 64));
  LODWORD(a2) = SXWriter::MapHandleToUnitoken(v3, a2);
  SXWriter::WriteByte(v3, 248);
  SXWriter::WriteMb32(v3, a2);
  return 0;
}

```

## disassembly

```asm
0x10040a980  mov     [rsp+arg_0], rbx
0x10040a985  mov     [rsp+arg_8], rsi
0x10040a98a  push    rdi
0x10040a98b  sub     rsp, 40h
0x10040a98f  mov     rbx, rdx
0x10040a992  xor     esi, esi
0x10040a994  lea     rdi, [rcx-40h]
0x10040a998  mov     rcx, rdi; this
0x10040a99b  call    ?endAttributesCheck@SXWriter@@AEAAXXZ; SXWriter::endAttributesCheck(void)
0x10040a9a0  mov     rdx, rbx; unsigned __int64
0x10040a9a3  mov     rcx, rdi; this
0x10040a9a6  call    ?MapHandleToUnitoken@SXWriter@@AEAAK_K@Z; SXWriter::MapHandleToUnitoken(unsigned __int64)
0x10040a9ab  mov     ebx, eax
0x10040a9ad  mov     dl, 0F8h; unsigned __int8
0x10040a9af  mov     rcx, rdi; this
0x10040a9b2  call    ?WriteByte@SXWriter@@IEAAXE@Z; SXWriter::WriteByte(uchar)
0x10040a9b7  mov     edx, ebx; unsigned int
0x10040a9b9  mov     rcx, rdi; this
0x10040a9bc  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x10040a9c1  jmp     short loc_10040A9C7
0x10040a9c3  mov     esi, [rsp+48h+var_28]
0x10040a9c7  mov     eax, esi
0x10040a9c9  mov     rbx, [rsp+48h+arg_0]
0x10040a9ce  mov     rsi, [rsp+48h+arg_8]
0x10040a9d3  add     rsp, 40h
0x10040a9d7  pop     rdi
0x10040a9d8  retn
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
