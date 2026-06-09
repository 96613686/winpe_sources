# CWdsTransportNamespaceScheduledCastAutoStart::InitializeNewNamespaceWorker(void)

- ea: `0x1800143b0`
- end: `0x180014415`
- name: `?InitializeNewNamespaceWorker@CWdsTransportNamespaceScheduledCastAutoStart@@EEAAJXZ`
- size: `101`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastAutoStart *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800143cf`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014400`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800143cf`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014400`

## string_xrefs

- `0x1800143b9`: `-> CWdsTransportNamespaceScheduledCastAutoStart::InitializeNewNamespaceWorker(0x%p)`
- `0x1800143e0`: `<- CWdsTransportNamespaceScheduledCastAutoStart::InitializeNewNamespaceWorker(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespaceScheduledCastAutoStart::InitializeNewNamespaceWorker(
        CWdsTransportNamespaceScheduledCastAutoStart *this)
{
  int v3; // [rsp+20h] [rbp-18h]

  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastAutoStart::InitializeNewNamespaceWorker(0x%p)",
    this);
  v3 = 0;
  *((_DWORD *)this + 33) = 3;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastAutoStart::InitializeNewNamespaceWorker(0x%p) =%x",
    this,
    v3);
  return 0;
}

```

## disassembly

```asm
0x1800143b0  push    rbx
0x1800143b2  sub     rsp, 30h
0x1800143b6  mov     rbx, rcx
0x1800143b9  lea     r8, aCwdstransportn_65; "-> CWdsTransportNamespaceScheduledCastA"...
0x1800143c0  mov     r9, rcx
0x1800143c3  mov     edx, 10000h
0x1800143c8  lea     rcx, qword_18003B770
0x1800143cf  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800143d6  nop     dword ptr [rax+rax+00h]
0x1800143db  and     [rsp+38h+var_18], 0
0x1800143e0  lea     r8, aCwdstransportn_68; "<- CWdsTransportNamespaceScheduledCastA"...
0x1800143e7  mov     r9, rbx
0x1800143ea  mov     dword ptr [rbx+84h], 3
0x1800143f4  mov     edx, 10000h
0x1800143f9  lea     rcx, qword_18003B770
0x180014400  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014407  nop     dword ptr [rax+rax+00h]
0x18001440c  xor     eax, eax
0x18001440e  add     rsp, 30h
0x180014412  pop     rbx
0x180014413  retn
```
