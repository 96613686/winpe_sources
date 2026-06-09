# CWdsTransportNamespaceScheduledCastManualStart::InitializeRegisteredNamespaceWorker(_WDSTPT_NAMESPACE *)

- ea: `0x1800140a0`
- end: `0x180014105`
- name: `?InitializeRegisteredNamespaceWorker@CWdsTransportNamespaceScheduledCastManualStart@@EEAAJPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `101`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastManualStart *__hidden this, struct _WDSTPT_NAMESPACE *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800140bf`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800140f0`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800140bf`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800140f0`

## string_xrefs

- `0x1800140a9`: `-> CWdsTransportNamespaceScheduledCastManualStart::InitializeRegisteredNamespaceWorker(0x%p)`
- `0x1800140d0`: `<- CWdsTransportNamespaceScheduledCastManualStart::InitializeRegisteredNamespaceWorker(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespaceScheduledCastManualStart::InitializeRegisteredNamespaceWorker(
        CWdsTransportNamespaceScheduledCastManualStart *this,
        struct _WDSTPT_NAMESPACE *a2)
{
  int v4; // [rsp+20h] [rbp-18h]

  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastManualStart::InitializeRegisteredNamespaceWorker(0x%p)",
    this);
  v4 = 0;
  *((_DWORD *)this + 33) = 2;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastManualStart::InitializeRegisteredNamespaceWorker(0x%p) =%x",
    this,
    v4);
  return 0;
}

```

## disassembly

```asm
0x1800140a0  push    rbx
0x1800140a2  sub     rsp, 30h
0x1800140a6  mov     rbx, rcx
0x1800140a9  lea     r8, aCwdstransportn_30; "-> CWdsTransportNamespaceScheduledCastM"...
0x1800140b0  mov     r9, rcx
0x1800140b3  mov     edx, 10000h
0x1800140b8  lea     rcx, qword_18003B770
0x1800140bf  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800140c6  nop     dword ptr [rax+rax+00h]
0x1800140cb  and     [rsp+38h+var_18], 0
0x1800140d0  lea     r8, aCwdstransportn_31; "<- CWdsTransportNamespaceScheduledCastM"...
0x1800140d7  mov     r9, rbx
0x1800140da  mov     dword ptr [rbx+84h], 2
0x1800140e4  mov     edx, 10000h
0x1800140e9  lea     rcx, qword_18003B770
0x1800140f0  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800140f7  nop     dword ptr [rax+rax+00h]
0x1800140fc  xor     eax, eax
0x1800140fe  add     rsp, 30h
0x180014102  pop     rbx
0x180014103  retn
```
