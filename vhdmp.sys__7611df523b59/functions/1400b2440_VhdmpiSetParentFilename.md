# VhdmpiSetParentFilename

- ea: `0x1400b2440`
- end: `0x1400b2a08`
- name: `VhdmpiSetParentFilename`
- size: `1480`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1400cbd20`

## callees

- `0x140019310`
- `0x14001b298`
- `0x14001b524`
- `0x14001b7fc`
- `0x14001bc68`
- `0x140021164`
- `0x140023560`
- `0x140035e94`
- `0x14004a524`
- `0x14005d7c0`
- `0x14005d840`
- `0x14005da00`
- `0x1400b1cc0`
- `0x1400b2440`
- `0x1400ceb9c`
- `0x1400d0370`
- `0x1400e98ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400b29b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b29d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b29b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b29d2`
- `ntoskrnl!ExAllocatePool2` at `0x1400b2846`
- `ntoskrnl!ExAllocatePool2` at `0x1400b2846`

## string_xrefs

- `0x1400b259f`: `VhdmpiSetParentFilename: attempt to modify parent of disk without using NO_PARENTS flag`
- `0x1400b2713`: `VhdmpiSetParentFilename: failed to open parent (0x%08x).`
- `0x1400b2614`: `VhdmpiSetParentFilename: attempt to modify parent of non-differencing disk`
- `0x1400b254a`: `VhdmpiSetParentFilename: leaf-only handle attempted to modify a parent`

## pseudocode

```c
__int64 __fastcall VhdmpiSetParentFilename(__int64 a1, unsigned int a2, __int64 a3)
{
  struct _VHD_BACKING_STORE_HEADER *v5; // r15
  struct _VHD_BACKING_STORE_HEADER *v6; // rsi
  unsigned int v7; // edx
  int BackingStoreChain; // ebx
  int *v9; // rdi
  int v10; // eax
  unsigned int v11; // edx
  unsigned int v12; // edx
  unsigned int v13; // ecx
  int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // edx
  int v17; // ecx
  char v18; // dl
  int v19; // eax
  struct _VHD_VIRTUAL_DISK *v20; // r12
  unsigned int v21; // edx
  int v22; // eax
  struct _VHD_BACKING_STORE_HEADER *v23; // rax
  struct _VHD_BACKING_STORE_HEADER **v24; // rcx
  unsigned int v25; // ebx
  void *Pool2; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  _QWORD *v29; // rcx
  __int64 v30; // r12
  struct _VHD_BACKING_STORE_HEADER *v31; // r13
  char v33; // [rsp+50h] [rbp-59h]
  char v34; // [rsp+51h] [rbp-58h]
  int v35; // [rsp+54h] [rbp-55h] BYREF
  struct _VHD_BACKING_STORE_HEADER *v36; // [rsp+58h] [rbp-51h] BYREF
  struct _VHD_VIRTUAL_DISK *v37; // [rsp+60h] [rbp-49h]
  PVOID P[2]; // [rsp+68h] [rbp-41h] BYREF
  void *Src[2]; // [rsp+78h] [rbp-31h] BYREF
  __int64 v40; // [rsp+88h] [rbp-21h]
  __int64 v41; // [rsp+90h] [rbp-19h]
  PVOID v42[2]; // [rsp+98h] [rbp-11h] BYREF
  __int128 v43; // [rsp+A8h] [rbp-1h] BYREF
  __int128 v44; // [rsp+B8h] [rbp+Fh] BYREF

  v41 = a1;
  v34 = 0;
  v37 = 0;
  v40 = 0;
  v36 = 0;
  v35 = 0;
  v5 = 0;
  *(_OWORD *)Src = 0;
  v6 = 0;
  v43 = 0;
  v44 = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v42 = 0;
  if ( !VhdmpiIsSetParentRequestValid(a2, (struct _STORAGE_SET_VIRTUAL_DISK_METADATA_REQUEST *)a3, (PUNICODE_STRING)Src) )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      TraceEvents("VhdmpiSetParentFilename", 0x4DBu, 2u, v7, "VhdmpiSetParentFilename: invalid request packet");
    BackingStoreChain = -1073741811;
    v9 = (int *)(a1 + 4);
    goto LABEL_64;
  }
  v9 = (int *)(a1 + 4);
  v10 = *(_DWORD *)(a1 + 4);
  if ( (v10 & 2) != 0 && *(_DWORD *)(a3 + 4) > 1u )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      TraceEvents(
        "VhdmpiSetParentFilename",
        0x4EAu,
        2u,
        v11,
        "VhdmpiSetParentFilename: leaf-only handle attempted to modify a parent");
