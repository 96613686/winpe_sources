# ProcessStateInIP6Token(ushort const * &,ushort const *,_PARSE_PROXY_STRING_TOKEN_TYPE &,_PARSE_PROXY_STRING_STATE &,sockaddr_storage *,long *)

- ea: `0x18000f3e0`
- end: `0x18000f4bb`
- name: `?ProcessStateInIP6Token@@YAPEBGAEAPEBGPEBGAEAW4_PARSE_PROXY_STRING_TOKEN_TYPE@@AEAW4_PARSE_PROXY_STRING_STATE@@PEAUsockaddr_storage@@PEAJ@Z`
- size: `219`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 **, const unsigned __int16 *, enum _PARSE_PROXY_STRING_TOKEN_TYPE *, enum _PARSE_PROXY_STRING_STATE *, struct sockaddr_storage *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f0ec`

## callees

- `0x18000f3e0`
- `0x18000f5f8`

## import_xrefs

- `msvcrt!iswdigit` at `0x18000f3f9`
- `msvcrt!iswdigit` at `0x18000f3f9`

## pseudocode

```c
wint_t *__fastcall ProcessStateInIP6Token(
        const unsigned __int16 **a1,
        wint_t *a2,
        enum _PARSE_PROXY_STRING_TOKEN_TYPE *a3,
        enum _PARSE_PROXY_STRING_STATE *a4,
        struct sockaddr_storage *a5,
        int *a6)
{
  unsigned int v10; // r10d
  unsigned int v11; // r10d
  unsigned int v12; // r10d
  bool v13; // zf
  unsigned int v14; // r10d
  unsigned int v15; // r10d
  unsigned int v16; // r10d
  unsigned int v17; // r10d
  unsigned int v18; // r10d

  if ( iswdigit(*a2) )
    return a2 + 1;
  v10 = *a2;
  if ( v10 <= 0x46 )
  {
    if ( v10 != 70 )
    {
      v11 = v10 - 37;
      if ( v11 )
      {
        v12 = v11 - 21;
        if ( v12 )
        {
          v14 = v12 - 7;
          v13 = v14 == 0;
LABEL_10:
          if ( !v13 )
          {
            v17 = v14 - 1;
            if ( v17 )
            {
              v18 = v17 - 1;
              if ( v18 )
              {
                if ( v18 - 1 >= 2 )
                  goto LABEL_14;
              }
            }
          }
          return a2 + 1;
        }
      }
    }
    return a2 + 1;
  }
  v15 = v10 - 93;
  if ( v15 )
  {
    v16 = v15 - 4;
    if ( v16 )
    {
      v14 = v16 - 1;
      v13 = v14 == 0;
      goto LABEL_10;
    }
    return a2 + 1;
  }
  ProcessTokenIntoAddress(*a1, (__int64)a2, *(_DWORD *)a3, (__int64)a5, a6);
  if ( a2[1] == 58 )
  {
    *(_DWORD *)a4 = 3;
  }
  else
  {
    if ( a2[1] != 59 )
    {
LABEL_14:
      *(_DWORD *)a4 = 4;
      return 0;
    }
    *(_DWORD *)a4 = 0;
  }
  return a2 + 2;
}

```

## disassembly

```asm
0x18000f3e0  push    rbx
0x18000f3e2  push    rsi
0x18000f3e3  push    rdi
0x18000f3e4  push    r14
0x18000f3e6  sub     rsp, 38h
0x18000f3ea  mov     r14, rcx
0x18000f3ed  mov     rdi, r9
0x18000f3f0  movzx   ecx, word ptr [rdx]; C
0x18000f3f3  mov     rsi, r8
0x18000f3f6  mov     rbx, rdx
0x18000f3f9  call    cs:__imp_iswdigit
0x18000f400  nop     dword ptr [rax+rax+00h]
0x18000f405  test    eax, eax
0x18000f407  jnz     loc_18000F4AC
0x18000f40d  movzx   r10d, word ptr [rbx]
0x18000f411  cmp     r10d, 46h ; 'F'
0x18000f415  ja      short loc_18000F433
0x18000f417  jz      loc_18000F4AC
0x18000f41d  sub     r10d, 25h ; '%'
0x18000f421  jz      loc_18000F4AC
0x18000f427  sub     r10d, 15h
0x18000f42b  jz      short loc_18000F4AC
0x18000f42d  sub     r10d, 7
0x18000f431  jmp     short loc_18000F443
0x18000f433  sub     r10d, 5Dh ; ']'
0x18000f437  jz      short loc_18000F467
0x18000f439  sub     r10d, 4
0x18000f43d  jz      short loc_18000F4AC
0x18000f43f  sub     r10d, 1
0x18000f443  jz      short loc_18000F4AC
0x18000f445  sub     r10d, 1
0x18000f449  jz      short loc_18000F4AC
0x18000f44b  sub     r10d, 1
0x18000f44f  jz      short loc_18000F4AC
0x18000f451  sub     r10d, 1
0x18000f455  jz      short loc_18000F4AC
0x18000f457  cmp     r10d, 1
0x18000f45b  jz      short loc_18000F4AC
0x18000f45d  mov     dword ptr [rdi], 4
0x18000f463  xor     eax, eax
0x18000f465  jmp     short loc_18000F4B0
0x18000f467  mov     rax, [rsp+58h+arg_28]
0x18000f46f  mov     rdx, rbx
0x18000f472  mov     r9, [rsp+58h+arg_20]
0x18000f47a  mov     r8d, [rsi]
0x18000f47d  mov     rcx, [r14]
0x18000f480  mov     [rsp+58h+var_38], rax
0x18000f485  call    ?ProcessTokenIntoAddress@@YAXPEBG0W4_PARSE_PROXY_STRING_TOKEN_TYPE@@PEAUsockaddr_storage@@PEAJ@Z; ProcessTokenIntoAddress(ushort const *,ushort const *,_PARSE_PROXY_STRING_TOKEN_TYPE,sockaddr_storage *,long *)
0x18000f48a  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18000f48f  jnz     short loc_18000F49D
0x18000f491  mov     dword ptr [rdi], 3
0x18000f497  lea     rax, [rbx+4]
0x18000f49b  jmp     short loc_18000F4B0
0x18000f49d  cmp     word ptr [rbx+2], 3Bh ; ';'
0x18000f4a2  jnz     short loc_18000F45D
0x18000f4a4  mov     dword ptr [rdi], 0
0x18000f4aa  jmp     short loc_18000F497
0x18000f4ac  lea     rax, [rbx+2]
0x18000f4b0  add     rsp, 38h
0x18000f4b4  pop     r14
0x18000f4b6  pop     rdi
0x18000f4b7  pop     rsi
0x18000f4b8  pop     rbx
0x18000f4b9  retn
```
