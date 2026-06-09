# DeleteNvmeAdapter

- ea: `0x1400f33e0`
- end: `0x1400f375c`
- name: `DeleteNvmeAdapter`
- size: `892`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1400979a0`
- `0x1401a82c8`

## callees

- `0x140048534`
- `0x14006f4ec`
- `0x140070394`
- `0x140076c00`
- `0x14007706c`
- `0x140077550`
- `0x1400e8b98`
- `0x1400f33e0`
- `0x1400fa09c`
- `0x14013a784`
- `0x140187e04`
- `0x140187e5c`
- `0x140190678`
- `0x140191698`
- `0x1401b76e8`
- `0x1401c0674`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400f340d`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400f340d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400f3446`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400f361c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400f362f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400f3446`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400f361c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400f362f`
- `ntoskrnl!IoFreeWorkItem` at `0x1400f3551`
- `ntoskrnl!IoFreeWorkItem` at `0x1400f3551`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3425`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3474`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3489`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f35ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3683`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f36a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f36c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f36f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3736`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3425`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3474`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3489`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f35ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3683`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f36a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f36c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f36f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f3736`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f351e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f351e`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400f365f`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400f365f`

## pseudocode

```c
void __fastcall DeleteNvmeAdapter(__int64 a1)
{
  void *v2; // rax
  _QWORD **v3; // rbx
  _QWORD *v4; // rcx
  _QWORD *v5; // rax
  struct _IO_WORKITEM *v6; // rcx
  unsigned __int64 v7; // rdx
  void *v8; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  __int64 v13; // rax
  void *v14; // rcx
  _QWORD *v15; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_QWORD *)(a1 + 616) )
  {
    NvmeAdapterFreeHostGateways();
    ExDeleteResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 616) + 24LL));
    ExFreePoolWithTag(*(PVOID *)(a1 + 616), 0x464E6152u);
    *(_QWORD *)(a1 + 616) = 0;
  }
  RtlFreeUnicodeString((PUNICODE_STRING)(*(_QWORD *)(a1 + 168) + 336LL));
  if ( *(_QWORD *)(a1 + 1344) )
  {
    v2 = (void *)NvmeIgnoredNamespacesSwapWhenFree(a1, 0);
    if ( v2 )
      ExFreePoolWithTag(v2, 0x504F6152u);
    ExFreePoolWithTag(*(PVOID *)(a1 + 1344), 0x504F6152u);
    *(_QWORD *)(a1 + 1344) = 0;
  }
  NvmeAdapterPowerUninitialize(a1);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 408) + 184LL) & 0x40000000) != 0 && *(_QWORD *)(a1 + 1152) )
  {
    NvmeAdapterDeleteNvmeController((PVOID *)(a1 + 1152));
  }
  else if ( (*(_DWORD *)(a1 + 424) & 0x40) != 0 )
  {
    NvmeAdapterAcquireStorMQControllerListLockExclusive(a1);
    v3 = (_QWORD **)(a1 + 1200);
    while ( 1 )
    {
      v4 = *v3;
      if ( *v3 == v3 )
        break;
      if ( (_QWORD **)v4[1] != v3 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
        __fastfail(3u);
      *v3 = v5;
      v5[1] = v3;
      --*(_DWORD *)(a1 + 1216);
      v15 = v4 - 14;
      ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v4[55]);
      NvmeAdapterDeleteNvmeController((PVOID *)&v15);
    }
    NvmeAdapterReleaseStorMQControllerListLockExclusive(a1);
    v6 = *(struct _IO_WORKITEM **)(a1 + 1224);
    if ( v6 )
    {
      IoFreeWorkItem(v6);
      *(_QWORD *)(a1 + 1224) = 0;
    }
  }
  PortFreeRegistryBuffer(a1 + 920);
  *(_DWORD *)(a1 + 976) = 0;
  v7 = (unsigned __int64)*(unsigned int *)(a1 + 152) >> 12;
  LOBYTE(v7) = (*(_DWORD *)(a1 + 152) & 0x1000LL) == 0;
  RaDeleteMiniport(a1 + 176, v7);
  if ( *(_DWORD *)(a1 + 1248) )
    StorFreeContiguousMemory(a1 + 1160);
  RaidDeleteDeferredQueue(a1 + 624);
  RaidDeleteDeferredQueue(a1 + 752);
  if ( *(_QWORD *)(a1 + 912) )
  {
    PortFreeDriverParameters();
    *(_QWORD *)(a1 + 912) = 0;
  }
  v8 = *(void **)(a1 + 1016);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0x52446152u);
    *(_QWORD *)(a1 + 1016) = 0;
  }
  if ( (*(_DWORD *)(a1 + 152) & 0x1000LL) != 0 )
    RaidDeleteDma(a1 + 1160);
  RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 880));
  RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 896));
  RaDriverDeleteDevice(a1);
  v9 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 160);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  if ( v9 )
  {
    ExFreeCacheAwareRundownProtection(v9);
    *(_QWORD *)(a1 + 160) = 0;
  }
  v10 = *(void **)(a1 + 1040);
  if ( v10 )
  {
    ExFreePoolWithTag(v10, 0x54456152u);
    *(_QWORD *)(a1 + 1040) = 0;
  }
  v11 = *(void **)(a1 + 48);
  if ( v11 )
    ExFreePoolWithTag(v11, 0x53446152u);
  v12 = *(void **)(a1 + 600);
  if ( v12 )
  {
    ExFreePoolWithTag(v12, 0x564E6152u);
    *(_QWORD *)(a1 + 600) = 0;
  }
  v13 = *(_QWORD *)(a1 + 608);
  if ( v13 )
  {
    v14 = *(void **)(v13 + 128);
    if ( v14 )
    {
      ExFreePoolWithTag(v14, 0x72446152u);
      *(_QWORD *)(*(_QWORD *)(a1 + 608) + 128LL) = 0;
    }
    RaidDeleteResourceList(*(_QWORD *)(a1 + 608) + 88LL);
    RaDeleteBus(*(_QWORD *)(a1 + 608) + 16LL);
    ExFreePoolWithTag(*(PVOID *)(a1 + 608), 0x564E6152u);
    *(_QWORD *)(a1 + 608) = 0;
  }
  *(_DWORD *)a1 = 0;
}

```

