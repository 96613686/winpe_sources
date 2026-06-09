# CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)

- ea: `0x180020258`
- end: `0x180020348`
- name: `?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z`
- size: `240`
- prototype: `unsigned int __fastcall(unsigned int, char *, struct _WDSMCTP_OPTIONS *, unsigned int)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d560`
- `0x18001d730`
- `0x18001d8a8`
- `0x18001dab0`
- `0x18001dd2c`
- `0x18001df44`
- `0x18001e16c`
- `0x18001e398`
- `0x180020350`

## callees

- `0x180020258`
- `0x180026d3a`

## import_xrefs

- `WS2_32!__imp_htons` at `0x18002029e`
- `WS2_32!__imp_htons` at `0x1800202e3`
- `WS2_32!__imp_htons` at `0x1800202f1`
- `WS2_32!__imp_htons` at `0x18002029e`
- `WS2_32!__imp_htons` at `0x1800202e3`
- `WS2_32!__imp_htons` at `0x1800202f1`

## pseudocode

```c
__int64 __fastcall CMcTpOptions::CreateOptions(
        unsigned int a1,
        u_short *a2,
        struct _WDSMCTP_OPTIONS *a3,
        unsigned int a4)
{
  unsigned int v4; // ebx
  unsigned __int64 v5; // r14
  u_short *v9; // r15
  __int64 v10; // r12
  u_short *v11; // rcx
  void *v12; // rax
  void *Src; // [rsp+20h] [rbp-38h]
  int v15; // [rsp+78h] [rbp+20h]

  v4 = 0;
  v5 = a4;
  if ( a4 >= 2 )
  {
    if ( a1 )
    {
      v15 = 0;
      v9 = (u_short *)((char *)a3 + 2);
      *(_WORD *)a3 = htons(a1);
      while ( 1 )
      {
        v10 = a2[4];
        v11 = a2;
        v12 = (void *)*((_QWORD *)a2 + 2);
        a2 += 12;
        Src = v12;
        if ( (unsigned __int64)v9 + (unsigned int)v10 - (_QWORD)a3 + 4 > v5 )
          break;
        *v9 = htons(*v11);
        v9[1] = htons(v10);
        memmove_0(v9 + 2, Src, (unsigned int)v10);
        v9 = (u_short *)((char *)v9 + v10 + 4);
        if ( ++v15 >= a1 )
          return v4;
      }
      return 111;
    }
    else
    {
      *(_WORD *)a3 = 0;
    }
  }
  else
  {
    return 122;
  }
  return v4;
}

```

## disassembly

```asm
0x180020258  mov     [rsp+arg_0], rbx
0x18002025d  mov     [rsp+arg_8], rbp
0x180020262  mov     [rsp+arg_10], rsi
0x180020267  push    rdi
0x180020268  push    r12
0x18002026a  push    r13
0x18002026c  push    r14
0x18002026e  push    r15
0x180020270  sub     rsp, 30h
0x180020274  xor     ebx, ebx
0x180020276  mov     r14d, r9d
0x180020279  mov     rdi, r8
0x18002027c  mov     rbp, rdx
0x18002027f  mov     esi, ecx
0x180020281  cmp     r9d, 2
0x180020285  jnb     short loc_180020291
0x180020287  mov     ebx, 7Ah ; 'z'
0x18002028c  jmp     loc_180020329
0x180020291  test    esi, esi
0x180020293  jnz     short loc_18002029E
0x180020295  mov     [r8], bx
0x180020299  jmp     loc_180020329
0x18002029e  call    cs:__imp_htons
0x1800202a4  mov     [rsp+58h+arg_18], ebx
0x1800202a8  lea     r15, [rdi+2]
0x1800202ac  mov     [rdi], ax
0x1800202af  test    esi, esi
0x1800202b1  jz      short loc_180020329
0x1800202b3  mov     r13, r14
0x1800202b6  movzx   r12d, word ptr [rbp+8]
0x1800202bb  mov     rcx, rbp
0x1800202be  mov     rax, [rbp+10h]
0x1800202c2  add     rbp, 18h
0x1800202c6  mov     [rsp+58h+Src], rax
0x1800202cb  mov     r14d, r12d
0x1800202ce  mov     eax, r12d
0x1800202d1  sub     rax, rdi
0x1800202d4  add     rax, 4
0x1800202d8  add     rax, r15
0x1800202db  cmp     rax, r13
0x1800202de  ja      short loc_180020324
0x1800202e0  movzx   ecx, word ptr [rcx]; hostshort
0x1800202e3  call    cs:__imp_htons
0x1800202e9  movzx   ecx, r12w; hostshort
0x1800202ed  mov     [r15], ax
0x1800202f1  call    cs:__imp_htons
0x1800202f7  mov     rdx, [rsp+58h+Src]; Src
0x1800202fc  lea     rcx, [r15+4]; void *
0x180020300  mov     r8d, r12d; Size
0x180020303  mov     [r15+2], ax
0x180020308  call    memmove_0
0x18002030d  mov     ecx, [rsp+58h+arg_18]
0x180020311  add     r15, 4
0x180020315  inc     ecx
0x180020317  add     r15, r12
0x18002031a  mov     [rsp+58h+arg_18], ecx
0x18002031e  cmp     ecx, esi
0x180020320  jb      short loc_1800202B6
0x180020322  jmp     short loc_180020329
0x180020324  mov     ebx, 6Fh ; 'o'
0x180020329  mov     rbp, [rsp+58h+arg_8]
0x18002032e  mov     eax, ebx
0x180020330  mov     rbx, [rsp+58h+arg_0]
0x180020335  mov     rsi, [rsp+58h+arg_10]
0x18002033a  add     rsp, 30h
0x18002033e  pop     r15
0x180020340  pop     r14
0x180020342  pop     r13
0x180020344  pop     r12
0x180020346  pop     rdi
0x180020347  retn
```
