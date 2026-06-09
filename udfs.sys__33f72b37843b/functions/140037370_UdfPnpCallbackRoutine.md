# UdfPnpCallbackRoutine

- ea: `0x140037370`
- end: `0x14003753d`
- name: `UdfPnpCallbackRoutine`
- size: `461`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x14000b128`
- `0x14000ca54`
- `0x14001c080`
- `0x140037370`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1400374ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400374fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003750e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400374ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400374fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003750e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400373be`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400373be`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400373a9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400373a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003751a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003751a`
- `ntoskrnl!ExQueueWorkItem` at `0x1400374d1`
- `ntoskrnl!ExQueueWorkItem` at `0x1400374d1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003747c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003747c`

## pseudocode

```c
__int64 __fastcall UdfPnpCallbackRoutine(char *NotificationStructure, __int64 *Context)
{
  __int64 v3; // rax
  __int64 *v4; // rbx
  __int64 *i; // rax
  _DWORD *v6; // rbx

  v3 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_IO_MEDIA_EJECT_REQUEST.Data1;
  if ( !v3 )
    v3 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_IO_MEDIA_EJECT_REQUEST.Data4;
  if ( !v3 )
  {
    v4 = 0;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    for ( i = (__int64 *)qword_140025B20; i != &qword_140025B20; i = (__int64 *)*i )
    {
      v4 = i - 4;
      if ( i - 4 == Context )
        goto LABEL_9;
    }
    if ( v4 != Context )
      goto LABEL_17;
LABEL_9:
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x20) != 0 )
    {
      WPP_SF_q(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        10,
        WPP_047ffe7159223357a68106d654fa515d_Traceguids,
        Context);
    }
    UdfAcquireResource(0, Context + 185, 0, 0);
    if ( *((_DWORD *)Context + 13) == 2 )
    {
      UdfAcquireResource(0, Context + 253, 0, 0);
      if ( (Context[266] & 0x36) == 0x10 )
      {
        v6 = ExAllocateFromNPagedLookasideList(&UdfIrpContextLookasideList);
        *((_DWORD *)Context + 532) |= 0x20u;
        memset(v6, 0, 0x68u);
        *v6 = 6818103;
        *((_QWORD *)v6 + 2) = Context;
        *((_BYTE *)v6 + 56) = 27;
        v6[7] |= 4u;
        *((_QWORD *)v6 + 11) = UdfPrepareMediaEjectWorker;
        *((_QWORD *)v6 + 12) = v6;
        *((_QWORD *)v6 + 9) = 0;
        ExQueueWorkItem((PWORK_QUEUE_ITEM)(v6 + 18), DelayedWorkQueue);
      }
      ExReleaseResourceLite((PERESOURCE)(Context + 253));
    }
    ExReleaseResourceLite((PERESOURCE)(Context + 185));
LABEL_17:
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
  return 0;
}

```

## disassembly

