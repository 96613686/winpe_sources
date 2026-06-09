# _WnfNoStateSubscription_&WNF_SHEL_LOGON_COMPLETE_LocationDataSource_&LocationDataSource::WnfNoStateSubscriptionCallback_::WnfCallback_::_1_::catch$0

- ea: `0x18001c244`
- end: `0x18001c29e`
- name: `_WnfNoStateSubscription_&WNF_SHEL_LOGON_COMPLETE_LocationDataSource_&LocationDataSource::WnfNoStateSubscriptionCallback_::WnfCallback_::_1_::catch$0`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800010bc`
- `0x18000166c`
- `0x18001c244`

## pseudocode

```c
__int64 __fastcall WnfNoStateSubscription__WNF_SHEL_LOGON_COMPLETE_LocationDataSource__LocationDataSource::WnfNoStateSubscriptionCallback_::WnfCallback_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9

  if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(a1, 0x200000000000LL, a3) )
  {
    *(_QWORD *)(a2 + 88) = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v4,
      (__int64)byte_180028D1D,
      v5,
      v6,
      a2 + 88);
  }
  return 0;
}

```

## disassembly

```asm
0x18001c244  mov     [rsp+arg_8], rdx
0x18001c249  push    rbp
0x18001c24a  sub     rsp, 30h
0x18001c24e  mov     rbp, rdx
0x18001c251  mov     eax, cs:dword_180030000
0x18001c257  cmp     eax, 5
0x18001c25a  jbe     short loc_18001C28D
0x18001c25c  mov     rdx, 200000000000h
0x18001c266  call    _tlgKeywordOn
0x18001c26b  test    al, al
0x18001c26d  jz      short loc_18001C28D
0x18001c26f  mov     qword ptr [rbp+58h], 1000000h
0x18001c277  lea     rax, [rbp+58h]
0x18001c27b  mov     [rsp+38h+var_18], rax
0x18001c280  lea     rdx, byte_180028D1D
0x18001c287  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18001c28c  nop
0x18001c28d  mov     rax, 0
0x18001c297  add     rsp, 30h
0x18001c29b  pop     rbp
0x18001c29c  retn
```
