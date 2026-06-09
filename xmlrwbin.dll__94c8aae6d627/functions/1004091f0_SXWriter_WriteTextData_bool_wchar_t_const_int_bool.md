# SXWriter::WriteTextData(bool,wchar_t const *,int,bool)

- ea: `0x1004091f0`
- end: `0x1004092a4`
- name: `?WriteTextData@SXWriter@@AEAAX_NPEB_WH0@Z`
- size: `180`
- prototype: `void __fastcall(SXWriter *this, char, const wchar_t *, unsigned int)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x100408bb0`
- `0x100408e10`
- `0x1004098d0`
- `0x10040a660`
- `0x10040a700`
- `0x10040ab90`
- `0x10040aee0`

## callees

- `0x1004086f0`
- `0x1004091f0`
- `0x100409840`
- `0x100415d60`

## pseudocode

```c
void __fastcall SXWriter::WriteTextData(SXWriter *this, char a2, const wchar_t *a3, unsigned int a4)
{
  _BYTE *v7; // rax
  unsigned int v8; // ebp
  unsigned int v9; // eax
  __int64 v10; // rsi

  if ( a2 )
  {
    v7 = (_BYTE *)*((_QWORD *)this + 38);
    if ( v7 == *((_BYTE **)this + 39) )
    {
      SXWriter::writeBuffer(this);
      v7 = (_BYTE *)*((_QWORD *)this + 38);
    }
    *v7 = 17;
    ++*((_QWORD *)this + 38);
  }
  SXWriter::WriteMb32(this, a4);
  v8 = 2 * a4;
  if ( v8 )
  {
    while ( 1 )
    {
      v9 = v8;
      if ( *((_DWORD *)this + 78) - *((_DWORD *)this + 76) <= v8 )
        v9 = *((_DWORD *)this + 78) - *((_DWORD *)this + 76);
      v10 = v9;
      memmove(*((void **)this + 38), a3, v9);
      *((_QWORD *)this + 38) += v10;
      v8 -= v10;
      if ( !v8 )
        break;
      SXWriter::writeBuffer(this);
      a3 = (const wchar_t *)((char *)a3 + v10);
    }
  }
}

```

## disassembly

```asm
0x1004091f0  mov     [rsp+arg_8], rbx
0x1004091f5  mov     [rsp+arg_10], rbp
0x1004091fa  push    rdi
0x1004091fb  sub     rsp, 20h
0x1004091ff  mov     ebp, r9d
0x100409202  mov     rdi, r8
0x100409205  mov     rbx, rcx
0x100409208  test    dl, dl
0x10040920a  jz      short loc_100409232
0x10040920c  mov     rax, [rcx+130h]
0x100409213  cmp     rax, [rcx+138h]
0x10040921a  jnz     short loc_100409228
0x10040921c  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x100409221  mov     rax, [rbx+130h]
0x100409228  mov     byte ptr [rax], 11h
0x10040922b  inc     qword ptr [rbx+130h]
0x100409232  mov     edx, ebp; unsigned int
0x100409234  mov     rcx, rbx; this
0x100409237  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x10040923c  add     ebp, ebp
0x10040923e  jz      short loc_100409294
0x100409240  mov     [rsp+28h+arg_0], rsi
0x100409245  nop     word ptr [rax+rax+00000000h]
0x100409250  mov     ecx, [rbx+138h]
0x100409256  mov     eax, ebp
0x100409258  sub     ecx, [rbx+130h]
0x10040925e  mov     rdx, rdi; Src
0x100409261  cmp     ecx, ebp
0x100409263  cmovbe  eax, ecx
0x100409266  mov     rcx, [rbx+130h]; void *
0x10040926d  mov     r8d, eax; Size
0x100409270  mov     esi, eax
0x100409272  call    memmove
0x100409277  add     [rbx+130h], rsi
0x10040927e  sub     ebp, esi
0x100409280  jz      short loc_10040928F
0x100409282  mov     rcx, rbx; this
0x100409285  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040928a  add     rdi, rsi
0x10040928d  jmp     short loc_100409250
0x10040928f  mov     rsi, [rsp+28h+arg_0]
0x100409294  mov     rbx, [rsp+28h+arg_8]
0x100409299  mov     rbp, [rsp+28h+arg_10]
0x10040929e  add     rsp, 20h
0x1004092a2  pop     rdi
0x1004092a3  retn
```
