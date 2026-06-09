# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x1800030cc`
- end: `0x18000334b`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `639`
- prototype: `__int64 __fastcall(LPCWSTR *this, WCHAR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800034f0`

## callees

- `0x180001470`
- `0x1800030cc`

## import_xrefs

- `KERNEL32!lstrcpynW` at `0x1800031cd`
- `KERNEL32!lstrcpynW` at `0x1800031cd`
- `KERNEL32!lstrcmpiW` at `0x1800031f4`
- `KERNEL32!lstrcmpiW` at `0x1800031f4`
- `ole32!CoTaskMemRealloc` at `0x18000323b`
- `ole32!CoTaskMemRealloc` at `0x180003290`
- `ole32!CoTaskMemRealloc` at `0x1800032de`
- `ole32!CoTaskMemRealloc` at `0x18000323b`
- `ole32!CoTaskMemRealloc` at `0x180003290`
- `ole32!CoTaskMemRealloc` at `0x1800032de`
- `ole32!CoTaskMemFree` at `0x1800032f1`
- `ole32!CoTaskMemFree` at `0x180003314`
- `ole32!CoTaskMemFree` at `0x1800032f1`
- `ole32!CoTaskMemFree` at `0x180003314`
- `ole32!CoTaskMemAlloc` at `0x180003133`
- `ole32!CoTaskMemAlloc` at `0x180003133`
- `USER32!CharNextW` at `0x180003164`
- `USER32!CharNextW` at `0x180003194`
- `USER32!CharNextW` at `0x18000326c`
- `USER32!CharNextW` at `0x1800032ae`
- `USER32!CharNextW` at `0x180003164`
- `USER32!CharNextW` at `0x180003194`
- `USER32!CharNextW` at `0x18000326c`
- `USER32!CharNextW` at `0x1800032ae`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, WCHAR *a2, unsigned __int16 **a3)
{
  unsigned __int16 **v3; // r14
  LPWSTR v4; // rbx
  __int64 v6; // rsi
  int v7; // esi
  void *v8; // rdi
  int v9; // ebp
  WCHAR v10; // ax
  WCHAR v11; // ax
  const WCHAR *v12; // r14
  __int64 v13; // r8
  LPCWSTR v14; // r12
  int v15; // ebx
  unsigned int v16; // ebx
  __int16 *v17; // rbx
  LPVOID v18; // rax
  __int16 v19; // ax
  __int64 v20; // rcx
  const WCHAR *i; // rax
  LPVOID v22; // rax
  __int64 v23; // rcx
  LPVOID v24; // rax
  WCHAR String1[32]; // [rsp+30h] [rbp-88h] BYREF

  v3 = a3;
  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6 + 2;
  v8 = CoTaskMemAlloc(2LL * v7);
  if ( !v8 )
  {
LABEL_41:
    v16 = -2147024882;
    goto LABEL_42;
  }
  *this = v4;
  v9 = 0;
  v10 = *v4;
  if ( !*v4 )
  {
LABEL_39:
    if ( v9 + 1 > v7 )
    {
      v24 = CoTaskMemRealloc(v8, 4LL * v7);
      if ( !v24 )
        goto LABEL_41;
      v8 = v24;
    }
    *((_WORD *)v8 + v9) = *v4;
    *v3 = (unsigned __int16 *)v8;
    CoTaskMemFree(0);
    return 0;
  }
  while ( 1 )
  {
    if ( v10 == 37 )
    {
      v4 = CharNextW(v4);
      *this = v4;
      v11 = *v4;
      if ( *v4 != 37 )
        break;
    }
    if ( v9 + 1 > v7 )
    {
      v7 *= 2;
      v22 = CoTaskMemRealloc(v8, 2LL * v7);
      if ( !v22 )
        goto LABEL_41;
      v8 = v22;
    }
    v23 = v9++;
    *((_WORD *)v8 + v23) = *v4;
LABEL_37:
    v4 = CharNextW(*this);
    *this = v4;
    v10 = *v4;
    if ( !*v4 )
    {
      v3 = a3;
      goto LABEL_39;
    }
  }
  if ( !v4 )
    goto LABEL_21;
  v12 = 0;
  while ( v11 )
  {
    if ( v11 == 37 )
    {
      v12 = v4;
      break;
    }
    v4 = CharNextW(v4);
    v11 = *v4;
  }
  if ( !v12 )
  {
LABEL_21:
    v16 = -2147352567;
    goto LABEL_42;
  }
  v13 = v12 - *this;
  if ( (int)v13 <= 31 )
  {
    lstrcpynW(String1, *this, v13 + 1);
    v14 = this[1];
    v15 = 0;
    if ( *((int *)v14 + 2) <= 0 )
      goto LABEL_21;
    while ( lstrcmpiW(**(LPCWSTR **)(*(_QWORD *)v14 + 8LL * v15), String1) )
    {
      if ( ++v15 >= *((_DWORD *)v14 + 2) )
        goto LABEL_21;
    }
    v17 = *(__int16 **)(*(_QWORD *)(*(_QWORD *)v14 + 8LL * v15) + 8LL);
    if ( !v17 )
      goto LABEL_21;
    while ( *v17 )
    {
      if ( v9 + 1 > v7 )
      {
        v7 *= 2;
        v18 = CoTaskMemRealloc(v8, 2LL * v7);
        if ( !v18 )
          goto LABEL_41;
        v8 = v18;
      }
      v19 = *v17++;
      v20 = v9++;
      *((_WORD *)v8 + v20) = v19;
    }
    for ( i = *this; i != v12; *this = i )
      i = CharNextW(i);
    goto LABEL_37;
  }
  v16 = -2147467259;
LABEL_42:
  CoTaskMemFree(v8);
  return v16;
}

