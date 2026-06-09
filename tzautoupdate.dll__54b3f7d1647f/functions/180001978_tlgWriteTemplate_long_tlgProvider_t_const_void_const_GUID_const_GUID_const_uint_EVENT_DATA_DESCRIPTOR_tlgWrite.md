# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001978`
- end: `0x1800019f0`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z`
- size: `120`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001126c`

## callees

- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
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
  v7[7] = 8;
  v7[5] = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 4, v7);
}

```

## disassembly

```asm
0x180001978  mov     r11, rsp
0x18000197b  sub     rsp, 88h
0x180001982  mov     rax, cs:__security_cookie
0x180001989  xor     rax, rsp
0x18000198c  mov     [rsp+88h+var_18], rax
0x180001991  mov     rax, [rsp+88h+arg_28]
0x180001999  lea     rcx, dword_180030000
0x1800019a0  mov     [r11-28h], rax
0x1800019a4  xor     r9d, r9d
0x1800019a7  mov     rax, [rsp+88h+arg_20]
0x1800019af  xor     r8d, r8d
0x1800019b2  mov     [r11-38h], rax
0x1800019b6  lea     rax, [r11-58h]
0x1800019ba  mov     [r11-60h], rax
0x1800019be  mov     [rsp+88h+var_68], 4
0x1800019c6  mov     qword ptr [r11-20h], 8
0x1800019ce  mov     qword ptr [r11-30h], 8
0x1800019d6  call    _tlgWriteTransfer_EventWriteTransfer
0x1800019db  mov     rcx, [rsp+88h+var_18]
0x1800019e0  xor     rcx, rsp; StackCookie
0x1800019e3  call    __security_check_cookie
0x1800019e8  add     rsp, 88h
0x1800019ef  retn
```
