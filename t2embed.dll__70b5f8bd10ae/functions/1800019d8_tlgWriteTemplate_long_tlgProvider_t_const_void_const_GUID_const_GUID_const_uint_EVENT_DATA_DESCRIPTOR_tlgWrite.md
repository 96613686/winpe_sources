# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800019d8`
- end: `0x180001a60`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `136`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c41c`
- `0x180026140`
- `0x180026380`
- `0x1800265c0`
- `0x180026800`

## callees

- `0x1800018c8`
- `0x18002a590`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-68h] BYREF
  __int64 v9; // [rsp+50h] [rbp-48h]
  __int64 v10; // [rsp+58h] [rbp-40h]
  __int64 v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  __int64 v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  v13 = a7;
  v11 = a6;
  v9 = a5;
  v14 = 4;
  v12 = 4;
  v10 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 5u, &v8);
}

```

## disassembly

```asm
0x1800019d8  mov     r11, rsp
0x1800019db  sub     rsp, 98h
0x1800019e2  mov     rax, cs:__security_cookie
0x1800019e9  xor     rax, rsp
0x1800019ec  mov     [rsp+98h+var_18], rax
0x1800019f4  mov     rax, [rsp+98h+arg_30]
0x1800019fc  xor     r9d, r9d
0x1800019ff  mov     [r11-28h], rax
0x180001a03  mov     rax, [rsp+98h+arg_28]
0x180001a0b  mov     [r11-38h], rax
0x180001a0f  mov     rax, [rsp+98h+arg_20]
0x180001a17  mov     [r11-48h], rax
0x180001a1b  lea     rax, [r11-68h]
0x180001a1f  mov     [r11-70h], rax
0x180001a23  mov     [rsp+98h+var_78], 5
0x180001a2b  mov     qword ptr [r11-20h], 4
0x180001a33  mov     qword ptr [r11-30h], 4
0x180001a3b  mov     qword ptr [r11-40h], 8
0x180001a43  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a48  mov     rcx, [rsp+98h+var_18]
0x180001a50  xor     rcx, rsp; StackCookie
0x180001a53  call    __security_check_cookie
0x180001a58  add     rsp, 98h
0x180001a5f  retn
```
