# AutoSwitchPreemptive::~AutoSwitchPreemptive(void)

- ea: `0x10082cad0`
- end: `0x10082cb72`
- name: `??1AutoSwitchPreemptive@@IEAA@XZ`
- size: `162`
- prototype: `void __fastcall(AutoSwitchPreemptive *__hidden this)`
- caller_count: `39`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x10082c6c0`
- `0x10082ca10`
- `0x10082cfb0`
- `0x10082d990`
- `0x10082db70`
- `0x10082de10`
- `0x10082e560`
- `0x1008385d0`
- `0x100838f00`
- `0x1008392b0`
- `0x1008454b8`
- `0x100845500`
- `0x100845530`
- `0x1008457cc`
- `0x1008458bf`
- `0x100845908`
- `0x10084593c`
- `0x100845978`
- `0x1008459ac`
- `0x1008459e8`
- `0x100845a30`
- `0x100845c8c`
- `0x100845d7f`
- `0x1008466a8`
- `0x1008466d9`
- `0x1008466fb`
- `0x10084671d`
- `0x10084673f`
- `0x100846761`
- `0x100846783`
- `0x1008467a5`
- `0x100846880`
- `0x1008468c0`
- `0x1008468e4`
- `0x100846908`
- `0x1008469b0`
- `0x1008469f0`
- `0x100846a14`
- `0x100846a38`

## callees

- `0x10082cad0`

## import_xrefs

- `sqldk!?PopWait@SOS_Task@@AEAAXXZ` at `0x10082cb5f`
- `sqldk!SystemThread_TlsIndex` at `0x10082cb24`
- `sqldk!SystemThread_TlsOffset` at `0x10082cb2d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082cb46`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10082cb46`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AutoSwitchPreemptive::~AutoSwitchPreemptive(AutoSwitchPreemptive *this)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 v4; // rcx

  if ( *(_DWORD *)this )
  {
    v2 = *((_QWORD *)this + 1);
    if ( *((_DWORD *)this + 1) )
      *(_DWORD *)(v2 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v2 + 608) + 16LL))(*(_QWORD *)(v2 + 608), v2, 1);
  }
  if ( *((_BYTE *)this + 64) )
  {
    v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v4 = *(_QWORD *)(v3 + 256);
    if ( !v4 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v4 = *(_QWORD *)(v3 + 256);
    }
    SOS_Task::PopWait(*(SOS_Task **)(v4 + 600));
  }
}

```

## disassembly

```asm
0x10082cad0  mov     [rsp+arg_0], rcx
0x10082cad5  push    rbx
0x10082cad6  sub     rsp, 30h
0x10082cada  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x10082cae3  mov     rbx, rcx
0x10082cae6  cmp     dword ptr [rcx], 0
0x10082cae9  jz      short loc_10082CB15
0x10082caeb  mov     rdx, [rcx+8]
0x10082caef  mov     rcx, [rdx+260h]
0x10082caf6  cmp     dword ptr [rbx+4], 0
0x10082cafa  jz      short loc_10082CB08
0x10082cafc  or      dword ptr [rdx+320h], 800h
0x10082cb06  jmp     short loc_10082CB15
0x10082cb08  mov     rax, [rcx]
0x10082cb0b  mov     r8d, 1
0x10082cb11  call    qword ptr [rax+10h]
0x10082cb14  nop
0x10082cb15  cmp     byte ptr [rbx+40h], 0
0x10082cb19  jz      short loc_10082CB6C
0x10082cb1b  mov     rdx, gs:58h
0x10082cb24  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10082cb2b  mov     ecx, [rax]
0x10082cb2d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10082cb34  mov     ebx, [rax]
0x10082cb36  add     rbx, [rdx+rcx*8]
0x10082cb3a  mov     rcx, [rbx+100h]
0x10082cb41  test    rcx, rcx
0x10082cb44  jnz     short loc_10082CB53
0x10082cb46  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10082cb4c  mov     rcx, [rbx+100h]
0x10082cb53  mov     rcx, [rcx+258h]
0x10082cb5a  add     rsp, 30h
0x10082cb5e  pop     rbx
0x10082cb5f  jmp     cs:__imp_?PopWait@SOS_Task@@AEAAXXZ; SOS_Task::PopWait(void)
0x10082cb6c  add     rsp, 30h
0x10082cb70  pop     rbx
0x10082cb71  retn
```
