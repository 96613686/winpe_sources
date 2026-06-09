# UbpmUtilsSearchMultiString(ushort const *,ushort const *)

- ea: `0x180019220`
- end: `0x1800192ea`
- name: `?UbpmUtilsSearchMultiString@@YAEPEBG0@Z`
- size: `202`
- prototype: `unsigned __int8 __fastcall(PCNZWCH lpString2, PCNZWCH lpString1)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002610`
- `0x180008b30`
- `0x1800157b8`
- `0x180015e20`
- `0x18002ecf8`
- `0x18002f75c`

## callees

- `0x180019220`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019299`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800192d7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019299`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800192d7`

## pseudocode

```c
unsigned __int8 __fastcall UbpmUtilsSearchMultiString(PCNZWCH lpString2, PCNZWCH lpString1)
{
  const WCHAR *v2; // rdi
  __int64 cchCount2; // rsi
  __int64 v5; // rbx
  __int64 v6; // r9

  v2 = lpString1;
  if ( lpString1 && lpString2 )
  {
    cchCount2 = -1;
    do
      ++cchCount2;
    while ( lpString2[cchCount2] );
    while ( *v2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( v2[v5] );
      if ( (unsigned int)cchCount2 >= (unsigned int)v5 )
      {
        v6 = (unsigned int)(v5 - 1);
        if ( v2[v6] == 42 )
        {
          if ( CompareStringW(0x7Fu, 1u, v2, v6, lpString2, v5 - 1) == 2 )
            return 1;
        }
        else if ( (_DWORD)cchCount2 == (_DWORD)v5 && CompareStringW(0x7Fu, 1u, v2, v5, lpString2, cchCount2) == 2 )
        {
          return 1;
        }
      }
      v2 += (unsigned int)(v5 + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019220  push    rbx
0x180019222  push    rbp
0x180019223  push    rsi
0x180019224  push    rdi
0x180019225  sub     rsp, 38h
0x180019229  mov     rdi, rdx
0x18001922c  mov     rbp, rcx
0x18001922f  test    rdx, rdx
0x180019232  jz      loc_1800192B6
0x180019238  test    rcx, rcx
0x18001923b  jz      short loc_1800192B6
0x18001923d  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180019244  inc     rsi
0x180019247  cmp     word ptr [rcx+rsi*2], 0
0x18001924c  jnz     short loc_180019244
0x18001924e  xchg    ax, ax
0x180019250  cmp     word ptr [rdi], 0
0x180019254  jz      short loc_1800192B6
0x180019256  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001925d  nop     dword ptr [rax]
0x180019260  inc     rbx
0x180019263  cmp     word ptr [rdi+rbx*2], 0
0x180019268  jnz     short loc_180019260
0x18001926a  cmp     esi, ebx
0x18001926c  jnb     short loc_180019276
0x18001926e  inc     ebx
0x180019270  lea     rdi, [rdi+rbx*2]
0x180019274  jmp     short loc_180019250
0x180019276  lea     r9d, [rbx-1]; cchCount1
0x18001927a  cmp     word ptr [rdi+r9*2], 2Ah ; '*'
0x180019280  jnz     short loc_1800192BA
0x180019282  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x180019287  mov     r8, rdi; lpString1
0x18001928a  mov     edx, 1; dwCmpFlags
0x18001928f  mov     [rsp+58h+lpString2], rbp; lpString2
0x180019294  mov     ecx, 7Fh; Locale
0x180019299  call    cs:__imp_CompareStringW
0x1800192a0  nop     dword ptr [rax+rax+00h]
0x1800192a5  cmp     eax, 2
0x1800192a8  jnz     short loc_18001926E
0x1800192aa  mov     al, 1
0x1800192ac  add     rsp, 38h
0x1800192b0  pop     rdi
0x1800192b1  pop     rsi
0x1800192b2  pop     rbp
0x1800192b3  pop     rbx
0x1800192b4  retn
0x1800192b6  xor     al, al
0x1800192b8  jmp     short loc_1800192AC
0x1800192ba  cmp     esi, ebx
0x1800192bc  jnz     short loc_18001926E
0x1800192be  mov     [rsp+58h+cchCount2], esi; cchCount2
0x1800192c2  mov     r9d, ebx; cchCount1
0x1800192c5  mov     r8, rdi; lpString1
0x1800192c8  mov     [rsp+58h+lpString2], rbp; lpString2
0x1800192cd  mov     edx, 1; dwCmpFlags
0x1800192d2  mov     ecx, 7Fh; Locale
0x1800192d7  call    cs:__imp_CompareStringW
0x1800192de  nop     dword ptr [rax+rax+00h]
0x1800192e3  cmp     eax, 2
0x1800192e6  jnz     short loc_18001926E
0x1800192e8  jmp     short loc_1800192AA
```
