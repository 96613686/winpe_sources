# UpdateScheduleTrigger(_GUID *,_TASK_TRIGGER *)

- ea: `0x18000d9f8`
- end: `0x18000db2b`
- name: `?UpdateScheduleTrigger@@YAJPEAU_GUID@@PEAU_TASK_TRIGGER@@@Z`
- size: `307`
- prototype: `int(struct _GUID *, struct _TASK_TRIGGER *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c7a4`
- `0x18000d63c`

## callees

- `0x18000af60`
- `0x18000af94`
- `0x18000ba94`
- `0x18000d9f8`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000da4d`
- `ole32!CoCreateInstance` at `0x18000da4d`
- `ole32!CoUninitialize` at `0x18000db16`
- `ole32!CoUninitialize` at `0x18000db16`
- `ole32!CoInitialize` at `0x18000da17`
- `ole32!CoInitialize` at `0x18000da17`

## pseudocode

```c
__int64 __fastcall UpdateScheduleTrigger(struct _GUID *a1, struct _TASK_TRIGGER *a2)
{
  HRESULT v4; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v7[8]; // [rsp+38h] [rbp-8h] BYREF
  __int64 v8; // [rsp+70h] [rbp+30h] BYREF
  __int64 v9; // [rsp+78h] [rbp+38h] BYREF

  ppv = 0;
  v4 = CoInitialize(0);
  if ( v4 >= 0 )
  {
    CWaitCursor::CWaitCursor((CWaitCursor *)v7);
    v4 = CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv);
    if ( v4 >= 0 )
    {
      v8 = 0;
      v4 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(
             ppv,
             a1,
             0,
             &v8);
      if ( v4 >= 0 )
      {
        v9 = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 96LL))(v8, &v9);
        if ( v4 >= 0 )
        {
          FixupRandomTrigger(a2);
          v4 = (*(__int64 (__fastcall **)(__int64, struct _TASK_TRIGGER *))(*(_QWORD *)v9 + 24LL))(v9, a2);
          if ( v4 >= 0 )
            v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 160LL))(v8);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CWaitCursor::~CWaitCursor((CWaitCursor *)v7);
    CoUninitialize();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d9f8  mov     [rsp-18h+arg_0], rbx
0x18000d9fd  push    rbp
0x18000d9fe  push    rsi
0x18000d9ff  push    rdi
0x18000da00  mov     rbp, rsp
0x18000da03  sub     rsp, 40h
0x18000da07  mov     rsi, rcx
0x18000da0a  mov     [rbp+var_10], 0
0x18000da12  xor     ecx, ecx; pvReserved
0x18000da14  mov     rdi, rdx
0x18000da17  call    cs:__imp_CoInitialize
0x18000da1d  mov     ebx, eax
0x18000da1f  test    eax, eax
0x18000da21  js      loc_18000DB1C
0x18000da27  lea     rcx, [rbp+var_8]; this
0x18000da2b  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x18000da30  xor     edx, edx; pUnkOuter
0x18000da32  lea     rax, [rbp+var_10]
0x18000da36  lea     r9, IID_ISyncScheduleMgr; riid
0x18000da3d  mov     [rsp+40h+ppv], rax; ppv
0x18000da42  lea     rcx, CLSID_SyncMgr; rclsid
0x18000da49  lea     r8d, [rdx+17h]; dwClsContext
0x18000da4d  call    cs:__imp_CoCreateInstance
0x18000da53  mov     ebx, eax
0x18000da55  test    eax, eax
0x18000da57  js      loc_18000DB0D
0x18000da5d  mov     rcx, [rbp+var_10]
0x18000da61  lea     r9, [rbp+arg_10]
0x18000da65  mov     [rbp+arg_10], 0
0x18000da6d  xor     r8d, r8d
0x18000da70  mov     rdx, rsi
0x18000da73  mov     rax, [rcx]
0x18000da76  mov     rax, [rax+28h]
0x18000da7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da7f  mov     ebx, eax
0x18000da81  test    eax, eax
0x18000da83  js      short loc_18000DAFD
0x18000da85  mov     rcx, [rbp+arg_10]
0x18000da89  lea     rdx, [rbp+arg_18]
0x18000da8d  mov     [rbp+arg_18], 0
0x18000da95  mov     rax, [rcx]
0x18000da98  mov     rax, [rax+60h]
0x18000da9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa1  mov     ebx, eax
0x18000daa3  test    eax, eax
0x18000daa5  js      short loc_18000DAED
0x18000daa7  mov     rcx, rdi; struct _TASK_TRIGGER *
0x18000daaa  call    ?FixupRandomTrigger@@YAXPEAU_TASK_TRIGGER@@@Z; FixupRandomTrigger(_TASK_TRIGGER *)
0x18000daaf  mov     rcx, [rbp+arg_18]
0x18000dab3  mov     rdx, rdi
0x18000dab6  mov     rax, [rcx]
0x18000dab9  mov     rax, [rax+18h]
0x18000dabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dac2  mov     ebx, eax
0x18000dac4  test    eax, eax
0x18000dac6  js      short loc_18000DADD
0x18000dac8  mov     rcx, [rbp+arg_10]
0x18000dacc  mov     rax, [rcx]
0x18000dacf  mov     rax, [rax+0A0h]
0x18000dad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dadb  mov     ebx, eax
0x18000dadd  mov     rcx, [rbp+arg_18]
0x18000dae1  mov     rax, [rcx]
0x18000dae4  mov     rax, [rax+10h]
0x18000dae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daed  mov     rcx, [rbp+arg_10]
0x18000daf1  mov     rax, [rcx]
0x18000daf4  mov     rax, [rax+10h]
0x18000daf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dafd  mov     rcx, [rbp+var_10]
0x18000db01  mov     rax, [rcx]
0x18000db04  mov     rax, [rax+10h]
0x18000db08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db0d  lea     rcx, [rbp+var_8]; this
0x18000db11  call    ??1CWaitCursor@@QEAA@XZ; CWaitCursor::~CWaitCursor(void)
0x18000db16  call    cs:__imp_CoUninitialize
0x18000db1c  mov     eax, ebx
0x18000db1e  mov     rbx, [rsp+40h+arg_0]
0x18000db23  add     rsp, 40h
0x18000db27  pop     rdi
0x18000db28  pop     rsi
0x18000db29  pop     rbp
0x18000db2a  retn
```
