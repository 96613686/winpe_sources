# UdfRmwBgFormatWorker

- ea: `0x14002c330`
- end: `0x14002c76b`
- name: `UdfRmwBgFormatWorker`
- size: `1083`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x140007aec`
- `0x14000a2e8`
- `0x14000cad4`
- `0x14000cbcc`
- `0x14001093c`
- `0x14001c080`
- `0x14002c330`
- `0x14002c7a0`
- `0x14003cf04`
- `0x140044860`
- `0x140058114`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14002c6f3`
- `ntoskrnl!ExRaiseStatus` at `0x14002c6f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c5af`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c68b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c5af`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c68b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002c56e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002c62d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002c677`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002c56e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002c62d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002c677`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002c463`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002c463`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002c4fa`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002c4fa`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c522`
- `ntoskrnl!ObfDereferenceObject` at `0x14002c522`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14002c513`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x14002c513`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c3b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002c3b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c70b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c70b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c40b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c40b`
- `ntoskrnl!ObfReferenceObject` at `0x14002c4a8`
- `ntoskrnl!ObfReferenceObject` at `0x14002c4a8`
- `ntoskrnl!KeReadStateEvent` at `0x14002c5d1`
- `ntoskrnl!KeReadStateEvent` at `0x14002c5d1`

## pseudocode

```c
void __fastcall UdfRmwBgFormatWorker(char *StartContext)
{
  __int64 v2; // r14
  int v3; // esi
  char v4; // r13
  void *v5; // rax
  NTSTATUS v6; // edi
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax
  struct _FILE_OBJECT *v10; // rdi
  __int64 v11; // rcx
  int v12; // r8d
  int *v13; // r15
  int v14; // edx
  __int64 v15; // rcx
  __int128 v16; // [rsp+30h] [rbp-69h] BYREF
  __int64 v17; // [rsp+40h] [rbp-59h]
  _QWORD Entry[20]; // [rsp+50h] [rbp-49h] BYREF
  int v19; // [rsp+100h] [rbp+67h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+108h] [rbp+6Fh] BYREF

  memset(Entry, 0, 0x68u);
  v2 = *((_QWORD *)StartContext + 13);
  v3 = -1;
  v17 = 0;
  Timeout.QuadPart = 0;
  v16 = 0;
  v4 = 0;
  v19 = -1;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 55, WPP_e04914546632397e8b30a0a107c62418_Traceguids);
  }
  Timeout.QuadPart = -600000000;
  KeEnterCriticalRegion();
  memset(Entry, 0, 0x68u);
  LODWORD(Entry[0]) = 6818103;
  Entry[2] = StartContext;
  HIDWORD(Entry[3]) = 4101;
  UdfSetThreadContext(Entry, &v16);
