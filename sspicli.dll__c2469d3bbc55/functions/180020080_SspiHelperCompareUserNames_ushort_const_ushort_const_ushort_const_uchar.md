# SspiHelperCompareUserNames(ushort const *,ushort const *,ushort const *,uchar *)

- ea: `0x180020080`
- end: `0x1800201de`
- name: `?SspiHelperCompareUserNames@@YAJPEBG00PEAE@Z`
- size: `350`
- prototype: `__int64 __fastcall(PCWSTR, PCWSTR SourceString, PCWSTR, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800110f0`

## callees

- `0x180014d38`
- `0x180018600`
- `0x180020080`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x1800200d3`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180020145`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x1800200d3`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180020145`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020114`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020114`

## pseudocode

```c
__int64 __fastcall SspiHelperCompareUserNames(
        PCWSTR a1,
        unsigned __int64 SourceString,
        unsigned __int64 a3,
        unsigned __int8 *a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  PCWSTR v7; // rbx
  unsigned int v8; // ebx
  wchar_t *v9; // rbp
  const WCHAR *v10; // r12
  __int64 v11; // r14
  wchar_t *v12; // rax
  wchar_t *v13; // rax

  *a4 = 0;
  v5 = a3;
  v6 = SourceString;
  v7 = a1;
  if ( !a1 )
  {
    if ( !SourceString && !a3 )
      *a4 = 1;
    return 0;
  }
  if ( !SourceString && !a3 )
    return 0;
  v9 = 0;
  v10 = 0;
  if ( wcschr(a1, 0x5Cu) )
  {
    v11 = -1;
    do
      ++v11;
    while ( v7[v11] );
    if ( (unsigned int)v11 > 0x7FFD )
      return (unsigned int)-1073741811;
    v12 = (wchar_t *)LocalAlloc(0x40u, (unsigned int)(2 * v11 + 2) + 2LL);
    v9 = v12;
    if ( !v12 )
      return (unsigned int)-1073741801;
    memcpy_0(v12, v7, 2LL * (unsigned int)v11);
    v13 = wcschr(v9, 0x5Cu);
    if ( v13 )
    {
      *v13 = 0;
      v7 = (PCWSTR)((unsigned __int64)(v13 + 1) & -(__int64)(v13[1] != 0));
      if ( *v9 )
        v10 = v9;
    }
  }
  if ( v6 )
    v6 &= -(__int64)(*(_WORD *)v6 != 0);
  if ( v5 )
    v5 &= -(__int64)(*(_WORD *)v5 != 0);
  if ( SspiHelperEqualStrings((PCWSTR)v6, v7, 1u) && SspiHelperEqualStrings((PCWSTR)v5, v10, 1u) )
    *a4 = 1;
  v8 = 0;
  if ( v9 )
    SspiLocalFree(v9);
  return v8;
}

```

## disassembly

