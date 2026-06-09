# CWdsTransportNamespaceScheduledCastManualStart::InitializeNewNamespaceWorker(void)

- ea: `0x180014030`
- end: `0x180014095`
- name: `?InitializeNewNamespaceWorker@CWdsTransportNamespaceScheduledCastManualStart@@EEAAJXZ`
- size: `101`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastManualStart *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001404f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014080`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001404f`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180014080`

## string_xrefs

- `0x180014039`: `-> CWdsTransportNamespaceScheduledCastManualStart::InitializeNewNamespaceWorker(0x%p)`
- `0x180014060`: `<- CWdsTransportNamespaceScheduledCastManualStart::InitializeNewNamespaceWorker(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespaceScheduledCastManualStart::InitializeNewNamespaceWorker(
        CWdsTransportNamespaceScheduledCastManualStart *this)
{
  int v3; // [rsp+20h] [rbp-18h]

  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastManualStart::InitializeNewNamespaceWorker(0x%p)",
    this);
  v3 = 0;
  *((_DWORD *)this + 33) = 2;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastManualStart::InitializeNewNamespaceWorker(0x%p) =%x",
    this,
    v3);
  return 0;
}

```

## disassembly

```asm
0x180014030  push    rbx
0x180014032  sub     rsp, 30h
0x180014036  mov     rbx, rcx
0x180014039  lea     r8, aCwdstransportn_19; "-> CWdsTransportNamespaceScheduledCastM"...
0x180014040  mov     r9, rcx
0x180014043  mov     edx, 10000h
0x180014048  lea     rcx, qword_18003B770
0x18001404f  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014056  nop     dword ptr [rax+rax+00h]
0x18001405b  and     [rsp+38h+var_18], 0
0x180014060  lea     r8, aCwdstransportn_11; "<- CWdsTransportNamespaceScheduledCastM"...
0x180014067  mov     r9, rbx
0x18001406a  mov     dword ptr [rbx+84h], 2
0x180014074  mov     edx, 10000h
0x180014079  lea     rcx, qword_18003B770
0x180014080  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014087  nop     dword ptr [rax+rax+00h]
0x18001408c  xor     eax, eax
0x18001408e  add     rsp, 30h
0x180014092  pop     rbx
0x180014093  retn
```
