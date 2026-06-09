# MTX_AHUFF_Create

- ea: `0x1800067cc`
- end: `0x180006a25`
- name: `MTX_AHUFF_Create`
- size: `601`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006548`
- `0x18000e2d4`

## callees

- `0x180006400`
- `0x1800067cc`
- `0x180007dc0`
- `0x180008780`
- `0x18001a640`
- `0x18001c9ec`

## pseudocode

```c
__int64 __fastcall MTX_AHUFF_Create(__int64 a1, __int64 a2, __int16 a3)
{
  __int64 v4; // rsi
  int v6; // r14d
  __int64 v7; // rdi
  __int64 v8; // rax
  int v9; // ebp
  __int16 v10; // r8
  __int64 v11; // rax
  __int16 v12; // cx
  __int64 v13; // rdx
  __int16 v14; // r8
  __int64 v15; // rax
  __int16 v16; // dx
  __int64 v17; // rcx
  __int16 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int16 i; // bx
  __int16 v23; // bx
  __int16 v24; // bx

  v4 = a3;
  v6 = a3 - 1;
  v7 = MTX_mem_malloc(a1, 64);
  *(_QWORD *)(v7 + 32) = a2;
  *(_DWORD *)(v7 + 24) = v4;
  *(_QWORD *)(v7 + 40) = a1;
  *(_DWORD *)(v7 + 16) = MTX_AHUFF_BitsUsed((unsigned int)(v4 - 1));
  *(_DWORD *)(v7 + 20) = 0;
  if ( (unsigned __int16)(v4 - 257) <= 0xFEu )
    *(_DWORD *)(v7 + 20) = MTX_AHUFF_BitsUsed((unsigned int)(v4 - 257)) + 1;
  *(_DWORD *)(v7 + 48) = v6;
  *(_DWORD *)(v7 + 52) = 100;
  *(_QWORD *)(v7 + 56) = 100;
  *(_QWORD *)(v7 + 8) = MTX_mem_malloc(a1, (unsigned int)(2 * v4));
  v8 = MTX_mem_malloc(a1, (unsigned int)(24 * v4));
  v9 = 2;
  *(_QWORD *)v7 = v8;
  v10 = 2;
  if ( (__int16)(2 * v4) > 2 )
  {
    do
    {
      v11 = (unsigned __int16)v10;
      v12 = (unsigned __int16)v10++ >> 1;
      v13 = 3 * v11;
      *(_WORD *)(*(_QWORD *)v7 + 4 * v13) = v12;
      *(_DWORD *)(*(_QWORD *)v7 + 4 * v13 + 8) = 1;
    }
    while ( v10 < (__int16)(2 * v4) );
  }
  v14 = 1;
  if ( (__int16)v4 <= 1 )
  {
    v18 = 0;
    if ( (__int16)v4 <= 0 )
      goto LABEL_9;
  }
  else
  {
    do
    {
      v15 = (unsigned __int16)v14;
      v16 = 2 * v14++;
      v17 = 3 * v15;
      *(_WORD *)(*(_QWORD *)v7 + 4 * v17 + 2) = v16;
      *(_WORD *)(*(_QWORD *)v7 + 4 * v17 + 4) = v16 + 1;
    }
    while ( v14 < (__int16)v4 );
    v18 = 0;
  }
  do
  {
    v19 = v18;
    *(_WORD *)(*(_QWORD *)v7 + 12LL * v18 + 6) = -1;
    v20 = 3LL * ((int)v4 + v18);
    *(_WORD *)(*(_QWORD *)v7 + 4 * v20 + 6) = v18;
    *(_WORD *)(*(_QWORD *)v7 + 4 * v20 + 2) = -1;
    *(_WORD *)(*(_QWORD *)v7 + 4 * v20 + 4) = -1;
    LOWORD(v20) = v4 + v18++;
    *(_WORD *)(*(_QWORD *)(v7 + 8) + 2 * v19) = v20;
  }
  while ( v18 < (__int16)v4 );
LABEL_9:
  init_weight(v7, 1);
  if ( *(_DWORD *)(v7 + 20) )
  {
    UpdateWeight(v7, *(unsigned __int16 *)(*(_QWORD *)(v7 + 8) + 512LL));
    UpdateWeight(v7, *(unsigned __int16 *)(*(_QWORD *)(v7 + 8) + 514LL));
    if ( (__int16)v4 <= 258 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v23 = 12;
    do
    {
      UpdateWeight(v7, *(unsigned __int16 *)(*(_QWORD *)(v7 + 8) + 2 * v4 - 6));
      --v23;
    }
    while ( v23 );
    v24 = 6;
    do
    {
      UpdateWeight(v7, *(unsigned __int16 *)(*(_QWORD *)(v7 + 8) + 2 * v4 - 4));
      --v24;
    }
    while ( v24 );
  }
  else
  {
    do
    {
      for ( i = 0; i < (__int16)v4; ++i )
        UpdateWeight(v7, *(unsigned __int16 *)(*(_QWORD *)(v7 + 8) + 2LL * (unsigned __int16)i));
      --v9;
    }
    while ( v9 );
  }
  *(_QWORD *)(v7 + 52) = 0;
  return v7;
}

```

## disassembly

```asm
0x1800067cc  push    rbx
0x1800067ce  push    rbp
0x1800067cf  push    rsi
0x1800067d0  push    rdi
0x1800067d1  push    r12
0x1800067d3  push    r14
0x1800067d5  sub     rsp, 28h
0x1800067d9  mov     rbx, rdx
0x1800067dc  movsx   rsi, r8w
0x1800067e0  mov     edx, 40h ; '@'
0x1800067e5  mov     rbp, rcx
0x1800067e8  call    MTX_mem_malloc
0x1800067ed  lea     r14d, [rsi-1]
0x1800067f1  mov     rdi, rax
0x1800067f4  mov     ecx, r14d
0x1800067f7  mov     [rax+20h], rbx
0x1800067fb  mov     rbx, rsi
0x1800067fe  mov     [rax+18h], ebx
0x180006801  mov     [rax+28h], rbp
0x180006805  call    MTX_AHUFF_BitsUsed
0x18000680a  mov     edx, 101h
0x18000680f  mov     [rdi+10h], eax
0x180006812  movzx   eax, si
0x180006815  mov     dword ptr [rdi+14h], 0
0x18000681c  sub     ax, dx
0x18000681f  mov     r12d, 1
0x180006825  lea     ecx, [rdx-3]
0x180006828  cmp     ax, cx
0x18000682b  jbe     loc_180006A0A
0x180006831  mov     eax, 64h ; 'd'
0x180006836  mov     [rdi+30h], r14d
0x18000683a  lea     edx, [rsi+rsi]
0x18000683d  mov     [rdi+34h], eax
0x180006840  mov     rcx, rbp
0x180006843  mov     qword ptr [rdi+38h], 64h ; 'd'
0x18000684b  call    MTX_mem_malloc
0x180006850  lea     edx, [rsi+rsi*2]
0x180006853  mov     [rdi+8], rax
0x180006857  shl     edx, 3
0x18000685a  mov     rcx, rbp
0x18000685d  call    MTX_mem_malloc
0x180006862  mov     ebp, 2
0x180006867  mov     [rdi], rax
0x18000686a  movzx   r9d, si
0x18000686e  movzx   r8d, bp
0x180006872  add     r9w, r9w
0x180006876  cmp     bp, r9w
0x18000687a  jge     short loc_1800068A4
0x18000687c  movzx   eax, r8w
0x180006880  movzx   ecx, r8w
0x180006884  shr     cx, 1
0x180006887  add     r8w, r12w
0x18000688b  lea     rdx, [rax+rax*2]
0x18000688f  mov     rax, [rdi]
0x180006892  mov     [rax+rdx*4], cx
0x180006896  mov     rax, [rdi]
0x180006899  mov     [rax+rdx*4+8], r12d
0x18000689e  cmp     r8w, r9w
0x1800068a2  jl      short loc_18000687C
0x1800068a4  or      r14d, 0FFFFFFFFh
0x1800068a8  movzx   r8d, r12w
0x1800068ac  cmp     r12w, si
0x1800068b0  jge     loc_1800069F6
0x1800068b6  movzx   eax, r8w
0x1800068ba  movzx   edx, r8w
0x1800068be  add     dx, dx
0x1800068c1  add     r8w, r12w
0x1800068c5  lea     rcx, [rax+rax*2]
0x1800068c9  mov     rax, [rdi]
0x1800068cc  mov     [rax+rcx*4+2], dx
0x1800068d1  add     dx, r12w
0x1800068d5  mov     rax, [rdi]
0x1800068d8  mov     [rax+rcx*4+4], dx
0x1800068dd  cmp     r8w, si
0x1800068e1  jl      short loc_1800068B6
0x1800068e3  xor     r8d, r8d
0x1800068e6  mov     rax, [rdi]
0x1800068e9  movsx   rdx, r8w
0x1800068ed  lea     rcx, [rdx+rdx*2]
0x1800068f1  mov     [rax+rcx*4+6], r14w
0x1800068f7  movsx   eax, r8w
0x1800068fb  add     eax, ebx
0x1800068fd  cdqe
0x1800068ff  lea     rcx, [rax+rax*2]
0x180006903  mov     rax, [rdi]
0x180006906  mov     [rax+rcx*4+6], r8w
0x18000690c  mov     rax, [rdi]
0x18000690f  mov     [rax+rcx*4+2], r14w
0x180006915  mov     rax, [rdi]
0x180006918  mov     [rax+rcx*4+4], r14w
0x18000691e  lea     ecx, [rsi+r8]
0x180006922  mov     rax, [rdi+8]
0x180006926  add     r8w, r12w
0x18000692a  mov     [rax+rdx*2], cx
0x18000692e  cmp     r8w, si
0x180006932  jl      short loc_1800068E6
0x180006934  mov     edx, r12d
0x180006937  mov     rcx, rdi
0x18000693a  call    init_weight
0x18000693f  cmp     dword ptr [rdi+14h], 0
0x180006943  jnz     short loc_180006989
0x180006945  xor     ebx, ebx
0x180006947  xor     eax, eax
0x180006949  cmp     ax, si
0x18000694c  jl      short loc_18000696B
0x18000694e  sub     ebp, r12d
0x180006951  jnz     short loc_180006945
0x180006953  mov     qword ptr [rdi+34h], 0
0x18000695b  mov     rax, rdi
0x18000695e  add     rsp, 28h
0x180006962  pop     r14
0x180006964  pop     r12
0x180006966  pop     rdi
0x180006967  pop     rsi
0x180006968  pop     rbp
0x180006969  pop     rbx
0x18000696a  retn
0x18000696b  mov     rdx, [rdi+8]
0x18000696f  mov     rcx, rdi
0x180006972  movzx   eax, bx
0x180006975  movzx   edx, word ptr [rdx+rax*2]
0x180006979  call    UpdateWeight
0x18000697e  add     bx, r12w
0x180006982  cmp     bx, si
0x180006985  jge     short loc_18000694E
0x180006987  jmp     short loc_18000696B
0x180006989  mov     rdx, [rdi+8]
0x18000698d  mov     rcx, rdi
0x180006990  movzx   edx, word ptr [rdx+200h]
0x180006997  call    UpdateWeight
0x18000699c  mov     rdx, [rdi+8]
0x1800069a0  mov     rcx, rdi
0x1800069a3  movzx   edx, word ptr [rdx+202h]
0x1800069aa  call    UpdateWeight
0x1800069af  mov     eax, 102h
0x1800069b4  cmp     ax, si
0x1800069b7  jge     short loc_180006A1E
0x1800069b9  mov     ebx, 0Ch
0x1800069be  mov     rdx, [rdi+8]
0x1800069c2  mov     rcx, rdi
0x1800069c5  movzx   edx, word ptr [rdx+rsi*2-6]
0x1800069ca  call    UpdateWeight
0x1800069cf  add     bx, r14w
0x1800069d3  jnz     short loc_1800069BE
0x1800069d5  mov     ebx, 6
0x1800069da  mov     rdx, [rdi+8]
0x1800069de  mov     rcx, rdi
0x1800069e1  movzx   edx, word ptr [rdx+rsi*2-4]
0x1800069e6  call    UpdateWeight
0x1800069eb  add     bx, r14w
0x1800069ef  jnz     short loc_1800069DA
0x1800069f1  jmp     loc_180006953
0x1800069f6  xor     eax, eax
0x1800069f8  movzx   r8d, ax
0x1800069fc  cmp     ax, si
0x1800069ff  jl      loc_1800068E6
0x180006a05  jmp     loc_180006934
0x180006a0a  mov     ecx, esi
0x180006a0c  sub     ecx, edx
0x180006a0e  call    MTX_AHUFF_BitsUsed
0x180006a13  add     eax, r12d
0x180006a16  mov     [rdi+14h], eax
0x180006a19  jmp     loc_180006831
0x180006a1e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006a23  jmp     short loc_1800069B9
```