## disassembly

```asm
0x1400f33e0  mov     [rsp+arg_8], rbx
0x1400f33e5  mov     [rsp+arg_10], rsi
0x1400f33ea  push    rdi
0x1400f33eb  sub     rsp, 20h
0x1400f33ef  xor     esi, esi
0x1400f33f1  mov     rdi, rcx
0x1400f33f4  cmp     [rcx+268h], rsi
0x1400f33fb  jz      short loc_1400F3438
0x1400f33fd  call    NvmeAdapterFreeHostGateways
0x1400f3402  mov     rcx, [rdi+268h]
0x1400f3409  add     rcx, 18h; Resource
0x1400f340d  call    cs:__imp_ExDeleteResourceLite
0x1400f3414  nop     dword ptr [rax+rax+00h]
0x1400f3419  mov     rcx, [rdi+268h]; P
0x1400f3420  mov     edx, 464E6152h; Tag
0x1400f3425  call    cs:__imp_ExFreePoolWithTag
0x1400f342c  nop     dword ptr [rax+rax+00h]
0x1400f3431  mov     [rdi+268h], rsi
0x1400f3438  mov     rcx, [rdi+0A8h]
0x1400f343f  add     rcx, 150h; UnicodeString
0x1400f3446  call    cs:__imp_RtlFreeUnicodeString
0x1400f344d  nop     dword ptr [rax+rax+00h]
0x1400f3452  cmp     [rdi+540h], rsi
0x1400f3459  jz      short loc_1400F349C
0x1400f345b  xor     edx, edx
0x1400f345d  mov     rcx, rdi
0x1400f3460  call    NvmeIgnoredNamespacesSwapWhenFree
0x1400f3465  mov     ebx, 504F6152h
0x1400f346a  test    rax, rax
0x1400f346d  jz      short loc_1400F3480
0x1400f346f  mov     edx, ebx; Tag
0x1400f3471  mov     rcx, rax; P
0x1400f3474  call    cs:__imp_ExFreePoolWithTag
0x1400f347b  nop     dword ptr [rax+rax+00h]
0x1400f3480  mov     rcx, [rdi+540h]; P
0x1400f3487  mov     edx, ebx; Tag
0x1400f3489  call    cs:__imp_ExFreePoolWithTag
0x1400f3490  nop     dword ptr [rax+rax+00h]
0x1400f3495  mov     [rdi+540h], rsi
0x1400f349c  mov     rcx, rdi
0x1400f349f  call    NvmeAdapterPowerUninitialize
0x1400f34a4  mov     rax, [rdi+198h]
0x1400f34ab  test    dword ptr [rax+0B8h], 40000000h
0x1400f34b5  jz      short loc_1400F34CD
0x1400f34b7  lea     rcx, [rdi+480h]
0x1400f34be  cmp     [rcx], rsi
0x1400f34c1  jz      short loc_1400F34CD
0x1400f34c3  call    NvmeAdapterDeleteNvmeController
0x1400f34c8  jmp     loc_1400F3564
0x1400f34cd  mov     eax, [rdi+1A8h]
0x1400f34d3  test    al, 40h
0x1400f34d5  jz      loc_1400F3564
0x1400f34db  mov     rcx, rdi
0x1400f34de  call    NvmeAdapterAcquireStorMQControllerListLockExclusive
0x1400f34e3  lea     rbx, [rdi+4B0h]
0x1400f34ea  mov     rcx, [rbx]
0x1400f34ed  cmp     rcx, rbx
0x1400f34f0  jz      short loc_1400F353D
0x1400f34f2  cmp     [rcx+8], rbx
0x1400f34f6  jnz     short loc_1400F3536
0x1400f34f8  mov     rax, [rcx]
0x1400f34fb  cmp     [rax+8], rcx
0x1400f34ff  jnz     short loc_1400F3536
0x1400f3501  mov     [rbx], rax
0x1400f3504  add     rcx, 0FFFFFFFFFFFFFF90h
0x1400f3508  mov     [rax+8], rbx
0x1400f350c  dec     dword ptr [rdi+4C0h]
0x1400f3512  mov     [rsp+28h+arg_0], rcx
0x1400f3517  mov     rcx, [rcx+228h]; RunRefCacheAware
0x1400f351e  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400f3525  nop     dword ptr [rax+rax+00h]
0x1400f352a  lea     rcx, [rsp+28h+arg_0]
0x1400f352f  call    NvmeAdapterDeleteNvmeController
0x1400f3534  jmp     short loc_1400F34EA
0x1400f3536  mov     ecx, 3
0x1400f353b  int     29h; Win8: RtlFailFast(ecx)
0x1400f353d  mov     rcx, rdi
0x1400f3540  call    NvmeAdapterReleaseStorMQControllerListLockExclusive
0x1400f3545  mov     rcx, [rdi+4C8h]; IoWorkItem
0x1400f354c  test    rcx, rcx
0x1400f354f  jz      short loc_1400F3564
0x1400f3551  call    cs:__imp_IoFreeWorkItem
0x1400f3558  nop     dword ptr [rax+rax+00h]
0x1400f355d  mov     [rdi+4C8h], rsi
0x1400f3564  lea     rbx, [rdi+398h]
0x1400f356b  mov     rcx, rbx
0x1400f356e  call    PortFreeRegistryBuffer
0x1400f3573  mov     [rbx+38h], esi
0x1400f3576  lea     rcx, [rdi+0B0h]
0x1400f357d  mov     edx, [rdi+98h]
0x1400f3583  shr     rdx, 0Ch
0x1400f3587  not     dl
0x1400f3589  and     dl, 1
0x1400f358c  call    RaDeleteMiniport
0x1400f3591  lea     rdx, [rdi+4D0h]
0x1400f3598  lea     rbx, [rdi+488h]
0x1400f359f  cmp     [rdx+10h], esi
0x1400f35a2  jz      short loc_1400F35AC
0x1400f35a4  mov     rcx, rbx
0x1400f35a7  call    StorFreeContiguousMemory
0x1400f35ac  lea     rcx, [rdi+270h]
0x1400f35b3  call    RaidDeleteDeferredQueue
0x1400f35b8  lea     rcx, [rdi+2F0h]
0x1400f35bf  call    RaidDeleteDeferredQueue
0x1400f35c4  mov     rcx, [rdi+390h]
0x1400f35cb  test    rcx, rcx
0x1400f35ce  jz      short loc_1400F35DC
0x1400f35d0  call    PortFreeDriverParameters
0x1400f35d5  mov     [rdi+390h], rsi
0x1400f35dc  mov     rcx, [rdi+3F8h]; P
0x1400f35e3  test    rcx, rcx
0x1400f35e6  jz      short loc_1400F3600
0x1400f35e8  mov     edx, 52446152h; Tag
0x1400f35ed  call    cs:__imp_ExFreePoolWithTag
0x1400f35f4  nop     dword ptr [rax+rax+00h]
0x1400f35f9  mov     [rdi+3F8h], rsi
0x1400f3600  mov     eax, [rdi+98h]
0x1400f3606  bt      rax, 0Ch
0x1400f360b  jnb     short loc_1400F3615
0x1400f360d  mov     rcx, rbx
0x1400f3610  call    RaidDeleteDma
0x1400f3615  lea     rcx, [rdi+370h]; UnicodeString
0x1400f361c  call    cs:__imp_RtlFreeUnicodeString
0x1400f3623  nop     dword ptr [rax+rax+00h]
0x1400f3628  lea     rcx, [rdi+380h]; UnicodeString
0x1400f362f  call    cs:__imp_RtlFreeUnicodeString
0x1400f3636  nop     dword ptr [rax+rax+00h]
0x1400f363b  mov     rcx, rdi
0x1400f363e  call    RaDriverDeleteDevice
0x1400f3643  mov     rcx, [rdi+0A0h]; RunRefCacheAware
0x1400f364a  mov     [rdi+8], rsi
0x1400f364e  mov     [rdi+10h], rsi
0x1400f3652  mov     [rdi+18h], rsi
0x1400f3656  mov     [rdi+20h], rsi
0x1400f365a  test    rcx, rcx
0x1400f365d  jz      short loc_1400F3672
0x1400f365f  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400f3666  nop     dword ptr [rax+rax+00h]
0x1400f366b  mov     [rdi+0A0h], rsi
0x1400f3672  mov     rcx, [rdi+410h]; P
0x1400f3679  test    rcx, rcx
0x1400f367c  jz      short loc_1400F3696
0x1400f367e  mov     edx, 54456152h; Tag
0x1400f3683  call    cs:__imp_ExFreePoolWithTag
0x1400f368a  nop     dword ptr [rax+rax+00h]
0x1400f368f  mov     [rdi+410h], rsi
0x1400f3696  mov     rcx, [rdi+30h]; P
0x1400f369a  test    rcx, rcx
0x1400f369d  jz      short loc_1400F36B0
0x1400f369f  mov     edx, 53446152h; Tag
0x1400f36a4  call    cs:__imp_ExFreePoolWithTag
0x1400f36ab  nop     dword ptr [rax+rax+00h]
0x1400f36b0  mov     rcx, [rdi+258h]; P
0x1400f36b7  mov     ebx, 564E6152h
0x1400f36bc  test    rcx, rcx
0x1400f36bf  jz      short loc_1400F36D6
0x1400f36c1  mov     edx, ebx; Tag
0x1400f36c3  call    cs:__imp_ExFreePoolWithTag
0x1400f36ca  nop     dword ptr [rax+rax+00h]
0x1400f36cf  mov     [rdi+258h], rsi
0x1400f36d6  mov     rax, [rdi+260h]
0x1400f36dd  test    rax, rax
0x1400f36e0  jz      short loc_1400F3749
0x1400f36e2  mov     rcx, [rax+80h]; P
0x1400f36e9  test    rcx, rcx
0x1400f36ec  jz      short loc_1400F370D
0x1400f36ee  mov     edx, 72446152h; Tag
0x1400f36f3  call    cs:__imp_ExFreePoolWithTag
0x1400f36fa  nop     dword ptr [rax+rax+00h]
0x1400f36ff  mov     rax, [rdi+260h]
0x1400f3706  mov     [rax+80h], rsi
0x1400f370d  mov     rcx, [rdi+260h]
0x1400f3714  add     rcx, 58h ; 'X'
0x1400f3718  call    RaidDeleteResourceList
0x1400f371d  mov     rcx, [rdi+260h]
0x1400f3724  add     rcx, 10h
0x1400f3728  call    RaDeleteBus
0x1400f372d  mov     rcx, [rdi+260h]; P
0x1400f3734  mov     edx, ebx; Tag
0x1400f3736  call    cs:__imp_ExFreePoolWithTag
0x1400f373d  nop     dword ptr [rax+rax+00h]
0x1400f3742  mov     [rdi+260h], rsi
0x1400f3749  mov     rbx, [rsp+28h+arg_8]
0x1400f374e  mov     [rdi], esi
0x1400f3750  mov     rsi, [rsp+28h+arg_10]
0x1400f3755  add     rsp, 20h
0x1400f3759  pop     rdi
0x1400f375a  retn
```
