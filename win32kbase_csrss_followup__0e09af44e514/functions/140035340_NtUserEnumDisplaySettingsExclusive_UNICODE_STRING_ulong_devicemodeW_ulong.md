# NtUserEnumDisplaySettingsExclusive(_UNICODE_STRING *,ulong,_devicemodeW *,ulong)

- ea: `0x140035340`
- end: `0x140035497`
- name: `?NtUserEnumDisplaySettingsExclusive@@YAJPEAU_UNICODE_STRING@@KPEAU_devicemodeW@@K@Z`
- size: `343`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned int, struct _devicemodeW *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140178c70`

## callees

- `0x14001bf30`
- `0x14001bf60`
- `0x14001c110`
- `0x14001c2a0`
- `0x140035340`
- `0x1400354a0`
- `0x140035700`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14003546b`
- `ntoskrnl!KeBugCheckEx` at `0x14003546b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140035423`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140035423`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140035486`
- `ntoskrnl!PsSetThreadWin32Thread` at `0x140035486`
- `ntoskrnl!ExReleaseFastResource` at `0x140035417`
- `ntoskrnl!ExReleaseFastResource` at `0x140035417`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400353ad`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400353ad`
- `WIN32K!W32GetUserGdiSessionState` at `0x140035359`
- `WIN32K!W32GetUserGdiSessionState` at `0x140035359`
- `WIN32K!W32GetUserSessionState` at `0x14003536f`
- `WIN32K!W32GetUserSessionState` at `0x14003539e`
- `WIN32K!W32GetUserSessionState` at `0x14003536f`
- `WIN32K!W32GetUserSessionState` at `0x14003539e`

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
  __int64 v8; // rcx
  unsigned int v9; // esi
  __int64 UserSessionState; // rdi
  __int64 v11; // rcx
  _DWORD *CurrentThreadWin32Thread; // rbx
  unsigned int Count; // eax

  UserSessionSwitchEnterCrit((__int64)a1);
  if ( *(_DWORD *)(W32GetUserGdiSessionState(v7, v6) + 32) )
  {
    W32GetUserSessionState(v8);
    v9 = DrvEnumDisplaySettings(a1, a4);
  }
  else
  {
    v9 = -1073741823;
  }
  UserSessionState = W32GetUserSessionState(v8);
  CurrentThreadWin32Thread = (_DWORD *)PsGetCurrentThreadWin32Thread(v11);
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
  return v9;
}

```

## disassembly

```asm
0x140035340  push    rbx
0x140035342  push    rbp
0x140035343  push    rsi
0x140035344  push    rdi
0x140035345  sub     rsp, 38h
0x140035349  mov     ebx, r9d
0x14003534c  mov     rdi, r8
0x14003534f  mov     esi, edx
0x140035351  mov     rbp, rcx
0x140035354  call    UserSessionSwitchEnterCrit
0x140035359  call    cs:__imp_W32GetUserGdiSessionState
0x140035360  nop     dword ptr [rax+rax+00h]
0x140035365  cmp     dword ptr [rax+20h], 0
0x140035369  jz      loc_14003544B
0x14003536f  call    cs:__imp_W32GetUserSessionState
0x140035376  nop     dword ptr [rax+rax+00h]
0x14003537b  mov     r9, rdi
0x14003537e  mov     dword ptr [rsp+58h+BugCheckParameter4], ebx; int
0x140035382  mov     r8d, esi
0x140035385  mov     rcx, rbp; struct _UNICODE_STRING *
0x140035388  mov     r10, [rax+0DDA8h]
0x14003538f  mov     rdx, [r10+60h]
0x140035393  mov     rdx, [rdx+50h]
0x140035397  call    DrvEnumDisplaySettings
0x14003539c  mov     esi, eax
0x14003539e  call    cs:__imp_W32GetUserSessionState
0x1400353a5  nop     dword ptr [rax+rax+00h]
0x1400353aa  mov     rdi, rax
0x1400353ad  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400353b4  nop     dword ptr [rax+rax+00h]
0x1400353b9  mov     rbx, rax
0x1400353bc  mov     ecx, [rax+18h]
0x1400353bf  and     cl, 0Ch
0x1400353c2  cmp     cl, 8
0x1400353c5  jnz     short loc_1400353EF
0x1400353c7  call    UpdateDirtyVisRgnTrackers
0x1400353cc  lea     rcx, [rdi+4C40h]
0x1400353d3  mov     dword ptr [rcx+64h], 0
0x1400353da  mov     qword ptr [rcx+50h], 0
0x1400353e2  call    DestroyExclusiveUserCritDeferredUnlockList
0x1400353e7  mov     qword ptr [rdi+10h], 0
0x1400353ef  mov     rcx, [rbx]
0x1400353f2  test    rcx, rcx
0x1400353f5  jnz     short loc_14003543B
0x1400353f7  call    ?GetCount@AtomicExecutionCheck@@SAIXZ; AtomicExecutionCheck::GetCount(void)
0x1400353fc  test    eax, eax
0x1400353fe  jnz     short loc_140035455
0x140035400  call    EtwTraceReleaseUserCrit
0x140035405  and     dword ptr [rbx+18h], 0FFFFFFF1h
0x140035409  mov     eax, [rbx+18h]
0x14003540c  test    al, 10h
0x14003540e  jnz     short loc_140035478
0x140035410  mov     rcx, [rdi]
0x140035413  lea     rdx, [rbx+20h]
0x140035417  call    cs:__imp_ExReleaseFastResource
0x14003541e  nop     dword ptr [rax+rax+00h]
0x140035423  call    cs:__imp_KeLeaveCriticalRegion
0x14003542a  nop     dword ptr [rax+rax+00h]
0x14003542f  mov     eax, esi
0x140035431  add     rsp, 38h
0x140035435  pop     rdi
0x140035436  pop     rsi
0x140035437  pop     rbp
0x140035438  pop     rbx
0x140035439  retn
0x14003543b  mov     eax, [rbx+18h]
0x14003543e  test    al, 2
0x140035440  jnz     short loc_1400353F7
0x140035442  mov     byte ptr [rcx+6ACh], 0
0x140035449  jmp     short loc_1400353F7
0x14003544b  mov     esi, 0C0000001h
0x140035450  jmp     loc_14003539E
0x140035455  mov     edx, eax; BugCheckParameter1
0x140035457  xor     r9d, r9d; BugCheckParameter3
0x14003545a  xor     r8d, r8d; BugCheckParameter2
0x14003545d  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x140035466  mov     ecx, 160h; BugCheckCode
0x14003546b  call    cs:__imp_KeBugCheckEx
0x140035478  mov     rcx, gs:188h
0x140035481  mov     r8, rbx
0x140035484  xor     edx, edx
0x140035486  call    cs:__imp_PsSetThreadWin32Thread
0x14003548d  nop     dword ptr [rax+rax+00h]
0x140035492  jmp     loc_140035410
```
