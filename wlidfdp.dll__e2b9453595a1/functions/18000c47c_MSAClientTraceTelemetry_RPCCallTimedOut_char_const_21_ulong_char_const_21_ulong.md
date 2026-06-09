# MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],ulong &>(char const (&)[21],ulong &)

- ea: `0x18000c47c`
- end: `0x18000c4ff`
- name: `??$RPCCallTimedOut@AEAY0BF@$$CBDAEAK@MSAClientTraceTelemetry@@SAXAEAY0BF@$$CBDAEAK@Z`
- size: `131`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000de3c`
- `0x18000e1c0`

## callees

- `0x180001010`
- `0x180001fec`
- `0x18000c47c`
- `0x18000cea8`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall MSAClientTraceTelemetry::RPCCallTimedOut<char const (&)[21],unsigned long &>(
        __int64 a1,
        int *a2)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v5; // r8
  int v6; // r8d
  int v7; // r9d
  _QWORD v8[3]; // [rsp+40h] [rbp-18h] BYREF
  int v9; // [rsp+70h] [rbp+18h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  result = MSAClientTraceTelemetry::Provider();
  v5 = *(unsigned int *)result;
  if ( (unsigned int)v5 > 5 )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x400000000000LL, v5, result);
    if ( (_BYTE)result )
    {
      v9 = *a2;
      v10 = 50331648;
      v8[0] = a1;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                                              v7,
                                              (unsigned int)byte_18001BAF9,
                                              v6,
                                              v7,
                                              (__int64)v8,
                                              (__int64)&v9,
                                              (__int64)&v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c47c  mov     [rsp+arg_0], rbx
0x18000c481  push    rdi
0x18000c482  sub     rsp, 50h
0x18000c486  mov     rbx, rdx
0x18000c489  mov     rdi, rcx
0x18000c48c  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000c491  mov     r9, rax
0x18000c494  mov     r8d, [rax]
0x18000c497  cmp     r8d, 5
0x18000c49b  jbe     short loc_18000C4F4
0x18000c49d  mov     rdx, 400000000000h
0x18000c4a7  mov     rcx, rax
0x18000c4aa  call    _tlgKeywordOn
0x18000c4af  test    al, al
0x18000c4b1  jz      short loc_18000C4F4
0x18000c4b3  mov     ecx, [rbx]
0x18000c4b5  lea     rax, [rsp+58h+arg_18]
0x18000c4ba  mov     [rsp+58h+var_28], rax
0x18000c4bf  lea     rdx, byte_18001BAF9
0x18000c4c6  lea     rax, [rsp+58h+arg_10]
0x18000c4cb  mov     [rsp+58h+arg_10], ecx
0x18000c4cf  mov     [rsp+58h+var_30], rax
0x18000c4d4  mov     rcx, r9
0x18000c4d7  lea     rax, [rsp+58h+var_18]
0x18000c4dc  mov     [rsp+58h+arg_18], 3000000h
0x18000c4e5  mov     [rsp+58h+var_38], rax
0x18000c4ea  mov     [rsp+58h+var_18], rdi
0x18000c4ef  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18000c4f4  mov     rbx, [rsp+58h+arg_0]
0x18000c4f9  add     rsp, 50h
0x18000c4fd  pop     rdi
0x18000c4fe  retn
```
