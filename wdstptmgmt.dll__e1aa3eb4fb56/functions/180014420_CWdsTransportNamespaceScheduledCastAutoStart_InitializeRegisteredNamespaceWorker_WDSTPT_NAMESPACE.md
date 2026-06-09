# CWdsTransportNamespaceScheduledCastAutoStart::InitializeRegisteredNamespaceWorker(_WDSTPT_NAMESPACE *)

- ea: `0x180014420`
- end: `0x1800144f5`
- name: `?InitializeRegisteredNamespaceWorker@CWdsTransportNamespaceScheduledCastAutoStart@@EEAAJPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCastAutoStart *__hidden this, struct _WDSTPT_NAMESPACE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180014420`

## import_xrefs

- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180014488`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180014488`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001444d`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800144b0`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800144d6`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18001444d`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800144b0`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800144d6`

## string_xrefs

- `0x180014432`: `-> CWdsTransportNamespaceScheduledCastAutoStart::InitializeRegisteredNamespaceWorker(0x%p)`
- `0x1800144c3`: `<- CWdsTransportNamespaceScheduledCastAutoStart::InitializeRegisteredNamespaceWorker(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespaceScheduledCastAutoStart::InitializeRegisteredNamespaceWorker(
        CWdsTransportNamespaceScheduledCastAutoStart *this,
        struct _WDSTPT_NAMESPACE *a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  unsigned int v7; // [rsp+20h] [rbp-18h]

  v4 = 0;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCastAutoStart::InitializeRegisteredNamespaceWorker(0x%p)",
    this);
  *((_DWORD *)this + 33) = 3;
  v5 = *((_DWORD *)a2 + 21);
  *((_DWORD *)this + 56) = v5;
  *((_DWORD *)this + 57) = *((_DWORD *)a2 + 22);
  if ( (v5 & 2) != 0 && !SystemTimeToVariantTime((LPSYSTEMTIME)((char *)a2 + 92), (DOUBLE *)this + 29) )
  {
    v4 = -1055915765;
    CTrace::Trace(
      (CTrace *)qword_18003B770,
      0x80000u,
      L"Received namespace data with an invalid start time from the server.\n");
  }
  v7 = v4;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCastAutoStart::InitializeRegisteredNamespaceWorker(0x%p) =%x",
    this,
    v7);
  return v4;
}

```

## disassembly

```asm
0x180014420  mov     [rsp+arg_0], rbx
0x180014425  mov     [rsp+arg_8], rsi
0x18001442a  push    rdi
0x18001442b  sub     rsp, 30h
0x18001442f  mov     rsi, rdx
0x180014432  lea     r8, aCwdstransportn_58; "-> CWdsTransportNamespaceScheduledCastA"...
0x180014439  mov     rdi, rcx
0x18001443c  mov     r9, rcx
0x18001443f  mov     edx, 10000h
0x180014444  lea     rcx, qword_18003B770
0x18001444b  xor     ebx, ebx
0x18001444d  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180014454  nop     dword ptr [rax+rax+00h]
0x180014459  mov     dword ptr [rdi+84h], 3
0x180014463  mov     r8d, [rsi+54h]
0x180014467  mov     [rdi+0E0h], r8d
0x18001446e  mov     eax, [rsi+58h]
0x180014471  mov     [rdi+0E4h], eax
0x180014477  test    r8b, 2
0x18001447b  jz      short loc_1800144BC
0x18001447d  lea     rdx, [rdi+0E8h]; pvtime
0x180014484  lea     rcx, [rsi+5Ch]; lpSystemTime
0x180014488  call    cs:__imp_SystemTimeToVariantTime
0x18001448f  nop     dword ptr [rax+rax+00h]
0x180014494  test    eax, eax
0x180014496  jnz     short loc_1800144BC
0x180014498  lea     r8, aReceivedNamesp_0; "Received namespace data with an invalid"...
0x18001449f  mov     edx, 80000h
0x1800144a4  lea     rcx, qword_18003B770
0x1800144ab  mov     ebx, 0C110010Bh
0x1800144b0  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800144b7  nop     dword ptr [rax+rax+00h]
0x1800144bc  mov     r9, rdi
0x1800144bf  mov     [rsp+38h+var_18], ebx
0x1800144c3  lea     r8, aCwdstransportn_32; "<- CWdsTransportNamespaceScheduledCastA"...
0x1800144ca  mov     edx, 10000h
0x1800144cf  lea     rcx, qword_18003B770
0x1800144d6  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800144dd  nop     dword ptr [rax+rax+00h]
0x1800144e2  mov     rsi, [rsp+38h+arg_8]
0x1800144e7  mov     eax, ebx
0x1800144e9  mov     rbx, [rsp+38h+arg_0]
0x1800144ee  add     rsp, 30h
0x1800144f2  pop     rdi
0x1800144f3  retn
```
