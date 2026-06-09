# CWdsTransportServicePolicy::put_StartIpAddress(__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006,ushort *)

- ea: `0x18000e850`
- end: `0x18000e999`
- name: `?put_StartIpAddress@CWdsTransportServicePolicy@@UEAAJW4__MIDL___MIDL_itf_wdstptmgmt_0000_0000_0006@@PEAG@Z`
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
- `0x18000e850`
- `0x18000eb74`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e951`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000e951`
- `WdsCommonLib!?WcsDupHr@@YAJPEBGPEAPEAG@Z` at `0x18000e929`
- `WdsCommonLib!?WcsDupHr@@YAJPEBGPEAPEAG@Z` at `0x18000e929`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::put_StartIpAddress(
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
    v11 = 136;
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
  if ( (int)ElValidateHr_4(v7, v8, v9, 1127) < 0 )
    goto LABEL_16;
  v10 = 23;
  v11 = 160;
  v12 = 2;
LABEL_9:
  v7 = CWdsTransportServicePolicy::ValidateMulticastIpAddress(v10, a3);
  if ( (int)ElValidateHr_4(v7, v13, v14, 1147) >= 0 )
  {
    v7 = CWdsTransportServicePolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_4(v7, v15, v16, 1153) >= 0 )
    {
      v7 = WcsDupHr(a3, &v22);
      if ( (int)ElValidateHr_4(v7, v17, v18, 1160) >= 0 )
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
0x18000e850  mov     rax, rsp
0x18000e853  mov     [rax+10h], rbx
0x18000e857  mov     [rax+18h], rbp
0x18000e85b  mov     [rax+20h], rsi
0x18000e85f  push    rdi
0x18000e860  push    r14
0x18000e862  push    r15
0x18000e864  sub     rsp, 30h
0x18000e868  mov     ebx, edx
0x18000e86a  mov     rdi, rcx
0x18000e86d  lea     rdx, [rcx+50h]
0x18000e871  mov     rbp, r8
0x18000e874  lea     rcx, [rax-28h]
0x18000e878  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e87d  xor     r15d, r15d
0x18000e880  mov     [rsp+48h+arg_0], r15
0x18000e885  test    rbp, rbp
0x18000e888  jz      loc_18000E96E
0x18000e88e  cmp     [rbp+0], r15w
0x18000e893  jz      loc_18000E96E
0x18000e899  test    ebx, ebx
0x18000e89b  jz      loc_18000E96E
0x18000e8a1  sub     ebx, 1
0x18000e8a4  jz      short loc_18000E8DD
0x18000e8a6  cmp     ebx, 1
0x18000e8a9  jnz     loc_18000E96E
0x18000e8af  mov     rcx, rdi; this
0x18000e8b2  call    ?VerifyIpv6Supported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyIpv6Supported(void)
0x18000e8b7  mov     r9d, 467h
0x18000e8bd  mov     ecx, eax
0x18000e8bf  mov     ebx, eax
0x18000e8c1  call    ElValidateHr_4
0x18000e8c6  test    eax, eax
0x18000e8c8  js      loc_18000E973
0x18000e8ce  lea     ecx, [r15+17h]
0x18000e8d2  mov     r14d, 0A0h
0x18000e8d8  lea     esi, [rcx-15h]
0x18000e8db  jmp     short loc_18000E8EB
0x18000e8dd  mov     ecx, 2; unsigned int
0x18000e8e2  mov     r14d, 88h
0x18000e8e8  lea     esi, [rcx-1]
0x18000e8eb  mov     rdx, rbp; unsigned __int16 *
0x18000e8ee  call    ?ValidateMulticastIpAddress@CWdsTransportServicePolicy@@CAJKPEBG@Z; CWdsTransportServicePolicy::ValidateMulticastIpAddress(ulong,ushort const *)
0x18000e8f3  mov     r9d, 47Bh
0x18000e8f9  mov     ecx, eax
0x18000e8fb  mov     ebx, eax
0x18000e8fd  call    ElValidateHr_4
0x18000e902  test    eax, eax
0x18000e904  js      short loc_18000E973
0x18000e906  mov     rcx, rdi; this
0x18000e909  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e90e  mov     r9d, 481h
0x18000e914  mov     ecx, eax
0x18000e916  mov     ebx, eax
0x18000e918  call    ElValidateHr_4
0x18000e91d  test    eax, eax
0x18000e91f  js      short loc_18000E973
0x18000e921  lea     rdx, [rsp+48h+arg_0]
0x18000e926  mov     rcx, rbp
0x18000e929  call    cs:__imp_?WcsDupHr@@YAJPEBGPEAPEAG@Z; WcsDupHr(ushort const *,ushort * *)
0x18000e930  nop     dword ptr [rax+rax+00h]
0x18000e935  mov     ecx, eax
0x18000e937  mov     r9d, 488h
0x18000e93d  mov     ebx, eax
0x18000e93f  call    ElValidateHr_4
0x18000e944  test    eax, eax
0x18000e946  js      short loc_18000E973
0x18000e948  mov     rcx, [r14+rdi]
0x18000e94c  test    rcx, rcx
0x18000e94f  jz      short loc_18000E95D
0x18000e951  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000e958  nop     dword ptr [rax+rax+00h]
0x18000e95d  mov     rax, [rsp+48h+arg_0]
0x18000e962  mov     [r14+rdi], rax
0x18000e966  or      [rdi+80h], esi
0x18000e96c  jmp     short loc_18000E973
0x18000e96e  mov     ebx, 80070057h
0x18000e973  lea     rcx, [rsp+48h+var_28]
0x18000e978  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e97d  mov     rbp, [rsp+48h+arg_10]
0x18000e982  mov     eax, ebx
0x18000e984  mov     rbx, [rsp+48h+arg_8]
0x18000e989  mov     rsi, [rsp+48h+arg_18]
0x18000e98e  add     rsp, 30h
0x18000e992  pop     r15
0x18000e994  pop     r14
0x18000e996  pop     rdi
0x18000e997  retn
```
