# ReadAllCTFInstructions

- ea: `0x180009d40`
- end: `0x18000a548`
- name: `ReadAllCTFInstructions`
- size: `2056`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180004e10`

## callees

- `0x180006400`
- `0x180009c80`
- `0x180009d40`
- `0x18000a550`
- `0x18000af64`
- `0x18000b1ac`
- `0x18000b1f0`
- `0x18000b4e0`
- `0x18000bc10`
- `0x18001c9ec`

## import_xrefs

- `msvcrt!longjmp` at `0x18000a04c`
- `msvcrt!longjmp` at `0x18000a063`
- `msvcrt!longjmp` at `0x18000a073`
- `msvcrt!longjmp` at `0x18000a0f8`
- `msvcrt!longjmp` at `0x18000a10f`
- `msvcrt!longjmp` at `0x18000a126`
- `msvcrt!longjmp` at `0x18000a13d`
- `msvcrt!longjmp` at `0x18000a14d`
- `msvcrt!longjmp` at `0x18000a183`
- `msvcrt!longjmp` at `0x18000a21b`
- `msvcrt!longjmp` at `0x18000a294`
- `msvcrt!longjmp` at `0x18000a2ab`
- `msvcrt!longjmp` at `0x18000a2c2`
- `msvcrt!longjmp` at `0x18000a2d2`
- `msvcrt!longjmp` at `0x18000a411`
- `msvcrt!longjmp` at `0x18000a421`
- `msvcrt!longjmp` at `0x18000a431`
- `msvcrt!longjmp` at `0x18000a441`
- `msvcrt!longjmp` at `0x18000a451`
- `msvcrt!longjmp` at `0x18000a461`
- `msvcrt!longjmp` at `0x18000a47d`
- `msvcrt!longjmp` at `0x18000a499`
- `msvcrt!longjmp` at `0x18000a4b5`
- `msvcrt!longjmp` at `0x18000a4d1`
- `msvcrt!longjmp` at `0x18000a4ed`
- `msvcrt!longjmp` at `0x18000a509`
- `msvcrt!longjmp` at `0x18000a525`
- `msvcrt!longjmp` at `0x18000a541`
- `msvcrt!longjmp` at `0x18000a04c`
- `msvcrt!longjmp` at `0x18000a063`
- `msvcrt!longjmp` at `0x18000a073`
- `msvcrt!longjmp` at `0x18000a0f8`
- `msvcrt!longjmp` at `0x18000a10f`
- `msvcrt!longjmp` at `0x18000a126`
- `msvcrt!longjmp` at `0x18000a13d`
- `msvcrt!longjmp` at `0x18000a14d`
- `msvcrt!longjmp` at `0x18000a183`
- `msvcrt!longjmp` at `0x18000a21b`
- `msvcrt!longjmp` at `0x18000a294`
- `msvcrt!longjmp` at `0x18000a2ab`
- `msvcrt!longjmp` at `0x18000a2c2`
- `msvcrt!longjmp` at `0x18000a2d2`
- `msvcrt!longjmp` at `0x18000a411`
- `msvcrt!longjmp` at `0x18000a421`
- `msvcrt!longjmp` at `0x18000a431`
- `msvcrt!longjmp` at `0x18000a441`
- `msvcrt!longjmp` at `0x18000a451`
- `msvcrt!longjmp` at `0x18000a461`
- `msvcrt!longjmp` at `0x18000a47d`
- `msvcrt!longjmp` at `0x18000a499`
- `msvcrt!longjmp` at `0x18000a4b5`
- `msvcrt!longjmp` at `0x18000a4d1`
- `msvcrt!longjmp` at `0x18000a4ed`
- `msvcrt!longjmp` at `0x18000a509`
- `msvcrt!longjmp` at `0x18000a525`
- `msvcrt!longjmp` at `0x18000a541`

## pseudocode

```c
__int64 __fastcall ReadAllCTFInstructions(__int64 a1, unsigned __int64 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned __int16 v7; // ax
  _JBTYPE *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rdx
  _BYTE *v12; // r8
  unsigned __int16 v13; // bp
  __int16 v14; // r13
  unsigned __int64 v15; // r12
  __int16 v16; // r15
  __int64 v17; // rax
  _BYTE *v18; // rdx
  unsigned __int64 v19; // rcx
  _BYTE *v20; // rcx
  __int64 v21; // rax
  unsigned __int64 v22; // rdx
  _JBTYPE *v23; // rdx
  unsigned __int8 v24; // al
  unsigned __int16 *v25; // rdi
  unsigned __int8 *v26; // rsi
  __int16 v27; // cx
  __int16 v28; // ax
  unsigned __int16 v29; // dx
  __int16 v30; // ax
  bool v31; // zf
  _JBTYPE *v32; // rcx
  int v33; // eax
  int v34; // edx
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // rdx
  _BYTE *v38; // rdx
  __int64 v39; // rcx
  int v40; // r9d
  __int16 i; // r8
  __int64 result; // rax
  unsigned int v43; // r8d
  int v44; // edx
  __int64 v45; // rax
  unsigned __int64 v46; // rcx
  __int64 v47; // rax
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // r8
  _JBTYPE *v50; // rcx
  __int64 v51; // rcx
  __int16 v52; // di
  __int64 v53; // rax
  unsigned __int16 v54; // bp
  __int16 v55; // ax
  __int64 v56; // rdx
  __int16 j; // r8
  __int64 v58; // rcx
  __int16 v59; // cx
  unsigned __int16 v60; // si
  unsigned __int16 v61; // di
  unsigned __int16 v62; // bp
  unsigned __int16 v63; // ax
  unsigned __int16 v64; // di
  unsigned __int16 v65; // ax
  __int16 v66; // cx
  _BYTE *v67; // [rsp+50h] [rbp+8h] BYREF

  DiscardPointer(*(_QWORD *)(a1 + 136), *(_QWORD *)(a1 + 88), 1);
  v4 = *(_QWORD *)(a1 + 104);
  v5 = *(_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 88) = 0;
  DiscardPointer(v5, v4, 1);
  *(_QWORD *)(a1 + 104) = 0;
  v7 = Read255UShort(a1, a2, v6);
  v8 = *(_JBTYPE **)(a1 + 136);
  *(_WORD *)(a1 + 80) = v7;
  v9 = 2 * (unsigned int)v7;
  if ( (unsigned int)v9 < v7 )
    longjmp(v8 + 3, 3362);
  *(_QWORD *)(a1 + 88) = MTX_mem_malloc(v8, v9);
  v10 = *(_QWORD *)(a1 + 112);
  if ( !v10 )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  v11 = *(_QWORD *)(v10 + 16) + *(int *)(v10 + 44);
  v12 = (_BYTE *)*a2;
  v13 = 0;
  *a2 = v11;
  v14 = *(_WORD *)(a1 + 80);
  v15 = v11 + *(int *)(*(_QWORD *)(a1 + 112) + 24LL);
  v67 = v12;
  if ( v14 > 0 )
  {
    v16 = -1;
    do
    {
      v17 = *(_QWORD *)(a1 + 112);
      v18 = (_BYTE *)*a2;
      v19 = *(_QWORD *)(v17 + 16);
      if ( *a2 < v19 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
      }
      if ( (unsigned __int64)v18 >= v19 + *(int *)(v17 + 24) )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
      }
      v20 = (_BYTE *)*a2;
      if ( *v18 == 0xFB )
      {
        *a2 = (unsigned __int64)(v18 + 1);
        v50 = *(_JBTYPE **)(a1 + 136);
        if ( (__int16)v13 < 2 )
          longjmp(v50 + 3, 3362);
        if ( v13 >= *(_WORD *)(a1 + 80) )
          longjmp(v50 + 3, 3362);
        v51 = *(_QWORD *)(a1 + 88);
        v52 = *(_WORD *)(v51 + 2LL * (__int16)v13 - 4);
        v53 = v13;
        v54 = v13 + 1;
        *(_WORD *)(v51 + 2 * v53) = v52;
        v55 = Read255Short(a1, a2, *a2, v15);
        if ( v54 >= *(_WORD *)(a1 + 80) )
          longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
        v56 = v54;
        v13 = v54 + 1;
        *(_WORD *)(*(_QWORD *)(a1 + 88) + 2 * v56) = v55;
        if ( v13 >= *(_WORD *)(a1 + 80) )
          longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
        *(_WORD *)(*(_QWORD *)(a1 + 88) + 2LL * v13) = v52;
      }
      else if ( *v18 == 0xFC )
      {
        *a2 = (unsigned __int64)(v18 + 1);
        VerifyConditionInternal(*(_QWORD *)(a1 + 136), (__int16)v13 >= 2);
        v60 = *(_WORD *)(*(_QWORD *)(a1 + 88) + 2LL * (__int16)v13 - 4);
        WritePushCode(a1, v13, *(unsigned __int16 *)(a1 + 80), v60);
        v61 = *(_WORD *)(a1 + 80);
        v62 = v13 + 1;
        v63 = Read255Short(a1, a2, *a2, v15);
        WritePushCode(a1, v62++, v61, v63);
        WritePushCode(a1, v62, *(unsigned __int16 *)(a1 + 80), v60);
        v64 = *(_WORD *)(a1 + 80);
        ++v62;
        v65 = Read255Short(a1, a2, *a2, v15);
        WritePushCode(a1, v62, v64, v65);
        v13 = v62 + 1;
        WritePushCode(a1, v13, *(unsigned __int16 *)(a1 + 80), v60);
      }
      else
      {
        v21 = *(_QWORD *)(a1 + 112);
        v22 = *(_QWORD *)(v21 + 16);
        if ( (unsigned __int64)v20 < v22 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
        }
        if ( (unsigned __int64)v20 >= v22 + *(int *)(v21 + 24) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
        }
        v23 = *(_JBTYPE **)(a1 + 136);
        if ( (unsigned __int64)v20 >= v15 )
          longjmp(v23 + 3, 3362);
        v24 = *v20;
        v25 = (unsigned __int16 *)(v20 + 1);
        if ( *v20 == 0xFD )
        {
          v45 = *(_QWORD *)(a1 + 112);
          v46 = *(_QWORD *)(v45 + 16);
          if ( (unsigned __int64)v25 < v46 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
          }
          if ( (unsigned __int64)v25 >= v46 + *(int *)(v45 + 24) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
          }
          if ( (unsigned __int64)v25 >= v15 )
            longjmp(v23 + 3, 3362);
          v47 = *(_QWORD *)(a1 + 112);
          v48 = (unsigned __int64)v25 + 1;
          v49 = *(_QWORD *)(v47 + 16);
          if ( (unsigned __int64)v25 + 1 < v49 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
          }
          if ( v48 >= v49 + *(int *)(v47 + 24) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
          }
          if ( v48 >= v15 )
            longjmp(v23 + 3, 3362);
          v26 = (unsigned __int8 *)(v25 + 1);
          v29 = _byteswap_ushort(*v25);
        }
        else
        {
          v26 = v20 + 1;
          if ( v24 == 0xFA )
          {
            ValidateGlyphPtr(
              a1,
              v20 + 1,
              *(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL),
              *(unsigned int *)(*(_QWORD *)(a1 + 112) + 24LL));
            v23 = *(_JBTYPE **)(a1 + 136);
            if ( (unsigned __int64)v25 >= v15 )
              longjmp(v23 + 3, 3362);
            v24 = *(_BYTE *)v25;
            v26 = (unsigned __int8 *)v25 + 1;
          }
          else
          {
            v16 = 1;
          }
          if ( v24 == 0xFF )
          {
            ValidateGlyphPtr(
              a1,
              v26,
              *(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL),
              *(unsigned int *)(*(_QWORD *)(a1 + 112) + 24LL));
            if ( (unsigned __int64)v26 >= v15 )
              longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
            v66 = *v26++;
            v27 = v66 + 250;
          }
          else if ( v24 == 0xFE )
          {
            ValidateGlyphPtr(
              a1,
              v26,
              *(_QWORD *)(*(_QWORD *)(a1 + 112) + 16LL),
              *(unsigned int *)(*(_QWORD *)(a1 + 112) + 24LL));
            if ( (unsigned __int64)v26 >= v15 )
              longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
            v59 = *v26++;
            v27 = v59 + 500;
          }
          else
          {
            if ( v24 >= 0xFAu )
              longjmp(v23 + 3, 3362);
            v27 = v24;
          }
          v28 = v16;
          v16 = -1;
          v29 = v28 * v27;
        }
        *a2 = (unsigned __int64)v26;
        if ( v13 >= *(_WORD *)(a1 + 80) )
          longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
        *(_WORD *)(*(_QWORD *)(a1 + 88) + 2LL * v13) = v29;
      }
      ++v13;
    }
    while ( (__int16)v13 < v14 );
    v12 = v67;
  }
  if ( (__int16)v13 != *(unsigned __int16 *)(a1 + 80) )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  *(_DWORD *)(*(_QWORD *)(a1 + 112) + 44LL) = *(_DWORD *)a2 - *(_DWORD *)(*(_QWORD *)(a1 + 112) + 16LL);
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 112) + 44LL) > *(_DWORD *)(*(_QWORD *)(a1 + 112) + 24LL) )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  *a2 = (unsigned __int64)v12;
  v30 = Read255UShort(a1, a2, v12);
  v31 = *(_QWORD *)(a1 + 112) == 0;
  v32 = *(_JBTYPE **)(a1 + 136);
  *(_WORD *)(a1 + 96) = v30;
  if ( v31 )
    longjmp(v32 + 3, 3362);
  DiscardPointer(v32, *(_QWORD *)(a1 + 72), 1);
  v33 = *(unsigned __int16 *)(a1 + 80);
  v34 = *(unsigned __int16 *)(a1 + 96) + 16;
  *(_QWORD *)(a1 + 72) = 0;
  v35 = MTX_mem_malloc(*(_QWORD *)(a1 + 136), (unsigned int)(3 * v33 + v34));
  v36 = *(unsigned __int16 *)(a1 + 80);
  v37 = *(_QWORD *)(a1 + 88);
  *(_QWORD *)(a1 + 72) = v35;
  v67 = (_BYTE *)v35;
  OptimizingPush(&v67, v37, v36);
  v38 = v67;
  if ( (__int64)&v67[-*(_QWORD *)(a1 + 72)] >= *(unsigned __int16 *)(a1 + 80)
                                             + 2 * (*(unsigned __int16 *)(a1 + 80) + 8LL) )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  v39 = *(_QWORD *)(a1 + 112);
  v40 = *(__int16 *)(a1 + 96);
  if ( v39 )
  {
    if ( *(_DWORD *)(v39 + 48) + v40 > *(_DWORD *)(v39 + 40) )
      longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
    for ( i = 0; i < (__int16)v40; ++*(_DWORD *)(*(_QWORD *)(a1 + 112) + 48LL) )
    {
      ++i;
      *v38++ = *(_BYTE *)(*(int *)(*(_QWORD *)(a1 + 112) + 48LL) + *(_QWORD *)(*(_QWORD *)(a1 + 112) + 32LL));
    }
  }
  else
  {
    for ( j = 0; j < (__int16)v40; ++v38 )
    {
      v58 = (unsigned __int16)j++;
      *v38 = *(_BYTE *)(v58 + *(_QWORD *)(a1 + 104));
    }
  }
  result = *(unsigned __int16 *)(a1 + 80);
  v43 = (unsigned __int16)((_WORD)v38 - *(_WORD *)(a1 + 72));
  v44 = *(unsigned __int16 *)(a1 + 96) + 16;
  *(_WORD *)(a1 + 70) = v43;
  if ( v43 >= 3 * (int)result + v44 )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 136) + 48LL), 3362);
  return result;
}

