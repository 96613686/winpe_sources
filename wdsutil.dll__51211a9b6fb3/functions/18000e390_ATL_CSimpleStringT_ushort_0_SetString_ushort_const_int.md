# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18000e390`
- end: `0x18000e449`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `185`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a10c`
- `0x18001486c`
- `0x1800158c4`
- `0x180016698`
- `0x180019164`
- `0x18001e334`
- `0x18001ef34`
- `0x180026e6c`
- `0x18002b490`
- `0x18002dea0`

## callees

- `0x1800085b8`
- `0x18000b7f4`
- `0x18000dd14`
- `0x18000e390`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e415`
- `msvcrt!memcpy_s` at `0x18000e415`
- `msvcrt!memmove_s` at `0x18000e404`
- `msvcrt!memmove_s` at `0x18000e404`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, _BYTE *a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 result; // rax
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // r15
  char *v9; // rcx
  rsize_t v10; // r9
  rsize_t v11; // rdx

  v3 = (int)a3;
  if ( !a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty();
  if ( !a2 )
    goto LABEL_12;
  v7 = (a2 - *a1) >> 1;
  v8 = *((unsigned int *)*a1 - 4);
  if ( (((*((_DWORD *)*a1 - 3) - a3) | (1 - *((_DWORD *)*a1 - 2))) & 0x80000000) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
  v9 = *a1;
  v10 = 2 * v3;
  v11 = 2 * v3;
  if ( v7 > v8 )
    memcpy_s(v9, v11, a2, v10);
  else
    memmove_s(v9, v11, &v9[2 * v7], v10);
  if ( (int)v3 < 0 || (int)v3 > *((_DWORD *)*a1 - 3) )
LABEL_12:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a1 - 4) = v3;
  result = 0;
  *(_WORD *)&(*a1)[2 * v3] = 0;
  return result;
}

```

## disassembly

```asm
0x18000e390  push    rbx
0x18000e392  push    rbp
0x18000e393  push    rsi
0x18000e394  push    rdi
0x18000e395  push    r14
0x18000e397  push    r15
0x18000e399  sub     rsp, 28h
0x18000e39d  movsxd  rbx, r8d
0x18000e3a0  mov     r14, rdx
0x18000e3a3  mov     rdi, rcx
0x18000e3a6  test    r8d, r8d
0x18000e3a9  jnz     short loc_18000E3BE
0x18000e3ab  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000e3b0  add     rsp, 28h
0x18000e3b4  pop     r15
0x18000e3b6  pop     r14
0x18000e3b8  pop     rdi
0x18000e3b9  pop     rsi
0x18000e3ba  pop     rbp
0x18000e3bb  pop     rbx
0x18000e3bc  retn
0x18000e3be  test    r14, r14
0x18000e3c1  jz      short loc_18000E43E
0x18000e3c3  mov     rax, [rcx]
0x18000e3c6  mov     rbp, r14
0x18000e3c9  sub     rbp, rax
0x18000e3cc  mov     ecx, 1
0x18000e3d1  sar     rbp, 1
0x18000e3d4  sub     ecx, [rax-8]
0x18000e3d7  mov     r15d, [rax-10h]
0x18000e3db  mov     eax, [rax-0Ch]
0x18000e3de  sub     eax, ebx
0x18000e3e0  or      ecx, eax
0x18000e3e2  jge     short loc_18000E3EE
0x18000e3e4  mov     edx, ebx
0x18000e3e6  mov     rcx, rdi
0x18000e3e9  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000e3ee  mov     rcx, [rdi]; Destination
0x18000e3f1  lea     rsi, [rbx+rbx]
0x18000e3f5  mov     r9, rsi; SourceSize
0x18000e3f8  mov     rdx, rsi; DestinationSize
0x18000e3fb  cmp     rbp, r15
0x18000e3fe  ja      short loc_18000E412
0x18000e400  lea     r8, [rcx+rbp*2]; Source
0x18000e404  call    cs:__imp_memmove_s
0x18000e40b  nop     dword ptr [rax+rax+00h]
0x18000e410  jmp     short loc_18000E421
0x18000e412  mov     r8, r14; Source
0x18000e415  call    cs:__imp_memcpy_s
0x18000e41c  nop     dword ptr [rax+rax+00h]
0x18000e421  test    ebx, ebx
0x18000e423  js      short loc_18000E43E
0x18000e425  mov     rax, [rdi]
0x18000e428  cmp     ebx, [rax-0Ch]
0x18000e42b  jg      short loc_18000E43E
0x18000e42d  mov     [rax-10h], ebx
0x18000e430  xor     eax, eax
0x18000e432  mov     rcx, [rdi]
0x18000e435  mov     [rsi+rcx], ax
0x18000e439  jmp     loc_18000E3B0
0x18000e43e  mov     ecx, 80070057h; int
0x18000e443  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
