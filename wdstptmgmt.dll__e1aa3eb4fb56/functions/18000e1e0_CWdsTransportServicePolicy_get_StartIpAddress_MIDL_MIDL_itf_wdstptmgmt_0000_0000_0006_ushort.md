# CWdsTransportServicePolicy::get_StartIpAddress(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006,ushort * *)

- ea: `0x18000e1e0`
- end: `0x18000e29c`
- name: `?get_StartIpAddress@CWdsTransportServicePolicy@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006@@PEAPEAG@Z`
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
- `0x18000e1e0`
- `0x18000eb74`

## import_xrefs

- `WdsCommonLib!?SysAllocStringHr@@YAJPEBGPEAPEAG@Z` at `0x18000e265`
- `WdsCommonLib!?SysAllocStringHr@@YAJPEBGPEAPEAG@Z` at `0x18000e265`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::get_StartIpAddress(
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
    v10 = 136;
    goto LABEL_8;
  }
  if ( v6 != 1 )
  {
LABEL_10:
    v7 = -2147024809;
    goto LABEL_11;
  }
  v7 = CWdsTransportServicePolicy::VerifyIpv6Supported(this);
  if ( (int)ElValidateHr_4(v7, v8, v9, 1033) < 0 )
    goto LABEL_11;
  v10 = 160;
LABEL_8:
  v7 = CWdsTransportServicePolicy::DelayInitialize(this);
  if ( (int)ElValidateHr_4(v7, v11, v12, 1050) >= 0 )
    v7 = SysAllocStringHr(*(const unsigned __int16 **)((char *)this + v10), a3);
LABEL_11:
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v14);
  return v7;
}

```

## disassembly

```asm
0x18000e1e0  mov     rax, rsp
0x18000e1e3  mov     [rax+8], rbx
0x18000e1e7  mov     [rax+10h], rbp
0x18000e1eb  mov     [rax+18h], rsi
0x18000e1ef  push    rdi
0x18000e1f0  sub     rsp, 30h
0x18000e1f4  mov     ebx, edx
0x18000e1f6  mov     rsi, rcx
0x18000e1f9  lea     rdx, [rcx+50h]
0x18000e1fd  mov     rbp, r8
0x18000e200  lea     rcx, [rax-18h]
0x18000e204  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e209  test    rbp, rbp
0x18000e20c  jz      short loc_18000E275
0x18000e20e  test    ebx, ebx
0x18000e210  jz      short loc_18000E275
0x18000e212  sub     ebx, 1
0x18000e215  jz      short loc_18000E23E
0x18000e217  cmp     ebx, 1
0x18000e21a  jnz     short loc_18000E275
0x18000e21c  mov     rcx, rsi; this
0x18000e21f  call    ?VerifyIpv6Supported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyIpv6Supported(void)
0x18000e224  mov     r9d, 409h
0x18000e22a  mov     ecx, eax
0x18000e22c  mov     ebx, eax
0x18000e22e  call    ElValidateHr_4
0x18000e233  test    eax, eax
0x18000e235  js      short loc_18000E27A
0x18000e237  mov     edi, 0A0h
0x18000e23c  jmp     short loc_18000E243
0x18000e23e  mov     edi, 88h
0x18000e243  mov     rcx, rsi; this
0x18000e246  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e24b  mov     r9d, 41Ah
0x18000e251  mov     ecx, eax
0x18000e253  mov     ebx, eax
0x18000e255  call    ElValidateHr_4
0x18000e25a  test    eax, eax
0x18000e25c  js      short loc_18000E27A
0x18000e25e  mov     rcx, [rdi+rsi]
0x18000e262  mov     rdx, rbp
0x18000e265  call    cs:__imp_?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x18000e26c  nop     dword ptr [rax+rax+00h]
0x18000e271  mov     ebx, eax
0x18000e273  jmp     short loc_18000E27A
0x18000e275  mov     ebx, 80070057h
0x18000e27a  lea     rcx, [rsp+38h+var_18]
0x18000e27f  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e284  mov     rbp, [rsp+38h+arg_8]
0x18000e289  mov     eax, ebx
0x18000e28b  mov     rbx, [rsp+38h+arg_0]
0x18000e290  mov     rsi, [rsp+38h+arg_10]
0x18000e295  add     rsp, 30h
0x18000e299  pop     rdi
0x18000e29a  retn
```