LABEL_5:
  v5 = (void *)(v2 + 232);
  while ( 1 )
  {
    v6 = KeWaitForSingleObject(v5, Executive, 0, 0, &Timeout);
    if ( !v6 )
      break;
    v5 = (void *)(v2 + 232);
    if ( (*((_DWORD *)StartContext + 532) & 2) == 0 )
    {
      if ( !v4 )
      {
        CurrentThread = KeGetCurrentThread();
        v8 = *(_QWORD *)(*((_QWORD *)StartContext + 36) + 136LL);
        if ( CurrentThread != *(struct _KTHREAD **)(v8 + 64) )
        {
          ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v8 + 80) + 216LL));
          *(_QWORD *)(*(_QWORD *)(*((_QWORD *)StartContext + 36) + 136LL) + 64LL) = CurrentThread;
        }
        ++*(_DWORD *)(*(_QWORD *)(*((_QWORD *)StartContext + 36) + 136LL) + 72LL);
        v9 = *((_QWORD *)StartContext + 36);
        v10 = *(struct _FILE_OBJECT **)(v9 + 504);
        if ( v10 )
          ObfReferenceObject(*(PVOID *)(v9 + 504));
        --*(_DWORD *)(*(_QWORD *)(*((_QWORD *)StartContext + 36) + 136LL) + 72LL);
        v11 = *(_QWORD *)(*((_QWORD *)StartContext + 36) + 136LL);
        if ( !*(_DWORD *)(v11 + 72) )
        {
          *(_QWORD *)(v11 + 64) = 0;
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)StartContext + 36) + 136LL) + 80LL)
                                         + 216LL));
        }
        if ( v10 )
        {
          FsRtlNotifyVolumeEvent(v10, 0xEu);
          ObfDereferenceObject(v10);
        }
        v4 = 1;
      }
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 56, WPP_e04914546632397e8b30a0a107c62418_Traceguids);
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(v2 + 128), 1u);
      v12 = *(_DWORD *)(v2 + 12);
      *(_DWORD *)(v2 + 4) |= 4u;
      memset(*(void **)(v2 + 24), 0, (unsigned int)(v12 << *((_DWORD *)StartContext + 18)));
      v13 = (int *)(StartContext + 684);
      v6 = UdfQueryFreeBlocksAndNWA(StartContext, &v19, StartContext + 684);
      ExReleaseResourceLite((PERESOURCE)(v2 + 128));
      v3 = v19;
      if ( v6 < 0 )
        break;
      while ( v3 && !KeReadStateEvent((PRKEVENT)(v2 + 232)) )
      {
        LOBYTE(v14) = 1;
        v6 = UdfRmwIssueIoRequest((int)Entry, v14, *v13, *(_DWORD *)(v2 + 12), *(PVOID *)(v2 + 24));
        if ( v6 < 0 )
        {
          if ( v6 == -1073741248 )
            v6 = 0;
          break;
        }
        *v13 += *(_DWORD *)(v2 + 12);
        v3 -= *(_DWORD *)(v2 + 12);
        v19 = v3;
      }
      if ( !ExAcquireResourceExclusiveLite((PERESOURCE)(StartContext + 136), (Entry[3] & 0x400000000LL) != 0) )
      {
        LODWORD(Entry[3]) = -1073741608;
        ExRaiseStatus(-1073741608);
      }
      UdfSynchronizeDeviceCache(*((_QWORD *)StartContext + 3));
      if ( !v3 )
        v6 = UdfCloseTrackSession(*((_QWORD *)StartContext + 3), 2, 0);
      UdfReleaseDevice(v15, StartContext, 0);
      if ( (*(_DWORD *)(v2 + 4) & 4) != 0 )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)(v2 + 128), 1u);
        *(_DWORD *)(v2 + 4) &= ~4u;
        ExReleaseResourceLite((PERESOURCE)(v2 + 128));
      }
      if ( !v3 || v6 < 0 )
        break;
      v5 = (void *)(v2 + 232);
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        v5 = (void *)(v2 + 232);
        if ( (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            57,
            WPP_e04914546632397e8b30a0a107c62418_Traceguids);
          goto LABEL_5;
        }
      }
    }
  }
  UdfCleanupIrpContext(Entry);
  KeLeaveCriticalRegion();
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20000000) != 0 )
  {
    WPP_SF_dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      58,
      WPP_e04914546632397e8b30a0a107c62418_Traceguids,
      (unsigned int)v6,
      v3);
  }
}