```asm
0x140037370  mov     [rsp+arg_10], rbx
0x140037375  mov     [rsp+arg_18], rsi
0x14003737a  push    rdi
0x14003737b  push    r14
0x14003737d  push    r15
0x14003737f  sub     rsp, 20h
0x140037383  mov     rdi, rdx
0x140037386  mov     rax, [rcx+4]
0x14003738a  sub     rax, qword ptr cs:GUID_IO_MEDIA_EJECT_REQUEST.Data1
0x140037391  jnz     short loc_14003739E
0x140037393  mov     rax, [rcx+0Ch]
0x140037397  sub     rax, qword ptr cs:GUID_IO_MEDIA_EJECT_REQUEST.Data4
0x14003739e  test    rax, rax
0x1400373a1  jnz     loc_140037526
0x1400373a7  xor     ebx, ebx
0x1400373a9  call    cs:__imp_KeEnterCriticalRegion
0x1400373b0  nop     dword ptr [rax+rax+00h]
0x1400373b5  mov     dl, 1; Wait
0x1400373b7  lea     rcx, Resource; Resource
0x1400373be  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400373c5  nop     dword ptr [rax+rax+00h]
0x1400373ca  mov     rax, cs:qword_140025B20
0x1400373d1  lea     rcx, qword_140025B20
0x1400373d8  jmp     short loc_1400373E6
0x1400373da  lea     rbx, [rax-20h]
0x1400373de  cmp     rbx, rdi
0x1400373e1  jz      short loc_1400373F4
0x1400373e3  mov     rax, [rax]
0x1400373e6  cmp     rax, rcx
0x1400373e9  jnz     short loc_1400373DA
0x1400373eb  cmp     rbx, rdi
0x1400373ee  jnz     loc_140037507
0x1400373f4  lea     rax, WPP_GLOBAL_Control
0x1400373fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140037402  cmp     rcx, rax
0x140037405  jz      short loc_140037426
0x140037407  mov     eax, [rcx+2Ch]
0x14003740a  test    al, 20h
0x14003740c  jz      short loc_140037426
0x14003740e  mov     edx, 0Ah
0x140037413  mov     r9, rdi
0x140037416  lea     r8, WPP_047ffe7159223357a68106d654fa515d_Traceguids
0x14003741d  mov     rcx, [rcx+18h]
0x140037421  call    WPP_SF_q
0x140037426  lea     rsi, [rdi+5C8h]
0x14003742d  mov     [rsp+38h+arg_0], rsi
0x140037432  xor     r9d, r9d
0x140037435  xor     r8d, r8d
0x140037438  mov     rdx, rsi
0x14003743b  xor     ecx, ecx
0x14003743d  call    UdfAcquireResource
0x140037442  cmp     dword ptr [rdi+34h], 2
0x140037446  jnz     loc_1400374F8
0x14003744c  lea     r14, [rdi+7E8h]
0x140037453  mov     [rsp+38h+arg_8], r14
0x140037458  xor     r9d, r9d
0x14003745b  xor     r8d, r8d
0x14003745e  mov     rdx, r14
0x140037461  xor     ecx, ecx
0x140037463  call    UdfAcquireResource
0x140037468  nop
0x140037469  mov     eax, [rdi+850h]
0x14003746f  and     al, 36h
0x140037471  cmp     al, 10h
0x140037473  jnz     short loc_1400374DD
0x140037475  lea     rcx, UdfIrpContextLookasideList; Lookaside
0x14003747c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140037483  nop     dword ptr [rax+rax+00h]
0x140037488  mov     rbx, rax
0x14003748b  or      dword ptr [rdi+850h], 20h
0x140037492  xor     edx, edx; Val
0x140037494  lea     r8d, [rdx+68h]; Size
0x140037498  mov     rcx, rax; void *
0x14003749b  call    memset
0x1400374a0  mov     dword ptr [rbx], 680937h
0x1400374a6  mov     [rbx+10h], rdi
0x1400374aa  mov     byte ptr [rbx+38h], 1Bh
0x1400374ae  or      dword ptr [rbx+1Ch], 4
0x1400374b2  lea     rcx, [rbx+48h]; WorkItem
0x1400374b6  lea     rax, UdfPrepareMediaEjectWorker
0x1400374bd  mov     [rcx+10h], rax
0x1400374c1  mov     [rcx+18h], rbx
0x1400374c5  mov     qword ptr [rcx], 0
0x1400374cc  mov     edx, 1; QueueType
0x1400374d1  call    cs:__imp_ExQueueWorkItem
0x1400374d8  nop     dword ptr [rax+rax+00h]
0x1400374dd  jmp     short loc_1400374E9
0x1400374df  mov     rsi, [rsp+38h+arg_0]
0x1400374e4  mov     r14, [rsp+38h+arg_8]
0x1400374e9  mov     rcx, r14; Resource
0x1400374ec  call    cs:__imp_ExReleaseResourceLite
0x1400374f3  nop     dword ptr [rax+rax+00h]
0x1400374f8  mov     rcx, rsi; Resource
0x1400374fb  call    cs:__imp_ExReleaseResourceLite
0x140037502  nop     dword ptr [rax+rax+00h]
0x140037507  lea     rcx, Resource; Resource
0x14003750e  call    cs:__imp_ExReleaseResourceLite
0x140037515  nop     dword ptr [rax+rax+00h]
0x14003751a  call    cs:__imp_KeLeaveCriticalRegion
0x140037521  nop     dword ptr [rax+rax+00h]
0x140037526  xor     eax, eax
0x140037528  mov     rbx, [rsp+38h+arg_10]
0x14003752d  mov     rsi, [rsp+38h+arg_18]
0x140037532  add     rsp, 20h
0x140037536  pop     r15
0x140037538  pop     r14
0x14003753a  pop     rdi
0x14003753b  retn
0x14005c09e  push    rbp
0x14005c0a0  sub     rsp, 20h
0x14005c0a4  mov     rbp, rdx
0x14005c0a7  mov     rdx, rcx
0x14005c0aa  xor     ecx, ecx
0x14005c0ac  call    UdfExceptionFilter
0x14005c0b1  nop
0x14005c0b2  add     rsp, 20h
0x14005c0b6  pop     rbp
0x14005c0b7  retn
```
