# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800016d0`
- end: `0x180001767`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$00@@3@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d1cc`
- `0x18001ec10`

## callees

- `0x180001010`
- `0x180001ec0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  _BYTE v10[32]; // [rsp+30h] [rbp-51h] BYREF
  __int64 v11; // [rsp+50h] [rbp-31h]
  __int64 v12; // [rsp+58h] [rbp-29h]
  __int64 v13; // [rsp+60h] [rbp-21h]
  __int64 v14; // [rsp+68h] [rbp-19h]
  __int64 v15; // [rsp+70h] [rbp-11h]
  __int64 v16; // [rsp+78h] [rbp-9h]
  __int64 v17; // [rsp+80h] [rbp-1h]
  __int64 v18; // [rsp+88h] [rbp+7h]
  __int64 v19; // [rsp+90h] [rbp+Fh]
  __int64 v20; // [rsp+98h] [rbp+17h]

  v19 = a9;
  v17 = a8;
  v15 = a7;
  v13 = a6;
  v11 = a5;
  v20 = 4;
  v18 = 1;
  v16 = 4;
  v14 = 4;
  v12 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 7, v10);
}

```

## disassembly

```asm
0x1800016d0  push    rbp
0x1800016d2  lea     rbp, [rsp-2Fh]
0x1800016d7  sub     rsp, 0B0h
0x1800016de  mov     rax, cs:__security_cookie
0x1800016e5  xor     rax, rsp
0x1800016e8  mov     [rbp+2Fh+var_10], rax
0x1800016ec  mov     rax, [rbp+2Fh+arg_40]
0x1800016f0  mov     [rbp+2Fh+var_20], rax
0x1800016f4  mov     rax, [rbp+2Fh+arg_38]
0x1800016f8  mov     [rbp+2Fh+var_30], rax
0x1800016fc  mov     rax, [rbp+2Fh+arg_30]
0x180001700  mov     [rbp+2Fh+var_40], rax
0x180001704  mov     rax, [rbp+2Fh+arg_28]
0x180001708  mov     [rbp+2Fh+var_50], rax
0x18000170c  mov     rax, [rbp+2Fh+arg_20]
0x180001710  mov     [rbp+2Fh+var_60], rax
0x180001714  lea     rax, [rbp+2Fh+var_80]
0x180001718  mov     [rsp+0B0h+var_88], rax
0x18000171d  mov     [rsp+0B0h+var_90], 7
0x180001725  mov     [rbp+2Fh+var_18], 4
0x18000172d  mov     [rbp+2Fh+var_28], 1
0x180001735  mov     [rbp+2Fh+var_38], 4
0x18000173d  mov     [rbp+2Fh+var_48], 4
0x180001745  mov     [rbp+2Fh+var_58], 4
0x18000174d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001752  mov     rcx, [rbp+2Fh+var_10]
0x180001756  xor     rcx, rsp; StackCookie
0x180001759  call    __security_check_cookie
0x18000175e  add     rsp, 0B0h
0x180001765  pop     rbp
0x180001766  retn
```
