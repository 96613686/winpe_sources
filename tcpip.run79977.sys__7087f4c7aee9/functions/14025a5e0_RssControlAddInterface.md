# RssControlAddInterface

- ea: `0x14025a5e0`
- end: `0x14025ac2b`
- name: `RssControlAddInterface`
- size: `1611`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x1400c81f4`
- `0x1400fd6e4`
- `0x14010a19c`
- `0x14010ca90`
- `0x14011f414`
- `0x1401233cc`
- `0x1401255b4`
- `0x140128320`
- `0x14015a758`
- `0x1401b4a48`
- `0x1401bf4d0`
- `0x140256638`
- `0x140256a38`
- `0x1402585d8`
- `0x140259304`
- `0x14025964c`
- `0x14025a5e0`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14025abce`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14025abe3`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14025abce`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14025abe3`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14025a90b`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14025a925`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14025a90b`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14025a925`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14025a958`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14025a968`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14025a958`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14025a968`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14025a74f`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14025a995`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14025a74f`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14025a995`
- `ntoskrnl!KeInitializeMutex` at `0x14025a8d2`
- `ntoskrnl!KeInitializeMutex` at `0x14025a8d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025ab9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025abb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025abf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025ab9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025abb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025abf7`
- `ntoskrnl!ExAllocatePool2` at `0x14025a7f2`
- `ntoskrnl!ExAllocatePool2` at `0x14025a8f1`
- `ntoskrnl!ExAllocatePool2` at `0x14025a7f2`
- `ntoskrnl!ExAllocatePool2` at `0x14025a8f1`

## pseudocode

```c
void __fastcall RssControlAddInterface(__int16 a1, unsigned int a2, void *a3)
{
  __int64 *v3; // r15
  __int16 v6; // r14
  int v7; // edx
  PVOID *i; // rbx
  unsigned int *v9; // rbx
  int v10; // edx
  int v11; // r9d
  int v12; // r14d
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v13; // rcx
  int v14; // eax
  __int64 Pool2; // rax
  unsigned int v16; // r8d
  void *v17; // rdx
  __int64 **v18; // rax
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v20; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v21; // rcx
  unsigned int j; // r14d
  __int128 *v23; // r9
  char *v24; // rdx
  _QWORD *v25; // rax
  int v26; // r8d
  void *v27; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v28; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v29; // rcx
  int v30; // [rsp+20h] [rbp-99h]
  unsigned __int64 v31; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v32; // [rsp+38h] [rbp-81h] BYREF
  __int64 *v33; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v34; // [rsp+48h] [rbp-71h]
  int v35; // [rsp+4Ch] [rbp-6Dh]
  __int64 *v36; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v37; // [rsp+58h] [rbp-61h]
  int v38; // [rsp+5Ch] [rbp-5Dh]
  __int128 v39; // [rsp+60h] [rbp-59h] BYREF
  int v40; // [rsp+70h] [rbp-49h]
  char v41[32]; // [rsp+80h] [rbp-39h] BYREF
  __int64 **v42; // [rsp+A0h] [rbp-19h]
  __int64 v43; // [rsp+A8h] [rbp-11h]
  unsigned __int64 *v44; // [rsp+B0h] [rbp-9h]
  __int64 v45; // [rsp+B8h] [rbp-1h]
  __int64 **v46; // [rsp+C0h] [rbp+7h]
  __int64 v47; // [rsp+C8h] [rbp+Fh]

  LOWORD(v31) = a1;
  v3 = 0;
  v40 = 0;
  v32 = 0;
  v36 = 0;
  v6 = a1;
  v39 = 0;
  if ( a1 != 2 && a1 != 23 )
    return;
  RssLockBindingList();
  for ( i = (PVOID *)RssBindingList; i != &RssBindingList; i = (PVOID *)*i )
  {
    if ( *((_DWORD *)i + 13) == a2 )
    {
      if ( dword_1402201D4 == 1 && (HIBYTE(WPP_MAIN_CB.Reserved) & 2) != 0 )
      {
        v38 = 0;
        v36 = &RssStartedModules;
        v37 = a2;
        McTemplateK0qhq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          v7,
          (unsigned int)&v36,
          a2,
          v6,
          1);
      }
      if ( v6 == 2 )
      {
        v13 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)i[5];
        i[4] = a3;
      }
      else
      {
        v13 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)i[3];
        i[2] = a3;
      }
      ExReInitializeRundownProtectionCacheAware(v13);
      goto LABEL_53;
    }
  }
  v9 = 0;
  RssTraceBindingActivityStart(a2);
  if ( dword_1402201D4 == 1 && (HIBYTE(WPP_MAIN_CB.Reserved) & 2) != 0 )
  {
    v35 = 0;
    v33 = &RssStartedModules;
    v34 = a2;
    McTemplateK0qhq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      v10,
      (unsigned int)&v33,
      a2,
      v6,
      1);
  }
  v32 = a2;
  RssQueryPortIndex(a3, 0, &v32);
  LOBYTE(v11) = 1;
  if ( (int)RssQueryPortRssInfo((_DWORD)a3, 0, v32, v11, (__int64)&v39) >= 0 )
    v12 = ((DWORD1(v39) & 0x10000000) != 0) + 1;
  else
    v12 = 0;
  if ( dword_1402201D4 == 1 && (HIBYTE(WPP_MAIN_CB.Reserved) & 2) != 0 )
  {
    v35 = 0;
    v33 = &RssStartedModules;
    v34 = a2;
    McTemplateK0qq_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, &RSS_BINDING_CAPABILITY, &v33, a2, v12);
  }
  if ( !v12 )
    goto LABEL_64;
  if ( v12 != 2 )
  {
    HIDWORD(v31) = 1;
    goto LABEL_28;
  }
  v14 = RssQueryInterfacePortInformation(a3, a2, &v36);
  v3 = v36;
  if ( v14 < 0 )
  {
LABEL_64:
    RssTraceBindingActivityStop(a2);
    goto LABEL_65;
  }
  HIDWORD(v31) = *((_DWORD *)v36 + 1);
