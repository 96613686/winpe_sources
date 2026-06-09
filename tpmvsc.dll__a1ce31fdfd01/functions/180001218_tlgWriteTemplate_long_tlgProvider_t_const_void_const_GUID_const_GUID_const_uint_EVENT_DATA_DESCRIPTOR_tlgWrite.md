# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001218`
- end: `0x18000127d`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800180a0`
- `0x180029938`
- `0x180033a88`
- `0x18003431c`

## callees

- `0x180001010`
- `0x180001ec0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  _QWORD v7[8]; // [rsp+30h] [rbp-58h] BYREF

  v7[6] = a6;
  v7[4] = a5;
  v7[7] = 4;
  v7[5] = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 4, v7);
}

```

## disassembly

```asm
0x180001218  mov     r11, rsp
0x18000121b  sub     rsp, 88h
0x180001222  mov     rax, cs:__security_cookie
0x180001229  xor     rax, rsp
0x18000122c  mov     [rsp+88h+var_18], rax
0x180001231  mov     rax, [rsp+88h+arg_28]
0x180001239  mov     r10d, 4
0x18000123f  mov     [r11-28h], rax
0x180001243  mov     rax, [rsp+88h+arg_20]
0x18000124b  mov     [r11-38h], rax
0x18000124f  lea     rax, [r11-58h]
0x180001253  mov     [r11-60h], rax
0x180001257  mov     [r11-68h], r10d
0x18000125b  mov     [r11-20h], r10
0x18000125f  mov     [r11-30h], r10
0x180001263  call    _tlgWriteTransfer_EventWriteTransfer
0x180001268  mov     rcx, [rsp+88h+var_18]
0x18000126d  xor     rcx, rsp; StackCookie
0x180001270  call    __security_check_cookie
0x180001275  add     rsp, 88h
0x18000127c  retn
```
