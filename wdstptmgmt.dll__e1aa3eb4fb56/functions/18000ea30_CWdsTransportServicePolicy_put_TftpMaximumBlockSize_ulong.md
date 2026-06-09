# CWdsTransportServicePolicy::put_TftpMaximumBlockSize(ulong)

- ea: `0x18000ea30`
- end: `0x18000eacb`
- name: `?put_TftpMaximumBlockSize@CWdsTransportServicePolicy@@UEAAJK@Z`
- size: `155`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dd08`
- `0x18000ea30`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::put_TftpMaximumBlockSize(
        CWdsTransportServicePolicy *this,
        unsigned int a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v10, (char *)this + 80);
  if ( a2 - 1 <= 0x1FE || a2 >= 0xFFFC )
  {
    v4 = -1055915741;
  }
  else
  {
    v4 = CWdsTransportServicePolicy::DelayInitialize(this);
    if ( (int)ElValidateHr_4(v4, v5, v6, 1947) >= 0 )
    {
      v4 = CWdsTransportServicePolicy::VerifyTftpMaximumBlockSizeSupported(this);
      if ( (int)ElValidateHr_4(v4, v7, v8, 1954) >= 0 )
      {
        *((_DWORD *)this + 32) |= 0x20u;
        *((_DWORD *)this + 48) = a2;
      }
    }
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v4;
}

```

## disassembly

```asm
0x18000ea30  mov     [rsp+arg_0], rbx
0x18000ea35  mov     [rsp+arg_8], rsi
0x18000ea3a  push    rdi
0x18000ea3b  sub     rsp, 30h
0x18000ea3f  mov     esi, edx
0x18000ea41  mov     rbx, rcx
0x18000ea44  lea     rdx, [rcx+50h]
0x18000ea48  lea     rcx, [rsp+38h+var_18]
0x18000ea4d  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000ea52  lea     eax, [rsi-1]
0x18000ea55  cmp     eax, 1FEh
0x18000ea5a  jbe     short loc_18000EAA9
0x18000ea5c  cmp     esi, 0FFFCh
0x18000ea62  jnb     short loc_18000EAA9
0x18000ea64  mov     rcx, rbx; this
0x18000ea67  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000ea6c  mov     r9d, 79Bh
0x18000ea72  mov     ecx, eax
0x18000ea74  mov     edi, eax
0x18000ea76  call    ElValidateHr_4
0x18000ea7b  test    eax, eax
0x18000ea7d  js      short loc_18000EAAE
0x18000ea7f  mov     rcx, rbx; this
0x18000ea82  call    ?VerifyTftpMaximumBlockSizeSupported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyTftpMaximumBlockSizeSupported(void)
0x18000ea87  mov     r9d, 7A2h
0x18000ea8d  mov     ecx, eax
0x18000ea8f  mov     edi, eax
0x18000ea91  call    ElValidateHr_4
0x18000ea96  test    eax, eax
0x18000ea98  js      short loc_18000EAAE
0x18000ea9a  or      dword ptr [rbx+80h], 20h
0x18000eaa1  mov     [rbx+0C0h], esi
0x18000eaa7  jmp     short loc_18000EAAE
0x18000eaa9  mov     edi, 0C1100123h
0x18000eaae  lea     rcx, [rsp+38h+var_18]
0x18000eab3  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000eab8  mov     rbx, [rsp+38h+arg_0]
0x18000eabd  mov     eax, edi
0x18000eabf  mov     rsi, [rsp+38h+arg_8]
0x18000eac4  add     rsp, 30h
0x18000eac8  pop     rdi
0x18000eac9  retn
```
