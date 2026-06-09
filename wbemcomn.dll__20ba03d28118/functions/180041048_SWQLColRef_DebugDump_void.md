# SWQLColRef::DebugDump(void)

- ea: `0x180041048`
- end: `0x1800411a8`
- name: `?DebugDump@SWQLColRef@@QEAAXXZ`
- size: `352`
- prototype: `void __fastcall(const wchar_t **this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800411b0`

## callees

- `0x180041048`

## import_xrefs

- `msvcrt!printf` at `0x180041058`
- `msvcrt!printf` at `0x180041068`
- `msvcrt!printf` at `0x180041079`
- `msvcrt!printf` at `0x180041089`
- `msvcrt!printf` at `0x180041099`
- `msvcrt!printf` at `0x1800410ac`
- `msvcrt!printf` at `0x1800410bf`
- `msvcrt!printf` at `0x1800410d2`
- `msvcrt!printf` at `0x1800410e8`
- `msvcrt!printf` at `0x1800410fe`
- `msvcrt!printf` at `0x180041114`
- `msvcrt!printf` at `0x18004112a`
- `msvcrt!printf` at `0x180041140`
- `msvcrt!printf` at `0x180041156`
- `msvcrt!printf` at `0x18004116c`
- `msvcrt!printf` at `0x180041182`
- `msvcrt!printf` at `0x18004118f`
- `msvcrt!printf` at `0x180041058`
- `msvcrt!printf` at `0x180041068`
- `msvcrt!printf` at `0x180041079`
- `msvcrt!printf` at `0x180041089`
- `msvcrt!printf` at `0x180041099`
- `msvcrt!printf` at `0x1800410ac`
- `msvcrt!printf` at `0x1800410bf`
- `msvcrt!printf` at `0x1800410d2`
- `msvcrt!printf` at `0x1800410e8`
- `msvcrt!printf` at `0x1800410fe`
- `msvcrt!printf` at `0x180041114`
- `msvcrt!printf` at `0x18004112a`
- `msvcrt!printf` at `0x180041140`
- `msvcrt!printf` at `0x180041156`
- `msvcrt!printf` at `0x18004116c`
- `msvcrt!printf` at `0x180041182`
- `msvcrt!printf` at `0x18004118f`
- `msvcrt!printf` at `0x1800411a1`

## string_xrefs

- `0x18004110d`: `WQL_FLAG_COMPLEX_NAME `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SWQLColRef::DebugDump(const wchar_t **this)
{
  printf("  ---SWQLColRef---\n");
  printf("  Col Name    = %S\n", *this);
  printf("  Table       = %S\n", this[1]);
  printf("  Array Index = %d\n", *((_DWORD *)this + 4));
  printf("  Flags       = 0x%X ", *((_DWORD *)this + 5));
  if ( (*((_BYTE *)this + 20) & 2) != 0 )
    printf("WQL_FLAG_TABLE ");
  if ( *((char *)this + 20) < 0 )
    printf("WQL_FLAG_COLUMN ");
  if ( (*((_BYTE *)this + 20) & 4) != 0 )
    printf("WQL_FLAG_ASTERISK ");
  if ( (*((_DWORD *)this + 5) & 0x40000) != 0 )
    printf("WQL_FLAG_NULL ");
  if ( (*((_DWORD *)this + 5) & 0x200) != 0 )
    printf("WQL_FLAG_FUNCTIONIZED ");
  if ( (*((_DWORD *)this + 5) & 0x100) != 0 )
    printf("WQL_FLAG_COMPLEX_NAME ");
  if ( (*((_DWORD *)this + 5) & 0x400) != 0 )
    printf(" WQL_FLAG_ARRAY_REF");
  if ( (*((_DWORD *)this + 5) & 0x800) != 0 )
    printf(" WQL_FLAG_UPPER");
  if ( (*((_DWORD *)this + 5) & 0x1000) != 0 )
    printf(" WQL_FLAG_LOWER");
  if ( (*((_DWORD *)this + 5) & 0x8000) != 0 )
    printf(" WQL_FLAG_SORT_ASC");
  if ( (*((_DWORD *)this + 5) & 0x10000) != 0 )
    printf(" WQL_FLAG_SORT_DESC");
  printf("\n");
  printf("  ---\n\n");
}