LABEL_11:
    BackingStoreChain = -1073741811;
    goto LABEL_64;
  }
  if ( (v10 & 3) == 1 )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      TraceEvents(
        "VhdmpiSetParentFilename",
        0x4FAu,
        2u,
        v12,
        "VhdmpiSetParentFilename: attempt to modify parent of disk without using NO_PARENTS flag");
    goto LABEL_11;
  }
  v13 = *(_DWORD *)(a3 + 4);
  v37 = *(struct _VHD_VIRTUAL_DISK **)(a1 + 56);
  v5 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v37 + 18);
  v14 = 1;
  if ( v13 > 1 )
  {
    while ( 1 )
    {
      v5 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v5 + 143);
      if ( !v5 )
        break;
      if ( ++v14 >= v13 )
        goto LABEL_19;
    }
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      TraceEvents(
        "VhdmpiSetParentFilename",
        0x513u,
        2u,
        v16,
        "VhdmpiSetParentFilename: depth in request exceeds the actual depth of the chain");
    goto LABEL_11;
  }
LABEL_19:
  if ( !(*(unsigned __int8 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *))(*(_QWORD *)v5 + 112LL))(v5) )
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      TraceEvents(
        "VhdmpiSetParentFilename",
        0x523u,
        2u,
        v15,
        "VhdmpiSetParentFilename: attempt to modify parent of non-differencing disk");
    goto LABEL_11;
  }
  v17 = *v9;
  if ( (*v9 & 1) != 0 || !*((_QWORD *)v5 + 143) )
  {
    v33 = 0;
    v18 = 0;
    if ( (*v9 & 1) != 0 )
      goto LABEL_32;
  }
  else
  {
    v33 = 1;
  }
  BackingStoreChain = VhdmpiAcquireBackingStoreAccess(a1, v5);
  if ( BackingStoreChain < 0 )
    goto LABEL_64;
  v17 = *v9;
  v18 = v33;
  v34 = 1;
