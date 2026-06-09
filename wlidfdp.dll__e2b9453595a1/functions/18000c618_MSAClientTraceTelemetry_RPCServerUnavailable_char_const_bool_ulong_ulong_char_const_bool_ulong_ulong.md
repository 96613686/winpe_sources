# MSAClientTraceTelemetry::RPCServerUnavailable<char const * &,bool &,ulong &,ulong &>(char const * &,bool &,ulong &,ulong &)

- ea: `0x18000c618`
- end: `0x18000c6c3`
- name: `??$RPCServerUnavailable@AEAPEBDAEA_NAEAKAEAK@MSAClientTraceTelemetry@@SAXAEAPEBDAEA_NAEAK2@Z`
- size: `171`
- prototype: `const struct _tlgProvider_t *__fastcall(_QWORD *, _BYTE *, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000dd84`

## callees

- `0x1800010d4`
- `0x180001fec`
- `0x18000c618`
- `0x18000cea8`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall MSAClientTraceTelemetry::RPCServerUnavailable<char const * &,bool &,unsigned long &,unsigned long &>(
        _QWORD *a1,
        _BYTE *a2,
        int *a3,
        int *a4)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // r8d
  int v12; // r9d
  int v13; // r11d
  int v14; // ecx
  _BYTE v15[4]; // [rsp+50h] [rbp-48h] BYREF
  int v16; // [rsp+54h] [rbp-44h] BYREF
  int v17; // [rsp+58h] [rbp-40h] BYREF
  __int64 v18; // [rsp+60h] [rbp-38h] BYREF
  _QWORD v19[6]; // [rsp+68h] [rbp-30h] BYREF

  result = MSAClientTraceTelemetry::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x400000000000LL, v9, v10);
    if ( (_BYTE)result )
    {
      v14 = *a4;
      v17 = *a3;
      v15[0] = *a2;
      v19[0] = *a1;
      v16 = v14;
      v18 = 0x1000000;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                                              v13,
                                              (unsigned int)&dword_18001BEE4,
                                              v11,
                                              v12,
                                              (__int64)v19,
                                              (__int64)v15,
                                              (__int64)&v17,
                                              (__int64)&v16,
                                              (__int64)&v18);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c618  push    rbx
0x18000c61a  push    rsi
0x18000c61b  push    rdi
0x18000c61c  push    r14
0x18000c61e  sub     rsp, 78h
0x18000c622  mov     rbx, r9
0x18000c625  mov     rdi, r8
0x18000c628  mov     rsi, rdx
0x18000c62b  mov     r14, rcx
0x18000c62e  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000c633  mov     r11, rax
0x18000c636  mov     r10d, [rax]
0x18000c639  cmp     r10d, 5
0x18000c63d  jbe     short loc_18000C6B9
0x18000c63f  mov     rdx, 400000000000h
0x18000c649  mov     rcx, rax
0x18000c64c  call    _tlgKeywordOn
0x18000c651  test    al, al
0x18000c653  jz      short loc_18000C6B9
0x18000c655  mov     eax, [rdi]
0x18000c657  lea     rdx, dword_18001BEE4
0x18000c65e  mov     ecx, [rbx]
0x18000c660  mov     [rsp+98h+var_40], eax
0x18000c664  mov     al, [rsi]
0x18000c666  mov     [rsp+98h+var_48], al
0x18000c66a  mov     rax, [r14]
0x18000c66d  mov     [rsp+98h+var_30], rax
0x18000c672  lea     rax, [rsp+98h+var_38]
0x18000c677  mov     [rsp+98h+var_58], rax
0x18000c67c  lea     rax, [rsp+98h+var_44]
0x18000c681  mov     [rsp+98h+var_60], rax
0x18000c686  lea     rax, [rsp+98h+var_40]
0x18000c68b  mov     [rsp+98h+var_68], rax
0x18000c690  lea     rax, [rsp+98h+var_48]
0x18000c695  mov     [rsp+98h+var_70], rax
0x18000c69a  lea     rax, [rsp+98h+var_30]
0x18000c69f  mov     [rsp+98h+var_44], ecx
0x18000c6a3  mov     rcx, r11
0x18000c6a6  mov     [rsp+98h+var_78], rax
0x18000c6ab  mov     [rsp+98h+var_38], 1000000h
0x18000c6b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18000c6b9  add     rsp, 78h
0x18000c6bd  pop     r14
0x18000c6bf  pop     rdi
0x18000c6c0  pop     rsi
0x18000c6c1  pop     rbx
0x18000c6c2  retn
```
