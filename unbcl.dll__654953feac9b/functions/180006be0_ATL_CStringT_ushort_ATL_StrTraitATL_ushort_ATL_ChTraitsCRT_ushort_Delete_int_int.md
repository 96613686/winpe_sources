# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Delete(int,int)

- ea: `0x180006be0`
- end: `0x180006cc6`
- name: `?Delete@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHH@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18005d4a0`

## callees

- `0x1800066cc`
- `0x180006be0`
- `0x180006fb0`

## import_xrefs

- `msvcrt!memmove_s` at `0x180006c5b`
- `msvcrt!memmove_s` at `0x180006c5b`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Delete(
        __int64 *a1,
        int a2,
        int a3)
{
  int v3; // ebp
  int v5; // edi
  __int64 v6; // rcx
  int v7; // ebx
  errno_t v8; // eax
  int v9; // ebx

  v3 = 0;
  if ( a2 >= 0 )
    v3 = a2;
  v5 = 0;
  if ( a3 >= 0 )
    v5 = a3;
  if ( 0x7FFFFFFF - v5 < v3 )
    goto LABEL_20;
  v6 = *a1;
  v7 = *(_DWORD *)(v6 - 16);
  if ( v5 + v3 > v7 )
    v5 = v7 - v3;
  if ( v5 > 0 )
  {
    if ( *(int *)(v6 - 8) > 1 )
      ATL::CSimpleStringT<unsigned short,0>::Fork(a1, (unsigned int)v7);
    v8 = memmove_s(
           (void *const)(*a1 + 2LL * v3),
           2LL * (v7 - v3 - v5 + 1),
           (const void *const)(*a1 + 2 * (v3 + (__int64)v5)),
           2LL * (v7 - v3 - v5 + 1));
    if ( v8 )
    {
      if ( v8 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v8 == 22 || v8 == 34 )
        goto LABEL_20;
      if ( v8 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v9 = v7 - v5;
    if ( v9 >= 0 && v9 <= *(_DWORD *)(*a1 - 12) )
    {
      *(_DWORD *)(*a1 - 16) = v9;
      *(_WORD *)(*a1 + 2LL * v9) = 0;
      return *(unsigned int *)(*a1 - 16);
    }
LABEL_20:
    ATL::AtlThrowImpl(-2147024809);
  }
  return *(unsigned int *)(*a1 - 16);
}

```

## disassembly

```asm
0x180006be0  push    rbx
0x180006be2  push    rbp
0x180006be3  push    rsi
0x180006be4  push    rdi
0x180006be5  push    r14
0x180006be7  sub     rsp, 20h
0x180006beb  xor     ebp, ebp
0x180006bed  mov     eax, 7FFFFFFFh
0x180006bf2  test    edx, edx
0x180006bf4  mov     rsi, rcx
0x180006bf7  cmovns  ebp, edx
0x180006bfa  xor     edi, edi
0x180006bfc  test    r8d, r8d
0x180006bff  cmovns  edi, r8d
0x180006c03  sub     eax, edi
0x180006c05  cmp     eax, ebp
0x180006c07  jl      loc_180006CA5
0x180006c0d  mov     rcx, [rcx]
0x180006c10  lea     eax, [rdi+rbp]
0x180006c13  mov     ebx, [rcx-10h]
0x180006c16  cmp     eax, ebx
0x180006c18  jle     short loc_180006C1E
0x180006c1a  mov     edi, ebx
0x180006c1c  sub     edi, ebp
0x180006c1e  test    edi, edi
0x180006c20  jle     short loc_180006C94
0x180006c22  mov     r14d, ebx
0x180006c25  sub     r14d, ebp
0x180006c28  cmp     dword ptr [rcx-8], 1
0x180006c2c  jle     short loc_180006C38
0x180006c2e  mov     edx, ebx
0x180006c30  mov     rcx, rsi
0x180006c33  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x180006c38  mov     r9, [rsi]
0x180006c3b  sub     r14d, edi
0x180006c3e  movsxd  rcx, ebp
0x180006c41  inc     r14d
0x180006c44  movsxd  rax, edi
0x180006c47  add     rax, rcx
0x180006c4a  movsxd  rdx, r14d
0x180006c4d  add     rdx, rdx; DestinationSize
0x180006c50  lea     rcx, [r9+rcx*2]; Destination
0x180006c54  lea     r8, [r9+rax*2]; Source
0x180006c58  mov     r9, rdx; SourceSize
0x180006c5b  call    cs:__imp_memmove_s
0x180006c61  test    eax, eax
0x180006c63  jz      short loc_180006C79
0x180006c65  cmp     eax, 0Ch
0x180006c68  jz      short loc_180006CBB
0x180006c6a  cmp     eax, 16h
0x180006c6d  jz      short loc_180006CA5
0x180006c6f  cmp     eax, 22h ; '"'
0x180006c72  jz      short loc_180006CA5
0x180006c74  cmp     eax, 50h ; 'P'
0x180006c77  jnz     short loc_180006CB0
0x180006c79  sub     ebx, edi
0x180006c7b  js      short loc_180006CA5
0x180006c7d  mov     rax, [rsi]
0x180006c80  cmp     ebx, [rax-0Ch]
0x180006c83  jg      short loc_180006CA5
0x180006c85  mov     [rax-10h], ebx
0x180006c88  xor     eax, eax
0x180006c8a  mov     rcx, [rsi]
0x180006c8d  movsxd  rdx, ebx
0x180006c90  mov     [rcx+rdx*2], ax
0x180006c94  mov     rax, [rsi]
0x180006c97  mov     eax, [rax-10h]
0x180006c9a  add     rsp, 20h
0x180006c9e  pop     r14
0x180006ca0  pop     rdi
0x180006ca1  pop     rsi
0x180006ca2  pop     rbp
0x180006ca3  pop     rbx
0x180006ca4  retn
0x180006ca5  mov     ecx, 80070057h; int
0x180006caa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006cb0  mov     ecx, 80004005h; int
0x180006cb5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006cbb  mov     ecx, 8007000Eh; int
0x180006cc0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
