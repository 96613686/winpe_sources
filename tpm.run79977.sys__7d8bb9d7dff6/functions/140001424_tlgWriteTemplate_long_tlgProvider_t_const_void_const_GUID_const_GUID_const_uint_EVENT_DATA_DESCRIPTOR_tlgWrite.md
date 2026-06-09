# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001424`
- end: `0x14000149a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14002cfa8`
- `0x14002d050`
- `0x14002df64`
- `0x14002e118`

## callees

- `0x1400010a4`
- `0x140039740`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-58h] BYREF
  __int64 v8; // [rsp+50h] [rbp-38h]
  __int64 v9; // [rsp+58h] [rbp-30h]
  __int64 v10; // [rsp+60h] [rbp-28h]
  __int64 v11; // [rsp+68h] [rbp-20h]

  v10 = a6;
  v8 = a5;
  v11 = 4;
  v9 = 8;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_1400470A0, a2, 0, 0, 4u, &v7);
}

```

## disassembly

```asm
0x140001424  mov     r11, rsp
0x140001427  sub     rsp, 88h
0x14000142e  mov     rax, cs:__security_cookie
0x140001435  xor     rax, rsp
0x140001438  mov     [rsp+88h+var_18], rax
0x14000143d  mov     rax, [rsp+88h+arg_28]
0x140001445  mov     ecx, 4
0x14000144a  mov     [r11-28h], rax
0x14000144e  xor     r9d, r9d
0x140001451  mov     rax, [rsp+88h+arg_20]
0x140001459  xor     r8d, r8d
0x14000145c  mov     [r11-38h], rax
0x140001460  lea     rax, [r11-58h]
0x140001464  mov     [r11-60h], rax
0x140001468  mov     [rsp+88h+var_68], ecx
0x14000146c  mov     [r11-20h], rcx
0x140001470  lea     rcx, dword_1400470A0
0x140001477  mov     qword ptr [r11-30h], 8
0x14000147f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001484  mov     rcx, [rsp+88h+var_18]
0x140001489  xor     rcx, rsp; StackCookie
0x14000148c  call    __security_check_cookie
0x140001491  add     rsp, 88h
0x140001498  retn
```
