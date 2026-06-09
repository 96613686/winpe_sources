# CWdsTransportNamespaceScheduledCast::StartTransmission(void)

- ea: `0x180013cb0`
- end: `0x180013dbc`
- name: `?StartTransmission@CWdsTransportNamespaceScheduledCast@@UEAAJXZ`
- size: `268`
- prototype: `__int64 __fastcall(CWdsTransportNamespaceScheduledCast *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012b90`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000671c`
- `0x180013cb0`
- `0x180013dc4`
- `0x18001c15c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180013d41`
- `KERNEL32!SetLastError` at `0x180013d41`
- `KERNEL32!GetLastError` at `0x180013d23`
- `KERNEL32!GetLastError` at `0x180013d23`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013cf0`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013d66`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013d93`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013cf0`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013d66`
- `WdsCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180013d93`

## string_xrefs

- `0x180013ce2`: `-> CWdsTransportNamespaceScheduledCast::StartTransmission(0x%p)`
- `0x180013d80`: `<- CWdsTransportNamespaceScheduledCast::StartTransmission(0x%p) =%x`

## pseudocode

```c
__int64 __fastcall CWdsTransportNamespaceScheduledCast::StartTransmission(CWdsTptMgmtClient **this)
{
  CWdsTptMgmtClient **v2; // rsi
  __int64 started; // rdi
  DWORD LastError; // ebx
  int v6; // [rsp+20h] [rbp-28h]
  _BYTE v7[24]; // [rsp+30h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v7, this - 18);
  v2 = this - 26;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"-> CWdsTransportNamespaceScheduledCast::StartTransmission(0x%p)",
    this - 26);
  if ( *((_DWORD *)this - 21) )
  {
    started = (unsigned int)CWdsTptMgmtClient::StartTransmission(*(this - 12), *(this - 4));
    ElValidateHrLite_8(started);
    if ( (int)started >= 0 )
    {
      CTrace::Trace(
        (CTrace *)qword_18003B770,
        0x10000u,
        L"Successfully started transmission on the namespace %s.\n",
        *(this - 9));
      *((_DWORD *)this - 2) = 1;
    }
    else
    {
      LastError = GetLastError();
      if ( (g_uErrLibFlags & 1) != 0 )
        ElTraceErrorInfo();
      SetLastError(LastError);
    }
  }
  else
  {
    LODWORD(started) = -1055915768;
  }
  v6 = started;
  CTrace::Trace(
    (CTrace *)qword_18003B770,
    0x10000u,
    L"<- CWdsTransportNamespaceScheduledCast::StartTransmission(0x%p) =%x",
    v2,
    v6);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v7);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180013cb0  mov     [rsp+arg_0], rbx
0x180013cb5  mov     [rsp+arg_8], rsi
0x180013cba  push    rdi
0x180013cbb  sub     rsp, 40h
0x180013cbf  mov     rbx, rcx
0x180013cc2  lea     rdx, [rcx-90h]
0x180013cc9  lea     rcx, [rsp+48h+var_18]
0x180013cce  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x180013cd3  lea     rsi, [rbx-0D0h]
0x180013cda  mov     edx, 10000h
0x180013cdf  mov     r9, rsi
0x180013ce2  lea     r8, aCwdstransportn_40; "-> CWdsTransportNamespaceScheduledCast:"...
0x180013ce9  lea     rcx, qword_18003B770
0x180013cf0  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013cf7  nop     dword ptr [rax+rax+00h]
0x180013cfc  cmp     dword ptr [rbx-54h], 0
0x180013d00  jnz     short loc_180013D09
0x180013d02  mov     edi, 0C1100108h
0x180013d07  jmp     short loc_180013D79
0x180013d09  mov     rdx, [rbx-20h]; void *
0x180013d0d  mov     rcx, [rbx-60h]; this
0x180013d11  call    ?StartTransmission@CWdsTptMgmtClient@@QEAAJPEAX@Z; CWdsTptMgmtClient::StartTransmission(void *)
0x180013d16  mov     ecx, eax
0x180013d18  mov     edi, eax
0x180013d1a  call    ElValidateHrLite_8
0x180013d1f  test    edi, edi
0x180013d21  jns     short loc_180013D4F
0x180013d23  call    cs:__imp_GetLastError
0x180013d2a  nop     dword ptr [rax+rax+00h]
0x180013d2f  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180013d36  mov     ebx, eax
0x180013d38  jz      short loc_180013D3F
0x180013d3a  call    ElTraceErrorInfo
0x180013d3f  mov     ecx, ebx; dwErrCode
0x180013d41  call    cs:__imp_SetLastError
0x180013d48  nop     dword ptr [rax+rax+00h]
0x180013d4d  jmp     short loc_180013D79
0x180013d4f  mov     r9, [rbx-48h]
0x180013d53  lea     r8, aSuccessfullySt; "Successfully started transmission on th"...
0x180013d5a  mov     edx, 10000h
0x180013d5f  lea     rcx, qword_18003B770
0x180013d66  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013d6d  nop     dword ptr [rax+rax+00h]
0x180013d72  mov     dword ptr [rbx-8], 1
0x180013d79  mov     r9, rsi
0x180013d7c  mov     [rsp+48h+var_28], edi
0x180013d80  lea     r8, aCwdstransportn_21; "<- CWdsTransportNamespaceScheduledCast:"...
0x180013d87  mov     edx, 10000h
0x180013d8c  lea     rcx, qword_18003B770
0x180013d93  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180013d9a  nop     dword ptr [rax+rax+00h]
0x180013d9f  lea     rcx, [rsp+48h+var_18]
0x180013da4  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180013da9  mov     rbx, [rsp+48h+arg_0]
0x180013dae  mov     eax, edi
0x180013db0  mov     rsi, [rsp+48h+arg_8]
0x180013db5  add     rsp, 40h
0x180013db9  pop     rdi
0x180013dba  retn
```
