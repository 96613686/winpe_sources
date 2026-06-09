# WwanNhIntfDeinit(_GUID *)

- ea: `0x180017290`
- end: `0x180017368`
- name: `?WwanNhIntfDeinit@@YAXPEAU_GUID@@@Z`
- size: `216`
- prototype: `void __fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001796c`
- `0x18008b9f0`
- `0x18008d968`

## callees

- `0x180014f1c`
- `0x180017290`
- `0x1800191c8`
- `0x18001926c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017323`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017323`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001734d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001734d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800172f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800172f5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800172b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017301`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800172b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800172a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800172a7`

## string_xrefs

- `0x1800172c0`: `signalled notification thread %x to exit`
- `0x1800172d9`: `waiting for notification thread %x to exit`
- `0x180017307`: `signaled but not waiting for notification thread as it is current thread`

## pseudocode

```c
void __fastcall WwanNhIntfDeinit(struct _GUID *a1)
{
  __int64 v1; // rbx
  __int64 v2; // r8
  _QWORD *v3; // rdx

  v1 = selectNhIfInfo(a1);
  if ( v1 )
  {
    if ( *(_DWORD *)(v1 + 112) == GetCurrentThreadId() )
    {
      SetEvent(*(HANDLE *)(v1 + 120));
      WwanLog::Info("WwanNhIntfDeinit", 0, L"signaled but not waiting for notification thread as it is current thread");
    }
    else
    {
      SetEvent(*(HANDLE *)(v1 + 72));
      WwanLog::Info("WwanNhIntfDeinit", 0, L"signalled notification thread %x to exit", *(unsigned int *)(v1 + 112));
      WwanLog::Info("WwanNhIntfDeinit", 0, L"waiting for notification thread %x to exit", *(unsigned int *)(v1 + 112));
      WaitForSingleObject(*(HANDLE *)(v1 + 88), 0xFFFFFFFF);
    }
    EnterCriticalSection(&stru_180152910);
    v2 = *(_QWORD *)(v1 + 56);
    if ( *(_QWORD *)(v2 + 8) != v1 + 56 || (v3 = *(_QWORD **)(v1 + 64), *v3 != v1 + 56) )
      __fastfail(3u);
    *v3 = v2;
    *(_QWORD *)(v2 + 8) = v3;
    LeaveCriticalSection(&stru_180152910);
    flushIfInfo((LPCRITICAL_SECTION)v1);
  }
}

```

## disassembly

```asm
0x180017290  push    rbx
0x180017292  sub     rsp, 20h
0x180017296  call    _selectNhIfInfo
0x18001729b  mov     rbx, rax
0x18001729e  test    rax, rax
0x1800172a1  jz      loc_18001735B
0x1800172a7  call    cs:__imp_GetCurrentThreadId
0x1800172ad  cmp     [rbx+70h], eax
0x1800172b0  jz      short loc_1800172FD
0x1800172b2  mov     rcx, [rbx+48h]; hEvent
0x1800172b6  call    cs:__imp_SetEvent
0x1800172bc  mov     r9d, [rbx+70h]
0x1800172c0  lea     r8, aSignalledNotif; "signalled notification thread %x to exi"...
0x1800172c7  xor     edx, edx; struct _GUID *
0x1800172c9  lea     rcx, aWwannhintfdein; "WwanNhIntfDeinit"
0x1800172d0  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800172d5  mov     r9d, [rbx+70h]
0x1800172d9  lea     r8, aWaitingForNoti; "waiting for notification thread %x to e"...
0x1800172e0  xor     edx, edx; struct _GUID *
0x1800172e2  lea     rcx, aWwannhintfdein; "WwanNhIntfDeinit"
0x1800172e9  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800172ee  mov     rcx, [rbx+58h]; hHandle
0x1800172f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800172f5  call    cs:__imp_WaitForSingleObject
0x1800172fb  jmp     short loc_18001731C
0x1800172fd  mov     rcx, [rbx+78h]; hEvent
0x180017301  call    cs:__imp_SetEvent
0x180017307  lea     r8, aSignaledButNot; "signaled but not waiting for notificati"...
0x18001730e  xor     edx, edx; struct _GUID *
0x180017310  lea     rcx, aWwannhintfdein; "WwanNhIntfDeinit"
0x180017317  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18001731c  lea     rcx, stru_180152910; lpCriticalSection
0x180017323  call    cs:__imp_EnterCriticalSection
0x180017329  lea     rax, [rbx+38h]
0x18001732d  mov     r8, [rax]
0x180017330  cmp     [r8+8], rax
0x180017334  jnz     short loc_180017361
0x180017336  mov     rdx, [rax+8]
0x18001733a  cmp     [rdx], rax
0x18001733d  jnz     short loc_180017361
0x18001733f  mov     [rdx], r8
0x180017342  lea     rcx, stru_180152910; lpCriticalSection
0x180017349  mov     [r8+8], rdx
0x18001734d  call    cs:__imp_LeaveCriticalSection
0x180017353  mov     rcx, rbx; lpCriticalSection
0x180017356  call    _flushIfInfo
0x18001735b  add     rsp, 20h
0x18001735f  pop     rbx
0x180017360  retn
0x180017361  mov     ecx, 3
0x180017366  int     29h; Win8: RtlFailFast(ecx)
```
