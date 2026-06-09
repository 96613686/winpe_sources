# SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)

- ea: `0x10082ca50`
- end: `0x10082caae`
- name: `??1SOS_ExternalAutoWait@@QEAA@XZ`
- size: `94`
- prototype: `void __fastcall(SOS_ExternalAutoWait *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1008454a0`
- `0x100845550`
- `0x1008457b4`
- `0x1008458f0`
- `0x100845960`
- `0x1008459d0`
- `0x100845c74`
- `0x100846692`
- `0x100846868`
- `0x100846998`

## callees

- `0x10082ca50`

## import_xrefs

- `sqldk!?PopWait@SOS_Task@@AEAAXXZ` at `0x10082caa7`
- `sqldk!SystemThread_TlsIndex` at `0x10082ca63`
- `sqldk!SystemThread_TlsOffset` at `0x10082ca71`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082ca8a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082ca8a`

## pseudocode

```c
void __fastcall SOS_ExternalAutoWait::~SOS_ExternalAutoWait(SOS_ExternalAutoWait *this)
{
  __int64 v1; // rbx
  __int64 v2; // rcx

  if ( *((_BYTE *)this + 48) )
  {
    v1 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v2 = *(_QWORD *)(v1 + 256);
    if ( !v2 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v2 = *(_QWORD *)(v1 + 256);
    }
    SOS_Task::PopWait(*(SOS_Task **)(v2 + 600));
  }
}

```

## disassembly

```asm
0x10082ca50  sub     rsp, 28h
0x10082ca54  cmp     byte ptr [rcx+30h], 0
0x10082ca58  jz      short loc_10082CABA
0x10082ca5a  mov     rdx, gs:58h
0x10082ca63  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082ca6a  mov     [rsp+28h+var_8], rbx
0x10082ca6f  mov     ecx, [rax]
0x10082ca71  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082ca78  mov     ebx, [rax]
0x10082ca7a  add     rbx, [rdx+rcx*8]
0x10082ca7e  mov     rcx, [rbx+100h]
0x10082ca85  test    rcx, rcx
0x10082ca88  jnz     short loc_10082CA97
0x10082ca8a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082ca90  mov     rcx, [rbx+100h]
0x10082ca97  mov     rcx, [rcx+258h]
0x10082ca9e  mov     rbx, [rsp+28h+var_8]
0x10082caa3  add     rsp, 28h
0x10082caa7  jmp     cs:__imp_?PopWait@SOS_Task@@AEAAXXZ; SOS_Task::PopWait(void)
0x10082cab8  and     al, 20h
0x10082caba  add     rsp, 28h
0x10082cabe  retn
```
