# CWdsTransportDiagnosticsPolicy::get_Components(ulong *)

- ea: `0x18000fab0`
- end: `0x18000fb1f`
- name: `?get_Components@CWdsTransportDiagnosticsPolicy@@UEAAJPEAK@Z`
- size: `111`
- prototype: `__int64 __fastcall(CWdsTransportDiagnosticsPolicy *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000f43c`
- `0x18000fab0`
- `0x18000fca8`

## pseudocode

```c
__int64 __fastcall CWdsTransportDiagnosticsPolicy::get_Components(
        CWdsTransportDiagnosticsPolicy *this,
        unsigned int *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 80);
  if ( a2 )
  {
    v4 = CWdsTransportDiagnosticsPolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_5(v4, v5, v6, 375) >= 0 )
      *a2 = *((_DWORD *)this + 34);
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
0x18000fab0  mov     [rsp+arg_0], rbx
0x18000fab5  mov     [rsp+arg_8], rsi
0x18000faba  push    rdi
0x18000fabb  sub     rsp, 30h
0x18000fabf  mov     rsi, rdx
0x18000fac2  mov     rdi, rcx
0x18000fac5  lea     rdx, [rcx+50h]
0x18000fac9  lea     rcx, [rsp+38h+var_18]
0x18000face  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000fad3  test    rsi, rsi
0x18000fad6  jnz     short loc_18000FADF
0x18000fad8  mov     ebx, 80070057h
0x18000fadd  jmp     short loc_18000FB02
0x18000fadf  mov     rcx, rdi; this
0x18000fae2  call    ?DelayInitialize@CWdsTransportDiagnosticsPolicy@@QEAAJXZ; CWdsTransportDiagnosticsPolicy::DelayInitialize(void)
0x18000fae7  mov     r9d, 177h
0x18000faed  mov     ecx, eax
0x18000faef  mov     ebx, eax
0x18000faf1  call    ElValidateHr_5
0x18000faf6  test    eax, eax
0x18000faf8  js      short loc_18000FB02
0x18000fafa  mov     ecx, [rdi+88h]
0x18000fb00  mov     [rsi], ecx
0x18000fb02  lea     rcx, [rsp+38h+var_18]
0x18000fb07  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000fb0c  mov     rsi, [rsp+38h+arg_8]
0x18000fb11  mov     eax, ebx
0x18000fb13  mov     rbx, [rsp+38h+arg_0]
0x18000fb18  add     rsp, 30h
0x18000fb1c  pop     rdi
0x18000fb1d  retn
```
