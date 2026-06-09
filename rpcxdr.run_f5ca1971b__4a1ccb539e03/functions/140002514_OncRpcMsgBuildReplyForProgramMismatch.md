# OncRpcMsgBuildReplyForProgramMismatch

- ea: `0x140002514`
- end: `0x140002886`
- name: `OncRpcMsgBuildReplyForProgramMismatch`
- size: `882`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x140002d84`
- `0x140002f50`
- `0x140006960`
- `0x140006990`

## callees

- `0x140001020`
- `0x1400020c0`
- `0x1400021b0`
- `0x140002514`
- `0x14000288c`
- `0x140002908`
- `0x140004b84`
- `0x140004ef0`
- `0x14000507c`
- `0x140005830`
- `0x1400059a4`
- `0x140005b40`
- `0x140005b88`
- `0x140005bac`
- `0x140005c28`

## pseudocode

```c
__int64 __fastcall OncRpcMsgBuildReplyForProgramMismatch(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6)
{
  __int64 v7; // rdi
  int v10; // edx
  int v11; // r11d
  int v12; // r14d
  unsigned int v13; // ecx
  unsigned int v14; // edx
  int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned int v24; // r9d
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v35; // [rsp+70h] [rbp+8h] BYREF

  v7 = a2 + 1120;
  v35 = a2 + 1152;
  *a1 = a2 + 1120;
  OncRpcMsgpInitializeReplyFields(a2, a2 + 1120);
  OncRpcMsgpSetReplyType(a2, v10, v11, a5, a6);
  v12 = OncRpcMsgCalculateGssOverhead(a2);
  v13 = a3 + v12 + OncRpcMsgCalculateRpcReplyOverhead();
  if ( v13 < a3
    || (v14 = (v13 + 15) & 0xFFFFFFF0, v14 < v13)
    || v13 > dword_14001A3F0
    || *(_WORD *)(a2 + 220) == 17 && v13 > 0xFE00 )
  {
    v15 = -1073741811;
    goto LABEL_42;
  }
  v15 = OncRpcBufMgrAllocate((unsigned int)&v35, v14, 4, 0, 0);
  if ( v15 < 0 )
    goto LABEL_42;
  if ( *(_QWORD *)(a2 + 2336) )
    *(_QWORD *)(*(_QWORD *)(v35 + 40) + 64LL) += 4LL;
  v16 = *(_QWORD *)(a2 + 1000);
  if ( v16 )
  {
    NfsStandardHeaderReferenceNoType(v16);
    *(_QWORD *)(v7 + 1000) = *(_QWORD *)(a2 + 1000);
  }
  v15 = OncRpcMsgpEncodeRpcReplyHeader(v7);
  if ( v15 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      41,
      WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids,
      *(unsigned int *)(v7 + 260),
      v15);
  }
  if ( v12 )
  {
    if ( !*(_DWORD *)(a2 + 284) && (unsigned int)(*(_DWORD *)(a2 + 312) - 1) <= 1 )
    {
      if ( *(_QWORD *)(v7 + 1000) )
      {
        XdrEncodeIntUnsafe(v7, 4);
        XdrEncodeIntUnsafe(v17, *(unsigned int *)(*(_QWORD *)(v7 + 1000) + 64LL));
        XdrEncodeIntUnsafe(v18, *(unsigned int *)(a2 + 440));
        XdrEncodeIntUnsafe(v19, *(unsigned int *)(a2 + 444));
        XdrEncodeIntUnsafe(v20, *(unsigned int *)(a2 + 448));
        XdrEncodeIntUnsafe(v21, *(unsigned int *)(a2 + 1024));
        if ( v24 )
          XdrEncodeOpaqueUnsafe(v22, v24, v23);
      }
      else
      {
        XdrEncodeIntUnsafe(v7, 0);
        XdrEncodeIntUnsafe(v25, *(unsigned int *)(a2 + 440));
        XdrEncodeIntUnsafe(v26, *(unsigned int *)(a2 + 444));
        XdrEncodeIntUnsafe(v27, 0);
        XdrEncodeIntUnsafe(v28, 0);
      }
      goto LABEL_35;
    }
    v29 = *(_DWORD *)(a2 + 320);
    if ( v29 == 2 )
    {
      if ( *(_DWORD *)(a2 + 312) == 1 )
        goto LABEL_35;
      v30 = *(_QWORD *)(a2 + 1192);
      if ( v30 )
        v30 = *(_QWORD *)(v30 + 64);
      *(_QWORD *)(v7 + 1088) = v30;
      *(_QWORD *)(*(_QWORD *)(a2 + 1192) + 64LL) += 4LL;
    }
    else
    {
      if ( v29 != 3 || *(_DWORD *)(a2 + 312) == 1 )
        goto LABEL_35;
      v31 = *(_QWORD *)(a2 + 1192);
      if ( v31 )
        v31 = *(_QWORD *)(v31 + 64);
      *(_QWORD *)(v7 + 1088) = v31;
      *(_QWORD *)(*(_QWORD *)(a2 + 1192) + 64LL) += 4LL;
      XdrNextMod4Boundary(v7);
      v32 = *(_QWORD *)(v7 + 1000);
      if ( !v32 )
      {
LABEL_34:
        XdrEncodeInt(v7, *(unsigned int *)(a2 + 316));
        goto LABEL_35;
      }
      *(_QWORD *)(*(_QWORD *)(a2 + 1192) + 64LL) += *(unsigned int *)(v32 + 116);
    }
    XdrNextMod4Boundary(v7);
    goto LABEL_34;
  }
