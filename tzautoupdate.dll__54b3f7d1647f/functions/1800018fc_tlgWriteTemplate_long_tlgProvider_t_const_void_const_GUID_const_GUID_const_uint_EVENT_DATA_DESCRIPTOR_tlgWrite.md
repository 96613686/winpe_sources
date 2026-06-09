# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800018fc`
- end: `0x180001971`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f530`
- `0x180010784`
- `0x180010cac`
- `0x180011100`
- `0x18001126c`
- `0x1800117d0`
- `0x180011b60`
- `0x180011e5c`
- `0x180011ff0`
- `0x180012178`
- `0x180013e60`
- `0x180015bd0`
- `0x1800169f8`

## callees

- `0x18000169c`
- `0x18001b150`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
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
  v7[5] = 8;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180030000, a2, 0, 0, 4, v7);
}

```

## disassembly

```asm
0x1800018fc  mov     r11, rsp
0x1800018ff  sub     rsp, 88h
0x180001906  mov     rax, cs:__security_cookie
0x18000190d  xor     rax, rsp
0x180001910  mov     [rsp+88h+var_18], rax
0x180001915  mov     rax, [rsp+88h+arg_28]
0x18000191d  mov     ecx, 4
0x180001922  mov     [r11-28h], rax
0x180001926  xor     r9d, r9d
0x180001929  mov     rax, [rsp+88h+arg_20]
0x180001931  xor     r8d, r8d
0x180001934  mov     [r11-38h], rax
0x180001938  lea     rax, [r11-58h]
0x18000193c  mov     [r11-60h], rax
0x180001940  mov     [rsp+88h+var_68], ecx
0x180001944  mov     [r11-20h], rcx
0x180001948  lea     rcx, dword_180030000
0x18000194f  mov     qword ptr [r11-30h], 8
0x180001957  call    _tlgWriteTransfer_EventWriteTransfer
0x18000195c  mov     rcx, [rsp+88h+var_18]
0x180001961  xor     rcx, rsp; StackCookie
0x180001964  call    __security_check_cookie
0x180001969  add     rsp, 88h
0x180001970  retn
```
