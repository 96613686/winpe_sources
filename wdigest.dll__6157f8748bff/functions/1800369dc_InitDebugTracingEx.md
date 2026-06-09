# _InitDebugTracingEx

- ea: `0x1800369dc`
- end: `0x180036b5d`
- name: `_InitDebugTracingEx`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180026520`

## callees

- `0x180035d38`
- `0x180035fc8`
- `0x180036360`
- `0x180036570`
- `0x1800369dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036b23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036b23`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180036a97`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180036a97`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180036ad3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180036ad3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x180036b12`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x180036b12`

## pseudocode

```c
void __fastcall InitDebugTracingEx(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        const unsigned __int16 *a4)
{
  struct _RTL_CRITICAL_SECTION *SharedMem; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  struct _DBG_TRACE_CONTROL_BLOCK **v6; // rcx
  struct _DBG_TRACE_CONTROL_BLOCK *v7; // rdi
  int SpinCount; // edx
  unsigned int OwningThread_high; // esi
  struct _DBG_TRACE_CONTROL_BLOCK *v10; // rcx
  const unsigned __int16 *DueTime; // [rsp+20h] [rbp-48h]
  DWORD Period; // [rsp+28h] [rbp-40h]
  struct _DBG_TRACE_CONTROL_BLOCK *v13; // [rsp+88h] [rbp+20h] BYREF

  v13 = 0;
  if ( (NtCurrentPeb()->BitField & 2) != 0 )
  {
    DigestGlobalTraceControlBlock = 0;
    return;
  }
  if ( (((unsigned __int64)DigestGlobalTraceControlBlock + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    if ( !_DbgpCreateTraceControl(a1, a2, a3, a4, DueTime, Period, &v13)
      || (SharedMem = (struct _RTL_CRITICAL_SECTION *)_DbgpOpenOrCreateSharedMem(), (v5 = SharedMem) == 0) )
    {
      v10 = v13;
LABEL_19:
      if ( v10 )
        _DbgpDeleteTraceControl(v10);
      return;
    }
    EnterCriticalSection(SharedMem + 2);
    v6 = *(struct _DBG_TRACE_CONTROL_BLOCK ***)&v5[1].LockCount;
    if ( *v6 != (struct _DBG_TRACE_CONTROL_BLOCK *)&v5[1] )
      __fastfail(3u);
    v7 = v13;
    *(_QWORD *)v13 = v5 + 1;
    *((_QWORD *)v7 + 1) = v6;
    *v6 = v7;
    *(_QWORD *)&v5[1].LockCount = v7;
    ++LODWORD(v5->SpinCount);
    if ( !v5[1].LockSemaphore )
    {
      if ( LOBYTE(v5[1].OwningThread) || IsDebuggerPresent() )
      {
        HIDWORD(v5[1].OwningThread) = 60;
        if ( CreateTimerQueueTimer(
               (PHANDLE)&v5[1].SpinCount,
               0,
               _DbgpTraceControllerTimerCallback,
               v5,
               0x2BF20u,
               0xEA60u,
               0) )
        {
          v5[1].LockSemaphore = _DbgpTraceControllerTimerCallback;
        }
        goto LABEL_17;
      }
      if ( !v5[1].LockSemaphore )
      {
LABEL_17:
        LeaveCriticalSection(v5 + 2);
        _DbgpRegistryChangeNotifycationCallback(*((void **)v7 + 29), 1u);
        v10 = 0;
        DigestGlobalTraceControlBlock = v7;
        goto LABEL_19;
      }
    }
    SpinCount = v5->SpinCount;
    OwningThread_high = HIDWORD(v5[1].OwningThread);
    if ( OwningThread_high < 10 * SpinCount )
    {
      HIDWORD(v5[1].OwningThread) = 10 * SpinCount + 60;
      if ( !ChangeTimerQueueTimer(0, (HANDLE)v5[1].SpinCount, 10000 * (SpinCount + 6), 10000 * (SpinCount + 6)) )
        HIDWORD(v5[1].OwningThread) = OwningThread_high;
    }
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1800369dc  mov     rax, rsp
0x1800369df  mov     [rax+20h], r9
0x1800369e3  push    rbx
0x1800369e4  push    rbp
0x1800369e5  push    rsi
0x1800369e6  push    rdi
0x1800369e7  sub     rsp, 48h
0x1800369eb  mov     qword ptr [rax+20h], 0
0x1800369f3  mov     rax, gs:60h
0x1800369fc  test    byte ptr [rax+3], 2
0x180036a00  jz      short loc_180036A12
0x180036a02  mov     cs:DigestGlobalTraceControlBlock, 0
0x180036a0d  jmp     loc_180036B54
0x180036a12  mov     rax, cs:DigestGlobalTraceControlBlock
0x180036a19  inc     rax
0x180036a1c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180036a22  jnz     loc_180036B54
0x180036a28  lea     rax, [rsp+68h+arg_18]
0x180036a30  mov     qword ptr [rsp+68h+Flags], rax; struct _DBG_TRACE_CONTROL_BLOCK **
0x180036a35  call    ?_DbgpCreateTraceControl@@YAHPEBG0PEAU_GUID@@00HPEAPEAU_DBG_TRACE_CONTROL_BLOCK@@@Z; _DbgpCreateTraceControl(ushort const *,ushort const *,_GUID *,ushort const *,ushort const *,int,_DBG_TRACE_CONTROL_BLOCK * *)
0x180036a3a  test    eax, eax
0x180036a3c  jz      loc_180036B42
0x180036a42  call    ?_DbgpOpenOrCreateSharedMem@@YAPEAU_DBG_TCB_HEADER@@XZ; _DbgpOpenOrCreateSharedMem(void)
0x180036a47  mov     rbx, rax
0x180036a4a  test    rax, rax
0x180036a4d  jz      loc_180036B42
0x180036a53  lea     rcx, [rax+50h]; lpCriticalSection
0x180036a57  call    cs:__imp_EnterCriticalSection
0x180036a5d  lea     rax, [rbx+28h]
0x180036a61  mov     rcx, [rax+8]
0x180036a65  cmp     [rcx], rax
0x180036a68  jz      short loc_180036A71
0x180036a6a  mov     ecx, 3
0x180036a6f  int     29h; Win8: RtlFailFast(ecx)
0x180036a71  mov     rdi, [rsp+68h+arg_18]
0x180036a79  mov     [rdi], rax
0x180036a7c  mov     [rdi+8], rcx
0x180036a80  mov     [rcx], rdi
0x180036a83  mov     [rax+8], rdi
0x180036a87  inc     dword ptr [rbx+20h]
0x180036a8a  cmp     qword ptr [rbx+40h], 0
0x180036a8f  jnz     short loc_180036AEA
0x180036a91  cmp     byte ptr [rbx+38h], 0
0x180036a95  jnz     short loc_180036AA1
0x180036a97  call    cs:__imp_IsDebuggerPresent
0x180036a9d  test    eax, eax
0x180036a9f  jz      short loc_180036AE3
0x180036aa1  mov     [rsp+68h+Flags], 0; Flags
0x180036aa9  lea     rsi, ?_DbgpTraceControllerTimerCallback@@YAXPEAXE@Z; _DbgpTraceControllerTimerCallback(void *,uchar)
0x180036ab0  mov     r8, rsi; Callback
0x180036ab3  mov     [rsp+68h+Period], 0EA60h; Period
0x180036abb  lea     rcx, [rbx+48h]; phNewTimer
0x180036abf  mov     dword ptr [rbx+3Ch], 3Ch ; '<'
0x180036ac6  mov     r9, rbx; Parameter
0x180036ac9  mov     dword ptr [rsp+68h+DueTime], 2BF20h; DueTime
0x180036ad1  xor     edx, edx; TimerQueue
0x180036ad3  call    cs:__imp_CreateTimerQueueTimer
0x180036ad9  test    eax, eax
0x180036adb  jz      short loc_180036B1F
0x180036add  mov     [rbx+40h], rsi
0x180036ae1  jmp     short loc_180036B1F
0x180036ae3  cmp     qword ptr [rbx+40h], 0
0x180036ae8  jz      short loc_180036B1F
0x180036aea  mov     edx, [rbx+20h]
0x180036aed  mov     esi, [rbx+3Ch]
0x180036af0  lea     eax, [rdx+rdx*4]
0x180036af3  add     eax, eax
0x180036af5  cmp     esi, eax
0x180036af7  jnb     short loc_180036B1F
0x180036af9  add     eax, 3Ch ; '<'
0x180036afc  xor     ecx, ecx; TimerQueue
0x180036afe  mov     [rbx+3Ch], eax
0x180036b01  lea     eax, [rdx+6]
0x180036b04  mov     rdx, [rbx+48h]; Timer
0x180036b08  imul    r8d, eax, 2710h; DueTime
0x180036b0f  mov     r9d, r8d; Period
0x180036b12  call    cs:__imp_ChangeTimerQueueTimer
0x180036b18  test    eax, eax
0x180036b1a  jnz     short loc_180036B1F
0x180036b1c  mov     [rbx+3Ch], esi
0x180036b1f  lea     rcx, [rbx+50h]; lpCriticalSection
0x180036b23  call    cs:__imp_LeaveCriticalSection
0x180036b29  mov     rcx, [rdi+0E8h]; void *
0x180036b30  mov     dl, 1; unsigned __int8
0x180036b32  call    ?_DbgpRegistryChangeNotifycationCallback@@YAXPEAXE@Z; _DbgpRegistryChangeNotifycationCallback(void *,uchar)
0x180036b37  xor     ecx, ecx
0x180036b39  mov     cs:DigestGlobalTraceControlBlock, rdi
0x180036b40  jmp     short loc_180036B4A
0x180036b42  mov     rcx, [rsp+68h+arg_18]; struct _DBG_TRACE_CONTROL_BLOCK *
0x180036b4a  test    rcx, rcx
0x180036b4d  jz      short loc_180036B54
0x180036b4f  call    ?_DbgpDeleteTraceControl@@YAXPEAU_DBG_TRACE_CONTROL_BLOCK@@@Z; _DbgpDeleteTraceControl(_DBG_TRACE_CONTROL_BLOCK *)
0x180036b54  add     rsp, 48h
0x180036b58  pop     rdi
0x180036b59  pop     rsi
0x180036b5a  pop     rbp
0x180036b5b  pop     rbx
0x180036b5c  retn
```
