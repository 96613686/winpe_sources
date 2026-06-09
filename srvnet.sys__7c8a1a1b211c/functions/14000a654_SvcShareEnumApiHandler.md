# SvcShareEnumApiHandler

- ea: `0x14000a654`
- end: `0x14000a961`
- name: `SvcShareEnumApiHandler`
- size: `781`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, int, PVOID)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000a1f0`

## callees

- `0x140004a60`
- `0x140007160`
- `0x14000a654`
- `0x14000bc90`
- `0x14000c260`
- `0x14000cd60`
- `0x14004c4d4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000a6c6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000a6df`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000a6c6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000a6df`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14000a80d`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14000a8ac`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14000a80d`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x14000a8ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a8e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a8f0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a8e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a8f0`

## pseudocode

```c
__int64 __fastcall SvcShareEnumApiHandler(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        int a4,
        ULONG DeleteCount,
        int a6,
        PVOID RestartKey)
{
  int v7; // esi
  int v10; // edi
  int v11; // r15d
  int v12; // r12d
  __int64 v13; // rax
  __int64 v14; // rsi
  int v15; // r8d
  __int64 v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // r13
  unsigned int v19; // esi
  int *v20; // r14
  unsigned int v21; // eax
  int v22; // r8d
  __int64 v24; // [rsp+40h] [rbp-61h] BYREF
  __int64 v25; // [rsp+48h] [rbp-59h] BYREF
  PRTL_AVL_TABLE Table; // [rsp+50h] [rbp-51h]
  __int64 v27; // [rsp+58h] [rbp-49h]
  PERESOURCE Resource; // [rsp+60h] [rbp-41h]
  PERESOURCE v29; // [rsp+68h] [rbp-39h]
  __int128 Buffer; // [rsp+70h] [rbp-31h] BYREF
  __int128 v31; // [rsp+80h] [rbp-21h]
  __int64 v32; // [rsp+90h] [rbp-11h]
  char v33; // [rsp+F0h] [rbp+4Fh]
  unsigned int v34; // [rsp+F8h] [rbp+57h] BYREF
  unsigned int v35; // [rsp+100h] [rbp+5Fh]
  char v36; // [rsp+108h] [rbp+67h]

  v7 = a2[23];
  v36 = 0;
  v32 = 0;
  RestartKey = 0;
  DeleteCount = 0;
  v24 = 0;
  v25 = a3;
  v34 = a4 & 0xFFFFFFFE;
  v35 = 0;
  Buffer = 0;
  v10 = 0;
  v11 = 0;
  v31 = 0;
  v12 = 0;
  a6 = v7;
  v29 = (PERESOURCE)(a1 + 200);
  ExAcquireResourceSharedLite((PERESOURCE)(a1 + 200), 1u);
  Resource = (PERESOURCE)(a1 + 96);
  ExAcquireResourceSharedLite((PERESOURCE)(a1 + 96), 1u);
  if ( (a2[18] & 1) != 0 )
  {
    v13 = SrvAdminLookupShareByName(a1, a2, a2 + 4);
    v14 = v13;
    if ( !v13 )
      goto LABEL_22;
    if ( (unsigned __int8)FilterShares(a2, v13, &v24) )
    {
      v35 = SizeShares(a2, v14);
      v12 = 1;
      if ( v35 <= v34 )
      {
        v10 = SrvAdminFillRoutineAndHandleSeh((_DWORD)a2, v14, v15, (unsigned int)&v25, (__int64)&v34);
        v11 = v10 >= 0;
      }
    }
LABEL_21:
    SrvAdminDereferenceShare(v14);
    goto LABEL_22;
  }
  if ( v7 )
  {
    v16 = RfsTableLookup(*(PEX_SPIN_LOCK *)(a1 + 72));
    v27 = v16;
    v14 = v16;
    if ( !v16 )
      goto LABEL_22;
    v33 = 1;
    Table = (PRTL_AVL_TABLE)(a1 + 408);
    v17 = RtlEnumerateGenericTableLikeADirectory(
            (PRTL_AVL_TABLE)(a1 + 408),
            0,
            0,
            1u,
            &RestartKey,
            &DeleteCount,
            (PVOID)(v16 + 8));
  }
  else
  {
    v33 = 0;
    v32 = 0;
    v27 = 0;
    Table = (PRTL_AVL_TABLE)(a1 + 408);
    v14 = 0;
    Buffer = 0;
    v31 = 0;
    v17 = RtlEnumerateGenericTableLikeADirectory(
            (PRTL_AVL_TABLE)(a1 + 408),
            0,
            0,
            0,
            &RestartKey,
            &DeleteCount,
            &Buffer);
  }
  v18 = v17;
  if ( v17 )
  {
    v19 = 0;
    do
    {
      v20 = (int *)v18[4];
      if ( (unsigned __int8)FilterShares(a2, v20, &v24) )
      {
        v21 = SizeShares(a2, v20);
        v19 += v21;
        ++v12;
        if ( v21 > v34 || v36 )
        {
          v36 = 1;
        }
        else
        {
          v10 = SrvAdminFillRoutineAndHandleSeh((_DWORD)a2, (_DWORD)v20, v22, (unsigned int)&v25, (__int64)&v34);
          if ( v10 < 0 )
            break;
          ++v11;
          a6 = *v20;
        }
      }
      v18 = RtlEnumerateGenericTableLikeADirectory(Table, 0, 0, 1u, &RestartKey, &DeleteCount, v18);
    }
    while ( v18 );
    v35 = v19;
    v14 = v27;
  }
  if ( v33 )
    goto LABEL_21;
LABEL_22:
  ExReleaseResourceLite(Resource);
  ExReleaseResourceLite(v29);
  a2[22] = v35;
  a2[20] = v11;
  a2[21] = v12;
  if ( v10 >= 0 )
  {
    if ( v11 || !v12 )
    {
      if ( v36 )
      {
        a2[23] = a6;
        a2[17] = 234;
      }
      else
      {
        a2[17] = 0;
        a2[23] = 0;
      }
    }
    else
    {
      a2[17] = 2123;
    }
    return 0;
  }
  else
  {
    a2[17] = 2140;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000a654  push    rbp
0x14000a656  push    rbx
0x14000a657  push    rsi
0x14000a658  push    rdi
0x14000a659  push    r12
0x14000a65b  push    r13
0x14000a65d  push    r14
0x14000a65f  push    r15
0x14000a661  lea     rbp, [rsp-7]
0x14000a666  sub     rsp, 0A8h
0x14000a66d  mov     esi, [rdx+5Ch]
0x14000a670  xor     r13d, r13d
0x14000a673  xor     eax, eax
0x14000a675  mov     [rbp+3Fh+arg_18], r13b
0x14000a679  xorps   xmm0, xmm0
0x14000a67c  mov     [rbp+3Fh+var_50], rax
0x14000a680  lea     rax, [rcx+0C8h]
0x14000a687  mov     [rbp+3Fh+arg_30], r13
0x14000a68b  mov     rbx, rdx
0x14000a68e  mov     [rbp+3Fh+arg_20], r13d
0x14000a692  mov     r14, rcx
0x14000a695  mov     [rbp+3Fh+var_A0], r13
0x14000a699  and     r9d, 0FFFFFFFEh
0x14000a69d  mov     [rbp+3Fh+var_98], r8
0x14000a6a1  mov     rcx, rax; Resource
0x14000a6a4  mov     [rbp+3Fh+arg_8], r9d
0x14000a6a8  mov     dl, 1; Wait
0x14000a6aa  mov     [rbp+3Fh+arg_10], r13d
0x14000a6ae  movups  [rbp+3Fh+var_70], xmm0
0x14000a6b2  mov     edi, r13d
0x14000a6b5  mov     r15d, r13d
0x14000a6b8  movups  [rbp+3Fh+var_60], xmm0
0x14000a6bc  mov     r12d, r13d
0x14000a6bf  mov     [rbp+3Fh+arg_28], esi
0x14000a6c2  mov     [rbp+3Fh+var_78], rax
0x14000a6c6  call    cs:__imp_ExAcquireResourceSharedLite
0x14000a6cd  nop     dword ptr [rax+rax+00h]
0x14000a6d2  lea     rax, [r14+60h]
0x14000a6d6  mov     dl, 1; Wait
0x14000a6d8  mov     rcx, rax; Resource
0x14000a6db  mov     [rbp+3Fh+Resource], rax
0x14000a6df  call    cs:__imp_ExAcquireResourceSharedLite
0x14000a6e6  nop     dword ptr [rax+rax+00h]
0x14000a6eb  mov     eax, [rbx+48h]
0x14000a6ee  test    al, 1
0x14000a6f0  jz      short loc_14000A76C
0x14000a6f2  lea     r8, [rbx+10h]
0x14000a6f6  mov     rdx, rbx
0x14000a6f9  mov     rcx, r14
0x14000a6fc  call    SrvAdminLookupShareByName
0x14000a701  mov     rsi, rax
0x14000a704  test    rax, rax
0x14000a707  jz      loc_14000A8DC
0x14000a70d  lea     r8, [rbp+3Fh+var_A0]
0x14000a711  mov     rdx, rax
0x14000a714  mov     rcx, rbx
0x14000a717  call    FilterShares
0x14000a71c  test    al, al
0x14000a71e  jz      loc_14000A8D4
0x14000a724  mov     rdx, rsi
0x14000a727  mov     rcx, rbx
0x14000a72a  call    SizeShares
0x14000a72f  lea     r14d, [r13+1]
0x14000a733  mov     [rbp+3Fh+arg_10], eax
0x14000a736  mov     r12d, r14d
0x14000a739  cmp     eax, [rbp+3Fh+arg_8]
0x14000a73c  ja      loc_14000A8D4
0x14000a742  lea     rax, [rbp+3Fh+arg_8]
0x14000a746  mov     rdx, rsi
0x14000a749  lea     r9, [rbp+3Fh+var_98]
0x14000a74d  mov     [rsp+0E0h+RestartKey], rax
0x14000a752  mov     rcx, rbx
0x14000a755  call    SrvAdminFillRoutineAndHandleSeh
0x14000a75a  mov     edi, eax
0x14000a75c  test    eax, eax
0x14000a75e  js      loc_14000A8D4
0x14000a764  mov     r15d, r14d
0x14000a767  jmp     loc_14000A8D4
0x14000a76c  test    esi, esi
0x14000a76e  jz      short loc_14000A7C0
0x14000a770  mov     rcx, [r14+48h]; SpinLock
0x14000a774  mov     edx, esi
0x14000a776  call    RfsTableLookup
0x14000a77b  mov     [rbp+3Fh+var_88], rax
0x14000a77f  mov     rsi, rax
0x14000a782  test    rax, rax
0x14000a785  jz      loc_14000A8DC
0x14000a78b  add     r14, 198h
0x14000a792  mov     [rbp+3Fh+arg_0], 1
0x14000a796  add     rax, 8
0x14000a79a  mov     [rbp+3Fh+Table], r14
0x14000a79e  mov     [rsp+0E0h+Buffer], rax
0x14000a7a3  mov     r9d, 1
0x14000a7a9  lea     rax, [rbp+3Fh+arg_20]
0x14000a7ad  mov     rcx, r14
0x14000a7b0  mov     [rsp+0E0h+DeleteCount], rax
0x14000a7b5  lea     rax, [rbp+3Fh+arg_30]
0x14000a7b9  mov     [rsp+0E0h+RestartKey], rax
0x14000a7be  jmp     short loc_14000A808
0x14000a7c0  xor     eax, eax
0x14000a7c2  mov     [rbp+3Fh+arg_0], r13b
0x14000a7c6  lea     rcx, [rbp+3Fh+var_70]
0x14000a7ca  mov     [rbp+3Fh+var_50], rax
0x14000a7ce  mov     [rsp+0E0h+Buffer], rcx; Buffer
0x14000a7d3  lea     rax, [r14+198h]
0x14000a7da  lea     rcx, [rbp+3Fh+arg_20]
0x14000a7de  mov     [rbp+3Fh+var_88], r13
0x14000a7e2  mov     [rsp+0E0h+DeleteCount], rcx; DeleteCount
0x14000a7e7  xorps   xmm0, xmm0
0x14000a7ea  lea     rcx, [rbp+3Fh+arg_30]
0x14000a7ee  mov     [rbp+3Fh+Table], rax
0x14000a7f2  mov     [rsp+0E0h+RestartKey], rcx; RestartKey
0x14000a7f7  mov     rsi, r13
0x14000a7fa  mov     rcx, rax; Table
0x14000a7fd  xor     r9d, r9d; NextFlag
0x14000a800  movups  [rbp+3Fh+var_70], xmm0
0x14000a804  movups  [rbp+3Fh+var_60], xmm0
0x14000a808  xor     r8d, r8d; MatchData
0x14000a80b  xor     edx, edx; MatchFunction
0x14000a80d  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x14000a814  nop     dword ptr [rax+rax+00h]
0x14000a819  mov     r13, rax
0x14000a81c  test    rax, rax
0x14000a81f  jz      loc_14000A8CB
0x14000a825  mov     esi, edi
0x14000a827  mov     r14, [r13+20h]
0x14000a82b  lea     r8, [rbp+3Fh+var_A0]
0x14000a82f  mov     rdx, r14
0x14000a832  mov     rcx, rbx
0x14000a835  call    FilterShares
0x14000a83a  test    al, al
0x14000a83c  jz      short loc_14000A886
0x14000a83e  mov     rdx, r14
0x14000a841  mov     rcx, rbx
0x14000a844  call    SizeShares
0x14000a849  add     esi, eax
0x14000a84b  inc     r12d
0x14000a84e  cmp     eax, [rbp+3Fh+arg_8]
0x14000a851  ja      short loc_14000A882
0x14000a853  cmp     [rbp+3Fh+arg_18], 0
0x14000a857  jnz     short loc_14000A882
0x14000a859  lea     rax, [rbp+3Fh+arg_8]
0x14000a85d  mov     rdx, r14
0x14000a860  lea     r9, [rbp+3Fh+var_98]
0x14000a864  mov     [rsp+0E0h+RestartKey], rax
0x14000a869  mov     rcx, rbx
0x14000a86c  call    SrvAdminFillRoutineAndHandleSeh
0x14000a871  mov     edi, eax
0x14000a873  test    eax, eax
0x14000a875  js      short loc_14000A8C4
0x14000a877  mov     eax, [r14]
0x14000a87a  inc     r15d
0x14000a87d  mov     [rbp+3Fh+arg_28], eax
0x14000a880  jmp     short loc_14000A886
0x14000a882  mov     [rbp+3Fh+arg_18], 1
0x14000a886  mov     rcx, [rbp+3Fh+Table]; Table
0x14000a88a  lea     rax, [rbp+3Fh+arg_20]
0x14000a88e  mov     [rsp+0E0h+Buffer], r13; Buffer
0x14000a893  mov     r9d, 1; NextFlag
0x14000a899  mov     [rsp+0E0h+DeleteCount], rax; DeleteCount
0x14000a89e  xor     r8d, r8d; MatchData
0x14000a8a1  lea     rax, [rbp+3Fh+arg_30]
0x14000a8a5  xor     edx, edx; MatchFunction
0x14000a8a7  mov     [rsp+0E0h+RestartKey], rax; RestartKey
0x14000a8ac  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x14000a8b3  nop     dword ptr [rax+rax+00h]
0x14000a8b8  mov     r13, rax
0x14000a8bb  test    rax, rax
0x14000a8be  jnz     loc_14000A827
0x14000a8c4  mov     [rbp+3Fh+arg_10], esi
0x14000a8c7  mov     rsi, [rbp+3Fh+var_88]
0x14000a8cb  xor     r13d, r13d
0x14000a8ce  cmp     [rbp+3Fh+arg_0], r13b
0x14000a8d2  jz      short loc_14000A8DC
0x14000a8d4  mov     rcx, rsi
0x14000a8d7  call    SrvAdminDereferenceShare
0x14000a8dc  mov     rcx, [rbp+3Fh+Resource]; Resource
0x14000a8e0  call    cs:__imp_ExReleaseResourceLite
0x14000a8e7  nop     dword ptr [rax+rax+00h]
0x14000a8ec  mov     rcx, [rbp+3Fh+var_78]; Resource
0x14000a8f0  call    cs:__imp_ExReleaseResourceLite
0x14000a8f7  nop     dword ptr [rax+rax+00h]
0x14000a8fc  mov     eax, [rbp+3Fh+arg_10]
0x14000a8ff  mov     [rbx+58h], eax
0x14000a902  mov     [rbx+50h], r15d
0x14000a906  mov     [rbx+54h], r12d
0x14000a90a  test    edi, edi
0x14000a90c  jns     short loc_14000A917
0x14000a90e  mov     dword ptr [rbx+44h], 85Ch
0x14000a915  jmp     short loc_14000A94A
0x14000a917  test    r15d, r15d
0x14000a91a  jnz     short loc_14000A92A
0x14000a91c  test    r12d, r12d
0x14000a91f  jz      short loc_14000A92A
0x14000a921  mov     dword ptr [rbx+44h], 84Bh
0x14000a928  jmp     short loc_14000A947
0x14000a92a  cmp     [rbp+3Fh+arg_18], r13b
0x14000a92e  jz      short loc_14000A93F
0x14000a930  mov     eax, [rbp+3Fh+arg_28]
0x14000a933  mov     [rbx+5Ch], eax
0x14000a936  mov     dword ptr [rbx+44h], 0EAh
0x14000a93d  jmp     short loc_14000A947
0x14000a93f  mov     [rbx+44h], r13d
0x14000a943  mov     [rbx+5Ch], r13d
0x14000a947  mov     edi, r13d
0x14000a94a  mov     eax, edi
0x14000a94c  add     rsp, 0A8h
0x14000a953  pop     r15
0x14000a955  pop     r14
0x14000a957  pop     r13
0x14000a959  pop     r12
0x14000a95b  pop     rdi
0x14000a95c  pop     rsi
0x14000a95d  pop     rbx
0x14000a95e  pop     rbp
0x14000a95f  retn
```
