# IsExecutionAbortedDueToAttention(void)

- ea: `0x10044af90`
- end: `0x10044b02f`
- name: `?IsExecutionAbortedDueToAttention@@YAHXZ`
- size: `159`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10044ace0`

## callees

- `0x10044af90`
- `0x10044b040`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044afc3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044afc3`
- `sqldk!SystemThread_TlsOffset` at `0x10044afa8`
- `sqldk!SystemThread_TlsOffset` at `0x10044aff3`
- `sqldk!SystemThread_TlsIndex` at `0x10044af9f`
- `sqldk!SystemThread_TlsIndex` at `0x10044afea`

## pseudocode

```c
_BOOL8 IsExecutionAbortedDueToAttention(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax
  __int64 v2; // rax

  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v1 = *(_QWORD *)(v0 + 256);
  if ( !v1 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v1 = *(_QWORD *)(v0 + 256);
  }
  return (*(_DWORD *)(*(_QWORD *)(v1 + 600) + 188LL) & 4) != 0
      && ((v2 = *(_QWORD *)(SystemThread_TlsOffset
                          + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) == 0
       || !*(_BYTE *)(*(_QWORD *)(v2 + 56) + 8LL))
      && !(unsigned int)SOS_Task::IsDelayAbortOn();
}

```

## disassembly

```asm
0x10044af90  push    rbx
0x10044af92  sub     rsp, 20h
0x10044af96  mov     rdx, gs:58h
0x10044af9f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044afa6  mov     ecx, [rax]
0x10044afa8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044afaf  mov     ebx, [rax]
0x10044afb1  add     rbx, [rdx+rcx*8]
0x10044afb5  mov     rax, [rbx+100h]
0x10044afbc  test    rax, rax
0x10044afbf  jnz     short loc_10044AFD0
0x10044afc1  xor     ecx, ecx
0x10044afc3  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044afc9  mov     rax, [rbx+100h]
0x10044afd0  mov     rax, [rax+258h]
0x10044afd7  mov     eax, [rax+0BCh]
0x10044afdd  test    al, 4
0x10044afdf  jz      short loc_10044B027
0x10044afe1  mov     r8, gs:58h
0x10044afea  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044aff1  mov     edx, [rax]
0x10044aff3  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044affa  mov     ecx, [rax]
0x10044affc  mov     rax, [r8+rdx*8]
0x10044b000  mov     rax, [rcx+rax]
0x10044b004  test    rax, rax
0x10044b007  jz      short loc_10044B013
0x10044b009  mov     rcx, [rax+38h]
0x10044b00d  cmp     byte ptr [rcx+8], 0
0x10044b011  jnz     short loc_10044B027
0x10044b013  call    ?IsDelayAbortOn@SOS_Task@@SAHXZ; SOS_Task::IsDelayAbortOn(void)
0x10044b018  test    eax, eax
0x10044b01a  jnz     short loc_10044B027
0x10044b01c  mov     eax, 1
0x10044b021  add     rsp, 20h
0x10044b025  pop     rbx
0x10044b026  retn
0x10044b027  xor     eax, eax
0x10044b029  add     rsp, 20h
0x10044b02d  pop     rbx
0x10044b02e  retn
```
