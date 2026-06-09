# TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)

- ea: `0x1800213d8`
- end: `0x180021446`
- name: `?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z`
- size: `110`
- prototype: `int(TOKEN_KEY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180019bc4`
- `0x180021fa4`

## callees

- `0x1800213d8`
- `0x180021720`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180021404`
- `msvcrt!_wcsupr` at `0x180021404`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800213f3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800213f3`

## pseudocode

```c
int __fastcall TOKEN_KEY::CreateCacheKey(wchar_t **this, const unsigned __int16 *a2, const BYTE *a3, int a4)
{
  const unsigned __int16 *v7; // rdi
  int result; // eax
  TOKEN_KEY *v9; // rcx
  int i; // ecx
  unsigned __int16 v11; // ax

  v7 = a2;
  result = STRU::Copy((STRU *)(this + 1), a2);
  if ( result >= 0 )
  {
    _wcsupr(this[5]);
    result = TOKEN_KEY::GeneratePasswordHash(v9, a3, (struct STRU *)(this + 8));
    if ( result >= 0 )
    {
      *((_DWORD *)this + 30) = a4;
      for ( i = 0; ; i = v11 + 101 * i )
      {
        v11 = *v7;
        if ( !*v7 )
          break;
        ++v7;
      }
      *((_DWORD *)this + 31) = i;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800213d8  push    rbx
0x1800213da  push    rbp
0x1800213db  push    rsi
0x1800213dc  push    rdi
0x1800213dd  push    r14
0x1800213df  sub     rsp, 20h
0x1800213e3  mov     rbx, rcx
0x1800213e6  mov     esi, r9d
0x1800213e9  add     rcx, 8
0x1800213ed  mov     rbp, r8
0x1800213f0  mov     rdi, rdx
0x1800213f3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800213f9  xor     r14d, r14d
0x1800213fc  test    eax, eax
0x1800213fe  js      short loc_18002143B
0x180021400  mov     rcx, [rbx+28h]; String
0x180021404  call    cs:__imp__wcsupr
0x18002140a  lea     r8, [rbx+40h]; struct STRU *
0x18002140e  mov     rdx, rbp; unsigned __int16 *
0x180021411  call    ?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z; TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)
0x180021416  test    eax, eax
0x180021418  js      short loc_18002143B
0x18002141a  mov     [rbx+78h], esi
0x18002141d  mov     ecx, r14d
0x180021420  jmp     short loc_18002142E
0x180021422  imul    ecx, 65h ; 'e'
0x180021425  lea     rdi, [rdi+2]
0x180021429  movzx   eax, ax
0x18002142c  add     ecx, eax
0x18002142e  movzx   eax, word ptr [rdi]
0x180021431  test    ax, ax
0x180021434  jnz     short loc_180021422
0x180021436  mov     [rbx+7Ch], ecx
0x180021439  xor     eax, eax
0x18002143b  add     rsp, 20h
0x18002143f  pop     r14
0x180021441  pop     rdi
0x180021442  pop     rsi
0x180021443  pop     rbp
0x180021444  pop     rbx
0x180021445  retn
```
