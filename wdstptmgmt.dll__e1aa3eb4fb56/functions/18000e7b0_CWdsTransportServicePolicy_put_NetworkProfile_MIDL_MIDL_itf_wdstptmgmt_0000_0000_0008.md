# CWdsTransportServicePolicy::put_NetworkProfile(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0008)

- ea: `0x18000e7b0`
- end: `0x18000e841`
- name: `?put_NetworkProfile@CWdsTransportServicePolicy@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0008@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0008)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dc68`
- `0x18000e7b0`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::put_NetworkProfile(
        CWdsTransportServicePolicy *this,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0008 a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v10, (char *)this + 80);
  if ( (unsigned int)(a2 - 1) > 3 )
  {
    v4 = -2147024809;
  }
  else
  {
    v4 = CWdsTransportServicePolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_4(v4, v5, v6, 1695) >= 0 )
    {
      v4 = CWdsTransportServicePolicy::VerifyNetworkProfileSupported(this);
      if ( (int)ElValidateHr_4(v4, v7, v8, 1702) >= 0 )
      {
        *((_DWORD *)this + 32) |= 8u;
        *((_DWORD *)this + 46) = a2;
      }
    }
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v4;
}

```

## disassembly

```asm
0x18000e7b0  mov     [rsp+arg_0], rbx
0x18000e7b5  mov     [rsp+arg_8], rsi
0x18000e7ba  push    rdi
0x18000e7bb  sub     rsp, 30h
0x18000e7bf  mov     esi, edx
0x18000e7c1  mov     rbx, rcx
0x18000e7c4  lea     rdx, [rcx+50h]
0x18000e7c8  lea     rcx, [rsp+38h+var_18]
0x18000e7cd  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e7d2  lea     eax, [rsi-1]
0x18000e7d5  cmp     eax, 3
0x18000e7d8  ja      short loc_18000E81F
0x18000e7da  mov     rcx, rbx; this
0x18000e7dd  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e7e2  mov     r9d, 69Fh
0x18000e7e8  mov     ecx, eax
0x18000e7ea  mov     edi, eax
0x18000e7ec  call    ElValidateHr_4
0x18000e7f1  test    eax, eax
0x18000e7f3  js      short loc_18000E824
0x18000e7f5  mov     rcx, rbx; this
0x18000e7f8  call    ?VerifyNetworkProfileSupported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyNetworkProfileSupported(void)
0x18000e7fd  mov     r9d, 6A6h
0x18000e803  mov     ecx, eax
0x18000e805  mov     edi, eax
0x18000e807  call    ElValidateHr_4
0x18000e80c  test    eax, eax
0x18000e80e  js      short loc_18000E824
0x18000e810  or      dword ptr [rbx+80h], 8
0x18000e817  mov     [rbx+0B8h], esi
0x18000e81d  jmp     short loc_18000E824
0x18000e81f  mov     edi, 80070057h
0x18000e824  lea     rcx, [rsp+38h+var_18]
0x18000e829  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e82e  mov     rbx, [rsp+38h+arg_0]
0x18000e833  mov     eax, edi
0x18000e835  mov     rsi, [rsp+38h+arg_8]
0x18000e83a  add     rsp, 30h
0x18000e83e  pop     rdi
0x18000e83f  retn
```
