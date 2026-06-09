# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x180001990`
- end: `0x1800019e7`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005784`
- `0x1800074fc`
- `0x1800075e4`
- `0x180007754`
- `0x1800078e0`

## callees

- `0x180001010`
- `0x180002410`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD v6[6]; // [rsp+30h] [rbp-48h] BYREF

  v6[4] = a5;
  v6[5] = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 3, v6);
}

```

## disassembly

```asm
0x180001990  mov     r11, rsp
0x180001993  sub     rsp, 78h
0x180001997  mov     rax, cs:__security_cookie
0x18000199e  xor     rax, rsp
0x1800019a1  mov     [rsp+78h+var_18], rax
0x1800019a6  mov     rax, [rsp+78h+arg_20]
0x1800019ae  xor     r9d, r9d
0x1800019b1  mov     [r11-28h], rax
0x1800019b5  xor     r8d, r8d
0x1800019b8  lea     rax, [r11-48h]
0x1800019bc  mov     qword ptr [r11-20h], 4
0x1800019c4  mov     [r11-50h], rax
0x1800019c8  mov     [rsp+78h+var_58], 3
0x1800019d0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800019d5  mov     rcx, [rsp+78h+var_18]
0x1800019da  xor     rcx, rsp; StackCookie
0x1800019dd  call    __security_check_cookie
0x1800019e2  add     rsp, 78h
0x1800019e6  retn
```
