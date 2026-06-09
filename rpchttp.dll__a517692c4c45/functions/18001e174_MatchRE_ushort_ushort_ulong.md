# MatchRE(ushort *,ushort *,ulong)

- ea: `0x18001e174`
- end: `0x18001e2c3`
- name: `?MatchRE@@YAHPEAG0K@Z`
- size: `335`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e174`
- `0x18001e2cc`

## callees

- `0x18001e174`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18001e1f1`
- `KERNEL32!CompareStringW` at `0x18001e1f1`

## pseudocode

```c
__int64 __fastcall MatchRE(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int16 v6; // ax
  unsigned __int16 v7; // dx
  unsigned __int16 v9; // r8
  unsigned __int16 v10; // cx
  unsigned int v11; // r8d
  unsigned __int16 *v12; // rdx
  int String1; // [rsp+60h] [rbp+18h] BYREF
  int String2; // [rsp+68h] [rbp+20h] BYREF

  String1 = 0;
  String2 = 0;
  if ( a3 > 0x3E8 )
    return 0;
  while ( 1 )
  {
    v6 = *a2;
    LOWORD(String2) = v6;
    if ( !v6 )
      return *a1 == 0;
    if ( v6 == 42 )
      break;
    v7 = *a1;
    if ( v6 == 63 )
    {
      if ( !v7 )
        return 0;
      goto LABEL_25;
    }
    LOWORD(String1) = *a1;
    if ( v6 != 91 )
    {
      if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)&String1, -1, (PCNZWCH)&String2, -1) != 2 )
        return 0;
LABEL_25:
      ++a2;
      goto LABEL_26;
    }
    if ( !v7 )
      return 0;
    ++a2;
    v9 = 0;
    do
    {
      v10 = *a2;
      if ( !*a2 )
        break;
      v6 = *a2;
      if ( v10 == 93 )
        return 0;
      ++a2;
      if ( v10 == 45 )
      {
        v6 = *a2;
        if ( !*a2 || v6 == 93 )
          return 0;
        if ( v7 >= v9 && v7 <= v6 )
          break;
        ++a2;
        v10 = v6;
      }
      v9 = v10;
    }
    while ( v7 != v10 );
    while ( v6 && v6 != 93 )
      v6 = *a2++;
LABEL_26:
    ++a1;
  }
  while ( 1 )
  {
    v11 = a3 + 1;
    v12 = a2 + 1;
    if ( !*a1 )
      break;
    if ( (unsigned int)MatchRE(a1, v12, v11) )
      return 1;
    ++a1;
  }
  return MatchRE(a1, v12, v11);
}

```

## disassembly