```

## disassembly

```asm
0x180009d40  push    rbx
0x180009d42  push    r14
0x180009d44  sub     rsp, 38h
0x180009d48  mov     r14, rdx
0x180009d4b  mov     rbx, rcx
0x180009d4e  mov     rdx, [rcx+58h]
0x180009d52  mov     r8d, 1
0x180009d58  mov     rcx, [rcx+88h]
0x180009d5f  call    DiscardPointer
0x180009d64  mov     rdx, [rbx+68h]
0x180009d68  mov     r8d, 1
0x180009d6e  mov     rcx, [rbx+88h]
0x180009d75  mov     qword ptr [rbx+58h], 0
0x180009d7d  call    DiscardPointer
0x180009d82  mov     rdx, r14
0x180009d85  mov     qword ptr [rbx+68h], 0
0x180009d8d  mov     rcx, rbx
0x180009d90  call    Read255UShort
0x180009d95  mov     rcx, [rbx+88h]
0x180009d9c  movzx   eax, ax
0x180009d9f  mov     [rbx+50h], ax
0x180009da3  lea     edx, [rax+rax]
0x180009da6  cmp     edx, eax
0x180009da8  jb      loc_18000A17A
0x180009dae  call    MTX_mem_malloc
0x180009db3  mov     [rbx+58h], rax
0x180009db7  mov     rax, [rbx+70h]
0x180009dbb  test    rax, rax
0x180009dbe  jz      loc_18000A0E8
0x180009dc4  movsxd  rdx, dword ptr [rax+2Ch]
0x180009dc8  add     rdx, [rax+10h]
0x180009dcc  mov     r8, [r14]
0x180009dcf  mov     [rsp+48h+arg_8], rbp
0x180009dd4  xor     ebp, ebp
0x180009dd6  mov     [rsp+48h+arg_10], rsi
0x180009ddb  mov     [r14], rdx
0x180009dde  mov     rax, [rbx+70h]
0x180009de2  mov     [rsp+48h+arg_18], rdi
0x180009de7  mov     [rsp+48h+var_18], r12
0x180009dec  mov     [rsp+48h+var_20], r13
0x180009df1  movsxd  r12, dword ptr [rax+18h]
0x180009df5  xor     eax, eax
0x180009df7  movzx   r13d, word ptr [rbx+50h]
0x180009dfc  add     r12, rdx
0x180009dff  mov     [rsp+48h+var_28], r15
0x180009e04  mov     [rsp+48h+arg_0], r8
0x180009e09  cmp     ax, r13w
0x180009e0d  jge     loc_180009F00
0x180009e13  mov     r15d, 0FFFFFFFFh
0x180009e19  nop     dword ptr [rax+00000000h]
0x180009e20  mov     rax, [rbx+70h]
0x180009e24  mov     rdx, [r14]
0x180009e27  mov     rcx, [rax+10h]
0x180009e2b  cmp     rdx, rcx
0x180009e2e  jb      loc_18000A52C
0x180009e34  movsxd  rax, dword ptr [rax+18h]
0x180009e38  add     rax, rcx
0x180009e3b  cmp     rdx, rax
0x180009e3e  jnb     loc_18000A510
0x180009e44  movzx   eax, byte ptr [rdx]
0x180009e47  mov     rcx, rdx
0x180009e4a  cmp     al, 0FBh
0x180009e4c  jz      loc_18000A18A
0x180009e52  cmp     al, 0FCh
0x180009e54  jz      loc_18000A30C
0x180009e5a  mov     rax, [rbx+70h]
0x180009e5e  mov     rdx, [rax+10h]
0x180009e62  cmp     rcx, rdx
0x180009e65  jb      loc_18000A4F4
0x180009e6b  movsxd  rax, dword ptr [rax+18h]
0x180009e6f  add     rax, rdx
0x180009e72  cmp     rcx, rax
0x180009e75  jnb     loc_18000A4D8
0x180009e7b  mov     rdx, [rbx+88h]
0x180009e82  cmp     rcx, r12
0x180009e85  jnb     loc_18000A408
0x180009e8b  movzx   eax, byte ptr [rcx]
0x180009e8e  lea     rdi, [rcx+1]
0x180009e92  cmp     al, 0FDh
0x180009e94  jz      loc_18000A07A
0x180009e9a  mov     rsi, rdi
0x180009e9d  cmp     al, 0FAh
0x180009e9f  jz      loc_18000A2D9
0x180009ea5  mov     r15d, 1
0x180009eab  cmp     al, 0FFh
0x180009ead  jz      loc_18000A3D2
0x180009eb3  cmp     al, 0FEh
0x180009eb5  jz      loc_18000A251
0x180009ebb  cmp     al, 0FAh
0x180009ebd  jnb     loc_18000A06A
0x180009ec3  movzx   ecx, al
0x180009ec6  movsx   eax, r15w
0x180009eca  mov     r15d, 0FFFFFFFFh
0x180009ed0  movsx   edx, cx
0x180009ed3  imul    edx, eax
0x180009ed6  mov     [r14], rsi
0x180009ed9  cmp     bp, [rbx+50h]
0x180009edd  jnb     loc_18000A053
0x180009ee3  mov     rax, [rbx+58h]
0x180009ee7  movzx   ecx, bp
0x180009eea  mov     [rax+rcx*2], dx
0x180009eee  inc     bp
0x180009ef1  cmp     bp, r13w
0x180009ef5  jl      loc_180009E20
0x180009efb  mov     r8, [rsp+48h+arg_0]
0x180009f00  movzx   ecx, word ptr [rbx+50h]
0x180009f04  movsx   eax, bp
0x180009f07  cmp     eax, ecx
0x180009f09  jnz     loc_18000A0FF
0x180009f0f  mov     rcx, [rbx+70h]
0x180009f13  mov     eax, [r14]
0x180009f16  sub     eax, [rcx+10h]
0x180009f19  mov     [rcx+2Ch], eax
0x180009f1c  mov     rcx, [rbx+70h]
0x180009f20  mov     eax, [rcx+18h]
0x180009f23  cmp     [rcx+2Ch], eax
0x180009f26  jg      loc_18000A116
0x180009f2c  mov     rdx, r14
0x180009f2f  mov     [r14], r8
0x180009f32  mov     rcx, rbx
0x180009f35  call    Read255UShort
0x180009f3a  cmp     qword ptr [rbx+70h], 0
0x180009f3f  mov     rcx, [rbx+88h]
0x180009f46  mov     [rbx+60h], ax
0x180009f4a  jz      loc_18000A144
0x180009f50  mov     rdx, [rbx+48h]
0x180009f54  mov     r8d, 1
0x180009f5a  call    DiscardPointer
0x180009f5f  movzx   eax, word ptr [rbx+50h]
0x180009f63  movzx   edx, word ptr [rbx+60h]
0x180009f67  add     edx, 10h
0x180009f6a  mov     qword ptr [rbx+48h], 0
0x180009f72  lea     ecx, [rax+rax*2]
0x180009f75  add     edx, ecx
0x180009f77  mov     rcx, [rbx+88h]
0x180009f7e  call    MTX_mem_malloc
0x180009f83  movzx   r8d, word ptr [rbx+50h]
0x180009f88  lea     rcx, [rsp+48h+arg_0]
0x180009f8d  mov     rdx, [rbx+58h]
0x180009f91  mov     [rbx+48h], rax
0x180009f95  mov     [rsp+48h+arg_0], rax
0x180009f9a  call    OptimizingPush
0x180009f9f  movzx   eax, word ptr [rbx+50h]
0x180009fa3  mov     rdx, [rsp+48h+arg_0]
0x180009fa8  lea     rcx, [rax+8]
0x180009fac  lea     rcx, [rax+rcx*2]
0x180009fb0  mov     rax, rdx
0x180009fb3  sub     rax, [rbx+48h]
0x180009fb7  cmp     rax, rcx
0x180009fba  jge     loc_18000A12D
0x180009fc0  mov     rcx, [rbx+70h]
0x180009fc4  movsx   r9d, word ptr [rbx+60h]
0x180009fc9  test    rcx, rcx
0x180009fcc  jz      loc_18000A222
0x180009fd2  mov     eax, r9d
0x180009fd5  add     eax, [rcx+30h]
0x180009fd8  cmp     eax, [rcx+28h]
0x180009fdb  jg      loc_18000A20B
0x180009fe1  xor     r8d, r8d
0x180009fe4  xor     eax, eax
0x180009fe6  cmp     ax, r9w
0x180009fea  jge     short loc_18000A016
0x180009fec  nop     dword ptr [rax+00h]
0x180009ff0  mov     rax, [rbx+70h]
0x180009ff4  inc     r8w
0x180009ff8  movsxd  rcx, dword ptr [rax+30h]
0x180009ffc  mov     rax, [rax+20h]
0x18000a000  movzx   ecx, byte ptr [rcx+rax]
0x18000a004  mov     [rdx], cl
0x18000a006  inc     rdx
0x18000a009  mov     rax, [rbx+70h]
0x18000a00d  inc     dword ptr [rax+30h]
0x18000a010  cmp     r8w, r9w
0x18000a014  jl      short loc_180009FF0
0x18000a016  sub     dx, [rbx+48h]
0x18000a01a  movzx   eax, word ptr [rbx+50h]
0x18000a01e  movzx   r8d, dx
0x18000a022  movzx   edx, word ptr [rbx+60h]
0x18000a026  add     edx, 10h
0x18000a029  mov     [rbx+46h], r8w
0x18000a02e  lea     ecx, [rax+rax*2]
0x18000a031  add     edx, ecx
0x18000a033  cmp     r8d, edx
0x18000a036  jb      loc_18000A154
0x18000a03c  mov     rcx, [rbx+88h]
0x18000a043  mov     edx, 0D22h; Value
0x18000a048  add     rcx, 30h ; '0'; Buf
0x18000a04c  call    cs:__imp_longjmp
0x18000a053  mov     rcx, [rbx+88h]
0x18000a05a  mov     edx, 0D22h; Value
0x18000a05f  add     rcx, 30h ; '0'; Buf
0x18000a063  call    cs:__imp_longjmp
0x18000a06a  lea     rcx, [rdx+30h]; Buf
0x18000a06e  mov     edx, 0D22h; Value
0x18000a073  call    cs:__imp_longjmp
0x18000a07a  mov     rax, [rbx+70h]
0x18000a07e  mov     rcx, [rax+10h]
0x18000a082  cmp     rdi, rcx
0x18000a085  jb      loc_18000A4BC
0x18000a08b  movsxd  rax, dword ptr [rax+18h]
0x18000a08f  add     rax, rcx
0x18000a092  cmp     rdi, rax
0x18000a095  jnb     loc_18000A4A0
0x18000a09b  cmp     rdi, r12
0x18000a09e  jnb     loc_18000A428
0x18000a0a4  mov     rax, [rbx+70h]
0x18000a0a8  lea     rcx, [rdi+1]
0x18000a0ac  mov     r8, [rax+10h]
0x18000a0b0  cmp     rcx, r8
0x18000a0b3  jb      loc_18000A484
0x18000a0b9  movsxd  rax, dword ptr [rax+18h]
0x18000a0bd  add     rax, r8
0x18000a0c0  cmp     rcx, rax
0x18000a0c3  jnb     loc_18000A468
0x18000a0c9  cmp     rcx, r12
0x18000a0cc  jnb     loc_18000A418
0x18000a0d2  movzx   edx, byte ptr [rdi]
0x18000a0d5  lea     rsi, [rcx+1]
0x18000a0d9  movzx   eax, byte ptr [rcx]
0x18000a0dc  shl     dx, 8
0x18000a0e0  or      dx, ax
0x18000a0e3  jmp     loc_180009ED6
0x18000a0e8  mov     rcx, [rbx+88h]
0x18000a0ef  mov     edx, 0D22h; Value
0x18000a0f4  add     rcx, 30h ; '0'; Buf
0x18000a0f8  call    cs:__imp_longjmp
0x18000a0ff  mov     rcx, [rbx+88h]
0x18000a106  mov     edx, 0D22h; Value
0x18000a10b  add     rcx, 30h ; '0'; Buf
0x18000a10f  call    cs:__imp_longjmp
0x18000a116  mov     rcx, [rbx+88h]
0x18000a11d  mov     edx, 0D22h; Value
0x18000a122  add     rcx, 30h ; '0'; Buf
0x18000a126  call    cs:__imp_longjmp
0x18000a12d  mov     rcx, [rbx+88h]
0x18000a134  mov     edx, 0D22h; Value
0x18000a139  add     rcx, 30h ; '0'; Buf
0x18000a13d  call    cs:__imp_longjmp
0x18000a144  add     rcx, 30h ; '0'; Buf
0x18000a148  mov     edx, 0D22h; Value
0x18000a14d  call    cs:__imp_longjmp
0x18000a154  mov     r13, [rsp+48h+var_20]
0x18000a159  mov     r12, [rsp+48h+var_18]
0x18000a15e  mov     rdi, [rsp+48h+arg_18]
0x18000a163  mov     rsi, [rsp+48h+arg_10]
0x18000a168  mov     rbp, [rsp+48h+arg_8]
0x18000a16d  mov     r15, [rsp+48h+var_28]
0x18000a172  add     rsp, 38h
0x18000a176  pop     r14
0x18000a178  pop     rbx
0x18000a179  retn
0x18000a17a  add     rcx, 30h ; '0'; Buf
0x18000a17e  mov     edx, 0D22h; Value
0x18000a183  call    cs:__imp_longjmp
0x18000a18a  lea     rax, [rdx+1]
0x18000a18e  mov     [r14], rax
0x18000a191  mov     rcx, [rbx+88h]
0x18000a198  cmp     bp, 2
0x18000a19c  jl      loc_18000A28B
0x18000a1a2  cmp     bp, [rbx+50h]
0x18000a1a6  jnb     loc_18000A2C9
0x18000a1ac  mov     rcx, [rbx+58h]
0x18000a1b0  mov     r9, r12
0x18000a1b3  movsx   rax, bp
0x18000a1b7  mov     rdx, r14
0x18000a1ba  movzx   edi, word ptr [rcx+rax*2-4]
0x18000a1bf  movzx   eax, bp
0x18000a1c2  inc     bp
0x18000a1c5  mov     [rcx+rax*2], di
0x18000a1c9  mov     rcx, rbx
0x18000a1cc  mov     r8, [r14]
0x18000a1cf  call    Read255Short
0x18000a1d4  cmp     bp, [rbx+50h]
0x18000a1d8  jnb     loc_18000A2B2
0x18000a1de  mov     rcx, [rbx+58h]
0x18000a1e2  movzx   edx, bp
0x18000a1e5  inc     bp
0x18000a1e8  mov     [rcx+rdx*2], ax
0x18000a1ec  movzx   eax, bp
0x18000a1ef  cmp     ax, [rbx+50h]
0x18000a1f3  jnb     loc_18000A29B
0x18000a1f9  mov     ecx, eax
0x18000a1fb  movzx   ebp, ax
0x18000a1fe  mov     rax, [rbx+58h]
0x18000a202  mov     [rax+rcx*2], di
0x18000a206  jmp     loc_180009EEE
0x18000a20b  mov     rcx, [rbx+88h]
0x18000a212  mov     edx, 0D22h; Value
0x18000a217  add     rcx, 30h ; '0'; Buf
0x18000a21b  call    cs:__imp_longjmp
0x18000a222  xor     r8d, r8d
0x18000a225  xor     eax, eax
0x18000a227  cmp     ax, r9w
0x18000a22b  jge     loc_18000A016
0x18000a231  mov     rax, [rbx+68h]
0x18000a235  movzx   ecx, r8w
0x18000a239  inc     r8w
0x18000a23d  movzx   ecx, byte ptr [rcx+rax]
0x18000a241  mov     [rdx], cl
0x18000a243  inc     rdx
  ... truncated ...
```