LABEL_28:
  Pool2 = ExAllocatePool2(64, 144, 1114862418);
  v9 = (unsigned int *)Pool2;
  if ( !Pool2 )
  {
    if ( dword_1402201D4 == 1 && (HIBYTE(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
    {
      v35 = 0;
      v33 = &RssStartedModules;
      v34 = a2;
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)&RSS_FAILURE,
        (unsigned int)&v33,
        a2,
        0,
        23);
    }
    if ( (unsigned int)dword_1402201F8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1402201F8, 0x200000000000LL) )
      goto LABEL_64;
    v42 = (__int64 **)((char *)&v31 + 4);
    v17 = &unk_1401F3A1D;
    v31 = __PAIR64__(a2, v16);
    v44 = &v31;
    v18 = &v36;
    LODWORD(v36) = -1073741801;
    goto LABEL_63;
  }
  *(_DWORD *)(Pool2 + 128) = 0;
  *(_DWORD *)(Pool2 + 48) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_QWORD *)(Pool2 + 16) = 0;
  *(_QWORD *)(Pool2 + 136) = 1;
  KeInitializeMutex((PRKMUTEX)(Pool2 + 64), 1u);
  *((_QWORD *)v9 + 7) = ExAllocatePool2(64, 16LL * HIDWORD(v31), 1114862418);
  *((_QWORD *)v9 + 5) = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x42737352u);
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x42737352u);
  *((_QWORD *)v9 + 3) = CacheAwareRundownProtection;
  if ( !*((_QWORD *)v9 + 7)
    || (v20 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v9 + 5)) == 0
    || !CacheAwareRundownProtection )
  {
    if ( dword_1402201D4 == 1 && (HIBYTE(WPP_MAIN_CB.Reserved) & 0x10) != 0 )
    {
      v35 = 0;
      v33 = &RssStartedModules;
      v34 = a2;
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)&RSS_FAILURE,
        (unsigned int)&v33,
        a2,
        0,
        23);
    }
    if ( (unsigned int)dword_1402201F8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1402201F8, 0x200000000000LL) )
      goto LABEL_64;
    LODWORD(v36) = a2;
    v42 = &v36;
    v17 = &unk_1401F3A60;
    HIDWORD(v31) = v26;
    v44 = (unsigned __int64 *)((char *)&v31 + 4);
    v18 = (__int64 **)&v31;
    LODWORD(v31) = -1073741801;
