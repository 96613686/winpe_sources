# CWdsTransportServicePolicy::put_IpAddressSource(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006,__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0007)

- ea: `0x18000e6d0`
- end: `0x18000e7a3`
- name: `?put_IpAddressSource@CWdsTransportServicePolicy@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006@@W4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0007@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0007)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dbc8`
- `0x18000e6d0`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::put_IpAddressSource(
        CWdsTransportServicePolicy *this,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006 a2,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0007 a3)
{
  int v6; // esi
  int v7; // ebx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r14
  __int64 v12; // rdx
  __int64 v13; // r8
  _BYTE v15[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v15, (char *)this + 80);
  v6 = 1;
  if ( (unsigned int)(a3 - 1) > 1 || a2 == WdsTptIpAddressUnknown )
    goto LABEL_12;
  v7 = a2 - 1;
  if ( !v7 )
  {
    v11 = 132;
    goto LABEL_10;
  }
  if ( v7 != 1 )
  {
LABEL_12:
    v8 = -2147024809;
    goto LABEL_13;
  }
  v8 = CWdsTransportServicePolicy::VerifyIpv6Supported(this);
  if ( (int)ElValidateHr_4(v8, v9, v10, 935) < 0 )
    goto LABEL_13;
  v6 = 2;
  if ( a3 != WdsTptIpAddressSourceRange )
  {
    v8 = -1055915750;
    goto LABEL_13;
  }
  v11 = 152;
LABEL_10:
  v8 = CWdsTransportServicePolicy::DelayInitialize(this);
  if ( (int)ElValidateHr_4(v8, v12, v13, 965) >= 0 )
  {
    *(_DWORD *)((char *)this + v11) = a3;
    *((_DWORD *)this + 32) |= v6;
  }
LABEL_13:
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v15);
  return v8;
}

```

## disassembly

```asm
0x18000e6d0  mov     rax, rsp
0x18000e6d3  mov     [rax+8], rbx
0x18000e6d7  mov     [rax+10h], rbp
0x18000e6db  mov     [rax+18h], rsi
0x18000e6df  mov     [rax+20h], rdi
0x18000e6e3  push    r14
0x18000e6e5  sub     rsp, 30h
0x18000e6e9  mov     ebx, edx
0x18000e6eb  mov     rdi, rcx
0x18000e6ee  lea     rdx, [rcx+50h]
0x18000e6f2  mov     ebp, r8d
0x18000e6f5  lea     rcx, [rax-18h]
0x18000e6f9  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e6fe  lea     eax, [rbp-1]
0x18000e701  mov     esi, 1
0x18000e706  cmp     eax, esi
0x18000e708  ja      short loc_18000E776
0x18000e70a  test    ebx, ebx
0x18000e70c  jz      short loc_18000E776
0x18000e70e  sub     ebx, esi
0x18000e710  jz      short loc_18000E749
0x18000e712  cmp     ebx, esi
0x18000e714  jnz     short loc_18000E776
0x18000e716  mov     rcx, rdi; this
0x18000e719  call    ?VerifyIpv6Supported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyIpv6Supported(void)
0x18000e71e  mov     r9d, 3A7h
0x18000e724  mov     ecx, eax
0x18000e726  mov     ebx, eax
0x18000e728  call    ElValidateHr_4
0x18000e72d  test    eax, eax
0x18000e72f  js      short loc_18000E77B
0x18000e731  mov     esi, 2
0x18000e736  cmp     ebp, esi
0x18000e738  jz      short loc_18000E741
0x18000e73a  mov     ebx, 0C110011Ah
0x18000e73f  jmp     short loc_18000E77B
0x18000e741  mov     r14d, 98h
0x18000e747  jmp     short loc_18000E74F
0x18000e749  mov     r14d, 84h
0x18000e74f  mov     rcx, rdi; this
0x18000e752  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e757  mov     r9d, 3C5h
0x18000e75d  mov     ecx, eax
0x18000e75f  mov     ebx, eax
0x18000e761  call    ElValidateHr_4
0x18000e766  test    eax, eax
0x18000e768  js      short loc_18000E77B
0x18000e76a  mov     [r14+rdi], ebp
0x18000e76e  or      [rdi+80h], esi
0x18000e774  jmp     short loc_18000E77B
0x18000e776  mov     ebx, 80070057h
0x18000e77b  lea     rcx, [rsp+38h+var_18]
0x18000e780  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e785  mov     rbp, [rsp+38h+arg_8]
0x18000e78a  mov     eax, ebx
0x18000e78c  mov     rbx, [rsp+38h+arg_0]
0x18000e791  mov     rsi, [rsp+38h+arg_10]
0x18000e796  mov     rdi, [rsp+38h+arg_18]
0x18000e79b  add     rsp, 30h
0x18000e79f  pop     r14
0x18000e7a1  retn
```