LABEL_35:
  if ( v15 >= 0 )
  {
    v33 = *(_QWORD *)(a2 + 1192);
    if ( v33 )
      v33 = *(_QWORD *)(v33 + 64);
    *(_QWORD *)(v7 + 1040) = v33;
    NfsStandardHeaderReferenceNoType(a2 - 96);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        42,
        WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids,
        a2 - 96,
        *(_DWORD *)(a2 - 92));
    return (unsigned int)v15;
  }
LABEL_42:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x2Bu,
      (__int64)WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids,
      v15);
  *a1 = 0;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140002514  push    rbx
0x140002516  push    rbp
0x140002517  push    rsi
0x140002518  push    rdi
0x140002519  push    r14
0x14000251b  push    r15
0x14000251d  sub     rsp, 38h
0x140002521  lea     rax, [rdx+480h]
0x140002528  mov     rsi, rdx
0x14000252b  lea     rdi, [rdx+460h]
0x140002532  mov     [rsp+68h+arg_0], rax
0x140002537  mov     [rcx], rdi
0x14000253a  mov     r15, rcx
0x14000253d  mov     rcx, rsi
0x140002540  mov     rdx, rdi
0x140002543  mov     r11d, r9d
0x140002546  mov     ebx, r8d
0x140002549  call    OncRpcMsgpInitializeReplyFields
0x14000254e  mov     r10d, [rsp+68h+arg_28]
0x140002556  mov     r8d, r11d
0x140002559  mov     r9d, [rsp+68h+arg_20]
0x140002561  mov     rcx, rsi
0x140002564  mov     dword ptr [rsp+68h+var_48], r10d
0x140002569  call    OncRpcMsgpSetReplyType
0x14000256e  mov     rcx, rsi
0x140002571  call    OncRpcMsgCalculateGssOverhead
0x140002576  mov     r14d, eax
0x140002579  call    OncRpcMsgCalculateRpcReplyOverhead
0x14000257e  lea     ecx, [r14+rax]
0x140002582  add     ecx, ebx
0x140002584  cmp     ecx, ebx
0x140002586  jb      loc_140002838
0x14000258c  lea     edx, [rcx+0Fh]
0x14000258f  and     edx, 0FFFFFFF0h
0x140002592  cmp     edx, ecx
0x140002594  jb      loc_140002838
0x14000259a  cmp     ecx, cs:dword_14001A3F0
0x1400025a0  ja      loc_140002838
0x1400025a6  cmp     word ptr [rsi+0DCh], 11h
0x1400025ae  jnz     short loc_1400025BC
0x1400025b0  cmp     ecx, 0FE00h
0x1400025b6  ja      loc_140002838
0x1400025bc  xor     r9d, r9d
0x1400025bf  mov     [rsp+68h+var_48], 0
0x1400025c8  lea     rcx, [rsp+68h+arg_0]
0x1400025cd  lea     r8d, [r9+4]
0x1400025d1  call    OncRpcBufMgrAllocate
0x1400025d6  mov     ebx, eax
0x1400025d8  test    eax, eax
0x1400025da  js      loc_14000283D
0x1400025e0  cmp     qword ptr [rsi+920h], 0
0x1400025e8  jz      short loc_1400025F8
0x1400025ea  mov     rax, [rsp+68h+arg_0]
0x1400025ef  mov     rcx, [rax+28h]
0x1400025f3  add     qword ptr [rcx+40h], 4
0x1400025f8  mov     rcx, [rsi+3E8h]
0x1400025ff  test    rcx, rcx
0x140002602  jz      short loc_140002617
0x140002604  call    NfsStandardHeaderReferenceNoType
0x140002609  mov     rax, [rsi+3E8h]
0x140002610  mov     [rdi+3E8h], rax
0x140002617  mov     rcx, rdi
0x14000261a  call    OncRpcMsgpEncodeRpcReplyHeader
0x14000261f  mov     ebx, eax
0x140002621  test    eax, eax
0x140002623  jns     short loc_140002660
0x140002625  mov     rcx, cs:WPP_GLOBAL_Control
0x14000262c  lea     rax, WPP_GLOBAL_Control
0x140002633  cmp     rcx, rax
0x140002636  jz      short loc_140002660
0x140002638  mov     edx, [rcx+2Ch]
0x14000263b  test    dl, 4
0x14000263e  jz      short loc_140002660
0x140002640  mov     r9d, [rdi+104h]
0x140002647  lea     r8, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids
0x14000264e  mov     rcx, [rcx+18h]
0x140002652  mov     edx, 29h ; ')'
0x140002657  mov     dword ptr [rsp+68h+var_48], ebx
0x14000265b  call    WPP_SF_Dd
0x140002660  test    r14d, r14d
0x140002663  jz      loc_1400027D1
0x140002669  cmp     dword ptr [rsi+11Ch], 0
0x140002670  jnz     loc_14000272A
0x140002676  mov     eax, [rsi+138h]
0x14000267c  dec     eax
0x14000267e  cmp     eax, 1
0x140002681  ja      loc_14000272A
0x140002687  cmp     qword ptr [rdi+3E8h], 0
0x14000268f  mov     rcx, rdi
0x140002692  jz      short loc_1400026FA
0x140002694  mov     edx, 4
0x140002699  call    XdrEncodeIntUnsafe
0x14000269e  mov     rdx, [rdi+3E8h]
0x1400026a5  mov     edx, [rdx+40h]
0x1400026a8  call    XdrEncodeIntUnsafe
0x1400026ad  mov     edx, [rsi+1B8h]
0x1400026b3  call    XdrEncodeIntUnsafe
0x1400026b8  mov     edx, [rsi+1BCh]
0x1400026be  call    XdrEncodeIntUnsafe
0x1400026c3  mov     edx, [rsi+1C0h]
0x1400026c9  call    XdrEncodeIntUnsafe
0x1400026ce  mov     r9d, [rsi+400h]
0x1400026d5  mov     edx, r9d
0x1400026d8  mov     r8, [rsi+3F8h]
0x1400026df  call    XdrEncodeIntUnsafe
0x1400026e4  test    r9d, r9d
0x1400026e7  jz      loc_1400027D1
0x1400026ed  mov     edx, r9d
0x1400026f0  call    XdrEncodeOpaqueUnsafe
0x1400026f5  jmp     loc_1400027D1
0x1400026fa  xor     edx, edx
0x1400026fc  call    XdrEncodeIntUnsafe
0x140002701  mov     edx, [rsi+1B8h]
0x140002707  call    XdrEncodeIntUnsafe
0x14000270c  mov     edx, [rsi+1BCh]
0x140002712  call    XdrEncodeIntUnsafe
0x140002717  xor     edx, edx
0x140002719  call    XdrEncodeIntUnsafe
0x14000271e  xor     edx, edx
0x140002720  call    XdrEncodeIntUnsafe
0x140002725  jmp     loc_1400027D1
0x14000272a  mov     eax, [rsi+140h]
0x140002730  cmp     eax, 2
0x140002733  jnz     short loc_140002767
0x140002735  cmp     dword ptr [rsi+138h], 1
0x14000273c  jz      loc_1400027D1
0x140002742  mov     rax, [rsi+4A8h]
0x140002749  test    rax, rax
0x14000274c  jz      short loc_140002752
0x14000274e  mov     rax, [rax+40h]
0x140002752  mov     [rdi+440h], rax
0x140002759  mov     rax, [rsi+4A8h]
0x140002760  add     qword ptr [rax+40h], 4
0x140002765  jmp     short loc_1400027BB
0x140002767  cmp     eax, 3
0x14000276a  jnz     short loc_1400027D1
0x14000276c  cmp     dword ptr [rsi+138h], 1
0x140002773  jz      short loc_1400027D1
0x140002775  mov     rax, [rsi+4A8h]
0x14000277c  test    rax, rax
0x14000277f  jz      short loc_140002785
0x140002781  mov     rax, [rax+40h]
0x140002785  mov     [rdi+440h], rax
0x14000278c  mov     rcx, rdi
0x14000278f  mov     rax, [rsi+4A8h]
0x140002796  add     qword ptr [rax+40h], 4
0x14000279b  call    XdrNextMod4Boundary
0x1400027a0  mov     r8, [rdi+3E8h]
0x1400027a7  test    r8, r8
0x1400027aa  jz      short loc_1400027C3
0x1400027ac  mov     rcx, [rsi+4A8h]
0x1400027b3  mov     eax, [r8+74h]
0x1400027b7  add     [rcx+40h], rax
0x1400027bb  mov     rcx, rdi
0x1400027be  call    XdrNextMod4Boundary
0x1400027c3  mov     edx, [rsi+13Ch]
0x1400027c9  mov     rcx, rdi
0x1400027cc  call    XdrEncodeInt
0x1400027d1  test    ebx, ebx
0x1400027d3  js      short loc_14000283D
0x1400027d5  mov     rax, [rsi+4A8h]
0x1400027dc  test    rax, rax
0x1400027df  jz      short loc_1400027E5
0x1400027e1  mov     rax, [rax+40h]
0x1400027e5  lea     rcx, [rsi-60h]
0x1400027e9  mov     [rdi+410h], rax
0x1400027f0  call    NfsStandardHeaderReferenceNoType
0x1400027f5  mov     rax, cs:WPP_GLOBAL_Control
0x1400027fc  lea     rcx, WPP_GLOBAL_Control
0x140002803  cmp     rax, rcx
0x140002806  jz      short loc_140002876
0x140002808  mov     eax, [rax+2Ch]
0x14000280b  test    al, 40h
0x14000280d  jz      short loc_140002876
0x14000280f  mov     eax, [rsi-5Ch]
0x140002812  lea     r9, [rsi-60h]
0x140002816  mov     rcx, cs:WPP_GLOBAL_Control
0x14000281d  lea     r8, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids
0x140002824  mov     edx, 2Ah ; '*'
0x140002829  mov     dword ptr [rsp+68h+var_48], eax
0x14000282d  mov     rcx, [rcx+18h]
0x140002831  call    WPP_SF_qd
0x140002836  jmp     short loc_140002876
0x140002838  mov     ebx, 0C000000Dh
0x14000283d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002844  lea     rax, WPP_GLOBAL_Control
0x14000284b  cmp     rcx, rax
0x14000284e  jz      short loc_14000286F
0x140002850  mov     eax, [rcx+2Ch]
0x140002853  test    al, 4
0x140002855  jz      short loc_14000286F
0x140002857  mov     rcx, [rcx+18h]
0x14000285b  lea     r8, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids
0x140002862  mov     edx, 2Bh ; '+'
0x140002867  mov     r9d, ebx
0x14000286a  call    WPP_SF_d
0x14000286f  mov     qword ptr [r15], 0
0x140002876  mov     eax, ebx
0x140002878  add     rsp, 38h
0x14000287c  pop     r15
0x14000287e  pop     r14
0x140002880  pop     rdi
0x140002881  pop     rsi
0x140002882  pop     rbp
0x140002883  pop     rbx
0x140002884  retn
```
