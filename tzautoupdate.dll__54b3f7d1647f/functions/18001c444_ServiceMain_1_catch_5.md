# _ServiceMain_::_1_::catch$5

- ea: `0x18001c444`
- end: `0x18001c49e`
- name: `_ServiceMain_::_1_::catch$5`
- size: `90`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800010bc`
- `0x18000166c`
- `0x18001c444`

## pseudocode

```c
__int64 __fastcall ServiceMain_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9

  if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(a1, 0x200000000000LL, a3) )
  {
    *(_QWORD *)(a2 + 64) = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v4,
      (__int64)&byte_180029A47,
      v5,
      v6,
      a2 + 64);
  }
  return 0;
}

```

## disassembly

```asm
0x18001c444  mov     [rsp+arg_8], rdx
0x18001c449  push    rbp
0x18001c44a  sub     rsp, 40h
0x18001c44e  mov     rbp, rdx
0x18001c451  mov     eax, cs:dword_180030000
0x18001c457  cmp     eax, 5
0x18001c45a  jbe     short loc_18001C48D
0x18001c45c  mov     rdx, 200000000000h
0x18001c466  call    _tlgKeywordOn
0x18001c46b  test    al, al
0x18001c46d  jz      short loc_18001C48D
0x18001c46f  mov     qword ptr [rbp+40h], 1000000h
0x18001c477  lea     rax, [rbp+40h]
0x18001c47b  mov     [rsp+48h+var_28], rax
0x18001c480  lea     rdx, byte_180029A47
0x18001c487  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18001c48c  nop
0x18001c48d  mov     rax, 0
0x18001c497  add     rsp, 40h
0x18001c49b  pop     rbp
0x18001c49c  retn
```
