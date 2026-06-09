# WcPreDismountLockRemove

- ea: `0x14001a148`
- end: `0x14001a206`
- name: `WcPreDismountLockRemove`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140023150`
- `0x14002ede0`

## callees

- `0x140001580`
- `0x14001a148`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x14001a1af`
- `ntoskrnl!PsIsHostSilo` at `0x14001a1af`
- `ntoskrnl!PsGetCurrentSilo` at `0x14001a1a0`
- `ntoskrnl!PsGetCurrentSilo` at `0x14001a1a0`
- `FLTMGR!FltReleaseContext` at `0x14001a1e7`
- `FLTMGR!FltReleaseContext` at `0x14001a1e7`
- `FLTMGR!FltGetInstanceContext` at `0x14001a172`
- `FLTMGR!FltGetInstanceContext` at `0x14001a172`

## pseudocode

```c
__int64 __fastcall WcPreDismountLockRemove(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 CurrentSilo; // rax
  PFLT_CONTEXT Context; // [rsp+40h] [rbp+18h] BYREF

  Context = 0;
  FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &Context);
  if ( *((_DWORD *)Context + 5)
    || _InterlockedCompareExchange((volatile signed __int32 *)Context + 6, 0, 0)
    || (v4 = 1, CurrentSilo = PsGetCurrentSilo(), !(unsigned __int8)PsIsHostSilo(CurrentSilo))
    && (unsigned __int8)WcUnionsExistForInstance(*(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32), 0, 0) )
  {
    v4 = 4;
    *(_DWORD *)(a1 + 24) = -1073741790;
  }
  FltReleaseContext(Context);
  return v4;
}

```

## disassembly

```asm
0x14001a148  mov     rax, rsp
0x14001a14b  mov     [rax+8], rbx
0x14001a14f  mov     [rax+10h], rsi
0x14001a153  mov     [rax+18h], r8
0x14001a157  push    rdi
0x14001a158  sub     rsp, 20h
0x14001a15c  mov     rsi, rdx
0x14001a15f  mov     qword ptr [rax+18h], 0
0x14001a167  mov     rdi, rcx
0x14001a16a  lea     rdx, [rax+18h]; Context
0x14001a16e  mov     rcx, [rsi+18h]; Instance
0x14001a172  call    cs:__imp_FltGetInstanceContext
0x14001a179  nop     dword ptr [rax+rax+00h]
0x14001a17e  mov     rax, [rsp+28h+Context]
0x14001a183  mov     r8d, [rax+14h]
0x14001a187  test    r8d, r8d
0x14001a18a  jnz     short loc_14001A1D6
0x14001a18c  mov     r8, [rsp+28h+Context]
0x14001a191  xor     ecx, ecx
0x14001a193  xor     eax, eax
0x14001a195  lock cmpxchg [r8+18h], ecx
0x14001a19b  jnz     short loc_14001A1D6
0x14001a19d  lea     ebx, [rcx+1]
0x14001a1a0  call    cs:__imp_PsGetCurrentSilo
0x14001a1a7  nop     dword ptr [rax+rax+00h]
0x14001a1ac  mov     rcx, rax
0x14001a1af  call    cs:__imp_PsIsHostSilo
0x14001a1b6  nop     dword ptr [rax+rax+00h]
0x14001a1bb  test    al, al
0x14001a1bd  jnz     short loc_14001A1E2
0x14001a1bf  mov     rdx, [rsi+20h]
0x14001a1c3  xor     r9d, r9d
0x14001a1c6  mov     rcx, [rsi+18h]
0x14001a1ca  xor     r8d, r8d
0x14001a1cd  call    WcUnionsExistForInstance
0x14001a1d2  test    al, al
0x14001a1d4  jz      short loc_14001A1E2
0x14001a1d6  mov     ebx, 4
0x14001a1db  mov     dword ptr [rdi+18h], 0C0000022h
0x14001a1e2  mov     rcx, [rsp+28h+Context]; Context
0x14001a1e7  call    cs:__imp_FltReleaseContext
0x14001a1ee  nop     dword ptr [rax+rax+00h]
0x14001a1f3  mov     rsi, [rsp+28h+arg_8]
0x14001a1f8  mov     eax, ebx
0x14001a1fa  mov     rbx, [rsp+28h+arg_0]
0x14001a1ff  add     rsp, 20h
0x14001a203  pop     rdi
0x14001a204  retn
```
