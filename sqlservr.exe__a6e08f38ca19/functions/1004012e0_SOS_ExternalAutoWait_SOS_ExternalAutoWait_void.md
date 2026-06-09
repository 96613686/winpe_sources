# SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)

- ea: `0x1004012e0`
- end: `0x100401339`
- name: `??1SOS_ExternalAutoWait@@QEAA@XZ`
- size: `89`
- prototype: `void __fastcall(SOS_ExternalAutoWait *__hidden this)`
- caller_count: `33`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x100401350`
- `0x10040d5d0`
- `0x1004119c0`
- `0x10041ebd0`
- `0x10041ec70`
- `0x1004219e0`
- `0x100421c40`
- `0x10043a840`
- `0x10043b680`
- `0x100454040`
- `0x1004541b6`
- `0x1004541f4`
- `0x10045429c`
- `0x100454884`
- `0x1004548a0`
- `0x100454c70`
- `0x100454cf0`
- `0x100455e40`
- `0x100455ef8`
- `0x100455f40`
- `0x100455f84`
- `0x100455fd0`
- `0x100456020`
- `0x100456064`
- `0x10045609c`
- `0x1004560d4`
- `0x100456120`
- `0x100456164`
- `0x10045619c`
- `0x1004561c4`
- `0x1004562a0`
- `0x100456be0`
- `0x100456c60`

## callees

- `0x1004012e0`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041ec46`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041ec46`
- `sqldk!SystemThread_TlsOffset` at `0x100401305`
- `sqldk!SystemThread_TlsIndex` at `0x1004012f7`
- `sqldk!?PopWait@SOS_Task@@AEAAXXZ` at `0x100401332`

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
0x1004012e0  sub     rsp, 28h
0x1004012e4  cmp     byte ptr [rcx+30h], 0
0x1004012e8  jz      loc_10041EC5E
0x1004012ee  mov     rdx, gs:58h
0x1004012f7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004012fe  mov     [rsp+28h+var_8], rbx
0x100401303  mov     ecx, [rax]
0x100401305  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040130c  mov     ebx, [rax]
0x10040130e  add     rbx, [rdx+rcx*8]
0x100401312  mov     rcx, [rbx+100h]
0x100401319  test    rcx, rcx
0x10040131c  jz      loc_10041EC46
0x100401322  mov     rcx, [rcx+258h]
0x100401329  mov     rbx, [rsp+28h+var_8]
0x10040132e  add     rsp, 28h
0x100401332  jmp     cs:__imp_?PopWait@SOS_Task@@AEAAXXZ; SOS_Task::PopWait(void)
0x10041ec46  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041ec4c  mov     rcx, [rbx+100h]
0x10041ec53  jmp     loc_100401322
0x10041ec59  mov     rbx, [rsp+28h+var_8]
0x10041ec5e  add     rsp, 28h
0x10041ec62  retn
```
