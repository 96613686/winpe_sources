# ComputeRootKey(CDynamicArray<ushort,ushort *> &,ushort const *,uint &)

- ea: `0x18001069c`
- end: `0x1800107bc`
- name: `?ComputeRootKey@@YAHAEAV?$CDynamicArray@GPEAG@@PEBGAEAI@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012464`

## callees

- `0x180009e30`
- `0x18001069c`
- `0x180017f94`

## import_xrefs

- `msvcrt!wcschr` at `0x1800106ba`
- `msvcrt!wcschr` at `0x1800106d1`
- `msvcrt!wcschr` at `0x18001071c`
- `msvcrt!wcschr` at `0x1800106ba`
- `msvcrt!wcschr` at `0x1800106d1`
- `msvcrt!wcschr` at `0x18001071c`
- `msvcrt!wcsrchr` at `0x180010787`
- `msvcrt!wcsrchr` at `0x180010787`

## pseudocode

```c
__int64 __fastcall ComputeRootKey(__int64 a1, wchar_t *a2, _DWORD *a3)
{
  wchar_t *v6; // rsi
  wchar_t *v7; // rax
  wchar_t *v8; // rbx
  const wchar_t *i; // rcx
  wchar_t *v10; // rax
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax

  v6 = wcschr(a2, 0x3Fu);
  v7 = wcschr(a2, 0x2Au);
  v8 = v7;
  if ( v7 )
  {
    if ( v6 && v6 < v7 )
      v8 = v6;
    *a3 = -1;
  }
  else
  {
    *a3 = 0;
    v8 = 0;
    if ( v6 )
    {
      v8 = v6;
      for ( i = v6; ; i = v10 + 1 )
      {
        v10 = wcschr(i, 0x3Fu);
        if ( !v10 )
          break;
        ++*a3;
      }
    }
  }
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( !(unsigned int)CDynamicArray<unsigned short,unsigned short *>::SetSize(a1, v11 + 1)
    || (int)StringCchCopyW(*(unsigned __int16 **)a1, *(_QWORD *)(a1 + 8), (size_t *)a2) < 0 )
  {
    return 0;
  }
  if ( v8 )
  {
    v12 = 0;
    if ( *(_QWORD *)(a1 + 8) )
      v12 = *(unsigned __int16 **)a1;
    v13 = 0;
    *((_BYTE *)v8 + (char *)v12 - (char *)a2) = 0;
    if ( *(_QWORD *)(a1 + 8) )
      v13 = *(const wchar_t **)a1;
    v14 = wcsrchr(v13, 0x5Cu);
    if ( v14 )
      *v14 = 0;
    else
      **(_WORD **)a1 = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001069c  push    rbx
0x18001069e  push    rbp
0x18001069f  push    rsi
0x1800106a0  push    rdi
0x1800106a1  push    r14
0x1800106a3  push    r15
0x1800106a5  sub     rsp, 28h
0x1800106a9  mov     rbp, rdx
0x1800106ac  mov     rdi, rcx
0x1800106af  mov     rcx, rbp; Str
0x1800106b2  mov     edx, 3Fh ; '?'; Ch
0x1800106b7  mov     r14, r8
0x1800106ba  call    cs:__imp_wcschr
0x1800106c1  nop     dword ptr [rax+rax+00h]
0x1800106c6  mov     edx, 2Ah ; '*'; Ch
0x1800106cb  mov     rcx, rbp; Str
0x1800106ce  mov     rsi, rax
0x1800106d1  call    cs:__imp_wcschr
0x1800106d8  nop     dword ptr [rax+rax+00h]
0x1800106dd  xor     r15d, r15d
0x1800106e0  mov     rbx, rax
0x1800106e3  test    rax, rax
0x1800106e6  jz      short loc_1800106FD
0x1800106e8  test    rsi, rsi
0x1800106eb  jz      short loc_1800106F4
0x1800106ed  cmp     rsi, rax
0x1800106f0  cmovb   rbx, rsi
0x1800106f4  mov     dword ptr [r14], 0FFFFFFFFh
0x1800106fb  jmp     short loc_18001072D
0x1800106fd  mov     [r14], r15d
0x180010700  mov     rbx, r15
0x180010703  test    rsi, rsi
0x180010706  jz      short loc_18001072D
0x180010708  mov     rbx, rsi
0x18001070b  mov     rcx, rsi
0x18001070e  jmp     short loc_180010717
0x180010710  inc     dword ptr [r14]
0x180010713  lea     rcx, [rax+2]; Str
0x180010717  mov     edx, 3Fh ; '?'; Ch
0x18001071c  call    cs:__imp_wcschr
0x180010723  nop     dword ptr [rax+rax+00h]
0x180010728  test    rax, rax
0x18001072b  jnz     short loc_180010710
0x18001072d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180010731  inc     rdx
0x180010734  cmp     [rbp+rdx*2+0], r15w
0x18001073a  jnz     short loc_180010731
0x18001073c  inc     rdx
0x18001073f  mov     rcx, rdi
0x180010742  call    ?SetSize@?$CDynamicArray@GPEAG@@QEAAH_K@Z; CDynamicArray<ushort,ushort *>::SetSize(unsigned __int64)
0x180010747  test    eax, eax
0x180010749  jz      short loc_1800107AC
0x18001074b  mov     rdx, [rdi+8]; unsigned __int64
0x18001074f  mov     r8, rbp; unsigned __int16 *
0x180010752  mov     rcx, [rdi]; unsigned __int16 *
0x180010755  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001075a  test    eax, eax
0x18001075c  js      short loc_1800107AC
0x18001075e  test    rbx, rbx
0x180010761  jz      short loc_1800107A5
0x180010763  mov     rax, r15
0x180010766  cmp     [rdi+8], r15
0x18001076a  jz      short loc_18001076F
0x18001076c  mov     rax, [rdi]
0x18001076f  sub     rax, rbp
0x180010772  mov     rcx, r15
0x180010775  mov     [rax+rbx], r15b
0x180010779  cmp     [rdi+8], r15
0x18001077d  jz      short loc_180010782
0x18001077f  mov     rcx, [rdi]; Str
0x180010782  mov     edx, 5Ch ; '\'; Ch
0x180010787  call    cs:__imp_wcsrchr
0x18001078e  nop     dword ptr [rax+rax+00h]
0x180010793  test    rax, rax
0x180010796  jz      short loc_18001079E
0x180010798  mov     [rax], r15w
0x18001079c  jmp     short loc_1800107A5
0x18001079e  mov     rdx, [rdi]
0x1800107a1  mov     [rdx], r15w
0x1800107a5  mov     eax, 1
0x1800107aa  jmp     short loc_1800107AE
0x1800107ac  xor     eax, eax
0x1800107ae  add     rsp, 28h
0x1800107b2  pop     r15
0x1800107b4  pop     r14
0x1800107b6  pop     rdi
0x1800107b7  pop     rsi
0x1800107b8  pop     rbp
0x1800107b9  pop     rbx
0x1800107ba  retn
```
