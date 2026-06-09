# SIPolicyUninitialize

- ea: `0x18002019c`
- end: `0x1800204bb`
- name: `SIPolicyUninitialize`
- size: `799`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180019cd0`
- `0x18001c2b8`
- `0x18001c9ac`
- `0x18001d258`
- `0x18001e674`
- `0x1800492f8`

## callees

- `0x1800187d4`
- `0x180019a4c`
- `0x18001e5cc`
- `0x18002019c`

## pseudocode

```c
void __fastcall SIPolicyUninitialize(__int64 a1)
{
  unsigned int i; // esi
  __int64 v3; // rbp
  __int64 v4; // r14
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // r15
  __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned int j; // ebx
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int k; // edi
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+60h] [rbp+8h]
  __int64 v21; // [rsp+68h] [rbp+10h]
  __int64 v22; // [rsp+70h] [rbp+18h]

  if ( a1 )
  {
    for ( i = 0; i < *(_DWORD *)(a1 + 88); ++i )
    {
      v3 = 0;
      v4 = 168LL * i;
      do
      {
        v5 = v4 + 16 * v3;
        SIPolicyFree(*(_QWORD *)(v5 + *(_QWORD *)(a1 + 96) + 16));
        v6 = v4 + 16 * (v3 + 4);
        SIPolicyFree(*(_QWORD *)(v6 + *(_QWORD *)(a1 + 96)));
        ++v3;
        *(_QWORD *)(v5 + *(_QWORD *)(a1 + 96) + 16) = 0;
        *(_QWORD *)(v6 + *(_QWORD *)(a1 + 96)) = 0;
      }
      while ( v3 != 3 );
    }
    if ( *(_DWORD *)(a1 + 56) )
    {
      SIPolicyFree(*(_QWORD *)(a1 + 64));
      *(_QWORD *)(a1 + 64) = 0;
    }
    if ( *(_DWORD *)(a1 + 736) )
    {
      SIPolicyFree(*(_QWORD *)(a1 + 744));
      *(_QWORD *)(a1 + 744) = 0;
    }
    if ( *(_DWORD *)(a1 + 72) )
    {
      SIPolicyFree(*(_QWORD *)(a1 + 80));
      *(_QWORD *)(a1 + 80) = 0;
    }
    v7 = 0;
    v20 = 0;
    do
    {
      v8 = 28 * v7;
      v9 = 0;
      v22 = 28 * v7;
      v21 = 0;
      do
      {
        SIPolicyFree(*(_QWORD *)(a1 + 8 * (v8 + v9) + 368));
        SIPolicyFree(*(_QWORD *)(a1 + 8 * (v8 + v9) + 344));
        SIPolicyFree(*(_QWORD *)(a1 + 8 * (v8 + v9) + 280));
        SIPolicyFree(*(_QWORD *)(a1 + 8 * (v8 + v9) + 256));
        SIPolicyFree(*(_QWORD *)(a1 + 8 * (v8 + v9) + 392));
        v10 = v9 + v8;
        SIPolicyFree(*(_QWORD *)(a1 + 8 * (v9 + v8) + 216));
        v11 = v22 + v9;
        SIPolicyFree(*(_QWORD *)(a1 + 8 * v11 + 304));
        *(_QWORD *)(a1 + 8 * v10 + 368) = 0;
        *(_QWORD *)(a1 + 8 * v11 + 304) = 0;
        v9 = v21 + 1;
        *(_QWORD *)(a1 + 8 * v10 + 216) = 0;
        v8 = v22;
        *(_QWORD *)(a1 + 8 * v10 + 344) = 0;
        *(_QWORD *)(a1 + 8 * v10 + 280) = 0;
        *(_QWORD *)(a1 + 8 * v10 + 256) = 0;
        *(_QWORD *)(a1 + 8 * v10 + 392) = 0;
        v21 = v9;
      }
      while ( v9 != 3 );
      v7 = (unsigned int)(v20 + 1);
      v20 = v7;
    }
    while ( (unsigned int)v7 < 2 );
    v12 = *(_QWORD *)(a1 + 96);
    if ( v12 )
    {
      SIPolicyFree(v12);
      *(_QWORD *)(a1 + 96) = 0;
    }
    if ( *(_QWORD *)(a1 + 184) )
    {
      for ( j = 0; j < *(_DWORD *)(a1 + 168); ++j )
        SIPolicyFree(*(_QWORD *)(168LL * j + *(_QWORD *)(a1 + 184) + 136));
      SIPolicyFree(*(_QWORD *)(a1 + 184));
      *(_QWORD *)(a1 + 184) = 0;
    }
    v14 = *(_QWORD *)(a1 + 160);
    if ( v14 )
    {
      SIPolicyFree(v14);
      *(_QWORD *)(a1 + 160) = 0;
    }
    v15 = *(_QWORD *)(a1 + 104);
    if ( v15 || (v15 = *(_QWORD *)(a1 + 136)) != 0 )
      SIPolicyFree(v15);
    if ( *(_QWORD *)(a1 + 664) )
    {
      for ( k = 0; k < *(_DWORD *)(a1 + 656); ++k )
      {
        v17 = *(_QWORD *)(*(_QWORD *)(a1 + 664) + 144LL * k + 32);
        if ( v17 )
          SIPolicyFree(v17);
        v18 = *(_QWORD *)(*(_QWORD *)(a1 + 664) + 144LL * k + 104);
        if ( v18 )
        {
          SIPolicyFree(v18);
          *(_QWORD *)(*(_QWORD *)(a1 + 664) + 144LL * k + 104) = 0;
        }
      }
      SIPolicyFree(*(_QWORD *)(a1 + 664));
    }
    v19 = *(_QWORD *)(a1 + 696);
    if ( v19 )
    {
      SIPolicyFree(v19);
      *(_QWORD *)(a1 + 696) = 0;
    }
    SIPolicyFreeApplicationRegion(*(unsigned int *)(a1 + 752), *(_QWORD *)(a1 + 760));
    SIPolicyFreeSIChainInfo(a1 + 776);
    SIPolicyFree(a1);
  }
}