LABEL_32:
  v19 = *(_DWORD *)(a3 + 4);
  v20 = v37;
  BackingStoreChain = VhdmpiCreateBackingStoreChain(
                        (struct _VHD_HANDLE_CONTEXT *)a1,
                        *(struct _BACKING_STORE_PARSER **)v5,
                        (struct _UNICODE_STRING *)Src,
                        (__int64)v37,
                        v19,
                        0,
                        v18 ^ 1u | (2 * ((v17 & 1) == 0)),
                        0,
                        (__int64 *)&v36);
  if ( BackingStoreChain >= 0 )
  {
    v6 = v36;
    BackingStoreChain = (*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, struct _VHD_BACKING_STORE_HEADER *))(*(_QWORD *)v5 + 136LL))(
                          v5,
                          v36);
    if ( BackingStoreChain >= 0 )
    {
      v22 = (*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, struct _VHD_BACKING_STORE_HEADER *))(*(_QWORD *)v5 + 128LL))(
              v5,
              v6);
      BackingStoreChain = 0;
      if ( v22 != -1069940722 )
        BackingStoreChain = v22;
      if ( BackingStoreChain >= 0 )
      {
        if ( v33 )
        {
          BackingStoreChain = VhdmpiRewriteParentLocators(v5, v6, 0);
          if ( BackingStoreChain < 0 )
            goto LABEL_64;
          v23 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v20 + 18);
          while ( v23 )
          {
            v24 = (struct _VHD_BACKING_STORE_HEADER **)((char *)v23 + 1152);
            if ( v23 == v5 )
            {
              *v24 = v6;
              v23 = v6;
            }
            else
            {
              v23 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v23 + 143);
              *v24 = v23;
            }
          }
          BackingStoreChain = VhdmpiActivateProposedBackingStoreChain(
                                v20,
                                *((struct _VHD_BACKING_STORE_HEADER **)v20 + 18));
          if ( BackingStoreChain < 0 )
            goto LABEL_64;
          while ( v6 )
          {
            VhdmpiReleaseBackingStoreAccess(a1, v6, 1);
            v6 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v6 + 143);
          }
          VhdmpiReleaseBackingStoreChain(v40, v20);
        }
        else
        {
          v25 = LOWORD(Src[0]) + 12;
          if ( v25 > 0xFFFE )
            v25 = 65534;
          if ( v25 < LOWORD(Src[0]) )
            goto LABEL_11;
          Pool2 = (void *)ExAllocatePool2(64, v25, 1849968726);
          P[1] = Pool2;
          if ( !Pool2 )
          {
            BackingStoreChain = -1073741670;
            goto LABEL_64;
          }
          memmove(Pool2, Src[1], LOWORD(Src[0]));
          LOWORD(P[0]) = Src[0];
          WORD1(P[0]) = v25;
          if ( (int)VhdmpiMakeLongPathDecorationAppropriate(P) < 0 )
          {
            BackingStoreChain = -1073741562;
            goto LABEL_64;
          }
          VhdmpiAbsolutePathNameToRelative((char *)v5 + 72, P, v42);
          VhdmpiAcquirePassiveLock((char *)v5 + 1120, v27, v28);
          (*(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, __int128 *, __int128 *))(*(_QWORD *)v5 + 200LL))(
            v5,
            &v43,
            &v44);
          (*(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, __int128 *))(*(_QWORD *)v6 + 216LL))(v6, &v43);
          (*(void (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, int *))(*(_QWORD *)v5 + 192LL))(v5, &v35);
          BackingStoreChain = (*(__int64 (__fastcall **)(struct _VHD_BACKING_STORE_HEADER *, PVOID *, PVOID *, _QWORD *, __int128 *, __int128 *, int *))(*(_QWORD *)v5 + 144LL))(
                                v5,
                                P,
                                v42,
                                (_QWORD *)v6 + 13,
                                &v43,
                                &v44,
                                &v35);
          v29 = (_QWORD *)((char *)v5 + 1120);
          if ( BackingStoreChain < 0 )
          {
            VhdmpiReleasePassiveLock(v29);
            goto LABEL_64;
          }
          *((_DWORD *)v5 + 291) = 2;
          VhdmpiReleasePassiveLock(v29);
        }
        BackingStoreChain = 0;
      }
    }
  }
  else
  {
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      TraceEvents(
        "VhdmpiSetParentFilename",
        0x588u,
        2u,
        v21,
        "VhdmpiSetParentFilename: failed to open parent (0x%08x).",
        BackingStoreChain);
    v6 = v36;
  }
LABEL_64:
  v30 = v41;
  v31 = v6;
  if ( v6 )
  {
    do
    {
      if ( (*v9 & 1) == 0 )
        VhdmpiReleaseBackingStoreAccess(v30, v31, 1);
      v31 = (struct _VHD_BACKING_STORE_HEADER *)*((_QWORD *)v31 + 143);
    }
    while ( v31 );
    VhdmpiReleaseBackingStoreChain(v6, v37);
  }
  if ( v34 )
    VhdmpiReleaseBackingStoreAccess(v30, v5, 2);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E444856u);
  if ( v42[1] )
    ExFreePoolWithTag(v42[1], 0x6E444856u);
  return (unsigned int)BackingStoreChain;
}

