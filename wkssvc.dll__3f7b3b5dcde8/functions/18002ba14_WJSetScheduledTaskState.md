# WJSetScheduledTaskState

- ea: `0x18002ba14`
- end: `0x18002bed0`
- name: `WJSetScheduledTaskState`
- size: `1212`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011438`
- `0x18001d4c0`
- `0x18001dcc0`
- `0x18002bfa0`

## callees

- `0x18002b39c`
- `0x18002b634`
- `0x18002ba14`
- `0x180034010`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bad8`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bba7`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bbe5`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bc46`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bce6`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bd39`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bdbe`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002be10`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bad8`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bba7`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bbe5`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bc46`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bce6`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bd39`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002bdbe`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002be10`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002ba9f`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002bc95`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002bd8d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002bead`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002ba9f`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002bc95`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002bd8d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002bead`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bb06`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002bb06`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002be85`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002be85`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002babb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002babb`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bb83`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bbf3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bb83`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bbf3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002be19`
- `OLEAUT32!__imp_SysFreeString` at `0x18002be22`
- `OLEAUT32!__imp_SysFreeString` at `0x18002be19`
- `OLEAUT32!__imp_SysFreeString` at `0x18002be22`
- `OLEAUT32!__imp_VariantInit` at `0x18002baa9`
- `OLEAUT32!__imp_VariantInit` at `0x18002baa9`

## string_xrefs

- `0x18002ba8e`: `WJSetScheduledTaskState`
- `0x18002bad1`: `WJSetScheduledTaskState`
- `0x18002bb9b`: `WJSetScheduledTaskState`
- `0x18002bbd4`: `WJSetScheduledTaskState`
- `0x18002bc35`: `WJSetScheduledTaskState`
- `0x18002bc87`: `WJSetScheduledTaskState`
- `0x18002bcb0`: `WJSetScheduledTaskState`
- `0x18002bd26`: `WJSetScheduledTaskState`
- `0x18002bd77`: `WJSetScheduledTaskState`
- `0x18002be02`: `WJSetScheduledTaskState`
- `0x18002be8f`: `WJSetScheduledTaskState`
- `0x18002ba7f`: `AutoJoinSvc/%s: started. Task: "%s\%s". enableTask: %s.`
- `0x18002bb12`: `AutoJoinSvc/%s: Failed to create an instance of the TaskService class: 0x%08x\n`
- `0x18002bb74`: `AutoJoinSvc/%s: ITaskService::Connect failed with code 0x%08x\n`
- `0x18002bb94`: `AutoJoinSvc/%s: Failed to allocate task folder name "%s".`
- `0x18002bbde`: `AutoJoinSvc/%s: ITaskService::GetFolder("%s") failed with code 0x%08x.`
- `0x18002bc04`: `AutoJoinSvc/%s: Failed to allocate task name "%s".`
- `0x18002bc2e`: `AutoJoinSvc/%s: ITaskService::GetTask("%s\%s") failed with code 0x%08x.`
- `0x18002bc8e`: `AutoJoinSvc/%s: IRegisteredTask_get_Enabled("%s\%s") failed with code 0x%08x.`
- `0x18002bd83`: `AutoJoinSvc/%s: The task "%s\%s" is already %s.`
- `0x18002bcdf`: `AutoJoinSvc/%s: Successfuly %s task "%s\%s".`
- `0x18002bdb7`: `AutoJoinSvc/%s: Failed to %s task "%s\%s" with error code 0x%08x.`
- `0x18002bd30`: `AutoJoinSvc/%s: Running task "%s\%s".`
- `0x18002bd47`: `AutoJoinSvc/%s: IRegisteredTask_Run("%s\%s") failed with code 0x%08x.`
- `0x18002be09`: `AutoJoinSvc/%s: Failed to create thread-pool timer to retry %s task "%s\%s". Status 0x%08x.`
- `0x18002be9b`: `AutoJoinSvc/%s: finished - hr: 0x%08x.  Task: "%s\%s". enableTask: %s.`

## pseudocode

```c
__int64 __fastcall WJSetScheduledTaskState(OLECHAR *psz, OLECHAR *a2, unsigned __int16 a3, _QWORD *a4)
{
  int v4; // r13d
  const wchar_t *v9; // rax
  OLECHAR *v10; // r15
  OLECHAR *v11; // r12
  HRESULT v12; // eax
  int v13; // ebx
  HRESULT v14; // eax
  __int64 v15; // rax
  __int64 (__fastcall *v16)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  int v17; // eax
  BSTR v18; // rax
  OLECHAR *v19; // r8
  const wchar_t *v20; // rcx
  int v21; // eax
  BSTR v22; // rax
  const wchar_t *v23; // rcx
  int v24; // eax
  const wchar_t *v25; // r8
  __int64 v26; // rax
  const wchar_t *v27; // r8
  const wchar_t *v28; // r8
  int v29; // eax
  const wchar_t *v30; // r8
  LPVOID *ppv; // [rsp+20h] [rbp-A9h]
  __int64 v33; // [rsp+28h] [rbp-A1h]
  __int64 *v34; // [rsp+30h] [rbp-99h] BYREF
  LPVOID v35; // [rsp+38h] [rbp-91h] BYREF
  __int64 v36; // [rsp+40h] [rbp-89h] BYREF
  __int64 v37; // [rsp+48h] [rbp-81h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-79h] BYREF
  const wchar_t *v39; // [rsp+68h] [rbp-61h]
  VARIANTARG v40; // [rsp+70h] [rbp-59h] BYREF
  __int128 v41; // [rsp+90h] [rbp-39h] BYREF
  IRecordInfo *pRecInfo; // [rsp+A0h] [rbp-29h]
  VARIANTARG v43; // [rsp+B0h] [rbp-19h] BYREF
  VARIANTARG v44; // [rsp+D0h] [rbp+7h] BYREF
  __int16 v45; // [rsp+140h] [rbp+77h] BYREF
  PVOID pv; // [rsp+148h] [rbp+7Fh]

  pv = a4;
  v4 = 0;
  pvarg.pRecInfo = 0;
  v35 = 0;
  v36 = 0;
  v34 = 0;
  v37 = 0;
  v9 = L"TRUE";
  if ( !a3 )
    v9 = L"FALSE";
  v39 = v9;
  *(_OWORD *)&pvarg.vt = 0;
  v10 = 0;
  v11 = 0;
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: started. Task: \"%s\\%s\". enableTask: %s.",
    L"WJSetScheduledTaskState",
    psz,
    a2,
    v9);
  VariantInit(&pvarg);
  WJCloseSetTaskStateRetryTimer(a4);
  v12 = CoInitializeEx(0, 0);
  v13 = v12;
  if ( v12 < 0 )
  {
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Failed to call CoInitializeEx. Failed with code 0x%08x\n",
      L"WJSetScheduledTaskState",
      (unsigned int)v12);
    goto LABEL_37;
  }
  v4 = 1;
  v14 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v35);
  v13 = v14;
  if ( v14 >= 0 )
  {
    v41 = *(_OWORD *)&pvarg.vt;
    v15 = *(_QWORD *)v35;
    pRecInfo = pvarg.pRecInfo;
    v43 = pvarg;
    v16 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v15 + 80);
    v44 = pvarg;
    v40 = pvarg;
    v17 = v16(v35, &v40, &v44, &v43, &v41);
    v13 = v17;
    if ( v17 < 0 )
    {
      DsrWriteAutoJoinSvcAdminEvent(
        L"AutoJoinSvc/%s: ITaskService::Connect failed with code 0x%08x\n",
        L"WJSetScheduledTaskState",
        (unsigned int)v17);
      goto LABEL_37;
    }
    v18 = SysAllocString(psz);
    v10 = v18;
    if ( !v18 )
    {
      v19 = psz;
      v20 = L"AutoJoinSvc/%s: Failed to allocate task folder name \"%s\".";
LABEL_12:
      v13 = -2147024882;
      DsrWriteAutoJoinSvcAdminEvent(v20, L"WJSetScheduledTaskState", v19);
      goto LABEL_37;
    }
    v21 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v35 + 56LL))(v35, v18, &v36);
    v13 = v21;
    if ( v21 < 0 )
    {
      DsrWriteAutoJoinSvcAdminEvent(
        L"AutoJoinSvc/%s: ITaskService::GetFolder(\"%s\") failed with code 0x%08x.",
        L"WJSetScheduledTaskState",
        psz,
        (unsigned int)v21);
      goto LABEL_37;
    }
    v22 = SysAllocString(a2);
    v11 = v22;
    if ( !v22 )
    {
      v19 = a2;
      v20 = L"AutoJoinSvc/%s: Failed to allocate task name \"%s\".";
      goto LABEL_12;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 **))(*(_QWORD *)v36 + 104LL))(v36, v22, &v34);
    if ( v13 < 0 )
    {
      v23 = L"AutoJoinSvc/%s: ITaskService::GetTask(\"%s\\%s\") failed with code 0x%08x.";
LABEL_19:
      LODWORD(ppv) = v13;
      DsrWriteAutoJoinSvcAdminEvent(v23, L"WJSetScheduledTaskState", psz, a2, ppv);
      goto LABEL_37;
    }
    if ( !v34 )
      goto LABEL_42;
    v45 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v34 + 80))(v34, &v45);
    v13 = v24;
    if ( v24 >= 0 )
    {
      if ( a3 == v45 )
      {
        v27 = L"enabled";
        if ( !a3 )
          v27 = L"disabled";
        DsrWriteAutoJoinSvcDebugEvent(
          L"AutoJoinSvc/%s: The task \"%s\\%s\" is already %s.",
          L"WJSetScheduledTaskState",
          psz,
          a2,
          v27);
LABEL_27:
        if ( a3 != 0xFFFF )
          goto LABEL_42;
        v26 = *v34;
        v40 = pvarg;
        v13 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64 *))(v26 + 96))(v34, &v40, &v37);
        DsrWriteAutoJoinSvcAdminEvent(L"AutoJoinSvc/%s: Running task \"%s\\%s\".", L"WJSetScheduledTaskState", psz, a2);
        if ( v13 >= 0 )
          goto LABEL_42;
        v23 = L"AutoJoinSvc/%s: IRegisteredTask_Run(\"%s\\%s\") failed with code 0x%08x.";
        goto LABEL_19;
      }
    }
    else
    {
      LODWORD(ppv) = v24;
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: IRegisteredTask_get_Enabled(\"%s\\%s\") failed with code 0x%08x.",
        L"WJSetScheduledTaskState",
        psz,
        a2,
        ppv);
    }
    v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v34 + 88))(v34, a3);
    if ( v13 < 0 )
    {
      v28 = L"enable";
      if ( !a3 )
        v28 = L"disable";
      DsrWriteAutoJoinSvcAdminEvent(
        L"AutoJoinSvc/%s: Failed to %s task \"%s\\%s\" with error code 0x%08x.",
        L"WJSetScheduledTaskState",
        v28,
        psz,
        a2,
        v13);
      goto LABEL_37;
    }
    v25 = L"enabled";
    if ( !a3 )
      v25 = L"disabled";
    DsrWriteAutoJoinSvcAdminEvent(
      L"AutoJoinSvc/%s: Successfuly %s task \"%s\\%s\".",
      L"WJSetScheduledTaskState",
      v25,
      psz,
      a2);
    goto LABEL_27;
  }
  DsrWriteAutoJoinSvcAdminEvent(
    L"AutoJoinSvc/%s: Failed to create an instance of the TaskService class: 0x%08x\n",
    L"WJSetScheduledTaskState",
    (unsigned int)v14);
