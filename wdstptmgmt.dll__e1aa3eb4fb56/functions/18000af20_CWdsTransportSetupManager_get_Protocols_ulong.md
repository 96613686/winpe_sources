# CWdsTransportSetupManager::get_Protocols(ulong *)

- ea: `0x18000af20`
- end: `0x18000af76`
- name: `?get_Protocols@CWdsTransportSetupManager@@UEAAJPEAK@Z`
- size: `86`
- prototype: `__int64 __fastcall(CWdsTransportSetupManager *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000af20`

## pseudocode

```c
__int64 __fastcall CWdsTransportSetupManager::get_Protocols(CWdsTransportSetupManager *this, unsigned int *a2)
{
  unsigned int v4; // ebx
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF

  v4 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v6, (char *)this + 80);
  if ( a2 )
    *a2 = *((_DWORD *)this + 34);
  else
    v4 = -2147024809;
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v6);
  return v4;
}

```

## disassembly

```asm
0x18000af20  mov     [rsp+arg_0], rbx
0x18000af25  mov     [rsp+arg_8], rsi
0x18000af2a  push    rdi
0x18000af2b  sub     rsp, 30h
0x18000af2f  mov     rdi, rdx
0x18000af32  mov     rsi, rcx
0x18000af35  lea     rdx, [rcx+50h]
0x18000af39  xor     ebx, ebx
0x18000af3b  lea     rcx, [rsp+38h+var_18]
0x18000af40  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000af45  test    rdi, rdi
0x18000af48  jnz     short loc_18000AF51
0x18000af4a  mov     ebx, 80070057h
0x18000af4f  jmp     short loc_18000AF59
0x18000af51  mov     ecx, [rsi+88h]
0x18000af57  mov     [rdi], ecx
0x18000af59  lea     rcx, [rsp+38h+var_18]
0x18000af5e  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000af63  mov     rsi, [rsp+38h+arg_8]
0x18000af68  mov     eax, ebx
0x18000af6a  mov     rbx, [rsp+38h+arg_0]
0x18000af6f  add     rsp, 30h
0x18000af73  pop     rdi
0x18000af74  retn
```
