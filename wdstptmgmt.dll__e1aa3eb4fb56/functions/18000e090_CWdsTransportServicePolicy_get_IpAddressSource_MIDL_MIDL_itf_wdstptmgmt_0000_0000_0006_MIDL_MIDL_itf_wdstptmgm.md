# CWdsTransportServicePolicy::get_IpAddressSource(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006,__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0007 *)

- ea: `0x18000e090`
- end: `0x18000e13f`
- name: `?get_IpAddressSource@CWdsTransportServicePolicy@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006@@PEAW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0007@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0007 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dbc8`
- `0x18000e090`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::get_IpAddressSource(
        CWdsTransportServicePolicy *this,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006 a2,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0007 *a3)
{
  int v6; // ebx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8
  _BYTE v14[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v14, (char *)this + 80);
  if ( !a3 || a2 == WdsTptIpAddressUnknown )
    goto LABEL_10;
  v6 = a2 - 1;
  if ( !v6 )
  {
    v10 = 132;
    goto LABEL_8;
  }
  if ( v6 != 1 )
  {
LABEL_10:
    v7 = -2147024809;
    goto LABEL_11;
  }
  v7 = CWdsTransportServicePolicy::VerifyIpv6Supported(this);
  if ( (int)ElValidateHr_4(v7, v8, v9, 848) < 0 )
    goto LABEL_11;
  v10 = 152;
LABEL_8:
  v7 = CWdsTransportServicePolicy::DelayInitialize(this);
  if ( (int)ElValidateHr_4(v7, v11, v12, 865) >= 0 )
    *a3 = *(enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0007 *)((char *)this + v10);
LABEL_11:
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v14);
  return v7;
}

```

## disassembly

```asm
0x18000e090  mov     rax, rsp
0x18000e093  mov     [rax+8], rbx
0x18000e097  mov     [rax+10h], rsi
0x18000e09b  mov     [rax+18h], rdi
0x18000e09f  push    r14
0x18000e0a1  sub     rsp, 30h
0x18000e0a5  mov     ebx, edx
0x18000e0a7  mov     rsi, rcx
0x18000e0aa  lea     rdx, [rcx+50h]
0x18000e0ae  mov     r14, r8
0x18000e0b1  lea     rcx, [rax-18h]
0x18000e0b5  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e0ba  test    r14, r14
0x18000e0bd  jz      short loc_18000E117
0x18000e0bf  test    ebx, ebx
0x18000e0c1  jz      short loc_18000E117
0x18000e0c3  sub     ebx, 1
0x18000e0c6  jz      short loc_18000E0EF
0x18000e0c8  cmp     ebx, 1
0x18000e0cb  jnz     short loc_18000E117
0x18000e0cd  mov     rcx, rsi; this
0x18000e0d0  call    ?VerifyIpv6Supported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyIpv6Supported(void)
0x18000e0d5  mov     r9d, 350h
0x18000e0db  mov     ecx, eax
0x18000e0dd  mov     ebx, eax
0x18000e0df  call    ElValidateHr_4
0x18000e0e4  test    eax, eax
0x18000e0e6  js      short loc_18000E11C
0x18000e0e8  mov     edi, 98h
0x18000e0ed  jmp     short loc_18000E0F4
0x18000e0ef  mov     edi, 84h
0x18000e0f4  mov     rcx, rsi; this
0x18000e0f7  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e0fc  mov     r9d, 361h
0x18000e102  mov     ecx, eax
0x18000e104  mov     ebx, eax
0x18000e106  call    ElValidateHr_4
0x18000e10b  test    eax, eax
0x18000e10d  js      short loc_18000E11C
0x18000e10f  mov     eax, [rdi+rsi]
0x18000e112  mov     [r14], eax
0x18000e115  jmp     short loc_18000E11C
0x18000e117  mov     ebx, 80070057h
0x18000e11c  lea     rcx, [rsp+38h+var_18]
0x18000e121  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e126  mov     rsi, [rsp+38h+arg_8]
0x18000e12b  mov     eax, ebx
0x18000e12d  mov     rbx, [rsp+38h+arg_0]
0x18000e132  mov     rdi, [rsp+38h+arg_10]
0x18000e137  add     rsp, 30h
0x18000e13b  pop     r14
0x18000e13d  retn
```
