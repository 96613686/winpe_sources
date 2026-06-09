# CSetAppropriateActivityId::InitInternal(ushort *)

- ea: `0x180020e44`
- end: `0x180020f01`
- name: `?InitInternal@CSetAppropriateActivityId@@AEAAJPEAG@Z`
- size: `189`
- prototype: `__int64 __fastcall(struct _GUID *this, LPCOLESTR lpsz)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001fd90`
- `0x18002057c`
- `0x180020610`
- `0x1800207c0`
- `0x180020fd0`
- `0x180043770`

## callees

- `0x180020e44`
- `0x180020f08`
- `0x180021540`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180020e78`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180020e78`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180020e97`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180020e97`

## pseudocode

```c
HRESULT __fastcall CSetAppropriateActivityId::InitInternal(struct _GUID *this, LPCOLESTR lpsz)
{
  HRESULT result; // eax
  int v4; // edi
  GUID pclsid; // [rsp+20h] [rbp-28h] BYREF

  pclsid = 0;
  if ( !lpsz )
    return 0;
  result = CLSIDFromString(lpsz, &pclsid);
  if ( result >= 0 )
  {
    if ( CWbemInstallObject::m_bOffline )
      return 1;
    result = CPublishWMIOperationEvent::GetFunctionPointers();
    if ( result >= 0 )
    {
      result = CoCreateGuid(this);
      if ( result >= 0 )
      {
        v4 = CSetAppropriateActivityId::WriteTransferEvent(this, &pclsid);
        if ( v4 < 0 )
          return v4;
        result = ((__int64 (__fastcall *)(__int64, struct _GUID *))CPublishWMIOperationEvent::m_fEventActivityIdControl)(
                   4,
                   this);
        if ( !result )
        {
          LOBYTE(this[1].Data1) = 1;
          return v4;
        }
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180020e44  mov     [rsp+arg_10], rbx
0x180020e49  push    rdi
0x180020e4a  sub     rsp, 40h
0x180020e4e  mov     rax, cs:__security_cookie
0x180020e55  xor     rax, rsp
0x180020e58  mov     [rsp+48h+var_18], rax
0x180020e5d  xorps   xmm0, xmm0
0x180020e60  mov     rax, rdx
0x180020e63  mov     rbx, rcx
0x180020e66  movups  xmmword ptr [rsp+48h+pclsid.Data1], xmm0
0x180020e6b  test    rdx, rdx
0x180020e6e  jz      short loc_180020EEA
0x180020e70  lea     rdx, [rsp+48h+pclsid]; pclsid
0x180020e75  mov     rcx, rax; lpsz
0x180020e78  call    cs:__imp_CLSIDFromString
0x180020e7e  test    eax, eax
0x180020e80  js      short loc_180020ED2
0x180020e82  cmp     cs:?m_bOffline@CWbemInstallObject@@0_NA, 0; bool CWbemInstallObject::m_bOffline
0x180020e89  jnz     short loc_180020EFA
0x180020e8b  call    ?GetFunctionPointers@CPublishWMIOperationEvent@@SAJXZ; CPublishWMIOperationEvent::GetFunctionPointers(void)
0x180020e90  test    eax, eax
0x180020e92  js      short loc_180020ED2
0x180020e94  mov     rcx, rbx; pguid
0x180020e97  call    cs:__imp_CoCreateGuid
0x180020e9d  test    eax, eax
0x180020e9f  js      short loc_180020ED2
0x180020ea1  lea     rdx, [rsp+48h+pclsid]; struct _GUID *
0x180020ea6  mov     rcx, rbx; struct _GUID *
0x180020ea9  call    ?WriteTransferEvent@CSetAppropriateActivityId@@CAJPEAU_GUID@@0@Z; CSetAppropriateActivityId::WriteTransferEvent(_GUID *,_GUID *)
0x180020eae  mov     edi, eax
0x180020eb0  test    eax, eax
0x180020eb2  js      short loc_180020ED0
0x180020eb4  mov     rax, cs:?m_fEventActivityIdControl@CPublishWMIOperationEvent@@2P6AKKPEAU_GUID@@@ZEA; ulong (*CPublishWMIOperationEvent::m_fEventActivityIdControl)(ulong,_GUID *)
0x180020ebb  mov     rdx, rbx
0x180020ebe  mov     ecx, 4
0x180020ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ec8  test    eax, eax
0x180020eca  jnz     short loc_180020EEE
0x180020ecc  mov     byte ptr [rbx+10h], 1
0x180020ed0  mov     eax, edi
0x180020ed2  mov     rcx, [rsp+48h+var_18]
0x180020ed7  xor     rcx, rsp; StackCookie
0x180020eda  call    __security_check_cookie
0x180020edf  mov     rbx, [rsp+48h+arg_10]
0x180020ee4  add     rsp, 40h
0x180020ee8  pop     rdi
0x180020ee9  retn
0x180020eea  xor     eax, eax
0x180020eec  jmp     short loc_180020ED2
0x180020eee  jle     short loc_180020ED2
0x180020ef0  movzx   eax, ax
0x180020ef3  or      eax, 80070000h
0x180020ef8  jmp     short loc_180020ED2
0x180020efa  mov     eax, 1
0x180020eff  jmp     short loc_180020ED2
```
