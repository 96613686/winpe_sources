# NtUserEnumDisplaySettingsExclusive(_UNICODE_STRING *,ulong,_devicemodeW *,ulong)

- ea: `0x14002c0c0`
- end: `0x14002c217`
- name: `?NtUserEnumDisplaySettingsExclusive@@YAJPEAU_UNICODE_STRING@@KPEAU_devicemodeW@@K@Z`
- size: `343`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned int, struct _devicemodeW *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140178100`

## callees

- `0x140012dc0`
- `0x140012df0`
- `0x140012fa0`
- `0x140013130`
- `0x14002c0c0`
- `0x14002c220`
- `0x14002c480`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14002c1eb`
- `ntoskrnl!KeBugCheckEx` at `0x14002c1eb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c1a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002c1a3`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14002c206`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x14002c206`
- `ntoskrnl!ExReleaseFastResource` at `0x14002c197`
- `ntoskrnl!ExReleaseFastResource` at `0x14002c197`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002c12d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14002c12d`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002c0d9`
- `WIN32K!W32GetUserGdiSessionState` at `0x14002c0d9`
- `WIN32K!W32GetUserSessionState` at `0x14002c0ef`
- `WIN32K!W32GetUserSessionState` at `0x14002c11e`
- `WIN32K!W32GetUserSessionState` at `0x14002c0ef`
- `WIN32K!W32GetUserSessionState` at `0x14002c11e`

## pseudocode

```c
__int64 __fastcall NtUserEnumDisplaySettingsExclusive(
        struct _UNICODE_STRING *a1,
        __int64 a2,
        struct _devicemodeW *a3,
        int a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int v11; // esi
  __int64 UserSessionState; // rdi
  __int64 v13; // rcx
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax

  UserSessionSwitchEnterCrit((__int64)a1, a2, (__int64)a3);
  if ( *(_DWORD *)(W32GetUserGdiSessionState(v7, v6) + 32) )
  {
    W32GetUserSessionState(v9, v8, v10);
    v11 = DrvEnumDisplaySettings(a1, a4);
  }
  else
  {
    v11 = -1073741823;
  }
  UserSessionState = W32GetUserSessionState(v9, v8, v10);
  CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread(v13);
  if ( (CurrentThreadWin32Thread[6] & 0xC) == 8 )
  {
    UpdateDirtyVisRgnTrackers();
    *(_DWORD *)(UserSessionState + 19620) = 0;
    *(_QWORD *)(UserSessionState + 19600) = 0;
    DestroyExclusiveUserCritDeferredUnlockList();
    *(_QWORD *)(UserSessionState + 16) = 0;
  }
  if ( *(_QWORD *)CurrentThreadWin32Thread && (CurrentThreadWin32Thread[6] & 2) == 0 )
    *(_BYTE *)(*(_QWORD *)CurrentThreadWin32Thread + 1708LL) = 0;
  Count = AtomicExecutionCheck::GetCount();
  if ( Count )
    KeBugCheckEx(0x160u, Count, 0, 0, 0);
  EtwTraceReleaseUserCrit();
  CurrentThreadWin32Thread[6] &= 0xFFFFFFF1;
  if ( (CurrentThreadWin32Thread[6] & 0x10) != 0 )
    PsSetThreadWin32Thread(KeGetCurrentThread(), 0, CurrentThreadWin32Thread);
  ExReleaseFastResource(*(_QWORD *)UserSessionState, CurrentThreadWin32Thread + 8);
  KeLeaveCriticalRegion();
  return v11;
}

```

## disassembly

