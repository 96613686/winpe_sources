# SXWriter::WriteTypedData(tagSXFORMATTYPE,int,IStream *)

- ea: `0x1004095b0`
- end: `0x10040964b`
- name: `?WriteTypedData@SXWriter@@AEAAXW4tagSXFORMATTYPE@@HPEAUIStream@@@Z`
- size: `155`
- prototype: `void __fastcall(SXWriter *, int, int, struct IStream *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10040ac40`
- `0x10040ac70`

## callees

- `0x1004086f0`
- `0x1004095b0`
- `0x1004097a0`
- `0x100409840`

## pseudocode

```c
void __fastcall SXWriter::WriteTypedData(SXWriter *a1, int a2, int a3, struct IStream *a4)
{
  _BYTE *v4; // rax
  unsigned __int64 v7; // rdi
  int v9; // eax
  int v10; // ecx
  unsigned int v11; // edx

  v4 = (_BYTE *)*((_QWORD *)a1 + 38);
  v7 = a3;
  if ( v4 == *((_BYTE **)a1 + 39) )
  {
    SXWriter::writeBuffer(a1);
    v4 = (_BYTE *)*((_QWORD *)a1 + 38);
  }
  *v4 = a2;
  ++*((_QWORD *)a1 + 38);
  v9 = a2 - 100;
  if ( a2 < 128 )
    v9 = a2;
  v10 = *((unsigned __int8 *)&SXFormatDataByType + 8 * v9);
  if ( (v10 & 0x40) != 0 )
  {
    v11 = v7;
    if ( v10 != 64 )
      v11 = v7 >> 1;
    SXWriter::WriteMb32(a1, v11);
  }
  SXWriter::WriteBytesFromStream(a1, a4, v7);
}

```

## disassembly

```asm
0x1004095b0  mov     [rsp+arg_0], rbx
0x1004095b5  mov     [rsp+arg_8], rbp
0x1004095ba  mov     [rsp+arg_10], rsi
0x1004095bf  push    rdi
0x1004095c0  sub     rsp, 20h
0x1004095c4  mov     rax, [rcx+130h]
0x1004095cb  mov     rbp, r9
0x1004095ce  mov     esi, edx
0x1004095d0  movsxd  rdi, r8d
0x1004095d3  mov     rbx, rcx
0x1004095d6  cmp     rax, [rcx+138h]
0x1004095dd  jnz     short loc_1004095EB
0x1004095df  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x1004095e4  mov     rax, [rbx+130h]
0x1004095eb  mov     [rax], sil
0x1004095ee  lea     rcx, ?SXFormatDataByType@@3PAUSXFORMATTYPEDATA@@A; SXFORMATTYPEDATA near * SXFormatDataByType
0x1004095f5  inc     qword ptr [rbx+130h]
0x1004095fc  lea     eax, [rsi-64h]
0x1004095ff  cmp     esi, 80h
0x100409605  cmovl   eax, esi
0x100409608  cdqe
0x10040960a  movzx   ecx, byte ptr [rcx+rax*8]
0x10040960e  test    cl, 40h
0x100409611  jz      short loc_100409629
0x100409613  mov     edx, edi
0x100409615  mov     rax, rdi
0x100409618  shr     rax, 1
0x10040961b  cmp     ecx, 40h ; '@'
0x10040961e  mov     rcx, rbx; this
0x100409621  cmovnz  edx, eax; unsigned int
0x100409624  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x100409629  mov     r8d, edi; unsigned int
0x10040962c  mov     rdx, rbp; struct IStream *
0x10040962f  mov     rcx, rbx; this
0x100409632  mov     rbx, [rsp+28h+arg_0]
0x100409637  mov     rbp, [rsp+28h+arg_8]
0x10040963c  mov     rsi, [rsp+28h+arg_10]
0x100409641  add     rsp, 20h
0x100409645  pop     rdi
0x100409646  jmp     ?WriteBytesFromStream@SXWriter@@IEAAXPEAUIStream@@H@Z; SXWriter::WriteBytesFromStream(IStream *,int)
```
