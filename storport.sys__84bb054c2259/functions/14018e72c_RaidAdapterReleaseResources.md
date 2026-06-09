# RaidAdapterReleaseResources

- ea: `0x14018e72c`
- end: `0x14018e9a2`
- name: `RaidAdapterReleaseResources`
- size: `630`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1401c21a0`
- `0x1401c259c`

## callees

- `0x140005c88`
- `0x14000ebfc`
- `0x14001c970`
- `0x140048da8`
- `0x14004a04c`
- `0x140050190`
- `0x14006fb34`
- `0x1400708b8`
- `0x1400716bc`
- `0x140087ac8`
- `0x14009c44c`
- `0x14018e72c`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14018e77f`
- `ntoskrnl!IoFreeWorkItem` at `0x14018e77f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e7ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e7cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e7f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e953`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e968`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e7ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e7cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e7f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e953`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018e968`
- `ntoskrnl!KeDelayExecutionThread` at `0x14018e820`
- `ntoskrnl!KeDelayExecutionThread` at `0x14018e896`
- `ntoskrnl!KeDelayExecutionThread` at `0x14018e820`
- `ntoskrnl!KeDelayExecutionThread` at `0x14018e896`

## pseudocode

```c
void __fastcall RaidAdapterReleaseResources(__int64 a1, __int64 a2)
{
  unsigned int v3; // ecx
  struct _IO_WORKITEM *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  unsigned int v8; // edi
  unsigned int i; // edi
  __int64 v10; // rdx
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF

  v3 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 184) + 1LL);
  Interval.QuadPart = 0;
  if ( *(_QWORD *)(a1 + 360) && (*(_BYTE *)(a1 + 108) & 0x40) != 0 )
    RaidPnPPassToMiniPort(*(_QWORD *)(a1 + 8), v3, 0, 0, 0);
  v4 = *(struct _IO_WORKITEM **)(a1 + 5744);
  if ( v4 )
  {
    IoFreeWorkItem(v4);
    *(_QWORD *)(a1 + 5744) = 0;
  }
  RaAdapterDeregisterFromIdleDetection(a1);
  v5 = *(void **)(a1 + 5432);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0x57506152u);
    *(_QWORD *)(a1 + 5432) = 0;
  }
  v6 = *(void **)(a1 + 5440);
  if ( v6 )
  {
    ExFreePoolWithTag(v6, 0x504F6152u);
    *(_QWORD *)(a1 + 5440) = 0;
  }
  v7 = *(void **)(a1 + 5768);
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0x504E6152u);
    *(_QWORD *)(a1 + 5768) = 0;
  }
  RaidAdapterDeleteAsyncCallbacks(a1);
  Interval.QuadPart = -10000000;
  KeDelayExecutionThread(0, 0, &Interval);
  RaidAdapterStop(a1);
  v8 = 0;
  while ( *(_DWORD *)(a1 + 4952) || *(_DWORD *)(a1 + 4192) )
  {
    if ( v8 < 0x32
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids);
    }
    Interval.QuadPart = -1000000;
    KeDelayExecutionThread(0, 0, &Interval);
    if ( ++v8 >= 0x258 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids);
      }
      break;
    }
  }
  for ( i = 0; i < *(_DWORD *)(a1 + 1032); ++i )
    RaFreeRaidResources(*(_QWORD *)(a1 + 1024) + 320LL * i, *(_QWORD *)(a1 + 8), *(_BYTE *)(a1 + 4434));
  *(_DWORD *)(a1 + 1032) = 0;
  StorFreeGatewayLockHandleArray(a1);
  StorDeleteIoGateway(a1);
  RaidFreeMappingList(a1 + 960);
  if ( *(_QWORD *)(a1 + 6112) )
  {
    StorpShutdownRegistryWatch();
    ExFreePoolWithTag(**(PVOID **)(a1 + 6112), 0x57526152u);
    ExFreePoolWithTag(*(PVOID *)(a1 + 6112), 0x57526152u);
    *(_QWORD *)(a1 + 6112) = 0;
  }
  v10 = *(_QWORD *)(a1 + 120);
  if ( v10 )
  {
    StorFreeContiguousIoResources(a1, v10);
    *(_DWORD *)(a1 + 128) &= ~2u;
    *(_QWORD *)(a1 + 120) = 0;
  }
}

