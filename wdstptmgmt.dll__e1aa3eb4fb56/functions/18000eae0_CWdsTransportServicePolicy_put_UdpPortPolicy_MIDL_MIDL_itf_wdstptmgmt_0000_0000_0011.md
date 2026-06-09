# CWdsTransportServicePolicy::put_UdpPortPolicy(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0011)

- ea: `0x18000eae0`
- end: `0x18000eb6e`
- name: `?put_UdpPortPolicy@CWdsTransportServicePolicy@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0011@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0011)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dd98`
- `0x18000eae0`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::put_UdpPortPolicy(CWdsTransportServicePolicy *this, unsigned int a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v10, (char *)this + 80);
  if ( a2 <= 1 )
  {
    v4 = CWdsTransportServicePolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_4(v4, v5, v6, 1822) >= 0 )
    {
      v4 = CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(this);
      if ( (int)ElValidateHr_4(v4, v7, v8, 1829) >= 0 )
      {
        *((_DWORD *)this + 32) |= 0x10u;
        *((_DWORD *)this + 47) = a2;
      }
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
0x18000eae0  mov     [rsp+arg_0], rbx
0x18000eae5  mov     [rsp+arg_8], rsi
0x18000eaea  push    rdi
0x18000eaeb  sub     rsp, 30h
0x18000eaef  mov     esi, edx
0x18000eaf1  mov     rbx, rcx
0x18000eaf4  lea     rdx, [rcx+50h]
0x18000eaf8  lea     rcx, [rsp+38h+var_18]
0x18000eafd  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000eb02  cmp     esi, 1
0x18000eb05  jbe     short loc_18000EB0E
0x18000eb07  mov     edi, 80070057h
0x18000eb0c  jmp     short loc_18000EB51
0x18000eb0e  mov     rcx, rbx; this
0x18000eb11  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000eb16  mov     r9d, 71Eh
0x18000eb1c  mov     ecx, eax
0x18000eb1e  mov     edi, eax
0x18000eb20  call    ElValidateHr_4
0x18000eb25  test    eax, eax
0x18000eb27  js      short loc_18000EB51
0x18000eb29  mov     rcx, rbx; this
0x18000eb2c  call    ?VerifyUdpPortPolicySupported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyUdpPortPolicySupported(void)
0x18000eb31  mov     r9d, 725h
0x18000eb37  mov     ecx, eax
0x18000eb39  mov     edi, eax
0x18000eb3b  call    ElValidateHr_4
0x18000eb40  test    eax, eax
0x18000eb42  js      short loc_18000EB51
0x18000eb44  or      dword ptr [rbx+80h], 10h
0x18000eb4b  mov     [rbx+0BCh], esi
0x18000eb51  lea     rcx, [rsp+38h+var_18]
0x18000eb56  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000eb5b  mov     rbx, [rsp+38h+arg_0]
0x18000eb60  mov     eax, edi
0x18000eb62  mov     rsi, [rsp+38h+arg_8]
0x18000eb67  add     rsp, 30h
0x18000eb6b  pop     rdi
0x18000eb6c  retn
```
