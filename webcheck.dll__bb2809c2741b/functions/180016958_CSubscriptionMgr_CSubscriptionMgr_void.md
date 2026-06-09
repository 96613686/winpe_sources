# CSubscriptionMgr::~CSubscriptionMgr(void)

- ea: `0x180016958`
- end: `0x1800169f0`
- name: `??1CSubscriptionMgr@@AEAA@XZ`
- size: `152`
- prototype: `void __fastcall(CSubscriptionMgr *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180017c80`

## callees

- `0x180016958`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800169af`
- `KERNEL32!LocalFree` at `0x1800169af`
- `ole32!CoTaskMemFree` at `0x180016995`
- `ole32!CoTaskMemFree` at `0x180016995`

## pseudocode

```c
void __fastcall CSubscriptionMgr::~CSubscriptionMgr(CSubscriptionMgr *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &CSubscriptionMgr::`vftable'{for `IShellPropSheetExt'};
  *((_QWORD *)this + 1) = &CSubscriptionMgr::`vftable'{for `IShellExtInit'};
  *((_QWORD *)this + 2) = &CSubscriptionMgr::`vftable'{for `ISubscriptionMgr2'};
  *((_QWORD *)this + 3) = &CSubscriptionMgr::`vftable'{for `ISubscriptionMgrPriv'};
  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 659);
  if ( v3 )
  {
    LocalFree(v3);
    *((_QWORD *)this + 659) = 0;
  }
  v4 = *((_QWORD *)this + 660);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 660) = 0;
  }
  _InterlockedDecrement((volatile signed __int32 *)&g_cObj);
}

```

## disassembly

```asm
0x180016958  push    rbx
0x18001695a  sub     rsp, 20h
0x18001695e  lea     rax, ??_7CSubscriptionMgr@@6BIShellPropSheetExt@@@; const CSubscriptionMgr::`vftable'{for `IShellPropSheetExt'}
0x180016965  mov     rbx, rcx
0x180016968  mov     [rcx], rax
0x18001696b  lea     rax, ??_7CSubscriptionMgr@@6BIShellExtInit@@@; const CSubscriptionMgr::`vftable'{for `IShellExtInit'}
0x180016972  mov     [rcx+8], rax
0x180016976  lea     rax, ??_7CSubscriptionMgr@@6BISubscriptionMgr2@@@; const CSubscriptionMgr::`vftable'{for `ISubscriptionMgr2'}
0x18001697d  mov     [rcx+10h], rax
0x180016981  lea     rax, ??_7CSubscriptionMgr@@6BISubscriptionMgrPriv@@@; const CSubscriptionMgr::`vftable'{for `ISubscriptionMgrPriv'}
0x180016988  mov     [rcx+18h], rax
0x18001698c  mov     rcx, [rcx+28h]; pv
0x180016990  test    rcx, rcx
0x180016993  jz      short loc_1800169A3
0x180016995  call    cs:__imp_CoTaskMemFree
0x18001699b  mov     qword ptr [rbx+28h], 0
0x1800169a3  mov     rcx, [rbx+1498h]; hMem
0x1800169aa  test    rcx, rcx
0x1800169ad  jz      short loc_1800169C0
0x1800169af  call    cs:__imp_LocalFree
0x1800169b5  mov     qword ptr [rbx+1498h], 0
0x1800169c0  mov     rcx, [rbx+14A0h]
0x1800169c7  test    rcx, rcx
0x1800169ca  jz      short loc_1800169E3
0x1800169cc  mov     rax, [rcx]
0x1800169cf  mov     rax, [rax+10h]
0x1800169d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169d8  mov     qword ptr [rbx+14A0h], 0
0x1800169e3  lock dec cs:?g_cObj@@3KA; ulong g_cObj
0x1800169ea  add     rsp, 20h
0x1800169ee  pop     rbx
0x1800169ef  retn
```
