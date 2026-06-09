# OSBODeleteDriverEntry

- ea: `0x180012b30`
- end: `0x180012c88`
- name: `OSBODeleteDriverEntry`
- size: `344`
- prototype: `char __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180012b30`
- `0x180012d4c`
- `0x1800179ad`
- `0x180018010`

## pseudocode

```c
char __fastcall OSBODeleteDriverEntry(__int64 a1, int a2)
{
  char v2; // bp
  __int64 v4; // rdi
  __int64 v5; // rsi
  __int64 v6; // rax
  int v7; // eax
  __int64 i; // rsi
  __int64 v9; // rcx
  unsigned int v10; // r14d
  char *v11; // rax
  char *v12; // rbp

  v2 = 0;
  if ( a1 )
  {
    v4 = *(_QWORD *)(a1 + 64);
    v5 = 0;
    while ( v4 )
    {
      if ( a2 == *(_DWORD *)v4 )
      {
        *(_DWORD *)(v4 + 2084) |= 0x10000002u;
        *(_DWORD *)(a1 + 4) |= 0x10000000u;
        v2 = (*(__int64 (__fastcall **)(__int64))(v4 + 2112))(v4);
        if ( v2 )
        {
          v6 = *(_QWORD *)(v4 + 2096);
          if ( v5 )
            *(_QWORD *)(v5 + 2096) = v6;
          else
            *(_QWORD *)(a1 + 64) = v6;
          v7 = *(_DWORD *)(a1 + 72);
          if ( v7 )
            *(_DWORD *)(a1 + 72) = v7 - 1;
          for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 88); i = (unsigned int)(i + 1) )
          {
            v9 = *(_QWORD *)(a1 + 80);
            if ( *(_DWORD *)(v9 + 4 * i) == *(_DWORD *)v4 )
            {
              if ( (_DWORD)i != -1 )
              {
                v10 = *(_DWORD *)(a1 + 88) - 1;
                if ( *(_DWORD *)(a1 + 88) == 1 )
                {
                  SBE_FREE(v9);
                  *(_QWORD *)(a1 + 80) = 0;
                  *(_DWORD *)(a1 + 88) = 0;
                }
                else if ( AllocRoutine && (v11 = (char *)AllocRoutine(4LL * v10), (v12 = v11) != 0) )
                {
                  memcpy_0(v11, *(const void **)(a1 + 80), 4 * i);
                  memcpy_0(
                    &v12[4 * i],
                    (const void *)(4 * i + *(_QWORD *)(a1 + 80) + 4LL),
                    4LL * (v10 - (unsigned int)i));
                  SBE_FREE(*(_QWORD *)(a1 + 80));
                  *(_QWORD *)(a1 + 80) = v12;
                  v2 = 1;
                  *(_DWORD *)(a1 + 88) = v10;
                }
                else
                {
                  v2 = 0;
                }
              }
              break;
            }
          }
          SBE_FREE(v4);
          *(_DWORD *)(a1 + 4) |= 0x10000000u;
        }
        return v2;
      }
      v5 = v4;
      v4 = *(_QWORD *)(v4 + 2096);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180012b30  push    rbx
0x180012b32  push    rbp
0x180012b33  push    rsi
0x180012b34  push    rdi
0x180012b35  push    r14
0x180012b37  push    r15
0x180012b39  sub     rsp, 28h
0x180012b3d  xor     bpl, bpl
0x180012b40  mov     rbx, rcx
0x180012b43  test    rcx, rcx
0x180012b46  jz      loc_180012C78
0x180012b4c  mov     rdi, [rcx+40h]
0x180012b50  xor     esi, esi
0x180012b52  test    rdi, rdi
0x180012b55  jz      loc_180012C78
0x180012b5b  cmp     edx, [rdi]
0x180012b5d  jz      short loc_180012B6B
0x180012b5f  mov     rsi, rdi
0x180012b62  mov     rdi, [rdi+830h]
0x180012b69  jmp     short loc_180012B52
0x180012b6b  or      dword ptr [rdi+824h], 10000002h
0x180012b75  bts     dword ptr [rcx+4], 1Ch
0x180012b7a  mov     rcx, rdi
0x180012b7d  mov     rax, [rdi+840h]
0x180012b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b89  mov     bpl, al
0x180012b8c  test    al, al
0x180012b8e  jz      loc_180012C78
0x180012b94  mov     rax, [rdi+830h]
0x180012b9b  test    rsi, rsi
0x180012b9e  jnz     short loc_180012BA6
0x180012ba0  mov     [rbx+40h], rax
0x180012ba4  jmp     short loc_180012BAD
0x180012ba6  mov     [rsi+830h], rax
0x180012bad  mov     eax, [rbx+48h]
0x180012bb0  test    eax, eax
0x180012bb2  jz      short loc_180012BB9
0x180012bb4  dec     eax
0x180012bb6  mov     [rbx+48h], eax
0x180012bb9  mov     edx, [rdi]
0x180012bbb  xor     esi, esi
0x180012bbd  cmp     esi, [rbx+58h]
0x180012bc0  jnb     loc_180012C6B
0x180012bc6  mov     rcx, [rbx+50h]
0x180012bca  lea     r15, ds:0[rsi*4]
0x180012bd2  cmp     [rcx+r15], edx
0x180012bd6  jz      short loc_180012BDC
0x180012bd8  inc     esi
0x180012bda  jmp     short loc_180012BBD
0x180012bdc  cmp     esi, 0FFFFFFFFh
0x180012bdf  jz      loc_180012C6B
0x180012be5  mov     r14d, [rbx+58h]
0x180012be9  sub     r14d, 1
0x180012bed  jz      short loc_180012C57
0x180012bef  mov     rax, cs:AllocRoutine
0x180012bf6  test    rax, rax
0x180012bf9  jz      short loc_180012C52
0x180012bfb  mov     ecx, r14d
0x180012bfe  shl     rcx, 2
0x180012c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c07  mov     rbp, rax
0x180012c0a  test    rax, rax
0x180012c0d  jz      short loc_180012C52
0x180012c0f  mov     rdx, [rbx+50h]; Src
0x180012c13  mov     r8, r15; Size
0x180012c16  mov     rcx, rax; void *
0x180012c19  call    memcpy_0
0x180012c1e  mov     rdx, [rbx+50h]
0x180012c22  lea     rcx, [r15+rbp]; void *
0x180012c26  mov     r8d, r14d
0x180012c29  add     rdx, 4
0x180012c2d  sub     r8d, esi
0x180012c30  add     rdx, r15; Src
0x180012c33  shl     r8, 2; Size
0x180012c37  call    memcpy_0
0x180012c3c  mov     rcx, [rbx+50h]
0x180012c40  call    SBE_FREE
0x180012c45  mov     [rbx+50h], rbp
0x180012c49  mov     bpl, 1
0x180012c4c  mov     [rbx+58h], r14d
0x180012c50  jmp     short loc_180012C6B
0x180012c52  xor     bpl, bpl
0x180012c55  jmp     short loc_180012C6B
0x180012c57  call    SBE_FREE
0x180012c5c  mov     qword ptr [rbx+50h], 0
0x180012c64  mov     dword ptr [rbx+58h], 0
0x180012c6b  mov     rcx, rdi
0x180012c6e  call    SBE_FREE
0x180012c73  bts     dword ptr [rbx+4], 1Ch
0x180012c78  mov     al, bpl
0x180012c7b  add     rsp, 28h
0x180012c7f  pop     r15
0x180012c81  pop     r14
0x180012c83  pop     rdi
0x180012c84  pop     rsi
0x180012c85  pop     rbp
0x180012c86  pop     rbx
0x180012c87  retn
```
