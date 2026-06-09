# CWdsTransportServicePolicy::get_TftpMaximumBlockSize(ulong *)

- ea: `0x18000e330`
- end: `0x18000e3ba`
- name: `?get_TftpMaximumBlockSize@CWdsTransportServicePolicy@@UEAAJPEAK@Z`
- size: `138`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dd08`
- `0x18000e330`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::get_TftpMaximumBlockSize(
        CWdsTransportServicePolicy *this,
        unsigned int *a2)
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
    if ( (int)ElValidateHr_4(v4, v5, v6, 1884) >= 0 )
    {
      v4 = CWdsTransportServicePolicy::VerifyTftpMaximumBlockSizeSupported(this);
      if ( (int)ElValidateHr_4(v4, v7, v8, 1891) >= 0 )
        *a2 = *((_DWORD *)this + 48);
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
0x18000e330  mov     [rsp+arg_0], rbx
0x18000e335  mov     [rsp+arg_8], rsi
0x18000e33a  push    rdi
0x18000e33b  sub     rsp, 30h
0x18000e33f  mov     rsi, rdx
0x18000e342  mov     rdi, rcx
0x18000e345  lea     rdx, [rcx+50h]
0x18000e349  lea     rcx, [rsp+38h+var_18]
0x18000e34e  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e353  test    rsi, rsi
0x18000e356  jnz     short loc_18000E35F
0x18000e358  mov     ebx, 80070057h
0x18000e35d  jmp     short loc_18000E39D
0x18000e35f  mov     rcx, rdi; this
0x18000e362  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e367  mov     r9d, 75Ch
0x18000e36d  mov     ecx, eax
0x18000e36f  mov     ebx, eax
0x18000e371  call    ElValidateHr_4
0x18000e376  test    eax, eax
0x18000e378  js      short loc_18000E39D
0x18000e37a  mov     rcx, rdi; this
0x18000e37d  call    ?VerifyTftpMaximumBlockSizeSupported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyTftpMaximumBlockSizeSupported(void)
0x18000e382  mov     r9d, 763h
0x18000e388  mov     ecx, eax
0x18000e38a  mov     ebx, eax
0x18000e38c  call    ElValidateHr_4
0x18000e391  test    eax, eax
0x18000e393  js      short loc_18000E39D
0x18000e395  mov     eax, [rdi+0C0h]
0x18000e39b  mov     [rsi], eax
0x18000e39d  lea     rcx, [rsp+38h+var_18]
0x18000e3a2  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e3a7  mov     rsi, [rsp+38h+arg_8]
0x18000e3ac  mov     eax, ebx
0x18000e3ae  mov     rbx, [rsp+38h+arg_0]
0x18000e3b3  add     rsp, 30h
0x18000e3b7  pop     rdi
0x18000e3b8  retn
```
