# CWdsTransportServicePolicy::put_StartPort(ulong)

- ea: `0x18000e9a0`
- end: `0x18000ea1b`
- name: `?put_StartPort@CWdsTransportServicePolicy@@UEAAJK@Z`
- size: `123`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000e9a0`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::put_StartPort(CWdsTransportServicePolicy *this, int a2)
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
    if ( (int)ElValidateHr_4(v4, v5, v6, 1469) >= 0 )
    {
      *((_DWORD *)this + 32) |= 4u;
      *((_DWORD *)this + 44) = a2;
    }
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v8);
  return v4;
}

```

## disassembly

```asm
0x18000e9a0  mov     [rsp+arg_0], rbx
0x18000e9a5  mov     [rsp+arg_8], rsi
0x18000e9aa  push    rdi
0x18000e9ab  sub     rsp, 30h
0x18000e9af  mov     esi, edx
0x18000e9b1  mov     rbx, rcx
0x18000e9b4  lea     rdx, [rcx+50h]
0x18000e9b8  lea     rcx, [rsp+38h+var_18]
0x18000e9bd  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e9c2  lea     eax, [rsi-401h]
0x18000e9c8  cmp     eax, 0FBFFh
0x18000e9cd  ja      short loc_18000E9F9
0x18000e9cf  mov     rcx, rbx; this
0x18000e9d2  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e9d7  mov     r9d, 5BDh
0x18000e9dd  mov     ecx, eax
0x18000e9df  mov     edi, eax
0x18000e9e1  call    ElValidateHr_4
0x18000e9e6  test    eax, eax
0x18000e9e8  js      short loc_18000E9FE
0x18000e9ea  or      dword ptr [rbx+80h], 4
0x18000e9f1  mov     [rbx+0B0h], esi
0x18000e9f7  jmp     short loc_18000E9FE
0x18000e9f9  mov     edi, 0C1100111h
0x18000e9fe  lea     rcx, [rsp+38h+var_18]
0x18000ea03  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000ea08  mov     rbx, [rsp+38h+arg_0]
0x18000ea0d  mov     eax, edi
0x18000ea0f  mov     rsi, [rsp+38h+arg_8]
0x18000ea14  add     rsp, 30h
0x18000ea18  pop     rdi
0x18000ea19  retn
```
