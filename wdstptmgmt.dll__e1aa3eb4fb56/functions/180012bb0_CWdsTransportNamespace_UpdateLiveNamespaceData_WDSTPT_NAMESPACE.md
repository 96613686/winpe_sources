# CWdsTransportNamespace::UpdateLiveNamespaceData(_WDSTPT_NAMESPACE *)

- ea: `0x180012bb0`
- end: `0x180012c7d`
- name: `?UpdateLiveNamespaceData@CWdsTransportNamespace@@AEAAJPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CWdsTransportNamespace *__hidden this, struct _WDSTPT_NAMESPACE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011f2c`
- `0x180012484`

## callees

- `0x180012bb0`

## import_xrefs

- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180012c03`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180012c03`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012bdd`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012c2b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012c5e`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012bdd`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012c2b`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012c5e`

## string_xrefs

- `0x180012bc2`: `-> CWdsTransportNamespace::UpdateLiveNamespaceData(0x%p)`
- `0x180012c4b`: `<- CWdsTransportNamespace::UpdateLiveNamespaceData(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespace::UpdateLiveNamespaceData(
        CWdsTransportNamespace *this,
        struct _WDSTPT_NAMESPACE *a2)
{
  unsigned int v4; // ebx
  unsigned int v6; // [rsp+20h] [rbp-18h]

  v4 = 0;
  CTrace::Trace((CTrace *)qword_18003B770, 0x10000u, L"-> CWdsTransportNamespace::UpdateLiveNamespaceData(0x%p)", this);
  if ( !*((_DWORD *)a2 + 14)
    || (*((_DWORD *)this + 46) = 1, SystemTimeToVariantTime((LPSYSTEMTIME)((char *)a2 + 60), (DOUBLE *)this + 24)) )
  {
    *((_DWORD *)this + 50) = *((_DWORD *)a2 + 19);
  }
  else
  {
    v4 = -1055915765;
    CTrace::Trace(
      (CTrace *)qword_18003B770,
      0x80000u,
      L"Received namespace data with an invalid tombstone time from the server.\n");
  }
  v6 = v4;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespace::UpdateLiveNamespaceData(0x%p) =%x",
    this,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180012bb0  mov     [rsp+arg_0], rbx
0x180012bb5  mov     [rsp+arg_8], rsi
0x180012bba  push    rdi
0x180012bbb  sub     rsp, 30h
0x180012bbf  mov     rsi, rdx
0x180012bc2  lea     r8, aCwdstransportn_28; "-> CWdsTransportNamespace::UpdateLiveNa"...
0x180012bc9  mov     rdi, rcx
0x180012bcc  mov     r9, rcx
0x180012bcf  mov     edx, 10000h
0x180012bd4  lea     rcx, qword_18003B770
0x180012bdb  xor     ebx, ebx
0x180012bdd  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180012be4  nop     dword ptr [rax+rax+00h]
0x180012be9  cmp     [rsi+38h], ebx
0x180012bec  jz      short loc_180012C39
0x180012bee  lea     rdx, [rdi+0C0h]; pvtime
0x180012bf5  mov     dword ptr [rdi+0B8h], 1
0x180012bff  lea     rcx, [rsi+3Ch]; lpSystemTime
0x180012c03  call    cs:__imp_SystemTimeToVariantTime
0x180012c0a  nop     dword ptr [rax+rax+00h]
0x180012c0f  test    eax, eax
0x180012c11  jnz     short loc_180012C39
0x180012c13  lea     r8, aReceivedNamesp; "Received namespace data with an invalid"...
0x180012c1a  mov     edx, 80000h
0x180012c1f  lea     rcx, qword_18003B770
0x180012c26  mov     ebx, 0C110010Bh
0x180012c2b  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180012c32  nop     dword ptr [rax+rax+00h]
0x180012c37  jmp     short loc_180012C44
0x180012c39  mov     r8d, [rsi+4Ch]
0x180012c3d  mov     [rdi+0C8h], r8d
0x180012c44  mov     r9, rdi
0x180012c47  mov     [rsp+38h+var_18], ebx
0x180012c4b  lea     r8, aCwdstransportn_3; "<- CWdsTransportNamespace::UpdateLiveNa"...
0x180012c52  mov     edx, 10000h
0x180012c57  lea     rcx, qword_18003B770
0x180012c5e  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180012c65  nop     dword ptr [rax+rax+00h]
0x180012c6a  mov     rsi, [rsp+38h+arg_8]
0x180012c6f  mov     eax, ebx
0x180012c71  mov     rbx, [rsp+38h+arg_0]
0x180012c76  add     rsp, 30h
0x180012c7a  pop     rdi
0x180012c7b  retn
```
