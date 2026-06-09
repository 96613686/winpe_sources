# VsmmVaGpaCorepCommitFinalize

- ea: `0x1400eb1a8`
- end: `0x1400eb50d`
- name: `VsmmVaGpaCorepCommitFinalize`
- size: `869`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400eabac`

## callees

- `0x1400e6030`
- `0x1400eb1a8`
- `0x1400eb720`
- `0x1400eb740`
- `0x1400ec68c`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400eb27b`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400eb311`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400eb27b`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400eb311`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400eb3ec`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400eb447`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400eb3ec`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400eb447`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eb419`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eb419`
- `winhvr!WinHvUncommitGpaPages` at `0x1400eb393`
- `winhvr!WinHvUncommitGpaPages` at `0x1400eb393`

## pseudocode

```c
void __fastcall VsmmVaGpaCorepCommitFinalize(__int64 a1, _QWORD **a2, _QWORD **a3)
{
  _QWORD **v3; // r15
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  _QWORD *v8; // rbp
  unsigned __int64 v9; // rbx
  int v10; // esi
  unsigned __int64 v11; // rax
  __int64 v12; // rbp
  __int64 v13; // rdi
  unsigned __int64 v14; // rbx
  int v15; // esi
  unsigned __int64 v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rbx
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rdi
  int v25; // eax
  __int64 v26; // rsi
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // [rsp+80h] [rbp+18h] BYREF

  v3 = a3;
  if ( a3 )
  {
    while ( 1 )
    {
      v6 = *v3;
      if ( *v3 == v3 )
        goto LABEL_31;
      if ( (_QWORD **)v6[1] != v3 || (v7 = (_QWORD *)*v6, *(_QWORD **)(*v6 + 8LL) != v6) )
LABEL_61:
        __fastfail(3u);
      *v3 = v7;
      v8 = v6 - 5;
      v7[1] = v3;
      v6[1] = 0;
      *v6 = 0;
      v9 = *(_QWORD *)(a1 + 10824);
      if ( (*(_BYTE *)(a1 + 10832) & 1) != 0 && v9 )
        v9 ^= a1 + 10824;
      LOBYTE(a3) = 0;
      v10 = *(_BYTE *)(a1 + 10832) & 1;
      if ( !v9 )
        goto LABEL_16;
      while ( 1 )
      {
        if ( (int)VsmmVaGpaCorepGpnCompareFunctionByPage(v8 + 7, v9, a3) >= 0 )
        {
          v11 = *(_QWORD *)(v9 + 8);
          if ( v10 )
          {
            if ( !v11 )
            {
LABEL_15:
              LOBYTE(a3) = 1;
              goto LABEL_16;
            }
            v11 ^= v9;
          }
          if ( !v11 )
            goto LABEL_15;
          goto LABEL_10;
        }
        v11 = *(_QWORD *)v9;
        if ( v10 )
          break;
LABEL_12:
        if ( !v11 )
          goto LABEL_46;
LABEL_10:
        v9 = v11;
      }
      if ( v11 )
        break;
LABEL_46:
      LOBYTE(a3) = 0;
LABEL_16:
      RtlRbInsertNodeEx(a1 + 10824, v9, a3, v8);
      if ( (v8[12] & 4) != 0 )
        ++*(_QWORD *)(a1 + 10856);
      v12 = v8[10];
      if ( *(_QWORD *)(v12 + 16) == -1 )
      {
        v13 = *(_QWORD *)(v12 + 24) + 64LL;
        v14 = *(_QWORD *)v13;
        if ( (*(_BYTE *)(*(_QWORD *)(v12 + 24) + 72LL) & 1) != 0 )
        {
          if ( v14 )
            v14 ^= v13;
        }
        LOBYTE(a3) = 0;
        v15 = *(_BYTE *)(*(_QWORD *)(v12 + 24) + 72LL) & 1;
        if ( v14 )
        {
          while ( 1 )
          {
            if ( (int)VsmmVaGpaCorepVpnCompareFunctionByPage(v12 + 32, v14, a3) < 0 )
            {
              v16 = *(_QWORD *)v14;
              if ( v15 )
              {
                if ( !v16 )
                {
LABEL_48:
                  LOBYTE(a3) = 0;
                  break;
                }
                v16 ^= v14;
              }
              if ( !v16 )
                goto LABEL_48;
            }
            else
            {
              v16 = *(_QWORD *)(v14 + 8);
              if ( v15 )
              {
                if ( !v16 )
                {
LABEL_29:
                  LOBYTE(a3) = 1;
                  break;
                }
                v16 ^= v14;
              }
              if ( !v16 )
                goto LABEL_29;
            }
            v14 = v16;
          }
        }
        RtlRbInsertNodeEx(v13, v14, a3, v12);
      }
    }
    v11 ^= v9;
    goto LABEL_12;
  }
LABEL_31:
  if ( a2 )
  {
    while ( 1 )
    {
      v17 = *a2;
      if ( *a2 == a2 )
        return;
      if ( (_QWORD **)v17[1] != a2 )
        goto LABEL_61;
      v18 = (_QWORD *)*v17;
      if ( *(_QWORD **)(*v17 + 8LL) != v17 )
        goto LABEL_61;
      *a2 = v18;
      v19 = v17 - 5;
      v18[1] = a2;
      v17[1] = 0;
      *v17 = 0;
      v20 = *(_QWORD *)(a1 + 648);
      v29 = 0;
      WinHvUncommitGpaPages(v20, v17[2], v17[3] - v17[2] + 1LL, &v29);
      v21 = v19 + 3;
      v22 = v19[3];
      if ( *(_QWORD **)(v22 + 8) != v19 + 3 )
        goto LABEL_61;
      v23 = (_QWORD *)v19[4];
      if ( (_QWORD *)*v23 != v21 )
        goto LABEL_61;
      v24 = v19[10];
      *v23 = v22;
      *(_QWORD *)(v22 + 8) = v23;
      *v21 = 0;
      v19[4] = 0;
      v19[10] = 0;
      --*(_DWORD *)(v24 + 64);
      RtlRbRemoveNode(a1 + 10824, v19);
      v25 = *((_DWORD *)v19 + 24);
      v19[2] = -1;
      if ( (v25 & 4) != 0 )
        --*(_QWORD *)(a1 + 10856);
      if ( !*(_DWORD *)(v24 + 64) )
        break;
LABEL_40:
      ExFreePoolWithTag(v19, 0x6D4D6456u);
    }
    RtlRbRemoveNode(*(_QWORD *)(v24 + 24) + 64LL, v24);
    v26 = *(_QWORD *)(v24 + 24);
    *(_QWORD *)(v24 + 16) = -1;
    VsmmVaGpaCorepFreeRanges(v27, v24);
    v28 = *(_QWORD *)(v26 + 64);
    if ( (*(_BYTE *)(v26 + 72) & 1) != 0 )
    {
      if ( !v28 )
      {
LABEL_44:
        VsmmVaGpaCorepProcessContextTeardown(a1, v26);
        goto LABEL_40;
      }
      v28 ^= v26 + 64;
    }
    if ( v28 )
      goto LABEL_40;
    goto LABEL_44;
  }
}

