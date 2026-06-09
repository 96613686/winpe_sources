# CASFArchive::LoadQWORD(unsigned __int64 &,unsigned __int64 *)

- ea: `0x18001d424`
- end: `0x18001d47b`
- name: `?LoadQWORD@CASFArchive@@QEAAJAEA_KPEA_K@Z`
- size: `87`
- prototype: `__int64 __fastcall(CASFArchive *__hidden this, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d270`
- `0x18001d2f0`
- `0x180021cf0`
- `0x180022590`
- `0x180022980`
- `0x180022a40`
- `0x180022f60`
- `0x180023570`
- `0x180023760`

## callees

- `0x180017fcc`
- `0x18001d424`
- `0x180026ae0`

## pseudocode

```c
__int64 __fastcall CASFArchive::LoadQWORD(CASFArchive *this, unsigned __int64 *a2, unsigned __int64 *a3)
{
  __int64 result; // rax
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned __int8 *v6; // r10
  CASFArchive **v7; // rax
  CASFArchive *v8; // rcx

  if ( (unsigned __int64)(*((_QWORD *)this + 1) + 8LL) > *((_QWORD *)this + 2) )
    return 3222079440LL;
  result = CASFArchive::CheckBoundary(this, 8u, a3);
  if ( (int)result >= 0 )
  {
    v7 = *(CASFArchive ***)(v5 + 8);
    v8 = *v7;
    *(_QWORD *)v6 = *v7;
    *(_QWORD *)(v5 + 8) += v4;
    if ( *(_BYTE *)(v5 + 28) != *(_BYTE *)(v5 + 29) )
      CASFArchive::SwapBlockEndian(v8, v6, v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001d424  sub     rsp, 28h
0x18001d428  mov     rax, [rcx+8]
0x18001d42c  mov     r10, rdx
0x18001d42f  add     rax, 8
0x18001d433  mov     r9, rcx
0x18001d436  cmp     rax, [rcx+10h]
0x18001d43a  jbe     short loc_18001D443
0x18001d43c  mov     eax, 0C00D07D0h
0x18001d441  jmp     short loc_18001D476
0x18001d443  mov     edx, 8; unsigned int
0x18001d448  call    ?CheckBoundary@CASFArchive@@IEAAJKPEA_K@Z; CASFArchive::CheckBoundary(ulong,unsigned __int64 *)
0x18001d44d  test    eax, eax
0x18001d44f  js      short loc_18001D476
0x18001d451  mov     rax, [r9+8]
0x18001d455  mov     rcx, [rax]; this
0x18001d458  mov     [r10], rcx
0x18001d45b  add     [r9+8], rdx
0x18001d45f  mov     al, [r9+1Dh]
0x18001d463  cmp     [r9+1Ch], al
0x18001d467  jz      short loc_18001D474
0x18001d469  mov     r8d, edx; int
0x18001d46c  mov     rdx, r10; unsigned __int8 *
0x18001d46f  call    ?SwapBlockEndian@CASFArchive@@QEAAXPEAEH@Z; CASFArchive::SwapBlockEndian(uchar *,int)
0x18001d474  xor     eax, eax
0x18001d476  add     rsp, 28h
0x18001d47a  retn
```
