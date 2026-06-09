# WJSetScheduledTaskState

- ea: `0x18002e16c`
- end: `0x18002e6a4`
- name: `WJSetScheduledTaskState`
- size: `1336`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180012368`
- `0x18001eb30`
- `0x18001f3f0`
- `0x18002e790`

## callees

- `0x18002d9dc`
- `0x18002dcfc`
- `0x18002e16c`
- `0x180037010`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e242`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e323`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e367`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e3d7`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e483`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e4dc`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e56d`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e5c5`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e242`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e323`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e367`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e3d7`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e483`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e4dc`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e56d`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002e5c5`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e1f7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e42c`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e536`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e67a`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e1f7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e42c`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e536`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e67a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e276`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e276`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002e64c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002e64c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002e21f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002e21f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e2f9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e37b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e2f9`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e37b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e5d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e5e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e5d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e5e3`
- `OLEAUT32!__imp_VariantInit` at `0x18002e207`
- `OLEAUT32!__imp_VariantInit` at `0x18002e207`

## string_xrefs

- `0x18002e1e6`: `WJSetScheduledTaskState`
- `0x18002e23b`: `WJSetScheduledTaskState`
- `0x18002e317`: `WJSetScheduledTaskState`
- `0x18002e356`: `WJSetScheduledTaskState`
- `0x18002e3c6`: `WJSetScheduledTaskState`
- `0x18002e41e`: `WJSetScheduledTaskState`
- `0x18002e44d`: `WJSetScheduledTaskState`
- `0x18002e4c9`: `WJSetScheduledTaskState`
- `0x18002e520`: `WJSetScheduledTaskState`
- `0x18002e5b7`: `WJSetScheduledTaskState`
- `0x18002e65c`: `WJSetScheduledTaskState`
- `0x18002e1d7`: `AutoJoinSvc/%s: started. Task: "%s\%s". enableTask: %s.`
- `0x18002e288`: `AutoJoinSvc/%s: Failed to create an instance of the TaskService class: 0x%08x\n`
- `0x18002e2ea`: `AutoJoinSvc/%s: ITaskService::Connect failed with code 0x%08x\n`
- `0x18002e310`: `AutoJoinSvc/%s: Failed to allocate task folder name "%s".`
- `0x18002e360`: `AutoJoinSvc/%s: ITaskService::GetFolder("%s") failed with code 0x%08x.`
- `0x18002e392`: `AutoJoinSvc/%s: Failed to allocate task name "%s".`
- `0x18002e3bf`: `AutoJoinSvc/%s: ITaskService::GetTask("%s\%s") failed with code 0x%08x.`
- `0x18002e425`: `AutoJoinSvc/%s: IRegisteredTask_get_Enabled("%s\%s") failed with code 0x%08x.`
- `0x18002e52c`: `AutoJoinSvc/%s: The task "%s\%s" is already %s.`
- `0x18002e47c`: `AutoJoinSvc/%s: Successfuly %s task "%s\%s".`
- `0x18002e566`: `AutoJoinSvc/%s: Failed to %s task "%s\%s" with error code 0x%08x.`
- `0x18002e4d3`: `AutoJoinSvc/%s: Running task "%s\%s".`
- `0x18002e4f0`: `AutoJoinSvc/%s: IRegisteredTask_Run("%s\%s") failed with code 0x%08x.`
- `0x18002e5be`: `AutoJoinSvc/%s: Failed to create thread-pool timer to retry %s task "%s\%s". Status 0x%08x.`
- `0x18002e668`: `AutoJoinSvc/%s: finished - hr: 0x%08x.  Task: "%s\%s". enableTask: %s.`

## pseudocode

