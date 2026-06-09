# KmclInitializeChannel

- ea: `0x140007068`
- end: `0x1400073b6`
- name: `KmclInitializeChannel`
- size: `846`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2, PVOID Object)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400073d0`
- `0x14001c270`

## callees

- `0x1400069c0`
- `0x140007068`
- `0x1400100c0`
- `0x1400109ac`
- `0x140011e90`
- `0x140012280`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140007353`
- `ntoskrnl!ExReleaseFastMutex` at `0x140007353`
- `ntoskrnl!ObfReferenceObject` at `0x1400071f0`
- `ntoskrnl!ObfReferenceObject` at `0x1400071f0`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400072f4`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400072f4`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000730e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000730e`
- `ntoskrnl!KeInitializeEvent` at `0x1400070b4`
- `ntoskrnl!KeInitializeEvent` at `0x1400070ed`
- `ntoskrnl!KeInitializeEvent` at `0x1400070b4`
- `ntoskrnl!KeInitializeEvent` at `0x1400070ed`
- `ntoskrnl!IoAllocateWorkItem` at `0x140007203`
- `ntoskrnl!IoAllocateWorkItem` at `0x140007226`
- `ntoskrnl!IoAllocateWorkItem` at `0x140007290`
- `ntoskrnl!IoAllocateWorkItem` at `0x140007203`
- `ntoskrnl!IoAllocateWorkItem` at `0x140007226`
- `ntoskrnl!IoAllocateWorkItem` at `0x140007290`

## pseudocode

```c
__int64 __fastcall KmclInitializeChannel(_QWORD *BugCheckParameter2, PVOID Object, char a3)
{
  __int64 v6; // rdx
  PIO_WORKITEM WorkItem; // rax
  PIO_WORKITEM v8; // rax
  char v9; // al
  PIO_WORKITEM v10; // rax
  _QWORD *v11; // rcx
  unsigned int v12; // edi
  __int128 v14; // [rsp+40h] [rbp-28h] BYREF

  memset(BugCheckParameter2, 0, 0xE80u);
  *((_DWORD *)BugCheckParameter2 + 572) = 1;
  KeInitializeEvent((PRKEVENT)(BugCheckParameter2 + 289), SynchronizationEvent, 0);
  *((_DWORD *)BugCheckParameter2 + 794) = 1;
  BugCheckParameter2[398] = 0;
  *((_DWORD *)BugCheckParameter2 + 798) = 0;
  KeInitializeEvent((PRKEVENT)(BugCheckParameter2 + 400), SynchronizationEvent, 0);
  LOBYTE(v6) = 30;
  BugCheckParameter2[407] = BugCheckParameter2 + 406;
  BugCheckParameter2[406] = BugCheckParameter2 + 406;
  BugCheckParameter2[405] = BugCheckParameter2 + 404;
  BugCheckParameter2[404] = BugCheckParameter2 + 404;
  BugCheckParameter2[364] = BugCheckParameter2 + 363;
  BugCheckParameter2[363] = BugCheckParameter2 + 363;
  BugCheckParameter2[366] = BugCheckParameter2 + 365;
  BugCheckParameter2[365] = BugCheckParameter2 + 365;
  *BugCheckParameter2 = BugCheckParameter2;
  *((_BYTE *)BugCheckParameter2 + 1200) = 1;
  *((_DWORD *)BugCheckParameter2 + 349) = a3 != 0 ? 256 : -1;
  VmbChannelSetAllowableDpcCpuUsage(BugCheckParameter2, v6);
  *((_BYTE *)BugCheckParameter2 + 1728) = a3;
  if ( !a3 )
    *((_BYTE *)BugCheckParameter2 + 2344) |= 1u;
  *((_BYTE *)BugCheckParameter2 + 2024) = 0;
  BugCheckParameter2[255] = KmclpDefaultChannelOpenedEx;
  *((_DWORD *)BugCheckParameter2 + 492) = -1;
  BugCheckParameter2[256] = KmclpDefaultChannelClosed;
  BugCheckParameter2[257] = KmclpDefaultChannelClosed;
  BugCheckParameter2[258] = KmclpDefaultChannelClosed;
  BugCheckParameter2[259] = KmclpDefaultChannelClosed;
  BugCheckParameter2[267] = KmclpDefaultChannelClosed;
  *((_DWORD *)BugCheckParameter2 + 411) = 1852402518;
  *((_DWORD *)BugCheckParameter2 + 268) = 1970236246;
  BugCheckParameter2[408] = Object;
  ObfReferenceObject(Object);
  WorkItem = IoAllocateWorkItem((PDEVICE_OBJECT)BugCheckParameter2[408]);
  BugCheckParameter2[278] = WorkItem;
  if ( !WorkItem )
    goto LABEL_14;
  v8 = IoAllocateWorkItem((PDEVICE_OBJECT)BugCheckParameter2[408]);
  BugCheckParameter2[349] = v8;
  if ( !v8 )
    goto LABEL_14;
  if ( !a3 )
  {
    v14 = 0;
    HviGetHypervisorFeatures(&v14);
    if ( (v14 & 0x40000000000000LL) != 0 )
    {
      *((_WORD *)BugCheckParameter2 + 1448) = 257;
      goto LABEL_9;
    }
    v9 = KmclForceNonIsolatedBounceBuffering;
    *((_BYTE *)BugCheckParameter2 + 2897) = KmclForceNonIsolatedBounceBuffering;
    if ( v9 )
    {
LABEL_9:
      v10 = IoAllocateWorkItem((PDEVICE_OBJECT)BugCheckParameter2[408]);
      BugCheckParameter2[367] = v10;
      if ( v10 )
      {
        *((_DWORD *)BugCheckParameter2 + 493) = 0;
        *((_DWORD *)BugCheckParameter2 + 494) = 0x80000;
        *((_DWORD *)BugCheckParameter2 + 495) = 0x2000000;
        ExInitializeNPagedLookasideList(
          (PNPAGED_LOOKASIDE_LIST)BugCheckParameter2 + 23,
          0,
          0,
          0x200u,
          0x20u,
          0x636D6B56u,
          0);
        *((_BYTE *)BugCheckParameter2 + 3072) = 1;
        goto LABEL_11;
      }
LABEL_14:
      v12 = -1073741670;
      VmbChannelCleanup((ULONG_PTR)BugCheckParameter2);
      return v12;
    }
  }
LABEL_11:
  ExAcquireFastMutex(&KmclChannelListLock);
  v11 = (_QWORD *)qword_1400162A8;
  if ( *(__int64 **)qword_1400162A8 != &KmclChannelList )
    __fastfail(3u);
  BugCheckParameter2[269] = qword_1400162A8;
  BugCheckParameter2[268] = &KmclChannelList;
  *v11 = BugCheckParameter2 + 268;
  qword_1400162A8 = (__int64)(BugCheckParameter2 + 268);
  ExReleaseFastMutex(&KmclChannelListLock);
  v12 = 0;
  BugCheckParameter2[76] = KmclPerformanceCounterFrequency;
  BugCheckParameter2[74] = -1;
  BugCheckParameter2[73] = 0;
  return v12;
}

