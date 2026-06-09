# CASFArchive::LoadWORD(ushort &,unsigned __int64 *)

- ea: `0x18001d484`
- end: `0x18001d4dc`
- name: `?LoadWORD@CASFArchive@@QEAAJAEAGPEA_K@Z`
- size: `88`
- prototype: `__int64 __fastcall(CASFArchive *__hidden this, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d1c0`
- `0x18001d39c`
- `0x1800209d0`
- `0x180020d20`
- `0x180020e70`
- `0x180020f70`
- `0x180021570`
- `0x180021f80`
- `0x180022220`
- `0x180022350`
- `0x180022590`
- `0x180022700`
- `0x180022a40`
- `0x180022b30`
- `0x180022d80`
- `0x1800230f0`
- `0x180023460`
- `0x180023570`
- `0x180023760`
- `0x180023ce0`
- `0x180023e50`
- `0x180024120`
- `0x180028630`
- `0x1800289f0`

## callees

- `0x180017fcc`
- `0x18001d484`
- `0x180026ae0`

## pseudocode

```c
__int64 __fastcall CASFArchive::LoadWORD(CASFArchive *this, unsigned __int16 *a2, unsigned __int64 *a3)
{
  __int64 result; // rax
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned __int8 *v6; // r10
  CASFArchive *v7; // rcx

  if ( (unsigned __int64)(*((_QWORD *)this + 1) + 2LL) > *((_QWORD *)this + 2) )
    return 3222079440LL;
  result = CASFArchive::CheckBoundary(this, 2u, a3);
  if ( (int)result >= 0 )
  {
    v7 = (CASFArchive *)**(unsigned __int16 **)(v5 + 8);
    *(_WORD *)v6 = (_WORD)v7;
    *(_QWORD *)(v5 + 8) += v4;
    if ( *(_BYTE *)(v5 + 28) != *(_BYTE *)(v5 + 29) )
      CASFArchive::SwapBlockEndian(v7, v6, v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001d484  sub     rsp, 28h
0x18001d488  mov     rax, [rcx+8]
0x18001d48c  mov     r10, rdx
0x18001d48f  add     rax, 2
0x18001d493  mov     r9, rcx
0x18001d496  cmp     rax, [rcx+10h]
0x18001d49a  jbe     short loc_18001D4A3
0x18001d49c  mov     eax, 0C00D07D0h
0x18001d4a1  jmp     short loc_18001D4D7
0x18001d4a3  mov     edx, 2; unsigned int
0x18001d4a8  call    ?CheckBoundary@CASFArchive@@IEAAJKPEA_K@Z; CASFArchive::CheckBoundary(ulong,unsigned __int64 *)
0x18001d4ad  test    eax, eax
0x18001d4af  js      short loc_18001D4D7
0x18001d4b1  mov     rax, [r9+8]
0x18001d4b5  movzx   ecx, word ptr [rax]; this
0x18001d4b8  mov     [r10], cx
0x18001d4bc  add     [r9+8], rdx
0x18001d4c0  mov     al, [r9+1Dh]
0x18001d4c4  cmp     [r9+1Ch], al
0x18001d4c8  jz      short loc_18001D4D5
0x18001d4ca  mov     r8d, edx; int
0x18001d4cd  mov     rdx, r10; unsigned __int8 *
0x18001d4d0  call    ?SwapBlockEndian@CASFArchive@@QEAAXPEAEH@Z; CASFArchive::SwapBlockEndian(uchar *,int)
0x18001d4d5  xor     eax, eax
0x18001d4d7  add     rsp, 28h
0x18001d4db  retn
```
