# VncDeferredChecksumMdlChain

- ea: `0x140028fcc`
- end: `0x140029b00`
- name: `VncDeferredChecksumMdlChain`
- size: `2868`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140028800`
- `0x140028e44`
- `0x140116e18`
- `0x140116e90`

## callees

- `0x140006620`
- `0x140028fcc`
- `0x1401bbcb0`
- `0x1401bbe10`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400291e4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140029502`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400297c5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400291e4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140029502`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400297c5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400291b6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029347`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400291b6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140029347`

## pseudocode

```c
__int64 __fastcall VncDeferredChecksumMdlChain(
        __int64 a1,
        char a2,
        __int64 a3,
        struct _MDL *a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        __int16 *a8)
{
  struct _MDL *v8; // r15
  char *MappedSystemVa; // rcx
  __int64 v12; // rdx
  unsigned int ByteCount; // eax
  __int16 *v14; // rbp
  unsigned int v15; // ecx
  unsigned int v16; // eax
  unsigned int v17; // r12d
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rcx
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  unsigned int v30; // ecx
  bool v31; // zf
  unsigned int v32; // edi
  __int16 *v34; // rax
  _DWORD *v35; // rax
  int v36; // ecx
  __int64 v37; // r8
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // r8
  __int64 v41; // r9
  volatile signed __int32 *v42; // rcx
  __int64 v43; // r8
  char v44; // di
  __int16 *v45; // rdx
  char v46; // al
  unsigned __int16 v47; // ax
  __int16 v48; // ax
  unsigned __int16 v49; // ax
  __int16 v50; // ax
  __int16 *v51; // r8
  __int16 v52; // cx
  __int16 v53; // cx
  __int16 v54; // cx
  __int16 v55; // cx
  __int64 v56; // r8
  __int64 v57; // rax
  char v58; // [rsp+80h] [rbp+18h]
  unsigned int v59; // [rsp+A0h] [rbp+38h]

