# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x180014850`
- end: `0x180014957`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `263`
- prototype: `__int64 __fastcall(__int64 *, const void *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180014028`
- `0x18001424c`

## callees

- `0x180003a60`
- `0x1800144f0`
- `0x180014850`
- `0x18001c010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001491e`
- `msvcrt!memmove_s` at `0x18001491e`
- `msvcrt!memcpy_s` at `0x180014929`
- `msvcrt!memcpy_s` at `0x180014929`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rdi
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // r15
  char *v11; // rcx
  rsize_t v12; // r9
  rsize_t v13; // rdx

  v3 = a3;
  if ( a3 )
  {
    if ( a2 )
    {
      v9 = ((__int64)a2 - *a1) >> 1;
      v10 = *(unsigned int *)(*a1 - 16);
      if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
      v11 = (char *)*a1;
      v12 = 2 * v3;
      v13 = 2 * v3;
      if ( v9 > v10 )
        memcpy_s(v11, v13, a2, v12);
      else
        memmove_s(v11, v13, &v11[2 * v9], v12);
      if ( (int)v3 >= 0 && (int)v3 <= *(_DWORD *)(*a1 - 12) )
      {
        *(_DWORD *)(*a1 - 16) = v3;
        result = 0;
        *(_WORD *)(2 * v3 + *a1) = 0;
        return result;
      }
    }
    goto LABEL_19;
  }
  result = *a1;
  v7 = (_QWORD *)(*a1 - 24);
  if ( !*((_DWORD *)v7 + 2) )
    return result;
  if ( *((int *)v7 + 4) < 0 )
  {
    if ( *(int *)(result - 12) >= 0 )
    {
      *(_DWORD *)(result - 16) = 0;
      result = 0;
      *(_WORD *)*a1 = 0;
      return result;
    }
LABEL_19:
    ATL::AtlThrowImpl(-2147024809);
  }
  v8 = *v7;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8) + 24;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180014850  push    rbx
0x180014852  push    rbp
0x180014853  push    rsi
0x180014854  push    rdi
0x180014855  push    r14
0x180014857  push    r15
0x180014859  sub     rsp, 28h
0x18001485d  movsxd  rdi, r8d
0x180014860  mov     r14, rdx
0x180014863  mov     rbx, rcx
0x180014866  test    r8d, r8d
0x180014869  jnz     short loc_1800148D8
0x18001486b  mov     rax, [rcx]
0x18001486e  lea     rdx, [rax-18h]
0x180014872  cmp     [rdx+8], r8d
0x180014876  jz      short loc_180014894
0x180014878  cmp     [rdx+10h], r8d
0x18001487c  jge     short loc_1800148A1
0x18001487e  cmp     [rax-0Ch], r8d
0x180014882  jl      loc_18001494C
0x180014888  mov     [rax-10h], r8d
0x18001488c  xor     eax, eax
0x18001488e  mov     rcx, [rcx]
0x180014891  mov     [rcx], ax
0x180014894  add     rsp, 28h
0x180014898  pop     r15
0x18001489a  pop     r14
0x18001489c  pop     rdi
0x18001489d  pop     rsi
0x18001489e  pop     rbp
0x18001489f  pop     rbx
0x1800148a0  retn
0x1800148a1  mov     rdi, [rdx]
0x1800148a4  or      eax, 0FFFFFFFFh
0x1800148a7  lock xadd [rdx+10h], eax
0x1800148ac  sub     eax, 1
0x1800148af  jg      short loc_1800148C0
0x1800148b1  mov     rcx, [rdx]
0x1800148b4  mov     rax, [rcx]
0x1800148b7  mov     rax, [rax+8]
0x1800148bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148c0  mov     rax, [rdi]
0x1800148c3  mov     rcx, rdi
0x1800148c6  mov     rax, [rax+18h]
0x1800148ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148cf  add     rax, 18h
0x1800148d3  mov     [rbx], rax
0x1800148d6  jmp     short loc_180014894
0x1800148d8  test    r14, r14
0x1800148db  jz      short loc_18001494C
0x1800148dd  mov     rax, [rcx]
0x1800148e0  mov     rbp, r14
0x1800148e3  sub     rbp, rax
0x1800148e6  mov     ecx, 1
0x1800148eb  sar     rbp, 1
0x1800148ee  sub     ecx, [rax-8]
0x1800148f1  mov     r15d, [rax-10h]
0x1800148f5  mov     eax, [rax-0Ch]
0x1800148f8  sub     eax, edi
0x1800148fa  or      ecx, eax
0x1800148fc  jge     short loc_180014908
0x1800148fe  mov     edx, edi
0x180014900  mov     rcx, rbx
0x180014903  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180014908  mov     rcx, [rbx]; Destination
0x18001490b  lea     rsi, [rdi+rdi]
0x18001490f  mov     r9, rsi; SourceSize
0x180014912  mov     rdx, rsi; DestinationSize
0x180014915  cmp     rbp, r15
0x180014918  ja      short loc_180014926
0x18001491a  lea     r8, [rcx+rbp*2]; Source
0x18001491e  call    cs:__imp_memmove_s
0x180014924  jmp     short loc_18001492F
0x180014926  mov     r8, r14; Source
0x180014929  call    cs:__imp_memcpy_s
0x18001492f  test    edi, edi
0x180014931  js      short loc_18001494C
0x180014933  mov     rax, [rbx]
0x180014936  cmp     edi, [rax-0Ch]
0x180014939  jg      short loc_18001494C
0x18001493b  mov     [rax-10h], edi
0x18001493e  xor     eax, eax
0x180014940  mov     rcx, [rbx]
0x180014943  mov     [rsi+rcx], ax
0x180014947  jmp     loc_180014894
0x18001494c  mov     ecx, 80070057h; int
0x180014951  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
