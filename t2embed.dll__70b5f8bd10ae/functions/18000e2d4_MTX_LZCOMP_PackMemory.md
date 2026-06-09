# MTX_LZCOMP_PackMemory

- ea: `0x18000e2d4`
- end: `0x18000e57a`
- name: `MTX_LZCOMP_PackMemory`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000e12c`

## callees

- `0x180006400`
- `0x1800067cc`
- `0x180006a2c`
- `0x180006d30`
- `0x180009c80`
- `0x18000d570`
- `0x18000e2d4`
- `0x18000e788`
- `0x18000e7d4`
- `0x18000e840`
- `0x18000ea00`
- `0x18000eacc`
- `0x18001c9ec`
- `0x18001ce2c`

## pseudocode

```c
__int64 __fastcall MTX_LZCOMP_PackMemory(__int64 *a1, __int64 a2, int a3, _DWORD *a4)
{
  _QWORD *v5; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rdi
  int v29; // edi
  __int64 v30; // rbx
  __int64 result; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  int v35; // edx
  _BYTE *i; // r9
  __int64 v37; // rax
  int v38; // [rsp+50h] [rbp+18h] BYREF

  *((_DWORD *)a1 + 7) = a3;
  v5 = a1 + 18;
  if ( *a1 )
    DiscardPointer(*v5, *a1, 1);
  v8 = *v5;
  v9 = (unsigned int)(*((_DWORD *)a1 + 7) + 7168);
  *a1 = 0;
  v10 = MTX_mem_malloc(v8, v9);
  v11 = *((unsigned int *)a1 + 7);
  *a1 = v10;
  memcpyHuge(v10 + 7168, a2, v11);
  v12 = *v5;
  v13 = *v5;
  *((_WORD *)a1 + 12) = 0;
  v38 = 0;
  v14 = MTX_mem_malloc(v13, 16);
  *(_QWORD *)(v14 + 8) = v12;
  *(_BYTE *)(v14 + 2) = 100;
  v15 = *((unsigned int *)a1 + 7);
  v16 = *a1 + 7168;
  a1[2] = v14;
  v17 = MTX_RUNLENGTHCOMP_PackData(v14, v16, v15, &v38);
  if ( v38 < 3 * *((_DWORD *)a1 + 7) / 4 )
  {
    v32 = *a1;
    *((_DWORD *)a1 + 7) = v38;
    v33 = *v5;
    *((_WORD *)a1 + 12) = 1;
    DiscardPointer(v33, v32, 1);
    v34 = MTX_mem_malloc(*v5, (unsigned int)(*((_DWORD *)a1 + 7) + 7168));
    v35 = 0;
    *a1 = v34;
    for ( i = (_BYTE *)(v34 + 7168); v35 < *((_DWORD *)a1 + 7); ++i )
    {
      v37 = v35++;
      *i = *(_BYTE *)(v37 + v17);
    }
  }
  DiscardPointer(*v5, v17, 1);
  DiscardPointer(*(_QWORD *)(a1[2] + 8), a1[2], 1);
  v18 = *v5;
  a1[2] = 0;
  v19 = MTX_mem_malloc(v18, 1024);
  LOBYTE(v20) = 119;
  v21 = MTX_BITIO_Create(*v5, v19, 1024, v20);
  a1[13] = v21;
  if ( !v21 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  MTX_BITIO_output_bit(a1[13], (unsigned int)*((__int16 *)a1 + 12));
  v22 = MTX_AHUFF_Create(*v5, a1[13], 8);
  a1[9] = v22;
  if ( !v22 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v23 = MTX_AHUFF_Create(*v5, a1[13], 8);
  a1[10] = v23;
  if ( !v23 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  SetDistRange(a1, *((unsigned int *)a1 + 7));
  v24 = MTX_AHUFF_Create(*v5, a1[13], *((unsigned __int16 *)a1 + 30));
  a1[11] = v24;
  if ( !v24 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Encode(a1);
  MTX_AHUFF_Destroy(a1[9]);
  v25 = a1[10];
  a1[9] = 0;
  MTX_AHUFF_Destroy(v25);
  v26 = a1[11];
  a1[10] = 0;
  MTX_AHUFF_Destroy(v26);
  v27 = a1[13];
  a1[11] = 0;
  MTX_BITIO_flush_bits(v27);
  v28 = a1[13];
  if ( *(_BYTE *)(v28 + 32) != 119 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v29 = *(_DWORD *)(v28 + 28);
  v30 = *(_QWORD *)a1[13];
  MTX_BITIO_Destroy();
  a1[13] = 0;
  result = v30;
  *a4 = v29;
  return result;
}

```

## disassembly

```asm
0x18000e2d4  mov     [rsp+arg_0], rbx
0x18000e2d9  mov     [rsp+arg_8], rsi
0x18000e2de  push    rdi
0x18000e2df  push    r14
0x18000e2e1  push    r15
0x18000e2e3  sub     rsp, 20h
0x18000e2e7  mov     rbx, rdx
0x18000e2ea  mov     [rcx+1Ch], r8d
0x18000e2ee  mov     rdx, [rcx]
0x18000e2f1  lea     rdi, [rcx+90h]
0x18000e2f8  mov     r14, r9
0x18000e2fb  mov     rsi, rcx
0x18000e2fe  mov     r15d, 1
0x18000e304  test    rdx, rdx
0x18000e307  jnz     loc_18000E542
0x18000e30d  mov     edx, [rsi+1Ch]
0x18000e310  mov     rcx, [rdi]
0x18000e313  add     edx, 1C00h
0x18000e319  mov     qword ptr [rsi], 0
0x18000e320  call    MTX_mem_malloc
0x18000e325  mov     r8d, [rsi+1Ch]
0x18000e329  mov     rdx, rbx
0x18000e32c  mov     [rsi], rax
0x18000e32f  lea     rcx, [rax+1C00h]
0x18000e336  call    memcpyHuge
0x18000e33b  mov     rbx, [rdi]
0x18000e33e  xor     eax, eax
0x18000e340  mov     rcx, rbx
0x18000e343  mov     [rsi+18h], ax
0x18000e347  mov     [rsp+38h+arg_10], eax
0x18000e34b  lea     edx, [rax+10h]
0x18000e34e  call    MTX_mem_malloc
0x18000e353  lea     r9, [rsp+38h+arg_10]
0x18000e358  mov     rcx, rax
0x18000e35b  mov     [rax+8], rbx
0x18000e35f  mov     byte ptr [rax+2], 64h ; 'd'
0x18000e363  mov     rdx, [rsi]
0x18000e366  mov     r8d, [rsi+1Ch]
0x18000e36a  add     rdx, 1C00h
0x18000e371  mov     [rsi+10h], rax
0x18000e375  call    MTX_RUNLENGTHCOMP_PackData
0x18000e37a  mov     ecx, [rsi+1Ch]
0x18000e37d  mov     rbx, rax
0x18000e380  lea     eax, [rcx+rcx*2]
0x18000e383  mov     ecx, 4
0x18000e388  cdq
0x18000e389  idiv    ecx
0x18000e38b  mov     ecx, [rsp+38h+arg_10]
0x18000e38f  cmp     ecx, eax
0x18000e391  jl      loc_18000E4E3
0x18000e397  mov     rcx, [rdi]
0x18000e39a  mov     r8d, r15d
0x18000e39d  mov     rdx, rbx
0x18000e3a0  call    DiscardPointer
0x18000e3a5  mov     rcx, [rsi+10h]
0x18000e3a9  mov     r8d, r15d
0x18000e3ac  mov     rdx, rcx
0x18000e3af  mov     rcx, [rcx+8]
0x18000e3b3  call    DiscardPointer
0x18000e3b8  mov     rcx, [rdi]
0x18000e3bb  mov     ebx, 400h
0x18000e3c0  mov     edx, ebx
0x18000e3c2  mov     qword ptr [rsi+10h], 0
0x18000e3ca  call    MTX_mem_malloc
0x18000e3cf  mov     rcx, [rdi]
0x18000e3d2  mov     r9b, 77h ; 'w'
0x18000e3d5  mov     r8d, ebx
0x18000e3d8  mov     rdx, rax
0x18000e3db  call    MTX_BITIO_Create
0x18000e3e0  mov     [rsi+68h], rax
0x18000e3e4  test    rax, rax
0x18000e3e7  jz      loc_18000E538
0x18000e3ed  movsx   edx, word ptr [rsi+18h]
0x18000e3f1  mov     rcx, [rsi+68h]
0x18000e3f5  call    MTX_BITIO_output_bit
0x18000e3fa  mov     rdx, [rsi+68h]
0x18000e3fe  mov     ebx, 8
0x18000e403  mov     rcx, [rdi]
0x18000e406  mov     r8d, ebx
0x18000e409  call    MTX_AHUFF_Create
0x18000e40e  mov     [rsi+48h], rax
0x18000e412  test    rax, rax
0x18000e415  jz      loc_18000E552
0x18000e41b  mov     rdx, [rsi+68h]
0x18000e41f  mov     r8d, ebx
0x18000e422  mov     rcx, [rdi]
0x18000e425  call    MTX_AHUFF_Create
0x18000e42a  mov     [rsi+50h], rax
0x18000e42e  test    rax, rax
0x18000e431  jz      loc_18000E55C
0x18000e437  mov     edx, [rsi+1Ch]
0x18000e43a  mov     rcx, rsi
0x18000e43d  call    SetDistRange
0x18000e442  movzx   r8d, word ptr [rsi+3Ch]
0x18000e447  mov     rdx, [rsi+68h]
0x18000e44b  mov     rcx, [rdi]
0x18000e44e  call    MTX_AHUFF_Create
0x18000e453  mov     [rsi+58h], rax
0x18000e457  test    rax, rax
0x18000e45a  jz      loc_18000E566
0x18000e460  mov     rcx, rsi
0x18000e463  call    Encode
0x18000e468  mov     rcx, [rsi+48h]
0x18000e46c  call    MTX_AHUFF_Destroy
0x18000e471  mov     rcx, [rsi+50h]
0x18000e475  mov     qword ptr [rsi+48h], 0
0x18000e47d  call    MTX_AHUFF_Destroy
0x18000e482  mov     rcx, [rsi+58h]
0x18000e486  mov     qword ptr [rsi+50h], 0
0x18000e48e  call    MTX_AHUFF_Destroy
0x18000e493  mov     rcx, [rsi+68h]
0x18000e497  mov     qword ptr [rsi+58h], 0
0x18000e49f  call    MTX_BITIO_flush_bits
0x18000e4a4  mov     rdi, [rsi+68h]
0x18000e4a8  cmp     byte ptr [rdi+20h], 77h ; 'w'
0x18000e4ac  jnz     loc_18000E570
0x18000e4b2  mov     rcx, [rsi+68h]
0x18000e4b6  mov     edi, [rdi+1Ch]
0x18000e4b9  mov     rbx, [rcx]
0x18000e4bc  call    MTX_BITIO_Destroy
0x18000e4c1  mov     qword ptr [rsi+68h], 0
0x18000e4c9  mov     rax, rbx
0x18000e4cc  mov     rbx, [rsp+38h+arg_0]
0x18000e4d1  mov     rsi, [rsp+38h+arg_8]
0x18000e4d6  mov     [r14], edi
0x18000e4d9  add     rsp, 20h
0x18000e4dd  pop     r15
0x18000e4df  pop     r14
0x18000e4e1  pop     rdi
0x18000e4e2  retn
0x18000e4e3  mov     rdx, [rsi]
0x18000e4e6  mov     r8d, r15d
0x18000e4e9  mov     [rsi+1Ch], ecx
0x18000e4ec  mov     rcx, [rdi]
0x18000e4ef  mov     [rsi+18h], r15w
0x18000e4f4  call    DiscardPointer
0x18000e4f9  mov     edx, [rsi+1Ch]
0x18000e4fc  mov     rcx, [rdi]
0x18000e4ff  add     edx, 1C00h
0x18000e505  call    MTX_mem_malloc
0x18000e50a  xor     edx, edx
0x18000e50c  mov     [rsi], rax
0x18000e50f  lea     r9, [rax+1C00h]
0x18000e516  cmp     [rsi+1Ch], edx
0x18000e519  jle     loc_18000E397
0x18000e51f  movsxd  rax, edx
0x18000e522  add     edx, r15d
0x18000e525  mov     cl, [rax+rbx]
0x18000e528  mov     [r9], cl
0x18000e52b  add     r9, r15
0x18000e52e  cmp     edx, [rsi+1Ch]
0x18000e531  jl      short loc_18000E51F
0x18000e533  jmp     loc_18000E397
0x18000e538  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e53d  jmp     loc_18000E3ED
0x18000e542  mov     rcx, [rdi]
0x18000e545  mov     r8d, r15d
0x18000e548  call    DiscardPointer
0x18000e54d  jmp     loc_18000E30D
0x18000e552  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e557  jmp     loc_18000E41B
0x18000e55c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e561  jmp     loc_18000E437
0x18000e566  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e56b  jmp     loc_18000E460
0x18000e570  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e575  jmp     loc_18000E4B2
```
