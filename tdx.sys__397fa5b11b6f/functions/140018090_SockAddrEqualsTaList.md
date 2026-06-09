# SockAddrEqualsTaList

- ea: `0x140018090`
- end: `0x140018210`
- name: `SockAddrEqualsTaList`
- size: `384`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140001ce0`
- `0x140007b90`
- `0x140010a08`

## callees

- `0x140002250`
- `0x140010cac`
- `0x140018090`
- `0x140018e20`

## pseudocode

```c
bool __fastcall SockAddrEqualsTaList(__int16 *a1, __int64 a2, int a3, __int64 a4, char a5)
{
  int v5; // r8d
  int v7; // r10d
  char v8; // al
  char v9; // r8
  __int64 v10; // rdx
  _WORD *v11; // rdx
  __int16 v12; // bp
  __int64 v13; // rax
  bool v14; // zf
  int v15; // ebx
  __int16 *v16; // r14
  __int16 v17; // si
  __int64 v18; // rcx
  __int16 v20; // ax
  int v21; // eax

  v5 = a3 - 4;
  if ( v5 <= 0 )
    return 0;
  if ( *(int *)a2 < 1 )
    return 0;
  v7 = v5 - 4;
  if ( v5 - 4 <= 0 )
    return 0;
  if ( a5 )
  {
    v8 = INETADDR_ISV4MAPPED(a1);
    v11 = (_WORD *)(v10 + 6);
    if ( v8 && *v11 == 2 )
    {
      v12 = 2;
      v13 = 10;
    }
    else
    {
      v12 = *a1;
      v13 = 4;
      v9 = 0;
      if ( *a1 != 23 )
        v13 = 2;
    }
    v14 = *a1 == 23;
  }
  else
  {
    v12 = *a1;
    v11 = (_WORD *)(a2 + 6);
    if ( *v11 != *a1 )
      return 0;
    v13 = 4;
    v14 = v12 == 23;
    v9 = 0;
    if ( v12 != 23 )
      v13 = 2;
  }
  if ( v14 )
    v15 = *((_DWORD *)a1 + 6);
  else
    v15 = 0;
  v16 = &a1[v13];
  if ( v7 < *(unsigned __int16 *)(a2 + 4) )
    return 0;
  v17 = a1[1];
  if ( v9 )
  {
    v18 = a2 + 8;
    if ( *(_DWORD *)v16 == *(_DWORD *)(a2 + 10) && v17 == *(_WORD *)v18 )
      return 1;
  }
  else
  {
    if ( !memcmp(a1, v11, *(unsigned __int16 *)(a2 + 4)) )
      return 1;
    v18 = a2 + 8;
  }
  if ( v12 != 2 )
  {
    if ( v12 == 23 )
    {
      if ( v15 != *(_DWORD *)(a2 + 30)
        || (*((_QWORD *)v16 + 1) != *(_QWORD *)(a2 + 22) || *(_QWORD *)v16 != *(_QWORD *)(a2 + 14))
        && !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)v16)
        && !IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)(a2 + 14)) )
      {
        return 0;
      }
      v20 = *(_WORD *)(a2 + 8);
      return v17 == v20 || !v17 || !v20;
    }
    if ( v12 != 35 )
      return 0;
  }
  v21 = *(_DWORD *)(v18 + 2);
  return (*(_DWORD *)v16 == v21 || !*(_DWORD *)v16 || !v21) && (v17 == *(_WORD *)v18 || !v17 || !*(_WORD *)v18);
}