```c
__int64 __fastcall WJSetScheduledTaskState(OLECHAR *psz, OLECHAR *a2, unsigned __int16 a3, void *a4)
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
0x18002e16c  mov     [rsp-8+arg_0], rbx
0x18002e171  mov     [rsp-8+pv], r9
0x18002e176  push    rbp
0x18002e177  push    rsi
0x18002e178  push    rdi
0x18002e179  push    r12
0x18002e17b  push    r13
0x18002e17d  push    r14
0x18002e17f  push    r15
0x18002e181  lea     rbp, [rsp-27h]
0x18002e186  sub     rsp, 0F0h
0x18002e18d  xor     r13d, r13d
0x18002e190  xor     eax, eax
0x18002e192  mov     rdi, rcx
0x18002e195  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002e199  test    r8w, r8w
0x18002e19d  mov     [rsp+120h+var_E8], r13
0x18002e1a2  lea     rcx, aFalse_0; "FALSE"
0x18002e1a9  mov     [rsp+120h+var_E0], r13
0x18002e1ae  mov     rbx, r9
0x18002e1b1  mov     [rsp+120h+var_F0], r13
0x18002e1b6  movzx   r14d, r8w
0x18002e1ba  mov     [rsp+120h+var_D8], r13
0x18002e1bf  mov     rsi, rdx
0x18002e1c2  lea     rax, aTrue_0; "TRUE"
0x18002e1c9  cmovz   rax, rcx
0x18002e1cd  xorps   xmm0, xmm0
0x18002e1d0  mov     r9, rdx
0x18002e1d3  mov     [rbp+57h+var_B8], rax
0x18002e1d7  lea     rcx, aAutojoinsvcSSt_2; "AutoJoinSvc/%s: started. Task: \"%s\\%s"...
0x18002e1de  mov     [rsp+120h+ppv], rax
0x18002e1e3  mov     r8, rdi
0x18002e1e6  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e1ed  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18002e1f1  mov     r15d, r13d
0x18002e1f4  mov     r12d, r13d
0x18002e1f7  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e1fe  nop     dword ptr [rax+rax+00h]
0x18002e203  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002e207  call    cs:__imp_VariantInit
0x18002e20e  nop     dword ptr [rax+rax+00h]
0x18002e213  mov     rcx, rbx
0x18002e216  call    WJCloseSetTaskStateRetryTimer
0x18002e21b  xor     edx, edx; dwCoInit
0x18002e21d  xor     ecx, ecx; pvReserved
0x18002e21f  call    cs:__imp_CoInitializeEx
0x18002e226  nop     dword ptr [rax+rax+00h]
0x18002e22b  mov     ebx, eax
0x18002e22d  test    eax, eax
0x18002e22f  jns     short loc_18002E253
0x18002e231  lea     rcx, aAutojoinsvcSFa_7; "AutoJoinSvc/%s: Failed to call CoInitia"...
0x18002e238  mov     r8d, eax
0x18002e23b  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e242  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e249  nop     dword ptr [rax+rax+00h]
0x18002e24e  jmp     loc_18002E579
0x18002e253  lea     rax, [rsp+120h+var_E8]
0x18002e258  mov     r13d, 1
0x18002e25e  mov     r8d, r13d; dwClsContext
0x18002e261  mov     [rsp+120h+ppv], rax; ppv
0x18002e266  lea     r9, IID_ITaskService; riid
0x18002e26d  xor     edx, edx; pUnkOuter
0x18002e26f  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002e276  call    cs:__imp_CoCreateInstance
0x18002e27d  nop     dword ptr [rax+rax+00h]
0x18002e282  mov     ebx, eax
0x18002e284  test    eax, eax
0x18002e286  jns     short loc_18002E291
0x18002e288  lea     rcx, aAutojoinsvcSFa_17; "AutoJoinSvc/%s: Failed to create an ins"...
0x18002e28f  jmp     short loc_18002E238
0x18002e291  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18002e295  lea     rdx, [rbp+57h+var_90]
0x18002e299  mov     rcx, [rsp+120h+var_E8]
0x18002e29e  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18002e2a3  lea     r9, [rbp+57h+var_70]
0x18002e2a7  mov     [rsp+120h+ppv], rdx
0x18002e2ac  lea     r8, [rbp+57h+var_50]
0x18002e2b0  lea     rdx, [rbp+57h+var_B0]
0x18002e2b4  movaps  [rbp+57h+var_90], xmm1
0x18002e2b8  mov     rax, [rcx]
0x18002e2bb  movsd   [rbp+57h+var_80], xmm0
0x18002e2c0  movaps  [rbp+57h+var_70], xmm1
0x18002e2c4  movsd   [rbp+57h+var_60], xmm0
0x18002e2c9  mov     rax, [rax+50h]
0x18002e2cd  movaps  [rbp+57h+var_50], xmm1
0x18002e2d1  movsd   [rbp+57h+var_40], xmm0
0x18002e2d6  movaps  [rbp+57h+var_B0], xmm1
0x18002e2da  movsd   [rbp+57h+var_A0], xmm0
0x18002e2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2e4  mov     ebx, eax
0x18002e2e6  test    eax, eax
0x18002e2e8  jns     short loc_18002E2F6
0x18002e2ea  lea     rcx, aAutojoinsvcSIt_1; "AutoJoinSvc/%s: ITaskService::Connect f"...
0x18002e2f1  jmp     loc_18002E238
0x18002e2f6  mov     rcx, rdi; psz
0x18002e2f9  call    cs:__imp_SysAllocString
0x18002e300  nop     dword ptr [rax+rax+00h]
0x18002e305  mov     r15, rax
0x18002e308  test    rax, rax
0x18002e30b  jnz     short loc_18002E334
0x18002e30d  mov     r8, rdi
0x18002e310  lea     rcx, aAutojoinsvcSFa; "AutoJoinSvc/%s: Failed to allocate task"...
0x18002e317  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e31e  mov     ebx, 8007000Eh
0x18002e323  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e32a  nop     dword ptr [rax+rax+00h]
0x18002e32f  jmp     loc_18002E579
0x18002e334  mov     rcx, [rsp+120h+var_E8]
0x18002e339  lea     r8, [rsp+120h+var_E0]
0x18002e33e  mov     rdx, r15
0x18002e341  mov     rax, [rcx]
0x18002e344  mov     rax, [rax+38h]
0x18002e348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e34d  mov     ebx, eax
0x18002e34f  test    eax, eax
0x18002e351  jns     short loc_18002E378
0x18002e353  mov     r9d, eax
0x18002e356  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e35d  mov     r8, rdi
0x18002e360  lea     rcx, aAutojoinsvcSIt_0; "AutoJoinSvc/%s: ITaskService::GetFolder"...
0x18002e367  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e36e  nop     dword ptr [rax+rax+00h]
0x18002e373  jmp     loc_18002E579
0x18002e378  mov     rcx, rsi; psz
0x18002e37b  call    cs:__imp_SysAllocString
0x18002e382  nop     dword ptr [rax+rax+00h]
0x18002e387  mov     r12, rax
0x18002e38a  test    rax, rax
0x18002e38d  jnz     short loc_18002E39E
0x18002e38f  mov     r8, rsi
0x18002e392  lea     rcx, aAutojoinsvcSFa_5; "AutoJoinSvc/%s: Failed to allocate task"...
0x18002e399  jmp     loc_18002E317
0x18002e39e  mov     rcx, [rsp+120h+var_E0]
0x18002e3a3  lea     r8, [rsp+120h+var_F0]
0x18002e3a8  mov     rdx, r12
0x18002e3ab  mov     rax, [rcx]
0x18002e3ae  mov     rax, [rax+68h]
0x18002e3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3b7  mov     ebx, eax
0x18002e3b9  xor     eax, eax
0x18002e3bb  test    ebx, ebx
0x18002e3bd  jns     short loc_18002E3E8
0x18002e3bf  lea     rcx, aAutojoinsvcSIt; "AutoJoinSvc/%s: ITaskService::GetTask("...
0x18002e3c6  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e3cd  mov     dword ptr [rsp+120h+ppv], ebx
0x18002e3d1  mov     r8, rdi
0x18002e3d4  mov     r9, rsi
0x18002e3d7  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e3de  nop     dword ptr [rax+rax+00h]
0x18002e3e3  jmp     loc_18002E579
0x18002e3e8  mov     rcx, [rsp+120h+var_F0]
0x18002e3ed  test    rcx, rcx
0x18002e3f0  jz      loc_18002E5D1
0x18002e3f6  mov     [rbp+57h+arg_10], ax
0x18002e3fa  lea     rdx, [rbp+57h+arg_10]
0x18002e3fe  mov     rax, [rcx]
0x18002e401  mov     rax, [rax+50h]
0x18002e405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e40a  mov     ebx, eax
0x18002e40c  test    eax, eax
0x18002e40e  jns     loc_18002E4FC
0x18002e414  mov     r9, rsi
0x18002e417  mov     dword ptr [rsp+120h+ppv], eax
0x18002e41b  mov     r8, rdi
0x18002e41e  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e425  lea     rcx, aAutojoinsvcSIr; "AutoJoinSvc/%s: IRegisteredTask_get_Ena"...
0x18002e42c  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e433  nop     dword ptr [rax+rax+00h]
0x18002e438  mov     rcx, [rsp+120h+var_F0]
0x18002e43d  movzx   edx, r14w
0x18002e441  mov     rax, [rcx]
0x18002e444  mov     rax, [rax+58h]
0x18002e448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e44d  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e454  mov     ebx, eax
0x18002e456  mov     r9, rdi
0x18002e459  test    eax, eax
0x18002e45b  js      loc_18002E547
0x18002e461  test    r14w, r14w
0x18002e465  mov     [rsp+120h+ppv], rsi
0x18002e46a  lea     rax, aDisabled; "disabled"
0x18002e471  lea     r8, aEnabled; "enabled"
0x18002e478  cmovz   r8, rax
0x18002e47c  lea     rcx, aAutojoinsvcSSu_0; "AutoJoinSvc/%s: Successfuly %s task \"%"...
0x18002e483  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e48a  nop     dword ptr [rax+rax+00h]
0x18002e48f  cmp     r14w, 0FFFFh
0x18002e494  jnz     loc_18002E5D1
0x18002e49a  mov     rcx, [rsp+120h+var_F0]
0x18002e49f  lea     r8, [rsp+120h+var_D8]
0x18002e4a4  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18002e4a8  lea     rdx, [rbp+57h+var_B0]
0x18002e4ac  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18002e4b1  mov     rax, [rcx]
0x18002e4b4  movaps  [rbp+57h+var_B0], xmm0
0x18002e4b8  movsd   [rbp+57h+var_A0], xmm1
0x18002e4bd  mov     rax, [rax+60h]
0x18002e4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4c6  mov     r9, rsi
0x18002e4c9  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e4d0  mov     r8, rdi
0x18002e4d3  lea     rcx, aAutojoinsvcSRu; "AutoJoinSvc/%s: Running task \"%s\\%s\""...
0x18002e4da  mov     ebx, eax
0x18002e4dc  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e4e3  nop     dword ptr [rax+rax+00h]
0x18002e4e8  test    ebx, ebx
0x18002e4ea  jns     loc_18002E5D1
0x18002e4f0  lea     rcx, aAutojoinsvcSIr_0; "AutoJoinSvc/%s: IRegisteredTask_Run(\"%"...
0x18002e4f7  jmp     loc_18002E3C6
0x18002e4fc  cmp     r14w, [rbp+57h+arg_10]
0x18002e501  jnz     loc_18002E438
0x18002e507  test    r14w, r14w
0x18002e50b  lea     rax, aDisabled; "disabled"
0x18002e512  lea     r8, aEnabled; "enabled"
0x18002e519  mov     r9, rsi
0x18002e51c  cmovz   r8, rax
0x18002e520  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e527  mov     [rsp+120h+ppv], r8
0x18002e52c  lea     rcx, aAutojoinsvcSTh_1; "AutoJoinSvc/%s: The task \"%s\\%s\" is "...
0x18002e533  mov     r8, rdi
0x18002e536  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e53d  nop     dword ptr [rax+rax+00h]
0x18002e542  jmp     loc_18002E48F
0x18002e547  test    r14w, r14w
0x18002e54b  mov     dword ptr [rsp+120h+var_F8], ebx
0x18002e54f  lea     rax, aDisable; "disable"
0x18002e556  mov     [rsp+120h+ppv], rsi
0x18002e55b  lea     r8, aEnable; "enable"
0x18002e562  cmovz   r8, rax
0x18002e566  lea     rcx, aAutojoinsvcSFa_2; "AutoJoinSvc/%s: Failed to %s task \"%s"...
0x18002e56d  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e574  nop     dword ptr [rax+rax+00h]
0x18002e579  mov     rcx, [rbp+57h+pv]; pv
0x18002e57d  test    rcx, rcx
0x18002e580  jz      short loc_18002E5D1
0x18002e582  movzx   r9d, r14w
0x18002e586  mov     r8, rsi
0x18002e589  mov     rdx, rdi
0x18002e58c  call    WJOpenSetTaskStateRetryTimer
0x18002e591  test    eax, eax
0x18002e593  jz      short loc_18002E5D1
0x18002e595  test    r14w, r14w
0x18002e599  mov     dword ptr [rsp+120h+var_F8], eax
0x18002e59d  lea     rcx, aDisabling; "disabling"
0x18002e5a4  mov     [rsp+120h+ppv], rsi
0x18002e5a9  lea     r8, aEnabling; "enabling"
0x18002e5b0  mov     r9, rdi
0x18002e5b3  cmovz   r8, rcx
0x18002e5b7  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e5be  lea     rcx, aAutojoinsvcSFa_19; "AutoJoinSvc/%s: Failed to create thread"...
0x18002e5c5  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002e5cc  nop     dword ptr [rax+rax+00h]
0x18002e5d1  mov     rcx, r15; bstrString
0x18002e5d4  call    cs:__imp_SysFreeString
0x18002e5db  nop     dword ptr [rax+rax+00h]
0x18002e5e0  mov     rcx, r12; bstrString
0x18002e5e3  call    cs:__imp_SysFreeString
0x18002e5ea  nop     dword ptr [rax+rax+00h]
0x18002e5ef  mov     rcx, [rsp+120h+var_D8]
0x18002e5f4  test    rcx, rcx
0x18002e5f7  jz      short loc_18002E605
0x18002e5f9  mov     rax, [rcx]
0x18002e5fc  mov     rax, [rax+10h]
0x18002e600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e605  mov     rcx, [rsp+120h+var_F0]
0x18002e60a  test    rcx, rcx
0x18002e60d  jz      short loc_18002E61B
0x18002e60f  mov     rax, [rcx]
0x18002e612  mov     rax, [rax+10h]
0x18002e616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e61b  mov     rcx, [rsp+120h+var_E0]
0x18002e620  test    rcx, rcx
0x18002e623  jz      short loc_18002E631
0x18002e625  mov     rax, [rcx]
0x18002e628  mov     rax, [rax+10h]
0x18002e62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e631  mov     rcx, [rsp+120h+var_E8]
0x18002e636  test    rcx, rcx
0x18002e639  jz      short loc_18002E647
0x18002e63b  mov     rax, [rcx]
0x18002e63e  mov     rax, [rax+10h]
0x18002e642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e647  test    r13d, r13d
0x18002e64a  jz      short loc_18002E658
0x18002e64c  call    cs:__imp_CoUninitialize
0x18002e653  nop     dword ptr [rax+rax+00h]
0x18002e658  mov     rax, [rbp+57h+var_B8]
0x18002e65c  lea     rdx, aWjsetscheduled; "WJSetScheduledTaskState"
0x18002e663  mov     [rsp+120h+var_F8], rax
0x18002e668  lea     rcx, aAutojoinsvcSFi_1; "AutoJoinSvc/%s: finished - hr: 0x%08x. "...
0x18002e66f  mov     r9, rdi
0x18002e672  mov     [rsp+120h+ppv], rsi
0x18002e677  mov     r8d, ebx
0x18002e67a  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e681  nop     dword ptr [rax+rax+00h]
0x18002e686  mov     eax, ebx
0x18002e688  mov     rbx, [rsp+120h+arg_0]
0x18002e690  add     rsp, 0F0h
0x18002e697  pop     r15
0x18002e699  pop     r14
  ... truncated ...
```
