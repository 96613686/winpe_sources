# LOG_WRITER::AppendSanitizedStringOrHyphen(STRA *,char *,ulong,char,int)

- ea: `0x180002ba8`
- end: `0x180002c22`
- name: `?AppendSanitizedStringOrHyphen@LOG_WRITER@@AEAAJPEAVSTRA@@PEADKDH@Z`
- size: `122`
- prototype: `int __fastcall(LOG_WRITER *this, struct STRA *, char *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003718`

## callees

- `0x180002ba8`

## import_xrefs

- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x180002bd0`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x180002bd0`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180002bf7`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180002bf7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002c13`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180002c13`

## pseudocode

```c
int __fastcall LOG_WRITER::AppendSanitizedStringOrHyphen(LOG_WRITER *this, struct STRA *a2, char *a3, unsigned int a4)
{
  int result; // eax
  unsigned int v8; // esi
  const char *v9; // rdx
  char v10; // [rsp+20h] [rbp-38h] BYREF

  v10 = 43;
  if ( !a4 )
    return STRA::Append(a2, "-");
  result = STRA::Resize(a2, a4 + *((_DWORD *)a2 + 12) + 2);
  if ( result >= 0 )
  {
    v8 = 0;
    do
    {
      if ( (unsigned __int8)*a3 <= 0x20u || (v9 = a3, *a3 == 127) )
        v9 = &v10;
      result = STRA::Append(a2, v9, 1u);
      if ( result < 0 )
        break;
      ++a3;
      ++v8;
    }
    while ( v8 < a4 );
  }
  return result;
}

```

## disassembly

```asm
0x180002ba8  push    rbx
0x180002baa  push    rbp
0x180002bab  push    rsi
0x180002bac  push    rdi
0x180002bad  sub     rsp, 38h
0x180002bb1  mov     [rsp+58h+var_38], 2Bh ; '+'
0x180002bb6  mov     ebp, r9d
0x180002bb9  mov     rdi, r8
0x180002bbc  mov     rbx, rdx
0x180002bbf  mov     rcx, rdx
0x180002bc2  test    r9d, r9d
0x180002bc5  jz      short loc_180002C0C
0x180002bc7  mov     edx, [rdx+30h]
0x180002bca  add     edx, 2
0x180002bcd  add     edx, r9d
0x180002bd0  call    cs:__imp_?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x180002bd6  test    eax, eax
0x180002bd8  js      short loc_180002C19
0x180002bda  xor     esi, esi
0x180002bdc  cmp     byte ptr [rdi], 20h ; ' '
0x180002bdf  jbe     short loc_180002BE9
0x180002be1  cmp     byte ptr [rdi], 7Fh
0x180002be4  mov     rdx, rdi
0x180002be7  jnz     short loc_180002BEE
0x180002be9  lea     rdx, [rsp+58h+var_38]
0x180002bee  mov     r8d, 1
0x180002bf4  mov     rcx, rbx
0x180002bf7  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180002bfd  test    eax, eax
0x180002bff  js      short loc_180002C19
0x180002c01  inc     rdi
0x180002c04  inc     esi
0x180002c06  cmp     esi, ebp
0x180002c08  jb      short loc_180002BDC
0x180002c0a  jmp     short loc_180002C19
0x180002c0c  lea     rdx, asc_180012088; "-"
0x180002c13  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180002c19  add     rsp, 38h
0x180002c1d  pop     rdi
0x180002c1e  pop     rsi
0x180002c1f  pop     rbp
0x180002c20  pop     rbx
0x180002c21  retn
```
