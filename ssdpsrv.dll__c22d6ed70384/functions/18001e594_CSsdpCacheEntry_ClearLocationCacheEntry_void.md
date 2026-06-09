# CSsdpCacheEntry::ClearLocationCacheEntry(void)

- ea: `0x18001e594`
- end: `0x18001e633`
- name: `?ClearLocationCacheEntry@CSsdpCacheEntry@@AEAAXXZ`
- size: `159`
- prototype: `void __fastcall(CSsdpCacheEntry *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005740`
- `0x18001e1d4`
- `0x18002487c`

## callees

- `0x18001e594`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e5c0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e5d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e5ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e60c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e5c0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e5d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e5ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e60c`

## pseudocode

```c
void __fastcall CSsdpCacheEntry::ClearLocationCacheEntry(CSsdpCacheEntry *this)
{
  __int64 v1; // rsi
  void **i; // rdi
  __int64 j; // r14
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v1 = 0;
  for ( i = (void **)((char *)this + 96); (unsigned int)v1 < *((_DWORD *)this + 26); v1 = (unsigned int)(v1 + 1) )
  {
    for ( j = 0; j != 2; ++j )
    {
      v5 = (void *)*((_QWORD *)*i + 8 * v1 + j);
      if ( v5 )
        free(v5);
      v6 = (void *)*((_QWORD *)*i + 8 * v1 + j + 2);
      if ( v6 )
        free(v6);
      v7 = (void *)*((_QWORD *)*i + 8 * v1 + j + 4);
      if ( v7 )
        free(v7);
    }
  }
  if ( *i )
  {
    free(*i);
    *i = 0;
    *((_DWORD *)this + 26) = 0;
  }
  *(_QWORD *)((char *)this + 108) = 0;
}

```

## disassembly

```asm
0x18001e594  push    rbx
0x18001e596  push    rbp
0x18001e597  push    rsi
0x18001e598  push    rdi
0x18001e599  push    r14
0x18001e59b  sub     rsp, 20h
0x18001e59f  xor     esi, esi
0x18001e5a1  lea     rdi, [rcx+60h]
0x18001e5a5  mov     rbx, rcx
0x18001e5a8  cmp     [rcx+68h], esi
0x18001e5ab  jbe     short loc_18001E604
0x18001e5ad  xor     r14d, r14d
0x18001e5b0  mov     rax, [rdi]
0x18001e5b3  lea     rcx, [r14+rsi*8]
0x18001e5b7  mov     rcx, [rax+rcx*8]; Block
0x18001e5bb  test    rcx, rcx
0x18001e5be  jz      short loc_18001E5C6
0x18001e5c0  call    cs:__imp_free
0x18001e5c6  mov     rax, [rdi]
0x18001e5c9  lea     rcx, [r14+rsi*8]
0x18001e5cd  mov     rcx, [rax+rcx*8+10h]; Block
0x18001e5d2  test    rcx, rcx
0x18001e5d5  jz      short loc_18001E5DD
0x18001e5d7  call    cs:__imp_free
0x18001e5dd  mov     rax, [rdi]
0x18001e5e0  lea     rcx, [r14+rsi*8]
0x18001e5e4  mov     rcx, [rax+rcx*8+20h]; Block
0x18001e5e9  test    rcx, rcx
0x18001e5ec  jz      short loc_18001E5F4
0x18001e5ee  call    cs:__imp_free
0x18001e5f4  inc     r14
0x18001e5f7  cmp     r14, 2
0x18001e5fb  jnz     short loc_18001E5B0
0x18001e5fd  inc     esi
0x18001e5ff  cmp     esi, [rbx+68h]
0x18001e602  jb      short loc_18001E5AD
0x18001e604  mov     rcx, [rdi]; Block
0x18001e607  test    rcx, rcx
0x18001e60a  jz      short loc_18001E620
0x18001e60c  call    cs:__imp_free
0x18001e612  mov     qword ptr [rdi], 0
0x18001e619  mov     dword ptr [rbx+68h], 0
0x18001e620  mov     qword ptr [rbx+6Ch], 0
0x18001e628  add     rsp, 20h
0x18001e62c  pop     r14
0x18001e62e  pop     rdi
0x18001e62f  pop     rsi
0x18001e630  pop     rbp
0x18001e631  pop     rbx
0x18001e632  retn
```
