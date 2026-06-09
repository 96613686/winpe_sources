# CWdsTransportServicePolicy::VerifyTftpVariableWindowSupported(void)

- ea: `0x18000dd50`
- end: `0x18000dd91`
- name: `?VerifyTftpVariableWindowSupported@CWdsTransportServicePolicy@@QEAAJXZ`
- size: `65`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000d2c0`
- `0x18000deb0`
- `0x18000e450`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x1800094a4`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::VerifyTftpVariableWindowSupported(CWdsTransportServicePolicy *this)
{
  CWdsTransportServicePolicy *v1; // rbx
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  v1 = this;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v3, (char *)this + 80);
  LODWORD(v1) = CWdsTransportServer::VerifyTftpCapability(
                  *((CWdsTransportServer **)v1 + 8),
                  WdsTptTftpCapVariableWindow,
                  -1055915742);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000dd50  push    rbx
0x18000dd52  sub     rsp, 30h
0x18000dd56  mov     rbx, rcx
0x18000dd59  lea     rdx, [rcx+50h]
0x18000dd5d  lea     rcx, [rsp+38h+var_18]
0x18000dd62  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000dd67  nop
0x18000dd68  mov     edx, 2; enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0012
0x18000dd6d  mov     r8d, 0C1100122h; int
0x18000dd73  mov     rcx, [rbx+40h]; this
0x18000dd77  call    ?VerifyTftpCapability@CWdsTransportServer@@QEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0012@@J@Z; CWdsTransportServer::VerifyTftpCapability(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0012,long)
0x18000dd7c  mov     ebx, eax
0x18000dd7e  lea     rcx, [rsp+38h+var_18]
0x18000dd83  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000dd88  mov     eax, ebx
0x18000dd8a  add     rsp, 30h
0x18000dd8e  pop     rbx
0x18000dd8f  retn
```