```

## disassembly

```asm
0x140018090  push    rbx
0x140018092  push    rbp
0x140018093  push    rsi
0x140018094  push    rdi
0x140018095  push    r12
0x140018097  push    r14
0x140018099  push    r15
0x14001809b  sub     rsp, 20h
0x14001809f  add     r8d, 0FFFFFFFCh
0x1400180a3  xor     r15d, r15d
0x1400180a6  mov     rdi, rdx
0x1400180a9  test    r8d, r8d
0x1400180ac  jle     loc_140018190
0x1400180b2  cmp     dword ptr [rdx], 1
0x1400180b5  jl      loc_140018190
0x1400180bb  lea     r10d, [r8-4]
0x1400180bf  test    r10d, r10d
0x1400180c2  jle     loc_140018190
0x1400180c8  mov     r8b, [rsp+58h+arg_20]
0x1400180d0  lea     r12d, [r15+2]
0x1400180d4  test    r8b, r8b
0x1400180d7  jz      short loc_140018113
0x1400180d9  call    INETADDR_ISV4MAPPED
0x1400180de  add     rdx, 6
0x1400180e2  test    al, al
0x1400180e4  jz      short loc_1400180F6
0x1400180e6  cmp     [rdx], r12w
0x1400180ea  jnz     short loc_1400180F6
0x1400180ec  movzx   ebp, r12w
0x1400180f0  lea     eax, [r15+14h]
0x1400180f4  jmp     short loc_14001810D
0x1400180f6  movzx   ebp, word ptr [rcx]
0x1400180f9  mov     eax, 8
0x1400180fe  cmp     bp, 17h
0x140018102  mov     r8b, r15b
0x140018105  lea     r9d, [rax-4]
0x140018109  cmovnz  eax, r9d
0x14001810d  cmp     word ptr [rcx], 17h
0x140018111  jmp     short loc_140018133
0x140018113  movzx   ebp, word ptr [rcx]
0x140018116  add     rdx, 6; Buf2
0x14001811a  cmp     [rdx], bp
0x14001811d  jnz     short loc_140018190
0x14001811f  mov     eax, 8
0x140018124  cmp     bp, 17h
0x140018128  mov     r8b, r15b
0x14001812b  lea     r9d, [rax-4]
0x14001812f  cmovnz  eax, r9d
0x140018133  jnz     short loc_14001813A
0x140018135  mov     ebx, [rcx+18h]
0x140018138  jmp     short loc_14001813D
0x14001813a  mov     ebx, r15d
0x14001813d  lea     r14, [rax+rcx]
0x140018141  movzx   eax, word ptr [rdi+4]
0x140018145  cmp     r10d, eax
0x140018148  jl      short loc_140018190
0x14001814a  movzx   esi, word ptr [rcx+2]
0x14001814e  test    r8b, r8b
0x140018151  jz      short loc_14001816A
0x140018153  lea     rcx, [rdi+8]; Buf1
0x140018157  mov     eax, [rcx+2]
0x14001815a  cmp     [r14], eax
0x14001815d  jnz     short loc_14001817E
0x14001815f  cmp     si, [rcx]
0x140018162  jz      loc_14001820C
0x140018168  jmp     short loc_14001817E
0x14001816a  mov     r8, rax; Size
0x14001816d  call    memcmp
0x140018172  test    eax, eax
0x140018174  jz      loc_14001820C
0x14001817a  lea     rcx, [rdi+8]
0x14001817e  cmp     bp, r12w
0x140018182  jz      short loc_1400181E8
0x140018184  cmp     bp, 17h
0x140018188  jz      short loc_1400181A2
0x14001818a  cmp     bp, 23h ; '#'
0x14001818e  jz      short loc_1400181E8
0x140018190  xor     al, al
0x140018192  add     rsp, 20h
0x140018196  pop     r15
0x140018198  pop     r14
0x14001819a  pop     r12
0x14001819c  pop     rdi
0x14001819d  pop     rsi
0x14001819e  pop     rbp
0x14001819f  pop     rbx
0x1400181a0  retn
0x1400181a2  cmp     ebx, [rdi+1Eh]
0x1400181a5  jnz     short loc_140018190
0x1400181a7  mov     rax, [rdi+16h]
0x1400181ab  cmp     [r14+8], rax
0x1400181af  jnz     short loc_1400181BA
0x1400181b1  mov     rax, [rdi+0Eh]
0x1400181b5  cmp     [r14], rax
0x1400181b8  jz      short loc_1400181D3
0x1400181ba  mov     rcx, r14; a
0x1400181bd  call    IN6_IS_ADDR_UNSPECIFIED
0x1400181c2  test    al, al
0x1400181c4  jnz     short loc_1400181D3
0x1400181c6  lea     rcx, [rdi+0Eh]; a
0x1400181ca  call    IN6_IS_ADDR_UNSPECIFIED
0x1400181cf  test    al, al
0x1400181d1  jz      short loc_140018190
0x1400181d3  movzx   eax, word ptr [rdi+8]
0x1400181d7  cmp     si, ax
0x1400181da  jz      short loc_14001820C
0x1400181dc  test    si, si
0x1400181df  jz      short loc_14001820C
0x1400181e1  test    ax, ax
0x1400181e4  jz      short loc_14001820C
0x1400181e6  jmp     short loc_140018190
0x1400181e8  mov     eax, [rcx+2]
0x1400181eb  mov     edx, [r14]
0x1400181ee  cmp     edx, eax
0x1400181f0  jz      short loc_1400181FA
0x1400181f2  test    edx, edx
0x1400181f4  jz      short loc_1400181FA
0x1400181f6  test    eax, eax
0x1400181f8  jnz     short loc_140018190
0x1400181fa  movzx   edx, word ptr [rcx]
0x1400181fd  cmp     si, dx
0x140018200  jz      short loc_14001820C
0x140018202  test    si, si
0x140018205  jz      short loc_14001820C
0x140018207  test    dx, dx
0x14001820a  jnz     short loc_140018190
0x14001820c  mov     al, 1
0x14001820e  jmp     short loc_140018192
```
