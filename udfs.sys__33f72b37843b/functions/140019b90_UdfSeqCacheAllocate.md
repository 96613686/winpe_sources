# UdfSeqCacheAllocate

- ea: `0x140019b90`
- end: `0x140019f56`
- name: `UdfSeqCacheAllocate`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14003bb18`

## callees

- `0x14000ca10`
- `0x14001093c`
- `0x140019b90`
- `0x14001b610`
- `0x14001c080`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140019bbe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140019d4c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140019ea9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140019ef2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140019bbe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140019d4c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140019ea9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140019ef2`
- `ntoskrnl!ExInitializeResourceLite` at `0x140019dc0`
- `ntoskrnl!ExInitializeResourceLite` at `0x140019dd3`
- `ntoskrnl!ExInitializeResourceLite` at `0x140019dc0`
- `ntoskrnl!ExInitializeResourceLite` at `0x140019dd3`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140019ede`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140019f27`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140019ede`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x140019f27`
- `ntoskrnl!KeInitializeEvent` at `0x140019def`
- `ntoskrnl!KeInitializeEvent` at `0x140019e07`
- `ntoskrnl!KeInitializeEvent` at `0x140019def`
- `ntoskrnl!KeInitializeEvent` at `0x140019e07`
- `ntoskrnl!IoAllocateIrp` at `0x140019d86`
- `ntoskrnl!IoAllocateIrp` at `0x140019d86`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheAllocate(__int64 a1, unsigned int a2, unsigned int a3, int a4, _QWORD *a5)
{
  char *PoolWithTag; // rax
  char *v10; // rbx
  unsigned int v11; // edi
  unsigned int v12; // r14d
  unsigned int v13; // ecx
  unsigned int v14; // r9d
  unsigned int v15; // r8d
  bool v16; // cf
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21; // ecx
  int v22; // edi
  int v23; // eax
  unsigned int v24; // edi
  SIZE_T v25; // r14
  PVOID v26; // rax
  PVOID v27; // rbp
  PIRP Irp; // rax
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 i; // rcx
  __int64 v34; // rax
  char v35; // al
  LARGE_MCB *v36; // rax
  LARGE_MCB *v37; // rax

  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1552, 0x2F8u, 0x57666455u);
  v10 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, 0x2F8u);
  *a5 = v10;
  *((_DWORD *)v10 + 145) = a3;
  *((_DWORD *)v10 + 146) = a4;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0x1Du) )
  {
    WPP_SF_dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      10,
      WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids,
      a3,
      a4);
  }
  *(_DWORD *)v10 = 49809726;
  v11 = a2 >> *(_DWORD *)(a1 + 72);
  *((_DWORD *)v10 + 144) = v11;
  v12 = a3 >> *(_DWORD *)(a1 + 72);
  *((_DWORD *)v10 + 2) = v12;
  v13 = 2 * v12;
  *((_QWORD *)v10 + 90) = a1;
  v14 = v11 % v12;
  v15 = v11 / v12;
  if ( v11 % v12 <= 0x20 )
  {
    v16 = v11 < v13;
  }
  else
  {
    v16 = v11 < v13;
    if ( v11 > v13 )
    {
      v17 = v14 % v15;
      v18 = (v12 + v14 / v15) & 0xFFFFFFDF;
      *((_DWORD *)v10 + 2) = v18;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0x1Du) )
      {
        WPP_SF_dDd(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), v17, v18, 2 * v14, v18, 2 * v18);
      }
      v19 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0x1Du) )
      {
        v20 = 12;
LABEL_20:
        WPP_SF_d(*(_QWORD *)(v19 + 24), v20, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids);
        goto LABEL_21;
      }
      goto LABEL_21;
    }
  }
  if ( v16 )
  {
    *((_DWORD *)v10 + 2) = (v11 >> 1) & 0x7FFFFFDF;
    v19 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL), 0x1Du) )
      {
        v20 = 13;
        goto LABEL_20;
      }
    }
  }
