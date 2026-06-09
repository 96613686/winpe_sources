# SrvNetUpdateNetNameWorkerRoutine

- ea: `0x140005ba0`
- end: `0x140005e07`
- name: `SrvNetUpdateNetNameWorkerRoutine`
- size: `615`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x140005ba0`
- `0x140007360`
- `0x14001389c`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x14004fbf0`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x140005ddb`
- `ntoskrnl!KeStackAttachProcess` at `0x140005ddb`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140005df6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140005df6`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140005d7d`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140005d7d`
- `ntoskrnl!IoUninitializeWorkItem` at `0x140005ceb`
- `ntoskrnl!IoUninitializeWorkItem` at `0x140005ceb`
- `ntoskrnl!IoGetCurrentProcess` at `0x140005bf4`
- `ntoskrnl!IoGetCurrentProcess` at `0x140005bf4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005c8b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005c8b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005c48`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005c48`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005c09`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005c09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005cb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005cb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d10`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005c7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005c7f`

## pseudocode

```c
void __fastcall SrvNetUpdateNetNameWorkerRoutine(PVOID IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  int v4; // ebp
  struct _KPROCESS *v5; // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 i; // rbx
  __int64 v9; // rcx
  void (__fastcall *v10)(__int64, _QWORD); // rax
  unsigned int v11; // [rsp+20h] [rbp-68h] BYREF
  __int64 v12; // [rsp+28h] [rbp-60h] BYREF
  _KAPC_STATE ApcState; // [rsp+30h] [rbp-58h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  v4 = 0;
  v12 = 0;
  v11 = 0;
  v5 = *(struct _KPROCESS **)&SrvNetDeviceExtension[4].ActiveCount;
  if ( IoGetCurrentProcess() != v5 )
  {
    KeStackAttachProcess(v5, &ApcState);
    v4 = 1;
  }
  KeEnterCriticalRegion();
  _InterlockedExchange(&SrvNetNetNameUpdateWorkerState, 2);
  v6 = SrvNetBuildNetname(&v12, &v11);
  v7 = v12;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids,
        (unsigned int)v6);
    }
  }
  else
  {
    ExAcquireResourceExclusiveLite(SrvNetDeviceExtension, 1u);
    for ( i = 0; i != 7; ++i )
    {
      v9 = *(&SrvNetDeviceExtension[4].OwnerEntry.OwnerThread + i);
      if ( v9 )
      {
        v10 = *(void (__fastcall **)(__int64, _QWORD))(v9 + 216);
        if ( v10 )
        {
          if ( !*(_DWORD *)(v9 + 132) )
            v10(v7, v11);
        }
      }
    }
    ExReleaseResourceLite(SrvNetDeviceExtension);
  }
  KeLeaveCriticalRegion();
  if ( v4 )
    KeUnstackDetachProcess(&ApcState);
  if ( v7 )
  {
    SrvNetUpdateMemStatistics(*(_DWORD *)(v7 - 12), *(_DWORD *)(v7 - 16), 0);
    ExFreePoolWithTag((PVOID)(v7 - 16), 0);
  }
  _m_prefetchw(&SrvNetNetNameUpdateWorkerState);
  if ( (_InterlockedAnd(&SrvNetNetNameUpdateWorkerState, 0xFFFFFFFD) & 1) != 0 )
  {
    IoQueueWorkItemEx(IoWorkItem, SrvNetUpdateNetNameWorkerRoutine, DelayedWorkQueue, 0);
  }
  else
  {
    IoUninitializeWorkItem(IoWorkItem);
    if ( IoWorkItem )
    {
      SrvNetUpdateMemStatistics(*((_DWORD *)IoWorkItem - 3), *((_DWORD *)IoWorkItem - 4), 0);
      ExFreePoolWithTag((char *)IoWorkItem - 16, 0);
    }
  }
}

```

## disassembly

