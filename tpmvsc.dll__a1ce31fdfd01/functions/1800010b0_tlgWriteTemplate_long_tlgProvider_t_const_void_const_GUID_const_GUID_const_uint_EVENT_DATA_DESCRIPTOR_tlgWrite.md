# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x1800010b0`
- end: `0x1800010ef`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `63`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006494`
- `0x18001cabc`

## callees

- `0x180001010`
- `0x180001ec0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _BYTE v4[32]; // [rsp+30h] [rbp-38h] BYREF

  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 2, v4);
}

```

## disassembly

```asm
0x1800010b0  sub     rsp, 68h
0x1800010b4  mov     rax, cs:__security_cookie
0x1800010bb  xor     rax, rsp
0x1800010be  mov     [rsp+68h+var_18], rax
0x1800010c3  lea     rax, [rsp+68h+var_38]
0x1800010c8  xor     r9d, r9d
0x1800010cb  mov     [rsp+68h+var_40], rax
0x1800010d0  mov     [rsp+68h+var_48], 2
0x1800010d8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010dd  mov     rcx, [rsp+68h+var_18]
0x1800010e2  xor     rcx, rsp; StackCookie
0x1800010e5  call    __security_check_cookie
0x1800010ea  add     rsp, 68h
0x1800010ee  retn
```
