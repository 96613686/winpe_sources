# CWdsTransportServicePolicy::get_StartPort(ulong *)

- ea: `0x18000e2b0`
- end: `0x18000e31f`
- name: `?get_StartPort@CWdsTransportServicePolicy@@UEAAJPEAK@Z`
- size: `111`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000e2b0`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::get_StartPort(CWdsTransportServicePolicy *this, unsigned int *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 80);
  if ( a2 )
  {
    v4 = CWdsTransportServicePolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_4(v4, v5, v6, 1411) >= 0 )
      *a2 = *((_DWORD *)this + 44);
  }
  else
  {
    v4 = -2147024809;
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return v4;
}

```

## disassembly

```asm
0x18000e2b0  mov     [rsp+arg_0], rbx
0x18000e2b5  mov     [rsp+arg_8], rsi
0x18000e2ba  push    rdi
0x18000e2bb  sub     rsp, 30h
0x18000e2bf  mov     rsi, rdx
0x18000e2c2  mov     rdi, rcx
0x18000e2c5  lea     rdx, [rcx+50h]
0x18000e2c9  lea     rcx, [rsp+38h+var_18]
0x18000e2ce  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e2d3  test    rsi, rsi
0x18000e2d6  jnz     short loc_18000E2DF
0x18000e2d8  mov     ebx, 80070057h
0x18000e2dd  jmp     short loc_18000E302
0x18000e2df  mov     rcx, rdi; this
0x18000e2e2  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e2e7  mov     r9d, 583h
0x18000e2ed  mov     ecx, eax
0x18000e2ef  mov     ebx, eax
0x18000e2f1  call    ElValidateHr_4
0x18000e2f6  test    eax, eax
0x18000e2f8  js      short loc_18000E302
0x18000e2fa  mov     ecx, [rdi+0B0h]
0x18000e300  mov     [rsi], ecx
0x18000e302  lea     rcx, [rsp+38h+var_18]
0x18000e307  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e30c  mov     rsi, [rsp+38h+arg_8]
0x18000e311  mov     eax, ebx
0x18000e313  mov     rbx, [rsp+38h+arg_0]
0x18000e318  add     rsp, 30h
0x18000e31c  pop     rdi
0x18000e31d  retn
```
