# CWdsTransportServicePolicy::get_EnableTftpVariableWindowExtension(short *)

- ea: `0x18000deb0`
- end: `0x18000df34`
- name: `?get_EnableTftpVariableWindowExtension@CWdsTransportServicePolicy@@UEAAJPEAF@Z`
- size: `132`
- prototype: `__int64 __fastcall(CWdsTransportServicePolicy *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x18000cef4`
- `0x18000dd50`
- `0x18000deb0`
- `0x18000eb74`

## pseudocode

```c
__int64 __fastcall CWdsTransportServicePolicy::get_EnableTftpVariableWindowExtension(
        CWdsTransportServicePolicy *this,
        __int16 *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v10, (char *)this + 80);
  v4 = CWdsTransportServicePolicy::DelayInitialize(this);
  if ( (int)ElValidateHr_4(v4, v5, v6, 2000) >= 0 )
  {
    v4 = CWdsTransportServicePolicy::VerifyTftpVariableWindowSupported(this);
    if ( (int)ElValidateHr_4(v4, v7, v8, 2007) >= 0 )
      *a2 = -(*((_DWORD *)this + 49) != 0);
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v10);
  return v4;
}

```

## disassembly

```asm
0x18000deb0  mov     [rsp+arg_0], rbx
0x18000deb5  mov     [rsp+arg_8], rsi
0x18000deba  push    rdi
0x18000debb  sub     rsp, 30h
0x18000debf  mov     rsi, rdx
0x18000dec2  mov     rdi, rcx
0x18000dec5  lea     rdx, [rcx+50h]
0x18000dec9  lea     rcx, [rsp+38h+var_18]
0x18000dece  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000ded3  mov     rcx, rdi; this
0x18000ded6  call    ?DelayInitialize@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::DelayInitialize(void)
0x18000dedb  mov     r9d, 7D0h
0x18000dee1  mov     ecx, eax
0x18000dee3  mov     ebx, eax
0x18000dee5  call    ElValidateHr_4
0x18000deea  test    eax, eax
0x18000deec  js      short loc_18000DF17
0x18000deee  mov     rcx, rdi; this
0x18000def1  call    ?VerifyTftpVariableWindowSupported@CWdsTransportServicePolicy@@QEAAJXZ; CWdsTransportServicePolicy::VerifyTftpVariableWindowSupported(void)
0x18000def6  mov     r9d, 7D7h
0x18000defc  mov     ecx, eax
0x18000defe  mov     ebx, eax
0x18000df00  call    ElValidateHr_4
0x18000df05  test    eax, eax
0x18000df07  js      short loc_18000DF17
0x18000df09  mov     eax, [rdi+0C4h]
0x18000df0f  neg     eax
0x18000df11  sbb     cx, cx
0x18000df14  mov     [rsi], cx
0x18000df17  lea     rcx, [rsp+38h+var_18]
0x18000df1c  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000df21  mov     rsi, [rsp+38h+arg_8]
0x18000df26  mov     eax, ebx
0x18000df28  mov     rbx, [rsp+38h+arg_0]
0x18000df2d  add     rsp, 30h
0x18000df31  pop     rdi
0x18000df32  retn
```