```

## disassembly

```asm
0x18002019c  test    rcx, rcx
0x18002019f  jz      locret_1800204B9
0x1800201a5  mov     [rsp+arg_18], rbx
0x1800201aa  push    rbp
0x1800201ab  push    rsi
0x1800201ac  push    rdi
0x1800201ad  push    r12
0x1800201af  push    r13
0x1800201b1  push    r14
0x1800201b3  push    r15
0x1800201b5  sub     rsp, 20h
0x1800201b9  xor     r12d, r12d
0x1800201bc  mov     r13, rcx
0x1800201bf  mov     esi, r12d
0x1800201c2  cmp     [rcx+58h], r12d
0x1800201c6  jbe     short loc_180020226
0x1800201c8  mov     eax, esi
0x1800201ca  mov     rbp, r12
0x1800201cd  imul    r14, rax, 0A8h
0x1800201d4  mov     rcx, [r13+60h]
0x1800201d8  mov     rdi, rbp
0x1800201db  shl     rdi, 4
0x1800201df  add     rdi, r14
0x1800201e2  mov     rcx, [rdi+rcx+10h]
0x1800201e7  call    SIPolicyFree
0x1800201ec  mov     rcx, [r13+60h]
0x1800201f0  lea     rbx, [rbp+4]
0x1800201f4  shl     rbx, 4
0x1800201f8  add     rbx, r14
0x1800201fb  mov     rcx, [rbx+rcx]
0x1800201ff  call    SIPolicyFree
0x180020204  mov     rax, [r13+60h]
0x180020208  inc     rbp
0x18002020b  mov     [rdi+rax+10h], r12
0x180020210  mov     rax, [r13+60h]
0x180020214  mov     [rbx+rax], r12
0x180020218  cmp     rbp, 3
0x18002021c  jnz     short loc_1800201D4
0x18002021e  inc     esi
0x180020220  cmp     esi, [r13+58h]
0x180020224  jb      short loc_1800201C8
0x180020226  cmp     [r13+38h], r12d
0x18002022a  jz      short loc_180020239
0x18002022c  mov     rcx, [r13+40h]
0x180020230  call    SIPolicyFree
0x180020235  mov     [r13+40h], r12
0x180020239  cmp     [r13+2E0h], r12d
0x180020240  jz      short loc_180020255
0x180020242  mov     rcx, [r13+2E8h]
0x180020249  call    SIPolicyFree
0x18002024e  mov     [r13+2E8h], r12
0x180020255  cmp     [r13+48h], r12d
0x180020259  jz      short loc_180020268
0x18002025b  mov     rcx, [r13+50h]
0x18002025f  call    SIPolicyFree
0x180020264  mov     [r13+50h], r12
0x180020268  mov     eax, r12d
0x18002026b  mov     [rsp+58h+arg_0], eax
0x18002026f  imul    rdi, rax, 1Ch
0x180020273  mov     rbx, r12
0x180020276  mov     [rsp+58h+arg_10], rdi
0x18002027b  mov     [rsp+58h+arg_8], rbx
0x180020280  lea     r12, [rdi+rbx]
0x180020284  mov     rcx, [r13+r12*8+170h]
0x18002028c  call    SIPolicyFree
0x180020291  lea     r15, [rdi+rbx]
0x180020295  mov     rcx, [r13+r15*8+158h]
0x18002029d  call    SIPolicyFree
0x1800202a2  lea     r14, [rdi+rbx]
0x1800202a6  mov     rcx, [r13+r14*8+118h]
0x1800202ae  call    SIPolicyFree
0x1800202b3  lea     rbp, [rdi+rbx]
0x1800202b7  mov     rcx, [r13+rbp*8+100h]
0x1800202bf  call    SIPolicyFree
0x1800202c4  lea     rsi, [rdi+rbx]
0x1800202c8  mov     rcx, [r13+rsi*8+188h]
0x1800202d0  call    SIPolicyFree
0x1800202d5  add     rdi, rbx
0x1800202d8  mov     rcx, [r13+rdi*8+0D8h]
0x1800202e0  call    SIPolicyFree
0x1800202e5  add     rbx, [rsp+58h+arg_10]
0x1800202ea  mov     rcx, [r13+rbx*8+130h]
0x1800202f2  call    SIPolicyFree
0x1800202f7  mov     qword ptr [r13+r12*8+170h], 0
0x180020303  xor     r12d, r12d
0x180020306  mov     [r13+rbx*8+130h], r12
0x18002030e  mov     rbx, [rsp+58h+arg_8]
0x180020313  inc     rbx
0x180020316  mov     [r13+rdi*8+0D8h], r12
0x18002031e  mov     rdi, [rsp+58h+arg_10]
0x180020323  mov     [r13+r15*8+158h], r12
0x18002032b  mov     [r13+r14*8+118h], r12
0x180020333  mov     [r13+rbp*8+100h], r12
0x18002033b  mov     [r13+rsi*8+188h], r12
0x180020343  mov     [rsp+58h+arg_8], rbx
0x180020348  cmp     rbx, 3
0x18002034c  jnz     loc_180020280
0x180020352  mov     eax, [rsp+58h+arg_0]
0x180020356  inc     eax
0x180020358  mov     [rsp+58h+arg_0], eax
0x18002035c  cmp     eax, 2
0x18002035f  jb      loc_18002026F
0x180020365  mov     rcx, [r13+60h]
0x180020369  test    rcx, rcx
0x18002036c  jz      short loc_180020377
0x18002036e  call    SIPolicyFree
0x180020373  mov     [r13+60h], r12
0x180020377  cmp     [r13+0B8h], r12
0x18002037e  jz      short loc_1800203C7
0x180020380  mov     ebx, r12d
0x180020383  cmp     [r13+0A8h], r12d
0x18002038a  jbe     short loc_1800203B4
0x18002038c  mov     rcx, [r13+0B8h]
0x180020393  mov     eax, ebx
0x180020395  imul    rdx, rax, 0A8h
0x18002039c  mov     rcx, [rdx+rcx+88h]
0x1800203a4  call    SIPolicyFree
0x1800203a9  inc     ebx
0x1800203ab  cmp     ebx, [r13+0A8h]
0x1800203b2  jb      short loc_18002038C
0x1800203b4  mov     rcx, [r13+0B8h]
0x1800203bb  call    SIPolicyFree
0x1800203c0  mov     [r13+0B8h], r12
0x1800203c7  mov     rcx, [r13+0A0h]
0x1800203ce  test    rcx, rcx
0x1800203d1  jz      short loc_1800203DF
0x1800203d3  call    SIPolicyFree
0x1800203d8  mov     [r13+0A0h], r12
0x1800203df  mov     rcx, [r13+68h]
0x1800203e3  test    rcx, rcx
0x1800203e6  jnz     short loc_1800203F4
0x1800203e8  mov     rcx, [r13+88h]
0x1800203ef  test    rcx, rcx
0x1800203f2  jz      short loc_1800203F9
0x1800203f4  call    SIPolicyFree
0x1800203f9  cmp     [r13+298h], r12
0x180020400  jz      short loc_180020466
0x180020402  mov     edi, r12d
0x180020405  cmp     [r13+290h], r12d
0x18002040c  jbe     short loc_18002045A
0x18002040e  mov     eax, edi
0x180020410  lea     rbx, [rax+rax*8]
0x180020414  mov     rax, [r13+298h]
0x18002041b  add     rbx, rbx
0x18002041e  mov     rcx, [rax+rbx*8+20h]
0x180020423  test    rcx, rcx
0x180020426  jz      short loc_18002042D
0x180020428  call    SIPolicyFree
0x18002042d  mov     rax, [r13+298h]
0x180020434  mov     rcx, [rax+rbx*8+68h]
0x180020439  test    rcx, rcx
0x18002043c  jz      short loc_18002044F
0x18002043e  call    SIPolicyFree
0x180020443  mov     rax, [r13+298h]
0x18002044a  mov     [rax+rbx*8+68h], r12
0x18002044f  inc     edi
0x180020451  cmp     edi, [r13+290h]
0x180020458  jb      short loc_18002040E
0x18002045a  mov     rcx, [r13+298h]
0x180020461  call    SIPolicyFree
0x180020466  mov     rcx, [r13+2B8h]
0x18002046d  test    rcx, rcx
0x180020470  jz      short loc_18002047E
0x180020472  call    SIPolicyFree
0x180020477  mov     [r13+2B8h], r12
0x18002047e  mov     rdx, [r13+2F8h]
0x180020485  mov     ecx, [r13+2F0h]
0x18002048c  call    SIPolicyFreeApplicationRegion
0x180020491  lea     rcx, [r13+308h]
0x180020498  call    SIPolicyFreeSIChainInfo
0x18002049d  mov     rcx, r13
0x1800204a0  call    SIPolicyFree
0x1800204a5  mov     rbx, [rsp+58h+arg_18]
0x1800204aa  add     rsp, 20h
0x1800204ae  pop     r15
0x1800204b0  pop     r14
0x1800204b2  pop     r13
0x1800204b4  pop     r12
0x1800204b6  pop     rdi
0x1800204b7  pop     rsi
0x1800204b8  pop     rbp
0x1800204b9  retn
```
