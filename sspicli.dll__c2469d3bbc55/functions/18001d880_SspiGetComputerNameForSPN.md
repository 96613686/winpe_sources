# SspiGetComputerNameForSPN

- ea: `0x18001d880`
- end: `0x18001d9bd`
- name: `SspiGetComputerNameForSPN`
- size: `317`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180018600`
- `0x18001d784`
- `0x18001d880`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x18001d915`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x18001d92a`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x18001d915`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x18001d92a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d8df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d95a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d8df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d95a`

## pseudocode

```c
char __fastcall SspiGetComputerNameForSPN(wchar_t *Str, PVOID *a2)
{
  wchar_t *v3; // rbx
  wchar_t v4; // ax
  _OWORD *v5; // rax
  __int64 v6; // rdi
  unsigned __int64 v7; // rdi
  _WORD *v8; // rax
  __int64 v9; // rcx
  _WORD *v10; // rdx

  v3 = Str;
  if ( !Str )
    return 0;
  if ( !a2 )
    return 0;
  *a2 = 0;
  if ( !SspiReadRKHKey() )
    return 0;
  v4 = *v3;
  if ( *v3 == 92 )
  {
    if ( v3[1] != 92 )
      goto LABEL_11;
    v3 += 2;
    v4 = *v3;
  }
  if ( v4 == 46 && !v3[1] )
  {
    v5 = LocalAlloc(0x40u, 0x16u);
    *a2 = v5;
    if ( v5 )
    {
      *v5 = *(_OWORD *)L"localhost";
      *((_DWORD *)v5 + 4) = *(_DWORD *)L"t";
      return 1;
    }
    return 0;
  }
LABEL_11:
  if ( *v3 )
  {
    if ( !wcschr(v3, 0x5Cu) && !wcschr(v3, 0x2Fu) )
    {
      v6 = -1;
      do
        ++v6;
      while ( v3[v6] );
      v7 = v6 + 1;
      if ( v7 <= 0x7FFFFFFF )
      {
        v8 = LocalAlloc(0x40u, (unsigned int)(2 * v7) + 2LL);
        *a2 = v8;
        if ( v8 )
        {
          if ( v7 )
          {
            v9 = 2147483646;
            do
            {
              if ( !v9 )
                break;
              if ( !*v3 )
                break;
              *v8++ = *v3++;
              --v9;
              --v7;
            }
            while ( v7 );
            v10 = v8 - 1;
            if ( v7 )
              v10 = v8;
            *v10 = 0;
            if ( v7 )
              return 1;
          }
          SspiLocalFree(*a2);
          *a2 = 0;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001d880  push    rbx
0x18001d882  push    rbp
0x18001d883  push    rsi
0x18001d884  push    rdi
0x18001d885  sub     rsp, 28h
0x18001d889  xor     ebp, ebp
0x18001d88b  mov     rsi, rdx
0x18001d88e  mov     rbx, rcx
0x18001d891  test    rcx, rcx
0x18001d894  jz      loc_18001D9B2
0x18001d89a  test    rdx, rdx
0x18001d89d  jz      loc_18001D9B2
0x18001d8a3  mov     [rdx], rbp
0x18001d8a6  call    ?SspiReadRKHKey@@YAEXZ; SspiReadRKHKey(void)
0x18001d8ab  test    al, al
0x18001d8ad  jz      loc_18001D9B2
0x18001d8b3  movzx   eax, word ptr [rbx]
0x18001d8b6  lea     edx, [rbp+5Ch]; Ch
0x18001d8b9  cmp     ax, dx
0x18001d8bc  jnz     short loc_18001D8CB
0x18001d8be  cmp     [rbx+2], dx
0x18001d8c2  jnz     short loc_18001D909
0x18001d8c4  add     rbx, 4
0x18001d8c8  movzx   eax, word ptr [rbx]
0x18001d8cb  cmp     ax, 2Eh ; '.'
0x18001d8cf  jnz     short loc_18001D909
0x18001d8d1  cmp     [rbx+2], bp
0x18001d8d5  jnz     short loc_18001D909
0x18001d8d7  mov     edx, 16h; uBytes
0x18001d8dc  lea     ecx, [rdx+2Ah]; uFlags
0x18001d8df  call    cs:__imp_LocalAlloc
0x18001d8e5  mov     [rsi], rax
0x18001d8e8  test    rax, rax
0x18001d8eb  jz      loc_18001D9B2
0x18001d8f1  movups  xmm0, xmmword ptr cs:aLocalhost; "localhost"
0x18001d8f8  movups  xmmword ptr [rax], xmm0
0x18001d8fb  mov     ecx, dword ptr cs:aLocalhost+10h; "t"
0x18001d901  mov     [rax+10h], ecx
0x18001d904  jmp     loc_18001D9A3
0x18001d909  cmp     [rbx], bp
0x18001d90c  jz      loc_18001D9B2
0x18001d912  mov     rcx, rbx; Str
0x18001d915  call    cs:__imp_wcschr
0x18001d91b  test    rax, rax
0x18001d91e  jnz     loc_18001D9B2
0x18001d924  lea     edx, [rax+2Fh]; Ch
0x18001d927  mov     rcx, rbx; Str
0x18001d92a  call    cs:__imp_wcschr
0x18001d930  test    rax, rax
0x18001d933  jnz     short loc_18001D9B2
0x18001d935  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001d939  inc     rdi
0x18001d93c  cmp     [rbx+rdi*2], bp
0x18001d940  jnz     short loc_18001D939
0x18001d942  inc     rdi
0x18001d945  cmp     rdi, 7FFFFFFFh
0x18001d94c  ja      short loc_18001D9B2
0x18001d94e  lea     edx, [rdi+rdi]
0x18001d951  mov     ecx, 40h ; '@'; uFlags
0x18001d956  add     rdx, 2; uBytes
0x18001d95a  call    cs:__imp_LocalAlloc
0x18001d960  mov     [rsi], rax
0x18001d963  test    rax, rax
0x18001d966  jz      short loc_18001D9B2
0x18001d968  test    rdi, rdi
0x18001d96b  jz      short loc_18001D9A7
0x18001d96d  mov     ecx, 7FFFFFFEh
0x18001d972  test    rcx, rcx
0x18001d975  jz      short loc_18001D993
0x18001d977  movzx   edx, word ptr [rbx]
0x18001d97a  test    dx, dx
0x18001d97d  jz      short loc_18001D993
0x18001d97f  mov     [rax], dx
0x18001d982  add     rbx, 2
0x18001d986  add     rax, 2
0x18001d98a  dec     rcx
0x18001d98d  sub     rdi, 1
0x18001d991  jnz     short loc_18001D972
0x18001d993  test    rdi, rdi
0x18001d996  lea     rdx, [rax-2]
0x18001d99a  cmovnz  rdx, rax
0x18001d99e  mov     [rdx], bp
0x18001d9a1  jz      short loc_18001D9A7
0x18001d9a3  mov     al, 1
0x18001d9a5  jmp     short loc_18001D9B4
0x18001d9a7  mov     rcx, [rsi]; DataBuffer
0x18001d9aa  call    SspiLocalFree
0x18001d9af  mov     [rsi], rbp
0x18001d9b2  xor     al, al
0x18001d9b4  add     rsp, 28h
0x18001d9b8  pop     rdi
0x18001d9b9  pop     rsi
0x18001d9ba  pop     rbp
0x18001d9bb  pop     rbx
0x18001d9bc  retn
```
