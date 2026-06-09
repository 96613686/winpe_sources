# WimpFSFBackgroundValidationWorker

- ea: `0x1400290e0`
- end: `0x1400292ce`
- name: `WimpFSFBackgroundValidationWorker`
- size: `494`
- prototype: `void __stdcall(PFLT_DEFERRED_IO_WORKITEM FltWorkItem, PFLT_CALLBACK_DATA CallbackData, PVOID Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140022e2c`
- `0x1400287cc`
- `0x140028ef4`
- `0x1400290e0`
- `0x140029684`

## import_xrefs

- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x1400292b3`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x1400292b3`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x140029140`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x140029140`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400291ad`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x1400291ad`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14002914f`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14002914f`
- `FLTMGR!FltIsIoCanceled` at `0x14002910e`
- `FLTMGR!FltIsIoCanceled` at `0x14002910e`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140029171`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140029171`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14002923b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14002923b`
- `FLTMGR!FltReleasePushLockEx` at `0x1400291f4`
- `FLTMGR!FltReleasePushLockEx` at `0x140029225`
- `FLTMGR!FltReleasePushLockEx` at `0x14002925f`
- `FLTMGR!FltReleasePushLockEx` at `0x1400291f4`
- `FLTMGR!FltReleasePushLockEx` at `0x140029225`
- `FLTMGR!FltReleasePushLockEx` at `0x14002925f`

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
0x1400290e0  mov     rax, rsp
0x1400290e3  mov     [rax+10h], rbx
0x1400290e7  mov     [rax+8], rcx
0x1400290eb  push    rbp
0x1400290ec  push    rsi
0x1400290ed  push    rdi
0x1400290ee  push    r12
0x1400290f0  push    r13
0x1400290f2  push    r14
0x1400290f4  push    r15
0x1400290f6  sub     rsp, 30h
0x1400290fa  mov     rcx, rdx; CallbackData
0x1400290fd  mov     byte ptr [rax+18h], 0
0x140029101  mov     rbx, r8
0x140029104  lea     r14, [r8+40008h]
0x14002910b  mov     r13, rdx
0x14002910e  call    cs:__imp_FltIsIoCanceled
0x140029115  nop     dword ptr [rax+rax+00h]
0x14002911a  test    al, al
0x14002911c  jz      short loc_140029193
0x14002911e  mov     edi, 0C0000120h
0x140029123  mov     rsi, [rsp+68h+FltWorkItem]
0x140029128  mov     rcx, r14
0x14002912b  call    WimpFSFCloseBackgroundValidationList
0x140029130  mov     rcx, [rbx+40000h]; Instance
0x140029137  mov     r8d, 69637077h; Tag
0x14002913d  mov     rdx, rbx; Buffer
0x140029140  call    cs:__imp_FltFreePoolAlignedWithTag
0x140029147  nop     dword ptr [rax+rax+00h]
0x14002914c  mov     rcx, rsi; FltWorkItem
0x14002914f  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140029156  nop     dword ptr [rax+rax+00h]
0x14002915b  xor     r8d, r8d; Context
0x14002915e  xor     eax, eax
0x140029160  xchg    eax, cs:g_WimIntegrityBackgroundValidationInProgress
0x140029166  mov     rcx, r13; CallbackData
0x140029169  mov     [r13+18h], edi
0x14002916d  lea     edx, [r8+4]; CallbackStatus
0x140029171  call    cs:__imp_FltCompletePendedPreOperation
0x140029178  nop     dword ptr [rax+rax+00h]
0x14002917d  mov     rbx, [rsp+68h+arg_8]
0x140029182  add     rsp, 30h
0x140029186  pop     r15
0x140029188  pop     r14
0x14002918a  pop     r13
0x14002918c  pop     r12
0x14002918e  pop     rdi
0x14002918f  pop     rsi
0x140029190  pop     rbp
0x140029191  retn
0x140029193  mov     rax, [r14]
0x140029196  xor     edi, edi
0x140029198  test    rax, rax
0x14002919b  jz      short loc_140029123
0x14002919d  lea     r15, [rax-20h]
0x1400291a1  xor     edx, edx
0x1400291a3  lea     rbp, [r15+3F0h]
0x1400291aa  mov     rcx, rbp
0x1400291ad  call    cs:__imp_FltAcquirePushLockSharedEx
0x1400291b4  nop     dword ptr [rax+rax+00h]
0x1400291b9  mov     rdx, [r15+3F8h]; BitMapHeader
0x1400291c0  test    rdx, rdx
0x1400291c3  jz      short loc_140029218
0x1400291c5  lea     r8, [rsp+68h+arg_10]
0x1400291cd  mov     rcx, rbx; Buffer
0x1400291d0  call    WimpFSFBackgroundValidateNextBlocks
0x1400291d5  mov     edi, eax
0x1400291d7  test    eax, eax
0x1400291d9  jns     short loc_140029207
0x1400291db  mov     esi, 1
0x1400291e0  add     [rbx+40010h], esi
0x1400291e6  cmp     dword ptr [rbx+40010h], 0Ah
0x1400291ed  jbe     short loc_140029205
0x1400291ef  xor     edx, edx
0x1400291f1  mov     rcx, rbp
0x1400291f4  call    cs:__imp_FltReleasePushLockEx
0x1400291fb  nop     dword ptr [rax+rax+00h]
0x140029200  jmp     loc_140029123
0x140029205  xor     edi, edi
0x140029207  mov     sil, [rsp+68h+arg_10]
0x14002920f  lea     r12, [rbx+40008h]
0x140029216  jmp     short loc_140029220
0x140029218  mov     esi, 1
0x14002921d  mov     r12, r14
0x140029220  xor     edx, edx
0x140029222  mov     rcx, rbp
0x140029225  call    cs:__imp_FltReleasePushLockEx
0x14002922c  nop     dword ptr [rax+rax+00h]
0x140029231  test    sil, sil
0x140029234  jz      short loc_14002928B
0x140029236  xor     edx, edx
0x140029238  mov     rcx, rbp
0x14002923b  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140029242  nop     dword ptr [rax+rax+00h]
0x140029247  xor     ecx, ecx
0x140029249  xchg    rcx, [r15+3F8h]; P
0x140029250  test    rcx, rcx
0x140029253  jz      short loc_14002925A
0x140029255  call    WimFSFDestroyIntegrity
0x14002925a  xor     edx, edx
0x14002925c  mov     rcx, rbp
0x14002925f  call    cs:__imp_FltReleasePushLockEx
0x140029266  nop     dword ptr [rax+rax+00h]
0x14002926b  mov     rax, [r14]
0x14002926e  test    rax, rax
0x140029271  jz      short loc_140029279
0x140029273  mov     rax, [rax]
0x140029276  mov     [r14], rax
0x140029279  mov     rcx, r15; P
0x14002927c  call    WimFSFDereferenceBackingFile
0x140029281  mov     dword ptr [rbx+40010h], 0
0x14002928b  cmp     qword ptr [r12], 0
0x140029290  jz      loc_140029123
0x140029296  mov     rsi, [rsp+68h+FltWorkItem]
0x14002929b  lea     r8, WimpFSFBackgroundValidationWorker; WorkerRoutine
0x1400292a2  mov     rcx, rsi; FltWorkItem
0x1400292a5  mov     [rsp+68h+Context], rbx; Context
0x1400292aa  mov     r9d, 4; QueueType
0x1400292b0  mov     rdx, r13; Data
0x1400292b3  call    cs:__imp_FltQueueDeferredIoWorkItem
0x1400292ba  nop     dword ptr [rax+rax+00h]
0x1400292bf  mov     edi, eax
0x1400292c1  test    eax, eax
0x1400292c3  jns     loc_14002917D
0x1400292c9  jmp     loc_140029128
```
