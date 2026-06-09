# CWdsTransportServicePolicy::VerifyTftpMaximumBlockSizeSupported(void)

- ea: `0x18000dd08`
- end: `0x18000dd49`
- name: `?VerifyTftpMaximumBlockSizeSupported@CWdsTransportServicePolicy@@QEAAJXZ`
- size: `65`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000d2c0`
- `0x18000e330`
- `0x18000ea30`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x1800094a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWdsTransportServicePolicy::VerifyTftpMaximumBlockSizeSupported(CWdsTransportServicePolicy *this)
{
  CWdsTransportServicePolicy *v1; // rbx
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  v1 = this;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v3, (char *)this + 80);
  LODWORD(v1) = CWdsTransportServer::VerifyTftpCapability(
                  *((CWdsTransportServer **)v1 + 8),
                  WdsTptTftpCapMaximumBlockSize,
                  -1055915743);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000dd08  push    rbx
0x18000dd0a  sub     rsp, 30h
0x18000dd0e  mov     rbx, rcx
0x18000dd11  lea     rdx, [rcx+50h]
0x18000dd15  lea     rcx, [rsp+38h+var_18]
0x18000dd1a  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000dd1f  nop
0x18000dd20  mov     edx, 1; enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0012
0x18000dd25  mov     r8d, 0C1100121h; int
0x18000dd2b  mov     rcx, [rbx+40h]; this
0x18000dd2f  call    ?VerifyTftpCapability@CWdsTransportServer@@QEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0012@@J@Z; CWdsTransportServer::VerifyTftpCapability(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0012,long)
0x18000dd34  mov     ebx, eax
0x18000dd36  lea     rcx, [rsp+38h+var_18]
0x18000dd3b  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000dd40  mov     eax, ebx
0x18000dd42  add     rsp, 30h
0x18000dd46  pop     rbx
0x18000dd47  retn
```
