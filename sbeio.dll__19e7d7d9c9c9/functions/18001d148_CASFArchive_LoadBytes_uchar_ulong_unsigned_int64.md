# CASFArchive::LoadBytes(uchar *,ulong,unsigned __int64 *)

- ea: `0x18001d148`
- end: `0x18001d1ab`
- name: `?LoadBytes@CASFArchive@@QEAAJPEAEKPEA_K@Z`
- size: `99`
- prototype: `int(CASFArchive *__hidden this, unsigned __int8 *, unsigned int, unsigned __int64 *)`
- caller_count: `25`
- callee_count: `3`
- tags: ``

## callers

- `0x1800209d0`
- `0x180020e70`
- `0x180020f70`
- `0x180021350`
- `0x180021570`
- `0x1800218c0`
- `0x180021b30`
- `0x180021c20`
- `0x180021da0`
- `0x180021e90`
- `0x180021f80`
- `0x180022890`
- `0x180022a40`
- `0x180022b30`
- `0x180022eb0`
- `0x1800230f0`
- `0x180023570`
- `0x180023760`
- `0x180023c40`
- `0x180023ce0`
- `0x180023e50`
- `0x180024120`
- `0x1800288c0`
- `0x1800289f0`
- `0x180028c10`

## callees

- `0x180017fcc`
- `0x18001d148`
- `0x18002a070`

## pseudocode

```c
__int64 __fastcall CASFArchive::LoadBytes(
        CASFArchive *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int64 *a4)
{
  size_t v6; // rdi
  __int64 result; // rax

  v6 = a3;
  if ( (unsigned __int64)a3 + *((_QWORD *)this + 1) > *((_QWORD *)this + 2) )
    return 3222079440LL;
  result = CASFArchive::CheckBoundary(this, a3, a4);
  if ( (int)result >= 0 )
  {
    memcpy_0(a2, *((const void **)this + 1), v6);
    *((_QWORD *)this + 1) += v6;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001d148  mov     [rsp+arg_0], rbx
0x18001d14d  mov     [rsp+arg_8], rsi
0x18001d152  push    rdi
0x18001d153  sub     rsp, 20h
0x18001d157  mov     r10, [rcx+8]
0x18001d15b  mov     rsi, rdx
0x18001d15e  mov     r11d, r8d
0x18001d161  mov     rbx, rcx
0x18001d164  add     r10, r11
0x18001d167  mov     edi, r8d
0x18001d16a  cmp     r10, [rcx+10h]
0x18001d16e  jbe     short loc_18001D177
0x18001d170  mov     eax, 0C00D07D0h
0x18001d175  jmp     short loc_18001D19B
0x18001d177  mov     r8, r9; unsigned __int64 *
0x18001d17a  mov     edx, r11d; unsigned int
0x18001d17d  call    ?CheckBoundary@CASFArchive@@IEAAJKPEA_K@Z; CASFArchive::CheckBoundary(ulong,unsigned __int64 *)
0x18001d182  test    eax, eax
0x18001d184  js      short loc_18001D19B
0x18001d186  mov     rdx, [rbx+8]; Src
0x18001d18a  mov     r8, rdi; Size
0x18001d18d  mov     rcx, rsi; void *
0x18001d190  call    memcpy_0
0x18001d195  add     [rbx+8], rdi
0x18001d199  xor     eax, eax
0x18001d19b  mov     rbx, [rsp+28h+arg_0]
0x18001d1a0  mov     rsi, [rsp+28h+arg_8]
0x18001d1a5  add     rsp, 20h
0x18001d1a9  pop     rdi
0x18001d1aa  retn
```
