# CSsdpCacheEntry::ClearLocationCacheEntry(void)

- ea: `0x18001fabc`
- end: `0x18001fb74`
- name: `?ClearLocationCacheEntry@CSsdpCacheEntry@@AEAAXXZ`
- size: `184`
- prototype: `void __fastcall(CSsdpCacheEntry *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a60`
- `0x18001f6c4`
- `0x180026394`

## callees

- `0x18001fabc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fae8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb05`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb46`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fae8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb05`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001fb46`

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
0x18001fabc  push    rbx
0x18001fabe  push    rbp
0x18001fabf  push    rsi
0x18001fac0  push    rdi
0x18001fac1  push    r14
0x18001fac3  sub     rsp, 20h
0x18001fac7  xor     esi, esi
0x18001fac9  lea     rdi, [rcx+60h]
0x18001facd  mov     rbx, rcx
0x18001fad0  cmp     [rcx+68h], esi
0x18001fad3  jbe     short loc_18001FB3E
0x18001fad5  xor     r14d, r14d
0x18001fad8  mov     rax, [rdi]
0x18001fadb  lea     rcx, [r14+rsi*8]
0x18001fadf  mov     rcx, [rax+rcx*8]; Block
0x18001fae3  test    rcx, rcx
0x18001fae6  jz      short loc_18001FAF4
0x18001fae8  call    cs:__imp_free
0x18001faef  nop     dword ptr [rax+rax+00h]
0x18001faf4  mov     rax, [rdi]
0x18001faf7  lea     rcx, [r14+rsi*8]
0x18001fafb  mov     rcx, [rax+rcx*8+10h]; Block
0x18001fb00  test    rcx, rcx
0x18001fb03  jz      short loc_18001FB11
0x18001fb05  call    cs:__imp_free
0x18001fb0c  nop     dword ptr [rax+rax+00h]
0x18001fb11  mov     rax, [rdi]
0x18001fb14  lea     rcx, [r14+rsi*8]
0x18001fb18  mov     rcx, [rax+rcx*8+20h]; Block
0x18001fb1d  test    rcx, rcx
0x18001fb20  jz      short loc_18001FB2E
0x18001fb22  call    cs:__imp_free
0x18001fb29  nop     dword ptr [rax+rax+00h]
0x18001fb2e  inc     r14
0x18001fb31  cmp     r14, 2
0x18001fb35  jnz     short loc_18001FAD8
0x18001fb37  inc     esi
0x18001fb39  cmp     esi, [rbx+68h]
0x18001fb3c  jb      short loc_18001FAD5
0x18001fb3e  mov     rcx, [rdi]; Block
0x18001fb41  test    rcx, rcx
0x18001fb44  jz      short loc_18001FB60
0x18001fb46  call    cs:__imp_free
0x18001fb4d  nop     dword ptr [rax+rax+00h]
0x18001fb52  mov     qword ptr [rdi], 0
0x18001fb59  mov     dword ptr [rbx+68h], 0
0x18001fb60  mov     qword ptr [rbx+6Ch], 0
0x18001fb68  add     rsp, 20h
0x18001fb6c  pop     r14
0x18001fb6e  pop     rdi
0x18001fb6f  pop     rsi
0x18001fb70  pop     rbp
0x18001fb71  pop     rbx
0x18001fb72  retn
```
