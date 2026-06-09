# RunTaskSchedulerTask(ushort const *)

- ea: `0x180017bf8`
- end: `0x180017d14`
- name: `?RunTaskSchedulerTask@@YAJPEBG@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct IRegisteredTask *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800183f4`

## callees

- `0x18000934c`
- `0x1800175b8`
- `0x18001777c`
- `0x180017bf8`
- `0x1800186c8`
- `0x18001f010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180017cba`
- `OLEAUT32!__imp_VariantClear` at `0x180017cba`

## string_xrefs

- `0x180017c25`: `shell\lib\comtaskserverutil.cpp`
- `0x180017c5d`: `shell\lib\comtaskserverutil.cpp`
- `0x180017cc8`: `shell\lib\comtaskserverutil.cpp`

## pseudocode

```c
__int64 __fastcall RunTaskSchedulerTask(struct IRegisteredTask *a1)
{
  int v1; // eax
  const unsigned __int16 *v2; // rdx
  int v3; // ebx
  int TaskSchedulerTask; // eax
  struct IRegisteredTaskVtbl *lpVtbl; // rax
  HRESULT (__stdcall *Run)(IRegisteredTask *, VARIANT, IRunningTask **); // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  __int128 v9; // [rsp+40h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  struct IRegisteredTask *v12; // [rsp+70h] [rbp+10h] BYREF
  __int64 v13; // [rsp+78h] [rbp+18h] BYREF
  struct ITaskService *v14; // [rsp+80h] [rbp+20h] BYREF

  v12 = a1;
  v14 = 0;
  v1 = ConnectToTaskScheduler(&v14);
  v3 = v1;
  if ( v1 >= 0 )
  {
    v12 = 0;
    TaskSchedulerTask = GetTaskSchedulerTask(v14, v2, &v12);
    v3 = TaskSchedulerTask;
    if ( TaskSchedulerTask >= 0 )
    {
      v13 = 0;
      pRecInfo = pvarg.pRecInfo;
      lpVtbl = v12->lpVtbl;
      pvarg.vt = 0;
      Run = lpVtbl->Run;
      v9 = *(_OWORD *)&pvarg.vt;
      v3 = ((__int64 (__fastcall *)(struct IRegisteredTask *, __int128 *, __int64 *))Run)(v12, &v9, &v13);
      VariantClear(&pvarg);
      if ( v3 >= 0 )
      {
        wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(&v13);
        wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(&v12);
        v3 = 0;
        goto LABEL_9;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
        (const char *)(unsigned int)v3,
        *(int *)&pvarg.vt);
      wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(&v13);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
        (const char *)(unsigned int)TaskSchedulerTask,
        *(int *)&pvarg.vt);
    }
    wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(&v12);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
      (const char *)(unsigned int)v1,
      *(int *)&pvarg.vt);
  }
LABEL_9:
  wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(&v14);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017bf8  mov     [rsp-8+arg_18], rbx
0x180017bfd  mov     [rsp-8+arg_0], rcx
0x180017c02  push    rbp
0x180017c03  mov     rbp, rsp
0x180017c06  sub     rsp, 60h
0x180017c0a  lea     rcx, [rbp+arg_10]
0x180017c0e  mov     [rbp+arg_10], 0
0x180017c16  call    ConnectToTaskScheduler
0x180017c1b  mov     ebx, eax
0x180017c1d  test    eax, eax
0x180017c1f  jns     short loc_180017C3E
0x180017c21  mov     rcx, [rbp+8]; this
0x180017c25  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180017c2c  mov     r9d, eax; char *
0x180017c2f  mov     edx, 37h ; '7'; void *
0x180017c34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c39  jmp     loc_180017CFB
0x180017c3e  mov     rcx, [rbp+arg_10]; struct ITaskService *
0x180017c42  lea     r8, [rbp+arg_0]; struct IRegisteredTask **
0x180017c46  mov     [rbp+arg_0], 0
0x180017c4e  call    ?GetTaskSchedulerTask@@YAJPEAUITaskService@@PEBGPEAPEAUIRegisteredTask@@@Z; GetTaskSchedulerTask(ITaskService *,ushort const *,IRegisteredTask * *)
0x180017c53  mov     ebx, eax
0x180017c55  test    eax, eax
0x180017c57  jns     short loc_180017C7C
0x180017c59  mov     rcx, [rbp+8]; this
0x180017c5d  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180017c64  mov     r9d, eax; char *
0x180017c67  mov     edx, 3Ah ; ':'; void *
0x180017c6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c71  lea     rcx, [rbp+arg_0]
0x180017c75  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x180017c7a  jmp     short loc_180017CFB
0x180017c7c  mov     rcx, [rbp+arg_0]
0x180017c80  lea     r8, [rbp+arg_8]
0x180017c84  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180017c89  xor     edx, edx
0x180017c8b  mov     [rbp+arg_8], 0
0x180017c93  movsd   [rbp+var_10], xmm1
0x180017c98  mov     rax, [rcx]
0x180017c9b  mov     word ptr [rbp+pvarg], dx
0x180017c9f  lea     rdx, [rbp+var_20]
0x180017ca3  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180017ca7  mov     rax, [rax+60h]
0x180017cab  movaps  [rbp+var_20], xmm0
0x180017caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cb4  lea     rcx, [rbp+pvarg]; pvarg
0x180017cb8  mov     ebx, eax
0x180017cba  call    cs:__imp_VariantClear
0x180017cc0  test    ebx, ebx
0x180017cc2  jns     short loc_180017CE7
0x180017cc4  mov     rcx, [rbp+8]; this
0x180017cc8  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180017ccf  mov     r9d, ebx; char *
0x180017cd2  mov     edx, 3Dh ; '='; void *
0x180017cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017cdc  lea     rcx, [rbp+arg_8]
0x180017ce0  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x180017ce5  jmp     short loc_180017C71
0x180017ce7  lea     rcx, [rbp+arg_8]
0x180017ceb  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x180017cf0  lea     rcx, [rbp+arg_0]
0x180017cf4  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x180017cf9  xor     ebx, ebx
0x180017cfb  lea     rcx, [rbp+arg_10]
0x180017cff  call    ??1?$com_ptr_t@UICreateObject@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICreateObject,wil::err_returncode_policy>::~com_ptr_t<ICreateObject,wil::err_returncode_policy>(void)
0x180017d04  mov     eax, ebx
0x180017d06  mov     rbx, [rsp+60h+arg_18]
0x180017d0e  add     rsp, 60h
0x180017d12  pop     rbp
0x180017d13  retn
```
