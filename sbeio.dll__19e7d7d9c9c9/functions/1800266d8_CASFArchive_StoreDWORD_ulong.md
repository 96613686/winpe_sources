# CASFArchive::StoreDWORD(ulong)

- ea: `0x1800266d8`
- end: `0x180026742`
- name: `?StoreDWORD@CASFArchive@@QEAAJK@Z`
- size: `106`
- prototype: `__int64 __fastcall(CASFArchive *__hidden this, unsigned int)`
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x18001da90`
- `0x18001dc30`
- `0x18001dce0`
- `0x18001de50`
- `0x18001df60`
- `0x18001e190`
- `0x18001e2e0`
- `0x18001e360`
- `0x18001e440`
- `0x18001e5a0`
- `0x18001e730`
- `0x18001e790`
- `0x18001e850`
- `0x18001e9c0`
- `0x18001ebb0`
- `0x18001ecf0`
- `0x18001efa0`
- `0x18001f0c0`
- `0x18001f4c0`
- `0x18001f620`
- `0x180026600`
- `0x180026660`
- `0x180026748`
- `0x1800282d0`
- `0x180028340`
- `0x1800283c0`
- `0x180028580`

## callees

- `0x1800015f0`
- `0x1800266d8`
- `0x180026ae0`

## pseudocode

```c
__int64 __fastcall CASFArchive::StoreDWORD(CASFArchive *this, int a2)
{
  CASFArchive *v2; // r9
  unsigned __int64 v3; // rax
  unsigned __int8 v5[8]; // [rsp+20h] [rbp-18h] BYREF

  v2 = this;
  v3 = *((_QWORD *)this + 1) + 4LL;
  *(_DWORD *)v5 = a2;
  if ( v3 > *((_QWORD *)this + 2) )
    return 3222079440LL;
  if ( *((_BYTE *)this + 28) != *((_BYTE *)this + 29) )
  {
    CASFArchive::SwapBlockEndian(this, v5, 4);
    a2 = *(_DWORD *)v5;
  }
  **((_DWORD **)v2 + 1) = a2;
  *((_QWORD *)v2 + 1) += 4LL;
  return 0;
}

```

## disassembly

```asm
0x1800266d8  sub     rsp, 38h
0x1800266dc  mov     rax, cs:__security_cookie
0x1800266e3  xor     rax, rsp
0x1800266e6  mov     [rsp+38h+var_10], rax
0x1800266eb  mov     rax, [rcx+8]
0x1800266ef  mov     r9, rcx
0x1800266f2  add     rax, 4
0x1800266f6  mov     dword ptr [rsp+38h+var_18], edx
0x1800266fa  cmp     rax, [rcx+10h]
0x1800266fe  jbe     short loc_180026707
0x180026700  mov     eax, 0C00D07D0h
0x180026705  jmp     short loc_180026730
0x180026707  mov     al, [rcx+1Dh]
0x18002670a  cmp     [rcx+1Ch], al
0x18002670d  jz      short loc_180026723
0x18002670f  mov     r8d, 4; int
0x180026715  lea     rdx, [rsp+38h+var_18]; unsigned __int8 *
0x18002671a  call    ?SwapBlockEndian@CASFArchive@@QEAAXPEAEH@Z; CASFArchive::SwapBlockEndian(uchar *,int)
0x18002671f  mov     edx, dword ptr [rsp+38h+var_18]
0x180026723  mov     rax, [r9+8]
0x180026727  mov     [rax], edx
0x180026729  add     qword ptr [r9+8], 4
0x18002672e  xor     eax, eax
0x180026730  mov     rcx, [rsp+38h+var_10]
0x180026735  xor     rcx, rsp; StackCookie
0x180026738  call    __security_check_cookie
0x18002673d  add     rsp, 38h
0x180026741  retn
```
