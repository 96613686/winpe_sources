# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001c1c`
- end: `0x180001ca7`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z`
- size: `139`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007134`
- `0x1800079c0`
- `0x180007f70`

## callees

- `0x180001010`
- `0x180002410`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD v8[10]; // [rsp+30h] [rbp-68h] BYREF

  v8[8] = a7;
  v8[6] = a6;
  v8[4] = a5;
  v8[9] = 4;
  v8[7] = 4;
  v8[5] = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5, v8);
}

```

## disassembly

```asm
0x180001c1c  mov     r11, rsp
0x180001c1f  sub     rsp, 98h
0x180001c26  mov     rax, cs:__security_cookie
0x180001c2d  xor     rax, rsp
0x180001c30  mov     [rsp+98h+var_18], rax
0x180001c38  mov     rax, [rsp+98h+arg_30]
0x180001c40  xor     r9d, r9d
0x180001c43  mov     [r11-28h], rax
0x180001c47  xor     r8d, r8d
0x180001c4a  mov     rax, [rsp+98h+arg_28]
0x180001c52  mov     [r11-38h], rax
0x180001c56  mov     rax, [rsp+98h+arg_20]
0x180001c5e  mov     [r11-48h], rax
0x180001c62  lea     rax, [r11-68h]
0x180001c66  mov     [r11-70h], rax
0x180001c6a  mov     [rsp+98h+var_78], 5
0x180001c72  mov     qword ptr [r11-20h], 4
0x180001c7a  mov     qword ptr [r11-30h], 4
0x180001c82  mov     qword ptr [r11-40h], 4
0x180001c8a  call    _tlgWriteTransfer_EventWriteTransfer
0x180001c8f  mov     rcx, [rsp+98h+var_18]
0x180001c97  xor     rcx, rsp; StackCookie
0x180001c9a  call    __security_check_cookie
0x180001c9f  add     rsp, 98h
0x180001ca6  retn
```