```

## disassembly

```asm
0x1400eb1a8  push    rbx
0x1400eb1aa  push    rbp
0x1400eb1ab  push    rsi
0x1400eb1ac  push    rdi
0x1400eb1ad  push    r12
0x1400eb1af  push    r13
0x1400eb1b1  push    r14
0x1400eb1b3  push    r15
0x1400eb1b5  sub     rsp, 28h
0x1400eb1b9  mov     r15, r8
0x1400eb1bc  mov     r13, rdx
0x1400eb1bf  mov     r14, rcx
0x1400eb1c2  test    r8, r8
0x1400eb1c5  jz      loc_1400EB322
0x1400eb1cb  mov     rax, [r15]
0x1400eb1ce  cmp     rax, r15
0x1400eb1d1  jz      loc_1400EB322
0x1400eb1d7  cmp     [rax+8], r15
0x1400eb1db  jnz     loc_1400EB506
0x1400eb1e1  mov     rcx, [rax]
0x1400eb1e4  cmp     [rcx+8], rax
0x1400eb1e8  jnz     loc_1400EB506
0x1400eb1ee  mov     [r15], rcx
0x1400eb1f1  lea     rbp, [rax-28h]
0x1400eb1f5  mov     [rcx+8], r15
0x1400eb1f9  lea     rdi, [r14+2A48h]
0x1400eb200  mov     qword ptr [rbp+30h], 0
0x1400eb208  mov     qword ptr [rax], 0
0x1400eb20f  test    byte ptr [r14+2A50h], 1
0x1400eb217  mov     rbx, [rdi]
0x1400eb21a  jnz     loc_1400EB4A0
0x1400eb220  movzx   esi, byte ptr [rdi+8]
0x1400eb224  xor     r8b, r8b
0x1400eb227  and     esi, 1
0x1400eb22a  test    rbx, rbx
0x1400eb22d  jz      short loc_1400EB272
0x1400eb22f  mov     rdx, rbx
0x1400eb232  lea     rcx, [rbp+38h]
0x1400eb236  call    VsmmVaGpaCorepGpnCompareFunctionByPage
0x1400eb23b  test    eax, eax
0x1400eb23d  js      short loc_1400EB251
0x1400eb23f  mov     rax, [rbx+8]
0x1400eb243  test    esi, esi
0x1400eb245  jnz     short loc_1400EB266
0x1400eb247  test    rax, rax
0x1400eb24a  jz      short loc_1400EB26F
0x1400eb24c  mov     rbx, rax
0x1400eb24f  jmp     short loc_1400EB22F
0x1400eb251  mov     rax, [rbx]
0x1400eb254  test    esi, esi
0x1400eb256  jnz     loc_1400EB486
0x1400eb25c  test    rax, rax
0x1400eb25f  jnz     short loc_1400EB24C
0x1400eb261  jmp     loc_1400EB48B
0x1400eb266  test    rax, rax
0x1400eb269  jnz     loc_1400EB4CE
0x1400eb26f  mov     r8b, 1
0x1400eb272  mov     r9, rbp
0x1400eb275  mov     rdx, rbx
0x1400eb278  mov     rcx, rdi
0x1400eb27b  call    cs:__imp_RtlRbInsertNodeEx
0x1400eb282  nop     dword ptr [rax+rax+00h]
0x1400eb287  mov     eax, [rbp+60h]
0x1400eb28a  test    al, 4
0x1400eb28c  jnz     loc_1400EB4DE
0x1400eb292  mov     rbp, [rbp+50h]
0x1400eb296  cmp     qword ptr [rbp+10h], 0FFFFFFFFFFFFFFFFh
0x1400eb29b  jnz     loc_1400EB1CB
0x1400eb2a1  mov     rdi, [rbp+18h]
0x1400eb2a5  add     rdi, 40h ; '@'
0x1400eb2a9  test    byte ptr [rdi+8], 1
0x1400eb2ad  mov     rbx, [rdi]
0x1400eb2b0  jnz     loc_1400EB4AA
0x1400eb2b6  movzx   esi, byte ptr [rdi+8]
0x1400eb2ba  xor     r8b, r8b
0x1400eb2bd  and     esi, 1
0x1400eb2c0  test    rbx, rbx
0x1400eb2c3  jz      short loc_1400EB308
0x1400eb2c5  mov     rdx, rbx
0x1400eb2c8  lea     rcx, [rbp+20h]
0x1400eb2cc  call    VsmmVaGpaCorepVpnCompareFunctionByPage
0x1400eb2d1  test    eax, eax
0x1400eb2d3  js      short loc_1400EB2E7
0x1400eb2d5  mov     rax, [rbx+8]
0x1400eb2d9  test    esi, esi
0x1400eb2db  jnz     short loc_1400EB2FC
0x1400eb2dd  test    rax, rax
0x1400eb2e0  jz      short loc_1400EB305
0x1400eb2e2  mov     rbx, rax
0x1400eb2e5  jmp     short loc_1400EB2C5
0x1400eb2e7  mov     rax, [rbx]
0x1400eb2ea  test    esi, esi
0x1400eb2ec  jnz     loc_1400EB493
0x1400eb2f2  test    rax, rax
0x1400eb2f5  jnz     short loc_1400EB2E2
0x1400eb2f7  jmp     loc_1400EB498
0x1400eb2fc  test    rax, rax
0x1400eb2ff  jnz     loc_1400EB4EA
0x1400eb305  mov     r8b, 1
0x1400eb308  mov     r9, rbp
0x1400eb30b  mov     rdx, rbx
0x1400eb30e  mov     rcx, rdi
0x1400eb311  call    cs:__imp_RtlRbInsertNodeEx
0x1400eb318  nop     dword ptr [rax+rax+00h]
0x1400eb31d  jmp     loc_1400EB1CB
0x1400eb322  test    r13, r13
0x1400eb325  jz      loc_1400EB42A
0x1400eb32b  mov     rax, [r13+0]
0x1400eb32f  cmp     rax, r13
0x1400eb332  jz      loc_1400EB42A
0x1400eb338  cmp     [rax+8], r13
0x1400eb33c  jnz     loc_1400EB506
0x1400eb342  mov     rcx, [rax]
0x1400eb345  cmp     [rcx+8], rax
0x1400eb349  jnz     loc_1400EB506
0x1400eb34f  mov     [r13+0], rcx
0x1400eb353  lea     rbx, [rax-28h]
0x1400eb357  mov     [rcx+8], r13
0x1400eb35b  lea     r9, [rsp+68h+arg_10]
0x1400eb363  mov     qword ptr [rbx+30h], 0
0x1400eb36b  mov     qword ptr [rax], 0
0x1400eb372  mov     rcx, [r14+288h]
0x1400eb379  mov     [rsp+68h+arg_10], 0
0x1400eb385  mov     rdx, [rbx+38h]
0x1400eb389  mov     r8, [rbx+40h]
0x1400eb38d  sub     r8, rdx
0x1400eb390  inc     r8
0x1400eb393  call    cs:__imp_WinHvUncommitGpaPages
0x1400eb39a  nop     dword ptr [rax+rax+00h]
0x1400eb39f  lea     rcx, [rbx+18h]
0x1400eb3a3  mov     rdx, [rcx]
0x1400eb3a6  cmp     [rdx+8], rcx
0x1400eb3aa  jnz     loc_1400EB506
0x1400eb3b0  mov     rax, [rbx+20h]
0x1400eb3b4  cmp     [rax], rcx
0x1400eb3b7  jnz     loc_1400EB506
0x1400eb3bd  mov     rdi, [rbx+50h]
0x1400eb3c1  mov     [rax], rdx
0x1400eb3c4  mov     [rdx+8], rax
0x1400eb3c8  mov     rdx, rbx
0x1400eb3cb  mov     qword ptr [rcx], 0
0x1400eb3d2  lea     rcx, [r14+2A48h]
0x1400eb3d9  mov     qword ptr [rbx+20h], 0
0x1400eb3e1  mov     qword ptr [rbx+50h], 0
0x1400eb3e9  dec     dword ptr [rdi+40h]
0x1400eb3ec  call    cs:__imp_RtlRbRemoveNode
0x1400eb3f3  nop     dword ptr [rax+rax+00h]
0x1400eb3f8  mov     eax, [rbx+60h]
0x1400eb3fb  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1400eb403  test    al, 4
0x1400eb405  jnz     loc_1400EB4FA
0x1400eb40b  cmp     dword ptr [rdi+40h], 0
0x1400eb40f  jz      short loc_1400EB43C
0x1400eb411  mov     edx, 6D4D6456h; Tag
0x1400eb416  mov     rcx, rbx; P
0x1400eb419  call    cs:__imp_ExFreePoolWithTag
0x1400eb420  nop     dword ptr [rax+rax+00h]
0x1400eb425  jmp     loc_1400EB32B
0x1400eb42a  add     rsp, 28h
0x1400eb42e  pop     r15
0x1400eb430  pop     r14
0x1400eb432  pop     r13
0x1400eb434  pop     r12
0x1400eb436  pop     rdi
0x1400eb437  pop     rsi
0x1400eb438  pop     rbp
0x1400eb439  pop     rbx
0x1400eb43a  retn
0x1400eb43c  mov     rcx, [rdi+18h]
0x1400eb440  mov     rdx, rdi
0x1400eb443  add     rcx, 40h ; '@'
0x1400eb447  call    cs:__imp_RtlRbRemoveNode
0x1400eb44e  nop     dword ptr [rax+rax+00h]
0x1400eb453  mov     rsi, [rdi+18h]
0x1400eb457  mov     rdx, rdi
0x1400eb45a  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x1400eb462  call    VsmmVaGpaCorepFreeRanges
0x1400eb467  test    byte ptr [rsi+48h], 1
0x1400eb46b  lea     rcx, [rsi+40h]
0x1400eb46f  mov     rax, [rcx]
0x1400eb472  jnz     short loc_1400EB4C4
0x1400eb474  test    rax, rax
0x1400eb477  jnz     short loc_1400EB411
0x1400eb479  mov     rdx, rsi
0x1400eb47c  mov     rcx, r14
0x1400eb47f  call    VsmmVaGpaCorepProcessContextTeardown
0x1400eb484  jmp     short loc_1400EB411
0x1400eb486  test    rax, rax
0x1400eb489  jnz     short loc_1400EB4D6
0x1400eb48b  xor     r8b, r8b
0x1400eb48e  jmp     loc_1400EB272
0x1400eb493  test    rax, rax
0x1400eb496  jnz     short loc_1400EB4F2
0x1400eb498  xor     r8b, r8b
0x1400eb49b  jmp     loc_1400EB308
0x1400eb4a0  test    rbx, rbx
0x1400eb4a3  jnz     short loc_1400EB4B7
0x1400eb4a5  jmp     loc_1400EB220
0x1400eb4aa  test    rbx, rbx
0x1400eb4ad  jz      short loc_1400EB4BF
0x1400eb4af  xor     rbx, rdi
0x1400eb4b2  jmp     loc_1400EB2B6
0x1400eb4b7  xor     rbx, rdi
0x1400eb4ba  jmp     loc_1400EB220
0x1400eb4bf  jmp     loc_1400EB2B6
0x1400eb4c4  test    rax, rax
0x1400eb4c7  jz      short loc_1400EB479
0x1400eb4c9  xor     rax, rcx
0x1400eb4cc  jmp     short loc_1400EB474
0x1400eb4ce  xor     rax, rbx
0x1400eb4d1  jmp     loc_1400EB247
0x1400eb4d6  xor     rax, rbx
0x1400eb4d9  jmp     loc_1400EB25C
0x1400eb4de  inc     qword ptr [r14+2A68h]
0x1400eb4e5  jmp     loc_1400EB292
0x1400eb4ea  xor     rax, rbx
0x1400eb4ed  jmp     loc_1400EB2DD
0x1400eb4f2  xor     rax, rbx
0x1400eb4f5  jmp     loc_1400EB2F2
0x1400eb4fa  dec     qword ptr [r14+2A68h]
0x1400eb501  jmp     loc_1400EB40B
0x1400eb506  mov     ecx, 3
0x1400eb50b  int     29h; Win8: RtlFailFast(ecx)
```
