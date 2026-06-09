# CWdsTransportServicePolicy::get_NetworkProfile(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0008 *)

- ea: `0x18000e150`
- end: `0x18000e1da`
- name: `?get_NetworkProfile@CWdsTransportServicePolicy@@UEAAJPEAW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0008@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0008 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dc68`
- `0x18000e150`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::get_NetworkProfile(
        CWdsTransportServicePolicy *this,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0008 *a2)
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
    if ( (int)ElValidateHr_4(v4, v5, v6, 1635) >= 0 )
    {
      v4 = CWdsTransportServicePolicy::VerifyNetworkProfileSupported(this);
      if ( (int)ElValidateHr_4(v4, v7, v8, 1642) >= 0 )
        *a2 = *((enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0008 *)this + 46);
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
0x18000e150  mov     [rsp+arg_0], rbx
0x18000e155  mov     [rsp+arg_8], rsi
0x18000e15a  push    rdi
0x18000e15b  sub     rsp, 30h
0x18000e15f  mov     rsi, rdx
0x18000e162  mov     rdi, rcx
0x18000e165  lea     rdx, [rcx+50h]
0x18000e169  lea     rcx, [rsp+38h+var_18]
0x18000e16e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e173  test    rsi, rsi
0x18000e176  jnz     short loc_18000E17F
0x18000e178  mov     ebx, 80070057h
0x18000e17d  jmp     short loc_18000E1BD
0x18000e17f  mov     rcx, rdi; this
0x18000e182  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e187  mov     r9d, 663h
0x18000e18d  mov     ecx, eax
0x18000e18f  mov     ebx, eax
0x18000e191  call    ElValidateHr_4
0x18000e196  test    eax, eax
0x18000e198  js      short loc_18000E1BD
0x18000e19a  mov     rcx, rdi; this
0x18000e19d  call    ?VerifyNetworkProfileSupported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyNetworkProfileSupported(void)
0x18000e1a2  mov     r9d, 66Ah
0x18000e1a8  mov     ecx, eax
0x18000e1aa  mov     ebx, eax
0x18000e1ac  call    ElValidateHr_4
0x18000e1b1  test    eax, eax
0x18000e1b3  js      short loc_18000E1BD
0x18000e1b5  mov     eax, [rdi+0B8h]
0x18000e1bb  mov     [rsi], eax
0x18000e1bd  lea     rcx, [rsp+38h+var_18]
0x18000e1c2  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e1c7  mov     rsi, [rsp+38h+arg_8]
0x18000e1cc  mov     eax, ebx
0x18000e1ce  mov     rbx, [rsp+38h+arg_0]
0x18000e1d3  add     rsp, 30h
0x18000e1d7  pop     rdi
0x18000e1d8  retn
```
