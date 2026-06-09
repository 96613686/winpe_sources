# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800012e0`
- end: `0x1800013ae`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$00@@U1@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$00@@35AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `206`
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
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x1800012e0  push    rbp
0x1800012e2  lea     rbp, [rsp-17h]
0x1800012e7  sub     rsp, 0E0h
0x1800012ee  mov     rax, cs:__security_cookie
0x1800012f5  xor     rax, rsp
0x1800012f8  mov     [rbp+17h+var_10], rax
0x1800012fc  mov     rax, [rbp+17h+arg_58]
0x180001300  xor     r9d, r9d
0x180001303  mov     [rbp+17h+var_20], rax
0x180001307  xor     r8d, r8d
0x18000130a  mov     rax, [rbp+17h+arg_50]
0x18000130e  mov     [rbp+17h+var_30], rax
0x180001312  mov     rax, [rbp+17h+arg_48]
0x180001316  mov     [rbp+17h+var_40], rax
0x18000131a  mov     rax, [rbp+17h+arg_40]
0x18000131e  mov     [rbp+17h+var_50], rax
0x180001322  mov     rax, [rbp+17h+arg_38]
0x180001326  mov     [rbp+17h+var_60], rax
0x18000132a  mov     rax, [rbp+17h+arg_30]
0x18000132e  mov     [rbp+17h+var_70], rax
0x180001332  mov     rax, [rbp+17h+arg_28]
0x180001336  mov     [rbp+17h+var_80], rax
0x18000133a  mov     rax, [rbp+17h+arg_20]
0x18000133e  mov     [rbp+17h+var_90], rax
0x180001342  lea     rax, [rsp+0E0h+var_B0]
0x180001347  mov     [rsp+0E0h+var_B8], rax
0x18000134c  mov     [rsp+0E0h+var_C0], 0Ah
0x180001354  mov     [rbp+17h+var_18], 8
0x18000135c  mov     [rbp+17h+var_28], 1
0x180001364  mov     [rbp+17h+var_38], 4
0x18000136c  mov     [rbp+17h+var_48], 1
0x180001374  mov     [rbp+17h+var_58], 2
0x18000137c  mov     [rbp+17h+var_68], 4
0x180001384  mov     [rbp+17h+var_78], 4
0x18000138c  mov     [rbp+17h+var_88], 4
0x180001394  call    _tlgWriteTransfer_EventWriteTransfer
0x180001399  mov     rcx, [rbp+17h+var_10]
0x18000139d  xor     rcx, rsp; StackCookie
0x1800013a0  call    __security_check_cookie
0x1800013a5  add     rsp, 0E0h
0x1800013ac  pop     rbp
0x1800013ad  retn
```
