# YReader::GraftAttDefs(_stack<DeclAttDef *,4> *)

- ea: `0x10040b230`
- end: `0x10040b4b8`
- name: `?GraftAttDefs@YReader@@AEAAXPEAV?$_stack@PEAVDeclAttDef@@$03@@@Z`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1004079d0`

## callees

- `0x10040b230`
- `0x10040bfc0`
- `0x10040c7b0`
- `0x1004394f0`

## pseudocode

```c
void __fastcall YReader::GraftAttDefs(__int64 a1, __int64 a2)
{
  __int64 *v3; // rsi
  unsigned __int64 v4; // r12
  __int64 v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // ecx
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // r13
  unsigned __int64 i; // r14
  __int64 v12; // rdi
  unsigned __int64 v13; // rbx
  __int64 v14; // rbp
  YReader *v15; // rcx
  unsigned int v16; // ecx
  __int64 v17; // rcx
  __int64 v18; // rax
  bool v19; // zf
  int v20; // r8d

  v3 = *(__int64 **)(a2 + 16);
  v4 = (unsigned __int64)&v3[*(unsigned int *)(a2 + 24)];
  v5 = *(unsigned int *)(a1 + 2840);
  if ( (_DWORD)v5 )
  {
    v10 = *(_QWORD *)(a1 + 2832);
    for ( i = v10 + 152 * v5; (unsigned __int64)v3 < v4; ++v3 )
    {
      v12 = *v3;
      v13 = v10;
      if ( v10 >= i )
      {
LABEL_16:
        if ( *(_DWORD *)(v12 + 128) && !*(_DWORD *)(v12 + 132) )
        {
          v16 = *(_DWORD *)(a1 + 2840);
          if ( *(_DWORD *)(a1 + 2844) == v16 )
          {
            _stack<Attribute,16>::grow(a1 + 2816);
            v16 = *(_DWORD *)(a1 + 2840);
          }
          *(_DWORD *)(a1 + 2840) = v16 + 1;
          v17 = 152LL * v16;
          v18 = *(_QWORD *)(a1 + 2832);
          *(_OWORD *)(v17 + v18) = *(_OWORD *)(v12 + 32);
          *(_OWORD *)(v17 + v18 + 16) = *(_OWORD *)(v12 + 48);
          *(_OWORD *)(v17 + v18 + 32) = *(_OWORD *)(v12 + 64);
          *(_OWORD *)(v17 + v18 + 48) = *(_OWORD *)(v12 + 80);
          *(_OWORD *)(v17 + v18 + 64) = *(_OWORD *)(v12 + 96);
          *(_OWORD *)(v17 + v18 + 80) = *(_OWORD *)(v12 + 112);
          *(_OWORD *)(v17 + v18 + 96) = *(_OWORD *)(v12 + 128);
          *(_OWORD *)(v17 + v18 + 112) = *(_OWORD *)(v12 + 144);
          *(_OWORD *)(v17 + v18 + 128) = *(_OWORD *)(v12 + 160);
          *(_QWORD *)(v17 + v18 + 144) = *(_QWORD *)(v12 + 176);
        }
      }
      else
      {
        v14 = *(unsigned int *)(v12 + 40);
        while ( (_DWORD)v14 != *(_DWORD *)(v13 + 8) || memcmp(*(const void **)(v12 + 32), *(const void **)v13, 2 * v14) )
        {
          v13 += 152LL;
          if ( v13 >= i )
            goto LABEL_16;
        }
        v19 = *(_QWORD *)(v13 + 104) == 0;
        *(_OWORD *)(v13 + 64) = *(_OWORD *)(v12 + 96);
        v20 = *(_DWORD *)(v12 + 172);
        if ( v19 )
        {
          if ( v20 )
            YReader::NormalizeTypedAttributeValue(v15, (struct StringPtr *)(v13 + 80), v20);
        }
        else
        {
          *(_DWORD *)(v13 + 140) = v20;
        }
      }
    }
  }
  else
  {
    for ( ; (unsigned __int64)v3 < v4; ++v3 )
    {
      v6 = *v3;
      if ( *(_DWORD *)(*v3 + 128) && !*(_DWORD *)(v6 + 132) )
      {
        v7 = *(_DWORD *)(a1 + 2840);
        if ( *(_DWORD *)(a1 + 2844) == v7 )
        {
          _stack<Attribute,16>::grow(a1 + 2816);
          v7 = *(_DWORD *)(a1 + 2840);
        }
        *(_DWORD *)(a1 + 2840) = v7 + 1;
        v8 = 152LL * v7;
        v9 = *(_QWORD *)(a1 + 2832);
        *(_OWORD *)(v8 + v9) = *(_OWORD *)(v6 + 32);
        *(_OWORD *)(v8 + v9 + 16) = *(_OWORD *)(v6 + 48);
        *(_OWORD *)(v8 + v9 + 32) = *(_OWORD *)(v6 + 64);
        *(_OWORD *)(v8 + v9 + 48) = *(_OWORD *)(v6 + 80);
        *(_OWORD *)(v8 + v9 + 64) = *(_OWORD *)(v6 + 96);
        *(_OWORD *)(v8 + v9 + 80) = *(_OWORD *)(v6 + 112);
        *(_OWORD *)(v8 + v9 + 96) = *(_OWORD *)(v6 + 128);
        *(_OWORD *)(v8 + v9 + 112) = *(_OWORD *)(v6 + 144);
        *(_OWORD *)(v8 + v9 + 128) = *(_OWORD *)(v6 + 160);
        *(_QWORD *)(v8 + v9 + 144) = *(_QWORD *)(v6 + 176);
        ++*(_DWORD *)(a1 + 2804);
      }
    }
  }
}