```

## disassembly

```asm
0x14002c330  mov     [rsp-8+arg_10], rbx
0x14002c335  push    rbp
0x14002c336  push    rsi
0x14002c337  push    rdi
0x14002c338  push    r12
0x14002c33a  push    r13
0x14002c33c  push    r14
0x14002c33e  push    r15
0x14002c340  lea     rbp, [rsp-27h]
0x14002c345  sub     rsp, 0C0h
0x14002c34c  mov     rbx, rcx
0x14002c34f  mov     edi, 68h ; 'h'
0x14002c354  mov     r8d, edi; Size
0x14002c357  lea     rcx, [rbp+57h+Entry]; void *
0x14002c35b  xor     edx, edx; Val
0x14002c35d  call    memset
0x14002c362  mov     r14, [rbx+68h]
0x14002c366  xor     eax, eax
0x14002c368  or      esi, 0FFFFFFFFh
0x14002c36b  mov     [rbp+57h+var_B0], rax
0x14002c36f  xorps   xmm0, xmm0
0x14002c372  mov     qword ptr [rbp+57h+arg_8], rax
0x14002c376  movups  [rbp+57h+var_C0], xmm0
0x14002c37a  xor     r13b, r13b
0x14002c37d  mov     [rbp+57h+arg_0], esi
0x14002c380  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c387  lea     rax, WPP_GLOBAL_Control
0x14002c38e  cmp     rcx, rax
0x14002c391  jz      short loc_14002C3AF
0x14002c393  test    dword ptr [rcx+2Ch], 20000000h
0x14002c39a  jz      short loc_14002C3AF
0x14002c39c  mov     rcx, [rcx+18h]
0x14002c3a0  lea     edx, [rdi-31h]
0x14002c3a3  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14002c3aa  call    WPP_SF_
0x14002c3af  mov     qword ptr [rbp+57h+arg_8], 0FFFFFFFFDC3CBA00h
0x14002c3b7  call    cs:__imp_KeEnterCriticalRegion
0x14002c3be  nop     dword ptr [rax+rax+00h]
0x14002c3c3  mov     r8, rdi; Size
0x14002c3c6  lea     rcx, [rbp+57h+Entry]; void *
0x14002c3ca  xor     edx, edx; Val
0x14002c3cc  call    memset
0x14002c3d1  lea     rdx, [rbp+57h+var_C0]
0x14002c3d5  mov     [rbp+57h+Entry], 680937h
0x14002c3dc  lea     rcx, [rbp+57h+Entry]
0x14002c3e0  mov     [rbp+57h+var_90], rbx
0x14002c3e4  mov     [rbp+57h+var_84], 1005h
0x14002c3eb  call    UdfSetThreadContext
0x14002c3f0  lea     rax, [r14+0E8h]
0x14002c3f7  lea     rcx, [rbp+57h+arg_8]
0x14002c3fb  xor     r9d, r9d; Alertable
0x14002c3fe  mov     [rsp+0F0h+Timeout], rcx; Timeout
0x14002c403  xor     r8d, r8d; WaitMode
0x14002c406  mov     rcx, rax; Object
0x14002c409  xor     edx, edx; WaitReason
0x14002c40b  call    cs:__imp_KeWaitForSingleObject
0x14002c412  nop     dword ptr [rax+rax+00h]
0x14002c417  mov     edi, eax
0x14002c419  test    eax, eax
0x14002c41b  jz      loc_14002C700
0x14002c421  mov     eax, [rbx+850h]
0x14002c427  test    al, 2
0x14002c429  lea     rax, [r14+0E8h]
0x14002c430  jnz     short loc_14002C3F7
0x14002c432  test    r13b, r13b
0x14002c435  jnz     loc_14002C531
0x14002c43b  mov     rdi, gs:188h
0x14002c444  mov     rax, [rbx+120h]
0x14002c44b  mov     rcx, [rax+88h]
0x14002c452  cmp     rdi, [rcx+40h]
0x14002c456  jz      short loc_14002C481
0x14002c458  mov     rcx, [rcx+50h]
0x14002c45c  add     rcx, 0D8h; FastMutex
0x14002c463  call    cs:__imp_ExAcquireFastMutex
0x14002c46a  nop     dword ptr [rax+rax+00h]
0x14002c46f  mov     rax, [rbx+120h]
0x14002c476  mov     rcx, [rax+88h]
0x14002c47d  mov     [rcx+40h], rdi
0x14002c481  mov     rax, [rbx+120h]
0x14002c488  mov     rcx, [rax+88h]
0x14002c48f  inc     dword ptr [rcx+48h]
0x14002c492  mov     rax, [rbx+120h]
0x14002c499  mov     rdi, [rax+1F8h]
0x14002c4a0  test    rdi, rdi
0x14002c4a3  jz      short loc_14002C4B4
0x14002c4a5  mov     rcx, rdi; Object
0x14002c4a8  call    cs:__imp_ObfReferenceObject
0x14002c4af  nop     dword ptr [rax+rax+00h]
0x14002c4b4  mov     rax, [rbx+120h]
0x14002c4bb  mov     rcx, [rax+88h]
0x14002c4c2  dec     dword ptr [rcx+48h]
0x14002c4c5  mov     rax, [rbx+120h]
0x14002c4cc  mov     rcx, [rax+88h]
0x14002c4d3  cmp     dword ptr [rcx+48h], 0
0x14002c4d7  jnz     short loc_14002C506
0x14002c4d9  mov     qword ptr [rcx+40h], 0
0x14002c4e1  mov     rax, [rbx+120h]
0x14002c4e8  mov     rdx, [rax+88h]
0x14002c4ef  mov     rcx, [rdx+50h]
0x14002c4f3  add     rcx, 0D8h; FastMutex
0x14002c4fa  call    cs:__imp_ExReleaseFastMutex
0x14002c501  nop     dword ptr [rax+rax+00h]
0x14002c506  test    rdi, rdi
0x14002c509  jz      short loc_14002C52E
0x14002c50b  mov     edx, 0Eh; EventCode
0x14002c510  mov     rcx, rdi; FileObject
0x14002c513  call    cs:__imp_FsRtlNotifyVolumeEvent
0x14002c51a  nop     dword ptr [rax+rax+00h]
0x14002c51f  mov     rcx, rdi; Object
0x14002c522  call    cs:__imp_ObfDereferenceObject
0x14002c529  nop     dword ptr [rax+rax+00h]
0x14002c52e  mov     r13b, 1
0x14002c531  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c538  lea     rax, WPP_GLOBAL_Control
0x14002c53f  cmp     rcx, rax
0x14002c542  jz      short loc_14002C562
0x14002c544  test    dword ptr [rcx+2Ch], 20000000h
0x14002c54b  jz      short loc_14002C562
0x14002c54d  mov     rcx, [rcx+18h]
0x14002c551  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14002c558  mov     edx, 38h ; '8'
0x14002c55d  call    WPP_SF_
0x14002c562  lea     r12, [r14+80h]
0x14002c569  mov     dl, 1; Wait
0x14002c56b  mov     rcx, r12; Resource
0x14002c56e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002c575  nop     dword ptr [rax+rax+00h]
0x14002c57a  mov     r8d, [r14+0Ch]
0x14002c57e  xor     edx, edx; Val
0x14002c580  or      dword ptr [r14+4], 4
0x14002c585  mov     ecx, [rbx+48h]
0x14002c588  shl     r8d, cl; Size
0x14002c58b  mov     rcx, [r14+18h]; void *
0x14002c58f  call    memset
0x14002c594  lea     r15, [rbx+2ACh]
0x14002c59b  mov     rcx, rbx
0x14002c59e  mov     r8, r15
0x14002c5a1  lea     rdx, [rbp+57h+arg_0]
0x14002c5a5  call    UdfQueryFreeBlocksAndNWA
0x14002c5aa  mov     rcx, r12; Resource
0x14002c5ad  mov     edi, eax
0x14002c5af  call    cs:__imp_ExReleaseResourceLite
0x14002c5b6  nop     dword ptr [rax+rax+00h]
0x14002c5bb  mov     esi, [rbp+57h+arg_0]
0x14002c5be  test    edi, edi
0x14002c5c0  js      loc_14002C700
0x14002c5c6  test    esi, esi
0x14002c5c8  jz      short loc_14002C61D
0x14002c5ca  lea     rcx, [r14+0E8h]; Event
0x14002c5d1  call    cs:__imp_KeReadStateEvent
0x14002c5d8  nop     dword ptr [rax+rax+00h]
0x14002c5dd  test    eax, eax
0x14002c5df  jnz     short loc_14002C61D
0x14002c5e1  mov     rax, [r14+18h]
0x14002c5e5  lea     rcx, [rbp+57h+Entry]; int
0x14002c5e9  mov     r9d, [r14+0Ch]; int
0x14002c5ed  mov     dl, 1; int
0x14002c5ef  mov     r8d, [r15]; int
0x14002c5f2  mov     [rsp+0F0h+Timeout], rax; VirtualAddress
0x14002c5f7  call    UdfRmwIssueIoRequest
0x14002c5fc  mov     edi, eax
0x14002c5fe  test    eax, eax
0x14002c600  js      short loc_14002C612
0x14002c602  mov     eax, [r14+0Ch]
0x14002c606  add     [r15], eax
0x14002c609  sub     esi, [r14+0Ch]
0x14002c60d  mov     [rbp+57h+arg_0], esi
0x14002c610  jmp     short loc_14002C5C6
0x14002c612  xor     eax, eax
0x14002c614  cmp     edi, 0C0000240h
0x14002c61a  cmovz   edi, eax
0x14002c61d  mov     edx, [rbp+57h+var_84]
0x14002c620  lea     rcx, [rbx+88h]; Resource
0x14002c627  shr     edx, 2
0x14002c62a  and     dl, 1; Wait
0x14002c62d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002c634  nop     dword ptr [rax+rax+00h]
0x14002c639  test    al, al
0x14002c63b  jz      loc_14002C6EB
0x14002c641  mov     rcx, [rbx+18h]
0x14002c645  call    UdfSynchronizeDeviceCache
0x14002c64a  test    esi, esi
0x14002c64c  jnz     short loc_14002C65F
0x14002c64e  mov     rcx, [rbx+18h]
0x14002c652  lea     edx, [rsi+2]
0x14002c655  xor     r8d, r8d
0x14002c658  call    UdfCloseTrackSession
0x14002c65d  mov     edi, eax
0x14002c65f  xor     r8d, r8d
0x14002c662  mov     rdx, rbx
0x14002c665  call    UdfReleaseDevice
0x14002c66a  mov     eax, [r14+4]
0x14002c66e  test    al, 4
0x14002c670  jz      short loc_14002C697
0x14002c672  mov     dl, 1; Wait
0x14002c674  mov     rcx, r12; Resource
0x14002c677  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14002c67e  nop     dword ptr [rax+rax+00h]
0x14002c683  and     dword ptr [r14+4], 0FFFFFFFBh
0x14002c688  mov     rcx, r12; Resource
0x14002c68b  call    cs:__imp_ExReleaseResourceLite
0x14002c692  nop     dword ptr [rax+rax+00h]
0x14002c697  test    esi, esi
0x14002c699  jz      short loc_14002C700
0x14002c69b  test    edi, edi
0x14002c69d  js      short loc_14002C700
0x14002c69f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c6a6  lea     rax, WPP_GLOBAL_Control
0x14002c6ad  cmp     rcx, rax
0x14002c6b0  lea     rax, [r14+0E8h]
0x14002c6b7  jz      loc_14002C3F7
0x14002c6bd  test    dword ptr [rcx+2Ch], 20000000h
0x14002c6c4  lea     rax, [r14+0E8h]
0x14002c6cb  jz      loc_14002C3F7
0x14002c6d1  mov     rcx, [rcx+18h]
0x14002c6d5  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14002c6dc  mov     edx, 39h ; '9'
0x14002c6e1  call    WPP_SF_
0x14002c6e6  jmp     loc_14002C3F0
0x14002c6eb  mov     ecx, 0C00000D8h; Status
0x14002c6f0  mov     [rbp+57h+var_88], ecx
0x14002c6f3  call    cs:__imp_ExRaiseStatus
0x14002c700  xor     edx, edx
0x14002c702  lea     rcx, [rbp+57h+Entry]; Entry
0x14002c706  call    UdfCleanupIrpContext
0x14002c70b  call    cs:__imp_KeLeaveCriticalRegion
0x14002c712  nop     dword ptr [rax+rax+00h]
0x14002c717  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c71e  lea     rax, WPP_GLOBAL_Control
0x14002c725  cmp     rcx, rax
0x14002c728  jz      short loc_14002C74F
0x14002c72a  test    dword ptr [rcx+2Ch], 20000000h
0x14002c731  jz      short loc_14002C74F
0x14002c733  mov     rcx, [rcx+18h]
0x14002c737  lea     r8, WPP_e04914546632397e8b30a0a107c62418_Traceguids
0x14002c73e  mov     edx, 3Ah ; ':'
0x14002c743  mov     dword ptr [rsp+0F0h+Timeout], esi
0x14002c747  mov     r9d, edi
0x14002c74a  call    WPP_SF_dd
0x14002c74f  mov     rbx, [rsp+0F0h+arg_10]
0x14002c757  add     rsp, 0C0h
0x14002c75e  pop     r15
0x14002c760  pop     r14
0x14002c762  pop     r13
0x14002c764  pop     r12
0x14002c766  pop     rdi
0x14002c767  pop     rsi
0x14002c768  pop     rbp
0x14002c769  retn
```
