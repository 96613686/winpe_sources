# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800013b4`
- end: `0x180001472`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e270`

## callees

- `0x180001ba8`
- `0x18000fa00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x1800013b4  push    rbp
0x1800013b6  lea     rbp, [rsp-1Fh]
0x1800013bb  sub     rsp, 0D0h
0x1800013c2  mov     rax, cs:__security_cookie
0x1800013c9  xor     rax, rsp
0x1800013cc  mov     [rbp+1Fh+var_10], rax
0x1800013d0  mov     rax, [rbp+1Fh+arg_50]
0x1800013d4  xor     r9d, r9d
0x1800013d7  mov     [rbp+1Fh+var_20], rax
0x1800013db  xor     r8d, r8d
0x1800013de  mov     rax, [rbp+1Fh+arg_48]
0x1800013e2  mov     [rbp+1Fh+var_30], rax
0x1800013e6  mov     rax, [rbp+1Fh+arg_40]
0x1800013ea  mov     [rbp+1Fh+var_40], rax
0x1800013ee  mov     rax, [rbp+1Fh+arg_38]
0x1800013f2  mov     [rbp+1Fh+var_50], rax
0x1800013f6  mov     rax, [rbp+1Fh+arg_30]
0x1800013fa  mov     [rbp+1Fh+var_60], rax
0x1800013fe  mov     rax, [rbp+1Fh+arg_28]
0x180001402  mov     [rbp+1Fh+var_70], rax
0x180001406  mov     rax, [rbp+1Fh+arg_20]
0x18000140a  mov     [rbp+1Fh+var_80], rax
0x18000140e  lea     rax, [rsp+0D0h+var_A0]
0x180001413  mov     [rsp+0D0h+var_A8], rax
0x180001418  mov     [rsp+0D0h+var_B0], 9
0x180001420  mov     [rbp+1Fh+var_18], 8
0x180001428  mov     [rbp+1Fh+var_28], 4
0x180001430  mov     [rbp+1Fh+var_38], 1
0x180001438  mov     [rbp+1Fh+var_48], 2
0x180001440  mov     [rbp+1Fh+var_58], 4
0x180001448  mov     [rbp+1Fh+var_68], 4
0x180001450  mov     [rbp+1Fh+var_78], 4
0x180001458  call    _tlgWriteTransfer_EventWriteTransfer
0x18000145d  mov     rcx, [rbp+1Fh+var_10]
0x180001461  xor     rcx, rsp; StackCookie
0x180001464  call    __security_check_cookie
0x180001469  add     rsp, 0D0h
0x180001470  pop     rbp
0x180001471  retn
```
