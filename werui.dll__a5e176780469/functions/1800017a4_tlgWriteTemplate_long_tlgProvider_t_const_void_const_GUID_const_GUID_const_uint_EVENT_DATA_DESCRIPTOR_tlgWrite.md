# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800017a4`
- end: `0x180001815`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800118a8`

## callees

- `0x180001260`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
  v9 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 4u, &v7);
}

```

## disassembly

```asm
0x1800017a4  mov     r11, rsp
0x1800017a7  sub     rsp, 88h
0x1800017ae  mov     rax, cs:__security_cookie
0x1800017b5  xor     rax, rsp
0x1800017b8  mov     [rsp+88h+var_18], rax
0x1800017bd  mov     rax, [rsp+88h+arg_28]
0x1800017c5  mov     ecx, 4
0x1800017ca  mov     [r11-28h], rax
0x1800017ce  xor     r9d, r9d
0x1800017d1  mov     rax, [rsp+88h+arg_20]
0x1800017d9  xor     r8d, r8d
0x1800017dc  mov     [r11-38h], rax
0x1800017e0  lea     rax, [r11-58h]
0x1800017e4  mov     [r11-60h], rax
0x1800017e8  mov     [rsp+88h+var_68], ecx
0x1800017ec  mov     [r11-20h], rcx
0x1800017f0  mov     [r11-30h], rcx
0x1800017f4  lea     rcx, dword_180022000
0x1800017fb  call    _tlgWriteTransfer_EventWriteTransfer
0x180001800  mov     rcx, [rsp+88h+var_18]
0x180001805  xor     rcx, rsp; StackCookie
0x180001808  call    __security_check_cookie
0x18000180d  add     rsp, 88h
0x180001814  retn
```