LABEL_21:
  v21 = *(_DWORD *)(a1 + 72);
  v22 = *((_DWORD *)v10 + 2);
  *(_DWORD *)(a1 + 48) |= 0x200000u;
  v23 = v22 << v21;
  v24 = 32 * v22;
  v25 = v24 + 8 * (v24 + v23);
  v26 = ExAllocatePoolWithTag((POOL_TYPE)1041, v25, 0x57666455u);
  v27 = v26;
  if ( !ExPoolZeroingNativelySupported && v26 )
    memset(v26, 0, (unsigned int)v25);
  *((_QWORD *)v10 + 89) = v27;
  Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 24) + 76LL), 0);
  *((_QWORD *)v10 + 81) = Irp;
  if ( !Irp )
    return 3221225626LL;
  memset(*((void **)v10 + 89), 0, v25);
  ExInitializeResourceLite((PERESOURCE)(v10 + 344));
  ExInitializeResourceLite((PERESOURCE)(v10 + 448));
  KeInitializeEvent((PRKEVENT)(v10 + 664), SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)v10 + 23, SynchronizationEvent, 1u);
  v30 = 0;
  *((_QWORD *)v10 + 79) = v10 + 624;
  *((_QWORD *)v10 + 78) = v10 + 624;
  v31 = *((_QWORD *)v10 + 89);
  do
  {
    v32 = 5 * v30++;
    *(_QWORD *)&v10[8 * v32 + 40] = v31;
    *(_DWORD *)&v10[8 * v32 + 28] = *((_DWORD *)v10 + 2);
    v31 += (unsigned int)(*((_DWORD *)v10 + 2) << *(_DWORD *)(a1 + 72));
  }
  while ( v30 != 8 );
  for ( i = 0; i != 8; ++i )
  {
    v34 = 5 * i;
    *(_QWORD *)&v10[8 * v34 + 56] = v31;
    v31 += v24;
  }
  *((_QWORD *)v10 + 87) = v31;
  v35 = -(*(_DWORD *)(a1 + 84) & 8);
  *((_DWORD *)v10 + 1) |= 0x23u;
  *((_DWORD *)v10 + 3) = v35 != 0 ? 16 : 32;
  if ( !_bittest((const signed __int32 *)(a1 + 48), 0x1Du) )
    return 0;
  v36 = (LARGE_MCB *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x20u, 0x74666455u);
  if ( !ExPoolZeroingNativelySupported && v36 )
  {
    *(_OWORD *)&v36->GuardedMutex = 0;
    *(_OWORD *)&v36->BaseMcb.PoolType = 0;
  }
  *((_QWORD *)v10 + 91) = v36;
  if ( v36 )
  {
    FsRtlInitializeLargeMcb(v36, PagedPool);
    v37 = (LARGE_MCB *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x20u, 0x74666455u);
    if ( !ExPoolZeroingNativelySupported )
    {
      if ( v37 )
      {
        *(_OWORD *)&v37->GuardedMutex = 0;
        *(_OWORD *)&v37->BaseMcb.PoolType = 0;
      }
    }
    *((_QWORD *)v10 + 92) = v37;
    if ( v37 )
    {
      FsRtlInitializeLargeMcb(v37, PagedPool);
      *((_DWORD *)v10 + 186) = 0;
      return 0;
    }
  }
  return 3221225495LL;
}

