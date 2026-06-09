# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000115c`
- end: `0x1800011e3`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006bc8`
- `0x180006fb8`
- `0x180008d28`
- `0x18000a46c`

## callees

- `0x180001010`
- `0x180001ec0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  _BYTE v9[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v10; // [rsp+50h] [rbp-19h]
  __int64 v11; // [rsp+58h] [rbp-11h]
  __int64 v12; // [rsp+60h] [rbp-9h]
  __int64 v13; // [rsp+68h] [rbp-1h]
  __int64 v14; // [rsp+70h] [rbp+7h]
  __int64 v15; // [rsp+78h] [rbp+Fh]
  __int64 v16; // [rsp+80h] [rbp+17h]
  __int64 v17; // [rsp+88h] [rbp+1Fh]

  v16 = a8;
  v14 = a7;
  v12 = a6;
  v10 = a5;
  v17 = 4;
  v15 = 4;
  v13 = 4;
  v11 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 6, v9);
}

```

## disassembly

```asm
0x18000115c  push    rbp
0x18000115e  lea     rbp, [rsp-37h]
0x180001163  sub     rsp, 0A0h
0x18000116a  mov     rax, cs:__security_cookie
0x180001171  xor     rax, rsp
0x180001174  mov     [rbp+37h+var_10], rax
0x180001178  mov     rax, [rbp+37h+arg_38]
0x18000117c  mov     [rbp+37h+var_20], rax
0x180001180  mov     rax, [rbp+37h+arg_30]
0x180001184  mov     [rbp+37h+var_30], rax
0x180001188  mov     rax, [rbp+37h+arg_28]
0x18000118c  mov     [rbp+37h+var_40], rax
0x180001190  mov     rax, [rbp+37h+arg_20]
0x180001194  mov     [rbp+37h+var_50], rax
0x180001198  lea     rax, [rbp+37h+var_70]
0x18000119c  mov     [rsp+0A0h+var_78], rax
0x1800011a1  mov     [rsp+0A0h+var_80], 6
0x1800011a9  mov     [rbp+37h+var_18], 4
0x1800011b1  mov     [rbp+37h+var_28], 4
0x1800011b9  mov     [rbp+37h+var_38], 4
0x1800011c1  mov     [rbp+37h+var_48], 4
0x1800011c9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800011ce  mov     rcx, [rbp+37h+var_10]
0x1800011d2  xor     rcx, rsp; StackCookie
0x1800011d5  call    __security_check_cookie
0x1800011da  add     rsp, 0A0h
0x1800011e1  pop     rbp
0x1800011e2  retn
```
