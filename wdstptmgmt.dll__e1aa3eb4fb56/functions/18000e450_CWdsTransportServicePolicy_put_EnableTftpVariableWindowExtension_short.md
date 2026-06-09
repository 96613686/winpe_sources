# CWdsTransportServicePolicy::put_EnableTftpVariableWindowExtension(short)

- ea: `0x18000e450`
- end: `0x18000e4e6`
- name: `?put_EnableTftpVariableWindowExtension@CWdsTransportServicePolicy@@UEAAJF@Z`
- size: `150`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dd50`
- `0x18000e450`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::put_EnableTftpVariableWindowExtension(
        CWdsTransportServicePolicy *this,
        __int16 a2)
{
  unsigned int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // r8
  _BYTE v11[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v11, (char *)this + 80);
  v4 = CWdsTransportServicePolicy::DelayInitialize(this);
  v7 = 0;
  if ( (int)ElValidateHr_4(v4, v5, v6, 2052) >= 0 )
  {
    v4 = CWdsTransportServicePolicy::VerifyTftpVariableWindowSupported(this);
    if ( (int)ElValidateHr_4(v4, v8, v9, 2059) >= 0 )
    {
      LOBYTE(v7) = a2 == -1;
      *((_DWORD *)this + 49) = v7;
      *((_DWORD *)this + 32) |= 0x40u;
    }
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v11);
  return v4;
}

```

## disassembly

```asm
0x18000e450  mov     rax, rsp
0x18000e453  mov     [rax+8], rbx
0x18000e457  mov     [rax+10h], rbp
0x18000e45b  mov     [rax+18h], rsi
0x18000e45f  push    rdi
0x18000e460  sub     rsp, 30h
0x18000e464  movzx   ebp, dx
0x18000e467  mov     rbx, rcx
0x18000e46a  lea     rdx, [rcx+50h]
0x18000e46e  lea     rcx, [rax-18h]
0x18000e472  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000e477  mov     rcx, rbx; this
0x18000e47a  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000e47f  mov     r9d, 804h
0x18000e485  mov     ecx, eax
0x18000e487  mov     esi, eax
0x18000e489  call    ElValidateHr_4
0x18000e48e  xor     edi, edi
0x18000e490  test    eax, eax
0x18000e492  js      short loc_18000E4C4
0x18000e494  mov     rcx, rbx; this
0x18000e497  call    ?VerifyTftpVariableWindowSupported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyTftpVariableWindowSupported(void)
0x18000e49c  mov     r9d, 80Bh
0x18000e4a2  mov     ecx, eax
0x18000e4a4  mov     esi, eax
0x18000e4a6  call    ElValidateHr_4
0x18000e4ab  test    eax, eax
0x18000e4ad  js      short loc_18000E4C4
0x18000e4af  cmp     bp, 0FFFFh
0x18000e4b3  setz    dil
0x18000e4b7  mov     [rbx+0C4h], edi
0x18000e4bd  or      dword ptr [rbx+80h], 40h
0x18000e4c4  lea     rcx, [rsp+38h+var_18]
0x18000e4c9  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000e4ce  mov     rbx, [rsp+38h+arg_0]
0x18000e4d3  mov     eax, esi
0x18000e4d5  mov     rsi, [rsp+38h+arg_10]
0x18000e4da  mov     rbp, [rsp+38h+arg_8]
0x18000e4df  add     rsp, 30h
0x18000e4e3  pop     rdi
0x18000e4e4  retn
```