```asm
0x140005ba0  mov     [rsp+arg_0], rbx
0x140005ba5  mov     [rsp+arg_8], rbp
0x140005baa  push    rsi
0x140005bab  push    rdi
0x140005bac  push    r14
0x140005bae  sub     rsp, 70h
0x140005bb2  mov     rax, cs:__security_cookie
0x140005bb9  xor     rax, rsp
0x140005bbc  mov     [rsp+88h+var_28], rax
0x140005bc1  mov     rax, cs:SrvNetDeviceExtension
0x140005bc8  xorps   xmm0, xmm0
0x140005bcb  xor     r14d, r14d
0x140005bce  mov     rsi, r8
0x140005bd1  movups  xmmword ptr [rsp+88h+ApcState.ApcListHead.Flink], xmm0
0x140005bd6  mov     ebp, r14d
0x140005bd9  mov     [rsp+88h+var_60], r14
0x140005bde  movups  xmmword ptr [rsp+88h+ApcState.ApcListHead.Flink+10h], xmm0
0x140005be3  mov     [rsp+88h+var_68], r14d
0x140005be8  movups  xmmword ptr [rsp+88h+ApcState.Process], xmm0
0x140005bed  mov     rbx, [rax+1B8h]
0x140005bf4  call    cs:__imp_IoGetCurrentProcess
0x140005bfb  nop     dword ptr [rax+rax+00h]
0x140005c00  cmp     rax, rbx
0x140005c03  jnz     loc_140005DD3
0x140005c09  call    cs:__imp_KeEnterCriticalRegion
0x140005c10  nop     dword ptr [rax+rax+00h]
0x140005c15  mov     eax, 2
0x140005c1a  lea     rdx, [rsp+88h+var_68]
0x140005c1f  xchg    eax, cs:SrvNetNetNameUpdateWorkerState
0x140005c25  lea     rcx, [rsp+88h+var_60]
0x140005c2a  call    SrvNetBuildNetname
0x140005c2f  mov     rdi, [rsp+88h+var_60]
0x140005c34  mov     r9d, eax
0x140005c37  test    eax, eax
0x140005c39  js      loc_140005D8B
0x140005c3f  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x140005c46  mov     dl, 1; Wait
0x140005c48  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140005c4f  nop     dword ptr [rax+rax+00h]
0x140005c54  mov     rbx, r14
0x140005c57  mov     rax, cs:SrvNetDeviceExtension
0x140005c5e  mov     rcx, [rax+rbx*8+1D0h]
0x140005c66  test    rcx, rcx
0x140005c69  jnz     loc_140005D3F
0x140005c6f  inc     rbx
0x140005c72  cmp     rbx, 7
0x140005c76  jnz     short loc_140005C57
0x140005c78  mov     rcx, cs:SrvNetDeviceExtension; Resource
0x140005c7f  call    cs:__imp_ExReleaseResourceLite
0x140005c86  nop     dword ptr [rax+rax+00h]
0x140005c8b  call    cs:__imp_KeLeaveCriticalRegion
0x140005c92  nop     dword ptr [rax+rax+00h]
0x140005c97  test    ebp, ebp
0x140005c99  jnz     loc_140005DF1
0x140005c9f  test    rdi, rdi
0x140005ca2  jz      short loc_140005CC4
0x140005ca4  mov     ecx, [rdi-0Ch]
0x140005ca7  xor     r8d, r8d
0x140005caa  mov     edx, [rdi-10h]
0x140005cad  call    SrvNetUpdateMemStatistics
0x140005cb2  xor     edx, edx; Tag
0x140005cb4  lea     rcx, [rdi-10h]; P
0x140005cb8  call    cs:__imp_ExFreePoolWithTag
0x140005cbf  nop     dword ptr [rax+rax+00h]
0x140005cc4  prefetchw byte ptr cs:SrvNetNetNameUpdateWorkerState
0x140005ccb  mov     eax, cs:SrvNetNetNameUpdateWorkerState
0x140005cd1  mov     edx, eax
0x140005cd3  and     edx, 0FFFFFFFDh
0x140005cd6  lock cmpxchg cs:SrvNetNetNameUpdateWorkerState, edx
0x140005cde  jnz     short loc_140005CD1
0x140005ce0  mov     rcx, rsi; IoWorkItem
0x140005ce3  test    al, 1
0x140005ce5  jnz     loc_140005D6D
0x140005ceb  call    cs:__imp_IoUninitializeWorkItem
0x140005cf2  nop     dword ptr [rax+rax+00h]
0x140005cf7  test    rsi, rsi
0x140005cfa  jz      short loc_140005D1C
0x140005cfc  mov     ecx, [rsi-0Ch]
0x140005cff  xor     r8d, r8d
0x140005d02  mov     edx, [rsi-10h]
0x140005d05  call    SrvNetUpdateMemStatistics
0x140005d0a  xor     edx, edx; Tag
0x140005d0c  lea     rcx, [rsi-10h]; P
0x140005d10  call    cs:__imp_ExFreePoolWithTag
0x140005d17  nop     dword ptr [rax+rax+00h]
0x140005d1c  mov     rcx, [rsp+88h+var_28]
0x140005d21  xor     rcx, rsp; StackCookie
0x140005d24  call    __security_check_cookie
0x140005d29  lea     r11, [rsp+88h+var_18]
0x140005d2e  mov     rbx, [r11+20h]
0x140005d32  mov     rbp, [r11+28h]
0x140005d36  mov     rsp, r11
0x140005d39  pop     r14
0x140005d3b  pop     rdi
0x140005d3c  pop     rsi
0x140005d3d  retn
0x140005d3f  mov     rax, [rcx+0D8h]
0x140005d46  test    rax, rax
0x140005d49  jz      loc_140005C6F
0x140005d4f  cmp     [rcx+84h], r14d
0x140005d56  jnz     loc_140005C6F
0x140005d5c  mov     edx, [rsp+88h+var_68]
0x140005d60  mov     rcx, rdi
0x140005d63  call    _guard_dispatch_icall
0x140005d68  jmp     loc_140005C6F
0x140005d6d  xor     r9d, r9d; Context
0x140005d70  lea     rdx, SrvNetUpdateNetNameWorkerRoutine; WorkerRoutine
0x140005d77  mov     r8d, 1; QueueType
0x140005d7d  call    cs:__imp_IoQueueWorkItemEx
0x140005d84  nop     dword ptr [rax+rax+00h]
0x140005d89  jmp     short loc_140005D1C
0x140005d8b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140005d92  lea     rax, WPP_GLOBAL_Control
0x140005d99  cmp     rcx, rax
0x140005d9c  jz      loc_140005C8B
0x140005da2  test    dword ptr [rcx+2Ch], 2000h
0x140005da9  jz      loc_140005C8B
0x140005daf  cmp     byte ptr [rcx+29h], 1
0x140005db3  jb      loc_140005C8B
0x140005db9  mov     rcx, [rcx+18h]
0x140005dbd  lea     r8, WPP_9738bdc07af3325d0d1e94f94c376033_Traceguids
0x140005dc4  mov     edx, 23h ; '#'
0x140005dc9  call    WPP_SF_d
0x140005dce  jmp     loc_140005C8B
0x140005dd3  lea     rdx, [rsp+88h+ApcState]; ApcState
0x140005dd8  mov     rcx, rbx; PROCESS
0x140005ddb  call    cs:__imp_KeStackAttachProcess
0x140005de2  nop     dword ptr [rax+rax+00h]
0x140005de7  mov     ebp, 1
0x140005dec  jmp     loc_140005C09
0x140005df1  lea     rcx, [rsp+88h+ApcState]; ApcState
0x140005df6  call    cs:__imp_KeUnstackDetachProcess
0x140005dfd  nop     dword ptr [rax+rax+00h]
0x140005e02  jmp     loc_140005C9F
```
