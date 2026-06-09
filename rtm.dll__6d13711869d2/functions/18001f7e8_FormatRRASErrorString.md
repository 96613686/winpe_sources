# FormatRRASErrorString

- ea: `0x18001f7e8`
- end: `0x18001f835`
- name: `FormatRRASErrorString`
- size: `77`
- prototype: ``
- caller_count: `75`
- callee_count: `1`
- tags: ``

## callers

- `0x1800027d8`
- `0x180002dd0`
- `0x180003a20`
- `0x180004300`
- `0x180004920`
- `0x180004b50`
- `0x1800052d0`
- `0x180005530`
- `0x180007a34`
- `0x1800094a8`
- `0x18000b440`
- `0x18000c560`
- `0x18000cf90`
- `0x180011850`
- `0x180012100`
- `0x180012620`
- `0x180012800`
- `0x180012d80`
- `0x180012ed0`
- `0x180013020`
- `0x180013140`
- `0x180013260`
- `0x180013390`
- `0x1800134c0`
- `0x1800136d0`
- `0x1800137e0`
- `0x180013930`
- `0x180013b00`
- `0x180014200`
- `0x180014580`
- `0x180014970`
- `0x180014bfc`
- `0x180014dd8`
- `0x1800151ec`
- `0x1800155fc`
- `0x1800158cc`
- `0x180015a8c`
- `0x180015f54`
- `0x180016470`
- `0x1800165d4`
- `0x1800167d0`
- `0x180016a40`
- `0x180016d00`
- `0x1800172b4`
- `0x18001740c`
- `0x1800176bc`
- `0x180017a44`
- `0x180018070`
- `0x180018c10`
- `0x180018dd4`

## callees

- `0x18001f7e8`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18001f813`
- `msvcrt!_vsnwprintf` at `0x18001f813`

## pseudocode

```c
unsigned int FormatRRASErrorString(wchar_t *a1, const wchar_t *a2, ...)
{
  unsigned int result; // eax
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  result = _vsnwprintf(a1, 0x3FFu, a2, va);
  if ( result > 0x3FE )
  {
    result = 0;
    a1[1023] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001f7e8  mov     rax, rsp
0x18001f7eb  mov     [rax+10h], rdx
0x18001f7ef  mov     [rax+18h], r8
0x18001f7f3  mov     [rax+20h], r9
0x18001f7f7  push    rbx
0x18001f7f8  sub     rsp, 30h
0x18001f7fc  mov     r8, rdx; Format
0x18001f7ff  mov     qword ptr [rax-18h], 0
0x18001f807  mov     edx, 3FFh; BufferCount
0x18001f80c  lea     r9, [rax+18h]; Args
0x18001f810  mov     rbx, rcx
0x18001f813  call    cs:__imp__vsnwprintf
0x18001f819  test    eax, eax
0x18001f81b  js      short loc_18001F826
0x18001f81d  cmp     eax, 3FFh
0x18001f822  ja      short loc_18001F826
0x18001f824  jnz     short loc_18001F82F
0x18001f826  xor     eax, eax
0x18001f828  mov     [rbx+7FEh], ax
0x18001f82f  add     rsp, 30h
0x18001f833  pop     rbx
0x18001f834  retn
```
