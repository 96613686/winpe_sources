# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x1800010f8`
- end: `0x180001156`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180006dc0`
- `0x180008d28`
- `0x180033b54`
- `0x180033d04`
- `0x180033ee8`
- `0x180033f70`
- `0x180033fe0`
- `0x180034154`
- `0x1800341ec`
- `0x18003431c`
- `0x180034798`

## callees

- `0x180001010`
- `0x180001ec0`

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
  return tlgWriteTransfer_EventWriteTransfer(&dword_180048098, a2, 0, 0, 3, v6);
}

```

## disassembly

```asm
0x1800010f8  mov     r11, rsp
0x1800010fb  sub     rsp, 78h
0x1800010ff  mov     rax, cs:__security_cookie
0x180001106  xor     rax, rsp
0x180001109  mov     [rsp+78h+var_18], rax
0x18000110e  mov     rax, [rsp+78h+arg_20]
0x180001116  lea     rcx, dword_180048098
0x18000111d  mov     [r11-28h], rax
0x180001121  xor     r9d, r9d
0x180001124  lea     rax, [r11-48h]
0x180001128  mov     qword ptr [r11-20h], 4
0x180001130  mov     [r11-50h], rax
0x180001134  xor     r8d, r8d
0x180001137  mov     [rsp+78h+var_58], 3
0x18000113f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001144  mov     rcx, [rsp+78h+var_18]
0x180001149  xor     rcx, rsp; StackCookie
0x18000114c  call    __security_check_cookie
0x180001151  add     rsp, 78h
0x180001155  retn
```