```asm
0x18001e174  mov     [rsp+arg_0], rbx
0x18001e179  push    rbp
0x18001e17a  push    rsi
0x18001e17b  push    rdi
0x18001e17c  sub     rsp, 30h
0x18001e180  xor     ebp, ebp
0x18001e182  mov     esi, r8d
0x18001e185  mov     [rsp+48h+String1], ebp
0x18001e189  mov     rbx, rdx
0x18001e18c  mov     [rsp+48h+String2], ebp
0x18001e190  mov     rdi, rcx
0x18001e193  cmp     r8d, 3E8h
0x18001e19a  ja      short loc_18001E1FC
0x18001e19c  movzx   eax, word ptr [rbx]
0x18001e19f  mov     word ptr [rsp+48h+String2], ax
0x18001e1a4  test    ax, ax
0x18001e1a7  jz      loc_18001E2B6
0x18001e1ad  cmp     ax, 2Ah ; '*'
0x18001e1b1  jz      loc_18001E283
0x18001e1b7  movzx   edx, word ptr [rdi]
0x18001e1ba  cmp     ax, 3Fh ; '?'
0x18001e1be  jz      loc_18001E271
0x18001e1c4  mov     word ptr [rsp+48h+String1], dx
0x18001e1c9  cmp     ax, 5Bh ; '['
0x18001e1cd  jz      short loc_18001E20B
0x18001e1cf  or      r9d, 0FFFFFFFFh; cchCount1
0x18001e1d3  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001e1db  lea     rax, [rsp+48h+String2]
0x18001e1e0  lea     r8, [rsp+48h+String1]; lpString1
0x18001e1e5  mov     [rsp+48h+lpString2], rax; lpString2
0x18001e1ea  lea     edx, [r9+2]; dwCmpFlags
0x18001e1ee  lea     ecx, [rdx+7Eh]; Locale
0x18001e1f1  call    cs:__imp_CompareStringW
0x18001e1f7  cmp     eax, 2
0x18001e1fa  jz      short loc_18001E276
0x18001e1fc  xor     eax, eax
0x18001e1fe  mov     rbx, [rsp+48h+arg_0]
0x18001e203  add     rsp, 30h
0x18001e207  pop     rdi
0x18001e208  pop     rsi
0x18001e209  pop     rbp
0x18001e20a  retn
0x18001e20b  test    dx, dx
0x18001e20e  jz      short loc_18001E1FC
0x18001e210  add     rbx, 2
0x18001e214  mov     r8d, ebp
0x18001e217  movzx   ecx, word ptr [rbx]
0x18001e21a  test    cx, cx
0x18001e21d  jz      short loc_18001E26A
0x18001e21f  movzx   eax, cx
0x18001e222  cmp     cx, 5Dh ; ']'
0x18001e226  jz      short loc_18001E1FC
0x18001e228  add     rbx, 2
0x18001e22c  cmp     cx, 2Dh ; '-'
0x18001e230  jnz     short loc_18001E252
0x18001e232  movzx   eax, word ptr [rbx]
0x18001e235  test    ax, ax
0x18001e238  jz      short loc_18001E1FC
0x18001e23a  cmp     ax, 5Dh ; ']'
0x18001e23e  jz      short loc_18001E1FC
0x18001e240  cmp     dx, r8w
0x18001e244  jb      short loc_18001E24B
0x18001e246  cmp     dx, ax
0x18001e249  jbe     short loc_18001E26A
0x18001e24b  add     rbx, 2
0x18001e24f  movzx   ecx, ax
0x18001e252  movzx   r8d, cx
0x18001e256  cmp     dx, cx
0x18001e259  jnz     short loc_18001E217
0x18001e25b  jmp     short loc_18001E26A
0x18001e25d  cmp     ax, 5Dh ; ']'
0x18001e261  jz      short loc_18001E27A
0x18001e263  movzx   eax, word ptr [rbx]
0x18001e266  add     rbx, 2
0x18001e26a  test    ax, ax
0x18001e26d  jnz     short loc_18001E25D
0x18001e26f  jmp     short loc_18001E27A
0x18001e271  test    dx, dx
0x18001e274  jz      short loc_18001E1FC
0x18001e276  add     rbx, 2
0x18001e27a  add     rdi, 2
0x18001e27e  jmp     loc_18001E19C
0x18001e283  lea     r8d, [rsi+1]; unsigned int
0x18001e287  mov     rcx, rdi; unsigned __int16 *
0x18001e28a  lea     rdx, [rbx+2]; unsigned __int16 *
0x18001e28e  cmp     [rdi], bp
0x18001e291  jz      short loc_18001E2AC
0x18001e293  call    ?MatchRE@@YAHPEAG0K@Z; MatchRE(ushort *,ushort *,ulong)
0x18001e298  test    eax, eax
0x18001e29a  jnz     short loc_18001E2A2
0x18001e29c  add     rdi, 2
0x18001e2a0  jmp     short loc_18001E283
0x18001e2a2  mov     eax, 1
0x18001e2a7  jmp     loc_18001E1FE
0x18001e2ac  call    ?MatchRE@@YAHPEAG0K@Z; MatchRE(ushort *,ushort *,ulong)
0x18001e2b1  jmp     loc_18001E1FE
0x18001e2b6  cmp     [rdi], bp
0x18001e2b9  mov     eax, ebp
0x18001e2bb  setz    al
0x18001e2be  jmp     loc_18001E1FE
```
