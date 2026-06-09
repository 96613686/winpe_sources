# RssControlAddInterface

- ea: `0x14025e580`
- end: `0x14025ebcb`
- name: `RssControlAddInterface`
- size: `1611`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x1400fb148`
- `0x140108a60`
- `0x140113ff0`
- `0x14011653c`
- `0x140129a14`
- `0x14012d53c`
- `0x14012f4b0`
- `0x140131ee0`
- `0x14015c4e8`
- `0x1401b6608`
- `0x1401c0fd0`
- `0x14025a638`
- `0x14025aa38`
- `0x14025c5d8`
- `0x14025d304`
- `0x14025d64c`
- `0x14025e580`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14025eb6e`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14025eb83`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14025eb6e`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14025eb83`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14025e8ab`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14025e8c5`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14025e8ab`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14025e8c5`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14025e8f8`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14025e908`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14025e8f8`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14025e908`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14025e6ef`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14025e935`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14025e6ef`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14025e935`
- `ntoskrnl!KeInitializeMutex` at `0x14025e872`
- `ntoskrnl!KeInitializeMutex` at `0x14025e872`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025eb3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025eb59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025eb97`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025eb3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025eb59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14025eb97`
- `ntoskrnl!ExAllocatePool2` at `0x14025e792`
- `ntoskrnl!ExAllocatePool2` at `0x14025e891`
- `ntoskrnl!ExAllocatePool2` at `0x14025e792`
- `ntoskrnl!ExAllocatePool2` at `0x14025e891`

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
  __int64 *v17; // rdx
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
      if ( dword_1402241D4 == 1 && (HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) & 2) != 0 )
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
  if ( dword_1402241D4 == 1 && (HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) & 2) != 0 )
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
  if ( dword_1402241D4 == 1 && (HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) & 2) != 0 )
  {
    v35 = 0;
    v33 = &RssStartedModules;
    v34 = a2;
    McTemplateK0qq_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, RSS_BINDING_CAPABILITY, &v33, a2, v12);
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
    if ( dword_1402241D4 == 1 && (HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
    {
      v35 = 0;
      v33 = &RssStartedModules;
      v34 = a2;
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)RSS_FAILURE,
        (unsigned int)&v33,
        a2,
        0,
        23);
    }
    if ( (unsigned int)dword_1402241F8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1402241F8, 0x200000000000LL) )
      goto LABEL_64;
    v42 = (__int64 **)((char *)&v31 + 4);
    v17 = (__int64 *)byte_1401F759D;
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
    if ( dword_1402241D4 == 1 && (HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x10) != 0 )
    {
      v35 = 0;
      v33 = &RssStartedModules;
      v34 = a2;
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)RSS_FAILURE,
        (unsigned int)&v33,
        a2,
        0,
        23);
    }
    if ( (unsigned int)dword_1402241F8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1402241F8, 0x200000000000LL) )
      goto LABEL_64;
    LODWORD(v36) = a2;
    v42 = &v36;
    v17 = qword_1401F75E0;
    HIDWORD(v31) = v26;
    v44 = (unsigned __int64 *)((char *)&v31 + 4);
    v18 = (__int64 **)&v31;
    LODWORD(v31) = -1073741801;
LABEL_63:
    v46 = v18;
    v43 = 4;
    v45 = 4;
    v47 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_1402241F8, v17, 0, 0, 5, v41, v31);
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
  v25 = (_QWORD *)qword_14022A088;
  if ( *(PVOID **)qword_14022A088 != &RssBindingList )
    __fastfail(3u);
  v6 = v31;
  *(_QWORD *)v9 = &RssBindingList;
  *((_QWORD *)v9 + 1) = v25;
  *v25 = v9;
  qword_14022A088 = (__int64)v9;
LABEL_53:
  if ( dword_1402241D4 == 1 && (HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
  {
    v35 = 0;
    v33 = &RssStartedModules;
    v34 = a2;
    LOWORD(v30) = v6;
    McTemplateK0qh_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, RSS_BINDING_BIND_COMPLETE, &v33, a2, v30);
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
0x14025e580  mov     [rsp-8+arg_0], rbx
0x14025e585  push    rbp
0x14025e586  push    rsi
0x14025e587  push    rdi
0x14025e588  push    r12
0x14025e58a  push    r13
0x14025e58c  push    r14
0x14025e58e  push    r15
0x14025e590  lea     rbp, [rsp-27h]
0x14025e595  sub     rsp, 0E0h
0x14025e59c  mov     rax, cs:__security_cookie
0x14025e5a3  xor     rax, rsp
0x14025e5a6  mov     [rbp+57h+var_40], rax
0x14025e5aa  xor     eax, eax
0x14025e5ac  mov     word ptr [rsp+110h+var_E0], cx
0x14025e5b1  xor     r15d, r15d
0x14025e5b4  mov     [rbp+57h+var_A0], eax
0x14025e5b7  mov     [rsp+110h+var_D8], eax
0x14025e5bb  xorps   xmm0, xmm0
0x14025e5be  mov     r12, r8
0x14025e5c1  mov     [rbp+57h+var_C0], r15
0x14025e5c5  mov     edi, edx
0x14025e5c7  movzx   r14d, cx
0x14025e5cb  lea     eax, [r15+2]
0x14025e5cf  movups  [rbp+57h+var_B0], xmm0
0x14025e5d3  cmp     cx, ax
0x14025e5d6  jz      short loc_14025E5E2
0x14025e5d8  cmp     cx, 17h
0x14025e5dc  jnz     loc_14025EBA3
0x14025e5e2  call    RssLockBindingList
0x14025e5e7  mov     rbx, cs:RssBindingList
0x14025e5ee  lea     rax, RssBindingList
0x14025e5f5  jmp     short loc_14025E603
0x14025e5f7  cmp     [rbx+34h], edi
0x14025e5fa  jz      loc_14025E68D
0x14025e600  mov     rbx, [rbx]
0x14025e603  cmp     rbx, rax
0x14025e606  jnz     short loc_14025E5F7
0x14025e608  mov     ecx, edi
0x14025e60a  xor     ebx, ebx
0x14025e60c  call    RssTraceBindingActivityStart
0x14025e611  lea     esi, [rbx+1]
0x14025e614  cmp     cs:dword_1402241D4, esi
0x14025e61a  lea     r13, RssStartedModules
0x14025e621  jnz     short loc_14025E653
0x14025e623  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, 2
0x14025e62a  jz      short loc_14025E653
0x14025e62c  mov     dword ptr [rsp+110h+var_E8], esi
0x14025e630  lea     r8, [rbp+57h+var_D0]
0x14025e634  mov     r9d, edi
0x14025e637  mov     word ptr [rsp+110h+var_F0], r14w
0x14025e63d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025e644  mov     [rbp+57h+var_C4], ebx
0x14025e647  mov     [rbp+57h+var_D0], r13
0x14025e64b  mov     [rbp+57h+var_C8], edi
0x14025e64e  call    McTemplateK0qhq_EtwWriteTransfer
0x14025e653  lea     r8, [rsp+110h+var_D8]
0x14025e658  mov     [rsp+110h+var_D8], edi
0x14025e65c  xor     edx, edx
0x14025e65e  mov     rcx, r12
0x14025e661  call    RssQueryPortIndex
0x14025e666  mov     r8d, [rsp+110h+var_D8]
0x14025e66b  lea     rax, [rbp+57h+var_B0]
0x14025e66f  mov     r9b, sil
0x14025e672  mov     [rsp+110h+var_F0], rax
0x14025e677  xor     edx, edx
0x14025e679  mov     rcx, r12
0x14025e67c  call    RssQueryPortRssInfo
0x14025e681  test    eax, eax
0x14025e683  jns     short loc_14025E700
0x14025e685  xor     r14d, r14d
0x14025e688  jmp     loc_14025E713
0x14025e68d  mov     esi, 1
0x14025e692  lea     r13, RssStartedModules
0x14025e699  cmp     cs:dword_1402241D4, esi
0x14025e69f  jnz     short loc_14025E6D2
0x14025e6a1  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, 2
0x14025e6a8  jz      short loc_14025E6D2
0x14025e6aa  mov     dword ptr [rsp+110h+var_E8], esi
0x14025e6ae  lea     r8, [rbp+57h+var_C0]
0x14025e6b2  mov     r9d, edi
0x14025e6b5  mov     word ptr [rsp+110h+var_F0], r14w
0x14025e6bb  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025e6c2  mov     [rbp+57h+var_B4], r15d
0x14025e6c6  mov     [rbp+57h+var_C0], r13
0x14025e6ca  mov     [rbp+57h+var_B8], edi
0x14025e6cd  call    McTemplateK0qhq_EtwWriteTransfer
0x14025e6d2  mov     eax, 2
0x14025e6d7  cmp     r14w, ax
0x14025e6db  jnz     short loc_14025E6E7
0x14025e6dd  mov     rcx, [rbx+28h]
0x14025e6e1  mov     [rbx+20h], r12
0x14025e6e5  jmp     short loc_14025E6EF
0x14025e6e7  mov     rcx, [rbx+18h]; RunRefCacheAware
0x14025e6eb  mov     [rbx+10h], r12
0x14025e6ef  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14025e6f6  nop     dword ptr [rax+rax+00h]
0x14025e6fb  jmp     loc_14025E9FC
0x14025e700  mov     eax, dword ptr [rbp+57h+var_B0+4]
0x14025e703  and     eax, 10000000h
0x14025e708  neg     eax
0x14025e70a  sbb     r14d, r14d
0x14025e70d  neg     r14d
0x14025e710  add     r14d, esi
0x14025e713  cmp     cs:dword_1402241D4, esi
0x14025e719  jnz     short loc_14025E74D
0x14025e71b  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, 2
0x14025e722  jz      short loc_14025E74D
0x14025e724  mov     r9d, edi
0x14025e727  mov     [rbp+57h+var_C4], ebx
0x14025e72a  lea     r8, [rbp+57h+var_D0]
0x14025e72e  mov     [rbp+57h+var_D0], r13
0x14025e732  lea     rdx, RSS_BINDING_CAPABILITY
0x14025e739  mov     [rbp+57h+var_C8], edi
0x14025e73c  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025e743  mov     dword ptr [rsp+110h+var_F0], r14d
0x14025e748  call    McTemplateK0qq_EtwWriteTransfer
0x14025e74d  test    r14d, r14d
0x14025e750  jz      loc_14025EB21
0x14025e756  cmp     r14d, 2
0x14025e75a  jnz     short loc_14025E780
0x14025e75c  lea     r8, [rbp+57h+var_C0]
0x14025e760  mov     edx, edi
0x14025e762  mov     rcx, r12
0x14025e765  call    RssQueryInterfacePortInformation
0x14025e76a  mov     r15, [rbp+57h+var_C0]
0x14025e76e  test    eax, eax
0x14025e770  js      loc_14025EB21
0x14025e776  mov     eax, [r15+4]
0x14025e77a  mov     [rsp+110h+var_DC], eax
0x14025e77e  jmp     short loc_14025E784
0x14025e780  mov     [rsp+110h+var_DC], esi
0x14025e784  mov     edx, 90h
0x14025e789  mov     r8d, 42737352h
0x14025e78f  lea     ecx, [rdx-50h]
0x14025e792  call    cs:__imp_ExAllocatePool2
0x14025e799  nop     dword ptr [rax+rax+00h]
0x14025e79e  xor     r8d, r8d
0x14025e7a1  mov     rbx, rax
0x14025e7a4  test    rax, rax
0x14025e7a7  jnz     loc_14025E852
0x14025e7ad  cmp     cs:dword_1402241D4, esi
0x14025e7b3  mov     r14d, 0C0000017h
0x14025e7b9  jnz     short loc_14025E7F6
0x14025e7bb  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, 10h
0x14025e7c2  jz      short loc_14025E7F6
0x14025e7c4  mov     [rbp+57h+var_C4], r8d
0x14025e7c8  lea     rdx, RSS_FAILURE
0x14025e7cf  mov     dword ptr [rsp+110h+var_E8], r14d
0x14025e7d4  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025e7db  mov     dword ptr [rsp+110h+var_F0], r8d
0x14025e7e0  mov     r9d, edi
0x14025e7e3  lea     r8, [rbp+57h+var_D0]
0x14025e7e7  mov     [rbp+57h+var_D0], r13
0x14025e7eb  mov     [rbp+57h+var_C8], edi
0x14025e7ee  call    McTemplateK0qqq_EtwWriteTransfer
0x14025e7f3  xor     r8d, r8d
0x14025e7f6  mov     eax, cs:dword_1402241F8
0x14025e7fc  cmp     eax, 5
0x14025e7ff  jbe     loc_14025EB21
0x14025e805  mov     rdx, 200000000000h
0x14025e80f  lea     rcx, dword_1402241F8
0x14025e816  call    _tlgKeywordOn
0x14025e81b  test    al, al
0x14025e81d  jz      loc_14025EB21
0x14025e823  lea     rax, [rsp+110h+var_DC]
0x14025e828  mov     [rsp+110h+var_DC], edi
0x14025e82c  mov     [rbp+57h+var_70], rax
0x14025e830  lea     rdx, byte_1401F759D
0x14025e837  lea     rax, [rsp+110h+var_E0]
0x14025e83c  mov     [rsp+110h+var_E0], r8d
0x14025e841  mov     [rbp+57h+var_60], rax
0x14025e845  lea     rax, [rbp+57h+var_C0]
0x14025e849  mov     dword ptr [rbp+57h+var_C0], r14d
0x14025e84d  jmp     loc_14025EAE2
0x14025e852  lea     rcx, [rax+40h]; Mutex
0x14025e856  mov     [rax+80h], r8d
0x14025e85d  mov     edx, esi; Level
0x14025e85f  mov     [rax+30h], r8d
0x14025e863  mov     [rax+20h], r8
0x14025e867  mov     [rax+10h], r8
0x14025e86b  mov     [rax+88h], rsi
0x14025e872  call    cs:__imp_KeInitializeMutex
0x14025e879  nop     dword ptr [rax+rax+00h]
0x14025e87e  mov     edx, [rsp+110h+var_DC]
0x14025e882  mov     ecx, 40h ; '@'
0x14025e887  shl     rdx, 4
0x14025e88b  mov     r8d, 42737352h
0x14025e891  call    cs:__imp_ExAllocatePool2
0x14025e898  nop     dword ptr [rax+rax+00h]
0x14025e89d  mov     edx, 42737352h; PoolTag
0x14025e8a2  mov     ecx, 200h; PoolType
0x14025e8a7  mov     [rbx+38h], rax
0x14025e8ab  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14025e8b2  nop     dword ptr [rax+rax+00h]
0x14025e8b7  mov     edx, 42737352h; PoolTag
0x14025e8bc  mov     ecx, 200h; PoolType
0x14025e8c1  mov     [rbx+28h], rax
0x14025e8c5  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14025e8cc  nop     dword ptr [rax+rax+00h]
0x14025e8d1  xor     r8d, r8d
0x14025e8d4  mov     [rbx+18h], rax
0x14025e8d8  cmp     [rbx+38h], r8
0x14025e8dc  jz      loc_14025EA46
0x14025e8e2  mov     rcx, [rbx+28h]; RunRef
0x14025e8e6  test    rcx, rcx
0x14025e8e9  jz      loc_14025EA46
0x14025e8ef  test    rax, rax
0x14025e8f2  jz      loc_14025EA46
0x14025e8f8  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14025e8ff  nop     dword ptr [rax+rax+00h]
0x14025e904  mov     rcx, [rbx+18h]; RunRef
0x14025e908  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14025e90f  nop     dword ptr [rax+rax+00h]
0x14025e914  mov     eax, 2
0x14025e919  mov     [rbx+34h], edi
0x14025e91c  cmp     word ptr [rsp+110h+var_E0], ax
0x14025e921  jnz     short loc_14025E92D
0x14025e923  mov     rcx, [rbx+28h]
0x14025e927  mov     [rbx+20h], r12
0x14025e92b  jmp     short loc_14025E935
0x14025e92d  mov     rcx, [rbx+18h]; RunRefCacheAware
0x14025e931  mov     [rbx+10h], r12
0x14025e935  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14025e93c  nop     dword ptr [rax+rax+00h]
0x14025e941  cmp     r14d, esi
0x14025e944  jnz     short loc_14025E969
0x14025e946  mov     rax, [rbx+38h]
0x14025e94a  lea     r9, [rbp+57h+var_B0]
0x14025e94e  mov     r8, rbx
0x14025e951  mov     [rsp+110h+var_F0], rax
0x14025e956  xor     edx, edx
0x14025e958  mov     rcx, r12
0x14025e95b  call    RssFindOrCreateAdapter
0x14025e960  test    al, al
0x14025e962  jz      short loc_14025E9BC
0x14025e964  add     [rbx+30h], esi
0x14025e967  jmp     short loc_14025E9BC
0x14025e969  xor     r14d, r14d
0x14025e96c  cmp     [r15+4], r14d
0x14025e970  jbe     short loc_14025E9BC
0x14025e972  mov     edx, [r15+8]
0x14025e976  lea     r9, [rbp+57h+var_B0]
0x14025e97a  mov     ecx, [rbx+30h]
0x14025e97d  mov     eax, r14d
0x14025e980  imul    eax, [r15+0Ch]
0x14025e985  mov     r8, rbx
0x14025e988  shl     rcx, 4
0x14025e98c  add     rcx, [rbx+38h]
0x14025e990  mov     [rsp+110h+var_F0], rcx
0x14025e995  mov     rcx, r12
0x14025e998  add     rax, r15
0x14025e99b  add     rdx, rax
0x14025e99e  xor     eax, eax
0x14025e9a0  cmp     [rdx+4], eax
0x14025e9a3  cmovnz  r9, rax
0x14025e9a7  call    RssFindOrCreateAdapter
0x14025e9ac  test    al, al
0x14025e9ae  jz      short loc_14025E9B3
0x14025e9b0  add     [rbx+30h], esi
0x14025e9b3  add     r14d, esi
0x14025e9b6  cmp     r14d, [r15+4]
0x14025e9ba  jb      short loc_14025E972
0x14025e9bc  or      dword ptr [rbx+80h], 18h
0x14025e9c3  mov     rcx, rbx
0x14025e9c6  call    RssQueueBindingWorkItemUnderLock
0x14025e9cb  mov     rax, cs:qword_14022A088
0x14025e9d2  lea     rcx, RssBindingList
0x14025e9d9  cmp     [rax], rcx
0x14025e9dc  jz      short loc_14025E9E5
0x14025e9de  mov     ecx, 3
0x14025e9e3  int     29h; Win8: RtlFailFast(ecx)
0x14025e9e5  movzx   r14d, word ptr [rsp+110h+var_E0]
0x14025e9eb  mov     [rbx], rcx
0x14025e9ee  mov     [rbx+8], rax
0x14025e9f2  mov     [rax], rbx
0x14025e9f5  mov     cs:qword_14022A088, rbx
0x14025e9fc  cmp     cs:dword_1402241D4, esi
0x14025ea02  jnz     short loc_14025EA3F
0x14025ea04  mov     edx, 4
0x14025ea09  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, dl
0x14025ea0f  jz      short loc_14025EA3F
0x14025ea11  mov     r9d, edi
0x14025ea14  mov     [rbp+57h+var_C4], 0
0x14025ea1b  lea     r8, [rbp+57h+var_D0]
0x14025ea1f  mov     [rbp+57h+var_D0], r13
0x14025ea23  lea     rdx, RSS_BINDING_BIND_COMPLETE
0x14025ea2a  mov     [rbp+57h+var_C8], edi
0x14025ea2d  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14025ea34  mov     word ptr [rsp+110h+var_F0], r14w
0x14025ea3a  call    McTemplateK0qh_EtwWriteTransfer
0x14025ea3f  xor     ebx, ebx
0x14025ea41  jmp     loc_14025EB28
0x14025ea46  cmp     cs:dword_1402241D4, esi
0x14025ea4c  mov     r14d, 0C0000017h
0x14025ea52  jnz     short loc_14025EA8F
0x14025ea54  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, 10h
0x14025ea5b  jz      short loc_14025EA8F
0x14025ea5d  mov     [rbp+57h+var_C4], r8d
0x14025ea61  lea     rdx, RSS_FAILURE
  ... truncated ...
```
