# WimpFSFBackgroundValidationWorker

- ea: `0x140029130`
- end: `0x14002931e`
- name: `WimpFSFBackgroundValidationWorker`
- size: `494`
- prototype: `void __stdcall(PFLT_DEFERRED_IO_WORKITEM FltWorkItem, PFLT_CALLBACK_DATA CallbackData, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140022e2c`
- `0x14002881c`
- `0x140028f44`
- `0x140029130`
- `0x1400296d4`

## import_xrefs

- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140029303`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140029303`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x140029190`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x140029190`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400291fd`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400291fd`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14002919f`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14002919f`
- `FLTMGR!FltIsIoCanceled` at `0x14002915e`
- `FLTMGR!FltIsIoCanceled` at `0x14002915e`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400291c1`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400291c1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14002928b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14002928b`
- `FLTMGR!FltReleasePushLockEx` at `0x140029244`
- `FLTMGR!FltReleasePushLockEx` at `0x140029275`
- `FLTMGR!FltReleasePushLockEx` at `0x1400292af`
- `FLTMGR!FltReleasePushLockEx` at `0x140029244`
- `FLTMGR!FltReleasePushLockEx` at `0x140029275`
- `FLTMGR!FltReleasePushLockEx` at `0x1400292af`

## pseudocode

```c
void __fastcall WimpFSFBackgroundValidationWorker(
        PFLT_DEFERRED_IO_WORKITEM FltWorkItem,
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE *Context)
{
  _QWORD **v4; // r14
  NTSTATUS v6; // edi
  struct _FLT_DEFERRED_IO_WORKITEM *v7; // rsi
  _QWORD *v8; // rax
  volatile __int64 *v9; // r15
  __int64 v10; // rbp
  struct _RTL_BITMAP *v11; // rdx
  char v12; // si
  _QWORD *v13; // r12
  char *v14; // rcx
  char v16; // [rsp+80h] [rbp+18h] BYREF

  v16 = 0;
  v4 = (_QWORD **)(Context + 32769);
  if ( FltIsIoCanceled(CallbackData) )
  {
    v6 = -1073741536;
LABEL_3:
    v7 = FltWorkItem;
LABEL_4:
    WimpFSFCloseBackgroundValidationList(v4);
    FltFreePoolAlignedWithTag(Context[0x8000], Context, 0x69637077u);
    FltFreeDeferredIoWorkItem(v7);
    _InterlockedExchange(&g_WimIntegrityBackgroundValidationInProgress, 0);
    CallbackData->IoStatus.Status = v6;
    FltCompletePendedPreOperation(CallbackData, FLT_PREOP_COMPLETE, 0);
    return;
  }
  v8 = *v4;
  v6 = 0;
  if ( !*v4 )
    goto LABEL_3;
  v9 = v8 - 4;
  v10 = (__int64)(v8 + 122);
  FltAcquirePushLockSharedEx(v10, 0);
  v11 = (struct _RTL_BITMAP *)*((_QWORD *)v9 + 127);
  if ( v11 )
  {
    v6 = WimpFSFBackgroundValidateNextBlocks(Context, v11, &v16);
    if ( v6 < 0 )
    {
      if ( ++*((_DWORD *)Context + 65540) > 0xAu )
      {
        FltReleasePushLockEx(v10, 0);
        goto LABEL_3;
      }
      v6 = 0;
    }
    v12 = v16;
    v13 = Context + 32769;
  }
  else
  {
    v12 = 1;
    v13 = v4;
  }
  FltReleasePushLockEx(v10, 0);
  if ( v12 )
  {
    FltAcquirePushLockExclusiveEx(v10, 0);
    v14 = (char *)_InterlockedExchange64(v9 + 127, 0);
    if ( v14 )
      WimFSFDestroyIntegrity(v14);
    FltReleasePushLockEx(v10, 0);
    if ( *v4 )
      *v4 = (_QWORD *)**v4;
    WimFSFDereferenceBackingFile((PVOID)v9);
    *((_DWORD *)Context + 65540) = 0;
  }
  if ( !*v13 )
    goto LABEL_3;
  v7 = FltWorkItem;
  v6 = FltQueueDeferredIoWorkItem(
         FltWorkItem,
         CallbackData,
         WimpFSFBackgroundValidationWorker,
         BackgroundWorkQueue,
         Context);
  if ( v6 < 0 )
    goto LABEL_4;
}

```

## disassembly

