# CDateTimeParser::IsValidAmPmString(ushort *,ushort const *,ushort * * const)

- ea: `0x180019b40`
- end: `0x180019c03`
- name: `?IsValidAmPmString@CDateTimeParser@@IEAAHPEAGPEBGQEAPEAG@Z`
- size: `195`
- prototype: `int(CDateTimeParser *__hidden this, unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **const)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018e50`
- `0x180019120`
- `0x180019270`
- `0x180019570`
- `0x180019710`

## callees

- `0x180019b40`
- `0x18002ea8c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019bad`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019bad`

## pseudocode

```c
__int64 __fastcall CDateTimeParser::IsValidAmPmString(
        CDateTimeParser *this,
        unsigned __int16 *a2,
        wchar_t *a3,
        unsigned __int16 **const a4)
{
  wchar_t *v6; // rax
  const WCHAR *lpString2; // rdi
  WCHAR i; // dx
  int j; // ebx
  unsigned __int8 v10; // cl

  v6 = wcstok_mvcrt_legacy_two_parameter_form(a2, a3, (wchar_t **)a3);
  lpString2 = v6;
  if ( !v6 )
    return 2;
  for ( i = *v6; i == 32; i = *lpString2 )
    ++lpString2;
  if ( !i )
    return 2;
  for ( j = 0; ; ++j )
  {
    if ( j >= 2 )
      return 1;
    if ( CompareStringW(0x7Fu, 1u, a4[j], -1, lpString2, -1) == 2 )
      break;
  }
  v10 = *((_BYTE *)this + 236);
  if ( j == 1 )
  {
    v10 += 12;
    *((_BYTE *)this + 236) = v10;
    return v10 > 0x17u;
  }
  if ( v10 != 12 )
    return v10 > 0x17u;
  *((_BYTE *)this + 236) = 0;
  return 0;
}

```

## disassembly

```asm
0x180019b40  push    rbx
0x180019b42  push    rsi
0x180019b43  push    rdi
0x180019b44  push    r14
0x180019b46  push    r15
0x180019b48  sub     rsp, 30h
0x180019b4c  mov     rax, rdx
0x180019b4f  mov     rsi, rcx
0x180019b52  mov     rcx, rax; String
0x180019b55  mov     rdx, r8; Delimiter
0x180019b58  mov     r14, r9
0x180019b5b  call    wcstok_mvcrt_legacy_two_parameter_form
0x180019b60  xor     r15d, r15d
0x180019b63  mov     rdi, rax
0x180019b66  test    rax, rax
0x180019b69  jz      loc_180019BF2
0x180019b6f  movzx   edx, word ptr [rax]
0x180019b72  jmp     short loc_180019B7B
0x180019b74  add     rdi, 2
0x180019b78  movzx   edx, word ptr [rdi]
0x180019b7b  cmp     dx, 20h ; ' '
0x180019b7f  jz      short loc_180019B74
0x180019b81  test    dx, dx
0x180019b84  jz      short loc_180019BF2
0x180019b86  mov     ebx, r15d
0x180019b89  cmp     ebx, 2
0x180019b8c  jge     short loc_180019BEB
0x180019b8e  or      r9d, 0FFFFFFFFh; cchCount1
0x180019b92  movsxd  r8, ebx
0x180019b95  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180019b9d  mov     [rsp+58h+lpString2], rdi; lpString2
0x180019ba2  mov     r8, [r14+r8*8]; lpString1
0x180019ba6  lea     edx, [r9+2]; dwCmpFlags
0x180019baa  lea     ecx, [rdx+7Eh]; Locale
0x180019bad  call    cs:__imp_CompareStringW
0x180019bb3  cmp     eax, 2
0x180019bb6  jz      short loc_180019BBC
0x180019bb8  inc     ebx
0x180019bba  jmp     short loc_180019B89
0x180019bbc  mov     cl, [rsi+0ECh]
0x180019bc2  cmp     ebx, 1
0x180019bc5  jnz     short loc_180019BDB
0x180019bc7  add     cl, 0Ch
0x180019bca  mov     [rsi+0ECh], cl
0x180019bd0  cmp     cl, 17h
0x180019bd3  mov     eax, r15d
0x180019bd6  setnbe  al
0x180019bd9  jmp     short loc_180019BF7
0x180019bdb  cmp     cl, 0Ch
0x180019bde  jnz     short loc_180019BD0
0x180019be0  mov     [rsi+0ECh], r15b
0x180019be7  xor     eax, eax
0x180019be9  jmp     short loc_180019BF7
0x180019beb  mov     eax, 1
0x180019bf0  jmp     short loc_180019BF7
0x180019bf2  mov     eax, 2
0x180019bf7  add     rsp, 30h
0x180019bfb  pop     r15
0x180019bfd  pop     r14
0x180019bff  pop     rdi
0x180019c00  pop     rsi
0x180019c01  pop     rbx
0x180019c02  retn
```
