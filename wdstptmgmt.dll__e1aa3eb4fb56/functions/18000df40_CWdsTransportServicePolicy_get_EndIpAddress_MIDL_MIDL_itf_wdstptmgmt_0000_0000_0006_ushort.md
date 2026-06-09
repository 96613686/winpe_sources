# CWdsTransportServicePolicy::get_EndIpAddress(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006,ushort * *)

- ea: `0x18000df40`
- end: `0x18000dffc`
- name: `?get_EndIpAddress@CWdsTransportServicePolicy@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006@@PEAPEAG@Z`
- size: `188`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dbc8`
- `0x18000df40`
- `0x18000eb74`

## import_xrefs

- `WdsCommonLib!?SysAllocStringHr@@YAJPEBGPEAPEAG@Z` at `0x18000dfc5`
- `WdsCommonLib!?SysAllocStringHr@@YAJPEBGPEAPEAG@Z` at `0x18000dfc5`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::get_EndIpAddress(
        CWdsTransportServicePolicy *this,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006 a2,
        unsigned __int16 **a3)
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
    v10 = 144;
    goto LABEL_8;
  }
  if ( v6 != 1 )
  {
LABEL_10:
    v7 = -2147024809;
    goto LABEL_11;
  }
  v7 = CWdsTransportServicePolicy::VerifyIpv6Supported(this);
  if ( (int)ElValidateHr_4(v7, v8, v9, 1229) < 0 )
    goto LABEL_11;
  v10 = 168;
LABEL_8:
  v7 = CWdsTransportServicePolicy::DelayInitialize(this);
  if ( (int)ElValidateHr_4(v7, v11, v12, 1246) >= 0 )
    v7 = SysAllocStringHr(*(const unsigned __int16 **)((char *)this + v10), a3);
LABEL_11:
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v14);
  return v7;
}

```

## disassembly

```asm
0x18000df40  mov     rax, rsp
0x18000df43  mov     [rax+8], rbx
0x18000df47  mov     [rax+10h], rbp
0x18000df4b  mov     [rax+18h], rsi
0x18000df4f  push    rdi
0x18000df50  sub     rsp, 30h
0x18000df54  mov     ebx, edx
0x18000df56  mov     rsi, rcx
0x18000df59  lea     rdx, [rcx+50h]
0x18000df5d  mov     rbp, r8
0x18000df60  lea     rcx, [rax-18h]
0x18000df64  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000df69  test    rbp, rbp
0x18000df6c  jz      short loc_18000DFD5
0x18000df6e  test    ebx, ebx
0x18000df70  jz      short loc_18000DFD5
0x18000df72  sub     ebx, 1
0x18000df75  jz      short loc_18000DF9E
0x18000df77  cmp     ebx, 1
0x18000df7a  jnz     short loc_18000DFD5
0x18000df7c  mov     rcx, rsi; this
0x18000df7f  call    ?VerifyIpv6Supported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyIpv6Supported(void)
0x18000df84  mov     r9d, 4CDh
0x18000df8a  mov     ecx, eax
0x18000df8c  mov     ebx, eax
0x18000df8e  call    ElValidateHr_4
0x18000df93  test    eax, eax
0x18000df95  js      short loc_18000DFDA
0x18000df97  mov     edi, 0A8h
0x18000df9c  jmp     short loc_18000DFA3
0x18000df9e  mov     edi, 90h
0x18000dfa3  mov     rcx, rsi; this
0x18000dfa6  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000dfab  mov     r9d, 4DEh
0x18000dfb1  mov     ecx, eax
0x18000dfb3  mov     ebx, eax
0x18000dfb5  call    ElValidateHr_4
0x18000dfba  test    eax, eax
0x18000dfbc  js      short loc_18000DFDA
0x18000dfbe  mov     rcx, [rdi+rsi]
0x18000dfc2  mov     rdx, rbp
0x18000dfc5  call    cs:__imp_?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x18000dfcc  nop     dword ptr [rax+rax+00h]
0x18000dfd1  mov     ebx, eax
0x18000dfd3  jmp     short loc_18000DFDA
0x18000dfd5  mov     ebx, 80070057h
0x18000dfda  lea     rcx, [rsp+38h+var_18]
0x18000dfdf  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000dfe4  mov     rbp, [rsp+38h+arg_8]
0x18000dfe9  mov     eax, ebx
0x18000dfeb  mov     rbx, [rsp+38h+arg_0]
0x18000dff0  mov     rsi, [rsp+38h+arg_10]
0x18000dff5  add     rsp, 30h
0x18000dff9  pop     rdi
0x18000dffa  retn
```
