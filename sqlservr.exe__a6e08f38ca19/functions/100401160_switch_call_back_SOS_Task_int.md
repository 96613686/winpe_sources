# switch_call_back(SOS_Task *,int)

- ea: `0x100401160`
- end: `0x100401244`
- name: `?switch_call_back@@YAXPEAVSOS_Task@@H@Z`
- size: `228`
- prototype: `void __fastcall(struct SOS_Task *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x100401160`
- `0x10041ed30`
- `0x10041ee70`

## import_xrefs

- `sqlmin!?SETaskSuspendingNotification@@YAXXZ` at `0x100401149`
- `sqlmin!?SETaskSuspendingNotification@@YAXXZ` at `0x100401149`
- `sqllang!?CheckPendingReads@@YAXXZ` at `0x10041f5e9`
- `sqllang!?CheckPendingReads@@YAXXZ` at `0x10041f5e9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f628`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f628`
- `sqldk!SystemThread_TlsOffset` at `0x10040118c`
- `sqldk!SystemThread_TlsOffset` at `0x1004011f9`
- `sqldk!SystemThread_TlsIndex` at `0x100401183`
- `sqldk!SystemThread_TlsIndex` at `0x1004011f0`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10041f63b`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10041f63b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10041f61b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10041f61b`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x1004011a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall switch_call_back(struct SOS_Task *a1, int a2)
{
  CHostTask *v3; // rbx
  __int64 v4; // rbx
  __int64 v5; // rcx
  _BYTE v6[16]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v7[24]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v8[56]; // [rsp+60h] [rbp-38h] BYREF

  v3 = *(CHostTask **)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset
                     + 56LL);
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v8, 0, 0, 0, hdl_backout, 0);
    switch ( a2 )
    {
      case 0:
        if ( v3 )
          CHostTask::DoSwitchIn(v3);
        break;
      case 1:
      case 4:
      case 5:
      case 6:
        break;
      case 2:
        if ( v3 )
          CHostTask::DoSwitchOut(v3);
        if ( (*(_BYTE *)(qword_10049F340 + 976) & 2) != 0 )
          CheckPendingReads();
        goto LABEL_14;
      case 3:
LABEL_14:
        SETaskSuspendingNotification();
        break;
      default:
        utassert_fail(1u, "FALSE", "sqlsos.cpp", 386, "Invalid switch value");
        break;
    }
    ExcHandler::~ExcHandler((ExcHandler *)v8);
  }
  catch ( SQLError v7 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v6, (const struct SQLError *)v7);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v6);
    }
    catch ( ShortStackException )
    {
    }
  }
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  if ( *(_DWORD *)(v5 + 556) )
    ExceptionPostCatchActions((struct Worker *)v5);
}

```

## disassembly

```asm
0x100401160  mov     r11, rsp
0x100401163  push    rdi
0x100401164  sub     rsp, 90h
0x10040116b  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x100401173  mov     [r11+8], rbx
0x100401177  movsxd  rdi, edx
0x10040117a  mov     r9, gs:58h
0x100401183  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040118a  mov     ecx, [rax]
0x10040118c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100401193  mov     r8d, [rax]
0x100401196  add     r8, [r9+rcx*8]
0x10040119a  mov     rbx, [r8+38h]
0x10040119e  xor     edx, edx; unsigned __int16
0x1004011a0  mov     [r11-70h], rdx
0x1004011a4  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x1004011ab  mov     [r11-78h], rax
0x1004011af  xor     r9d, r9d; unsigned __int8
0x1004011b2  xor     r8d, r8d; unsigned __int8
0x1004011b5  lea     rcx, [r11-38h]; this
0x1004011b9  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x1004011be  nop
0x1004011bf  cmp     edi, 6; switch 7 cases
0x1004011c2  ja      def_1004011D9; jumptable 00000001004011D9 default case
0x1004011c8  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004011cf  mov     edx, ds:(jpt_1004011D9 - 100400000h)[rcx+rdi*4]
0x1004011d6  add     rdx, rcx
0x1004011d9  jmp     rdx; switch jump
0x1004011dc  lea     rcx, [rsp+98h+var_38]; jumptable 00000001004011D9 cases 1,4-6
0x1004011e1  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x1004011e6  nop
0x1004011e7  mov     rdx, gs:58h
0x1004011f0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004011f7  mov     ecx, [rax]
0x1004011f9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100401200  mov     ebx, [rax]
0x100401202  add     rbx, [rdx+rcx*8]
0x100401206  mov     rcx, [rbx+100h]
0x10040120d  test    rcx, rcx
0x100401210  jz      loc_10041F628
0x100401216  cmp     dword ptr [rcx+22Ch], 0
0x10040121d  jnz     loc_10041F63B
0x100401223  mov     rbx, [rsp+98h+arg_0]
0x10040122b  add     rsp, 90h
0x100401232  pop     rdi
0x100401233  retn
0x100401234  test    rbx, rbx; jumptable 00000001004011D9 case 0
0x100401237  jz      short loc_1004011DC; jumptable 00000001004011D9 cases 1,4-6
0x100401239  mov     rcx, rbx; this
0x10040123c  call    ?DoSwitchIn@CHostTask@@QEAAJXZ; CHostTask::DoSwitchIn(void)
0x100401241  jmp     short loc_1004011DC; jumptable 00000001004011D9 cases 1,4-6
0x10040112c  test    rbx, rbx; jumptable 00000001004011D9 case 2
0x10040112f  jnz     loc_10041F5DA
0x100401135  mov     rax, cs:qword_10049F340
0x10040113c  test    byte ptr [rax+3D0h], 2
0x100401143  jnz     loc_10041F5E9
0x100401149  call    cs:__imp_?SETaskSuspendingNotification@@YAXXZ; jumptable 00000001004011D9 case 3
0x10040114f  jmp     loc_1004011DC; jumptable 00000001004011D9 cases 1,4-6
0x10041f5da  mov     rcx, rbx; this
0x10041f5dd  call    ?DoSwitchOut@CHostTask@@QEAAJXZ; CHostTask::DoSwitchOut(void)
0x10041f5e2  nop
0x10041f5e3  jmp     loc_100401135
0x10041f5e9  call    cs:__imp_?CheckPendingReads@@YAXXZ; CheckPendingReads(void)
0x10041f5ef  nop
0x10041f5f0  jmp     loc_100401149; jumptable 00000001004011D9 case 3
0x10041f5f6  lea     rax, aInvalidSwitchV; jumptable 00000001004011D9 default case
0x10041f5fd  mov     [rsp+98h+var_78], rax
0x10041f602  mov     r9d, 182h
0x10041f608  lea     r8, aSqlsosCpp_0; "sqlsos.cpp"
0x10041f60f  lea     rdx, aFalse_0; "FALSE"
0x10041f616  mov     ecx, 1
0x10041f61b  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10041f621  nop
0x10041f622  jmp     loc_1004011DC; jumptable 00000001004011D9 cases 1,4-6
0x10041f628  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041f62e  mov     rcx, [rbx+100h]
0x10041f635  jmp     loc_100401216
0x10041f63b  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10041f641  nop
0x10041f642  jmp     loc_100401223
```