```

## disassembly

```asm
0x140007068  mov     [rsp+arg_8], rbx
0x14000706d  mov     [rsp+arg_10], rsi
0x140007072  push    rdi
0x140007073  sub     rsp, 60h
0x140007077  mov     rax, cs:__security_cookie
0x14000707e  xor     rax, rsp
0x140007081  mov     [rsp+68h+var_18], rax
0x140007086  mov     dil, r8b
0x140007089  mov     rsi, rdx
0x14000708c  xor     edx, edx; Val
0x14000708e  mov     r8d, 0E80h; Size
0x140007094  mov     rbx, rcx
0x140007097  call    memset
0x14000709c  xor     r8d, r8d; State
0x14000709f  mov     dword ptr [rbx+8F0h], 1
0x1400070a9  lea     rcx, [rbx+908h]; Event
0x1400070b0  lea     edx, [r8+1]; Type
0x1400070b4  call    cs:__imp_KeInitializeEvent
0x1400070bb  nop     dword ptr [rax+rax+00h]
0x1400070c0  xor     r8d, r8d; State
0x1400070c3  mov     dword ptr [rbx+0C68h], 1
0x1400070cd  lea     rcx, [rbx+0C80h]; Event
0x1400070d4  mov     qword ptr [rbx+0C70h], 0
0x1400070df  mov     dword ptr [rbx+0C78h], 0
0x1400070e9  lea     edx, [r8+1]; Type
0x1400070ed  call    cs:__imp_KeInitializeEvent
0x1400070f4  nop     dword ptr [rax+rax+00h]
0x1400070f9  lea     rax, [rbx+0CB0h]
0x140007100  mov     dl, 1Eh
0x140007102  mov     [rax+8], rax
0x140007106  mov     [rax], rax
0x140007109  lea     rax, [rbx+0CA0h]
0x140007110  mov     [rax+8], rax
0x140007114  mov     [rax], rax
0x140007117  lea     rax, [rbx+0B58h]
0x14000711e  mov     [rax+8], rax
0x140007122  mov     [rax], rax
0x140007125  lea     rax, [rbx+0B68h]
0x14000712c  mov     [rax+8], rax
0x140007130  mov     [rax], rax
0x140007133  mov     al, dil
0x140007136  neg     al
0x140007138  mov     [rbx], rbx
0x14000713b  mov     byte ptr [rbx+4B0h], 1
0x140007142  sbb     ecx, ecx
0x140007144  and     ecx, 101h
0x14000714a  dec     ecx
0x14000714c  mov     [rbx+574h], ecx
0x140007152  mov     rcx, rbx
0x140007155  call    VmbChannelSetAllowableDpcCpuUsage
0x14000715a  mov     [rbx+6C0h], dil
0x140007161  test    dil, dil
0x140007164  jnz     short loc_14000716D
0x140007166  or      byte ptr [rbx+928h], 1
0x14000716d  lea     rax, KmclpDefaultChannelOpenedEx
0x140007174  mov     byte ptr [rbx+7E8h], 0
0x14000717b  mov     [rbx+7F8h], rax
0x140007182  mov     rcx, rsi; Object
0x140007185  lea     rax, KmclpDefaultChannelClosed
0x14000718c  mov     dword ptr [rbx+7B0h], 0FFFFFFFFh
0x140007196  mov     [rbx+800h], rax
0x14000719d  lea     rax, KmclpDefaultChannelClosed
0x1400071a4  mov     [rbx+808h], rax
0x1400071ab  lea     rax, KmclpDefaultChannelClosed
0x1400071b2  mov     [rbx+810h], rax
0x1400071b9  lea     rax, KmclpDefaultChannelClosed
0x1400071c0  mov     [rbx+818h], rax
0x1400071c7  lea     rax, KmclpDefaultChannelClosed
0x1400071ce  mov     [rbx+858h], rax
0x1400071d5  mov     dword ptr [rbx+66Ch], 6E696B56h
0x1400071df  mov     dword ptr [rbx+430h], 756F6B56h
0x1400071e9  mov     [rbx+0CC0h], rsi
0x1400071f0  call    cs:__imp_ObfReferenceObject
0x1400071f7  nop     dword ptr [rax+rax+00h]
0x1400071fc  mov     rcx, [rbx+0CC0h]; DeviceObject
0x140007203  call    cs:__imp_IoAllocateWorkItem
0x14000720a  nop     dword ptr [rax+rax+00h]
0x14000720f  mov     [rbx+8B0h], rax
0x140007216  test    rax, rax
0x140007219  jz      loc_140007387
0x14000721f  mov     rcx, [rbx+0CC0h]; DeviceObject
0x140007226  call    cs:__imp_IoAllocateWorkItem
0x14000722d  nop     dword ptr [rax+rax+00h]
0x140007232  mov     [rbx+0AE8h], rax
0x140007239  test    rax, rax
0x14000723c  jz      loc_140007387
0x140007242  test    dil, dil
0x140007245  jnz     loc_140007307
0x14000724b  xorps   xmm0, xmm0
0x14000724e  lea     rcx, [rsp+68h+var_28]
0x140007253  movups  [rsp+68h+var_28], xmm0
0x140007258  call    HviGetHypervisorFeatures
0x14000725d  mov     rax, 40000000000000h
0x140007267  test    qword ptr [rsp+68h+var_28], rax
0x14000726c  jz      short loc_140007279
0x14000726e  mov     word ptr [rbx+0B50h], 101h
0x140007277  jmp     short loc_140007289
0x140007279  mov     al, cs:KmclForceNonIsolatedBounceBuffering
0x14000727f  mov     [rbx+0B51h], al
0x140007285  test    al, al
0x140007287  jz      short loc_140007307
0x140007289  mov     rcx, [rbx+0CC0h]; DeviceObject
0x140007290  call    cs:__imp_IoAllocateWorkItem
0x140007297  nop     dword ptr [rax+rax+00h]
0x14000729c  mov     [rbx+0B78h], rax
0x1400072a3  test    rax, rax
0x1400072a6  jz      loc_140007387
0x1400072ac  xor     eax, eax
0x1400072ae  mov     dword ptr [rbx+7B4h], 0
0x1400072b8  mov     [rsp+68h+Depth], ax; Depth
0x1400072bd  lea     rcx, [rbx+0B80h]; Lookaside
0x1400072c4  mov     [rsp+68h+Tag], 636D6B56h; Tag
0x1400072cc  mov     r9d, 200h; Flags
0x1400072d2  xor     r8d, r8d; Free
0x1400072d5  mov     [rsp+68h+Size], 20h ; ' '; Size
0x1400072de  xor     edx, edx; Allocate
0x1400072e0  mov     dword ptr [rbx+7B8h], 80000h
0x1400072ea  mov     dword ptr [rbx+7BCh], 2000000h
0x1400072f4  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400072fb  nop     dword ptr [rax+rax+00h]
0x140007300  mov     byte ptr [rbx+0C00h], 1
0x140007307  lea     rcx, KmclChannelListLock; FastMutex
0x14000730e  call    cs:__imp_ExAcquireFastMutex
0x140007315  nop     dword ptr [rax+rax+00h]
0x14000731a  mov     rcx, cs:qword_1400162A8
0x140007321  lea     rdx, KmclChannelList
0x140007328  cmp     [rcx], rdx
0x14000732b  jz      short loc_140007334
0x14000732d  mov     ecx, 3
0x140007332  int     29h; Win8: RtlFailFast(ecx)
0x140007334  lea     rax, [rbx+860h]
0x14000733b  mov     [rax+8], rcx
0x14000733f  mov     [rax], rdx
0x140007342  mov     [rcx], rax
0x140007345  lea     rcx, KmclChannelListLock; FastMutex
0x14000734c  mov     cs:qword_1400162A8, rax
0x140007353  call    cs:__imp_ExReleaseFastMutex
0x14000735a  nop     dword ptr [rax+rax+00h]
0x14000735f  mov     rax, cs:KmclPerformanceCounterFrequency
0x140007366  xor     edi, edi
0x140007368  mov     [rbx+260h], rax
0x14000736f  mov     qword ptr [rbx+250h], 0FFFFFFFFFFFFFFFFh
0x14000737a  mov     qword ptr [rbx+248h], 0
0x140007385  jmp     short loc_140007394
0x140007387  mov     edi, 0C000009Ah
0x14000738c  mov     rcx, rbx; BugCheckParameter2
0x14000738f  call    VmbChannelCleanup
0x140007394  mov     eax, edi
0x140007396  mov     rcx, [rsp+68h+var_18]
0x14000739b  xor     rcx, rsp; StackCookie
0x14000739e  call    __security_check_cookie
0x1400073a3  lea     r11, [rsp+68h+var_8]
0x1400073a8  mov     rbx, [r11+18h]
0x1400073ac  mov     rsi, [r11+20h]
0x1400073b0  mov     rsp, r11
0x1400073b3  pop     rdi
0x1400073b4  retn
```