LABEL_63:
    v46 = v18;
    v43 = 4;
    v45 = 4;
    v47 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_1402201F8, v17, 0, 0, 5, v41, v31);
    goto LABEL_64;
  }
  ExWaitForRundownProtectionReleaseCacheAware(v20);
  ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)v9 + 3));
  v9[13] = a2;
  if ( (_WORD)v31 == 2 )
  {
    v21 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v9 + 5);
    *((_QWORD *)v9 + 4) = a3;
  }
  else
  {
    v21 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v9 + 3);
    *((_QWORD *)v9 + 2) = a3;
  }
  ExReInitializeRundownProtectionCacheAware(v21);
  if ( v12 == 1 )
  {
    if ( (unsigned __int8)RssFindOrCreateAdapter((_DWORD)a3, 0, (_DWORD)v9, (unsigned int)&v39, *((_QWORD *)v9 + 7)) )
      ++v9[12];
  }
  else
  {
    for ( j = 0; j < *((_DWORD *)v3 + 1); ++j )
    {
      v23 = &v39;
      v24 = (char *)v3 + *((_DWORD *)v3 + 3) * j + *((unsigned int *)v3 + 2);
      if ( *((_DWORD *)v24 + 1) )
        LODWORD(v23) = 0;
      if ( (unsigned __int8)RssFindOrCreateAdapter(
                              (_DWORD)a3,
                              (_DWORD)v24,
                              (_DWORD)v9,
                              (_DWORD)v23,
                              *((_QWORD *)v9 + 7) + 16LL * v9[12]) )
        ++v9[12];
    }
  }
  v9[32] |= 0x18u;
  RssQueueBindingWorkItemUnderLock(v9);
  v25 = (_QWORD *)qword_140225FA8;
  if ( *(PVOID **)qword_140225FA8 != &RssBindingList )
    __fastfail(3u);
  v6 = v31;
  *(_QWORD *)v9 = &RssBindingList;
  *((_QWORD *)v9 + 1) = v25;
  *v25 = v9;
  qword_140225FA8 = (__int64)v9;
LABEL_53:
  if ( dword_1402201D4 == 1 && (HIBYTE(WPP_MAIN_CB.Reserved) & 4) != 0 )
  {
    v35 = 0;
    v33 = &RssStartedModules;
    v34 = a2;
    LOWORD(v30) = v6;
    McTemplateK0qh_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, &RSS_BINDING_BIND_COMPLETE, &v33, a2, v30);
  }
  v9 = 0;
LABEL_65:
  RssUnlockBindingList();
  if ( v3 )
    ExFreePoolWithTag(v3, 0x67737352u);
  if ( v9 )
  {
    v27 = (void *)*((_QWORD *)v9 + 7);
    if ( v27 )
      ExFreePoolWithTag(v27, 0x42737352u);
    v28 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v9 + 5);
    if ( v28 )
      ExFreeCacheAwareRundownProtection(v28);
    v29 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v9 + 3);
    if ( v29 )
      ExFreeCacheAwareRundownProtection(v29);
    ExFreePoolWithTag(v9, 0x42737352u);
  }
}

