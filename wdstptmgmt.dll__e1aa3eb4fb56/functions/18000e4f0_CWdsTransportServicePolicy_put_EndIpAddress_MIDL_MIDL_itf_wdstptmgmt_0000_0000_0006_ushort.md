# CWdsTransportServicePolicy::put_EndIpAddress(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006,ushort *)

- ea: `0x18000e4f0`
- end: `0x18000e639`
- name: `?put_EndIpAddress@CWdsTransportServicePolicy@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006@@PEAG@Z`
- size: `329`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000d9e8`
- `0x18000dbc8`
- `0x18000e4f0`
- `0x18000eb74`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e5f1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e5f1`
- `WdsCommonLib!?WcsDupHr@@YAJPEBGPEAPEAG@Z` at `0x18000e5c9`
- `WdsCommonLib!?WcsDupHr@@YAJPEBGPEAPEAG@Z` at `0x18000e5c9`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::put_EndIpAddress(
        CWdsTransportServicePolicy *this,
        enum __MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006 a2,
        unsigned __int16 *a3)
{
  int v6; // ebx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ecx
  __int64 v11; // r14
  int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  void *v19; // rcx
  _BYTE v21[40]; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v22; // [rsp+50h] [rbp+8h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v21, (char *)this + 80);
  v22 = 0;
  if ( !a3 || !*a3 || a2 == WdsTptIpAddressUnknown )
    goto LABEL_15;
  v6 = a2 - 1;
  if ( !v6 )
  {
    v10 = 2;
    v11 = 144;
    v12 = 1;
    goto LABEL_9;
  }
  if ( v6 != 1 )
  {
LABEL_15:
    v7 = -2147024809;
    goto LABEL_16;
  }
  v7 = CWdsTransportServicePolicy::VerifyIpv6Supported(this);
  if ( (int)ElValidateHr_4(v7, v8, v9, 1323) < 0 )
    goto LABEL_16;
  v10 = 23;
  v11 = 168;
  v12 = 2;
LABEL_9:
  v7 = CWdsTransportServicePolicy::ValidateMulticastIpAddress(v10, a3);
  if ( (int)ElValidateHr_4(v7, v13, v14, 1343) >= 0 )
  {
    v7 = CWdsTransportServicePolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_4(v7, v15, v16, 1349) >= 0 )
    {
      v7 = WcsDupHr(a3, &v22);
      if ( (int)ElValidateHr_4(v7, v17, v18, 1356) >= 0 )
      {
        v19 = *(void **)((char *)this + v11);
        if ( v19 )
          operator delete[](v19);
        *(_QWORD *)((char *)this + v11) = v22;
        *((_DWORD *)this + 32) |= v12;
      }
    }
  }
LABEL_16:
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v21);
  return v7;
}

```

## disassembly

```asm
0x18000e4f0  mov     rax, rsp
0x18000e4f3  mov     [rax+10h], rbx
0x18000e4f7  mov     [rax+18h], rbp
0x18000e4fb  mov     [rax+20h], rsi
0x18000e4ff  push    rdi
0x18000e500  push    r14
0x18000e502  push    r15
0x18000e504  sub     rsp, 30h
0x18000e508  mov     ebx, edx
0x18000e50a  mov     rdi, rcx
0x18000e50d  lea     rdx, [rcx+50h]
0x18000e511  mov     rbp, r8
0x18000e514  lea     rcx, [rax-28h]
0x18000e518  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e51d  xor     r15d, r15d
0x18000e520  mov     [rsp+48h+arg_0], r15
0x18000e525  test    rbp, rbp
0x18000e528  jz      loc_18000E60E
0x18000e52e  cmp     [rbp+0], r15w
0x18000e533  jz      loc_18000E60E
0x18000e539  test    ebx, ebx
0x18000e53b  jz      loc_18000E60E
0x18000e541  sub     ebx, 1
0x18000e544  jz      short loc_18000E57D
0x18000e546  cmp     ebx, 1
0x18000e549  jnz     loc_18000E60E
0x18000e54f  mov     rcx, rdi; this
0x18000e552  call    ?VerifyIpv6Supported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyIpv6Supported(void)
0x18000e557  mov     r9d, 52Bh
0x18000e55d  mov     ecx, eax
0x18000e55f  mov     ebx, eax
0x18000e561  call    ElValidateHr_4
0x18000e566  test    eax, eax
0x18000e568  js      loc_18000E613
0x18000e56e  lea     ecx, [r15+17h]
0x18000e572  mov     r14d, 0A8h
0x18000e578  lea     esi, [rcx-15h]
0x18000e57b  jmp     short loc_18000E58B
0x18000e57d  mov     ecx, 2; unsigned int
0x18000e582  mov     r14d, 90h
0x18000e588  lea     esi, [rcx-1]
0x18000e58b  mov     rdx, rbp; unsigned __int16 *
0x18000e58e  call    ?ValidateMulticastIpAddress@CWdsTransportServicePolicy@@CAJKPEBG@Z; CWdsTransportServicePolicy::ValidateMulticastIpAddress(ulong,ushort const *)
0x18000e593  mov     r9d, 53Fh
0x18000e599  mov     ecx, eax
0x18000e59b  mov     ebx, eax
0x18000e59d  call    ElValidateHr_4
0x18000e5a2  test    eax, eax
0x18000e5a4  js      short loc_18000E613
0x18000e5a6  mov     rcx, rdi; this
0x18000e5a9  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e5ae  mov     r9d, 545h
0x18000e5b4  mov     ecx, eax
0x18000e5b6  mov     ebx, eax
0x18000e5b8  call    ElValidateHr_4
0x18000e5bd  test    eax, eax
0x18000e5bf  js      short loc_18000E613
0x18000e5c1  lea     rdx, [rsp+48h+arg_0]
0x18000e5c6  mov     rcx, rbp
0x18000e5c9  call    cs:__imp_?WcsDupHr@@YAJPEBGPEAPEAG@Z; WcsDupHr(ushort const *,ushort * *)
0x18000e5d0  nop     dword ptr [rax+rax+00h]
0x18000e5d5  mov     ecx, eax
0x18000e5d7  mov     r9d, 54Ch
0x18000e5dd  mov     ebx, eax
0x18000e5df  call    ElValidateHr_4
0x18000e5e4  test    eax, eax
0x18000e5e6  js      short loc_18000E613
0x18000e5e8  mov     rcx, [r14+rdi]
0x18000e5ec  test    rcx, rcx
0x18000e5ef  jz      short loc_18000E5FD
0x18000e5f1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000e5f8  nop     dword ptr [rax+rax+00h]
0x18000e5fd  mov     rax, [rsp+48h+arg_0]
0x18000e602  mov     [r14+rdi], rax
0x18000e606  or      [rdi+80h], esi
0x18000e60c  jmp     short loc_18000E613
0x18000e60e  mov     ebx, 80070057h
0x18000e613  lea     rcx, [rsp+48h+var_28]
0x18000e618  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e61d  mov     rbp, [rsp+48h+arg_10]
0x18000e622  mov     eax, ebx
0x18000e624  mov     rbx, [rsp+48h+arg_8]
0x18000e629  mov     rsi, [rsp+48h+arg_18]
0x18000e62e  add     rsp, 30h
0x18000e632  pop     r15
0x18000e634  pop     r14
0x18000e636  pop     rdi
0x18000e637  retn
```
