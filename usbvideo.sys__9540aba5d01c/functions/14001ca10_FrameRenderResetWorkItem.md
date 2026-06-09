# FrameRenderResetWorkItem

- ea: `0x14001ca10`
- end: `0x14001cc04`
- name: `FrameRenderResetWorkItem`
- size: `500`
- prototype: `__int64 __fastcall(PKSPIN Pin)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000b34c`
- `0x14001ab4c`
- `0x14001baac`
- `0x14001ca10`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cac5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cb41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cac5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cb41`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ca9b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ca9b`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14001caf3`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14001caf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cb08`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cb5e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cb08`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cb5e`
- `ntoskrnl!KeReleaseMutex` at `0x14001cb6f`
- `ntoskrnl!KeReleaseMutex` at `0x14001cb6f`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001cb25`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x14001cb25`
- `ks!KsPinAcquireProcessingMutex` at `0x14001ca67`
- `ks!KsPinAcquireProcessingMutex` at `0x14001ca67`
- `ks!KsDecrementCountedWorker` at `0x14001cb95`
- `ks!KsDecrementCountedWorker` at `0x14001cb95`
- `ks!KsPinReleaseProcessingMutex` at `0x14001cb7e`
- `ks!KsPinReleaseProcessingMutex` at `0x14001cbe6`
- `ks!KsPinReleaseProcessingMutex` at `0x14001cb7e`
- `ks!KsPinReleaseProcessingMutex` at `0x14001cbe6`

## pseudocode

```c
void __fastcall FrameRenderResetWorkItem(PKSPIN Pin)
{
  _QWORD *Context; // rsi
  __int64 v3; // rbp
  int v4; // ebx
  KIRQL v5; // al
  KIRQL v6; // r12
  struct _LIST_ENTRY *v7; // rbx
  KIRQL v8; // dl

  Context = Pin->Context;
  v3 = Context[12];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids, Context, Pin->Id);
  do
  {
    KsPinAcquireProcessingMutex(Pin);
    if ( !*((_BYTE *)Context + 384) )
    {
      KsPinReleaseProcessingMutex(Pin);
      return;
    }
    KeWaitForSingleObject((PVOID)(v3 + 216), Executive, 0, 0, 0);
    v4 = AbortUSBPipe(Context, 1);
    if ( v4 >= 0 )
    {
      v5 = KeAcquireSpinLockRaiseToDpc(Context + 15);
      v6 = v5;
      if ( *(_DWORD *)(v3 + 8) )
      {
        do
        {
          if ( *(_QWORD *)(v3 + 288) == v3 + 288 )
            break;
          --*(_DWORD *)(v3 + 64);
          v7 = ExInterlockedRemoveHeadList((PLIST_ENTRY)(v3 + 288), (PKSPIN_LOCK)(v3 + 280));
          KeReleaseSpinLock(Context + 15, v6);
          ExInterlockedInsertTailList((PLIST_ENTRY)(v3 + 304), v7, (PKSPIN_LOCK)(v3 + 272));
          ++*(_DWORD *)(v3 + 60);
          v4 = FrameRenderTransmitData(Pin);
          v6 = KeAcquireSpinLockRaiseToDpc(Context + 15);
        }
        while ( v4 >= 0 );
        v8 = v6;
      }
      else
      {
        v8 = v5;
      }
      KeReleaseSpinLock(Context + 15, v8);
    }
    KeReleaseMutex((PRKMUTEX)(v3 + 216), 0);
    KsPinReleaseProcessingMutex(Pin);
  }
  while ( v4 >= 0 && KsDecrementCountedWorker(*(PKSWORKER *)(v3 + 168)) );
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids, Context, Pin->Id);
}

```

## disassembly

