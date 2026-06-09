# SplitCommandLine(ushort *,ushort * *)

- ea: `0x140014330`
- end: `0x1400143fb`
- name: `?SplitCommandLine@@YAIPEAGPEAPEAG@Z`
- size: `203`
- prototype: `unsigned int __fastcall(wchar_t *Destination, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002310`
- `0x140006c88`

## callees

- `0x140014330`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1400143a9`
- `msvcrt!wcscpy_s` at `0x1400143a9`

## pseudocode

```c
__int64 __fastcall SplitCommandLine(wchar_t *Destination, unsigned __int16 **a2)
{
  wchar_t *v3; // rbx
  unsigned int v4; // esi
  wchar_t v5; // ax
  bool v6; // di
  unsigned __int16 *v7; // rbp
  __int64 v8; // rdx

  v3 = Destination;
  v4 = 0;
  if ( !*Destination )
    return v4;
  do
  {
    while ( 1 )
    {
      v5 = *v3;
      if ( *v3 != 32 && v5 != 9 )
        break;
      ++v3;
    }
    if ( !v5 )
      return v4;
    v6 = 0;
    v7 = v3;
    while ( 1 )
    {
      if ( v5 != 32 && v5 != 9 )
      {
        if ( v5 == 34 )
        {
          v6 = !v6;
          if ( a2 )
          {
            v8 = -1;
            do
              ++v8;
            while ( v3[v8] );
            wcscpy_s(v3, v8 + 1, v3 + 1);
            --v3;
          }
        }
        goto LABEL_15;
      }
      if ( !v6 )
        break;
LABEL_15:
      v5 = *++v3;
      if ( !*v3 )
        goto LABEL_20;
    }
    if ( a2 )
      *v3 = 0;
    ++v3;
LABEL_20:
    if ( a2 )
      a2[v4] = v7;
    ++v4;
  }
  while ( *v3 );
  return v4;
}

```

## disassembly

```asm
0x140014330  push    rbx
0x140014332  push    rbp
0x140014333  push    rsi
0x140014334  push    rdi
0x140014335  push    r14
0x140014337  push    r15
0x140014339  sub     rsp, 28h
0x14001433d  xor     r15d, r15d
0x140014340  mov     r14, rdx
0x140014343  mov     rbx, rcx
0x140014346  mov     esi, r15d
0x140014349  cmp     [rcx], r15w
0x14001434d  jz      loc_1400143EC
0x140014353  movzx   eax, word ptr [rbx]
0x140014356  cmp     ax, 20h ; ' '
0x14001435a  jz      short loc_140014362
0x14001435c  cmp     ax, 9
0x140014360  jnz     short loc_140014368
0x140014362  add     rbx, 2
0x140014366  jmp     short loc_140014353
0x140014368  test    ax, ax
0x14001436b  jz      short loc_1400143EC
0x14001436d  mov     dil, r15b
0x140014370  mov     rbp, rbx
0x140014373  cmp     ax, 20h ; ' '
0x140014377  jz      short loc_1400143B5
0x140014379  cmp     ax, 9
0x14001437d  jz      short loc_1400143B5
0x14001437f  cmp     ax, 22h ; '"'
0x140014383  jnz     short loc_1400143BA
0x140014385  test    dil, dil
0x140014388  setz    dil
0x14001438c  test    r14, r14
0x14001438f  jz      short loc_1400143BA
0x140014391  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140014395  inc     rdx
0x140014398  cmp     [rbx+rdx*2], r15w
0x14001439d  jnz     short loc_140014395
0x14001439f  lea     r8, [rbx+2]; Source
0x1400143a3  inc     rdx; SizeInWords
0x1400143a6  mov     rcx, rbx; Destination
0x1400143a9  call    cs:__imp_wcscpy_s
0x1400143af  sub     rbx, 2
0x1400143b3  jmp     short loc_1400143BA
0x1400143b5  test    dil, dil
0x1400143b8  jz      short loc_1400143C8
0x1400143ba  add     rbx, 2
0x1400143be  movzx   eax, word ptr [rbx]
0x1400143c1  test    ax, ax
0x1400143c4  jnz     short loc_140014373
0x1400143c6  jmp     short loc_1400143D5
0x1400143c8  test    r14, r14
0x1400143cb  jz      short loc_1400143D1
0x1400143cd  mov     [rbx], r15w
0x1400143d1  add     rbx, 2
0x1400143d5  test    r14, r14
0x1400143d8  jz      short loc_1400143E0
0x1400143da  mov     ecx, esi
0x1400143dc  mov     [r14+rcx*8], rbp
0x1400143e0  inc     esi
0x1400143e2  cmp     [rbx], r15w
0x1400143e6  jnz     loc_140014353
0x1400143ec  mov     eax, esi
0x1400143ee  add     rsp, 28h
0x1400143f2  pop     r15
0x1400143f4  pop     r14
0x1400143f6  pop     rdi
0x1400143f7  pop     rsi
0x1400143f8  pop     rbp
0x1400143f9  pop     rbx
0x1400143fa  retn
```
