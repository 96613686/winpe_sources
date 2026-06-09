# UdfOpenObjectFromDirContext

- ea: `0x140050224`
- end: `0x140050a85`
- name: `UdfOpenObjectFromDirContext`
- size: `2145`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *, char, char, __int64, char, __int64, __int64 *, ULONG)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x140042c40`

## callees

- `0x140009730`
- `0x140009b64`
- `0x14000c0ec`
- `0x14000c490`
- `0x14000cad4`
- `0x140011b54`
- `0x14001c080`
- `0x14003dec8`
- `0x14003f360`
- `0x14004ce50`
- `0x14004cf74`
- `0x14004fc70`
- `0x140050224`
- `0x140050a8c`
- `0x140050ee0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140050601`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400508ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050a20`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a919`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050601`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400508ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050a20`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a919`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400503bb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005058f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005064e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005069c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400503bb`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005058f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005064e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005069c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400505bf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400505dd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140050684`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005080e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400509ce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400509f3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005a8ae`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005a8da`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400505bf`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400505dd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140050684`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005080e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400509ce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400509f3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005a8ae`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005a8da`
- `ntoskrnl!_wcsnicmp` at `0x140050879`
- `ntoskrnl!_wcsnicmp` at `0x140050879`

## pseudocode

```c
__int64 __fastcall UdfOpenObjectFromDirContext(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        char a5,
        char a6,
        __int64 a7,
        char a8,
        __int64 a9,
        __int64 *a10,
        ULONG a11)
{
  __int64 v14; // r14
  __int64 v15; // r9
  unsigned int v17; // r10d
  unsigned __int16 v18; // bx
  int v19; // r15d
  __int64 v20; // rsi
  int v21; // eax
  __int64 v22; // r9
  __int64 Scb; // rax
  __int64 v24; // r8
  __int64 v25; // rbx
  __int64 v26; // rax
  _QWORD *v27; // rdx
  __int64 v28; // rcx
  char v29; // r14
  __int64 v30; // rcx
  char v31; // dl
  __int64 v32; // rdx
  __int64 inserted; // r14
  __int64 v34; // r15
  int v35; // eax
  __int64 *v36; // rdx
  int v37; // [rsp+38h] [rbp-F0h]
  char v38; // [rsp+51h] [rbp-D7h]
  char v39; // [rsp+52h] [rbp-D6h]
  char v40; // [rsp+53h] [rbp-D5h] BYREF
  char v41; // [rsp+54h] [rbp-D4h]
  unsigned int v42; // [rsp+58h] [rbp-D0h]
  int v43; // [rsp+5Ch] [rbp-CCh]
  unsigned int v44; // [rsp+60h] [rbp-C8h]
  __int64 v45; // [rsp+68h] [rbp-C0h]
  __int64 v46; // [rsp+70h] [rbp-B8h]
  __int64 v47; // [rsp+78h] [rbp-B0h]
  __int64 v48; // [rsp+80h] [rbp-A8h]
  int v49; // [rsp+88h] [rbp-A0h]
  _QWORD v50[19]; // [rsp+90h] [rbp-98h] BYREF
  int v52; // [rsp+138h] [rbp+10h]

  v52 = a2;
  v14 = a1;
  v45 = 0;
  v40 = 0;
  memset(v50, 0, 0x60u);
  v15 = *(_QWORD *)(a7 + 32);
  if ( (*(_BYTE *)(v15 + 18) & 2) != 0 )
  {
    if ( a8 && (a11 & 0xFFFFFFFA) == 0 && a11 != 1 )
      return 3221225525LL;
    v17 = 3;
    v18 = 2355;
  }
  else
  {
    v17 = 4;
    v18 = 2356;
  }
  v44 = v17;
  v41 = *(_BYTE *)(a2 + 2) & 4;
  if ( a8 && (unsigned __int8)UdfIllegalScbAccess(v14, v17, *(unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL)) )
    return (*(_DWORD *)(a3 + 48) & 0x20) != 0 ? -1073739770 : -1073741790;
  v19 = 0;
  v48 = 0;
  v20 = 0;
  v46 = 0;
  v42 = 0;
  v38 = 0;
  if ( a9 )
  {
    if ( (*(_BYTE *)(a9 + 4) & 3) != 0 )
      v19 = 2;
    v19 |= 0x800u;
    v43 = v19;
  }
  if ( a6 )
  {
    v19 |= 4u;
    v43 = v19;
  }
  if ( a5 )
  {
    v19 |= 0x80u;
    v43 = v19;
  }
  LODWORD(v45) = *(_DWORD *)(v15 + 24);
  v21 = *(unsigned __int16 *)(v15 + 28);
  HIDWORD(v45) = v21;
  if ( v17 == 3 )
    HIDWORD(v45) = v21 | 0x80000000;
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1648));
  *(_QWORD *)(a3 + 1704) = KeGetCurrentThread();
  v39 = 1;
  if ( (*(_DWORD *)(*a4 + 212) & 8) != 0 )
    v22 = *(_QWORD *)(*a4 + 136);
  else
    LODWORD(v22) = 0;
  Scb = UdfCreateScb(v14, v45, v18, v22, (__int64)&v40);
  v25 = Scb;
  v48 = Scb;
  if ( !v40 )
  {
    v26 = *(_QWORD *)(Scb + 136);
    if ( (*(_DWORD *)(*a4 + 212) & 8) != 0 )
    {
      v27 = (_QWORD *)(v26 + 32);
      v28 = *(_QWORD *)(v26 + 32);
      if ( *(_QWORD *)(v28 + 8) != v26 + 32 )
        __fastfail(3u);
      *(_QWORD *)(v25 + 120) = v28;
      *(_QWORD *)(v25 + 128) = v27;
      *(_QWORD *)(v28 + 8) = v25 + 120;
      *v27 = v25 + 120;
      *(_DWORD *)(v25 + 212) |= 0x10u;
    }
    else
    {
      *(_QWORD *)(v26 + 16) = v25;
    }
    *(_DWORD *)(v25 + 176) = *(_DWORD *)(*(_QWORD *)(a7 + 32) + 20LL) & 0x3FFFFFFF;
    UdfInitializeIcbContextFromScb(v14, (__int64)v50, v25);
    v29 = 1;
    UdfLookupActiveIcb(a1, v50, *(unsigned int *)(v25 + 176));
    v31 = *(_BYTE *)(v50[2] + 27LL);
    if ( v31 == 13
      || v31 == -8
      || (v30 = (*(unsigned __int8 *)(*(_QWORD *)(a7 + 32) + 18LL) >> 1) & 1, (v31 == 4) != (_DWORD)v30) )
    {
      v42 = -1073741566;
LABEL_70:
      v34 = a1;
      goto LABEL_71;
    }
    v14 = a1;
    UdfInitializeScbFromIcbContext(a1, v25, v50, *a4);
    UdfCleanupIcbContext(a1, v50);
  }
  v32 = *(_QWORD *)(v25 + 136);
  if ( *(_QWORD *)(*a4 + 136) == v32
    || (LOBYTE(v24) = 1, (unsigned __int8)UdfAcquireResource(v14, *(_QWORD *)(v32 + 80) + 8LL, v24, 0)) )
  {
    *(_QWORD *)(a3 + 1704) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1648));
    v39 = 0;
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
    *(_QWORD *)(a3 + 1640) = KeGetCurrentThread();
  }
  else
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
    *(_QWORD *)(a3 + 1640) = KeGetCurrentThread();
    ++*(_DWORD *)(v25 + 204);
    *(_QWORD *)(a3 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
    *(_QWORD *)(a3 + 1704) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1648));
    v39 = 0;
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*a4 + 136) + 80LL) + 8LL));
    UdfAcquireResource(v14, *(_QWORD *)(*(_QWORD *)(v25 + 136) + 80LL) + 8LL, 0, 0);
    UdfAcquireResource(v14, *(_QWORD *)(*(_QWORD *)(*a4 + 136) + 80LL) + 8LL, 0, 0);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
    *(_QWORD *)(a3 + 1640) = KeGetCurrentThread();
    --*(_DWORD *)(v25 + 204);
  }
  v38 = 1;
  v20 = *a4;
  v46 = *a4;
  *a4 = v25;
  if ( (*(_DWORD *)(v25 + 212) & 0x200) != 0 )
  {
    v42 = -1073741738;
LABEL_69:
    v29 = 0;
    goto LABEL_70;
  }
  inserted = UdfInsertPrefix(v14, v25, (int)a7 + 64, (int)a7 + 80, a7 + 112, v20, *(_QWORD *)(a7 + 48));
  v47 = inserted;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
  {
    WPP_SF_qdddd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      16,
      WPP_962a5ab0fb873cc757a84452495a3943_Traceguids,
      v20,
      *(_DWORD *)(a3 + 256),
      *(_DWORD *)(a3 + 260),
      *(_DWORD *)(v20 + 204),
      *(_DWORD *)(v20 + 208));
  }
  ++*(_DWORD *)(v20 + 204);
  ++*(_DWORD *)(v20 + 208);
  ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 136) + 8LL) + 256LL);
  ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 136) + 8LL) + 260LL);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
  {
    WPP_SF_DDDD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      17,
      WPP_962a5ab0fb873cc757a84452495a3943_Traceguids,
      *(unsigned int *)(a3 + 256),
      *(_DWORD *)(a3 + 260),
      *(_DWORD *)(v20 + 204),
      *(_DWORD *)(v20 + 208));
  }
  *(_QWORD *)(a3 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
  v38 = 0;
  if ( (*(_BYTE *)(*(_QWORD *)(a7 + 32) + 18LL) & 1) != 0 )
    *(_DWORD *)(inserted + 72) |= 2u;
  if ( *(_WORD *)v25 == 2355
    && v20 == *(_QWORD *)(a3 + 288)
    && *(_WORD *)(a3 + 2138) == 258
    && *(_WORD *)(inserted + 168) == 16
    && !_wcsnicmp(*(const wchar_t **)(inserted + 176), L"VIDEO_TS", 8u)
    && (*(_DWORD *)(a3 + 48) & 0x10) != 0 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 18, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids);
    }
    *(_DWORD *)(v25 + 212) |= 0x100000u;
  }
  if ( v41 && a8 )
  {
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*a4 + 136) + 80LL) + 8LL));
    *a4 = v20;
    v20 = 0;
    v46 = 0;
    v30 = 3;
    v49 = 3;
    if ( *a4 == *(_QWORD *)(a3 + 288) )
      inserted = 0;
    else
      inserted = *(_QWORD *)(*a4 + 160) - 32LL;
    v47 = inserted;
  }
  else
  {
    v30 = v44;
  }
  if ( !a8 )
  {
    *a10 = inserted;
    goto LABEL_69;
  }
  v37 = v19;
  v34 = a1;
  v42 = UdfCompleteScbOpen(a1, v52, a3, (int)a4, inserted, *a10, v30, v37, a11, 1);
  v29 = 0;
LABEL_71:
  if ( v38 )
  {
    *(_QWORD *)(a3 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1584));
  }
  if ( v39 )
  {
    *(_QWORD *)(a3 + 1704) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a3 + 1648));
  }
  if ( v20 )
  {
    v30 = *(_QWORD *)(v20 + 136);
    if ( v30 != *(_QWORD *)(*a4 + 136) )
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v30 + 80) + 8LL));
  }
  v35 = *(_DWORD *)(v25 + 212);
  if ( (v35 & 1) == 0 )
  {
    if ( (v35 & 0x10) != 0 )
    {
      v30 = *(_QWORD *)(v25 + 120);
      if ( *(_QWORD *)(v30 + 8) != v25 + 120 || (v36 = *(__int64 **)(v25 + 128), *v36 != v25 + 120) )
        __fastfail(3u);
      *v36 = v30;
      *(_QWORD *)(v30 + 8) = v36;
    }
    UdfDeleteScb(v30, v25);
  }
  if ( v29 )
    UdfCleanupIcbContext(v34, v50);
  return v42;
}

```

