# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000121c`
- end: `0x18000128d`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f8c`
- `0x1800066a8`

## callees

- `0x180001010`
- `0x180002410`

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
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C038, a2, 0, 0, 4, v7);
}

```

## disassembly

```asm
0x18000121c  mov     r11, rsp
0x18000121f  sub     rsp, 88h
0x180001226  mov     rax, cs:__security_cookie
0x18000122d  xor     rax, rsp
0x180001230  mov     [rsp+88h+var_18], rax
0x180001235  mov     rax, [rsp+88h+arg_28]
0x18000123d  mov     ecx, 4
0x180001242  mov     [r11-28h], rax
0x180001246  xor     r9d, r9d
0x180001249  mov     rax, [rsp+88h+arg_20]
0x180001251  xor     r8d, r8d
0x180001254  mov     [r11-38h], rax
0x180001258  lea     rax, [r11-58h]
0x18000125c  mov     [r11-60h], rax
0x180001260  mov     [rsp+88h+var_68], ecx
0x180001264  mov     [r11-20h], rcx
0x180001268  mov     [r11-30h], rcx
0x18000126c  lea     rcx, dword_18001C038
0x180001273  call    _tlgWriteTransfer_EventWriteTransfer
0x180001278  mov     rcx, [rsp+88h+var_18]
0x18000127d  xor     rcx, rsp; StackCookie
0x180001280  call    __security_check_cookie
0x180001285  add     rsp, 88h
0x18000128c  retn
```
