# fp_format_f_internal

- ea: `0x1004321ac`
- end: `0x100432302`
- name: `fp_format_f_internal`
- size: `342`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, char, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1004320d0`
- `0x100432308`

## callees

- `0x100425d50`
- `0x1004277a0`
- `0x10042d4f0`
- `0x1004321ac`

## pseudocode

```c
__int64 __fastcall fp_format_f_internal(char *Src, __int64 a2, int a3, __int64 a4, char a5, __crt_cached_ptd_host *a6)
{
  __int64 v7; // rcx
  int v9; // ebp
  __int64 v10; // rax
  __int64 v11; // rdi
  bool v12; // al
  char *v13; // rsi
  __int64 v14; // r8
  char *v15; // rbx
  _BYTE *v16; // rsi
  __int64 v17; // r8
  int v18; // eax
  int v19; // eax

  v7 = *(int *)(a4 + 4);
  v9 = a3;
  if ( a5 && (_DWORD)v7 - 1 == a3 )
    *(_WORD *)&Src[(*(_DWORD *)a4 == 45) - 1 + v7] = 48;
  if ( *(_DWORD *)a4 == 45 )
    *Src++ = 45;
  v10 = *(int *)(a4 + 4);
  v11 = -1;
  if ( (int)v10 > 0 )
  {
    v15 = &Src[v10];
  }
  else
  {
    v12 = !(_DWORD)v10 && **(_BYTE **)(a4 + 8) == 48;
    if ( a5 && v12 )
    {
      v13 = Src + 1;
    }
    else
    {
      v13 = Src + 1;
      v14 = -1;
      do
        ++v14;
      while ( Src[v14] );
      memmove(Src + 1, Src, v14 + 1);
    }
    *Src = 48;
    v15 = v13;
  }
  if ( v9 > 0 )
  {
    v16 = v15 + 1;
    v17 = -1;
    do
      ++v17;
    while ( v15[v17] );
    memmove(v15 + 1, v15, v17 + 1);
    if ( !*((_BYTE *)a6 + 40) )
      __crt_cached_ptd_host::update_locale_slow(a6);
    *v15 = ***(_BYTE ***)(*((_QWORD *)a6 + 3) + 248LL);
    v18 = *(_DWORD *)(a4 + 4);
    if ( v18 < 0 )
    {
      v19 = -v18;
      if ( a5 || v19 < v9 )
        v9 = v19;
      do
        ++v11;
      while ( v16[v11] );
      memmove(&v16[v9], v16, v11 + 1);
      memset(v16, 48, v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1004321ac  mov     [rsp+arg_0], rbx
0x1004321b1  mov     [rsp+arg_8], rbp
0x1004321b6  mov     [rsp+arg_10], rsi
0x1004321bb  push    rdi
0x1004321bc  push    r14
0x1004321be  push    r15
0x1004321c0  sub     rsp, 20h
0x1004321c4  cmp     [rsp+38h+arg_20], 0
0x1004321c9  mov     rbx, rcx
0x1004321cc  movsxd  rcx, dword ptr [r9+4]
0x1004321d0  mov     r14, r9
0x1004321d3  mov     ebp, r8d
0x1004321d6  jz      short loc_1004321F3
0x1004321d8  lea     eax, [rcx-1]
0x1004321db  cmp     eax, r8d
0x1004321de  jnz     short loc_1004321F3
0x1004321e0  xor     eax, eax
0x1004321e2  cmp     dword ptr [r9], 2Dh ; '-'
0x1004321e6  setz    al
0x1004321e9  add     rax, rbx
0x1004321ec  mov     word ptr [rcx+rax-1], 30h ; '0'
0x1004321f3  cmp     dword ptr [r9], 2Dh ; '-'
0x1004321f7  jnz     short loc_1004321FF
0x1004321f9  mov     byte ptr [rbx], 2Dh ; '-'
0x1004321fc  inc     rbx
0x1004321ff  movsxd  rax, dword ptr [r9+4]
0x100432203  or      rdi, 0FFFFFFFFFFFFFFFFh
0x100432207  test    eax, eax
0x100432209  jg      short loc_100432254
0x10043220b  jnz     short loc_10043221A
0x10043220d  mov     rax, [r9+8]
0x100432211  cmp     byte ptr [rax], 30h ; '0'
0x100432214  jnz     short loc_10043221A
0x100432216  mov     al, 1
0x100432218  jmp     short loc_10043221C
0x10043221a  xor     al, al
0x10043221c  cmp     [rsp+38h+arg_20], 0
0x100432221  jz      short loc_10043222D
0x100432223  test    al, al
0x100432225  jz      short loc_10043222D
0x100432227  lea     rsi, [rbx+1]
0x10043222b  jmp     short loc_10043224C
0x10043222d  lea     rsi, [rbx+1]
0x100432231  mov     r8, rdi
0x100432234  inc     r8
0x100432237  cmp     byte ptr [rbx+r8], 0
0x10043223c  jnz     short loc_100432234
0x10043223e  inc     r8; Size
0x100432241  mov     rdx, rbx; Src
0x100432244  mov     rcx, rsi; void *
0x100432247  call    memmove
0x10043224c  mov     byte ptr [rbx], 30h ; '0'
0x10043224f  mov     rbx, rsi
0x100432252  jmp     short loc_100432257
0x100432254  add     rbx, rax
0x100432257  test    ebp, ebp
0x100432259  jle     loc_1004322E7
0x10043225f  lea     rsi, [rbx+1]
0x100432263  mov     r8, rdi
0x100432266  inc     r8
0x100432269  cmp     byte ptr [rbx+r8], 0
0x10043226e  jnz     short loc_100432266
0x100432270  inc     r8; Size
0x100432273  mov     rdx, rbx; Src
0x100432276  mov     rcx, rsi; void *
0x100432279  call    memmove
0x10043227e  mov     r15, [rsp+38h+arg_28]
0x100432283  cmp     byte ptr [r15+28h], 0
0x100432288  jnz     short loc_100432292
0x10043228a  mov     rcx, r15; this
0x10043228d  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x100432292  mov     rax, [r15+18h]
0x100432296  mov     rcx, [rax+0F8h]
0x10043229d  mov     rax, [rcx]
0x1004322a0  mov     cl, [rax]
0x1004322a2  mov     [rbx], cl
0x1004322a4  mov     eax, [r14+4]
0x1004322a8  test    eax, eax
0x1004322aa  jns     short loc_1004322E7
0x1004322ac  neg     eax
0x1004322ae  cmp     [rsp+38h+arg_20], 0
0x1004322b3  jnz     short loc_1004322B9
0x1004322b5  cmp     eax, ebp
0x1004322b7  jge     short loc_1004322BB
0x1004322b9  mov     ebp, eax
0x1004322bb  movsxd  rbx, ebp
0x1004322be  inc     rdi
0x1004322c1  cmp     byte ptr [rsi+rdi], 0
0x1004322c5  jnz     short loc_1004322BE
0x1004322c7  lea     r8, [rdi+1]; Size
0x1004322cb  mov     rdx, rsi; Src
0x1004322ce  lea     rcx, [rbx+rsi]; void *
0x1004322d2  call    memmove
0x1004322d7  mov     r8, rbx; Size
0x1004322da  mov     edx, 30h ; '0'; Val
0x1004322df  mov     rcx, rsi; void *
0x1004322e2  call    memset
0x1004322e7  mov     rbx, [rsp+38h+arg_0]
0x1004322ec  xor     eax, eax
0x1004322ee  mov     rbp, [rsp+38h+arg_8]
0x1004322f3  mov     rsi, [rsp+38h+arg_10]
0x1004322f8  add     rsp, 20h
0x1004322fc  pop     r15
0x1004322fe  pop     r14
0x100432300  pop     rdi
0x100432301  retn
```
