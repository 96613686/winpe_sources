# CreateSchedule(ushort const *,ulong,_GUID *,_TASK_TRIGGER *,int)

- ea: `0x18000b3fc`
- end: `0x18000b50c`
- name: `?CreateSchedule@@YAJPEBGKPEAU_GUID@@PEAU_TASK_TRIGGER@@H@Z`
- size: `272`
- prototype: `int(const unsigned __int16 *, unsigned int, struct _GUID *, struct _TASK_TRIGGER *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b208`
- `0x18000c7a4`
- `0x18000d63c`

## callees

- `0x18000af60`
- `0x18000af94`
- `0x18000b3fc`
- `0x18000d7e4`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000b45e`
- `ole32!CoCreateInstance` at `0x18000b45e`
- `ole32!CoUninitialize` at `0x18000b4f9`
- `ole32!CoUninitialize` at `0x18000b4f9`
- `ole32!CoInitialize` at `0x18000b426`
- `ole32!CoInitialize` at `0x18000b426`

## pseudocode

```c
__int64 __fastcall CreateSchedule(
        const unsigned __int16 *a1,
        unsigned int a2,
        struct _GUID *a3,
        struct _TASK_TRIGGER *a4,
        int a5)
{
  HRESULT v9; // ebx
  HRESULT v10; // eax
  struct ISyncSchedule *v12; // [rsp+30h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v14[56]; // [rsp+40h] [rbp-38h] BYREF

  ppv = 0;
  v12 = 0;
  v9 = CoInitialize(0);
  if ( v9 >= 0 )
  {
    CWaitCursor::CWaitCursor((CWaitCursor *)v14);
    v9 = CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv);
    if ( v9 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD, struct _GUID *, struct ISyncSchedule **))(*(_QWORD *)ppv + 24LL))(
              ppv,
              a1,
              0,
              a3,
              &v12);
      v9 = v10;
      if ( v10 == -2147024713 )
      {
        if ( a5 )
          v9 = 0;
      }
      else if ( !v10 )
      {
        v9 = SetScheduleValues(v12, a4, a2);
      }
      if ( v12 )
      {
        (*(void (__fastcall **)(struct ISyncSchedule *))(*(_QWORD *)v12 + 16LL))(v12);
        v12 = 0;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CWaitCursor::~CWaitCursor((CWaitCursor *)v14);
    CoUninitialize();
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b3fc  push    rbx
0x18000b3fe  push    rbp
0x18000b3ff  push    rsi
0x18000b400  push    rdi
0x18000b401  push    r14
0x18000b403  sub     rsp, 50h
0x18000b407  mov     r14, rcx
0x18000b40a  mov     [rsp+78h+var_40], 0
0x18000b413  xor     ecx, ecx; pvReserved
0x18000b415  mov     [rsp+78h+var_48], 0
0x18000b41e  mov     rdi, r9
0x18000b421  mov     rbp, r8
0x18000b424  mov     esi, edx
0x18000b426  call    cs:__imp_CoInitialize
0x18000b42c  mov     ebx, eax
0x18000b42e  test    eax, eax
0x18000b430  js      loc_18000B4FF
0x18000b436  lea     rcx, [rsp+78h+var_38]; this
0x18000b43b  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x18000b440  xor     edx, edx; pUnkOuter
0x18000b442  lea     rax, [rsp+78h+var_40]
0x18000b447  lea     r9, IID_ISyncScheduleMgr; riid
0x18000b44e  mov     [rsp+78h+ppv], rax; ppv
0x18000b453  lea     rcx, CLSID_SyncMgr; rclsid
0x18000b45a  lea     r8d, [rdx+17h]; dwClsContext
0x18000b45e  call    cs:__imp_CoCreateInstance
0x18000b464  mov     ebx, eax
0x18000b466  test    eax, eax
0x18000b468  js      loc_18000B4EF
0x18000b46e  mov     rcx, [rsp+78h+var_40]
0x18000b473  lea     rdx, [rsp+78h+var_48]
0x18000b478  mov     [rsp+78h+ppv], rdx
0x18000b47d  mov     r9, rbp
0x18000b480  xor     r8d, r8d
0x18000b483  mov     rdx, r14
0x18000b486  mov     rax, [rcx]
0x18000b489  mov     rax, [rax+18h]
0x18000b48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b492  mov     ebx, eax
0x18000b494  cmp     eax, 800700B7h
0x18000b499  jz      short loc_18000B4B3
0x18000b49b  test    eax, eax
0x18000b49d  jnz     short loc_18000B4BF
0x18000b49f  mov     rcx, [rsp+78h+var_48]; struct ISyncSchedule *
0x18000b4a4  mov     r8d, esi; unsigned int
0x18000b4a7  mov     rdx, rdi; struct _TASK_TRIGGER *
0x18000b4aa  call    ?SetScheduleValues@@YAJPEAUISyncSchedule@@PEAU_TASK_TRIGGER@@K@Z; SetScheduleValues(ISyncSchedule *,_TASK_TRIGGER *,ulong)
0x18000b4af  mov     ebx, eax
0x18000b4b1  jmp     short loc_18000B4BF
0x18000b4b3  xor     eax, eax
0x18000b4b5  cmp     [rsp+78h+arg_20], eax
0x18000b4bc  cmovnz  ebx, eax
0x18000b4bf  mov     rcx, [rsp+78h+var_48]
0x18000b4c4  test    rcx, rcx
0x18000b4c7  jz      short loc_18000B4DE
0x18000b4c9  mov     rax, [rcx]
0x18000b4cc  mov     rax, [rax+10h]
0x18000b4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4d5  mov     [rsp+78h+var_48], 0
0x18000b4de  mov     rcx, [rsp+78h+var_40]
0x18000b4e3  mov     rax, [rcx]
0x18000b4e6  mov     rax, [rax+10h]
0x18000b4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4ef  lea     rcx, [rsp+78h+var_38]; this
0x18000b4f4  call    ??1CWaitCursor@@QEAA@XZ; CWaitCursor::~CWaitCursor(void)
0x18000b4f9  call    cs:__imp_CoUninitialize
0x18000b4ff  mov     eax, ebx
0x18000b501  add     rsp, 50h
0x18000b505  pop     r14
0x18000b507  pop     rdi
0x18000b508  pop     rsi
0x18000b509  pop     rbp
0x18000b50a  pop     rbx
0x18000b50b  retn
```
