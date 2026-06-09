# MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],ulong &>(char const (&)[26],ulong &)

- ea: `0x18000c508`
- end: `0x18000c588`
- name: `??$RPCCallTimedOut@AEAY0BK@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BK@$$CBDAEAK@Z`
- size: `128`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000e8b8`

## callees

- `0x180001010`
- `0x180001fec`
- `0x18000c508`
- `0x18000cea8`

## string_xrefs

- `0x18000c53c`: `WLIDCpGetConfigDWORDValue`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[26],unsigned long &>(
        __int64 a1,
        int *a2)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v4; // r9
  int v5; // r8d
  int v6; // r9d
  int v7; // ecx
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF
  const char *v10; // [rsp+68h] [rbp+20h] BYREF

  v8 = a1;
  result = MSAClientTraceTelemetry::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x400000000000LL, result, v4);
    if ( (_BYTE)result )
    {
      v7 = *a2;
      v10 = "WLIDCpGetConfigDWORDValue";
      LODWORD(v8) = v7;
      v9 = 50331648;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                                              v5,
                                              (unsigned int)&byte_18001BCB7,
                                              v5,
                                              v6,
                                              (__int64)&v10,
                                              (__int64)&v8,
                                              (__int64)&v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c508  mov     [rsp+arg_0], rcx
0x18000c50d  push    rbx
0x18000c50e  sub     rsp, 40h
0x18000c512  mov     rbx, rdx
0x18000c515  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000c51a  mov     r8, rax
0x18000c51d  mov     ecx, [rax]
0x18000c51f  cmp     ecx, 5
0x18000c522  jbe     short loc_18000C582
0x18000c524  mov     rdx, 400000000000h
0x18000c52e  mov     rcx, rax
0x18000c531  call    _tlgKeywordOn
0x18000c536  test    al, al
0x18000c538  jz      short loc_18000C582
0x18000c53a  mov     ecx, [rbx]
0x18000c53c  lea     rax, aWlidcpgetconfi; "WLIDCpGetConfigDWORDValue"
0x18000c543  mov     [rsp+48h+arg_18], rax
0x18000c548  lea     rdx, byte_18001BCB7
0x18000c54f  lea     rax, [rsp+48h+arg_10]
0x18000c554  mov     dword ptr [rsp+48h+arg_0], ecx
0x18000c558  mov     [rsp+48h+var_18], rax
0x18000c55d  mov     rcx, r8
0x18000c560  lea     rax, [rsp+48h+arg_0]
0x18000c565  mov     [rsp+48h+arg_10], 3000000h
0x18000c56e  mov     [rsp+48h+var_20], rax
0x18000c573  lea     rax, [rsp+48h+arg_18]
0x18000c578  mov     [rsp+48h+var_28], rax
0x18000c57d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18000c582  add     rsp, 40h
0x18000c586  pop     rbx
0x18000c587  retn
```
