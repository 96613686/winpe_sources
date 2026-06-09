# SOS_Task::IsDelayAbortOn(void)

- ea: `0x10044b040`
- end: `0x10044b0a8`
- name: `?IsDelayAbortOn@SOS_Task@@SAHXZ`
- size: `104`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x10044ace0`
- `0x10044af90`

## callees

- `0x10044b040`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044b073`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044b073`
- `sqldk!SystemThread_TlsOffset` at `0x10044b058`
- `sqldk!SystemThread_TlsIndex` at `0x10044b04f`

## pseudocode

```c
_BOOL8 SOS_Task::IsDelayAbortOn(void)
{
  __int64 v0; // rbx
  __int64 v1; // rax

  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v1 = *(_QWORD *)(v0 + 256);
  if ( !v1 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v1 = *(_QWORD *)(v0 + 256);
  }
  return (*(_BYTE *)(v1 + 616) & 1) != 0 || (*(_DWORD *)(v1 + 800) & 0x180) != 0;
}

```

## disassembly

```asm
0x10044b040  push    rbx
0x10044b042  sub     rsp, 20h
0x10044b046  mov     rdx, gs:58h
0x10044b04f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044b056  mov     ecx, [rax]
0x10044b058  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044b05f  mov     ebx, [rax]
0x10044b061  add     rbx, [rdx+rcx*8]
0x10044b065  mov     rax, [rbx+100h]
0x10044b06c  test    rax, rax
0x10044b06f  jnz     short loc_10044B080
0x10044b071  xor     ecx, ecx
0x10044b073  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044b079  mov     rax, [rbx+100h]
0x10044b080  test    byte ptr [rax+268h], 1
0x10044b087  jnz     short loc_10044B09D
0x10044b089  test    dword ptr [rax+320h], 180h
0x10044b093  jnz     short loc_10044B09D
0x10044b095  xor     eax, eax
0x10044b097  add     rsp, 20h
0x10044b09b  pop     rbx
0x10044b09c  retn
0x10044b09d  mov     eax, 1
0x10044b0a2  add     rsp, 20h
0x10044b0a6  pop     rbx
0x10044b0a7  retn
```
