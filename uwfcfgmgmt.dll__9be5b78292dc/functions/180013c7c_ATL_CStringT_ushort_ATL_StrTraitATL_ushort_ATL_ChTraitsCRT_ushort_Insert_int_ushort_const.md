# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Insert(int,ushort const *)

- ea: `0x180013c7c`
- end: `0x180013d66`
- name: `?Insert@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHPEBG@Z`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013a90`

## callees

- `0x180003a60`
- `0x180013c7c`
- `0x1800144f0`

## import_xrefs

- `msvcrt!memmove_s` at `0x180013cd3`
- `msvcrt!memmove_s` at `0x180013cd3`
- `msvcrt!memcpy_s` at `0x180013d03`
- `msvcrt!memcpy_s` at `0x180013d03`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Insert(
        _QWORD *a1)
{
  __int64 v2; // rsi
  int v3; // ebp
  int v4; // ebx
  rsize_t v5; // r9
  __int64 v6; // rbp
  errno_t v7; // eax
  errno_t v8; // eax
  __int64 result; // rax

  v2 = *(int *)(*a1 - 16LL);
  v3 = *(_DWORD *)(*a1 - 16LL);
  if ( (int)v2 >= 0 )
    v3 = 0;
  v4 = v2 + 4;
  if ( (int)((*(_DWORD *)(*a1 - 12LL) - (v2 + 4)) | (1 - *(_DWORD *)(*a1 - 8LL))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v4);
  v5 = 2LL * ((int)v2 - v3 + 1);
  v6 = *a1 + 2LL * v3;
  v7 = memmove_s((void *const)(v6 + 8), v5, (const void *const)v6, v5);
  if ( v7 )
  {
    if ( v7 == 12 )
      goto LABEL_20;
    if ( v7 == 22 || v7 == 34 )
      goto LABEL_18;
    if ( v7 != 80 )
      goto LABEL_19;
  }
  v8 = memcpy_s((void *const)v6, 8u, L"\\\\?\\", 8u);
  if ( v8 )
  {
    if ( v8 != 12 )
    {
      if ( v8 != 22 && v8 != 34 )
      {
        if ( v8 == 80 )
          goto LABEL_15;
LABEL_19:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_18:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_20:
    ATL::AtlThrowImpl(-2147024882);
  }
LABEL_15:
  if ( v4 < 0 || v4 > *(_DWORD *)(*a1 - 12LL) )
    goto LABEL_18;
  *(_DWORD *)(*a1 - 16LL) = v4;
  result = (unsigned int)v4;
  *(_WORD *)(*a1 + 2 * v2 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180013c7c  push    rbx
0x180013c7e  push    rbp
0x180013c7f  push    rsi
0x180013c80  push    rdi
0x180013c81  sub     rsp, 28h
0x180013c85  mov     r8, [rcx]
0x180013c88  xor     eax, eax
0x180013c8a  mov     rdi, rcx
0x180013c8d  movsxd  rsi, dword ptr [r8-10h]
0x180013c91  lea     edx, [rax+1]
0x180013c94  test    esi, esi
0x180013c96  mov     ebp, esi
0x180013c98  cmovns  ebp, eax
0x180013c9b  sub     edx, [r8-8]
0x180013c9f  mov     eax, [r8-0Ch]
0x180013ca3  lea     ebx, [rsi+4]
0x180013ca6  sub     eax, ebx
0x180013ca8  or      edx, eax
0x180013caa  jge     short loc_180013CB3
0x180013cac  mov     edx, ebx
0x180013cae  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180013cb3  mov     eax, esi
0x180013cb5  movsxd  rcx, ebp
0x180013cb8  sub     eax, ebp
0x180013cba  inc     eax
0x180013cbc  movsxd  rdx, eax
0x180013cbf  mov     rax, [rdi]
0x180013cc2  add     rdx, rdx; DestinationSize
0x180013cc5  mov     r9, rdx; SourceSize
0x180013cc8  lea     rbp, [rax+rcx*2]
0x180013ccc  lea     rcx, [rbp+8]; Destination
0x180013cd0  mov     r8, rbp; Source
0x180013cd3  call    cs:__imp_memmove_s
0x180013cd9  test    eax, eax
0x180013cdb  jz      short loc_180013CF1
0x180013cdd  cmp     eax, 0Ch
0x180013ce0  jz      short loc_180013D5B
0x180013ce2  cmp     eax, 16h
0x180013ce5  jz      short loc_180013D45
0x180013ce7  cmp     eax, 22h ; '"'
0x180013cea  jz      short loc_180013D45
0x180013cec  cmp     eax, 50h ; 'P'
0x180013cef  jnz     short loc_180013D50
0x180013cf1  mov     edx, 8; DestinationSize
0x180013cf6  lea     r8, String2; "\\\\?\\"
0x180013cfd  mov     r9d, edx; SourceSize
0x180013d00  mov     rcx, rbp; Destination
0x180013d03  call    cs:__imp_memcpy_s
0x180013d09  test    eax, eax
0x180013d0b  jz      short loc_180013D21
0x180013d0d  cmp     eax, 0Ch
0x180013d10  jz      short loc_180013D5B
0x180013d12  cmp     eax, 16h
0x180013d15  jz      short loc_180013D45
0x180013d17  cmp     eax, 22h ; '"'
0x180013d1a  jz      short loc_180013D45
0x180013d1c  cmp     eax, 50h ; 'P'
0x180013d1f  jnz     short loc_180013D50
0x180013d21  test    ebx, ebx
0x180013d23  js      short loc_180013D45
0x180013d25  mov     rax, [rdi]
0x180013d28  cmp     ebx, [rax-0Ch]
0x180013d2b  jg      short loc_180013D45
0x180013d2d  mov     [rax-10h], ebx
0x180013d30  xor     ecx, ecx
0x180013d32  mov     rdx, [rdi]
0x180013d35  mov     eax, ebx
0x180013d37  mov     [rdx+rsi*2+8], cx
0x180013d3c  add     rsp, 28h
0x180013d40  pop     rdi
0x180013d41  pop     rsi
0x180013d42  pop     rbp
0x180013d43  pop     rbx
0x180013d44  retn
0x180013d45  mov     ecx, 80070057h; int
0x180013d4a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180013d50  mov     ecx, 80004005h; int
0x180013d55  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180013d5b  mov     ecx, 8007000Eh; int
0x180013d60  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
