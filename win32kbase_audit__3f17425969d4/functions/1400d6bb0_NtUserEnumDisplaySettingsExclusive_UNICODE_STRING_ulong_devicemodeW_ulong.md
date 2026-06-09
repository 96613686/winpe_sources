# NtUserEnumDisplaySettingsExclusive(_UNICODE_STRING *,ulong,_devicemodeW *,ulong)

- ea: `0x1400d6bb0`
- end: `0x1400d6d07`
- name: `?NtUserEnumDisplaySettingsExclusive@@YAJPEAU_UNICODE_STRING@@KPEAU_devicemodeW@@K@Z`
- size: `343`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int64, struct _devicemodeW *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14017ac50`

## callees

- `0x140029850`
- `0x140029880`
- `0x140029a30`
- `0x140029bc0`
- `0x1400d6bb0`
- `0x1400d6d10`
- `0x1400d6f70`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400d6cdb`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6cdb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d6c93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d6c93`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400d6cf6`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x1400d6cf6`
- `ntoskrnl!ExReleaseFastResource` at `0x1400d6c87`
- `ntoskrnl!ExReleaseFastResource` at `0x1400d6c87`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d6c1d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d6c1d`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d6bc9`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d6bc9`
- `WIN32K!W32GetUserSessionState` at `0x1400d6bdf`
- `WIN32K!W32GetUserSessionState` at `0x1400d6c0e`
- `WIN32K!W32GetUserSessionState` at `0x1400d6bdf`
- `WIN32K!W32GetUserSessionState` at `0x1400d6c0e`

## pseudocode

```c
__int64 __fastcall NtUserEnumDisplaySettingsExclusive(
        struct _UNICODE_STRING *a1,
        __int64 a2,
        struct _devicemodeW *a3,
        bool a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // esi
  __int64 UserSessionState; // rdi
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax

  UserSessionSwitchEnterCrit();
  if ( *(_DWORD *)(W32GetUserGdiSessionState() + 32) )
  {
    W32GetUserSessionState(v7, v6);
    v8 = DrvEnumDisplaySettings(a1, a4);
  }
  else
  {
    v8 = -1073741823;
  }
  UserSessionState = W32GetUserSessionState(v7, v6);
  CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread();
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
  return v8;
}

```

## disassembly

```asm
0x1400d6bb0  push    rbx
0x1400d6bb2  push    rbp
0x1400d6bb3  push    rsi
0x1400d6bb4  push    rdi
0x1400d6bb5  sub     rsp, 38h
0x1400d6bb9  mov     ebx, r9d
0x1400d6bbc  mov     rdi, r8
0x1400d6bbf  mov     esi, edx
0x1400d6bc1  mov     rbp, rcx
0x1400d6bc4  call    UserSessionSwitchEnterCrit
0x1400d6bc9  call    cs:__imp_W32GetUserGdiSessionState
0x1400d6bd0  nop     dword ptr [rax+rax+00h]
0x1400d6bd5  cmp     dword ptr [rax+20h], 0
0x1400d6bd9  jz      loc_1400D6CBB
0x1400d6bdf  call    cs:__imp_W32GetUserSessionState
0x1400d6be6  nop     dword ptr [rax+rax+00h]
0x1400d6beb  mov     r9, rdi
0x1400d6bee  mov     dword ptr [rsp+58h+BugCheckParameter4], ebx; bool
0x1400d6bf2  mov     r8d, esi
0x1400d6bf5  mov     rcx, rbp; struct _UNICODE_STRING *
0x1400d6bf8  mov     r10, [rax+0DDA8h]
0x1400d6bff  mov     rdx, [r10+60h]
0x1400d6c03  mov     rdx, [rdx+50h]
0x1400d6c07  call    DrvEnumDisplaySettings
0x1400d6c0c  mov     esi, eax
0x1400d6c0e  call    cs:__imp_W32GetUserSessionState
0x1400d6c15  nop     dword ptr [rax+rax+00h]
0x1400d6c1a  mov     rdi, rax
0x1400d6c1d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400d6c24  nop     dword ptr [rax+rax+00h]
0x1400d6c29  mov     rbx, rax
0x1400d6c2c  mov     ecx, [rax+18h]
0x1400d6c2f  and     cl, 0Ch
0x1400d6c32  cmp     cl, 8
0x1400d6c35  jnz     short loc_1400D6C5F
0x1400d6c37  call    UpdateDirtyVisRgnTrackers
0x1400d6c3c  lea     rcx, [rdi+4C40h]
0x1400d6c43  mov     dword ptr [rcx+64h], 0
0x1400d6c4a  mov     qword ptr [rcx+50h], 0
0x1400d6c52  call    DestroyExclusiveUserCritDeferredUnlockList
0x1400d6c57  mov     qword ptr [rdi+10h], 0
0x1400d6c5f  mov     rcx, [rbx]
0x1400d6c62  test    rcx, rcx
0x1400d6c65  jnz     short loc_1400D6CAB
0x1400d6c67  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x1400d6c6c  test    eax, eax
0x1400d6c6e  jnz     short loc_1400D6CC5
0x1400d6c70  call    EtwTraceReleaseUserCrit
0x1400d6c75  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x1400d6c79  mov     eax, [rbx+18h]
0x1400d6c7c  test    al, 10h
0x1400d6c7e  jnz     short loc_1400D6CE8
0x1400d6c80  mov     rcx, [rdi]
0x1400d6c83  lea     rdx, [rbx+20h]
0x1400d6c87  call    cs:__imp_ExReleaseFastResource
0x1400d6c8e  nop     dword ptr [rax+rax+00h]
0x1400d6c93  call    cs:__imp_KeLeaveCriticalRegion
0x1400d6c9a  nop     dword ptr [rax+rax+00h]
0x1400d6c9f  mov     eax, esi
0x1400d6ca1  add     rsp, 38h
0x1400d6ca5  pop     rdi
0x1400d6ca6  pop     rsi
0x1400d6ca7  pop     rbp
0x1400d6ca8  pop     rbx
0x1400d6ca9  retn
0x1400d6cab  mov     eax, [rbx+18h]
0x1400d6cae  test    al, 2
0x1400d6cb0  jnz     short loc_1400D6C67
0x1400d6cb2  mov     byte ptr [rcx+6ACh], 0
0x1400d6cb9  jmp     short loc_1400D6C67
0x1400d6cbb  mov     esi, 0C0000001h
0x1400d6cc0  jmp     loc_1400D6C0E
0x1400d6cc5  mov     edx, eax; BugCheckParameter1
0x1400d6cc7  xor     r9d, r9d; BugCheckParameter3
0x1400d6cca  xor     r8d, r8d; BugCheckParameter2
0x1400d6ccd  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x1400d6cd6  mov     ecx, 160h; BugCheckCode
0x1400d6cdb  call    cs:__imp_KeBugCheckEx
0x1400d6ce8  mov     rcx, gs:188h
0x1400d6cf1  mov     r8, rbx
0x1400d6cf4  xor     edx, edx
0x1400d6cf6  call    cs:__imp_PsSetThreadWin32Thread
0x1400d6cfd  nop     dword ptr [rax+rax+00h]
0x1400d6d02  jmp     loc_1400D6C80
```