  v58 = a3;
  v8 = a4;
  if ( a6 )
  {
    if ( a4 )
    {
      if ( (a4->MdlFlags & 5) != 0 )
        MappedSystemVa = (char *)a4->MappedSystemVa;
      else
        MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(a4, 0, MmCached, 0, 0, 0x40000000u);
      if ( MappedSystemVa )
      {
        v12 = a5;
        ByteCount = v8->ByteCount;
        if ( ByteCount > a5 )
        {
          v14 = (__int16 *)&MappedSystemVa[a5];
          v15 = a6;
          v16 = ByteCount - a5;
          v59 = a6;
          while ( 1 )
          {
            v17 = v15;
            if ( v16 <= v15 )
              v17 = v16;
            v18 = *(_QWORD *)(a1 + 80);
            if ( *(_BYTE *)(v18 + 1) == 1 && !*(_BYTE *)(a1 + 4) )
            {
              v56 = *(unsigned int *)(a1 + 12);
              v57 = 0;
              *(_BYTE *)(a1 + 4) = 1;
              if ( (_DWORD)v56 != -1 )
              {
                v12 = *(_QWORD *)(v18 + 24);
                if ( v12 )
                  v57 = v12 + 20 * v56;
              }
              _InterlockedAdd16((volatile signed __int16 *)(v57 + 16), 1u);
            }
            v19 = *(_QWORD *)(a1 + 80);
            v20 = *(_DWORD *)(v19 + 4);
            if ( v20 )
              break;
            if ( *(_DWORD *)(a1 + 20) )
            {
              LOBYTE(v12) = 1;
              BLFlushBatchOpContextEx(a1, v12, 0);
            }
            if ( (*(_BYTE *)(a1 + 8) & 5) == 5 || (v44 = 0, (*(_DWORD *)(a1 + 8) & 6) == 6) )
              v44 = 1;
            v45 = *(__int16 **)(a1 + 48);
            if ( v45 && v45 != a8 )
            {
              if ( v44 )
              {
                (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
                v51 = *(__int16 **)(a1 + 48);
                v52 = *v51;
                if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                  v52 = __ROR2__(v52, 8);
                v53 = ~v52;
                if ( *(_BYTE *)(a1 + 40) && !v53 )
                  v53 = -1;
                *v51 = v53;
                *(_QWORD *)(a1 + 48) = 0;
                *(_DWORD *)(a1 + 44) = 0;
                (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
              }
              else
              {
                v54 = *v45;
                if ( (*(_DWORD *)(a1 + 44) & 1) != 0 )
                  v54 = __ROR2__(v54, 8);
                v55 = ~v54;
                if ( *(_BYTE *)(a1 + 40) && !v55 )
                  v55 = -1;
                *v45 = v55;
                *(_DWORD *)(a1 + 44) = 0;
              }
            }
            if ( !v58 || (v46 = 1, a2 != 1) )
              v46 = 0;
            *(_BYTE *)(a1 + 40) = v46;
            *(_QWORD *)(a1 + 48) = a8;
            if ( v44 )
            {
              (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 32LL))();
              if ( a8 >= v14 && a8 < (__int16 *)((char *)v14 + v17) )
                v49 = 0;
              else
                v49 = *a8;
              v50 = tcpxsum(v49, v14, v17);
              *a8 = v50;
              if ( (v17 & 1) != 0 )
              {
                *a8 = __ROR2__(v50, 8);
                ++*(_DWORD *)(a1 + 44);
              }
              (*(void (**)(void))(*(_QWORD *)(a1 + 80) + 40LL))();
            }
            else
            {
              if ( a8 < v14 || a8 >= (__int16 *)((char *)v14 + v17) )
                v47 = *a8;
              else
                v47 = 0;
              v48 = tcpxsum(v47, v14, v17);
              *a8 = v48;
              if ( (v17 & 1) != 0 )
              {
                *a8 = __ROR2__(v48, 8);
                ++*(_DWORD *)(a1 + 44);
              }
            }
LABEL_24:
            v31 = v59 == v17;
            v15 = v59 - v17;
            v59 -= v17;
            if ( v31 )
              return 0;
            v8 = v8->Next;
            if ( !v8 )
              goto LABEL_30;
            if ( (v8->MdlFlags & 5) != 0 )
            {
              v14 = (__int16 *)v8->MappedSystemVa;
            }
            else
            {
              v34 = (__int16 *)MmMapLockedPagesSpecifyCache(v8, 0, MmCached, 0, 0, 0x40000000u);
              v15 = v59;
              v14 = v34;
            }
            if ( !v14 )
              goto LABEL_30;
            v16 = v8->ByteCount;
          }
          v12 = *(_QWORD *)(a1 + 32);
          v21 = *(_DWORD *)(v12 + 8);
          if ( v21 >= *(_DWORD *)(v12 + 12) )
          {
            v21 = 0;
            if ( *(_DWORD *)(a1 + 16) >= v20 )
            {
              LOBYTE(v12) = 1;
            }
            else
            {
              v35 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v19 + 64));
              v12 = (__int64)v35;
              if ( v35 )
              {
                *(_QWORD *)v35 = 0;
                v35[2] = 0;
                v36 = *(_DWORD *)(*(_QWORD *)(a1 + 80) + 8LL);
                *((_QWORD *)v35 + 2) = v35 + 6;
                v35[3] = v36;
                **(_QWORD **)(a1 + 32) = v35;
                v37 = *(_QWORD *)(a1 + 80);
                ++*(_DWORD *)(a1 + 16);
                *(_QWORD *)(a1 + 32) = v35;
                if ( *(_BYTE *)(v37 + 1) == 1 )
                {
                  v38 = *(unsigned int *)(a1 + 12);
                  v39 = 0;
                  if ( (_DWORD)v38 != -1 )
                  {
                    v40 = *(_QWORD *)(v37 + 24);
                    if ( v40 )
                      v39 = v40 + 20 * v38;
                  }
                  _InterlockedAdd16((volatile signed __int16 *)(v39 + 12), 1u);
                  v41 = *(unsigned int *)(a1 + 12);
                  v42 = 0;
                  if ( (_DWORD)v41 != -1 )
                  {
                    v43 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
                    if ( v43 )
                      v42 = (volatile signed __int32 *)(v43 + 20 * v41);
                  }
                  _InterlockedAdd(v42, 1u);
                }
                goto LABEL_13;
              }
              v12 = 1;
            }
            BLFlushBatchOpContextEx(a1, v12, 0);
            v12 = a1 + 56;
          }
LABEL_13:
          ++*(_DWORD *)(a1 + 20);
          ++*(_DWORD *)(v12 + 8);
          v22 = *(_QWORD *)(a1 + 80);
          if ( *(_BYTE *)(v22 + 1) == 1 )
          {
            v23 = *(unsigned int *)(a1 + 12);
            v24 = 0;
            if ( (_DWORD)v23 != -1 )
            {
              v25 = *(_QWORD *)(v22 + 24);
              if ( v25 )
                v24 = v25 + 20 * v23;
            }
            _InterlockedAdd16((volatile signed __int16 *)(v24 + 14), 1u);
            v26 = *(unsigned int *)(a1 + 12);
            v27 = 0;
            if ( (_DWORD)v26 != -1 )
            {
              v28 = *(_QWORD *)(*(_QWORD *)(a1 + 80) + 24LL);
              if ( v28 )
                v27 = v28 + 20 * v26;
            }
            _InterlockedAdd((volatile signed __int32 *)(v27 + 4), 1u);
          }
          v29 = *(_QWORD *)(v12 + 16);
          a3 = 3LL * v21;
          if ( v58 && a2 == 1 )
            v30 = *(_DWORD *)(v29 + 24LL * v21 + 16) & 0xFFFFFFF0 | 7;
          else
            v30 = *(_DWORD *)(v29 + 24LL * v21 + 16) & 0xFFFFFFF0 | 6;
          *(_QWORD *)(v29 + 24LL * v21 + 8) = v14;
          *(_QWORD *)(v29 + 24LL * v21) = a8;
          *(_DWORD *)(v29 + 24LL * v21 + 16) = (16 * v17) | v30 & 0xF;
          goto LABEL_24;
        }
      }
LABEL_30:
      v32 = -1073741670;
    }
    else
    {
      v32 = -1073741811;
    }
    LOBYTE(a3) = 1;
    BLFlushBatchOpContextEx(a1, 0, a3);
  }
  else
  {
    return 0;
  }
  return v32;
}

