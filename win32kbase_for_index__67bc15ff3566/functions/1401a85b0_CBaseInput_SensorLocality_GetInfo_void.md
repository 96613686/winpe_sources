# CBaseInput::SensorLocality::GetInfo(void)

- ea: `0x1401a85b0`
- end: `0x1401a8675`
- name: `?GetInfo@SensorLocality@CBaseInput@@QEBA?AW4SensorLocalityInfo@@XZ`
- size: `197`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140194e20`
- `0x1401a84a0`
- `0x1401a8590`
- `0x1402119fc`

## callees

- `0x1401a85b0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1401a8627`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401a8627`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a85bd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a85bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a865b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a865b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a85ce`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a85ce`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401a864f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401a864f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401a85fe`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401a85fe`
- `ntoskrnl!PsGetProcessId` at `0x1401a8636`
- `ntoskrnl!PsGetProcessId` at `0x1401a8636`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1401a85e4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1401a85e4`
- `ntoskrnl!KeIsAttachedProcess` at `0x1401a8617`
- `ntoskrnl!KeIsAttachedProcess` at `0x1401a8617`

## pseudocode

```c
__int64 __fastcall CBaseInput::SensorLocality::GetInfo(__int64 a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  struct _KPROCESS *CurrentProcess; // rax

  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  if ( *(_DWORD *)(a1 + 12) )
  {
    v2 = 5;
    if ( (unsigned int)PsGetCurrentThreadId() != *(_DWORD *)(a1 + 12) )
      v2 = 1;
    if ( ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) == *(_DWORD *)(a1 + 8) )
    {
      v2 |= 2u;
    }
    else if ( (unsigned __int8)KeIsAttachedProcess(v4, v3) )
    {
      CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v6, v5, v7);
      if ( *(_DWORD *)(a1 + 8) == (unsigned int)PsGetProcessId(CurrentProcess) )
        v2 |= 0x12u;
    }
  }
  else
  {
    v2 = 0;
  }
  ExReleasePushLockSharedEx(a1, 0);
  KeLeaveCriticalRegion();
  return v2;
}

```

## disassembly

```asm
0x1401a85b0  mov     [rsp+arg_0], rbx
0x1401a85b5  push    rdi
0x1401a85b6  sub     rsp, 20h
0x1401a85ba  mov     rdi, rcx
0x1401a85bd  call    cs:__imp_KeEnterCriticalRegion
0x1401a85c4  nop     dword ptr [rax+rax+00h]
0x1401a85c9  xor     edx, edx
0x1401a85cb  mov     rcx, rdi
0x1401a85ce  call    cs:__imp_ExAcquirePushLockSharedEx
0x1401a85d5  nop     dword ptr [rax+rax+00h]
0x1401a85da  cmp     dword ptr [rdi+0Ch], 0
0x1401a85de  jnz     short loc_1401A85E4
0x1401a85e0  xor     ebx, ebx
0x1401a85e2  jmp     short loc_1401A864A
0x1401a85e4  call    cs:__imp_PsGetCurrentThreadId
0x1401a85eb  nop     dword ptr [rax+rax+00h]
0x1401a85f0  cmp     eax, [rdi+0Ch]
0x1401a85f3  mov     ebx, 5
0x1401a85f8  lea     ecx, [rbx-4]
0x1401a85fb  cmovnz  ebx, ecx
0x1401a85fe  call    cs:__imp_PsGetCurrentProcessId
0x1401a8605  nop     dword ptr [rax+rax+00h]
0x1401a860a  and     eax, 0FFFFFFFCh
0x1401a860d  cmp     eax, [rdi+8]
0x1401a8610  jnz     short loc_1401A8617
0x1401a8612  or      ebx, 2
0x1401a8615  jmp     short loc_1401A864A
0x1401a8617  call    cs:__imp_KeIsAttachedProcess
0x1401a861e  nop     dword ptr [rax+rax+00h]
0x1401a8623  test    al, al
0x1401a8625  jz      short loc_1401A864A
0x1401a8627  call    cs:__imp_PsGetCurrentProcess
0x1401a862e  nop     dword ptr [rax+rax+00h]
0x1401a8633  mov     rcx, rax; Process
0x1401a8636  call    cs:__imp_PsGetProcessId
0x1401a863d  nop     dword ptr [rax+rax+00h]
0x1401a8642  cmp     [rdi+8], eax
0x1401a8645  jnz     short loc_1401A864A
0x1401a8647  or      ebx, 12h
0x1401a864a  xor     edx, edx
0x1401a864c  mov     rcx, rdi
0x1401a864f  call    cs:__imp_ExReleasePushLockSharedEx
0x1401a8656  nop     dword ptr [rax+rax+00h]
0x1401a865b  call    cs:__imp_KeLeaveCriticalRegion
0x1401a8662  nop     dword ptr [rax+rax+00h]
0x1401a8667  mov     eax, ebx
0x1401a8669  mov     rbx, [rsp+28h+arg_0]
0x1401a866e  add     rsp, 20h
0x1401a8672  pop     rdi
0x1401a8673  retn
```
