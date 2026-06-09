# MTX_LZCOMP_UnPackMemory

- ea: `0x180006548`
- end: `0x18000674f`
- name: `MTX_LZCOMP_UnPackMemory`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000de70`

## callees

- `0x180006400`
- `0x180006548`
- `0x180006760`
- `0x1800067cc`
- `0x180006a2c`
- `0x1800088a0`
- `0x180009c80`
- `0x18000e788`
- `0x18000e7d4`
- `0x18001c9ec`
- `0x18001ce2c`

## pseudocode

```c
__int64 __fastcall MTX_LZCOMP_UnPackMemory(__int64 a1, __int64 a2, unsigned int a3, int *a4, char a5)
{
  _QWORD *v6; // rsi
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rax
  __int16 v16; // ax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r14
  __int64 v20; // rdx
  int i; // ebp
  unsigned int v22; // ebx
  __int16 v23; // ax
  __int64 v24; // rdx
  int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rsi
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx

  v6 = (_QWORD *)(a1 + 144);
  if ( *(_QWORD *)a1 )
    DiscardPointer(*v6, *(_QWORD *)a1, 1);
  v10 = *v6;
  v11 = *v6;
  *(_QWORD *)a1 = 0;
  v12 = MTX_mem_malloc(v11, 16);
  LOBYTE(v13) = 114;
  *(_QWORD *)(v12 + 8) = v10;
  *(_BYTE *)(v12 + 2) = 100;
  v14 = *v6;
  *(_QWORD *)(a1 + 16) = v12;
  v15 = MTX_BITIO_Create(v14, a2, a3, v13);
  *(_QWORD *)(a1 + 96) = v15;
  if ( !v15 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v15 = *(_QWORD *)(a1 + 96);
  }
  if ( a5 == 1 )
    v16 = 0;
  else
    v16 = MTX_BITIO_input_bit(v15);
  *(_WORD *)(a1 + 24) = v16;
  v17 = MTX_AHUFF_Create(*v6, *(_QWORD *)(a1 + 96), 8);
  *(_QWORD *)(a1 + 72) = v17;
  if ( !v17 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v18 = MTX_AHUFF_Create(*v6, *(_QWORD *)(a1 + 96), 8);
  *(_QWORD *)(a1 + 80) = v18;
  if ( !v18 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v19 = *(_QWORD *)(a1 + 96);
  LODWORD(v20) = 0;
  for ( i = 23; i >= 0; --i )
  {
    v22 = 2 * v20;
    v23 = MTX_BITIO_input_bit(v19);
    v20 = v22 | 1;
    if ( !v23 )
      v20 = v22;
  }
  *(_DWORD *)(a1 + 32) = v20;
  SetDistRange(a1, v20);
  v24 = *(unsigned int *)(a1 + 64);
  v25 = *(_DWORD *)(a1 + 32) + 7168;
  if ( (int)v24 >= v25 )
    v24 = (unsigned int)v25;
  else
    *(_BYTE *)(a1 + 8) = 1;
  v26 = MTX_mem_malloc(*v6, v24);
  v27 = *(unsigned __int16 *)(a1 + 60);
  v28 = *(_QWORD *)(a1 + 96);
  v29 = *v6;
  *(_QWORD *)a1 = v26;
  v30 = MTX_AHUFF_Create(v29, v28, v27);
  *(_QWORD *)(a1 + 88) = v30;
  if ( !v30 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v31 = Decode(a1, a4);
  MTX_AHUFF_Destroy(*(_QWORD *)(a1 + 72));
  v32 = *(_QWORD *)(a1 + 80);
  *(_QWORD *)(a1 + 72) = 0;
  MTX_AHUFF_Destroy(v32);
  v33 = *(_QWORD *)(a1 + 88);
  *(_QWORD *)(a1 + 80) = 0;
  MTX_AHUFF_Destroy(v33);
  v34 = *(_QWORD *)(a1 + 96);
  *(_QWORD *)(a1 + 88) = 0;
  MTX_BITIO_Destroy(v34);
  v35 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 96) = 0;
  DiscardPointer(*(_QWORD *)(v35 + 8), v35, 1);
  *(_QWORD *)(a1 + 16) = 0;
  if ( !*(_WORD *)(a1 + 24) && *a4 >= v25 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  return v31;
}

```

## disassembly

```asm
0x180006548  push    rbx
0x18000654a  push    rbp
0x18000654b  push    rsi
0x18000654c  push    rdi
0x18000654d  push    r12
0x18000654f  push    r14
0x180006551  push    r15
0x180006553  sub     rsp, 20h
0x180006557  mov     r14, rdx
0x18000655a  lea     rsi, [rcx+90h]
0x180006561  mov     rdx, [rcx]
0x180006564  xor     r12d, r12d
0x180006567  mov     r15, r9
0x18000656a  mov     ebp, r8d
0x18000656d  mov     rdi, rcx
0x180006570  test    rdx, rdx
0x180006573  jnz     loc_180006710
0x180006579  mov     rbx, [rsi]
0x18000657c  mov     edx, 10h
0x180006581  mov     rcx, rbx
0x180006584  mov     [rdi], r12
0x180006587  call    MTX_mem_malloc
0x18000658c  mov     r9b, 72h ; 'r'
0x18000658f  mov     r8d, ebp
0x180006592  mov     rdx, r14
0x180006595  mov     [rax+8], rbx
0x180006599  mov     byte ptr [rax+2], 64h ; 'd'
0x18000659d  mov     rcx, [rsi]
0x1800065a0  mov     [rdi+10h], rax
0x1800065a4  call    MTX_BITIO_Create
0x1800065a9  mov     [rdi+60h], rax
0x1800065ad  test    rax, rax
0x1800065b0  jz      loc_180006723
0x1800065b6  cmp     [rsp+58h+arg_20], 1
0x1800065be  jnz     loc_1800066F0
0x1800065c4  mov     eax, r12d
0x1800065c7  mov     [rdi+18h], ax
0x1800065cb  mov     ebx, 8
0x1800065d0  mov     rdx, [rdi+60h]
0x1800065d4  mov     r8d, ebx
0x1800065d7  mov     rcx, [rsi]
0x1800065da  call    MTX_AHUFF_Create
0x1800065df  mov     [rdi+48h], rax
0x1800065e3  test    rax, rax
0x1800065e6  jz      loc_180006731
0x1800065ec  mov     rdx, [rdi+60h]
0x1800065f0  mov     r8d, ebx
0x1800065f3  mov     rcx, [rsi]
0x1800065f6  call    MTX_AHUFF_Create
0x1800065fb  mov     [rdi+50h], rax
0x1800065ff  test    rax, rax
0x180006602  jz      loc_18000673B
0x180006608  mov     r14, [rdi+60h]
0x18000660c  mov     edx, r12d
0x18000660f  mov     ebp, 17h
0x180006614  mov     rcx, r14
0x180006617  lea     ebx, [rdx+rdx]
0x18000661a  call    MTX_BITIO_input_bit
0x18000661f  mov     edx, ebx
0x180006621  or      edx, 1
0x180006624  test    ax, ax
0x180006627  cmovz   edx, ebx
0x18000662a  sub     ebp, 1
0x18000662d  jns     short loc_180006614
0x18000662f  mov     rcx, rdi
0x180006632  mov     [rdi+20h], edx
0x180006635  call    SetDistRange
0x18000663a  mov     ebx, [rdi+20h]
0x18000663d  mov     edx, [rdi+40h]
0x180006640  add     ebx, 1C00h
0x180006646  cmp     edx, ebx
0x180006648  jge     loc_1800066FD
0x18000664e  mov     byte ptr [rdi+8], 1
0x180006652  mov     rcx, [rsi]
0x180006655  call    MTX_mem_malloc
0x18000665a  movzx   r8d, word ptr [rdi+3Ch]
0x18000665f  mov     rdx, [rdi+60h]
0x180006663  mov     rcx, [rsi]
0x180006666  mov     [rdi], rax
0x180006669  call    MTX_AHUFF_Create
0x18000666e  mov     [rdi+58h], rax
0x180006672  test    rax, rax
0x180006675  jz      loc_180006745
0x18000667b  mov     rdx, r15
0x18000667e  mov     rcx, rdi
0x180006681  call    Decode
0x180006686  mov     rcx, [rdi+48h]
0x18000668a  mov     rsi, rax
0x18000668d  call    MTX_AHUFF_Destroy
0x180006692  mov     rcx, [rdi+50h]
0x180006696  mov     [rdi+48h], r12
0x18000669a  call    MTX_AHUFF_Destroy
0x18000669f  mov     rcx, [rdi+58h]
0x1800066a3  mov     [rdi+50h], r12
0x1800066a7  call    MTX_AHUFF_Destroy
0x1800066ac  mov     rcx, [rdi+60h]
0x1800066b0  mov     [rdi+58h], r12
0x1800066b4  call    MTX_BITIO_Destroy
0x1800066b9  mov     rcx, [rdi+10h]
0x1800066bd  mov     r8d, 1
0x1800066c3  mov     [rdi+60h], r12
0x1800066c7  mov     rdx, rcx
0x1800066ca  mov     rcx, [rcx+8]
0x1800066ce  call    DiscardPointer
0x1800066d3  mov     [rdi+10h], r12
0x1800066d7  cmp     [rdi+18h], r12w
0x1800066dc  jz      short loc_180006704
0x1800066de  mov     rax, rsi
0x1800066e1  add     rsp, 20h
0x1800066e5  pop     r15
0x1800066e7  pop     r14
0x1800066e9  pop     r12
0x1800066eb  pop     rdi
0x1800066ec  pop     rsi
0x1800066ed  pop     rbp
0x1800066ee  pop     rbx
0x1800066ef  retn
0x1800066f0  mov     rcx, rax
0x1800066f3  call    MTX_BITIO_input_bit
0x1800066f8  jmp     loc_1800065C7
0x1800066fd  mov     edx, ebx
0x1800066ff  jmp     loc_180006652
0x180006704  cmp     [r15], ebx
0x180006707  jl      short loc_1800066DE
0x180006709  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000670e  jmp     short loc_1800066DE
0x180006710  mov     rcx, [rsi]
0x180006713  mov     r8d, 1
0x180006719  call    DiscardPointer
0x18000671e  jmp     loc_180006579
0x180006723  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006728  mov     rax, [rdi+60h]
0x18000672c  jmp     loc_1800065B6
0x180006731  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006736  jmp     loc_1800065EC
0x18000673b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006740  jmp     loc_180006608
0x180006745  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000674a  jmp     loc_18000667B
```