```

## disassembly

```asm
0x140028fcc  mov     [rsp+arg_0], rbx
0x140028fd1  mov     [rsp+arg_10], r8b
0x140028fd6  mov     [rsp+arg_8], dl
0x140028fda  push    rbp
0x140028fdb  push    rsi
0x140028fdc  push    rdi
0x140028fdd  push    r12
0x140028fdf  push    r13
0x140028fe1  push    r14
0x140028fe3  push    r15
0x140028fe5  sub     rsp, 30h
0x140028fe9  mov     edi, [rsp+68h+arg_28]
0x140028ff0  xor     r10d, r10d
0x140028ff3  mov     r15, r9
0x140028ff6  mov     sil, dl
0x140028ff9  mov     rbx, rcx
0x140028ffc  test    edi, edi
0x140028ffe  jz      loc_140029149
0x140029004  lea     r11d, [r10+1]
0x140029008  test    r9, r9
0x14002900b  jz      loc_140029A35
0x140029011  test    byte ptr [r9+0Ah], 5
0x140029016  jz      loc_14002932F
0x14002901c  mov     rcx, [r9+18h]
0x140029020  test    rcx, rcx
0x140029023  jz      loc_14002917E
0x140029029  mov     edx, [rsp+68h+arg_20]
0x140029030  mov     eax, [r15+28h]
0x140029034  cmp     eax, edx
0x140029036  jbe     loc_14002917E
0x14002903c  mov     r14, [rsp+68h+arg_38]
0x140029044  lea     rbp, [rcx+rdx]
0x140029048  mov     ecx, edi
0x14002904a  sub     eax, edx
0x14002904c  mov     [rsp+68h+arg_30], ecx
0x140029053  mov     r13, r10
0x140029056  cmp     eax, ecx
0x140029058  mov     r12d, ecx
0x14002905b  cmovbe  r12d, eax
0x14002905f  test    r13, r13
0x140029062  jnz     loc_14002939E
0x140029068  mov     rcx, [rbx+50h]
0x14002906c  cmp     [rcx+1], r11b
0x140029070  jz      loc_140029A6D
0x140029076  mov     rcx, [rbx+50h]
0x14002907a  mov     eax, [rcx+4]
0x14002907d  test    eax, eax
0x14002907f  jz      loc_140029286
0x140029085  mov     rdx, [rbx+20h]
0x140029089  mov     edi, [rdx+8]
0x14002908c  cmp     edi, [rdx+0Ch]
0x14002908f  jnb     loc_1400291D4
0x140029095  add     [rbx+14h], r11d
0x140029099  add     [rdx+8], r11d
0x14002909d  mov     rcx, [rbx+50h]
0x1400290a1  cmp     [rcx+1], r11b
0x1400290a5  jnz     short loc_1400290F2
0x1400290a7  mov     r9d, [rbx+0Ch]
0x1400290ab  mov     rax, r10
0x1400290ae  cmp     r9d, 0FFFFFFFFh
0x1400290b2  jz      short loc_1400290C5
0x1400290b4  mov     r8, [rcx+18h]
0x1400290b8  test    r8, r8
0x1400290bb  jz      short loc_1400290C5
0x1400290bd  lea     rcx, [r9+r9*4]
0x1400290c1  lea     rax, [r8+rcx*4]
0x1400290c5  lock add [rax+0Eh], r11w
0x1400290cb  mov     r9d, [rbx+0Ch]
0x1400290cf  mov     rcx, r10
0x1400290d2  cmp     r9d, 0FFFFFFFFh
0x1400290d6  jz      short loc_1400290ED
0x1400290d8  mov     rax, [rbx+50h]
0x1400290dc  mov     r8, [rax+18h]
0x1400290e0  test    r8, r8
0x1400290e3  jz      short loc_1400290ED
0x1400290e5  lea     rcx, [r9+r9*4]
0x1400290e9  lea     rcx, [r8+rcx*4]
0x1400290ed  lock add [rcx+4], r11d
0x1400290f2  mov     r9, [rdx+10h]
0x1400290f6  mov     eax, edi
0x1400290f8  lea     r8, [rax+rax*2]
0x1400290fc  mov     dil, [rsp+68h+arg_10]
0x140029104  test    dil, dil
0x140029107  jnz     short loc_140029164
0x140029109  mov     ecx, [r9+r8*8+10h]
0x14002910e  and     ecx, 0FFFFFFF6h
0x140029111  or      ecx, 6
0x140029114  mov     eax, r12d
0x140029117  mov     [r9+r8*8+8], rbp
0x14002911c  shl     eax, 4
0x14002911f  and     ecx, 0Fh
0x140029122  or      ecx, eax
0x140029124  mov     [r9+r8*8], r14
0x140029128  mov     [r9+r8*8+10h], ecx
0x14002912d  mov     ecx, [rsp+68h+arg_30]
0x140029134  sub     ecx, r12d
0x140029137  mov     [rsp+68h+arg_30], ecx
0x14002913e  jnz     short loc_140029176
0x140029140  test    r13, r13
0x140029143  jnz     loc_1400296C5
0x140029149  mov     edi, r10d
0x14002914c  mov     rbx, [rsp+68h+arg_0]
0x140029151  mov     eax, edi
0x140029153  add     rsp, 30h
0x140029157  pop     r15
0x140029159  pop     r14
0x14002915b  pop     r13
0x14002915d  pop     r12
0x14002915f  pop     rdi
0x140029160  pop     rsi
0x140029161  pop     rbp
0x140029162  retn
0x140029164  cmp     sil, r11b
0x140029167  jnz     short loc_140029109
0x140029169  mov     ecx, [r9+r8*8+10h]
0x14002916e  and     ecx, 0FFFFFFF7h
0x140029171  or      ecx, 7
0x140029174  jmp     short loc_140029114
0x140029176  mov     r15, [r15]
0x140029179  test    r15, r15
0x14002917c  jnz     short loc_140029192
0x14002917e  mov     edi, 0C000009Ah
0x140029183  mov     r8b, 1
0x140029186  xor     edx, edx
0x140029188  mov     rcx, rbx
0x14002918b  call    BLFlushBatchOpContextEx
0x140029190  jmp     short loc_14002914C
0x140029192  test    byte ptr [r15+0Ah], 5
0x140029197  jnz     loc_1400294DA
0x14002919d  xor     r9d, r9d; RequestedAddress
0x1400291a0  mov     [rsp+68h+Priority], 40000000h; Priority
0x1400291a8  xor     edx, edx; AccessMode
0x1400291aa  mov     [rsp+68h+BugCheckOnFailure], r10d; BugCheckOnFailure
0x1400291af  mov     rcx, r15; MemoryDescriptorList
0x1400291b2  lea     r8d, [r9+1]; CacheType
0x1400291b6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400291bd  nop     dword ptr [rax+rax+00h]
0x1400291c2  mov     ecx, [rsp+68h+arg_30]
0x1400291c9  xor     r10d, r10d
0x1400291cc  mov     rbp, rax
0x1400291cf  jmp     loc_1400294DE
0x1400291d4  mov     edi, r10d
0x1400291d7  cmp     [rbx+10h], eax
0x1400291da  jnb     loc_140029362
0x1400291e0  add     rcx, 40h ; '@'; Lookaside
0x1400291e4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400291eb  nop     dword ptr [rax+rax+00h]
0x1400291f0  xor     r10d, r10d
0x1400291f3  mov     rdx, rax
0x1400291f6  test    rax, rax
0x1400291f9  jz      loc_140029380
0x1400291ff  mov     [rax], r10
0x140029202  lea     r11d, [r10+1]
0x140029206  mov     [rax+8], r10d
0x14002920a  mov     rax, [rbx+50h]
0x14002920e  mov     ecx, [rax+8]
0x140029211  lea     rax, [rdx+18h]
0x140029215  mov     [rdx+10h], rax
0x140029219  mov     [rdx+0Ch], ecx
0x14002921c  mov     rax, [rbx+20h]
0x140029220  mov     [rax], rdx
0x140029223  mov     r8, [rbx+50h]
0x140029227  add     [rbx+10h], r11d
0x14002922b  mov     [rbx+20h], rdx
0x14002922f  cmp     [r8+1], r11b
0x140029233  jnz     loc_140029095
0x140029239  mov     ecx, [rbx+0Ch]
0x14002923c  mov     eax, r10d
0x14002923f  cmp     ecx, 0FFFFFFFFh
0x140029242  jz      short loc_140029255
0x140029244  mov     r8, [r8+18h]
0x140029248  test    r8, r8
0x14002924b  jz      short loc_140029255
0x14002924d  lea     rcx, [rcx+rcx*4]
0x140029251  lea     rax, [r8+rcx*4]
0x140029255  lock add [rax+0Ch], r11w
0x14002925b  mov     r9d, [rbx+0Ch]
0x14002925f  mov     rcx, r10
0x140029262  cmp     r9d, 0FFFFFFFFh
0x140029266  jz      short loc_14002927D
0x140029268  mov     rax, [rbx+50h]
0x14002926c  mov     r8, [rax+18h]
0x140029270  test    r8, r8
0x140029273  jz      short loc_14002927D
0x140029275  lea     rcx, [r9+r9*4]
0x140029279  lea     rcx, [r8+rcx*4]
0x14002927d  lock add [rcx], r11d
0x140029281  jmp     loc_140029095
0x140029286  cmp     [rbx+14h], r10d
0x14002928a  jnz     loc_140029384
0x140029290  mov     ecx, [rbx+8]
0x140029293  mov     eax, ecx
0x140029295  and     eax, 5
0x140029298  cmp     al, 5
0x14002929a  jz      loc_140029A7C
0x1400292a0  and     ecx, 6
0x1400292a3  mov     dil, r10b
0x1400292a6  cmp     cl, 6
0x1400292a9  jz      loc_140029A7C
0x1400292af  mov     rdx, [rbx+30h]
0x1400292b3  test    rdx, rdx
0x1400292b6  jnz     loc_140029A84
0x1400292bc  cmp     [rsp+68h+arg_10], r10b
0x1400292c4  jnz     loc_140029AAF
0x1400292ca  mov     al, r10b
0x1400292cd  mov     [rbx+28h], al
0x1400292d0  mov     [rbx+30h], r14
0x1400292d4  test    dil, dil
0x1400292d7  jnz     loc_14002953F
0x1400292dd  cmp     r14, rbp
0x1400292e0  jb      loc_14002948E
0x1400292e6  mov     ecx, r12d
0x1400292e9  add     rcx, rbp
0x1400292ec  cmp     r14, rcx
0x1400292ef  jnb     loc_14002948E
0x1400292f5  mov     eax, r10d
0x1400292f8  mov     r8d, r12d
0x1400292fb  mov     rdx, rbp
0x1400292fe  movzx   ecx, ax
0x140029301  call    tcpxsum
0x140029306  mov     edi, 1
0x14002930b  mov     [r14], ax
0x14002930f  test    dil, r12b
0x140029312  jz      short loc_14002931F
0x140029314  ror     ax, 8
0x140029318  mov     [r14], ax
0x14002931c  add     [rbx+2Ch], edi
0x14002931f  mov     dil, [rsp+68h+arg_10]
0x140029327  xor     r10d, r10d
0x14002932a  jmp     loc_14002912D
0x14002932f  mov     [rsp+68h+Priority], 40000000h; Priority
0x140029337  xor     r9d, r9d; RequestedAddress
0x14002933a  mov     r8d, r11d; CacheType
0x14002933d  mov     [rsp+68h+BugCheckOnFailure], r10d; BugCheckOnFailure
0x140029342  xor     edx, edx; AccessMode
0x140029344  mov     rcx, r15; MemoryDescriptorList
0x140029347  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002934e  nop     dword ptr [rax+rax+00h]
0x140029353  xor     r10d, r10d
0x140029356  mov     rcx, rax
0x140029359  lea     r11d, [r10+1]
0x14002935d  jmp     loc_140029020
0x140029362  mov     dl, r11b
0x140029365  xor     r8d, r8d
0x140029368  mov     rcx, rbx
0x14002936b  call    BLFlushBatchOpContextEx
0x140029370  xor     r10d, r10d
0x140029373  lea     rdx, [rbx+38h]
0x140029377  lea     r11d, [r10+1]
0x14002937b  jmp     loc_140029095
0x140029380  mov     dl, 1
0x140029382  jmp     short loc_140029365
0x140029384  xor     r8d, r8d
0x140029387  mov     dl, r11b
0x14002938a  mov     rcx, rbx
0x14002938d  call    BLFlushBatchOpContextEx
0x140029392  xor     r10d, r10d
0x140029395  lea     r11d, [r10+1]
0x140029399  jmp     loc_140029290
0x14002939e  test    rbx, rbx
0x1400293a1  jz      loc_1400294C7
0x1400293a7  mov     rcx, [rbx+50h]
0x1400293ab  cmp     [rcx+1], r11b
0x1400293af  jnz     short loc_1400293DF
0x1400293b1  cmp     [rbx+4], r10b
0x1400293b5  jnz     short loc_1400293DF
0x1400293b7  mov     r8d, [rbx+0Ch]
0x1400293bb  mov     rax, r10
0x1400293be  mov     [rbx+4], r11b
0x1400293c2  cmp     r8d, 0FFFFFFFFh
0x1400293c6  jz      short loc_1400293D9
0x1400293c8  mov     rdx, [rcx+18h]
0x1400293cc  test    rdx, rdx
0x1400293cf  jz      short loc_1400293D9
0x1400293d1  lea     rcx, [r8+r8*4]
0x1400293d5  lea     rax, [rdx+rcx*4]
0x1400293d9  lock add [rax+10h], r11w
0x1400293df  lea     rsi, [rbx+50h]
0x1400293e3  mov     rcx, [rsi]
0x1400293e6  mov     eax, [rcx+4]
0x1400293e9  test    eax, eax
0x1400293eb  jz      loc_140029497
0x1400293f1  mov     r8, [rbx+20h]
0x1400293f5  mov     edi, [r8+8]
0x1400293f9  cmp     edi, [r8+0Ch]
0x1400293fd  jnb     loc_1400294F6
0x140029403  add     [rbx+14h], r11d
0x140029407  add     [r8+8], r11d
0x14002940b  mov     rcx, [rsi]
0x14002940e  cmp     [rcx+1], r11b
0x140029412  jnz     short loc_14002945E
0x140029414  mov     r9d, [rbx+0Ch]
0x140029418  mov     rax, r10
0x14002941b  cmp     r9d, 0FFFFFFFFh
0x14002941f  jz      short loc_140029432
0x140029421  mov     rdx, [rcx+18h]
0x140029425  test    rdx, rdx
0x140029428  jz      short loc_140029432
0x14002942a  lea     rcx, [r9+r9*4]
0x14002942e  lea     rax, [rdx+rcx*4]
  ... truncated ...
```
