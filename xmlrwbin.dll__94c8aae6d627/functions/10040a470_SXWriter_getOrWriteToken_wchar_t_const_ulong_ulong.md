# SXWriter::getOrWriteToken(wchar_t const *,ulong,ulong *)

- ea: `0x10040a470`
- end: `0x10040a5b7`
- name: `?getOrWriteToken@SXWriter@@AEAAHPEB_WKPEAK@Z`
- size: `327`
- prototype: `__int64 __fastcall(SXWriter *__hidden this, const wchar_t *Src, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x100409da0`
- `0x10040a700`

## callees

- `0x1004086f0`
- `0x100409840`
- `0x10040a470`
- `0x100412e30`
- `0x100415d60`

## pseudocode

```c
__int64 __fastcall SXWriter::getOrWriteToken(SXWriter *this, const wchar_t *Src, unsigned int a3, unsigned int *a4)
{
  unsigned int v6; // r9d
  const wchar_t *v7; // rdi
  const wchar_t *v10; // r10
  const wchar_t *i; // r8
  int v12; // eax
  int v13; // eax
  _BYTE *v14; // rax
  unsigned int v15; // ebp
  unsigned int v16; // eax
  __int64 v17; // rsi

  v6 = 0;
  v7 = Src;
  if ( !a3 )
  {
    *a4 = 0;
    return 0;
  }
  v10 = &Src[a3];
  for ( i = Src; i < v10; ++i )
  {
    v12 = *i;
    v6 = v12 + 16 * v6;
    if ( (v6 & 0xF0000000) != 0 )
      v6 ^= v6 & 0xF0000000 ^ ((v6 & 0xF0000000) >> 24);
  }
  v13 = SXTokenTable::getTokenFromNameAndHash(*((_QWORD *)this + 10), Src, a3, v6, a4, 1) - 1;
  if ( v13 )
  {
    if ( v13 != 1 )
      return 1;
    v14 = (_BYTE *)*((_QWORD *)this + 38);
    if ( v14 == *((_BYTE **)this + 39) )
    {
      SXWriter::writeBuffer(this);
      v14 = (_BYTE *)*((_QWORD *)this + 38);
    }
    *v14 = -16;
    ++*((_QWORD *)this + 38);
    SXWriter::WriteMb32(this, a3);
    v15 = 2 * a3;
    if ( v15 )
    {
      while ( 1 )
      {
        v16 = v15;
        if ( *((_DWORD *)this + 78) - *((_DWORD *)this + 76) <= v15 )
          v16 = *((_DWORD *)this + 78) - *((_DWORD *)this + 76);
        v17 = v16;
        memmove(*((void **)this + 38), v7, v16);
        *((_QWORD *)this + 38) += v17;
        v15 -= v17;
        if ( !v15 )
          break;
        SXWriter::writeBuffer(this);
        v7 = (const wchar_t *)((char *)v7 + v17);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10040a470  mov     [rsp+arg_8], rbx
0x10040a475  mov     [rsp+arg_10], rbp
0x10040a47a  push    rdi
0x10040a47b  sub     rsp, 30h
0x10040a47f  mov     r11, r9
0x10040a482  mov     ebp, r8d
0x10040a485  xor     r9d, r9d
0x10040a488  mov     rdi, rdx
0x10040a48b  mov     rbx, rcx
0x10040a48e  test    r8d, r8d
0x10040a491  jnz     short loc_10040A4A8
0x10040a493  mov     [r11], r9d
0x10040a496  xor     eax, eax
0x10040a498  mov     rbx, [rsp+38h+arg_8]
0x10040a49d  mov     rbp, [rsp+38h+arg_10]
0x10040a4a2  add     rsp, 30h
0x10040a4a6  pop     rdi
0x10040a4a7  retn
0x10040a4a8  lea     r10, [rdx+rbp*2]
0x10040a4ac  mov     r8, rdi
0x10040a4af  cmp     rdi, r10
0x10040a4b2  jnb     short loc_10040A4E9
0x10040a4b4  nop     dword ptr [rax+00h]
0x10040a4b8  nop     dword ptr [rax+rax+00000000h]
0x10040a4c0  movzx   eax, word ptr [r8]
0x10040a4c4  add     r8, 2
0x10040a4c8  shl     r9d, 4
0x10040a4cc  add     r9d, eax
0x10040a4cf  mov     edx, r9d
0x10040a4d2  and     edx, 0F0000000h
0x10040a4d8  jz      short loc_10040A4E4
0x10040a4da  mov     eax, edx
0x10040a4dc  shr     eax, 18h
0x10040a4df  xor     eax, edx
0x10040a4e1  xor     r9d, eax
0x10040a4e4  cmp     r8, r10
0x10040a4e7  jb      short loc_10040A4C0
0x10040a4e9  mov     rcx, [rcx+50h]
0x10040a4ed  mov     r8d, ebp
0x10040a4f0  mov     [rsp+38h+var_10], 1
0x10040a4f5  mov     rdx, rdi
0x10040a4f8  mov     [rsp+38h+var_18], r11
0x10040a4fd  call    ?getTokenFromNameAndHash@SXTokenTable@@QEAA?AW4TokenSearchResult@@PEB_WKKPEAK_N@Z; SXTokenTable::getTokenFromNameAndHash(wchar_t const *,ulong,ulong,ulong *,bool)
0x10040a502  sub     eax, 1
0x10040a505  jz      loc_10040A5A5
0x10040a50b  cmp     eax, 1
0x10040a50e  jz      short loc_10040A525
0x10040a510  mov     eax, 1
0x10040a515  mov     rbx, [rsp+38h+arg_8]
0x10040a51a  mov     rbp, [rsp+38h+arg_10]
0x10040a51f  add     rsp, 30h
0x10040a523  pop     rdi
0x10040a524  retn
0x10040a525  mov     rax, [rbx+130h]
0x10040a52c  cmp     rax, [rbx+138h]
0x10040a533  jnz     short loc_10040A544
0x10040a535  mov     rcx, rbx; this
0x10040a538  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040a53d  mov     rax, [rbx+130h]
0x10040a544  mov     byte ptr [rax], 0F0h
0x10040a547  mov     edx, ebp; unsigned int
0x10040a549  inc     qword ptr [rbx+130h]
0x10040a550  mov     rcx, rbx; this
0x10040a553  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x10040a558  add     ebp, ebp
0x10040a55a  jz      short loc_10040A5A5
0x10040a55c  mov     [rsp+38h+arg_0], rsi
0x10040a561  mov     ecx, [rbx+138h]
0x10040a567  mov     eax, ebp
0x10040a569  sub     ecx, [rbx+130h]
0x10040a56f  mov     rdx, rdi; Src
0x10040a572  cmp     ecx, ebp
0x10040a574  cmovbe  eax, ecx
0x10040a577  mov     rcx, [rbx+130h]; void *
0x10040a57e  mov     r8d, eax; Size
0x10040a581  mov     esi, eax
0x10040a583  call    memmove
0x10040a588  add     [rbx+130h], rsi
0x10040a58f  sub     ebp, esi
0x10040a591  jz      short loc_10040A5A0
0x10040a593  mov     rcx, rbx; this
0x10040a596  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040a59b  add     rdi, rsi
0x10040a59e  jmp     short loc_10040A561
0x10040a5a0  mov     rsi, [rsp+38h+arg_0]
0x10040a5a5  mov     rbx, [rsp+38h+arg_8]
0x10040a5aa  xor     eax, eax
0x10040a5ac  mov     rbp, [rsp+38h+arg_10]
0x10040a5b1  add     rsp, 30h
0x10040a5b5  pop     rdi
0x10040a5b6  retn
```
