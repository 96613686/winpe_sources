# CSecureProcessDump::Cleanup(void)

- ea: `0x1400060a4`
- end: `0x14000617e`
- name: `?Cleanup@CSecureProcessDump@@QEAAXXZ`
- size: `218`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140006038`
- `0x14000628c`
- `0x1400068c0`

## callees

- `0x1400060a4`
- `0x14000e820`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000614e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006161`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000614e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400060b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400060b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000611a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000611a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400060c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000612d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400060c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14000612d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14000613b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x14000613b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000616f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000616f`

## pseudocode

```c
void __fastcall CSecureProcessDump::Cleanup(LPCRITICAL_SECTION lpCriticalSection)
{
  struct _TP_WAIT *SpinCount; // rcx
  struct _TP_WAIT *v3; // rdi
  HANDLE LockSemaphore; // rsi
  HANDLE OwningThread; // rbp

  EnterCriticalSection(lpCriticalSection);
  SpinCount = (struct _TP_WAIT *)lpCriticalSection[62].SpinCount;
  if ( SpinCount )
    SetThreadpoolWait(SpinCount, 0, 0);
  v3 = (struct _TP_WAIT *)lpCriticalSection[62].SpinCount;
  LockSemaphore = lpCriticalSection[62].LockSemaphore;
  OwningThread = lpCriticalSection[62].OwningThread;
  lpCriticalSection[62].SpinCount = 0;
  lpCriticalSection[62].LockSemaphore = 0;
  lpCriticalSection[62].OwningThread = 0;
  lpCriticalSection[62].DebugInfo = 0;
  CDumpCollection::Cleanup((CDumpCollection *)&lpCriticalSection[1].LockCount);
  LeaveCriticalSection(lpCriticalSection);
  if ( v3 )
  {
    SetThreadpoolWait(v3, 0, 0);
    WaitForThreadpoolWaitCallbacks(v3, 1);
  }
  if ( (unsigned __int64)OwningThread + 1 > 1 )
    CloseHandle(OwningThread);
  if ( (unsigned __int64)LockSemaphore + 1 > 1 )
    CloseHandle(LockSemaphore);
  if ( v3 )
    CloseThreadpoolWait(v3);
}

```

## disassembly

```asm
0x1400060a4  push    rbx
0x1400060a6  push    rbp
0x1400060a7  push    rsi
0x1400060a8  push    rdi
0x1400060a9  sub     rsp, 28h
0x1400060ad  mov     rbx, rcx
0x1400060b0  call    cs:__imp_EnterCriticalSection
0x1400060b6  mov     rcx, [rbx+9D0h]; pwa
0x1400060bd  test    rcx, rcx
0x1400060c0  jz      short loc_1400060CD
0x1400060c2  xor     r8d, r8d; pftTimeout
0x1400060c5  xor     edx, edx; h
0x1400060c7  call    cs:__imp_SetThreadpoolWait
0x1400060cd  mov     rdi, [rbx+9D0h]
0x1400060d4  lea     rcx, [rbx+30h]; this
0x1400060d8  mov     rsi, [rbx+9C8h]
0x1400060df  mov     rbp, [rbx+9C0h]
0x1400060e6  mov     qword ptr [rbx+9D0h], 0
0x1400060f1  mov     qword ptr [rbx+9C8h], 0
0x1400060fc  mov     qword ptr [rbx+9C0h], 0
0x140006107  mov     qword ptr [rbx+9B0h], 0
0x140006112  call    ?Cleanup@CDumpCollection@@QEAAXXZ; CDumpCollection::Cleanup(void)
0x140006117  mov     rcx, rbx; lpCriticalSection
0x14000611a  call    cs:__imp_LeaveCriticalSection
0x140006120  test    rdi, rdi
0x140006123  jz      short loc_140006141
0x140006125  xor     r8d, r8d; pftTimeout
0x140006128  xor     edx, edx; h
0x14000612a  mov     rcx, rdi; pwa
0x14000612d  call    cs:__imp_SetThreadpoolWait
0x140006133  mov     edx, 1; fCancelPendingCallbacks
0x140006138  mov     rcx, rdi; pwa
0x14000613b  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x140006141  lea     rax, [rbp+1]
0x140006145  cmp     rax, 1
0x140006149  jbe     short loc_140006154
0x14000614b  mov     rcx, rbp; hObject
0x14000614e  call    cs:__imp_CloseHandle
0x140006154  lea     rax, [rsi+1]
0x140006158  cmp     rax, 1
0x14000615c  jbe     short loc_140006167
0x14000615e  mov     rcx, rsi; hObject
0x140006161  call    cs:__imp_CloseHandle
0x140006167  test    rdi, rdi
0x14000616a  jz      short loc_140006175
0x14000616c  mov     rcx, rdi; pwa
0x14000616f  call    cs:__imp_CloseThreadpoolWait
0x140006175  add     rsp, 28h
0x140006179  pop     rdi
0x14000617a  pop     rsi
0x14000617b  pop     rbp
0x14000617c  pop     rbx
0x14000617d  retn
```