```

## disassembly

```asm
0x180041048  push    rbx
0x18004104a  sub     rsp, 20h
0x18004104e  mov     rbx, rcx
0x180041051  lea     rcx, aSwqlcolref; "  ---SWQLColRef---\n"
0x180041058  call    cs:__imp_printf
0x18004105e  mov     rdx, [rbx]
0x180041061  lea     rcx, aColNameS; "  Col Name    = %S\n"
0x180041068  call    cs:__imp_printf
0x18004106e  mov     rdx, [rbx+8]
0x180041072  lea     rcx, aTableS; "  Table       = %S\n"
0x180041079  call    cs:__imp_printf
0x18004107f  mov     edx, [rbx+10h]
0x180041082  lea     rcx, aArrayIndexD; "  Array Index = %d\n"
0x180041089  call    cs:__imp_printf
0x18004108f  mov     edx, [rbx+14h]
0x180041092  lea     rcx, aFlags0xX; "  Flags       = 0x%X "
0x180041099  call    cs:__imp_printf
0x18004109f  test    byte ptr [rbx+14h], 2
0x1800410a3  jz      short loc_1800410B2
0x1800410a5  lea     rcx, aWqlFlagTable; "WQL_FLAG_TABLE "
0x1800410ac  call    cs:__imp_printf
0x1800410b2  test    byte ptr [rbx+14h], 80h
0x1800410b6  jz      short loc_1800410C5
0x1800410b8  lea     rcx, aWqlFlagColumn; "WQL_FLAG_COLUMN "
0x1800410bf  call    cs:__imp_printf
0x1800410c5  test    byte ptr [rbx+14h], 4
0x1800410c9  jz      short loc_1800410D8
0x1800410cb  lea     rcx, aWqlFlagAsteris; "WQL_FLAG_ASTERISK "
0x1800410d2  call    cs:__imp_printf
0x1800410d8  test    dword ptr [rbx+14h], 40000h
0x1800410df  jz      short loc_1800410EE
0x1800410e1  lea     rcx, aWqlFlagNull; "WQL_FLAG_NULL "
0x1800410e8  call    cs:__imp_printf
0x1800410ee  test    dword ptr [rbx+14h], 200h
0x1800410f5  jz      short loc_180041104
0x1800410f7  lea     rcx, aWqlFlagFunctio; "WQL_FLAG_FUNCTIONIZED "
0x1800410fe  call    cs:__imp_printf
0x180041104  test    dword ptr [rbx+14h], 100h
0x18004110b  jz      short loc_18004111A
0x18004110d  lea     rcx, aWqlFlagComplex; "WQL_FLAG_COMPLEX_NAME "
0x180041114  call    cs:__imp_printf
0x18004111a  test    dword ptr [rbx+14h], 400h
0x180041121  jz      short loc_180041130
0x180041123  lea     rcx, aWqlFlagArrayRe; " WQL_FLAG_ARRAY_REF"
0x18004112a  call    cs:__imp_printf
0x180041130  test    dword ptr [rbx+14h], 800h
0x180041137  jz      short loc_180041146
0x180041139  lea     rcx, aWqlFlagUpper; " WQL_FLAG_UPPER"
0x180041140  call    cs:__imp_printf
0x180041146  test    dword ptr [rbx+14h], 1000h
0x18004114d  jz      short loc_18004115C
0x18004114f  lea     rcx, aWqlFlagLower; " WQL_FLAG_LOWER"
0x180041156  call    cs:__imp_printf
0x18004115c  test    dword ptr [rbx+14h], 8000h
0x180041163  jz      short loc_180041172
0x180041165  lea     rcx, aWqlFlagSortAsc; " WQL_FLAG_SORT_ASC"
0x18004116c  call    cs:__imp_printf
0x180041172  test    dword ptr [rbx+14h], 10000h
0x180041179  jz      short loc_180041188
0x18004117b  lea     rcx, aWqlFlagSortDes; " WQL_FLAG_SORT_DESC"
0x180041182  call    cs:__imp_printf
0x180041188  lea     rcx, asc_18004DD1C; "\n"
0x18004118f  call    cs:__imp_printf
0x180041195  lea     rcx, asc_18004DD20; "  ---\n\n"
0x18004119c  add     rsp, 20h
0x1800411a0  pop     rbx
0x1800411a1  jmp     cs:__imp_printf
```
