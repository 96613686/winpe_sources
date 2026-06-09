# ProcessStateInToken(ushort const * &,ushort const *,_PARSE_PROXY_STRING_TOKEN_TYPE &,_PARSE_PROXY_STRING_STATE &,sockaddr_storage *,long *)

- ea: `0x18000f4c4`
- end: `0x18000f5f1`
- name: `?ProcessStateInToken@@YAPEBGAEAPEBGPEBGAEAW4_PARSE_PROXY_STRING_TOKEN_TYPE@@AEAW4_PARSE_PROXY_STRING_STATE@@PEAUsockaddr_storage@@PEAJ@Z`
- size: `301`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 **, const unsigned __int16 *, enum _PARSE_PROXY_STRING_TOKEN_TYPE *, enum _PARSE_PROXY_STRING_STATE *, struct sockaddr_storage *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f0ec`

## callees

- `0x18000f4c4`
- `0x18000f5f8`

## import_xrefs

- `msvcrt!iswdigit` at `0x18000f4df`
- `msvcrt!iswdigit` at `0x18000f580`
- `msvcrt!iswdigit` at `0x18000f4df`
- `msvcrt!iswdigit` at `0x18000f580`

## pseudocode

```c
const unsigned __int16 *__fastcall ProcessStateInToken(
        const unsigned __int16 **a1,
        const unsigned __int16 *a2,
        enum _PARSE_PROXY_STRING_TOKEN_TYPE *a3,
        enum _PARSE_PROXY_STRING_STATE *a4,
        struct sockaddr_storage *a5,
        int *a6)
{
  const unsigned __int16 *result; // rax

  if ( iswdigit(*a2) )
    return a2 + 1;
  if ( *a2 )
  {
    if ( *a2 == 46 )
      return a2 + 1;
    if ( *a2 != 58 )
    {
      if ( *a2 == 59 )
      {
        ProcessTokenIntoAddress(*a1, (__int64)a2, *(_DWORD *)a3, (__int64)a5, a6);
      }
      else if ( *a2 != 61 )
      {
        if ( *(_DWORD *)a3 != 1 )
          return a2 + 1;
        goto LABEL_17;
      }
      *(_DWORD *)a4 = 0;
      return a2 + 1;
    }
    if ( a2[1] == 47 && a2[2] == 47 )
    {
      *(_DWORD *)a4 = 0;
      return a2 + 3;
    }
    if ( iswdigit(a2[1]) )
    {
      ProcessTokenIntoAddress(*a1, (__int64)a2, *(_DWORD *)a3, (__int64)a5, a6);
      result = a2 + 1;
      *(_DWORD *)a4 = 3;
      return result;
    }
  }
  else
  {
    ProcessTokenIntoAddress(*a1, (__int64)a2, *(_DWORD *)a3, (__int64)a5, a6);
  }
LABEL_17:
  *(_DWORD *)a4 = 4;
  return 0;
}

