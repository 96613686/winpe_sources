# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)

- ea: `0x180001c98`
- end: `0x180001d2a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@4@Z`
- size: `146`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014ec0`

## callees

- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD v8[10]; // [rsp+30h] [rbp-68h] BYREF

  v8[8] = a7;
  v8[6] = a6;
  v8[4] = a5;
  v8[9] = 1;
  v8[7] = 1;
  v8[5] = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 5, v8);
}

```

## disassembly

```asm
0x180001c98  mov     r11, rsp
0x180001c9b  sub     rsp, 98h
0x180001ca2  mov     rax, cs:__security_cookie
0x180001ca9  xor     rax, rsp
0x180001cac  mov     [rsp+98h+var_18], rax
0x180001cb4  mov     rax, [rsp+98h+arg_30]
0x180001cbc  lea     rcx, dword_180030000
0x180001cc3  mov     [r11-28h], rax
0x180001cc7  xor     r9d, r9d
0x180001cca  mov     rax, [rsp+98h+arg_28]
0x180001cd2  xor     r8d, r8d
0x180001cd5  mov     [r11-38h], rax
0x180001cd9  mov     rax, [rsp+98h+arg_20]
0x180001ce1  mov     [r11-48h], rax
0x180001ce5  lea     rax, [r11-68h]
0x180001ce9  mov     [r11-70h], rax
0x180001ced  mov     [rsp+98h+var_78], 5
0x180001cf5  mov     qword ptr [r11-20h], 1
0x180001cfd  mov     qword ptr [r11-30h], 1
0x180001d05  mov     qword ptr [r11-40h], 8
0x180001d0d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001d12  mov     rcx, [rsp+98h+var_18]
0x180001d1a  xor     rcx, rsp; StackCookie
0x180001d1d  call    __security_check_cookie
0x180001d22  add     rsp, 98h
0x180001d29  retn
```