```

## disassembly

```asm
0x14018e72c  push    rbx
0x14018e72e  push    rsi
0x14018e72f  push    rdi
0x14018e730  push    r14
0x14018e732  sub     rsp, 38h
0x14018e736  mov     rax, [rdx+0B8h]
0x14018e73d  mov     rbx, rcx
0x14018e740  xor     esi, esi
0x14018e742  movzx   ecx, byte ptr [rax+1]
0x14018e746  mov     qword ptr [rsp+58h+Interval], rsi
0x14018e74b  cmp     [rbx+168h], rsi
0x14018e752  jz      short loc_14018E773
0x14018e754  test    byte ptr [rbx+6Ch], 40h
0x14018e758  jz      short loc_14018E773
0x14018e75a  mov     edx, ecx
0x14018e75c  mov     [rsp+58h+var_30], esi
0x14018e760  mov     rcx, [rbx+8]
0x14018e764  xor     r9d, r9d
0x14018e767  xor     r8d, r8d
0x14018e76a  mov     [rsp+58h+var_38], esi
0x14018e76e  call    RaidPnPPassToMiniPort
0x14018e773  mov     rcx, [rbx+1670h]; IoWorkItem
0x14018e77a  test    rcx, rcx
0x14018e77d  jz      short loc_14018E792
0x14018e77f  call    cs:__imp_IoFreeWorkItem
0x14018e786  nop     dword ptr [rax+rax+00h]
0x14018e78b  mov     [rbx+1670h], rsi
0x14018e792  mov     rcx, rbx
0x14018e795  call    RaAdapterDeregisterFromIdleDetection
0x14018e79a  mov     rcx, [rbx+1538h]; P
0x14018e7a1  test    rcx, rcx
0x14018e7a4  jz      short loc_14018E7BE
0x14018e7a6  mov     edx, 57506152h; Tag
0x14018e7ab  call    cs:__imp_ExFreePoolWithTag
0x14018e7b2  nop     dword ptr [rax+rax+00h]
0x14018e7b7  mov     [rbx+1538h], rsi
0x14018e7be  mov     rcx, [rbx+1540h]; P
0x14018e7c5  test    rcx, rcx
0x14018e7c8  jz      short loc_14018E7E2
0x14018e7ca  mov     edx, 504F6152h; Tag
0x14018e7cf  call    cs:__imp_ExFreePoolWithTag
0x14018e7d6  nop     dword ptr [rax+rax+00h]
0x14018e7db  mov     [rbx+1540h], rsi
0x14018e7e2  mov     rcx, [rbx+1688h]; P
0x14018e7e9  test    rcx, rcx
0x14018e7ec  jz      short loc_14018E806
0x14018e7ee  mov     edx, 504E6152h; Tag
0x14018e7f3  call    cs:__imp_ExFreePoolWithTag
0x14018e7fa  nop     dword ptr [rax+rax+00h]
0x14018e7ff  mov     [rbx+1688h], rsi
0x14018e806  mov     rcx, rbx
0x14018e809  call    RaidAdapterDeleteAsyncCallbacks
0x14018e80e  lea     r8, [rsp+58h+Interval]; Interval
0x14018e813  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFF676980h
0x14018e81c  xor     edx, edx; Alertable
0x14018e81e  xor     ecx, ecx; WaitMode
0x14018e820  call    cs:__imp_KeDelayExecutionThread
0x14018e827  nop     dword ptr [rax+rax+00h]
0x14018e82c  mov     rcx, rbx
0x14018e82f  call    RaidAdapterStop
0x14018e834  mov     edi, esi
0x14018e836  lea     r14, WPP_GLOBAL_Control
0x14018e83d  cmp     [rbx+1358h], esi
0x14018e843  ja      short loc_14018E851
0x14018e845  cmp     [rbx+1060h], esi
0x14018e84b  jbe     loc_14018E8DA
0x14018e851  cmp     edi, 32h ; '2'
0x14018e854  jnb     short loc_14018E884
0x14018e856  mov     rcx, cs:WPP_GLOBAL_Control
0x14018e85d  cmp     rcx, r14
0x14018e860  jz      short loc_14018E884
0x14018e862  mov     eax, [rcx+2Ch]
0x14018e865  test    al, 2
0x14018e867  jz      short loc_14018E884
0x14018e869  cmp     byte ptr [rcx+29h], 4
0x14018e86d  jb      short loc_14018E884
0x14018e86f  mov     rcx, [rcx+18h]
0x14018e873  lea     r8, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids
0x14018e87a  mov     edx, 1Ah
0x14018e87f  call    WPP_SF_
0x14018e884  lea     r8, [rsp+58h+Interval]; Interval
0x14018e889  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFF0BDC0h
0x14018e892  xor     edx, edx; Alertable
0x14018e894  xor     ecx, ecx; WaitMode
0x14018e896  call    cs:__imp_KeDelayExecutionThread
0x14018e89d  nop     dword ptr [rax+rax+00h]
0x14018e8a2  inc     edi
0x14018e8a4  cmp     edi, 258h
0x14018e8aa  jb      short loc_14018E83D
0x14018e8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14018e8b3  cmp     rcx, r14
0x14018e8b6  jz      short loc_14018E8DA
0x14018e8b8  mov     eax, [rcx+2Ch]
0x14018e8bb  test    al, 2
0x14018e8bd  jz      short loc_14018E8DA
0x14018e8bf  cmp     byte ptr [rcx+29h], 2
0x14018e8c3  jb      short loc_14018E8DA
0x14018e8c5  mov     rcx, [rcx+18h]
0x14018e8c9  lea     r8, WPP_17a2ccf459a039b6fd190e52d544bf1c_Traceguids
0x14018e8d0  mov     edx, 1Bh
0x14018e8d5  call    WPP_SF_
0x14018e8da  mov     edi, esi
0x14018e8dc  cmp     [rbx+408h], esi
0x14018e8e2  jbe     short loc_14018E90F
0x14018e8e4  mov     r8b, [rbx+1152h]
0x14018e8eb  mov     rdx, [rbx+8]
0x14018e8ef  mov     eax, edi
0x14018e8f1  lea     rcx, [rax+rax*4]
0x14018e8f5  shl     rcx, 6
0x14018e8f9  add     rcx, [rbx+400h]
0x14018e900  call    RaFreeRaidResources
0x14018e905  inc     edi
0x14018e907  cmp     edi, [rbx+408h]
0x14018e90d  jb      short loc_14018E8E4
0x14018e90f  mov     rcx, rbx
0x14018e912  mov     [rbx+408h], esi
0x14018e918  call    StorFreeGatewayLockHandleArray
0x14018e91d  mov     rcx, rbx
0x14018e920  call    StorDeleteIoGateway
0x14018e925  lea     rcx, [rbx+3C0h]
0x14018e92c  call    RaidFreeMappingList
0x14018e931  mov     rcx, [rbx+17E0h]
0x14018e938  test    rcx, rcx
0x14018e93b  jz      short loc_14018E97B
0x14018e93d  call    StorpShutdownRegistryWatch
0x14018e942  mov     rcx, [rbx+17E0h]
0x14018e949  mov     edi, 57526152h
0x14018e94e  mov     edx, edi; Tag
0x14018e950  mov     rcx, [rcx]; P
0x14018e953  call    cs:__imp_ExFreePoolWithTag
0x14018e95a  nop     dword ptr [rax+rax+00h]
0x14018e95f  mov     rcx, [rbx+17E0h]; P
0x14018e966  mov     edx, edi; Tag
0x14018e968  call    cs:__imp_ExFreePoolWithTag
0x14018e96f  nop     dword ptr [rax+rax+00h]
0x14018e974  mov     [rbx+17E0h], rsi
0x14018e97b  mov     rdx, [rbx+78h]
0x14018e97f  test    rdx, rdx
0x14018e982  jz      short loc_14018E997
0x14018e984  mov     rcx, rbx
0x14018e987  call    StorFreeContiguousIoResources
0x14018e98c  and     dword ptr [rbx+80h], 0FFFFFFFDh
0x14018e993  mov     [rbx+78h], rsi
0x14018e997  add     rsp, 38h
0x14018e99b  pop     r14
0x14018e99d  pop     rdi
0x14018e99e  pop     rsi
0x14018e99f  pop     rbx
0x14018e9a0  retn
```