```

## disassembly

```asm
0x1400b2440  mov     [rsp-8+arg_8], rbx
0x1400b2445  push    rbp
0x1400b2446  push    rsi
0x1400b2447  push    rdi
0x1400b2448  push    r12
0x1400b244a  push    r13
0x1400b244c  push    r14
0x1400b244e  push    r15
0x1400b2450  lea     rbp, [rsp-27h]
0x1400b2455  sub     rsp, 0D0h
0x1400b245c  mov     rax, cs:__security_cookie
0x1400b2463  xor     rax, rsp
0x1400b2466  mov     [rbp+57h+var_38], rax
0x1400b246a  xor     ebx, ebx
0x1400b246c  mov     [rbp+57h+var_70], rcx
0x1400b2470  xorps   xmm0, xmm0
0x1400b2473  mov     [rbp+57h+var_AF], bl
0x1400b2476  mov     r12, r8
0x1400b2479  mov     [rbp+57h+var_A0], rbx
0x1400b247d  mov     eax, edx
0x1400b247f  mov     [rbp+57h+var_78], rbx
0x1400b2483  xorps   xmm1, xmm1
0x1400b2486  mov     [rbp+57h+var_A8], rbx
0x1400b248a  mov     r13, rcx
0x1400b248d  mov     [rbp+57h+var_AC], ebx
0x1400b2490  mov     rdx, r12; struct _STORAGE_SET_VIRTUAL_DISK_METADATA_REQUEST *
0x1400b2493  lea     r8, [rbp+57h+Src]; DestinationString
0x1400b2497  mov     ecx, eax; unsigned int
0x1400b2499  mov     r15d, ebx
0x1400b249c  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1400b24a0  mov     esi, ebx
0x1400b24a2  movups  [rbp+57h+var_58], xmm1
0x1400b24a6  movups  [rbp+57h+var_48], xmm0
0x1400b24aa  movups  xmmword ptr [rbp+57h+P], xmm1
0x1400b24ae  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x1400b24b2  call    ?VhdmpiIsSetParentRequestValid@@YAEKPEAU_STORAGE_SET_VIRTUAL_DISK_METADATA_REQUEST@@PEAU_UNICODE_STRING@@@Z; VhdmpiIsSetParentRequestValid(ulong,_STORAGE_SET_VIRTUAL_DISK_METADATA_REQUEST *,_UNICODE_STRING *)
0x1400b24b7  lea     edx, [rbx+1]
0x1400b24ba  lea     r14d, [rbx+2]
0x1400b24be  test    al, al
0x1400b24c0  jnz     short loc_1400B2513
0x1400b24c2  mov     eax, cs:dword_140087708
0x1400b24c8  cmp     eax, r14d
0x1400b24cb  jbe     short loc_1400B2505
0x1400b24cd  lea     edx, [rbx+8]
0x1400b24d0  lea     rcx, dword_140087708
0x1400b24d7  call    _tlgKeywordOn
0x1400b24dc  test    al, al
0x1400b24de  jz      short loc_1400B2505
0x1400b24e0  mov     ecx, 4DBh
0x1400b24e5  lea     rax, aVhdmpisetparen_4; "VhdmpiSetParentFilename: invalid reques"...
0x1400b24ec  mov     r9d, edx; int
0x1400b24ef  mov     [rsp+100h+var_E0], rax; char *
0x1400b24f4  mov     edx, ecx; int
0x1400b24f6  mov     r8d, r14d; int
0x1400b24f9  lea     rcx, aVhdmpisetparen_0; "VhdmpiSetParentFilename"
0x1400b2500  call    TraceEvents
0x1400b2505  mov     ebx, 0C000000Dh
0x1400b250a  lea     rdi, [r13+4]
0x1400b250e  jmp     loc_1400B2956
0x1400b2513  lea     rdi, [r13+4]
0x1400b2517  mov     eax, [rdi]
0x1400b2519  test    r14b, al
0x1400b251c  jz      short loc_1400B2574
0x1400b251e  cmp     [r12+4], edx
0x1400b2523  jbe     short loc_1400B2574
0x1400b2525  mov     eax, cs:dword_140087708
0x1400b252b  cmp     eax, r14d
0x1400b252e  jbe     short loc_1400B256A
0x1400b2530  mov     edx, 8
0x1400b2535  lea     rcx, dword_140087708
0x1400b253c  call    _tlgKeywordOn
0x1400b2541  test    al, al
0x1400b2543  jz      short loc_1400B256A
0x1400b2545  mov     ecx, 4EAh
0x1400b254a  lea     rax, aVhdmpisetparen_6; "VhdmpiSetParentFilename: leaf-only hand"...
0x1400b2551  mov     r9d, edx; int
0x1400b2554  mov     [rsp+100h+var_E0], rax; char *
0x1400b2559  mov     edx, ecx; int
0x1400b255b  mov     r8d, r14d; int
0x1400b255e  lea     rcx, aVhdmpisetparen_0; "VhdmpiSetParentFilename"
0x1400b2565  call    TraceEvents
0x1400b256a  mov     ebx, 0C000000Dh
0x1400b256f  jmp     loc_1400B2956
0x1400b2574  and     al, 3
0x1400b2576  cmp     al, dl
0x1400b2578  jnz     short loc_1400B25A8
0x1400b257a  mov     eax, cs:dword_140087708
0x1400b2580  cmp     eax, r14d
0x1400b2583  jbe     short loc_1400B256A
0x1400b2585  mov     edx, 8
0x1400b258a  lea     rcx, dword_140087708
0x1400b2591  call    _tlgKeywordOn
0x1400b2596  test    al, al
0x1400b2598  jz      short loc_1400B256A
0x1400b259a  mov     ecx, 4FAh
0x1400b259f  lea     rax, aVhdmpisetparen_2; "VhdmpiSetParentFilename: attempt to mod"...
0x1400b25a6  jmp     short loc_1400B2551
0x1400b25a8  mov     rax, [r13+38h]
0x1400b25ac  mov     ecx, [r12+4]
0x1400b25b1  mov     [rbp+57h+var_A0], rax
0x1400b25b5  mov     r15, [rax+90h]
0x1400b25bc  mov     eax, edx
0x1400b25be  cmp     ecx, edx
0x1400b25c0  jbe     short loc_1400B25D4
0x1400b25c2  mov     r15, [r15+478h]
0x1400b25c9  test    r15, r15
0x1400b25cc  jz      short loc_1400B2620
0x1400b25ce  add     eax, edx
0x1400b25d0  cmp     eax, ecx
0x1400b25d2  jb      short loc_1400B25C2
0x1400b25d4  mov     rax, [r15]
0x1400b25d7  mov     rcx, r15
0x1400b25da  mov     rax, [rax+70h]
0x1400b25de  call    _guard_dispatch_icall
0x1400b25e3  test    al, al
0x1400b25e5  jnz     short loc_1400B2659
0x1400b25e7  mov     eax, cs:dword_140087708
0x1400b25ed  cmp     eax, r14d
0x1400b25f0  jbe     loc_1400B256A
0x1400b25f6  mov     edx, 8
0x1400b25fb  lea     rcx, dword_140087708
0x1400b2602  call    _tlgKeywordOn
0x1400b2607  test    al, al
0x1400b2609  jz      loc_1400B256A
0x1400b260f  mov     ecx, 523h
0x1400b2614  lea     rax, aVhdmpisetparen_1; "VhdmpiSetParentFilename: attempt to mod"...
0x1400b261b  jmp     loc_1400B2551
0x1400b2620  mov     eax, cs:dword_140087708
0x1400b2626  cmp     eax, r14d
0x1400b2629  jbe     loc_1400B256A
0x1400b262f  mov     edx, 8
0x1400b2634  lea     rcx, dword_140087708
0x1400b263b  call    _tlgKeywordOn
0x1400b2640  test    al, al
0x1400b2642  jz      loc_1400B256A
0x1400b2648  mov     ecx, 513h
0x1400b264d  lea     rax, aVhdmpisetparen_5; "VhdmpiSetParentFilename: depth in reque"...
0x1400b2654  jmp     loc_1400B2551
0x1400b2659  mov     ecx, [rdi]
0x1400b265b  mov     eax, ecx
0x1400b265d  and     eax, 1
0x1400b2660  jnz     short loc_1400B2671
0x1400b2662  cmp     [r15+478h], rbx
0x1400b2669  jz      short loc_1400B2671
0x1400b266b  mov     [rbp+57h+var_B0], 1
0x1400b266f  jmp     short loc_1400B267A
0x1400b2671  mov     [rbp+57h+var_B0], bl
0x1400b2674  mov     dl, bl
0x1400b2676  test    eax, eax
0x1400b2678  jnz     short loc_1400B269D
0x1400b267a  mov     r8d, r14d
0x1400b267d  mov     rdx, r15
0x1400b2680  mov     rcx, r13
0x1400b2683  call    VhdmpiAcquireBackingStoreAccess
0x1400b2688  mov     ebx, eax
0x1400b268a  test    eax, eax
0x1400b268c  js      loc_1400B2956
0x1400b2692  mov     ecx, [rdi]
0x1400b2694  xor     ebx, ebx
0x1400b2696  mov     dl, [rbp+57h+var_B0]
0x1400b2699  mov     [rbp+57h+var_AF], 1
0x1400b269d  not     ecx
0x1400b269f  movzx   eax, dl
0x1400b26a2  mov     rdx, [r15]
0x1400b26a5  lea     r8, [rbp+57h+Src]
0x1400b26a9  and     ecx, 1
0x1400b26ac  xor     eax, 1
0x1400b26af  add     ecx, ecx
0x1400b26b1  or      ecx, eax
0x1400b26b3  lea     rax, [rbp+57h+var_A8]
0x1400b26b7  mov     [rsp+100h+var_C0], rax
0x1400b26bc  mov     eax, [r12+4]
0x1400b26c1  mov     r12, [rbp+57h+var_A0]
0x1400b26c5  mov     [rsp+100h+var_C8], ebx
0x1400b26c9  mov     r9, r12
0x1400b26cc  mov     dword ptr [rsp+100h+var_D0], ecx
0x1400b26d0  mov     rcx, r13
0x1400b26d3  mov     qword ptr [rsp+100h+var_D8], rbx
0x1400b26d8  mov     dword ptr [rsp+100h+var_E0], eax
0x1400b26dc  call    VhdmpiCreateBackingStoreChain
0x1400b26e1  mov     ebx, eax
0x1400b26e3  test    eax, eax
0x1400b26e5  jns     short loc_1400B2739
0x1400b26e7  mov     eax, cs:dword_140087708
0x1400b26ed  cmp     eax, r14d
0x1400b26f0  jbe     short loc_1400B2730
0x1400b26f2  mov     edx, 8
0x1400b26f7  lea     rcx, dword_140087708
0x1400b26fe  call    _tlgKeywordOn
0x1400b2703  test    al, al
0x1400b2705  jz      short loc_1400B2730
0x1400b2707  mov     ecx, 588h
0x1400b270c  mov     dword ptr [rsp+100h+var_D8], ebx; char
0x1400b2710  mov     r9d, edx; int
0x1400b2713  lea     rax, aVhdmpisetparen_7; "VhdmpiSetParentFilename: failed to open"...
0x1400b271a  mov     edx, ecx; int
0x1400b271c  mov     [rsp+100h+var_E0], rax; char *
0x1400b2721  lea     rcx, aVhdmpisetparen_0; "VhdmpiSetParentFilename"
0x1400b2728  mov     r8d, r14d; int
0x1400b272b  call    TraceEvents
0x1400b2730  mov     rsi, [rbp+57h+var_A8]
0x1400b2734  jmp     loc_1400B2956
0x1400b2739  mov     rax, [r15]
0x1400b273c  mov     rcx, r15
0x1400b273f  mov     rsi, [rbp+57h+var_A8]
0x1400b2743  mov     rdx, rsi
0x1400b2746  mov     rax, [rax+88h]
0x1400b274d  call    _guard_dispatch_icall
0x1400b2752  mov     ebx, eax
0x1400b2754  test    eax, eax
0x1400b2756  js      loc_1400B2956
0x1400b275c  mov     rax, [r15]
0x1400b275f  mov     rdx, rsi
0x1400b2762  mov     rcx, r15
0x1400b2765  mov     rax, [rax+80h]
0x1400b276c  call    _guard_dispatch_icall
0x1400b2771  xor     ebx, ebx
0x1400b2773  cmp     eax, 0C03A000Eh
0x1400b2778  cmovnz  ebx, eax
0x1400b277b  test    ebx, ebx
0x1400b277d  js      loc_1400B2956
0x1400b2783  cmp     [rbp+57h+var_B0], 0
0x1400b2787  jz      loc_1400B2820
0x1400b278d  xor     r8d, r8d
0x1400b2790  mov     rdx, rsi
0x1400b2793  mov     rcx, r15
0x1400b2796  call    VhdmpiRewriteParentLocators
0x1400b279b  mov     ebx, eax
0x1400b279d  test    eax, eax
0x1400b279f  js      loc_1400B2956
0x1400b27a5  mov     rax, [r12+90h]
0x1400b27ad  jmp     short loc_1400B27CD
0x1400b27af  lea     rcx, [rax+480h]
0x1400b27b6  cmp     rax, r15
0x1400b27b9  jnz     short loc_1400B27C3
0x1400b27bb  mov     [rcx], rsi
0x1400b27be  mov     rax, rsi
0x1400b27c1  jmp     short loc_1400B27CD
0x1400b27c3  mov     rax, [rax+478h]
0x1400b27ca  mov     [rcx], rax
0x1400b27cd  test    rax, rax
0x1400b27d0  jnz     short loc_1400B27AF
0x1400b27d2  mov     rdx, [r12+90h]; struct _VHD_BACKING_STORE_HEADER *
0x1400b27da  lea     r8, [rbp+57h+var_78]
0x1400b27de  mov     rcx, r12; struct _VHD_VIRTUAL_DISK *
0x1400b27e1  call    VhdmpiActivateProposedBackingStoreChain
0x1400b27e6  mov     ebx, eax
0x1400b27e8  test    eax, eax
0x1400b27ea  js      loc_1400B2956
0x1400b27f0  jmp     short loc_1400B280A
0x1400b27f2  mov     r8d, 1
0x1400b27f8  mov     rdx, rsi
0x1400b27fb  mov     rcx, r13
0x1400b27fe  call    VhdmpiReleaseBackingStoreAccess
0x1400b2803  mov     rsi, [rsi+478h]
0x1400b280a  test    rsi, rsi
0x1400b280d  jnz     short loc_1400B27F2
0x1400b280f  mov     rcx, [rbp+57h+var_78]
0x1400b2813  mov     rdx, r12
0x1400b2816  call    VhdmpiReleaseBackingStoreChain
0x1400b281b  jmp     loc_1400B2954
0x1400b2820  movzx   eax, word ptr [rbp+57h+Src]
0x1400b2824  mov     ecx, 0FFFEh
0x1400b2829  lea     ebx, [rax+0Ch]
0x1400b282c  cmp     ebx, ecx
0x1400b282e  cmova   ebx, ecx
0x1400b2831  cmp     ebx, eax
0x1400b2833  jb      loc_1400B256A
0x1400b2839  mov     edx, ebx
0x1400b283b  mov     ecx, 40h ; '@'
0x1400b2840  mov     r8d, 6E444856h
0x1400b2846  call    cs:__imp_ExAllocatePool2
0x1400b284d  nop     dword ptr [rax+rax+00h]
0x1400b2852  mov     [rbp+57h+P+8], rax
0x1400b2856  test    rax, rax
0x1400b2859  jnz     short loc_1400B2865
0x1400b285b  mov     ebx, 0C000009Ah
0x1400b2860  jmp     loc_1400B2956
0x1400b2865  movzx   r8d, word ptr [rbp+57h+Src]; Size
0x1400b286a  mov     rcx, rax; void *
0x1400b286d  mov     rdx, [rbp+57h+Src+8]; Src
0x1400b2871  call    memmove
0x1400b2876  movzx   eax, word ptr [rbp+57h+Src]
0x1400b287a  lea     rcx, [rbp+57h+P]
0x1400b287e  mov     word ptr [rbp+57h+P], ax
0x1400b2882  mov     word ptr [rbp+57h+P+2], bx
0x1400b2886  call    VhdmpiMakeLongPathDecorationAppropriate
0x1400b288b  test    eax, eax
0x1400b288d  jns     short loc_1400B2899
0x1400b288f  mov     ebx, 0C0000106h
0x1400b2894  jmp     loc_1400B2956
0x1400b2899  lea     rcx, [r15+48h]
0x1400b289d  lea     r8, [rbp+57h+var_68]
0x1400b28a1  lea     rdx, [rbp+57h+P]
0x1400b28a5  call    VhdmpiAbsolutePathNameToRelative
0x1400b28aa  lea     r12, [r15+460h]
0x1400b28b1  mov     rcx, r12
0x1400b28b4  call    VhdmpiAcquirePassiveLock
0x1400b28b9  mov     rax, [r15]
0x1400b28bc  lea     r8, [rbp+57h+var_48]
  ... truncated ...
```