```

## disassembly

```asm
0x10040b230  push    rbx
0x10040b232  push    rsi
0x10040b233  push    rdi
0x10040b234  push    r12
0x10040b236  push    r15
0x10040b238  sub     rsp, 20h
0x10040b23c  mov     eax, [rdx+18h]
0x10040b23f  mov     r15, rcx
0x10040b242  mov     rsi, [rdx+10h]
0x10040b246  lea     r12, [rsi+rax*8]
0x10040b24a  mov     eax, [rcx+0B18h]
0x10040b250  test    eax, eax
0x10040b252  jnz     loc_10040B349
0x10040b258  cmp     rsi, r12
0x10040b25b  jnb     loc_10040B47D
0x10040b261  nop     dword ptr [rax+00h]
0x10040b265  nop     word ptr [rax+rax+00000000h]
0x10040b270  mov     rbx, [rsi]
0x10040b273  cmp     dword ptr [rbx+80h], 0
0x10040b27a  jz      loc_10040B330
0x10040b280  cmp     dword ptr [rbx+84h], 0
0x10040b287  jnz     loc_10040B330
0x10040b28d  lea     rdi, [r15+0B00h]
0x10040b294  mov     ecx, [rdi+18h]
0x10040b297  cmp     [rdi+1Ch], ecx
0x10040b29a  jnz     short loc_10040B2A9
0x10040b29c  xor     edx, edx
0x10040b29e  mov     rcx, rdi
0x10040b2a1  call    ?grow@?$_stack@UAttribute@@$0BA@@@AEAAXI@Z; _stack<Attribute,16>::grow(uint)
0x10040b2a6  mov     ecx, [rdi+18h]
0x10040b2a9  lea     eax, [rcx+1]
0x10040b2ac  mov     [rdi+18h], eax
0x10040b2af  movups  xmm0, xmmword ptr [rbx+20h]
0x10040b2b3  mov     eax, ecx
0x10040b2b5  imul    rcx, rax, 98h
0x10040b2bc  mov     rax, [rdi+10h]
0x10040b2c0  movups  xmmword ptr [rcx+rax], xmm0
0x10040b2c4  movups  xmm1, xmmword ptr [rbx+30h]
0x10040b2c8  movups  xmmword ptr [rcx+rax+10h], xmm1
0x10040b2cd  movups  xmm0, xmmword ptr [rbx+40h]
0x10040b2d1  movups  xmmword ptr [rcx+rax+20h], xmm0
0x10040b2d6  movups  xmm1, xmmword ptr [rbx+50h]
0x10040b2da  movups  xmmword ptr [rcx+rax+30h], xmm1
0x10040b2df  movups  xmm0, xmmword ptr [rbx+60h]
0x10040b2e3  movups  xmmword ptr [rcx+rax+40h], xmm0
0x10040b2e8  movups  xmm1, xmmword ptr [rbx+70h]
0x10040b2ec  movups  xmmword ptr [rcx+rax+50h], xmm1
0x10040b2f1  movups  xmm0, xmmword ptr [rbx+80h]
0x10040b2f8  movups  xmmword ptr [rcx+rax+60h], xmm0
0x10040b2fd  movups  xmm1, xmmword ptr [rbx+90h]
0x10040b304  movups  xmmword ptr [rcx+rax+70h], xmm1
0x10040b309  movups  xmm0, xmmword ptr [rbx+0A0h]
0x10040b310  movups  xmmword ptr [rcx+rax+80h], xmm0
0x10040b318  movsd   xmm1, qword ptr [rbx+0B0h]
0x10040b320  movsd   qword ptr [rcx+rax+90h], xmm1
0x10040b329  inc     dword ptr [r15+0AF4h]
0x10040b330  add     rsi, 8
0x10040b334  cmp     rsi, r12
0x10040b337  jb      loc_10040B270
0x10040b33d  add     rsp, 20h
0x10040b341  pop     r15
0x10040b343  pop     r12
0x10040b345  pop     rdi
0x10040b346  pop     rsi
0x10040b347  pop     rbx
0x10040b348  retn
0x10040b349  mov     [rsp+48h+arg_8], r13
0x10040b34e  mov     r13, [rcx+0B10h]
0x10040b355  mov     [rsp+48h+arg_10], r14
0x10040b35a  imul    r14, rax, 98h
0x10040b361  add     r14, r13
0x10040b364  cmp     rsi, r12
0x10040b367  jnb     loc_10040B473
0x10040b36d  mov     [rsp+48h+arg_0], rbp
0x10040b372  mov     rdi, [rsi]
0x10040b375  mov     rbx, r13
0x10040b378  cmp     r13, r14
0x10040b37b  jnb     short loc_10040B3AB
0x10040b37d  mov     ebp, [rdi+28h]
0x10040b380  cmp     ebp, [rbx+8]
0x10040b383  jnz     short loc_10040B39F
0x10040b385  mov     rdx, [rbx]; Buf2
0x10040b388  mov     r8, rbp
0x10040b38b  mov     rcx, [rdi+20h]; Buf1
0x10040b38f  add     r8, r8; Size
0x10040b392  call    memcmp
0x10040b397  test    eax, eax
0x10040b399  jz      loc_10040B489
0x10040b39f  add     rbx, 98h
0x10040b3a6  cmp     rbx, r14
0x10040b3a9  jb      short loc_10040B380
0x10040b3ab  cmp     dword ptr [rdi+80h], 0
0x10040b3b2  jz      loc_10040B461
0x10040b3b8  cmp     dword ptr [rdi+84h], 0
0x10040b3bf  jnz     loc_10040B461
0x10040b3c5  lea     rbx, [r15+0B00h]
0x10040b3cc  mov     ecx, [rbx+18h]
0x10040b3cf  cmp     [rbx+1Ch], ecx
0x10040b3d2  jnz     short loc_10040B3E1
0x10040b3d4  xor     edx, edx
0x10040b3d6  mov     rcx, rbx
0x10040b3d9  call    ?grow@?$_stack@UAttribute@@$0BA@@@AEAAXI@Z; _stack<Attribute,16>::grow(uint)
0x10040b3de  mov     ecx, [rbx+18h]
0x10040b3e1  lea     eax, [rcx+1]
0x10040b3e4  mov     [rbx+18h], eax
0x10040b3e7  movups  xmm0, xmmword ptr [rdi+20h]
0x10040b3eb  mov     eax, ecx
0x10040b3ed  imul    rcx, rax, 98h
0x10040b3f4  mov     rax, [rbx+10h]
0x10040b3f8  movups  xmmword ptr [rcx+rax], xmm0
0x10040b3fc  movups  xmm1, xmmword ptr [rdi+30h]
0x10040b400  movups  xmmword ptr [rcx+rax+10h], xmm1
0x10040b405  movups  xmm0, xmmword ptr [rdi+40h]
0x10040b409  movups  xmmword ptr [rcx+rax+20h], xmm0
0x10040b40e  movups  xmm1, xmmword ptr [rdi+50h]
0x10040b412  movups  xmmword ptr [rcx+rax+30h], xmm1
0x10040b417  movups  xmm0, xmmword ptr [rdi+60h]
0x10040b41b  movups  xmmword ptr [rcx+rax+40h], xmm0
0x10040b420  movups  xmm1, xmmword ptr [rdi+70h]
0x10040b424  movups  xmmword ptr [rcx+rax+50h], xmm1
0x10040b429  movups  xmm0, xmmword ptr [rdi+80h]
0x10040b430  movups  xmmword ptr [rcx+rax+60h], xmm0
0x10040b435  movups  xmm1, xmmword ptr [rdi+90h]
0x10040b43c  movups  xmmword ptr [rcx+rax+70h], xmm1
0x10040b441  movups  xmm0, xmmword ptr [rdi+0A0h]
0x10040b448  movups  xmmword ptr [rcx+rax+80h], xmm0
0x10040b450  movsd   xmm1, qword ptr [rdi+0B0h]
0x10040b458  movsd   qword ptr [rcx+rax+90h], xmm1
0x10040b461  add     rsi, 8
0x10040b465  cmp     rsi, r12
0x10040b468  jb      loc_10040B372
0x10040b46e  mov     rbp, [rsp+48h+arg_0]
0x10040b473  mov     r13, [rsp+48h+arg_8]
0x10040b478  mov     r14, [rsp+48h+arg_10]
0x10040b47d  add     rsp, 20h
0x10040b481  pop     r15
0x10040b483  pop     r12
0x10040b485  pop     rdi
0x10040b486  pop     rsi
0x10040b487  pop     rbx
0x10040b488  retn
0x10040b489  cmp     qword ptr [rbx+68h], 0
0x10040b48e  movups  xmm0, xmmword ptr [rdi+60h]
0x10040b492  movups  xmmword ptr [rbx+40h], xmm0
0x10040b496  mov     r8d, [rdi+0ACh]; int
0x10040b49d  jz      short loc_10040B4A8
0x10040b49f  mov     [rbx+8Ch], r8d
0x10040b4a6  jmp     short loc_10040B461
0x10040b4a8  test    r8d, r8d
0x10040b4ab  jz      short loc_10040B461
0x10040b4ad  lea     rdx, [rbx+50h]; struct StringPtr *
0x10040b4b1  call    ?NormalizeTypedAttributeValue@YReader@@AEAAXPEAUStringPtr@@H@Z; YReader::NormalizeTypedAttributeValue(StringPtr *,int)
0x10040b4b6  jmp     short loc_10040B461
```
