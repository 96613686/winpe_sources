# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)

- ea: `0x180001300`
- end: `0x180001349`
- name: `??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001275c`
- `0x180012d68`

## callees

- `0x180001260`
- `0x180016c50`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        __int64 a1,
        unsigned __int8 *a2)
{
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+30h] [rbp-38h] BYREF

  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180022000, a2, 0, 0, 2u, &v3);
}

```

## disassembly

```asm
0x180001300  sub     rsp, 68h
0x180001304  mov     rax, cs:__security_cookie
0x18000130b  xor     rax, rsp
0x18000130e  mov     [rsp+68h+var_18], rax
0x180001313  lea     rax, [rsp+68h+var_38]
0x180001318  xor     r9d, r9d
0x18000131b  mov     [rsp+68h+var_40], rax
0x180001320  lea     rcx, dword_180022000
0x180001327  xor     r8d, r8d
0x18000132a  mov     [rsp+68h+var_48], 2
0x180001332  call    _tlgWriteTransfer_EventWriteTransfer
0x180001337  mov     rcx, [rsp+68h+var_18]
0x18000133c  xor     rcx, rsp; StackCookie
0x18000133f  call    __security_check_cookie
0x180001344  add     rsp, 68h
0x180001348  retn
```