```

## disassembly

```asm
0x14025a5e0  mov     [rsp-8+arg_0], rbx
0x14025a5e5  push    rbp
0x14025a5e6  push    rsi
0x14025a5e7  push    rdi
0x14025a5e8  push    r12
0x14025a5ea  push    r13
0x14025a5ec  push    r14
0x14025a5ee  push    r15
0x14025a5f0  lea     rbp, [rsp-27h]
0x14025a5f5  sub     rsp, 0E0h
0x14025a5fc  mov     rax, cs:__security_cookie
0x14025a603  xor     rax, rsp
0x14025a606  mov     [rbp+57h+var_40], rax
0x14025a60a  xor     eax, eax
0x14025a60c  mov     word ptr [rsp+110h+var_E0], cx
0x14025a611  xor     r15d, r15d
0x14025a614  mov     [rbp+57h+var_A0], eax
0x14025a617  mov     [rsp+110h+var_D8], eax
0x14025a61b  xorps   xmm0, xmm0
0x14025a61e  mov     r12, r8
0x14025a621  mov     [rbp+57h+var_C0], r15
0x14025a625  mov     edi, edx
0x14025a627  movzx   r14d, cx
0x14025a62b  lea     eax, [r15+2]
0x14025a62f  movups  [rbp+57h+var_B0], xmm0
0x14025a633  cmp     cx, ax
0x14025a636  jz      short loc_14025A642
0x14025a638  cmp     cx, 17h
0x14025a63c  jnz     loc_14025AC03
0x14025a642  call    RssLockBindingList
0x14025a647  mov     rbx, cs:RssBindingList
0x14025a64e  lea     rax, RssBindingList
0x14025a655  jmp     short loc_14025A663
0x14025a657  cmp     [rbx+34h], edi
0x14025a65a  jz      loc_14025A6ED
0x14025a660  mov     rbx, [rbx]
0x14025a663  cmp     rbx, rax
0x14025a666  jnz     short loc_14025A657
0x14025a668  mov     ecx, edi
0x14025a66a  xor     ebx, ebx
0x14025a66c  call    RssTraceBindingActivityStart
0x14025a671  lea     esi, [rbx+1]
0x14025a674  cmp     cs:dword_1402201D4, esi
0x14025a67a  lea     r13, RssStartedModules
0x14025a681  jnz     short loc_14025A6B3
0x14025a683  test    byte ptr cs:WPP_MAIN_CB.Reserved+7, 2
0x14025a68a  jz      short loc_14025A6B3
0x14025a68c  mov     dword ptr [rsp+110h+var_E8], esi
0x14025a690  lea     r8, [rbp+57h+var_D0]
0x14025a694  mov     r9d, edi
0x14025a697  mov     word ptr [rsp+110h+var_F0], r14w
0x14025a69d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025a6a4  mov     [rbp+57h+var_C4], ebx
0x14025a6a7  mov     [rbp+57h+var_D0], r13
0x14025a6ab  mov     [rbp+57h+var_C8], edi
0x14025a6ae  call    McTemplateK0qhq_EtwWriteTransfer
0x14025a6b3  lea     r8, [rsp+110h+var_D8]
0x14025a6b8  mov     [rsp+110h+var_D8], edi
0x14025a6bc  xor     edx, edx
0x14025a6be  mov     rcx, r12
0x14025a6c1  call    RssQueryPortIndex
0x14025a6c6  mov     r8d, [rsp+110h+var_D8]
0x14025a6cb  lea     rax, [rbp+57h+var_B0]
0x14025a6cf  mov     r9b, sil
0x14025a6d2  mov     [rsp+110h+var_F0], rax
0x14025a6d7  xor     edx, edx
0x14025a6d9  mov     rcx, r12
0x14025a6dc  call    RssQueryPortRssInfo
0x14025a6e1  test    eax, eax
0x14025a6e3  jns     short loc_14025A760
0x14025a6e5  xor     r14d, r14d
0x14025a6e8  jmp     loc_14025A773
0x14025a6ed  mov     esi, 1
0x14025a6f2  lea     r13, RssStartedModules
0x14025a6f9  cmp     cs:dword_1402201D4, esi
0x14025a6ff  jnz     short loc_14025A732
0x14025a701  test    byte ptr cs:WPP_MAIN_CB.Reserved+7, 2
0x14025a708  jz      short loc_14025A732
0x14025a70a  mov     dword ptr [rsp+110h+var_E8], esi
0x14025a70e  lea     r8, [rbp+57h+var_C0]
0x14025a712  mov     r9d, edi
0x14025a715  mov     word ptr [rsp+110h+var_F0], r14w
0x14025a71b  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025a722  mov     [rbp+57h+var_B4], r15d
0x14025a726  mov     [rbp+57h+var_C0], r13
0x14025a72a  mov     [rbp+57h+var_B8], edi
0x14025a72d  call    McTemplateK0qhq_EtwWriteTransfer
0x14025a732  mov     eax, 2
0x14025a737  cmp     r14w, ax
0x14025a73b  jnz     short loc_14025A747
0x14025a73d  mov     rcx, [rbx+28h]
0x14025a741  mov     [rbx+20h], r12
0x14025a745  jmp     short loc_14025A74F
0x14025a747  mov     rcx, [rbx+18h]; RunRefCacheAware
0x14025a74b  mov     [rbx+10h], r12
0x14025a74f  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14025a756  nop     dword ptr [rax+rax+00h]
0x14025a75b  jmp     loc_14025AA5C
0x14025a760  mov     eax, dword ptr [rbp+57h+var_B0+4]
0x14025a763  and     eax, 10000000h
0x14025a768  neg     eax
0x14025a76a  sbb     r14d, r14d
0x14025a76d  neg     r14d
0x14025a770  add     r14d, esi
0x14025a773  cmp     cs:dword_1402201D4, esi
0x14025a779  jnz     short loc_14025A7AD
0x14025a77b  test    byte ptr cs:WPP_MAIN_CB.Reserved+7, 2
0x14025a782  jz      short loc_14025A7AD
0x14025a784  mov     r9d, edi
0x14025a787  mov     [rbp+57h+var_C4], ebx
0x14025a78a  lea     r8, [rbp+57h+var_D0]
0x14025a78e  mov     [rbp+57h+var_D0], r13
0x14025a792  lea     rdx, RSS_BINDING_CAPABILITY
0x14025a799  mov     [rbp+57h+var_C8], edi
0x14025a79c  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025a7a3  mov     dword ptr [rsp+110h+var_F0], r14d
0x14025a7a8  call    McTemplateK0qq_EtwWriteTransfer
0x14025a7ad  test    r14d, r14d
0x14025a7b0  jz      loc_14025AB81
0x14025a7b6  cmp     r14d, 2
0x14025a7ba  jnz     short loc_14025A7E0
0x14025a7bc  lea     r8, [rbp+57h+var_C0]
0x14025a7c0  mov     edx, edi
0x14025a7c2  mov     rcx, r12
0x14025a7c5  call    RssQueryInterfacePortInformation
0x14025a7ca  mov     r15, [rbp+57h+var_C0]
0x14025a7ce  test    eax, eax
0x14025a7d0  js      loc_14025AB81
0x14025a7d6  mov     eax, [r15+4]
0x14025a7da  mov     [rsp+110h+var_DC], eax
0x14025a7de  jmp     short loc_14025A7E4
0x14025a7e0  mov     [rsp+110h+var_DC], esi
0x14025a7e4  mov     edx, 90h
0x14025a7e9  mov     r8d, 42737352h
0x14025a7ef  lea     ecx, [rdx-50h]
0x14025a7f2  call    cs:__imp_ExAllocatePool2
0x14025a7f9  nop     dword ptr [rax+rax+00h]
0x14025a7fe  xor     r8d, r8d
0x14025a801  mov     rbx, rax
0x14025a804  test    rax, rax
0x14025a807  jnz     loc_14025A8B2
0x14025a80d  cmp     cs:dword_1402201D4, esi
0x14025a813  mov     r14d, 0C0000017h
0x14025a819  jnz     short loc_14025A856
0x14025a81b  test    byte ptr cs:WPP_MAIN_CB.Reserved+7, 10h
0x14025a822  jz      short loc_14025A856
0x14025a824  mov     [rbp+57h+var_C4], r8d
0x14025a828  lea     rdx, RSS_FAILURE
0x14025a82f  mov     dword ptr [rsp+110h+var_E8], r14d
0x14025a834  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025a83b  mov     dword ptr [rsp+110h+var_F0], r8d
0x14025a840  mov     r9d, edi
0x14025a843  lea     r8, [rbp+57h+var_D0]
0x14025a847  mov     [rbp+57h+var_D0], r13
0x14025a84b  mov     [rbp+57h+var_C8], edi
0x14025a84e  call    McTemplateK0qqq_EtwWriteTransfer
0x14025a853  xor     r8d, r8d
0x14025a856  mov     eax, cs:dword_1402201F8
0x14025a85c  cmp     eax, 5
0x14025a85f  jbe     loc_14025AB81
0x14025a865  mov     rdx, 200000000000h
0x14025a86f  lea     rcx, dword_1402201F8
0x14025a876  call    _tlgKeywordOn
0x14025a87b  test    al, al
0x14025a87d  jz      loc_14025AB81
0x14025a883  lea     rax, [rsp+110h+var_DC]
0x14025a888  mov     [rsp+110h+var_DC], edi
0x14025a88c  mov     [rbp+57h+var_70], rax
0x14025a890  lea     rdx, unk_1401F3A1D
0x14025a897  lea     rax, [rsp+110h+var_E0]
0x14025a89c  mov     [rsp+110h+var_E0], r8d
0x14025a8a1  mov     [rbp+57h+var_60], rax
0x14025a8a5  lea     rax, [rbp+57h+var_C0]
0x14025a8a9  mov     dword ptr [rbp+57h+var_C0], r14d
0x14025a8ad  jmp     loc_14025AB42
0x14025a8b2  lea     rcx, [rax+40h]; Mutex
0x14025a8b6  mov     [rax+80h], r8d
0x14025a8bd  mov     edx, esi; Level
0x14025a8bf  mov     [rax+30h], r8d
0x14025a8c3  mov     [rax+20h], r8
0x14025a8c7  mov     [rax+10h], r8
0x14025a8cb  mov     [rax+88h], rsi
0x14025a8d2  call    cs:__imp_KeInitializeMutex
0x14025a8d9  nop     dword ptr [rax+rax+00h]
0x14025a8de  mov     edx, [rsp+110h+var_DC]
0x14025a8e2  mov     ecx, 40h ; '@'
0x14025a8e7  shl     rdx, 4
0x14025a8eb  mov     r8d, 42737352h
0x14025a8f1  call    cs:__imp_ExAllocatePool2
0x14025a8f8  nop     dword ptr [rax+rax+00h]
0x14025a8fd  mov     edx, 42737352h; PoolTag
0x14025a902  mov     ecx, 200h; PoolType
0x14025a907  mov     [rbx+38h], rax
0x14025a90b  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14025a912  nop     dword ptr [rax+rax+00h]
0x14025a917  mov     edx, 42737352h; PoolTag
0x14025a91c  mov     ecx, 200h; PoolType
0x14025a921  mov     [rbx+28h], rax
0x14025a925  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14025a92c  nop     dword ptr [rax+rax+00h]
0x14025a931  xor     r8d, r8d
0x14025a934  mov     [rbx+18h], rax
0x14025a938  cmp     [rbx+38h], r8
0x14025a93c  jz      loc_14025AAA6
0x14025a942  mov     rcx, [rbx+28h]; RunRef
0x14025a946  test    rcx, rcx
0x14025a949  jz      loc_14025AAA6
0x14025a94f  test    rax, rax
0x14025a952  jz      loc_14025AAA6
0x14025a958  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14025a95f  nop     dword ptr [rax+rax+00h]
0x14025a964  mov     rcx, [rbx+18h]; RunRef
0x14025a968  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14025a96f  nop     dword ptr [rax+rax+00h]
0x14025a974  mov     eax, 2
0x14025a979  mov     [rbx+34h], edi
0x14025a97c  cmp     word ptr [rsp+110h+var_E0], ax
0x14025a981  jnz     short loc_14025A98D
0x14025a983  mov     rcx, [rbx+28h]
0x14025a987  mov     [rbx+20h], r12
0x14025a98b  jmp     short loc_14025A995
0x14025a98d  mov     rcx, [rbx+18h]; RunRefCacheAware
0x14025a991  mov     [rbx+10h], r12
0x14025a995  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14025a99c  nop     dword ptr [rax+rax+00h]
0x14025a9a1  cmp     r14d, esi
0x14025a9a4  jnz     short loc_14025A9C9
0x14025a9a6  mov     rax, [rbx+38h]
0x14025a9aa  lea     r9, [rbp+57h+var_B0]
0x14025a9ae  mov     r8, rbx
0x14025a9b1  mov     [rsp+110h+var_F0], rax
0x14025a9b6  xor     edx, edx
0x14025a9b8  mov     rcx, r12
0x14025a9bb  call    RssFindOrCreateAdapter
0x14025a9c0  test    al, al
0x14025a9c2  jz      short loc_14025AA1C
0x14025a9c4  add     [rbx+30h], esi
0x14025a9c7  jmp     short loc_14025AA1C
0x14025a9c9  xor     r14d, r14d
0x14025a9cc  cmp     [r15+4], r14d
0x14025a9d0  jbe     short loc_14025AA1C
0x14025a9d2  mov     edx, [r15+8]
0x14025a9d6  lea     r9, [rbp+57h+var_B0]
0x14025a9da  mov     ecx, [rbx+30h]
0x14025a9dd  mov     eax, r14d
0x14025a9e0  imul    eax, [r15+0Ch]
0x14025a9e5  mov     r8, rbx
0x14025a9e8  shl     rcx, 4
0x14025a9ec  add     rcx, [rbx+38h]
0x14025a9f0  mov     [rsp+110h+var_F0], rcx
0x14025a9f5  mov     rcx, r12
0x14025a9f8  add     rax, r15
0x14025a9fb  add     rdx, rax
0x14025a9fe  xor     eax, eax
0x14025aa00  cmp     [rdx+4], eax
0x14025aa03  cmovnz  r9, rax
0x14025aa07  call    RssFindOrCreateAdapter
0x14025aa0c  test    al, al
0x14025aa0e  jz      short loc_14025AA13
0x14025aa10  add     [rbx+30h], esi
0x14025aa13  add     r14d, esi
0x14025aa16  cmp     r14d, [r15+4]
0x14025aa1a  jb      short loc_14025A9D2
0x14025aa1c  or      dword ptr [rbx+80h], 18h
0x14025aa23  mov     rcx, rbx
0x14025aa26  call    RssQueueBindingWorkItemUnderLock
0x14025aa2b  mov     rax, cs:qword_140225FA8
0x14025aa32  lea     rcx, RssBindingList
0x14025aa39  cmp     [rax], rcx
0x14025aa3c  jz      short loc_14025AA45
0x14025aa3e  mov     ecx, 3
0x14025aa43  int     29h; Win8: RtlFailFast(ecx)
0x14025aa45  movzx   r14d, word ptr [rsp+110h+var_E0]
0x14025aa4b  mov     [rbx], rcx
0x14025aa4e  mov     [rbx+8], rax
0x14025aa52  mov     [rax], rbx
0x14025aa55  mov     cs:qword_140225FA8, rbx
0x14025aa5c  cmp     cs:dword_1402201D4, esi
0x14025aa62  jnz     short loc_14025AA9F
0x14025aa64  mov     edx, 4
0x14025aa69  test    byte ptr cs:WPP_MAIN_CB.Reserved+7, dl
0x14025aa6f  jz      short loc_14025AA9F
0x14025aa71  mov     r9d, edi
0x14025aa74  mov     [rbp+57h+var_C4], 0
0x14025aa7b  lea     r8, [rbp+57h+var_D0]
0x14025aa7f  mov     [rbp+57h+var_D0], r13
0x14025aa83  lea     rdx, RSS_BINDING_BIND_COMPLETE
0x14025aa8a  mov     [rbp+57h+var_C8], edi
0x14025aa8d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025aa94  mov     word ptr [rsp+110h+var_F0], r14w
0x14025aa9a  call    McTemplateK0qh_EtwWriteTransfer
0x14025aa9f  xor     ebx, ebx
0x14025aaa1  jmp     loc_14025AB88
0x14025aaa6  cmp     cs:dword_1402201D4, esi
0x14025aaac  mov     r14d, 0C0000017h
0x14025aab2  jnz     short loc_14025AAEF
0x14025aab4  test    byte ptr cs:WPP_MAIN_CB.Reserved+7, 10h
0x14025aabb  jz      short loc_14025AAEF
0x14025aabd  mov     [rbp+57h+var_C4], r8d
0x14025aac1  lea     rdx, RSS_FAILURE
  ... truncated ...
```
