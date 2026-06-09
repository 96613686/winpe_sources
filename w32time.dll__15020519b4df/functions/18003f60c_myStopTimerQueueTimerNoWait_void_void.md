# myStopTimerQueueTimerNoWait(void *,void *)

- ea: `0x18003f60c`
- end: `0x18003f6a5`
- name: `?myStopTimerQueueTimerNoWait@@YAJPEAX0@Z`
- size: `153`
- prototype: `int(void *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010748`

## callees

- `0x18003f60c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f68b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f68b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f61c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f61c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f648`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003f638`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003f638`

## pseudocode

```c
__int64 __fastcall myStopTimerQueueTimerNoWait(void *a1, struct _RTL_CRITICAL_SECTION *a2)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  signed int v4; // ebx
  signed int LastError; // eax

  EnterCriticalSection(a2);
  DebugInfo = a2[1].DebugInfo;
  if ( !DebugInfo )
    goto LABEL_9;
  v4 = 0;
  if ( DeleteTimerQueueTimer(0, DebugInfo, 0) )
    goto LABEL_7;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147023899 )
LABEL_7:
    a2[1].DebugInfo = 0;
  a2[1].LockCount = v4;
  if ( v4 >= 0 )
LABEL_9:
    v4 = 0;
  LeaveCriticalSection(a2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003f60c  mov     [rsp+arg_0], rbx
0x18003f611  push    rdi
0x18003f612  sub     rsp, 20h
0x18003f616  mov     rcx, rdx; lpCriticalSection
0x18003f619  mov     rdi, rdx
0x18003f61c  call    cs:__imp_EnterCriticalSection
0x18003f623  nop     dword ptr [rax+rax+00h]
0x18003f628  mov     rdx, [rdi+28h]; Timer
0x18003f62c  test    rdx, rdx
0x18003f62f  jz      short loc_18003F686
0x18003f631  xor     r8d, r8d; CompletionEvent
0x18003f634  xor     ecx, ecx; TimerQueue
0x18003f636  xor     ebx, ebx
0x18003f638  call    cs:__imp_DeleteTimerQueueTimer
0x18003f63f  nop     dword ptr [rax+rax+00h]
0x18003f644  test    eax, eax
0x18003f646  jnz     short loc_18003F677
0x18003f648  call    cs:__imp_GetLastError
0x18003f64f  nop     dword ptr [rax+rax+00h]
0x18003f654  mov     ebx, eax
0x18003f656  test    eax, eax
0x18003f658  jle     short loc_18003F663
0x18003f65a  movzx   ebx, ax
0x18003f65d  or      ebx, 80070000h
0x18003f663  mov     ecx, 80000000h
0x18003f668  lea     eax, [rbx+rcx]
0x18003f66b  test    ecx, eax
0x18003f66d  jnz     short loc_18003F677
0x18003f66f  cmp     ebx, 800703E5h
0x18003f675  jnz     short loc_18003F67F
0x18003f677  mov     qword ptr [rdi+28h], 0
0x18003f67f  mov     [rdi+30h], ebx
0x18003f682  test    ebx, ebx
0x18003f684  js      short loc_18003F688
0x18003f686  xor     ebx, ebx
0x18003f688  mov     rcx, rdi; lpCriticalSection
0x18003f68b  call    cs:__imp_LeaveCriticalSection
0x18003f692  nop     dword ptr [rax+rax+00h]
0x18003f697  mov     eax, ebx
0x18003f699  mov     rbx, [rsp+28h+arg_0]
0x18003f69e  add     rsp, 20h
0x18003f6a2  pop     rdi
0x18003f6a3  retn
```
