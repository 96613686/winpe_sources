# CWdsTransportDiagnosticsPolicy::put_Components(ulong)

- ea: `0x18000fbb0`
- end: `0x18000fc26`
- name: `?put_Components@CWdsTransportDiagnosticsPolicy@@UEAAJK@Z`
- size: `118`
- prototype: `__int64 __fastcall(CWdsTransportDiagnosticsPolicy *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000f43c`
- `0x18000fbb0`
- `0x18000fca8`

## pseudocode

```c
__int64 __fastcall CWdsTransportDiagnosticsPolicy::put_Components(CWdsTransportDiagnosticsPolicy *this, int a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 80);
  if ( (a2 & 0xFFFFFFF0) != 0 )
  {
    v4 = -1055915762;
  }
  else
  {
    v4 = CWdsTransportDiagnosticsPolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_5(v4, v5, v6, 430) >= 0 )
    {
      *((_DWORD *)this + 32) |= 2u;
      *((_DWORD *)this + 34) = a2;
    }
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return v4;
}

```

## disassembly

```asm
0x18000fbb0  mov     [rsp+arg_0], rbx
0x18000fbb5  mov     [rsp+arg_8], rsi
0x18000fbba  push    rdi
0x18000fbbb  sub     rsp, 30h
0x18000fbbf  mov     esi, edx
0x18000fbc1  mov     rbx, rcx
0x18000fbc4  lea     rdx, [rcx+50h]
0x18000fbc8  lea     rcx, [rsp+38h+var_18]
0x18000fbcd  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000fbd2  test    esi, 0FFFFFFF0h
0x18000fbd8  jz      short loc_18000FBE1
0x18000fbda  mov     edi, 0C110010Eh
0x18000fbdf  jmp     short loc_18000FC09
0x18000fbe1  mov     rcx, rbx; this
0x18000fbe4  call    ?DelayInitialize@CWdsTransportDiagnosticsPolicy@@QEAAJXZ; CWdsTransportDiagnosticsPolicy::DelayInitialize(void)
0x18000fbe9  mov     r9d, 1AEh
0x18000fbef  mov     ecx, eax
0x18000fbf1  mov     edi, eax
0x18000fbf3  call    ElValidateHr_5
0x18000fbf8  test    eax, eax
0x18000fbfa  js      short loc_18000FC09
0x18000fbfc  or      dword ptr [rbx+80h], 2
0x18000fc03  mov     [rbx+88h], esi
0x18000fc09  lea     rcx, [rsp+38h+var_18]
0x18000fc0e  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000fc13  mov     rbx, [rsp+38h+arg_0]
0x18000fc18  mov     eax, edi
0x18000fc1a  mov     rsi, [rsp+38h+arg_8]
0x18000fc1f  add     rsp, 30h
0x18000fc23  pop     rdi
0x18000fc24  retn
```
