# SXWriter::WriteQNameHandleData(unsigned __int64)

- ea: `0x1004092b0`
- end: `0x100409314`
- name: `?WriteQNameHandleData@SXWriter@@AEAAX_K@Z`
- size: `100`
- prototype: `void __fastcall(SXWriter *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1004089c0`

## callees

- `0x1004086f0`
- `0x1004092b0`
- `0x100409840`
- `0x10040aab0`

## pseudocode

```c
void __fastcall SXWriter::WriteQNameHandleData(SXWriter *this, unsigned __int64 a2)
{
  unsigned int v3; // eax
  _BYTE *v4; // rcx
  unsigned int v5; // edi

  v3 = SXWriter::MapHandleToUnitoken(this, a2);
  v4 = (_BYTE *)*((_QWORD *)this + 38);
  v5 = v3;
  if ( v4 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    v4 = (_BYTE *)*((_QWORD *)this + 38);
  }
  *v4 = -116;
  ++*((_QWORD *)this + 38);
  if ( (byte_100434BA0 & 0x40) != 0 )
    SXWriter::WriteMb32(this, 0);
  SXWriter::WriteMb32(this, v5);
}

```

## disassembly

```asm
0x1004092b0  mov     [rsp+arg_0], rbx
0x1004092b5  push    rdi
0x1004092b6  sub     rsp, 20h
0x1004092ba  mov     rbx, rcx
0x1004092bd  call    ?MapHandleToUnitoken@SXWriter@@AEAAK_K@Z; SXWriter::MapHandleToUnitoken(unsigned __int64)
0x1004092c2  mov     rcx, [rbx+130h]
0x1004092c9  mov     edi, eax
0x1004092cb  cmp     rcx, [rbx+138h]
0x1004092d2  jnz     short loc_1004092E3
0x1004092d4  mov     rcx, rbx; this
0x1004092d7  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x1004092dc  mov     rcx, [rbx+130h]
0x1004092e3  mov     byte ptr [rcx], 8Ch
0x1004092e6  inc     qword ptr [rbx+130h]
0x1004092ed  test    cs:byte_100434BA0, 40h
0x1004092f4  jz      short loc_100409300
0x1004092f6  xor     edx, edx; unsigned int
0x1004092f8  mov     rcx, rbx; this
0x1004092fb  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x100409300  mov     edx, edi; unsigned int
0x100409302  mov     rcx, rbx; this
0x100409305  mov     rbx, [rsp+28h+arg_0]
0x10040930a  add     rsp, 20h
0x10040930e  pop     rdi
0x10040930f  jmp     ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
```
