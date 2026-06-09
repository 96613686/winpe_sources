# _RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore.llvm.18110786352924170244

- ea: `0x1400193b0`
- end: `0x1400194e6`
- name: `_RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore.llvm.18110786352924170244`
- size: `310`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14000b240`
- `0x14000b710`
- `0x14000b860`
- `0x14000bc20`
- `0x14000c0d0`
- `0x14000c1a0`
- `0x14000c2a0`
- `0x14000c640`
- `0x14000cc10`
- `0x14000e9d0`
- `0x140012770`
- `0x140012a30`
- `0x140012b60`
- `0x140012f10`
- `0x140014460`
- `0x140014940`
- `0x140014ae0`
- `0x140014dd0`
- `0x1400153c0`
- `0x140015ac0`
- `0x1400161a0`
- `0x140018840`

## callees

- `0x14000fda0`
- `0x14000fdb0`
- `0x14001790a`
- `0x140017940`
- `0x140017b00`
- `0x1400193b0`

## pseudocode

```c
__int64 __fastcall RNvMs4_NtCsexo9QDNEsji_5alloc7raw_vecINtB5_11RawVecInnerINtCsdwtLm5uWta6_10gdi_region22ScanLookAsideAllocatorKj70_EE11finish_growCsdcpJtfrLhSH_7rgncore_llvm_18110786352924170244(
        __int64 *a1,
        __int64 a2,
        const void *a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  unsigned __int128 v7; // rax
  unsigned __int64 v8; // r9
  __int64 v9; // r15
  __int64 *v11; // r13
  __int64 v12; // rbp
  __int64 v13; // rax
  __int64 *v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // rax
  void *v17; // rbx
  bool v18; // zf

  v7 = a4 * (unsigned __int128)a6;
  BYTE8(v7) = *((_QWORD *)&v7 + 1) != 0;
  v8 = 0x8000000000000000uLL - a5;
  LOBYTE(v8) = BYTE8(v7) | ((unsigned __int64)v7 > 0x8000000000000000uLL - a5);
  v9 = 1;
  if ( !(_BYTE)v8 )
  {
    if ( a2 )
    {
      if ( a5 <= 0x10 )
      {
        v11 = a1;
        if ( (_QWORD)v7 == 112 )
        {
          v12 = 112;
          v13 = RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate(a1, *((_QWORD *)&v7 + 1), a3, v8);
        }
        else
        {
          v12 = v7;
          v13 = Win32AllocPool_0(v7, 1852011335);
        }
        v17 = (void *)v13;
        v18 = v13 == 0;
        a1 = v11;
        *(_QWORD *)&v7 = v12;
        if ( !v18 )
        {
          memmove(v17, a3, a2 * a6);
          if ( a2 * a6 == 112 )
            RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free(a3);
          else
            Win32FreePool_0(a3);
          a1 = v11;
          *(_QWORD *)&v7 = v12;
LABEL_18:
          a1[1] = (__int64)v17;
          *((_QWORD *)&v7 + 1) = 16;
          v9 = 0;
          goto LABEL_20;
        }
      }
    }
    else if ( a5 <= 0x10 )
    {
      v14 = a1;
      if ( (_QWORD)v7 == 112 )
      {
        v15 = 112;
        v16 = RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate(a1, *((_QWORD *)&v7 + 1), a3, v8);
      }
      else
      {
        v15 = v7;
        v16 = Win32AllocPool_0(v7, 1852011335);
      }
      v17 = (void *)v16;
      v18 = v16 == 0;
      a1 = v14;
      *(_QWORD *)&v7 = v15;
      if ( !v18 )
        goto LABEL_18;
    }
    a1[1] = a5;
    *((_QWORD *)&v7 + 1) = 16;
    goto LABEL_20;
  }
  *((_QWORD *)&v7 + 1) = 8;
  *(_QWORD *)&v7 = 0;
LABEL_20:
  *(__int64 *)((char *)a1 + *((_QWORD *)&v7 + 1)) = v7;
  *a1 = v9;
  return v7;
}

