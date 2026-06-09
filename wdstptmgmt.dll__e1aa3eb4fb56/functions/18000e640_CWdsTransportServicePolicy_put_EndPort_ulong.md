# CWdsTransportServicePolicy::put_EndPort(ulong)

- ea: `0x18000e640`
- end: `0x18000e6bb`
- name: `?put_EndPort@CWdsTransportServicePolicy@@UEAAJK@Z`
- size: `123`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000e640`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::put_EndPort(CWdsTransportServicePolicy *this, int a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // r8
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v8, (char *)this + 80);
  if ( (unsigned int)(a2 - 1025) > 0xFBFF )
  {
    v4 = -1055915759;
  }
  else
  {
    v4 = CWdsTransportServicePolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_4(v4, v5, v6, 1581) >= 0 )
    {
      *((_DWORD *)this + 32) |= 4u;
      *((_DWORD *)this + 45) = a2;
    }
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return v4;
}

```

## disassembly

```asm
0x18000e640  mov     [rsp+arg_0], rbx
0x18000e645  mov     [rsp+arg_8], rsi
0x18000e64a  push    rdi
0x18000e64b  sub     rsp, 30h
0x18000e64f  mov     esi, edx
0x18000e651  mov     rbx, rcx
0x18000e654  lea     rdx, [rcx+50h]
0x18000e658  lea     rcx, [rsp+38h+var_18]
0x18000e65d  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e662  lea     eax, [rsi-401h]
0x18000e668  cmp     eax, 0FBFFh
0x18000e66d  ja      short loc_18000E699
0x18000e66f  mov     rcx, rbx; this
0x18000e672  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e677  mov     r9d, 62Dh
0x18000e67d  mov     ecx, eax
0x18000e67f  mov     edi, eax
0x18000e681  call    ElValidateHr_4
0x18000e686  test    eax, eax
0x18000e688  js      short loc_18000E69E
0x18000e68a  or      dword ptr [rbx+80h], 4
0x18000e691  mov     [rbx+0B4h], esi
0x18000e697  jmp     short loc_18000E69E
0x18000e699  mov     edi, 0C1100111h
0x18000e69e  lea     rcx, [rsp+38h+var_18]
0x18000e6a3  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e6a8  mov     rbx, [rsp+38h+arg_0]
0x18000e6ad  mov     eax, edi
0x18000e6af  mov     rsi, [rsp+38h+arg_8]
0x18000e6b4  add     rsp, 30h
0x18000e6b8  pop     rdi
0x18000e6b9  retn
```
