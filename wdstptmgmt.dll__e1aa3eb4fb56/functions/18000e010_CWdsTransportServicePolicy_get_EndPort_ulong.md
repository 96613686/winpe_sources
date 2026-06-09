# CWdsTransportServicePolicy::get_EndPort(ulong *)

- ea: `0x18000e010`
- end: `0x18000e07f`
- name: `?get_EndPort@CWdsTransportServicePolicy@@UEAAJPEAK@Z`
- size: `111`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000e010`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::get_EndPort(CWdsTransportServicePolicy *this, unsigned int *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 80);
  if ( a2 )
  {
    v4 = CWdsTransportServicePolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_4(v4, v5, v6, 1523) >= 0 )
      *a2 = *((_DWORD *)this + 45);
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
0x18000e010  mov     [rsp+arg_0], rbx
0x18000e015  mov     [rsp+arg_8], rsi
0x18000e01a  push    rdi
0x18000e01b  sub     rsp, 30h
0x18000e01f  mov     rsi, rdx
0x18000e022  mov     rdi, rcx
0x18000e025  lea     rdx, [rcx+50h]
0x18000e029  lea     rcx, [rsp+38h+var_18]
0x18000e02e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e033  test    rsi, rsi
0x18000e036  jnz     short loc_18000E03F
0x18000e038  mov     ebx, 80070057h
0x18000e03d  jmp     short loc_18000E062
0x18000e03f  mov     rcx, rdi; this
0x18000e042  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e047  mov     r9d, 5F3h
0x18000e04d  mov     ecx, eax
0x18000e04f  mov     ebx, eax
0x18000e051  call    ElValidateHr_4
0x18000e056  test    eax, eax
0x18000e058  js      short loc_18000E062
0x18000e05a  mov     ecx, [rdi+0B4h]
0x18000e060  mov     [rsi], ecx
0x18000e062  lea     rcx, [rsp+38h+var_18]
0x18000e067  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e06c  mov     rsi, [rsp+38h+arg_8]
0x18000e071  mov     eax, ebx
0x18000e073  mov     rbx, [rsp+38h+arg_0]
0x18000e078  add     rsp, 30h
0x18000e07c  pop     rdi
0x18000e07d  retn
```