```

## disassembly

```asm
0x1800030cc  mov     [rsp+arg_8], rbx
0x1800030d1  push    rbp
0x1800030d2  push    rsi
0x1800030d3  push    rdi
0x1800030d4  push    r12
0x1800030d6  push    r13
0x1800030d8  push    r14
0x1800030da  push    r15
0x1800030dc  sub     rsp, 80h
0x1800030e3  mov     rax, cs:__security_cookie
0x1800030ea  xor     rax, rsp
0x1800030ed  mov     [rsp+0B8h+var_48], rax
0x1800030f2  xor     r13d, r13d
0x1800030f5  mov     [rsp+0B8h+var_98], r8
0x1800030fa  mov     r14, r8
0x1800030fd  mov     rbx, rdx
0x180003100  mov     r15, rcx
0x180003103  test    rdx, rdx
0x180003106  jz      loc_18000331E
0x18000310c  test    r8, r8
0x18000310f  jz      loc_18000331E
0x180003115  mov     [r8], r13
0x180003118  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000311c  inc     rsi
0x18000311f  cmp     [rdx+rsi*2], r13w
0x180003124  jnz     short loc_18000311C
0x180003126  lea     esi, ds:2[rsi*2]
0x18000312d  movsxd  rcx, esi
0x180003130  add     rcx, rcx; cb
0x180003133  call    cs:__imp_CoTaskMemAlloc
0x180003139  mov     rdi, rax
0x18000313c  test    rax, rax
0x18000313f  jz      loc_1800032E9
0x180003145  mov     [r15], rbx
0x180003148  mov     ebp, r13d
0x18000314b  movzx   eax, word ptr [rbx]
0x18000314e  test    ax, ax
0x180003151  jz      loc_1800032CB
0x180003157  cmp     ax, 25h ; '%'
0x18000315b  jnz     loc_18000327C
0x180003161  mov     rcx, rbx; lpsz
0x180003164  call    cs:__imp_CharNextW
0x18000316a  mov     rbx, rax
0x18000316d  mov     [r15], rax
0x180003170  movzx   eax, word ptr [rax]
0x180003173  cmp     ax, 25h ; '%'
0x180003177  jz      loc_18000327C
0x18000317d  test    rbx, rbx
0x180003180  jz      loc_180003207
0x180003186  mov     r14, r13
0x180003189  jmp     short loc_1800031A0
0x18000318b  cmp     ax, 25h ; '%'
0x18000318f  jz      short loc_1800031A7
0x180003191  mov     rcx, rbx; lpsz
0x180003194  call    cs:__imp_CharNextW
0x18000319a  mov     rbx, rax
0x18000319d  movzx   eax, word ptr [rax]
0x1800031a0  test    ax, ax
0x1800031a3  jnz     short loc_18000318B
0x1800031a5  jmp     short loc_1800031AA
0x1800031a7  mov     r14, rbx
0x1800031aa  test    r14, r14
0x1800031ad  jz      short loc_180003207
0x1800031af  mov     r8, r14
0x1800031b2  sub     r8, [r15]
0x1800031b5  sar     r8, 1
0x1800031b8  cmp     r8d, 1Fh
0x1800031bc  jg      loc_1800032FB
0x1800031c2  mov     rdx, [r15]; lpString2
0x1800031c5  lea     rcx, [rsp+0B8h+String1]; lpString1
0x1800031ca  inc     r8d; iMaxLength
0x1800031cd  call    cs:__imp_lstrcpynW
0x1800031d3  mov     r12, [r15+8]
0x1800031d7  mov     ebx, r13d
0x1800031da  cmp     [r12+8], r13d
0x1800031df  jle     short loc_180003207
0x1800031e1  mov     rax, [r12]
0x1800031e5  lea     rdx, [rsp+0B8h+String1]; lpString2
0x1800031ea  movsxd  r13, ebx
0x1800031ed  mov     rcx, [rax+r13*8]
0x1800031f1  mov     rcx, [rcx]; lpString1
0x1800031f4  call    cs:__imp_lstrcmpiW
0x1800031fa  test    eax, eax
0x1800031fc  jz      short loc_180003211
0x1800031fe  inc     ebx
0x180003200  cmp     ebx, [r12+8]
0x180003205  jl      short loc_1800031E1
0x180003207  mov     ebx, 80020009h
0x18000320c  jmp     loc_1800032EE
0x180003211  mov     rax, [r12]
0x180003215  mov     rcx, [rax+r13*8]
0x180003219  xor     r13d, r13d
0x18000321c  mov     rbx, [rcx+8]
0x180003220  test    rbx, rbx
0x180003223  jz      short loc_180003207
0x180003225  jmp     short loc_18000325E
0x180003227  lea     r12d, [rbp+1]
0x18000322b  cmp     r12d, esi
0x18000322e  jle     short loc_18000324D
0x180003230  add     esi, esi
0x180003232  mov     rcx, rdi; pv
0x180003235  movsxd  rdx, esi
0x180003238  add     rdx, rdx; cb
0x18000323b  call    cs:__imp_CoTaskMemRealloc
0x180003241  test    rax, rax
0x180003244  jz      loc_1800032E9
0x18000324a  mov     rdi, rax
0x18000324d  movzx   eax, word ptr [rbx]
0x180003250  add     rbx, 2
0x180003254  movsxd  rcx, ebp
0x180003257  mov     ebp, r12d
0x18000325a  mov     [rdi+rcx*2], ax
0x18000325e  cmp     [rbx], r13w
0x180003262  jnz     short loc_180003227
0x180003264  mov     rax, [r15]
0x180003267  jmp     short loc_180003275
0x180003269  mov     rcx, rax; lpsz
0x18000326c  call    cs:__imp_CharNextW
0x180003272  mov     [r15], rax
0x180003275  cmp     rax, r14
0x180003278  jnz     short loc_180003269
0x18000327a  jmp     short loc_1800032AB
0x18000327c  lea     r14d, [rbp+1]
0x180003280  cmp     r14d, esi
0x180003283  jle     short loc_18000329E
0x180003285  add     esi, esi
0x180003287  mov     rcx, rdi; pv
0x18000328a  movsxd  rdx, esi
0x18000328d  add     rdx, rdx; cb
0x180003290  call    cs:__imp_CoTaskMemRealloc
0x180003296  test    rax, rax
0x180003299  jz      short loc_1800032E9
0x18000329b  mov     rdi, rax
0x18000329e  movzx   eax, word ptr [rbx]
0x1800032a1  movsxd  rcx, ebp
0x1800032a4  mov     ebp, r14d
0x1800032a7  mov     [rdi+rcx*2], ax
0x1800032ab  mov     rcx, [r15]; lpsz
0x1800032ae  call    cs:__imp_CharNextW
0x1800032b4  mov     rbx, rax
0x1800032b7  mov     [r15], rax
0x1800032ba  movzx   eax, word ptr [rax]
0x1800032bd  test    ax, ax
0x1800032c0  jnz     loc_180003157
0x1800032c6  mov     r14, [rsp+0B8h+var_98]
0x1800032cb  lea     eax, [rbp+1]
0x1800032ce  cmp     eax, esi
0x1800032d0  jle     short loc_180003305
0x1800032d2  lea     eax, [rsi+rsi]
0x1800032d5  mov     rcx, rdi; pv
0x1800032d8  movsxd  rdx, eax
0x1800032db  add     rdx, rdx; cb
0x1800032de  call    cs:__imp_CoTaskMemRealloc
0x1800032e4  test    rax, rax
0x1800032e7  jnz     short loc_180003302
0x1800032e9  mov     ebx, 8007000Eh
0x1800032ee  mov     rcx, rdi; pv
0x1800032f1  call    cs:__imp_CoTaskMemFree
0x1800032f7  mov     eax, ebx
0x1800032f9  jmp     short loc_180003323
0x1800032fb  mov     ebx, 80004005h
0x180003300  jmp     short loc_1800032EE
0x180003302  mov     rdi, rax
0x180003305  movzx   eax, word ptr [rbx]
0x180003308  movsxd  rcx, ebp
0x18000330b  mov     [rdi+rcx*2], ax
0x18000330f  xor     ecx, ecx; pv
0x180003311  mov     [r14], rdi
0x180003314  call    cs:__imp_CoTaskMemFree
0x18000331a  xor     eax, eax
0x18000331c  jmp     short loc_180003323
0x18000331e  mov     eax, 80004003h
0x180003323  mov     rcx, [rsp+0B8h+var_48]
0x180003328  xor     rcx, rsp; StackCookie
0x18000332b  call    __security_check_cookie
0x180003330  mov     rbx, [rsp+0B8h+arg_8]
0x180003338  add     rsp, 80h
0x18000333f  pop     r15
0x180003341  pop     r14
0x180003343  pop     r13
0x180003345  pop     r12
0x180003347  pop     rdi
0x180003348  pop     rsi
0x180003349  pop     rbp
0x18000334a  retn
```