```asm
0x14001ca10  push    rbx
0x14001ca12  push    rbp
0x14001ca13  push    rsi
0x14001ca14  push    rdi
0x14001ca15  push    r12
0x14001ca17  push    r13
0x14001ca19  push    r14
0x14001ca1b  push    r15
0x14001ca1d  sub     rsp, 38h
0x14001ca21  mov     rsi, [rcx+10h]
0x14001ca25  mov     rdi, rcx
0x14001ca28  mov     rbp, [rsi+60h]
0x14001ca2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ca33  lea     rax, WPP_GLOBAL_Control
0x14001ca3a  cmp     rcx, rax
0x14001ca3d  jz      short loc_14001CA64
0x14001ca3f  cmp     byte ptr [rcx+29h], 4
0x14001ca43  jb      short loc_14001CA64
0x14001ca45  mov     eax, [rdi+18h]
0x14001ca48  lea     r8, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids
0x14001ca4f  mov     rcx, [rcx+18h]
0x14001ca53  mov     edx, 0Ah
0x14001ca58  mov     r9, rsi
0x14001ca5b  mov     dword ptr [rsp+78h+Timeout], eax
0x14001ca5f  call    WPP_SF_qD
0x14001ca64  mov     rcx, rdi; Pin
0x14001ca67  call    cs:__imp_KsPinAcquireProcessingMutex
0x14001ca6e  nop     dword ptr [rax+rax+00h]
0x14001ca73  cmp     byte ptr [rsi+180h], 0
0x14001ca7a  jz      loc_14001CBE3
0x14001ca80  lea     r13, [rbp+0D8h]
0x14001ca87  mov     [rsp+78h+Timeout], 0; Timeout
0x14001ca90  mov     rcx, r13; Object
0x14001ca93  xor     r9d, r9d; Alertable
0x14001ca96  xor     r8d, r8d; WaitMode
0x14001ca99  xor     edx, edx; WaitReason
0x14001ca9b  call    cs:__imp_KeWaitForSingleObject
0x14001caa2  nop     dword ptr [rax+rax+00h]
0x14001caa7  mov     edx, 1
0x14001caac  mov     rcx, rsi
0x14001caaf  call    AbortUSBPipe
0x14001cab4  mov     ebx, eax
0x14001cab6  test    eax, eax
0x14001cab8  js      loc_14001CB6A
0x14001cabe  lea     r14, [rsi+78h]
0x14001cac2  mov     rcx, r14; SpinLock
0x14001cac5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001cacc  nop     dword ptr [rax+rax+00h]
0x14001cad1  cmp     dword ptr [rbp+8], 0
0x14001cad5  mov     r12b, al
0x14001cad8  jz      short loc_14001CB59
0x14001cada  lea     r15, [rbp+120h]
0x14001cae1  cmp     [r15], r15
0x14001cae4  jz      short loc_14001CB54
0x14001cae6  dec     dword ptr [rbp+40h]
0x14001cae9  lea     rdx, [rbp+118h]; Lock
0x14001caf0  mov     rcx, r15; ListHead
0x14001caf3  call    cs:__imp_ExInterlockedRemoveHeadList
0x14001cafa  nop     dword ptr [rax+rax+00h]
0x14001caff  mov     dl, r12b; NewIrql
0x14001cb02  mov     rcx, r14; SpinLock
0x14001cb05  mov     rbx, rax
0x14001cb08  call    cs:__imp_KeReleaseSpinLock
0x14001cb0f  nop     dword ptr [rax+rax+00h]
0x14001cb14  lea     r8, [rbp+110h]; Lock
0x14001cb1b  mov     rdx, rbx; ListEntry
0x14001cb1e  lea     rcx, [rbp+130h]; ListHead
0x14001cb25  call    cs:__imp_ExInterlockedInsertTailList
0x14001cb2c  nop     dword ptr [rax+rax+00h]
0x14001cb31  inc     dword ptr [rbp+3Ch]
0x14001cb34  mov     rcx, rdi; Pin
0x14001cb37  call    FrameRenderTransmitData
0x14001cb3c  mov     rcx, r14; SpinLock
0x14001cb3f  mov     ebx, eax
0x14001cb41  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001cb48  nop     dword ptr [rax+rax+00h]
0x14001cb4d  mov     r12b, al
0x14001cb50  test    ebx, ebx
0x14001cb52  jns     short loc_14001CAE1
0x14001cb54  mov     dl, r12b
0x14001cb57  jmp     short loc_14001CB5B
0x14001cb59  mov     dl, al; NewIrql
0x14001cb5b  mov     rcx, r14; SpinLock
0x14001cb5e  call    cs:__imp_KeReleaseSpinLock
0x14001cb65  nop     dword ptr [rax+rax+00h]
0x14001cb6a  xor     edx, edx; Wait
0x14001cb6c  mov     rcx, r13; Mutex
0x14001cb6f  call    cs:__imp_KeReleaseMutex
0x14001cb76  nop     dword ptr [rax+rax+00h]
0x14001cb7b  mov     rcx, rdi; Pin
0x14001cb7e  call    cs:__imp_KsPinReleaseProcessingMutex
0x14001cb85  nop     dword ptr [rax+rax+00h]
0x14001cb8a  test    ebx, ebx
0x14001cb8c  js      short loc_14001CBA9
0x14001cb8e  mov     rcx, [rbp+0A8h]; Worker
0x14001cb95  call    cs:__imp_KsDecrementCountedWorker
0x14001cb9c  nop     dword ptr [rax+rax+00h]
0x14001cba1  test    eax, eax
0x14001cba3  jnz     loc_14001CA64
0x14001cba9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbb0  lea     rax, WPP_GLOBAL_Control
0x14001cbb7  cmp     rcx, rax
0x14001cbba  jz      short loc_14001CBF2
0x14001cbbc  cmp     byte ptr [rcx+29h], 5
0x14001cbc0  jb      short loc_14001CBF2
0x14001cbc2  mov     eax, [rdi+18h]
0x14001cbc5  lea     r8, WPP_9e091edf6a993739dccdf8ddcdcaa537_Traceguids
0x14001cbcc  mov     rcx, [rcx+18h]
0x14001cbd0  mov     edx, 0Bh
0x14001cbd5  mov     r9, rsi
0x14001cbd8  mov     dword ptr [rsp+78h+Timeout], eax
0x14001cbdc  call    WPP_SF_qD
0x14001cbe1  jmp     short loc_14001CBF2
0x14001cbe3  mov     rcx, rdi; Pin
0x14001cbe6  call    cs:__imp_KsPinReleaseProcessingMutex
0x14001cbed  nop     dword ptr [rax+rax+00h]
0x14001cbf2  add     rsp, 38h
0x14001cbf6  pop     r15
0x14001cbf8  pop     r14
0x14001cbfa  pop     r13
0x14001cbfc  pop     r12
0x14001cbfe  pop     rdi
0x14001cbff  pop     rsi
0x14001cc00  pop     rbp
0x14001cc01  pop     rbx
0x14001cc02  retn
```