```

## disassembly

```asm
0x18000f4c4  push    rbx
0x18000f4c6  push    rsi
0x18000f4c7  push    rdi
0x18000f4c8  push    r14
0x18000f4ca  push    r15
0x18000f4cc  sub     rsp, 30h
0x18000f4d0  mov     r15, rcx
0x18000f4d3  mov     rdi, r9
0x18000f4d6  movzx   ecx, word ptr [rdx]; C
0x18000f4d9  mov     rsi, r8
0x18000f4dc  mov     rbx, rdx
0x18000f4df  call    cs:__imp_iswdigit
0x18000f4e6  nop     dword ptr [rax+rax+00h]
0x18000f4eb  test    eax, eax
0x18000f4ed  jnz     short loc_18000F51D
0x18000f4ef  movzx   r10d, word ptr [rbx]
0x18000f4f3  test    r10d, r10d
0x18000f4f6  jz      loc_18000F5C1
0x18000f4fc  sub     r10d, 2Eh ; '.'
0x18000f500  jz      short loc_18000F51D
0x18000f502  sub     r10d, 0Ch
0x18000f506  jz      short loc_18000F55B
0x18000f508  sub     r10d, 1
0x18000f50c  jz      short loc_18000F536
0x18000f50e  cmp     r10d, 2
0x18000f512  jz      short loc_18000F52E
0x18000f514  cmp     dword ptr [rsi], 1
0x18000f517  jz      loc_18000F5E4
0x18000f51d  lea     rax, [rbx+2]
0x18000f521  add     rsp, 30h
0x18000f525  pop     r15
0x18000f527  pop     r14
0x18000f529  pop     rdi
0x18000f52a  pop     rsi
0x18000f52b  pop     rbx
0x18000f52c  retn
0x18000f52e  mov     dword ptr [rdi], 0
0x18000f534  jmp     short loc_18000F51D
0x18000f536  mov     rax, [rsp+58h+arg_28]
0x18000f53e  mov     rdx, rbx
0x18000f541  mov     r9, [rsp+58h+arg_20]
0x18000f549  mov     r8d, [rsi]
0x18000f54c  mov     rcx, [r15]
0x18000f54f  mov     [rsp+58h+var_38], rax
0x18000f554  call    ?ProcessTokenIntoAddress@@YAXPEBG0W4_PARSE_PROXY_STRING_TOKEN_TYPE@@PEAUsockaddr_storage@@PEAJ@Z; ProcessTokenIntoAddress(ushort const *,ushort const *,_PARSE_PROXY_STRING_TOKEN_TYPE,sockaddr_storage *,long *)
0x18000f559  jmp     short loc_18000F52E
0x18000f55b  lea     r14, [rbx+2]
0x18000f55f  mov     eax, 2Fh ; '/'
0x18000f564  cmp     ax, [r14]
0x18000f568  jnz     short loc_18000F57C
0x18000f56a  cmp     ax, [rbx+4]
0x18000f56e  jnz     short loc_18000F57C
0x18000f570  mov     dword ptr [rdi], 0
0x18000f576  lea     rax, [rbx+6]
0x18000f57a  jmp     short loc_18000F521
0x18000f57c  movzx   ecx, word ptr [r14]; C
0x18000f580  call    cs:__imp_iswdigit
0x18000f587  nop     dword ptr [rax+rax+00h]
0x18000f58c  test    eax, eax
0x18000f58e  jz      short loc_18000F5E4
0x18000f590  mov     rcx, [rsp+58h+arg_28]
0x18000f598  mov     rdx, rbx
0x18000f59b  mov     r9, [rsp+58h+arg_20]
0x18000f5a3  mov     r8d, [rsi]
0x18000f5a6  mov     [rsp+58h+var_38], rcx
0x18000f5ab  mov     rcx, [r15]
0x18000f5ae  call    ?ProcessTokenIntoAddress@@YAXPEBG0W4_PARSE_PROXY_STRING_TOKEN_TYPE@@PEAUsockaddr_storage@@PEAJ@Z; ProcessTokenIntoAddress(ushort const *,ushort const *,_PARSE_PROXY_STRING_TOKEN_TYPE,sockaddr_storage *,long *)
0x18000f5b3  mov     rax, r14
0x18000f5b6  mov     dword ptr [rdi], 3
0x18000f5bc  jmp     loc_18000F521
0x18000f5c1  mov     rax, [rsp+58h+arg_28]
0x18000f5c9  mov     rdx, rbx
0x18000f5cc  mov     r9, [rsp+58h+arg_20]
0x18000f5d4  mov     r8d, [rsi]
0x18000f5d7  mov     rcx, [r15]
0x18000f5da  mov     [rsp+58h+var_38], rax
0x18000f5df  call    ?ProcessTokenIntoAddress@@YAXPEBG0W4_PARSE_PROXY_STRING_TOKEN_TYPE@@PEAUsockaddr_storage@@PEAJ@Z; ProcessTokenIntoAddress(ushort const *,ushort const *,_PARSE_PROXY_STRING_TOKEN_TYPE,sockaddr_storage *,long *)
0x18000f5e4  mov     dword ptr [rdi], 4
0x18000f5ea  xor     eax, eax
0x18000f5ec  jmp     loc_18000F521
```
