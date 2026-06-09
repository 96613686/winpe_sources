# LOG_WRITER::AppendSanitizedStringOrHyphen(STRU *,ushort *,ulong,ushort,int)

- ea: `0x180002d38`
- end: `0x180002ddc`
- name: `?AppendSanitizedStringOrHyphen@LOG_WRITER@@AEAAJPEAVSTRU@@PEAGKGH@Z`
- size: `164`
- prototype: `int __fastcall(LOG_WRITER *this, struct STRU *, unsigned __int16 *, unsigned int, unsigned __int16, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002de4`
- `0x180003718`

## callees

- `0x180002d38`

## import_xrefs

- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180002d69`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180002d69`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002daf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002dcd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002daf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002dcd`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002d92`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002d92`

## pseudocode

```c
int __fastcall LOG_WRITER::AppendSanitizedStringOrHyphen(
        LOG_WRITER *this,
        struct STRU *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 a5,
        int a6)
{
  int result; // eax
  int v10; // esi
  const unsigned __int16 *v11; // rdx
  __int16 v12; // [rsp+20h] [rbp-38h] BYREF

  v12 = 43;
  if ( a4 )
  {
    result = STRU::Resize(a2, 2 * (a4 + *((_DWORD *)a2 + 12)) + 4);
    if ( result >= 0 )
    {
      v10 = 0;
      while ( 1 )
      {
        if ( *a3 <= 0x20u || (v11 = a3, *a3 == 127) )
          v11 = (const unsigned __int16 *)&v12;
        result = STRU::Append(a2, v11, 1u);
        if ( result < 0 )
          break;
        ++a3;
        if ( ++v10 >= a4 )
          goto LABEL_11;
      }
    }
  }
  else
  {
    result = STRU::Append(a2, L"-");
    if ( result >= 0 )
    {
LABEL_11:
      if ( a6 )
        return STRU::Append(a2, L" ");
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002d38  push    rbx
0x180002d3a  push    rbp
0x180002d3b  push    rsi
0x180002d3c  push    rdi
0x180002d3d  sub     rsp, 38h
0x180002d41  mov     eax, 2Bh ; '+'
0x180002d46  mov     ebp, r9d
0x180002d49  mov     [rsp+58h+var_38], ax
0x180002d4e  mov     rdi, r8
0x180002d51  mov     rbx, rdx
0x180002d54  mov     rcx, rdx
0x180002d57  test    r9d, r9d
0x180002d5a  jz      short loc_180002DA8
0x180002d5c  mov     edx, [rdx+30h]
0x180002d5f  add     edx, r9d
0x180002d62  lea     edx, ds:4[rdx*2]
0x180002d69  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180002d6f  test    eax, eax
0x180002d71  js      short loc_180002DD3
0x180002d73  xor     esi, esi
0x180002d75  cmp     word ptr [rdi], 20h ; ' '
0x180002d79  jbe     short loc_180002D84
0x180002d7b  cmp     word ptr [rdi], 7Fh
0x180002d7f  mov     rdx, rdi
0x180002d82  jnz     short loc_180002D89
0x180002d84  lea     rdx, [rsp+58h+var_38]
0x180002d89  mov     r8d, 1
0x180002d8f  mov     rcx, rbx
0x180002d92  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002d98  test    eax, eax
0x180002d9a  js      short loc_180002DD3
0x180002d9c  add     rdi, 2
0x180002da0  inc     esi
0x180002da2  cmp     esi, ebp
0x180002da4  jb      short loc_180002D75
0x180002da6  jmp     short loc_180002DB9
0x180002da8  lea     rdx, asc_18001208C; "-"
0x180002daf  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002db5  test    eax, eax
0x180002db7  js      short loc_180002DD3
0x180002db9  cmp     [rsp+58h+arg_28], 0
0x180002dc1  jz      short loc_180002DD3
0x180002dc3  lea     rdx, asc_180012138; " "
0x180002dca  mov     rcx, rbx
0x180002dcd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002dd3  add     rsp, 38h
0x180002dd7  pop     rdi
0x180002dd8  pop     rsi
0x180002dd9  pop     rbp
0x180002dda  pop     rbx
0x180002ddb  retn
```