LABEL_37:
  if ( pv )
  {
    v29 = WJOpenSetTaskStateRetryTimer(pv);
    if ( v29 )
    {
      LODWORD(v33) = v29;
      v30 = L"enabling";
      if ( !a3 )
        v30 = L"disabling";
      DsrWriteAutoJoinSvcAdminEvent(
        L"AutoJoinSvc/%s: Failed to create thread-pool timer to retry %s task \"%s\\%s\". Status 0x%08x.",
        L"WJSetScheduledTaskState",
        v30,
        psz,
        a2,
        v33);
    }
  }
LABEL_42:
  SysFreeString(v10);
  SysFreeString(v11);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v34 )
    (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v35 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v4 )
    CoUninitialize();
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: finished - hr: 0x%08x.  Task: \"%s\\%s\". enableTask: %s.",
    L"WJSetScheduledTaskState",
    (unsigned int)v13,
    psz,
    a2,
    v39);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002ba14  mov     [rsp-8+arg_0], rbx
0x18002ba19  mov     [rsp-8+pv], r9
0x18002ba1e  push    rbp
0x18002ba1f  push    rsi
0x18002ba20  push    rdi
0x18002ba21  push    r12
0x18002ba23  push    r13
0x18002ba25  push    r14
0x18002ba27  push    r15
0x18002ba29  lea     rbp, [rsp-27h]
0x18002ba2e  sub     rsp, 0F0h
0x18002ba35  xor     r13d, r13d
0x18002ba38  xor     eax, eax
0x18002ba3a  mov     rdi, rcx
0x18002ba3d  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002ba41  test    r8w, r8w
0x18002ba45  mov     [rsp+120h+var_E8], r13
0x18002ba4a  lea     rcx, aFalse_0; "FALSE"
0x18002ba51  mov     [rsp+120h+var_E0], r13
0x18002ba56  mov     rbx, r9
0x18002ba59  mov     [rsp+120h+var_F0], r13
0x18002ba5e  movzx   r14d, r8w
0x18002ba62  mov     [rsp+120h+var_D8], r13
0x18002ba67  mov     rsi, rdx
0x18002ba6a  lea     rax, aTrue_0; "TRUE"
0x18002ba71  cmovz   rax, rcx
0x18002ba75  xorps   xmm0, xmm0
0x18002ba78  mov     r9, rdx
0x18002ba7b  mov     [rbp+57h+var_B8], rax
0x18002ba7f  lea     rcx, aAutojoinsvcSSt_2; "AutoJoinSvc/%s: started. Task: \"%s\\%s"...
0x18002ba86  mov     [rsp+120h+ppv], rax
0x18002ba8b  mov     r8, rdi
0x18002ba8e  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002ba95  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002ba99  mov     r15d, r13d
0x18002ba9c  mov     r12d, r13d
0x18002ba9f  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002baa5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002baa9  call    cs:__imp_VariantInit
0x18002baaf  mov     rcx, rbx
0x18002bab2  call    WJCloseSetTaskStateRetryTimer
0x18002bab7  xor     edx, edx; dwCoInit
0x18002bab9  xor     ecx, ecx; pvReserved
0x18002babb  call    cs:__imp_CoInitializeEx
0x18002bac1  mov     ebx, eax
0x18002bac3  test    eax, eax
0x18002bac5  jns     short loc_18002BAE3
0x18002bac7  lea     rcx, aAutojoinsvcSFa_7; "AutoJoinSvc/%s: Failed to call CoInitia"...
0x18002bace  mov     r8d, eax
0x18002bad1  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002bad8  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002bade  jmp     loc_18002BDC4
0x18002bae3  lea     rax, [rsp+120h+var_E8]
0x18002bae8  mov     r13d, 1
0x18002baee  mov     r8d, r13d; dwClsContext
0x18002baf1  mov     [rsp+120h+ppv], rax; ppv
0x18002baf6  lea     r9, IID_ITaskService; riid
0x18002bafd  xor     edx, edx; pUnkOuter
0x18002baff  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002bb06  call    cs:__imp_CoCreateInstance
0x18002bb0c  mov     ebx, eax
0x18002bb0e  test    eax, eax
0x18002bb10  jns     short loc_18002BB1B
0x18002bb12  lea     rcx, aAutojoinsvcSFa_17; "AutoJoinSvc/%s: Failed to create an ins"...
0x18002bb19  jmp     short loc_18002BACE
0x18002bb1b  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18002bb1f  lea     rdx, [rbp+57h+var_90]
0x18002bb23  mov     rcx, [rsp+120h+var_E8]
0x18002bb28  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18002bb2d  lea     r9, [rbp+57h+var_70]
0x18002bb31  mov     [rsp+120h+ppv], rdx
0x18002bb36  lea     r8, [rbp+57h+var_50]
0x18002bb3a  lea     rdx, [rbp+57h+var_B0]
0x18002bb3e  movaps  [rbp+57h+var_90], xmm1
0x18002bb42  mov     rax, [rcx]
0x18002bb45  movsd   [rbp+57h+var_80], xmm0
0x18002bb4a  movaps  [rbp+57h+var_70], xmm1
0x18002bb4e  movsd   [rbp+57h+var_60], xmm0
0x18002bb53  mov     rax, [rax+50h]
0x18002bb57  movaps  [rbp+57h+var_50], xmm1
0x18002bb5b  movsd   [rbp+57h+var_40], xmm0
0x18002bb60  movaps  [rbp+57h+var_B0], xmm1
0x18002bb64  movsd   [rbp+57h+var_A0], xmm0
0x18002bb69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb6e  mov     ebx, eax
0x18002bb70  test    eax, eax
0x18002bb72  jns     short loc_18002BB80
0x18002bb74  lea     rcx, aAutojoinsvcSIt_1; "AutoJoinSvc/%s: ITaskService::Connect f"...
0x18002bb7b  jmp     loc_18002BACE
0x18002bb80  mov     rcx, rdi; psz
0x18002bb83  call    cs:__imp_SysAllocString
0x18002bb89  mov     r15, rax
0x18002bb8c  test    rax, rax
0x18002bb8f  jnz     short loc_18002BBB2
0x18002bb91  mov     r8, rdi
0x18002bb94  lea     rcx, aAutojoinsvcSFa; "AutoJoinSvc/%s: Failed to allocate task"...
0x18002bb9b  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002bba2  mov     ebx, 8007000Eh
0x18002bba7  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002bbad  jmp     loc_18002BDC4
0x18002bbb2  mov     rcx, [rsp+120h+var_E8]
0x18002bbb7  lea     r8, [rsp+120h+var_E0]
0x18002bbbc  mov     rdx, r15
0x18002bbbf  mov     rax, [rcx]
0x18002bbc2  mov     rax, [rax+38h]
0x18002bbc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbcb  mov     ebx, eax
0x18002bbcd  test    eax, eax
0x18002bbcf  jns     short loc_18002BBF0
0x18002bbd1  mov     r9d, eax
0x18002bbd4  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002bbdb  mov     r8, rdi
0x18002bbde  lea     rcx, aAutojoinsvcSIt_0; "AutoJoinSvc/%s: ITaskService::GetFolder"...
0x18002bbe5  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002bbeb  jmp     loc_18002BDC4
0x18002bbf0  mov     rcx, rsi; psz
0x18002bbf3  call    cs:__imp_SysAllocString
0x18002bbf9  mov     r12, rax
0x18002bbfc  test    rax, rax
0x18002bbff  jnz     short loc_18002BC0D
0x18002bc01  mov     r8, rsi
0x18002bc04  lea     rcx, aAutojoinsvcSFa_5; "AutoJoinSvc/%s: Failed to allocate task"...
0x18002bc0b  jmp     short loc_18002BB9B
0x18002bc0d  mov     rcx, [rsp+120h+var_E0]
0x18002bc12  lea     r8, [rsp+120h+var_F0]
0x18002bc17  mov     rdx, r12
0x18002bc1a  mov     rax, [rcx]
0x18002bc1d  mov     rax, [rax+68h]
0x18002bc21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc26  mov     ebx, eax
0x18002bc28  xor     eax, eax
0x18002bc2a  test    ebx, ebx
0x18002bc2c  jns     short loc_18002BC51
0x18002bc2e  lea     rcx, aAutojoinsvcSIt; "AutoJoinSvc/%s: ITaskService::GetTask("...
0x18002bc35  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002bc3c  mov     dword ptr [rsp+120h+ppv], ebx
0x18002bc40  mov     r8, rdi
0x18002bc43  mov     r9, rsi
0x18002bc46  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002bc4c  jmp     loc_18002BDC4
0x18002bc51  mov     rcx, [rsp+120h+var_F0]
0x18002bc56  test    rcx, rcx
0x18002bc59  jz      loc_18002BE16
0x18002bc5f  mov     [rbp+57h+arg_10], ax
0x18002bc63  lea     rdx, [rbp+57h+arg_10]
0x18002bc67  mov     rax, [rcx]
0x18002bc6a  mov     rax, [rax+50h]
0x18002bc6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc73  mov     ebx, eax
0x18002bc75  test    eax, eax
0x18002bc77  jns     loc_18002BD53
0x18002bc7d  mov     r9, rsi
0x18002bc80  mov     dword ptr [rsp+120h+ppv], eax
0x18002bc84  mov     r8, rdi
0x18002bc87  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002bc8e  lea     rcx, aAutojoinsvcSIr; "AutoJoinSvc/%s: IRegisteredTask_get_Ena"...
0x18002bc95  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002bc9b  mov     rcx, [rsp+120h+var_F0]
0x18002bca0  movzx   edx, r14w
0x18002bca4  mov     rax, [rcx]
0x18002bca7  mov     rax, [rax+58h]
0x18002bcab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcb0  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002bcb7  mov     ebx, eax
0x18002bcb9  mov     r9, rdi
0x18002bcbc  test    eax, eax
0x18002bcbe  js      loc_18002BD98
0x18002bcc4  test    r14w, r14w
0x18002bcc8  mov     [rsp+120h+ppv], rsi
0x18002bccd  lea     rax, aDisabled; "disabled"
0x18002bcd4  lea     r8, aEnabled; "enabled"
0x18002bcdb  cmovz   r8, rax
0x18002bcdf  lea     rcx, aAutojoinsvcSSu_0; "AutoJoinSvc/%s: Successfuly %s task \"%"...
0x18002bce6  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002bcec  cmp     r14w, 0FFFFh
0x18002bcf1  jnz     loc_18002BE16
0x18002bcf7  mov     rcx, [rsp+120h+var_F0]
0x18002bcfc  lea     r8, [rsp+120h+var_D8]
0x18002bd01  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18002bd05  lea     rdx, [rbp+57h+var_B0]
0x18002bd09  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18002bd0e  mov     rax, [rcx]
0x18002bd11  movaps  [rbp+57h+var_B0], xmm0
0x18002bd15  movsd   [rbp+57h+var_A0], xmm1
0x18002bd1a  mov     rax, [rax+60h]
0x18002bd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd23  mov     r9, rsi
0x18002bd26  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002bd2d  mov     r8, rdi
0x18002bd30  lea     rcx, aAutojoinsvcSRu; "AutoJoinSvc/%s: Running task \"%s\\%s\""...
0x18002bd37  mov     ebx, eax
0x18002bd39  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002bd3f  test    ebx, ebx
0x18002bd41  jns     loc_18002BE16
0x18002bd47  lea     rcx, aAutojoinsvcSIr_0; "AutoJoinSvc/%s: IRegisteredTask_Run(\"%"...
0x18002bd4e  jmp     loc_18002BC35
0x18002bd53  cmp     r14w, [rbp+57h+arg_10]
0x18002bd58  jnz     loc_18002BC9B
0x18002bd5e  test    r14w, r14w
0x18002bd62  lea     rax, aDisabled; "disabled"
0x18002bd69  lea     r8, aEnabled; "enabled"
0x18002bd70  mov     r9, rsi
0x18002bd73  cmovz   r8, rax
0x18002bd77  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002bd7e  mov     [rsp+120h+ppv], r8
0x18002bd83  lea     rcx, aAutojoinsvcSTh_1; "AutoJoinSvc/%s: The task \"%s\\%s\" is "...
0x18002bd8a  mov     r8, rdi
0x18002bd8d  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002bd93  jmp     loc_18002BCEC
0x18002bd98  test    r14w, r14w
0x18002bd9c  mov     dword ptr [rsp+120h+var_F8], ebx
0x18002bda0  lea     rax, aDisable; "disable"
0x18002bda7  mov     [rsp+120h+ppv], rsi
0x18002bdac  lea     r8, aEnable; "enable"
0x18002bdb3  cmovz   r8, rax
0x18002bdb7  lea     rcx, aAutojoinsvcSFa_2; "AutoJoinSvc/%s: Failed to %s task \"%s"...
0x18002bdbe  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002bdc4  mov     rcx, [rbp+57h+pv]; pv
0x18002bdc8  test    rcx, rcx
0x18002bdcb  jz      short loc_18002BE16
0x18002bdcd  movzx   r9d, r14w
0x18002bdd1  mov     r8, rsi
0x18002bdd4  mov     rdx, rdi
0x18002bdd7  call    WJOpenSetTaskStateRetryTimer
0x18002bddc  test    eax, eax
0x18002bdde  jz      short loc_18002BE16
0x18002bde0  test    r14w, r14w
0x18002bde4  mov     dword ptr [rsp+120h+var_F8], eax
0x18002bde8  lea     rcx, aDisabling; "disabling"
0x18002bdef  mov     [rsp+120h+ppv], rsi
0x18002bdf4  lea     r8, aEnabling; "enabling"
0x18002bdfb  mov     r9, rdi
0x18002bdfe  cmovz   r8, rcx
0x18002be02  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002be09  lea     rcx, aAutojoinsvcSFa_19; "AutoJoinSvc/%s: Failed to create thread"...
0x18002be10  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002be16  mov     rcx, r15; bstrString
0x18002be19  call    cs:__imp_SysFreeString
0x18002be1f  mov     rcx, r12; bstrString
0x18002be22  call    cs:__imp_SysFreeString
0x18002be28  mov     rcx, [rsp+120h+var_D8]
0x18002be2d  test    rcx, rcx
0x18002be30  jz      short loc_18002BE3E
0x18002be32  mov     rax, [rcx]
0x18002be35  mov     rax, [rax+10h]
0x18002be39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be3e  mov     rcx, [rsp+120h+var_F0]
0x18002be43  test    rcx, rcx
0x18002be46  jz      short loc_18002BE54
0x18002be48  mov     rax, [rcx]
0x18002be4b  mov     rax, [rax+10h]
0x18002be4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be54  mov     rcx, [rsp+120h+var_E0]
0x18002be59  test    rcx, rcx
0x18002be5c  jz      short loc_18002BE6A
0x18002be5e  mov     rax, [rcx]
0x18002be61  mov     rax, [rax+10h]
0x18002be65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be6a  mov     rcx, [rsp+120h+var_E8]
0x18002be6f  test    rcx, rcx
0x18002be72  jz      short loc_18002BE80
0x18002be74  mov     rax, [rcx]
0x18002be77  mov     rax, [rax+10h]
0x18002be7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be80  test    r13d, r13d
0x18002be83  jz      short loc_18002BE8B
0x18002be85  call    cs:__imp_CoUninitialize
0x18002be8b  mov     rax, [rbp+57h+var_B8]
0x18002be8f  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002be96  mov     [rsp+120h+var_F8], rax
0x18002be9b  lea     rcx, aAutojoinsvcSFi_1; "AutoJoinSvc/%s: finished - hr: 0x%08x. "...
0x18002bea2  mov     r9, rdi
0x18002bea5  mov     [rsp+120h+ppv], rsi
0x18002beaa  mov     r8d, ebx
0x18002bead  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002beb3  mov     eax, ebx
0x18002beb5  mov     rbx, [rsp+120h+arg_0]
0x18002bebd  add     rsp, 0F0h
0x18002bec4  pop     r15
0x18002bec6  pop     r14
0x18002bec8  pop     r13
0x18002beca  pop     r12
0x18002becc  pop     rdi
0x18002becd  pop     rsi
0x18002bece  pop     rbp
0x18002becf  retn
```
