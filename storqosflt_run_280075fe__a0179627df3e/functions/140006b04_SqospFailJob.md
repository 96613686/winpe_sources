# SqospFailJob

- ea: `0x140006b04`
- end: `0x140006c48`
- name: `SqospFailJob`
- size: `324`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006a38`

## callees

- `0x140001940`
- `0x140001ab0`
- `0x140003080`
- `0x140006b04`

## import_xrefs

- `ntoskrnl!KeAreAllApcsDisabled` at `0x140006b68`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140006b68`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bf6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006bf6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006b58`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006b58`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006bc3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006bc3`
- `HAL!KeQueryPerformanceCounter` at `0x140006b9e`
- `HAL!KeQueryPerformanceCounter` at `0x140006b9e`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140006c20`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140006c20`
- `FLTMGR!FltReferenceContext` at `0x140006b33`
- `FLTMGR!FltReferenceContext` at `0x140006b33`

## pseudocode

```c
__int64 __fastcall SqospFailJob(LARGE_INTEGER *Entry, NTSTATUS a2)
{
  LARGE_INTEGER v2; // rax
  struct _FLT_CALLBACK_DATA *QuadPart; // r14
  void *v6; // rbx
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v8; // rcx
  LARGE_INTEGER v9; // rdi
  __int64 v10; // rbx
  __int128 v12; // [rsp+20h] [rbp-28h] BYREF
  __int128 v13; // [rsp+30h] [rbp-18h]

  v2 = Entry[4];
  QuadPart = (struct _FLT_CALLBACK_DATA *)Entry->QuadPart;
  v12 = 0;
  v13 = 0;
  v6 = *(void **)(v2.QuadPart + 8);
  FltReferenceContext(v6);
  *(_QWORD *)&v12 = v6;
  *((_QWORD *)&v12 + 1) = &Object;
  WORD4(v13) = 0;
  BYTE10(v13) = 0;
  if ( KeGetCurrentIrql() > 1u || KeAreAllApcsDisabled() )
    *(_QWORD *)&v13 = 0;
  else
    *(_QWORD *)&v13 = *(_QWORD *)(*((_QWORD *)&v12 + 1) + 80LL)
                    + ((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v8 = Entry[4];
  v9 = PerformanceCounter;
  Entry[22] = PerformanceCounter;
  v10 = *(_QWORD *)(v8.QuadPart + 8);
  *(_BYTE *)(v10 + 840) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 832));
  BalanceCompleteJob(Entry, &v12);
  KeReleaseSpinLock(
    (PKSPIN_LOCK)(*(_QWORD *)(Entry[4].QuadPart + 8) + 832LL),
    *(_BYTE *)(*(_QWORD *)(Entry[4].QuadPart + 8) + 840LL));
  SqospDestroyJob(Entry);
  QuadPart->IoStatus.Information = 0;
  QuadPart->IoStatus.Status = a2;
  FltCompletePendedPreOperation(QuadPart, FLT_PREOP_COMPLETE, 0);
  return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SqospProcessJobDispatcherContext)(
           &v12,
           0,
           (LARGE_INTEGER)v9.QuadPart);
}

```

## disassembly

```asm
0x140006b04  push    rbp
0x140006b06  push    rbx
0x140006b07  push    rsi
0x140006b08  push    rdi
0x140006b09  push    r14
0x140006b0b  push    r15
0x140006b0d  mov     rbp, rsp
0x140006b10  sub     rsp, 48h
0x140006b14  mov     rax, [rcx+20h]
0x140006b18  xorps   xmm0, xmm0
0x140006b1b  mov     r14, [rcx]
0x140006b1e  mov     rsi, rcx
0x140006b21  movups  [rbp+var_28], xmm0
0x140006b25  mov     r15d, edx
0x140006b28  movups  [rbp+var_18], xmm0
0x140006b2c  mov     rbx, [rax+8]
0x140006b30  mov     rcx, rbx; Context
0x140006b33  call    cs:__imp_FltReferenceContext
0x140006b3a  nop     dword ptr [rax+rax+00h]
0x140006b3f  lea     rax, Object
0x140006b46  mov     qword ptr [rbp+var_28], rbx
0x140006b4a  mov     qword ptr [rbp+var_28+8], rax
0x140006b4e  mov     word ptr [rbp+var_18+8], 0
0x140006b54  mov     byte ptr [rbp+var_18+0Ah], 0
0x140006b58  call    cs:__imp_KeGetCurrentIrql
0x140006b5f  nop     dword ptr [rax+rax+00h]
0x140006b64  cmp     al, 1
0x140006b66  ja      short loc_140006B94
0x140006b68  call    cs:__imp_KeAreAllApcsDisabled
0x140006b6f  nop     dword ptr [rax+rax+00h]
0x140006b74  test    al, al
0x140006b76  jnz     short loc_140006B94
0x140006b78  mov     eax, gs:1A4h
0x140006b80  mov     ecx, eax
0x140006b82  mov     rax, qword ptr [rbp+var_28+8]
0x140006b86  shl     rcx, 6
0x140006b8a  add     rcx, [rax+50h]
0x140006b8e  mov     qword ptr [rbp+var_18], rcx
0x140006b92  jmp     short loc_140006B9C
0x140006b94  mov     qword ptr [rbp+var_18], 0
0x140006b9c  xor     ecx, ecx; PerformanceFrequency
0x140006b9e  call    cs:__imp_KeQueryPerformanceCounter
0x140006ba5  nop     dword ptr [rax+rax+00h]
0x140006baa  mov     rcx, [rsi+20h]
0x140006bae  mov     rdi, rax
0x140006bb1  mov     [rsi+0B0h], rax
0x140006bb8  mov     rbx, [rcx+8]
0x140006bbc  lea     rcx, [rbx+340h]; SpinLock
0x140006bc3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006bca  nop     dword ptr [rax+rax+00h]
0x140006bcf  lea     rdx, [rbp+var_28]
0x140006bd3  mov     rcx, rsi
0x140006bd6  mov     [rbx+348h], al
0x140006bdc  call    BalanceCompleteJob
0x140006be1  mov     rdx, [rsi+20h]
0x140006be5  mov     rdx, [rdx+8]
0x140006be9  lea     rcx, [rdx+340h]; SpinLock
0x140006bf0  mov     dl, [rdx+348h]; NewIrql
0x140006bf6  call    cs:__imp_KeReleaseSpinLock
0x140006bfd  nop     dword ptr [rax+rax+00h]
0x140006c02  mov     rcx, rsi; Entry
0x140006c05  call    SqospDestroyJob
0x140006c0a  xor     r8d, r8d; Context
0x140006c0d  mov     qword ptr [r14+20h], 0
0x140006c15  mov     rcx, r14; CallbackData
0x140006c18  mov     [r14+18h], r15d
0x140006c1c  lea     edx, [r8+4]; CallbackStatus
0x140006c20  call    cs:__imp_FltCompletePendedPreOperation
0x140006c27  nop     dword ptr [rax+rax+00h]
0x140006c2c  mov     r8, rdi
0x140006c2f  lea     rcx, [rbp+var_28]
0x140006c33  xor     edx, edx
0x140006c35  call    SqospProcessJobDispatcherContext
0x140006c3a  add     rsp, 48h
0x140006c3e  pop     r15
0x140006c40  pop     r14
0x140006c42  pop     rdi
0x140006c43  pop     rsi
0x140006c44  pop     rbx
0x140006c45  pop     rbp
0x140006c46  retn
```
