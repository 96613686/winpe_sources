# ReRegisterRgCallback(void *)

- ea: `0x1004238f0`
- end: `0x100423961`
- name: `?ReRegisterRgCallback@@YAIPEAX@Z`
- size: `113`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1004238f0`
- `0x100435700`
- `0x100440570`

## import_xrefs

- `sqlmin!?RefreshTelemetryTagsExtern@@YAX_N0@Z` at `0x100423901`
- `sqlmin!?RefreshTelemetryTagsExtern@@YAX_N0@Z` at `0x100423901`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x100423939`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x100423939`
- `sqldk!?SOS_OS_MemoryModel@@3W4SOS_MemoryModel@@A` at `0x100423907`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReRegisterRgCallback(void *a1)
{
  __int64 *v2; // [rsp+58h] [rbp+10h] BYREF

  RefreshTelemetryTagsExtern(1, 0);
  if ( SOS_OS_MemoryModel == 4 )
  {
    v2 = 0;
    if ( (unsigned int)SOS_OS::EnqueueTask(ResendSharedMemoryNameTask, 0, 1024, &v2, -1) )
      log_unlocalized_systemmetadata(L"Could not resend shared memory name from SQL\n");
    CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(&v2);
  }
  return 0;
}

```

## disassembly

```asm
0x1004238f0  sub     rsp, 48h
0x1004238f4  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1004238fd  xor     edx, edx
0x1004238ff  mov     cl, 1
0x100423901  call    cs:__imp_?RefreshTelemetryTagsExtern@@YAX_N0@Z; RefreshTelemetryTagsExtern(bool,bool)
0x100423907  mov     rax, cs:__imp_?SOS_OS_MemoryModel@@3W4SOS_MemoryModel@@A; SOS_MemoryModel SOS_OS_MemoryModel
0x10042390e  cmp     dword ptr [rax], 4
0x100423911  jnz     short loc_10042395A
0x100423913  mov     [rsp+48h+arg_8], 0
0x10042391c  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFFh
0x100423925  lea     r9, [rsp+48h+arg_8]
0x10042392a  xor     edx, edx
0x10042392c  mov     r8d, 400h
0x100423932  lea     rcx, ResendSharedMemoryNameTask
0x100423939  call    cs:__imp_?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z; SOS_OS::EnqueueTask(void * (*)(void *),void *,ulong,SOS_Task * *,unsigned __int64)
0x10042393f  test    eax, eax
0x100423941  jz      short loc_100423950
0x100423943  lea     rcx, aCouldNotResend; "Could not resend shared memory name fro"...
0x10042394a  call    ?log_unlocalized_systemmetadata@@YAXPEB_WZZ; log_unlocalized_systemmetadata(wchar_t const *,...)
0x10042394f  nop
0x100423950  lea     rcx, [rsp+48h+arg_8]
0x100423955  call    ??1?$CAutoRefc@VSOS_Task@@@@QEAA@XZ; CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(void)
0x10042395a  xor     eax, eax
0x10042395c  add     rsp, 48h
0x100423960  retn
```