```asm
0x140029130  mov     rax, rsp
0x140029133  mov     [rax+10h], rbx
0x140029137  mov     [rax+8], rcx
0x14002913b  push    rbp
0x14002913c  push    rsi
0x14002913d  push    rdi
0x14002913e  push    r12
0x140029140  push    r13
0x140029142  push    r14
0x140029144  push    r15
0x140029146  sub     rsp, 30h
0x14002914a  mov     rcx, rdx; CallbackData
0x14002914d  mov     byte ptr [rax+18h], 0
0x140029151  mov     rbx, r8
0x140029154  lea     r14, [r8+40008h]
0x14002915b  mov     r13, rdx
0x14002915e  call    cs:__imp_FltIsIoCanceled
0x140029165  nop     dword ptr [rax+rax+00h]
0x14002916a  test    al, al
0x14002916c  jz      short loc_1400291E3
0x14002916e  mov     edi, 0C0000120h
0x140029173  mov     rsi, [rsp+68h+FltWorkItem]
0x140029178  mov     rcx, r14
0x14002917b  call    WimpFSFCloseBackgroundValidationList
0x140029180  mov     rcx, [rbx+40000h]; Instance
0x140029187  mov     r8d, 69637077h; Tag
0x14002918d  mov     rdx, rbx; Buffer
0x140029190  call    cs:__imp_FltFreePoolAlignedWithTag
0x140029197  nop     dword ptr [rax+rax+00h]
0x14002919c  mov     rcx, rsi; FltWorkItem
0x14002919f  call    cs:__imp_FltFreeDeferredIoWorkItem
0x1400291a6  nop     dword ptr [rax+rax+00h]
0x1400291ab  xor     r8d, r8d; Context
0x1400291ae  xor     eax, eax
0x1400291b0  xchg    eax, cs:g_WimIntegrityBackgroundValidationInProgress
0x1400291b6  mov     rcx, r13; CallbackData
0x1400291b9  mov     [r13+18h], edi
0x1400291bd  lea     edx, [r8+4]; CallbackStatus
0x1400291c1  call    cs:__imp_FltCompletePendedPreOperation
0x1400291c8  nop     dword ptr [rax+rax+00h]
0x1400291cd  mov     rbx, [rsp+68h+arg_8]
0x1400291d2  add     rsp, 30h
0x1400291d6  pop     r15
0x1400291d8  pop     r14
0x1400291da  pop     r13
0x1400291dc  pop     r12
0x1400291de  pop     rdi
0x1400291df  pop     rsi
0x1400291e0  pop     rbp
0x1400291e1  retn
0x1400291e3  mov     rax, [r14]
0x1400291e6  xor     edi, edi
0x1400291e8  test    rax, rax
0x1400291eb  jz      short loc_140029173
0x1400291ed  lea     r15, [rax-20h]
0x1400291f1  xor     edx, edx
0x1400291f3  lea     rbp, [r15+3F0h]
0x1400291fa  mov     rcx, rbp
0x1400291fd  call    cs:__imp_FltAcquirePushLockSharedEx
0x140029204  nop     dword ptr [rax+rax+00h]
0x140029209  mov     rdx, [r15+3F8h]; BitMapHeader
0x140029210  test    rdx, rdx
0x140029213  jz      short loc_140029268
0x140029215  lea     r8, [rsp+68h+arg_10]
0x14002921d  mov     rcx, rbx; Buffer
0x140029220  call    WimpFSFBackgroundValidateNextBlocks
0x140029225  mov     edi, eax
0x140029227  test    eax, eax
0x140029229  jns     short loc_140029257
0x14002922b  mov     esi, 1
0x140029230  add     [rbx+40010h], esi
0x140029236  cmp     dword ptr [rbx+40010h], 0Ah
0x14002923d  jbe     short loc_140029255
0x14002923f  xor     edx, edx
0x140029241  mov     rcx, rbp
0x140029244  call    cs:__imp_FltReleasePushLockEx
0x14002924b  nop     dword ptr [rax+rax+00h]
0x140029250  jmp     loc_140029173
0x140029255  xor     edi, edi
0x140029257  mov     sil, [rsp+68h+arg_10]
0x14002925f  lea     r12, [rbx+40008h]
0x140029266  jmp     short loc_140029270
0x140029268  mov     esi, 1
0x14002926d  mov     r12, r14
0x140029270  xor     edx, edx
0x140029272  mov     rcx, rbp
0x140029275  call    cs:__imp_FltReleasePushLockEx
0x14002927c  nop     dword ptr [rax+rax+00h]
0x140029281  test    sil, sil
0x140029284  jz      short loc_1400292DB
0x140029286  xor     edx, edx
0x140029288  mov     rcx, rbp
0x14002928b  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140029292  nop     dword ptr [rax+rax+00h]
0x140029297  xor     ecx, ecx
0x140029299  xchg    rcx, [r15+3F8h]; P
0x1400292a0  test    rcx, rcx
0x1400292a3  jz      short loc_1400292AA
0x1400292a5  call    WimFSFDestroyIntegrity
0x1400292aa  xor     edx, edx
0x1400292ac  mov     rcx, rbp
0x1400292af  call    cs:__imp_FltReleasePushLockEx
0x1400292b6  nop     dword ptr [rax+rax+00h]
0x1400292bb  mov     rax, [r14]
0x1400292be  test    rax, rax
0x1400292c1  jz      short loc_1400292C9
0x1400292c3  mov     rax, [rax]
0x1400292c6  mov     [r14], rax
0x1400292c9  mov     rcx, r15; P
0x1400292cc  call    WimFSFDereferenceBackingFile
0x1400292d1  mov     dword ptr [rbx+40010h], 0
0x1400292db  cmp     qword ptr [r12], 0
0x1400292e0  jz      loc_140029173
0x1400292e6  mov     rsi, [rsp+68h+FltWorkItem]
0x1400292eb  lea     r8, WimpFSFBackgroundValidationWorker; WorkerRoutine
0x1400292f2  mov     rcx, rsi; FltWorkItem
0x1400292f5  mov     [rsp+68h+Context], rbx; Context
0x1400292fa  mov     r9d, 4; QueueType
0x140029300  mov     rdx, r13; Data
0x140029303  call    cs:__imp_FltQueueDeferredIoWorkItem
0x14002930a  nop     dword ptr [rax+rax+00h]
0x14002930f  mov     edi, eax
0x140029311  test    eax, eax
0x140029313  jns     loc_1400291CD
0x140029319  jmp     loc_140029178
```
