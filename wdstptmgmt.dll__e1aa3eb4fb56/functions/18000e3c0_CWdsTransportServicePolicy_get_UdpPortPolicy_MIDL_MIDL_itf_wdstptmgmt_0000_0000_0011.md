# CWdsTransportServicePolicy::get_UdpPortPolicy(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0011 *)

- ea: `0x18000e3c0`
- end: `0x18000e44a`
- name: `?get_UdpPortPolicy@CWdsTransportServicePolicy@@UEAAJPEAW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0011@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0011 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dd98`
- `0x18000e3c0`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::get_UdpPortPolicy(
        CWdsTransportServicePolicy *this,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0011 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v10, (char *)this + 80);
  if ( a2 )
  {
    v4 = CWdsTransportServicePolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_4(v4, v5, v6, 1761) >= 0 )
    {
      v4 = CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(this);
      if ( (int)ElValidateHr_4(v4, v7, v8, 1768) >= 0 )
        *a2 = *((enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0011 *)this + 47);
    }
  }
  else
  {
    v4 = -2147024809;
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v4;
}

```

## disassembly

```asm
0x18000e3c0  mov     [rsp+arg_0], rbx
0x18000e3c5  mov     [rsp+arg_8], rsi
0x18000e3ca  push    rdi
0x18000e3cb  sub     rsp, 30h
0x18000e3cf  mov     rsi, rdx
0x18000e3d2  mov     rdi, rcx
0x18000e3d5  lea     rdx, [rcx+50h]
0x18000e3d9  lea     rcx, [rsp+38h+var_18]
0x18000e3de  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e3e3  test    rsi, rsi
0x18000e3e6  jnz     short loc_18000E3EF
0x18000e3e8  mov     ebx, 80070057h
0x18000e3ed  jmp     short loc_18000E42D
0x18000e3ef  mov     rcx, rdi; this
0x18000e3f2  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e3f7  mov     r9d, 6E1h
0x18000e3fd  mov     ecx, eax
0x18000e3ff  mov     ebx, eax
0x18000e401  call    ElValidateHr_4
0x18000e406  test    eax, eax
0x18000e408  js      short loc_18000E42D
0x18000e40a  mov     rcx, rdi; this
0x18000e40d  call    ?VerifyUdpPortPolicySupported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(void)
0x18000e412  mov     r9d, 6E8h
0x18000e418  mov     ecx, eax
0x18000e41a  mov     ebx, eax
0x18000e41c  call    ElValidateHr_4
0x18000e421  test    eax, eax
0x18000e423  js      short loc_18000E42D
0x18000e425  mov     eax, [rdi+0BCh]
0x18000e42b  mov     [rsi], eax
0x18000e42d  lea     rcx, [rsp+38h+var_18]
0x18000e432  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e437  mov     rsi, [rsp+38h+arg_8]
0x18000e43c  mov     eax, ebx
0x18000e43e  mov     rbx, [rsp+38h+arg_0]
0x18000e443  add     rsp, 30h
0x18000e447  pop     rdi
0x18000e448  retn
```