## disassembly

```asm
0x140050224  mov     rax, rsp
0x140050227  mov     [rax+20h], r9
0x14005022b  mov     [rax+18h], r8
0x14005022f  mov     [rax+10h], rdx
0x140050233  mov     [rax+8], rcx
0x140050237  push    rbx
0x140050238  push    rsi
0x140050239  push    rdi
0x14005023a  push    r12
0x14005023c  push    r13
0x14005023e  push    r14
0x140050240  push    r15
0x140050242  sub     rsp, 0F0h
0x140050249  mov     r12, r9
0x14005024c  mov     rdi, r8
0x14005024f  mov     rsi, rdx
0x140050252  mov     r14, rcx
0x140050255  xor     r13d, r13d
0x140050258  mov     [rsp+128h+var_C0], r13
0x14005025d  mov     [rsp+128h+var_D5], r13b
0x140050262  xor     edx, edx; Val
0x140050264  lea     r8d, [r13+60h]; Size
0x140050268  lea     rcx, [rax-98h]; void *
0x14005026f  call    memset
0x140050274  mov     r9, [rsp+128h+arg_30]
0x14005027c  mov     r9, [r9+20h]
0x140050280  mov     al, [r9+12h]
0x140050284  lea     edx, [r13+2]
0x140050288  test    dl, al
0x14005028a  mov     al, [rsp+128h+arg_38]
0x140050291  jz      short loc_1400502D4
0x140050293  test    al, al
0x140050295  jz      short loc_1400502C7
0x140050297  test    [rsp+128h+arg_50], 0FFFFFFFAh
0x1400502a2  jnz     short loc_1400502C7
0x1400502a4  cmp     [rsp+128h+arg_50], 1
0x1400502ac  jz      short loc_1400502C7
0x1400502ae  mov     eax, 0C0000035h
0x1400502b3  add     rsp, 0F0h
0x1400502ba  pop     r15
0x1400502bc  pop     r14
0x1400502be  pop     r13
0x1400502c0  pop     r12
0x1400502c2  pop     rdi
0x1400502c3  pop     rsi
0x1400502c4  pop     rbx
0x1400502c5  retn
0x1400502c7  mov     r10d, 3
0x1400502cd  mov     ebx, 933h
0x1400502d2  jmp     short loc_1400502DF
0x1400502d4  mov     r10d, 4
0x1400502da  mov     ebx, 934h
0x1400502df  mov     [rsp+128h+var_C8], r10d
0x1400502e4  mov     cl, [rsi+2]
0x1400502e7  and     cl, 4
0x1400502ea  mov     [rsp+128h+var_D4], cl
0x1400502ee  test    al, al
0x1400502f0  jz      short loc_140050323
0x1400502f2  mov     r8, [rsi+8]
0x1400502f6  mov     r8d, [r8+10h]
0x1400502fa  mov     edx, r10d
0x1400502fd  mov     rcx, r14
0x140050300  call    UdfIllegalScbAccess
0x140050305  test    al, al
0x140050307  jz      short loc_14005031E
0x140050309  mov     eax, [rdi+30h]
0x14005030c  and     al, 20h
0x14005030e  neg     al
0x140050310  sbb     eax, eax
0x140050312  and     eax, 7E4h
0x140050317  add     eax, 0C0000022h
0x14005031c  jmp     short loc_1400502B3
0x14005031e  mov     edx, 2
0x140050323  mov     r15d, r13d
0x140050326  mov     [rsp+128h+var_A8], r13
0x14005032e  mov     rsi, r13
0x140050331  mov     [rsp+128h+var_B8], r13
0x140050336  mov     [rsp+128h+var_D8], r13b
0x14005033b  mov     [rsp+128h+var_D0], r13d
0x140050340  mov     [rsp+128h+var_D7], r13b
0x140050345  mov     [rsp+128h+var_D6], r13b
0x14005034a  mov     rax, [rsp+128h+arg_40]
0x140050352  test    rax, rax
0x140050355  jz      short loc_14005036E
0x140050357  test    byte ptr [rax+4], 3
0x14005035b  cmovnz  r15d, edx
0x14005035f  mov     [rsp+128h+var_CC], r15d
0x140050364  bts     r15d, 0Bh
0x140050369  mov     [rsp+128h+var_CC], r15d
0x14005036e  cmp     [rsp+128h+arg_28], r13b
0x140050376  jz      short loc_140050381
0x140050378  or      r15d, 4
0x14005037c  mov     [rsp+128h+var_CC], r15d
0x140050381  cmp     [rsp+128h+arg_20], r13b
0x140050389  jz      short loc_140050395
0x14005038b  bts     r15d, 7
0x140050390  mov     [rsp+128h+var_CC], r15d
0x140050395  mov     eax, [r9+18h]
0x140050399  mov     dword ptr [rsp+128h+var_C0], eax
0x14005039d  movzx   eax, word ptr [r9+1Ch]
0x1400503a2  mov     dword ptr [rsp+128h+var_C0+4], eax
0x1400503a6  cmp     r10d, 3
0x1400503aa  jnz     short loc_1400503B4
0x1400503ac  bts     eax, 1Fh
0x1400503b0  mov     dword ptr [rsp+128h+var_C0+4], eax
0x1400503b4  lea     rcx, [rdi+670h]; FastMutex
0x1400503bb  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400503c2  nop     dword ptr [rax+rax+00h]
0x1400503c7  mov     rax, gs:188h
0x1400503d0  mov     [rdi+6A8h], rax
0x1400503d7  mov     [rsp+128h+var_D6], 1
0x1400503dc  mov     rcx, [r12]
0x1400503e0  mov     eax, [rcx+0D4h]
0x1400503e6  test    al, 8
0x1400503e8  jz      short loc_1400503F3
0x1400503ea  mov     r9, [rcx+88h]
0x1400503f1  jmp     short loc_1400503F6
0x1400503f3  mov     r9, r13
0x1400503f6  lea     rax, [rsp+128h+var_D5]
0x1400503fb  mov     qword ptr [rsp+128h+var_108], rax
0x140050400  movzx   r8d, bx
0x140050404  mov     rdx, [rsp+128h+var_C0]
0x140050409  mov     rcx, r14
0x14005040c  call    UdfCreateScb
0x140050411  mov     rbx, rax
0x140050414  mov     [rsp+128h+var_A8], rax
0x14005041c  cmp     [rsp+128h+var_D5], r13b
0x140050421  jnz     loc_140050549
0x140050427  mov     rax, [rax+88h]
0x14005042e  mov     rdx, [r12]
0x140050432  mov     r8d, [rdx+0D4h]
0x140050439  test    r8b, 8
0x14005043d  jz      short loc_140050474
0x14005043f  lea     rdx, [rax+20h]
0x140050443  mov     rcx, [rdx]
0x140050446  cmp     [rcx+8], rdx
0x14005044a  jz      short loc_140050453
0x14005044c  mov     ecx, 3
0x140050451  int     29h; Win8: RtlFailFast(ecx)
0x140050453  lea     rax, [rbx+78h]
0x140050457  mov     [rax], rcx
0x14005045a  mov     [rax+8], rdx
0x14005045e  mov     [rcx+8], rax
0x140050462  mov     [rdx], rax
0x140050465  mov     r13d, 10h
0x14005046b  or      [rbx+0D4h], r13d
0x140050472  jmp     short loc_14005047E
0x140050474  mov     [rax+10h], rbx
0x140050478  mov     r13d, 10h
0x14005047e  mov     rax, [rsp+128h+arg_30]
0x140050486  mov     rax, [rax+20h]
0x14005048a  mov     ecx, [rax+14h]
0x14005048d  and     ecx, 3FFFFFFFh
0x140050493  mov     [rbx+0B0h], ecx
0x140050499  mov     r8, rbx
0x14005049c  lea     rdx, [rsp+128h+var_98]
0x1400504a4  mov     rcx, r14
0x1400504a7  call    UdfInitializeIcbContextFromScb
0x1400504ac  mov     r14b, 1
0x1400504af  mov     [rsp+128h+var_D8], r14b
0x1400504b4  mov     r8d, [rbx+0B0h]
0x1400504bb  lea     rdx, [rsp+128h+var_98]
0x1400504c3  mov     rcx, qword ptr [rsp+128h+arg_0]
0x1400504cb  call    UdfLookupActiveIcb
0x1400504d0  mov     rax, [rsp+128h+var_88]
0x1400504d8  mov     dl, [rax+1Bh]
0x1400504db  cmp     dl, 0Dh
0x1400504de  jz      short loc_14005053C
0x1400504e0  cmp     dl, 0F8h
0x1400504e3  jz      short loc_14005053C
0x1400504e5  mov     rax, [rsp+128h+arg_30]
0x1400504ed  mov     rax, [rax+20h]
0x1400504f1  movzx   ecx, byte ptr [rax+12h]
0x1400504f5  shr     ecx, 1
0x1400504f7  and     ecx, 1
0x1400504fa  xor     eax, eax
0x1400504fc  cmp     dl, 4
0x1400504ff  setz    al
0x140050502  cmp     eax, ecx
0x140050504  jnz     short loc_14005053C
0x140050506  mov     r9, [r12]
0x14005050a  lea     r8, [rsp+128h+var_98]
0x140050512  mov     rdx, rbx
0x140050515  mov     r14, qword ptr [rsp+128h+arg_0]
0x14005051d  mov     rcx, r14
0x140050520  call    UdfInitializeScbFromIcbContext
0x140050525  lea     rdx, [rsp+128h+var_98]
0x14005052d  mov     rcx, r14
0x140050530  call    UdfCleanupIcbContext
0x140050535  mov     [rsp+128h+var_D8], 0
0x14005053a  jmp     short loc_14005054F
0x14005053c  mov     [rsp+128h+var_D0], 0C0000102h
0x140050544  jmp     loc_1400509AD
0x140050549  mov     r13d, 10h
0x14005054f  mov     rdx, [rbx+88h]
0x140050556  mov     rax, [r12]
0x14005055a  cmp     [rax+88h], rdx
0x140050561  jz      loc_140050672
0x140050567  mov     rdx, [rdx+50h]
0x14005056b  add     rdx, 8
0x14005056f  xor     r9d, r9d
0x140050572  mov     r8b, 1
0x140050575  mov     rcx, r14
0x140050578  call    UdfAcquireResource
0x14005057d  test    al, al
0x14005057f  jnz     loc_140050672
0x140050585  lea     rsi, [rdi+630h]
0x14005058c  mov     rcx, rsi; FastMutex
0x14005058f  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140050596  nop     dword ptr [rax+rax+00h]
0x14005059b  mov     rax, gs:188h
0x1400505a4  mov     [rdi+668h], rax
0x1400505ab  inc     dword ptr [rbx+0CCh]
0x1400505b1  mov     qword ptr [rdi+668h], 0
0x1400505bc  mov     rcx, rsi; FastMutex
0x1400505bf  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400505c6  nop     dword ptr [rax+rax+00h]
0x1400505cb  mov     qword ptr [rdi+6A8h], 0
0x1400505d6  lea     rcx, [rdi+670h]; FastMutex
0x1400505dd  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400505e4  nop     dword ptr [rax+rax+00h]
0x1400505e9  mov     [rsp+128h+var_D6], 0
0x1400505ee  mov     rax, [r12]
0x1400505f2  mov     rcx, [rax+88h]
0x1400505f9  mov     rcx, [rcx+50h]
0x1400505fd  add     rcx, 8; Resource
0x140050601  call    cs:__imp_ExReleaseResourceLite
0x140050608  nop     dword ptr [rax+rax+00h]
0x14005060d  mov     rax, [rbx+88h]
0x140050614  mov     rdx, [rax+50h]
0x140050618  add     rdx, 8
0x14005061c  xor     r9d, r9d
0x14005061f  xor     r8d, r8d
0x140050622  mov     rcx, r14
0x140050625  call    UdfAcquireResource
0x14005062a  mov     rax, [r12]
0x14005062e  mov     rcx, [rax+88h]
0x140050635  mov     rdx, [rcx+50h]
0x140050639  add     rdx, 8
0x14005063d  xor     r9d, r9d
0x140050640  xor     r8d, r8d
0x140050643  mov     rcx, r14
0x140050646  call    UdfAcquireResource
0x14005064b  mov     rcx, rsi; FastMutex
0x14005064e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140050655  nop     dword ptr [rax+rax+00h]
0x14005065a  mov     rax, gs:188h
0x140050663  mov     [rdi+668h], rax
0x14005066a  dec     dword ptr [rbx+0CCh]
0x140050670  jmp     short loc_1400506B8
0x140050672  mov     qword ptr [rdi+6A8h], 0
0x14005067d  lea     rcx, [rdi+670h]; FastMutex
0x140050684  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005068b  nop     dword ptr [rax+rax+00h]
0x140050690  mov     [rsp+128h+var_D6], 0
0x140050695  lea     rcx, [rdi+630h]; FastMutex
0x14005069c  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400506a3  nop     dword ptr [rax+rax+00h]
0x1400506a8  mov     rax, gs:188h
0x1400506b1  mov     [rdi+668h], rax
0x1400506b8  mov     [rsp+128h+var_D7], 1
0x1400506bd  mov     rsi, [r12]
0x1400506c1  mov     [rsp+128h+var_B8], rsi
0x1400506c6  mov     [r12], rbx
0x1400506ca  mov     eax, [rbx+0D4h]
0x1400506d0  bt      eax, 9
0x1400506d4  jnb     short loc_1400506E3
0x1400506d6  mov     [rsp+128h+var_D0], 0C0000056h
0x1400506de  jmp     loc_1400509A5
0x1400506e3  mov     rax, [rsp+128h+arg_30]
0x1400506eb  lea     rcx, [rax+70h]
0x1400506ef  lea     r9, [rax+50h]
0x1400506f3  lea     r8, [rax+40h]
0x1400506f7  mov     rax, [rax+30h]
0x1400506fb  mov     qword ptr [rsp+128h+var_F8], rax
0x140050700  mov     [rsp+128h+var_100], rsi
0x140050705  mov     qword ptr [rsp+128h+var_108], rcx
0x14005070a  mov     rdx, rbx
0x14005070d  mov     rcx, r14
0x140050710  call    UdfInsertPrefix
0x140050715  mov     r14, rax
0x140050718  mov     [rsp+128h+var_B0], rax
0x14005071d  lea     rax, WPP_GLOBAL_Control
0x140050724  mov     r10, cs:WPP_GLOBAL_Control
0x14005072b  cmp     r10, rax
0x14005072e  jz      short loc_140050779
0x140050730  mov     ecx, [r10+2Ch]
0x140050734  test    r13b, cl
0x140050737  jz      short loc_140050779
0x140050739  mov     edx, r13d
0x14005073c  mov     r8d, [rsi+0D0h]
0x140050743  mov     [rsp+128h+var_F0], r8d
0x140050748  mov     eax, [rsi+0CCh]
0x14005074e  mov     [rsp+128h+var_F8], eax
0x140050752  mov     eax, [rdi+104h]
0x140050758  mov     dword ptr [rsp+128h+var_100], eax
0x14005075c  mov     eax, [rdi+100h]
0x140050762  mov     [rsp+128h+var_108], eax
0x140050766  mov     r9, rsi
0x140050769  lea     r8, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids
  ... truncated ...
```
