# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)

- ea: `0x140001328`
- end: `0x1400013e0`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@4444@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001171c`

## callees

- `0x140001420`
- `0x140005050`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-69h] BYREF
  __int64 v12; // [rsp+50h] [rbp-49h]
  __int64 v13; // [rsp+58h] [rbp-41h]
  __int64 v14; // [rsp+60h] [rbp-39h]
  __int64 v15; // [rsp+68h] [rbp-31h]
  __int64 v16; // [rsp+70h] [rbp-29h]
  __int64 v17; // [rsp+78h] [rbp-21h]
  __int64 v18; // [rsp+80h] [rbp-19h]
  __int64 v19; // [rsp+88h] [rbp-11h]
  __int64 v20; // [rsp+90h] [rbp-9h]
  __int64 v21; // [rsp+98h] [rbp-1h]
  __int64 v22; // [rsp+A0h] [rbp+7h]
  __int64 v23; // [rsp+A8h] [rbp+Fh]

  v22 = a10;
  v20 = a9;
  v18 = a8;
  v16 = a7;
  v14 = a6;
  v23 = 1;
  v21 = 1;
  v19 = 1;
  v12 = *a5;
  v17 = 1;
  v15 = 1;
  v13 = 16;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14000A048, a2, 0, 0, 8u, &v11);
}

```

## disassembly

```asm
0x140001328  push    rbp
0x14000132a  lea     rbp, [rsp-27h]
0x14000132f  sub     rsp, 0C0h
0x140001336  mov     rax, cs:__security_cookie
0x14000133d  xor     rax, rsp
0x140001340  mov     [rbp+27h+var_10], rax
0x140001344  mov     rax, [rbp+27h+arg_48]
0x140001348  xor     r9d, r9d
0x14000134b  mov     [rbp+27h+var_20], rax
0x14000134f  xor     r8d, r8d
0x140001352  mov     rax, [rbp+27h+arg_40]
0x140001356  mov     [rbp+27h+var_30], rax
0x14000135a  mov     rax, [rbp+27h+arg_38]
0x14000135e  mov     [rbp+27h+var_40], rax
0x140001362  mov     rax, [rbp+27h+arg_30]
0x140001366  mov     [rbp+27h+var_50], rax
0x14000136a  mov     rax, [rbp+27h+arg_28]
0x14000136e  mov     [rbp+27h+var_60], rax
0x140001372  mov     rax, [rbp+27h+arg_20]
0x140001376  mov     [rbp+27h+var_18], 1
0x14000137e  mov     [rbp+27h+var_28], 1
0x140001386  mov     [rbp+27h+var_38], 1
0x14000138e  mov     rcx, [rax]
0x140001391  lea     rax, [rbp+27h+var_90]
0x140001395  mov     [rbp+27h+var_70], rcx
0x140001399  lea     rcx, dword_14000A048
0x1400013a0  mov     [rsp+0C0h+var_98], rax
0x1400013a5  mov     [rsp+0C0h+var_A0], 8
0x1400013ad  mov     [rbp+27h+var_48], 1
0x1400013b5  mov     [rbp+27h+var_58], 1
0x1400013bd  mov     [rbp+27h+var_68], 10h
0x1400013c5  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400013ca  mov     rcx, [rbp+27h+var_10]
0x1400013ce  xor     rcx, rsp; StackCookie
0x1400013d1  call    __security_check_cookie
0x1400013d6  add     rsp, 0C0h
0x1400013dd  pop     rbp
0x1400013de  retn
```
