# CBaseInput::SensorLocality::GetInfo(void)

- ea: `0x1401a7f0c`
- end: `0x1401a7fd1`
- name: `?GetInfo@SensorLocality@CBaseInput@@QEBA?AW4SensorLocalityInfo@@XZ`
- size: `197`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140191fc8`
- `0x1401a7dfc`
- `0x1401a7eec`
- `0x140211a1c`

## callees

- `0x1401a7f0c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1401a7f83`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401a7f83`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a7f19`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a7f19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a7fb7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a7fb7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a7f2a`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a7f2a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401a7fab`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401a7fab`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401a7f5a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1401a7f5a`
- `ntoskrnl!PsGetProcessId` at `0x1401a7f92`
- `ntoskrnl!PsGetProcessId` at `0x1401a7f92`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1401a7f40`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1401a7f40`
- `ntoskrnl!KeIsAttachedProcess` at `0x1401a7f73`
- `ntoskrnl!KeIsAttachedProcess` at `0x1401a7f73`

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
0x1401a7f0c  mov     [rsp+arg_0], rbx
0x1401a7f11  push    rdi
0x1401a7f12  sub     rsp, 20h
0x1401a7f16  mov     rdi, rcx
0x1401a7f19  call    cs:__imp_KeEnterCriticalRegion
0x1401a7f20  nop     dword ptr [rax+rax+00h]
0x1401a7f25  xor     edx, edx
0x1401a7f27  mov     rcx, rdi
0x1401a7f2a  call    cs:__imp_ExAcquirePushLockSharedEx
0x1401a7f31  nop     dword ptr [rax+rax+00h]
0x1401a7f36  cmp     dword ptr [rdi+0Ch], 0
0x1401a7f3a  jnz     short loc_1401A7F40
0x1401a7f3c  xor     ebx, ebx
0x1401a7f3e  jmp     short loc_1401A7FA6
0x1401a7f40  call    cs:__imp_PsGetCurrentThreadId
0x1401a7f47  nop     dword ptr [rax+rax+00h]
0x1401a7f4c  cmp     eax, [rdi+0Ch]
0x1401a7f4f  mov     ebx, 5
0x1401a7f54  lea     ecx, [rbx-4]
0x1401a7f57  cmovnz  ebx, ecx
0x1401a7f5a  call    cs:__imp_PsGetCurrentProcessId
0x1401a7f61  nop     dword ptr [rax+rax+00h]
0x1401a7f66  and     eax, 0FFFFFFFCh
0x1401a7f69  cmp     eax, [rdi+8]
0x1401a7f6c  jnz     short loc_1401A7F73
0x1401a7f6e  or      ebx, 2
0x1401a7f71  jmp     short loc_1401A7FA6
0x1401a7f73  call    cs:__imp_KeIsAttachedProcess
0x1401a7f7a  nop     dword ptr [rax+rax+00h]
0x1401a7f7f  test    al, al
0x1401a7f81  jz      short loc_1401A7FA6
0x1401a7f83  call    cs:__imp_PsGetCurrentProcess
0x1401a7f8a  nop     dword ptr [rax+rax+00h]
0x1401a7f8f  mov     rcx, rax; Process
0x1401a7f92  call    cs:__imp_PsGetProcessId
0x1401a7f99  nop     dword ptr [rax+rax+00h]
0x1401a7f9e  cmp     [rdi+8], eax
0x1401a7fa1  jnz     short loc_1401A7FA6
0x1401a7fa3  or      ebx, 12h
0x1401a7fa6  xor     edx, edx
0x1401a7fa8  mov     rcx, rdi
0x1401a7fab  call    cs:__imp_ExReleasePushLockSharedEx
0x1401a7fb2  nop     dword ptr [rax+rax+00h]
0x1401a7fb7  call    cs:__imp_KeLeaveCriticalRegion
0x1401a7fbe  nop     dword ptr [rax+rax+00h]
0x1401a7fc3  mov     eax, ebx
0x1401a7fc5  mov     rbx, [rsp+28h+arg_0]
0x1401a7fca  add     rsp, 20h
0x1401a7fce  pop     rdi
0x1401a7fcf  retn
```
