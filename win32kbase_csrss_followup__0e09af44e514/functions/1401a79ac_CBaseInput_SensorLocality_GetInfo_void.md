# CBaseInput::SensorLocality::GetInfo(void)

- ea: `0x1401a79ac`
- end: `0x1401a7a71`
- name: `?GetInfo@SensorLocality@CBaseInput@@QEBA?AW4SensorLocalityInfo@@XZ`
- size: `197`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140191e48`
- `0x1401a789c`
- `0x1401a798c`
- `0x1402111fc`

## callees

- `0x1401a79ac`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1401a7a23`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401a7a23`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a79b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a79b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a7a57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a7a57`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a79ca`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a79ca`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401a7a4b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401a7a4b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401a79fa`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401a79fa`
- `ntoskrnl!PsGetProcessId` at `0x1401a7a32`
- `ntoskrnl!PsGetProcessId` at `0x1401a7a32`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1401a79e0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1401a79e0`
- `ntoskrnl!KeIsAttachedProcess` at `0x1401a7a13`
- `ntoskrnl!KeIsAttachedProcess` at `0x1401a7a13`

## pseudocode

```c
__int64 __fastcall CBaseInput::SensorLocality::GetInfo(__int64 a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
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
    else if ( (unsigned __int8)KeIsAttachedProcess() )
    {
      CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v4, v3, v5);
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
0x1401a79ac  mov     [rsp+arg_0], rbx
0x1401a79b1  push    rdi
0x1401a79b2  sub     rsp, 20h
0x1401a79b6  mov     rdi, rcx
0x1401a79b9  call    cs:__imp_KeEnterCriticalRegion
0x1401a79c0  nop     dword ptr [rax+rax+00h]
0x1401a79c5  xor     edx, edx
0x1401a79c7  mov     rcx, rdi
0x1401a79ca  call    cs:__imp_ExAcquirePushLockSharedEx
0x1401a79d1  nop     dword ptr [rax+rax+00h]
0x1401a79d6  cmp     dword ptr [rdi+0Ch], 0
0x1401a79da  jnz     short loc_1401A79E0
0x1401a79dc  xor     ebx, ebx
0x1401a79de  jmp     short loc_1401A7A46
0x1401a79e0  call    cs:__imp_PsGetCurrentThreadId
0x1401a79e7  nop     dword ptr [rax+rax+00h]
0x1401a79ec  cmp     eax, [rdi+0Ch]
0x1401a79ef  mov     ebx, 5
0x1401a79f4  lea     ecx, [rbx-4]
0x1401a79f7  cmovnz  ebx, ecx
0x1401a79fa  call    cs:__imp_PsGetCurrentProcessId
0x1401a7a01  nop     dword ptr [rax+rax+00h]
0x1401a7a06  and     eax, 0FFFFFFFCh
0x1401a7a09  cmp     eax, [rdi+8]
0x1401a7a0c  jnz     short loc_1401A7A13
0x1401a7a0e  or      ebx, 2
0x1401a7a11  jmp     short loc_1401A7A46
0x1401a7a13  call    cs:__imp_KeIsAttachedProcess
0x1401a7a1a  nop     dword ptr [rax+rax+00h]
0x1401a7a1f  test    al, al
0x1401a7a21  jz      short loc_1401A7A46
0x1401a7a23  call    cs:__imp_PsGetCurrentProcess
0x1401a7a2a  nop     dword ptr [rax+rax+00h]
0x1401a7a2f  mov     rcx, rax; Process
0x1401a7a32  call    cs:__imp_PsGetProcessId
0x1401a7a39  nop     dword ptr [rax+rax+00h]
0x1401a7a3e  cmp     [rdi+8], eax
0x1401a7a41  jnz     short loc_1401A7A46
0x1401a7a43  or      ebx, 12h
0x1401a7a46  xor     edx, edx
0x1401a7a48  mov     rcx, rdi
0x1401a7a4b  call    cs:__imp_ExReleasePushLockSharedEx
0x1401a7a52  nop     dword ptr [rax+rax+00h]
0x1401a7a57  call    cs:__imp_KeLeaveCriticalRegion
0x1401a7a5e  nop     dword ptr [rax+rax+00h]
0x1401a7a63  mov     eax, ebx
0x1401a7a65  mov     rbx, [rsp+28h+arg_0]
0x1401a7a6a  add     rsp, 20h
0x1401a7a6e  pop     rdi
0x1401a7a6f  retn
```
