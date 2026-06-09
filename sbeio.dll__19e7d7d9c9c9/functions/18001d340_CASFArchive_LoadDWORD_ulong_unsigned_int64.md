# CASFArchive::LoadDWORD(ulong &,unsigned __int64 *)

- ea: `0x18001d340`
- end: `0x18001d396`
- name: `?LoadDWORD@CASFArchive@@QEAAJAEAKPEA_K@Z`
- size: `86`
- prototype: `__int64 __fastcall(CASFArchive *__hidden this, unsigned int *, unsigned __int64 *)`
- caller_count: `30`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d1c0`
- `0x18001d270`
- `0x18001d39c`
- `0x1800209d0`
- `0x180020d20`
- `0x180020e70`
- `0x180021130`
- `0x180021350`
- `0x1800218c0`
- `0x180021b30`
- `0x180021c20`
- `0x180021da0`
- `0x180021e90`
- `0x180022220`
- `0x1800224f0`
- `0x180022590`
- `0x180022700`
- `0x180022890`
- `0x180022b30`
- `0x180022f60`
- `0x1800230f0`
- `0x180023570`
- `0x180023760`
- `0x180023e50`
- `0x180024120`
- `0x180028630`
- `0x1800288c0`
- `0x1800289f0`
- `0x180028b60`
- `0x180028c10`

## callees

- `0x180017fcc`
- `0x18001d340`
- `0x180026ae0`

## pseudocode

```c
__int64 __fastcall CASFArchive::LoadDWORD(CASFArchive *this, unsigned int *a2, unsigned __int64 *a3)
{
  __int64 result; // rax
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned __int8 *v6; // r10
  CASFArchive *v7; // rcx

  if ( (unsigned __int64)(*((_QWORD *)this + 1) + 4LL) > *((_QWORD *)this + 2) )
    return 3222079440LL;
  result = CASFArchive::CheckBoundary(this, 4u, a3);
  if ( (int)result >= 0 )
  {
    v7 = (CASFArchive *)**(unsigned int **)(v5 + 8);
    *(_DWORD *)v6 = (_DWORD)v7;
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
0x18001d340  sub     rsp, 28h
0x18001d344  mov     rax, [rcx+8]
0x18001d348  mov     r10, rdx
0x18001d34b  add     rax, 4
0x18001d34f  mov     r9, rcx
0x18001d352  cmp     rax, [rcx+10h]
0x18001d356  jbe     short loc_18001D35F
0x18001d358  mov     eax, 0C00D07D0h
0x18001d35d  jmp     short loc_18001D391
0x18001d35f  mov     edx, 4; unsigned int
0x18001d364  call    ?CheckBoundary@CASFArchive@@IEAAJKPEA_K@Z; CASFArchive::CheckBoundary(ulong,unsigned __int64 *)
0x18001d369  test    eax, eax
0x18001d36b  js      short loc_18001D391
0x18001d36d  mov     rax, [r9+8]
0x18001d371  mov     ecx, [rax]; this
0x18001d373  mov     [r10], ecx
0x18001d376  add     [r9+8], rdx
0x18001d37a  mov     al, [r9+1Dh]
0x18001d37e  cmp     [r9+1Ch], al
0x18001d382  jz      short loc_18001D38F
0x18001d384  mov     r8d, edx; int
0x18001d387  mov     rdx, r10; unsigned __int8 *
0x18001d38a  call    ?SwapBlockEndian@CASFArchive@@QEAAXPEAEH@Z; CASFArchive::SwapBlockEndian(uchar *,int)
0x18001d38f  xor     eax, eax
0x18001d391  add     rsp, 28h
0x18001d395  retn
```
