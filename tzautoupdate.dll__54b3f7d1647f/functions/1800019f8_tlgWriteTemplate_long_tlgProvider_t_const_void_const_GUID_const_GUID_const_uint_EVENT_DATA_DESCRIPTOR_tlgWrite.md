# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800019f8`
- end: `0x180001aa9`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4444@Z`
- size: `177`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
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
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  _BYTE v11[32]; // [rsp+30h] [rbp-69h] BYREF
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
  v12 = a5;
  v13 = 8;
  v23 = 4;
  v21 = 4;
  v19 = 4;
  v17 = 4;
  v15 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 8, v11);
}

```

## disassembly

```asm
0x1800019f8  push    rbp
0x1800019fa  lea     rbp, [rsp-27h]
0x1800019ff  sub     rsp, 0C0h
0x180001a06  mov     rax, cs:__security_cookie
0x180001a0d  xor     rax, rsp
0x180001a10  mov     [rbp+27h+var_10], rax
0x180001a14  mov     rax, [rbp+27h+arg_48]
0x180001a18  mov     ecx, 8
0x180001a1d  mov     [rbp+27h+var_20], rax
0x180001a21  xor     r9d, r9d
0x180001a24  mov     rax, [rbp+27h+arg_40]
0x180001a28  xor     r8d, r8d
0x180001a2b  mov     [rbp+27h+var_30], rax
0x180001a2f  mov     rax, [rbp+27h+arg_38]
0x180001a33  mov     [rbp+27h+var_40], rax
0x180001a37  mov     rax, [rbp+27h+arg_30]
0x180001a3b  mov     [rbp+27h+var_50], rax
0x180001a3f  mov     rax, [rbp+27h+arg_28]
0x180001a43  mov     [rbp+27h+var_60], rax
0x180001a47  mov     rax, [rbp+27h+arg_20]
0x180001a4b  mov     [rbp+27h+var_70], rax
0x180001a4f  lea     rax, [rbp+27h+var_90]
0x180001a53  mov     [rsp+0C0h+var_98], rax
0x180001a58  mov     [rsp+0C0h+var_A0], ecx
0x180001a5c  mov     [rbp+27h+var_68], rcx
0x180001a60  lea     rcx, dword_180030000
0x180001a67  mov     [rbp+27h+var_18], 4
0x180001a6f  mov     [rbp+27h+var_28], 4
0x180001a77  mov     [rbp+27h+var_38], 4
0x180001a7f  mov     [rbp+27h+var_48], 4
0x180001a87  mov     [rbp+27h+var_58], 4
0x180001a8f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a94  mov     rcx, [rbp+27h+var_10]
0x180001a98  xor     rcx, rsp; StackCookie
0x180001a9b  call    __security_check_cookie
0x180001aa0  add     rsp, 0C0h
0x180001aa7  pop     rbp
0x180001aa8  retn
```