```

## disassembly

```asm
0x1400193b0  push    r15
0x1400193b2  push    r14
0x1400193b4  push    r13
0x1400193b6  push    r12
0x1400193b8  push    rsi
0x1400193b9  push    rdi
0x1400193ba  push    rbp
0x1400193bb  push    rbx
0x1400193bc  sub     rsp, 28h
0x1400193c0  mov     rdi, rdx
0x1400193c3  mov     r12, [rsp+68h+arg_20]
0x1400193cb  mov     rsi, [rsp+68h+arg_28]
0x1400193d3  mov     rax, rsi
0x1400193d6  mul     r9
0x1400193d9  seto    dl
0x1400193dc  mov     r9, 8000000000000000h
0x1400193e6  sub     r9, r12
0x1400193e9  cmp     rax, r9
0x1400193ec  setnbe  r9b
0x1400193f0  or      r9b, dl
0x1400193f3  mov     r15d, 1
0x1400193f9  jz      short loc_140019407
0x1400193fb  mov     edx, 8
0x140019400  xor     eax, eax
0x140019402  jmp     loc_1400194CE
0x140019407  test    rdi, rdi
0x14001940a  jz      short loc_14001942C
0x14001940c  cmp     r12, 10h
0x140019410  ja      loc_1400194C5
0x140019416  mov     r14, r8
0x140019419  mov     r13, rcx
0x14001941c  cmp     rax, 70h ; 'p'
0x140019420  jnz     short loc_140019449
0x140019422  mov     rbp, rax
0x140019425  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate
0x14001942a  jmp     short loc_140019459
0x14001942c  cmp     r12, 10h
0x140019430  ja      loc_1400194C5
0x140019436  mov     rsi, rcx
0x140019439  cmp     rax, 70h ; 'p'
0x14001943d  jnz     short loc_140019499
0x14001943f  mov     rdi, rax
0x140019442  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi26ScanLookAsideList_Allocate
0x140019447  jmp     short loc_1400194A9
0x140019449  mov     rbp, rax
0x14001944c  mov     rcx, rax
0x14001944f  mov     edx, 6E637347h
0x140019454  call    Win32AllocPool_0
0x140019459  mov     rbx, rax
0x14001945c  test    rax, rax
0x14001945f  mov     rcx, r13
0x140019462  mov     rax, rbp
0x140019465  jz      short loc_1400194C5
0x140019467  mov     rdx, r14; Src
0x14001946a  mov     r15, rax
0x14001946d  imul    rsi, rdi
0x140019471  mov     rcx, rbx; void *
0x140019474  mov     r8, rsi; Size
0x140019477  call    memmove
0x14001947c  mov     rcx, r14
0x14001947f  cmp     rsi, 70h ; 'p'
0x140019483  jnz     short loc_14001948C
0x140019485  call    _RNvNtCsdwtLm5uWta6_10gdi_region3ffi22ScanLookAsideList_Free
0x14001948a  jmp     short loc_140019491
0x14001948c  call    Win32FreePool_0
0x140019491  mov     rcx, r13
0x140019494  mov     rax, r15
0x140019497  jmp     short loc_1400194B7
0x140019499  mov     rdi, rax
0x14001949c  mov     rcx, rax
0x14001949f  mov     edx, 6E637347h
0x1400194a4  call    Win32AllocPool_0
0x1400194a9  mov     rbx, rax
0x1400194ac  test    rax, rax
0x1400194af  mov     rcx, rsi
0x1400194b2  mov     rax, rdi
0x1400194b5  jz      short loc_1400194C5
0x1400194b7  mov     [rcx+8], rbx
0x1400194bb  mov     edx, 10h
0x1400194c0  xor     r15d, r15d
0x1400194c3  jmp     short loc_1400194CE
0x1400194c5  mov     [rcx+8], r12
0x1400194c9  mov     edx, 10h
0x1400194ce  mov     [rcx+rdx], rax
0x1400194d2  mov     [rcx], r15
0x1400194d5  add     rsp, 28h
0x1400194d9  pop     rbx
0x1400194da  pop     rbp
0x1400194db  pop     rdi
0x1400194dc  pop     rsi
0x1400194dd  pop     r12
0x1400194df  pop     r13
0x1400194e1  pop     r14
0x1400194e3  pop     r15
0x1400194e5  retn
```
