# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x180001740`
- end: `0x18000179e`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800118a8`
- `0x180011af0`
- `0x180012d68`

## callees

- `0x180001260`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+50h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-20h]

  v7 = a5;
  v8 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 3u, &v6);
}

```

## disassembly

```asm
0x180001740  mov     r11, rsp
0x180001743  sub     rsp, 78h
0x180001747  mov     rax, cs:__security_cookie
0x18000174e  xor     rax, rsp
0x180001751  mov     [rsp+78h+var_18], rax
0x180001756  mov     rax, [rsp+78h+arg_20]
0x18000175e  lea     rcx, dword_180022000
0x180001765  mov     [r11-28h], rax
0x180001769  xor     r9d, r9d
0x18000176c  lea     rax, [r11-48h]
0x180001770  mov     qword ptr [r11-20h], 4
0x180001778  mov     [r11-50h], rax
0x18000177c  xor     r8d, r8d
0x18000177f  mov     [rsp+78h+var_58], 3
0x180001787  call    _tlgWriteTransfer_EventWriteTransfer
0x18000178c  mov     rcx, [rsp+78h+var_18]
0x180001791  xor     rcx, rsp; StackCookie
0x180001794  call    __security_check_cookie
0x180001799  add     rsp, 78h
0x18000179d  retn
```