```asm
0x14002c0c0  push    rbx
0x14002c0c2  push    rbp
0x14002c0c3  push    rsi
0x14002c0c4  push    rdi
0x14002c0c5  sub     rsp, 38h
0x14002c0c9  mov     ebx, r9d
0x14002c0cc  mov     rdi, r8
0x14002c0cf  mov     esi, edx
0x14002c0d1  mov     rbp, rcx
0x14002c0d4  call    UserSessionSwitchEnterCrit
0x14002c0d9  call    cs:__imp_W32GetUserGdiSessionState
0x14002c0e0  nop     dword ptr [rax+rax+00h]
0x14002c0e5  cmp     dword ptr [rax+20h], 0
0x14002c0e9  jz      loc_14002C1CB
0x14002c0ef  call    cs:__imp_W32GetUserSessionState
0x14002c0f6  nop     dword ptr [rax+rax+00h]
0x14002c0fb  mov     r9, rdi
0x14002c0fe  mov     dword ptr [rsp+58h+BugCheckParameter4], ebx; int
0x14002c102  mov     r8d, esi
0x14002c105  mov     rcx, rbp; struct _UNICODE_STRING *
0x14002c108  mov     r10, [rax+0DDA8h]
0x14002c10f  mov     rdx, [r10+60h]
0x14002c113  mov     rdx, [rdx+50h]
0x14002c117  call    DrvEnumDisplaySettings
0x14002c11c  mov     esi, eax
0x14002c11e  call    cs:__imp_W32GetUserSessionState
0x14002c125  nop     dword ptr [rax+rax+00h]
0x14002c12a  mov     rdi, rax
0x14002c12d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14002c134  nop     dword ptr [rax+rax+00h]
0x14002c139  mov     rbx, rax
0x14002c13c  mov     ecx, [rax+18h]
0x14002c13f  and     cl, 0Ch
0x14002c142  cmp     cl, 8
0x14002c145  jnz     short loc_14002C16F
0x14002c147  call    UpdateDirtyVisRgnTrackers
0x14002c14c  lea     rcx, [rdi+4C40h]
0x14002c153  mov     dword ptr [rcx+64h], 0
0x14002c15a  mov     qword ptr [rcx+50h], 0
0x14002c162  call    DestroyExclusiveUserCritDeferredUnlockList
0x14002c167  mov     qword ptr [rdi+10h], 0
0x14002c16f  mov     rcx, [rbx]
0x14002c172  test    rcx, rcx
0x14002c175  jnz     short loc_14002C1BB
0x14002c177  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x14002c17c  test    eax, eax
0x14002c17e  jnz     short loc_14002C1D5
0x14002c180  call    EtwTraceReleaseUserCrit
0x14002c185  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x14002c189  mov     eax, [rbx+18h]
0x14002c18c  test    al, 10h
0x14002c18e  jnz     short loc_14002C1F8
0x14002c190  mov     rcx, [rdi]
0x14002c193  lea     rdx, [rbx+20h]
0x14002c197  call    cs:__imp_ExReleaseFastResource
0x14002c19e  nop     dword ptr [rax+rax+00h]
0x14002c1a3  call    cs:__imp_KeLeaveCriticalRegion
0x14002c1aa  nop     dword ptr [rax+rax+00h]
0x14002c1af  mov     eax, esi
0x14002c1b1  add     rsp, 38h
0x14002c1b5  pop     rdi
0x14002c1b6  pop     rsi
0x14002c1b7  pop     rbp
0x14002c1b8  pop     rbx
0x14002c1b9  retn
0x14002c1bb  mov     eax, [rbx+18h]
0x14002c1be  test    al, 2
0x14002c1c0  jnz     short loc_14002C177
0x14002c1c2  mov     byte ptr [rcx+6ACh], 0
0x14002c1c9  jmp     short loc_14002C177
0x14002c1cb  mov     esi, 0C0000001h
0x14002c1d0  jmp     loc_14002C11E
0x14002c1d5  mov     edx, eax; BugCheckParameter1
0x14002c1d7  xor     r9d, r9d; BugCheckParameter3
0x14002c1da  xor     r8d, r8d; BugCheckParameter2
0x14002c1dd  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x14002c1e6  mov     ecx, 160h; BugCheckCode
0x14002c1eb  call    cs:__imp_KeBugCheckEx
0x14002c1f8  mov     rcx, gs:188h
0x14002c201  mov     r8, rbx
0x14002c204  xor     edx, edx
0x14002c206  call    cs:__imp_PsSetThreadWin32Thread
0x14002c20d  nop     dword ptr [rax+rax+00h]
0x14002c212  jmp     loc_14002C190
```