```asm
0x180020080  push    rbx
0x180020082  push    rbp
0x180020083  push    rsi
0x180020084  push    rdi
0x180020085  push    r12
0x180020087  push    r13
0x180020089  push    r14
0x18002008b  push    r15
0x18002008d  sub     rsp, 28h
0x180020091  xor     r13d, r13d
0x180020094  mov     r15, r9
0x180020097  mov     [r9], r13b
0x18002009a  mov     rdi, r8
0x18002009d  mov     rsi, rdx
0x1800200a0  mov     rbx, rcx
0x1800200a3  test    rcx, rcx
0x1800200a6  jnz     short loc_1800200BE
0x1800200a8  test    rdx, rdx
0x1800200ab  jnz     short loc_1800200B6
0x1800200ad  test    r8, r8
0x1800200b0  jnz     short loc_1800200B6
0x1800200b2  mov     byte ptr [r9], 1
0x1800200b6  mov     ebx, r13d
0x1800200b9  jmp     loc_1800201CB
0x1800200be  test    rsi, rsi
0x1800200c1  jnz     short loc_1800200C8
0x1800200c3  test    rdi, rdi
0x1800200c6  jz      short loc_1800200B6
0x1800200c8  mov     edx, 5Ch ; '\'; Ch
0x1800200cd  mov     rbp, r13
0x1800200d0  mov     r12, r13
0x1800200d3  call    cs:__imp_wcschr
0x1800200d9  test    rax, rax
0x1800200dc  jz      loc_180020171
0x1800200e2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800200e6  inc     r14
0x1800200e9  cmp     [rbx+r14*2], r13w
0x1800200ee  jnz     short loc_1800200E6
0x1800200f0  cmp     r14d, 7FFDh
0x1800200f7  jbe     short loc_180020103
0x1800200f9  mov     ebx, 0C000000Dh
0x1800200fe  jmp     loc_1800201CB
0x180020103  lea     edx, ds:2[r14*2]
0x18002010b  mov     ecx, 40h ; '@'; uFlags
0x180020110  add     rdx, 2; uBytes
0x180020114  call    cs:__imp_LocalAlloc
0x18002011a  mov     rbp, rax
0x18002011d  test    rax, rax
0x180020120  jnz     short loc_18002012C
0x180020122  mov     ebx, 0C0000017h
0x180020127  jmp     loc_1800201CB
0x18002012c  mov     r8d, r14d
0x18002012f  mov     rdx, rbx; Src
0x180020132  add     r8, r8; Size
0x180020135  mov     rcx, rbp; void *
0x180020138  call    memcpy_0
0x18002013d  mov     edx, 5Ch ; '\'; Ch
0x180020142  mov     rcx, rbp; Str
0x180020145  call    cs:__imp_wcschr
0x18002014b  mov     rcx, rax
0x18002014e  test    rax, rax
0x180020151  jz      short loc_180020171
0x180020153  add     rcx, 2
0x180020157  mov     [rax], r13w
0x18002015b  movzx   eax, word ptr [rcx]
0x18002015e  neg     ax
0x180020161  sbb     rbx, rbx
0x180020164  and     rbx, rcx
0x180020167  cmp     [rbp+0], r13w
0x18002016c  jz      short loc_180020171
0x18002016e  mov     r12, rbp
0x180020171  test    rsi, rsi
0x180020174  jz      short loc_180020182
0x180020176  movzx   eax, word ptr [rsi]
0x180020179  neg     ax
0x18002017c  sbb     rcx, rcx
0x18002017f  and     rsi, rcx
0x180020182  test    rdi, rdi
0x180020185  jz      short loc_180020193
0x180020187  movzx   eax, word ptr [rdi]
0x18002018a  neg     ax
0x18002018d  sbb     rcx, rcx
0x180020190  and     rdi, rcx
0x180020193  mov     r8b, 1; CaseInsensitive
0x180020196  mov     rdx, rbx; PCWSTR
0x180020199  mov     rcx, rsi; SourceString
0x18002019c  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x1800201a1  test    al, al
0x1800201a3  jz      short loc_1800201BB
0x1800201a5  mov     r8b, 1; CaseInsensitive
0x1800201a8  mov     rdx, r12; PCWSTR
0x1800201ab  mov     rcx, rdi; SourceString
0x1800201ae  call    ?SspiHelperEqualStrings@@YAEPEBG0E@Z; SspiHelperEqualStrings(ushort const *,ushort const *,uchar)
0x1800201b3  test    al, al
0x1800201b5  jz      short loc_1800201BB
0x1800201b7  mov     byte ptr [r15], 1
0x1800201bb  mov     ebx, r13d
0x1800201be  test    rbp, rbp
0x1800201c1  jz      short loc_1800201CB
0x1800201c3  mov     rcx, rbp; DataBuffer
0x1800201c6  call    SspiLocalFree
0x1800201cb  mov     eax, ebx
0x1800201cd  add     rsp, 28h
0x1800201d1  pop     r15
0x1800201d3  pop     r14
0x1800201d5  pop     r13
0x1800201d7  pop     r12
0x1800201d9  pop     rdi
0x1800201da  pop     rsi
0x1800201db  pop     rbp
0x1800201dc  pop     rbx
0x1800201dd  retn
```