```

## disassembly

```asm
0x140019b90  push    rbx
0x140019b92  push    rbp
0x140019b93  push    rsi
0x140019b94  push    rdi
0x140019b95  push    r12
0x140019b97  push    r13
0x140019b99  push    r14
0x140019b9b  sub     rsp, 30h
0x140019b9f  mov     r14d, r8d
0x140019ba2  mov     edi, edx
0x140019ba4  mov     rsi, rcx
0x140019ba7  mov     r12d, 2F8h
0x140019bad  mov     edx, r12d; NumberOfBytes
0x140019bb0  mov     r8d, 57666455h; Tag
0x140019bb6  mov     ecx, 610h; PoolType
0x140019bbb  mov     ebp, r9d
0x140019bbe  call    cs:__imp_ExAllocatePoolWithTag
0x140019bc5  nop     dword ptr [rax+rax+00h]
0x140019bca  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140019bd1  mov     rbx, rax
0x140019bd4  jnz     short loc_140019BE8
0x140019bd6  test    rax, rax
0x140019bd9  jz      short loc_140019BE8
0x140019bdb  mov     r8d, r12d; Size
0x140019bde  xor     edx, edx; Val
0x140019be0  mov     rcx, rax; void *
0x140019be3  call    memset
0x140019be8  mov     rax, [rsp+68h+arg_20]
0x140019bf0  mov     [rax], rbx
0x140019bf3  mov     [rbx+244h], r14d
0x140019bfa  mov     [rbx+248h], ebp
0x140019c00  mov     rcx, cs:WPP_GLOBAL_Control
0x140019c07  lea     r13, WPP_GLOBAL_Control
0x140019c0e  cmp     rcx, r13
0x140019c11  jz      short loc_140019C36
0x140019c13  bt      dword ptr [rcx+2Ch], 1Dh
0x140019c18  jnb     short loc_140019C36
0x140019c1a  mov     rcx, [rcx+18h]
0x140019c1e  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x140019c25  mov     edx, 0Ah
0x140019c2a  mov     [rsp+68h+var_48], ebp
0x140019c2e  mov     r9d, r14d
0x140019c31  call    WPP_SF_dd
0x140019c36  mov     dword ptr [rbx], 2F8093Eh
0x140019c3c  xor     edx, edx
0x140019c3e  mov     ecx, [rsi+48h]
0x140019c41  shr     edi, cl
0x140019c43  mov     [rbx+240h], edi
0x140019c49  mov     eax, edi
0x140019c4b  mov     ecx, [rsi+48h]
0x140019c4e  shr     r14d, cl
0x140019c51  div     r14d
0x140019c54  mov     [rbx+8], r14d
0x140019c58  lea     ecx, [r14+r14]
0x140019c5c  mov     [rbx+2D0h], rsi
0x140019c63  mov     r9d, edx
0x140019c66  mov     r8d, eax
0x140019c69  cmp     edx, 20h ; ' '
0x140019c6c  jbe     short loc_140019CDE
0x140019c6e  cmp     edi, ecx
0x140019c70  jbe     short loc_140019CE0
0x140019c72  xor     edx, edx
0x140019c74  mov     eax, r9d
0x140019c77  div     r8d
0x140019c7a  lea     r8d, [r14+rax]
0x140019c7e  and     r8d, 0FFFFFFDFh
0x140019c82  mov     [rbx+8], r8d
0x140019c86  mov     rcx, cs:WPP_GLOBAL_Control
0x140019c8d  cmp     rcx, r13
0x140019c90  jz      short loc_140019CB6
0x140019c92  bt      dword ptr [rcx+2Ch], 1Dh
0x140019c97  jnb     short loc_140019CB6
0x140019c99  mov     rcx, [rcx+18h]
0x140019c9d  lea     eax, [r8+r8]
0x140019ca1  mov     [rsp+68h+var_40], eax
0x140019ca5  add     r9d, r9d
0x140019ca8  mov     [rsp+68h+var_48], r8d
0x140019cad  call    WPP_SF_dDd
0x140019cb2  mov     r8d, [rbx+8]
0x140019cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140019cbd  cmp     rcx, r13
0x140019cc0  jz      short loc_140019D25
0x140019cc2  bt      dword ptr [rcx+2Ch], 1Dh
0x140019cc7  jnb     short loc_140019D25
0x140019cc9  mov     eax, [rbx+240h]
0x140019ccf  xor     edx, edx
0x140019cd1  div     r8d
0x140019cd4  mov     r9d, edx
0x140019cd7  mov     edx, 0Ch
0x140019cdc  jmp     short loc_140019D15
0x140019cde  cmp     edi, ecx
0x140019ce0  jnb     short loc_140019D25
0x140019ce2  mov     r8d, edi
0x140019ce5  shr     r8d, 1
0x140019ce8  and     r8d, 7FFFFFDFh
0x140019cef  mov     [rbx+8], r8d
0x140019cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x140019cfa  cmp     rcx, r13
0x140019cfd  jz      short loc_140019D25
0x140019cff  bt      dword ptr [rcx+2Ch], 1Dh
0x140019d04  jnb     short loc_140019D25
0x140019d06  xor     edx, edx
0x140019d08  mov     eax, edi
0x140019d0a  div     r8d
0x140019d0d  mov     r9d, edx
0x140019d10  mov     edx, 0Dh
0x140019d15  mov     rcx, [rcx+18h]
0x140019d19  lea     r8, WPP_091ecc37555d3ea49b7bb42fddee33c5_Traceguids
0x140019d20  call    WPP_SF_d
0x140019d25  mov     eax, [rbx+8]
0x140019d28  mov     r8d, 57666455h; Tag
0x140019d2e  mov     ecx, [rsi+48h]
0x140019d31  mov     edi, eax
0x140019d33  bts     dword ptr [rsi+30h], 15h
0x140019d38  shl     eax, cl
0x140019d3a  mov     ecx, 411h; PoolType
0x140019d3f  shl     edi, 5
0x140019d42  add     eax, edi
0x140019d44  lea     eax, [rdi+rax*8]
0x140019d47  mov     edx, eax; NumberOfBytes
0x140019d49  mov     r14d, eax
0x140019d4c  call    cs:__imp_ExAllocatePoolWithTag
0x140019d53  nop     dword ptr [rax+rax+00h]
0x140019d58  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140019d5f  mov     rbp, rax
0x140019d62  jnz     short loc_140019D76
0x140019d64  test    rax, rax
0x140019d67  jz      short loc_140019D76
0x140019d69  mov     r8d, r14d; Size
0x140019d6c  xor     edx, edx; Val
0x140019d6e  mov     rcx, rax; void *
0x140019d71  call    memset
0x140019d76  mov     [rbx+2C8h], rbp
0x140019d7d  xor     edx, edx; ChargeQuota
0x140019d7f  mov     rcx, [rsi+18h]
0x140019d83  mov     cl, [rcx+4Ch]; StackSize
0x140019d86  call    cs:__imp_IoAllocateIrp
0x140019d8d  nop     dword ptr [rax+rax+00h]
0x140019d92  mov     [rbx+288h], rax
0x140019d99  test    rax, rax
0x140019d9c  jnz     short loc_140019DA8
0x140019d9e  mov     eax, 0C000009Ah
0x140019da3  jmp     loc_140019F3F
0x140019da8  mov     rcx, [rbx+2C8h]; void *
0x140019daf  mov     r8, r14; Size
0x140019db2  xor     edx, edx; Val
0x140019db4  call    memset
0x140019db9  lea     rcx, [rbx+158h]; Resource
0x140019dc0  call    cs:__imp_ExInitializeResourceLite
0x140019dc7  nop     dword ptr [rax+rax+00h]
0x140019dcc  lea     rcx, [rbx+1C0h]; Resource
0x140019dd3  call    cs:__imp_ExInitializeResourceLite
0x140019dda  nop     dword ptr [rax+rax+00h]
0x140019ddf  xor     r8d, r8d; State
0x140019de2  lea     rcx, [rbx+298h]; Event
0x140019de9  lea     ebp, [r8+1]
0x140019ded  mov     edx, ebp; Type
0x140019def  call    cs:__imp_KeInitializeEvent
0x140019df6  nop     dword ptr [rax+rax+00h]
0x140019dfb  lea     rcx, [rbx+228h]; Event
0x140019e02  mov     r8b, bpl; State
0x140019e05  mov     edx, ebp; Type
0x140019e07  call    cs:__imp_KeInitializeEvent
0x140019e0e  nop     dword ptr [rax+rax+00h]
0x140019e13  lea     rax, [rbx+270h]
0x140019e1a  xor     r8d, r8d
0x140019e1d  mov     [rax+8], rax
0x140019e21  mov     [rax], rax
0x140019e24  mov     rdx, [rbx+2C8h]
0x140019e2b  lea     rcx, [r8+r8*4]
0x140019e2f  add     r8, rbp
0x140019e32  mov     [rbx+rcx*8+28h], rdx
0x140019e37  mov     eax, [rbx+8]
0x140019e3a  mov     [rbx+rcx*8+1Ch], eax
0x140019e3e  mov     eax, [rbx+8]
0x140019e41  mov     ecx, [rsi+48h]
0x140019e44  shl     eax, cl
0x140019e46  add     rdx, rax
0x140019e49  cmp     r8, 8
0x140019e4d  jnz     short loc_140019E2B
0x140019e4f  mov     r8d, edi
0x140019e52  xor     ecx, ecx
0x140019e54  lea     rax, [rcx+rcx*4]
0x140019e58  add     rcx, rbp
0x140019e5b  mov     [rbx+rax*8+38h], rdx
0x140019e60  add     rdx, r8
0x140019e63  cmp     rcx, 8
0x140019e67  jnz     short loc_140019E54
0x140019e69  mov     [rbx+2B8h], rdx
0x140019e70  mov     r14d, 20h ; ' '
0x140019e76  mov     eax, [rsi+54h]
0x140019e79  and     al, cl
0x140019e7b  neg     al
0x140019e7d  sbb     ecx, ecx
0x140019e7f  or      dword ptr [rbx+4], 23h
0x140019e83  and     ecx, 0FFFFFFF0h
0x140019e86  add     ecx, r14d
0x140019e89  mov     [rbx+0Ch], ecx
0x140019e8c  bt      dword ptr [rsi+30h], 1Dh
0x140019e91  jnb     loc_140019F3D
0x140019e97  mov     edi, 74666455h
0x140019e9c  mov     esi, 401h
0x140019ea1  mov     r8d, edi; Tag
0x140019ea4  mov     ecx, esi; PoolType
0x140019ea6  mov     edx, r14d; NumberOfBytes
0x140019ea9  call    cs:__imp_ExAllocatePoolWithTag
0x140019eb0  nop     dword ptr [rax+rax+00h]
0x140019eb5  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140019ebc  jnz     short loc_140019ECD
0x140019ebe  test    rax, rax
0x140019ec1  jz      short loc_140019ECD
0x140019ec3  xorps   xmm0, xmm0
0x140019ec6  movups  xmmword ptr [rax], xmm0
0x140019ec9  movups  xmmword ptr [rax+10h], xmm0
0x140019ecd  mov     [rbx+2D8h], rax
0x140019ed4  test    rax, rax
0x140019ed7  jz      short loc_140019F4F
0x140019ed9  mov     edx, ebp; PoolType
0x140019edb  mov     rcx, rax; Mcb
0x140019ede  call    cs:__imp_FsRtlInitializeLargeMcb
0x140019ee5  nop     dword ptr [rax+rax+00h]
0x140019eea  mov     r8d, edi; Tag
0x140019eed  mov     rdx, r14; NumberOfBytes
0x140019ef0  mov     ecx, esi; PoolType
0x140019ef2  call    cs:__imp_ExAllocatePoolWithTag
0x140019ef9  nop     dword ptr [rax+rax+00h]
0x140019efe  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140019f05  jnz     short loc_140019F16
0x140019f07  test    rax, rax
0x140019f0a  jz      short loc_140019F16
0x140019f0c  xorps   xmm0, xmm0
0x140019f0f  movups  xmmword ptr [rax], xmm0
0x140019f12  movups  xmmword ptr [rax+10h], xmm0
0x140019f16  mov     [rbx+2E0h], rax
0x140019f1d  test    rax, rax
0x140019f20  jz      short loc_140019F4F
0x140019f22  mov     edx, ebp; PoolType
0x140019f24  mov     rcx, rax; Mcb
0x140019f27  call    cs:__imp_FsRtlInitializeLargeMcb
0x140019f2e  nop     dword ptr [rax+rax+00h]
0x140019f33  mov     dword ptr [rbx+2E8h], 0
0x140019f3d  xor     eax, eax
0x140019f3f  add     rsp, 30h
0x140019f43  pop     r14
0x140019f45  pop     r13
0x140019f47  pop     r12
0x140019f49  pop     rdi
0x140019f4a  pop     rsi
0x140019f4b  pop     rbp
0x140019f4c  pop     rbx
0x140019f4d  retn
0x140019f4f  mov     eax, 0C0000017h
0x140019f54  jmp     short loc_140019F3F
```
