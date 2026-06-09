# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x14000491c`
- end: `0x1400049ef`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `211`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x1400022cc`
- `0x140005658`
- `0x1400062ec`
- `0x140006d7c`
- `0x140006fe8`
- `0x1400073b4`

## callees

- `0x140001e22`
- `0x140003004`
- `0x14000326c`
- `0x140003bf8`
- `0x14000491c`
- `0x1400055c8`
- `0x1400075e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004993`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004993`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, char *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  char *v5; // r14
  __int64 result; // rax
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // r15
  char *v10; // rcx
  __int64 v11; // rsi

  v4 = (int)a3;
  v5 = a2;
  if ( !(_DWORD)a3 )
    return ATL::CSimpleStringT<unsigned short,0>::Empty(a1, a2, a3);
  if ( !a2 )
    goto LABEL_16;
  v8 = (__int64)&a2[-*a1] >> 1;
  v9 = *(unsigned int *)(*a1 - 16);
  if ( (int)((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
  v10 = (char *)*a1;
  v11 = 2 * v4;
  if ( v8 > v9 )
  {
    memcpy_s(v10, 2 * v4, v5, 2 * v4);
  }
  else if ( v11 )
  {
    if ( v10 && (a2 = &v10[2 * v8]) != 0 )
    {
      memmove_0(v10, a2, 2 * v4);
    }
    else
    {
      *(_DWORD *)_o__errno(v10, a2, a3, a4) = 22;
      invalid_parameter_noinfo();
    }
  }
  if ( (int)v4 < 0 || (int)v4 > *(_DWORD *)(*a1 - 12) )
LABEL_16:
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16) = v4;
  result = 0;
  *(_WORD *)(v11 + *a1) = 0;
  return result;
}

```

## disassembly

```asm
0x14000491c  push    rbx
0x14000491e  push    rbp
0x14000491f  push    rsi
0x140004920  push    rdi
0x140004921  push    r14
0x140004923  push    r15
0x140004925  sub     rsp, 28h
0x140004929  movsxd  rbx, r8d
0x14000492c  mov     r14, rdx
0x14000492f  mov     rdi, rcx
0x140004932  test    r8d, r8d
0x140004935  jnz     short loc_140004949
0x140004937  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14000493c  add     rsp, 28h
0x140004940  pop     r15
0x140004942  pop     r14
0x140004944  pop     rdi
0x140004945  pop     rsi
0x140004946  pop     rbp
0x140004947  pop     rbx
0x140004948  retn
0x140004949  test    r14, r14
0x14000494c  jz      loc_1400049E4
0x140004952  mov     rax, [rcx]
0x140004955  mov     rbp, r14
0x140004958  sub     rbp, rax
0x14000495b  mov     ecx, 1
0x140004960  sar     rbp, 1
0x140004963  sub     ecx, [rax-8]
0x140004966  mov     r15d, [rax-10h]
0x14000496a  mov     eax, [rax-0Ch]
0x14000496d  sub     eax, ebx
0x14000496f  or      ecx, eax
0x140004971  jge     short loc_14000497D
0x140004973  mov     edx, ebx
0x140004975  mov     rcx, rdi
0x140004978  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14000497d  mov     rcx, [rdi]; void *
0x140004980  lea     rsi, [rbx+rbx]
0x140004984  cmp     rbp, r15
0x140004987  ja      short loc_1400049B9
0x140004989  test    rsi, rsi
0x14000498c  jz      short loc_1400049C7
0x14000498e  test    rcx, rcx
0x140004991  jnz     short loc_1400049A6
0x140004993  call    cs:__imp__o__errno
0x140004999  mov     dword ptr [rax], 16h
0x14000499f  call    _invalid_parameter_noinfo
0x1400049a4  jmp     short loc_1400049C7
0x1400049a6  lea     rdx, [rcx+rbp*2]; Src
0x1400049aa  test    rdx, rdx
0x1400049ad  jz      short loc_140004993
0x1400049af  mov     r8, rsi; Size
0x1400049b2  call    memmove_0
0x1400049b7  jmp     short loc_1400049C7
0x1400049b9  mov     r9, rsi; SourceSize
0x1400049bc  mov     r8, r14; Source
0x1400049bf  mov     rdx, rsi; DestinationSize
0x1400049c2  call    memcpy_s
0x1400049c7  test    ebx, ebx
0x1400049c9  js      short loc_1400049E4
0x1400049cb  mov     rax, [rdi]
0x1400049ce  cmp     ebx, [rax-0Ch]
0x1400049d1  jg      short loc_1400049E4
0x1400049d3  mov     [rax-10h], ebx
0x1400049d6  xor     eax, eax
0x1400049d8  mov     rcx, [rdi]
0x1400049db  mov     [rsi+rcx], ax
0x1400049df  jmp     loc_14000493C
0x1400049e4  mov     ecx, 80070057h; int
0x1400049e9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
