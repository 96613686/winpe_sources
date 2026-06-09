# WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_LFS_SIGNIFICANT_LOCATION_EVENT,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfUnsubscribe(void)

- ea: `0x180012af8`
- end: `0x180012b80`
- name: `?WnfUnsubscribe@?$WnfNoStateSubscription@$1?WNF_LFS_SIGNIFICANT_LOCATION_EVENT@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010a9c`
- `0x180010b54`

## callees

- `0x18000144c`
- `0x18000166c`
- `0x180012af8`

## import_xrefs

- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180012b38`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180012b38`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012b07`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012b07`

## pseudocode

```c
void __fastcall WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_LFS_SIGNIFICANT_LOCATION_EVENT,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfUnsubscribe(
        __int64 a1)
{
  int v1; // ebx
  __int64 v2; // r8
  const unsigned __int16 *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *v8; // [rsp+58h] [rbp+10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  if ( *(_QWORD *)(a1 + 8) )
  {
    v1 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    if ( v1 < 0 && (unsigned int)dword_180030000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, v2) )
      {
        v3 = (const unsigned __int16 *)type_info::name((type_info *)&WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_LFS_SIGNIFICANT_LOCATION_EVENT,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)> `RTTI Type Descriptor');
        v7 = v1;
        v8 = v3;
        v9 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v4,
          (__int64)&byte_180028ECF,
          v5,
          v6,
          (__int64)&v9,
          (__int64)&v7,
          &v8);
      }
    }
  }
}

```

## disassembly

```asm
0x180012af8  push    rbx
0x180012afa  sub     rsp, 40h
0x180012afe  mov     rcx, [rcx+8]
0x180012b02  test    rcx, rcx
0x180012b05  jz      short loc_180012B7A
0x180012b07  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180012b0d  mov     ebx, eax
0x180012b0f  test    eax, eax
0x180012b11  jns     short loc_180012B7A
0x180012b13  mov     ecx, cs:dword_180030000
0x180012b19  cmp     ecx, 5
0x180012b1c  jbe     short loc_180012B7A
0x180012b1e  mov     rdx, 200000000000h
0x180012b28  call    _tlgKeywordOn
0x180012b2d  test    al, al
0x180012b2f  jz      short loc_180012B7A
0x180012b31  lea     rcx, ??_R0?AV?$WnfNoStateSubscription@$1?WNF_LFS_SIGNIFICANT_LOCATION_EVENT@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@@8; WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_LFS_SIGNIFICANT_LOCATION_EVENT,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)> `RTTI Type Descriptor'
0x180012b38  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x180012b3e  lea     rdx, byte_180028ECF
0x180012b45  mov     [rsp+48h+arg_0], ebx
0x180012b49  mov     [rsp+48h+arg_8], rax
0x180012b4e  lea     rax, [rsp+48h+arg_8]
0x180012b53  mov     [rsp+48h+var_18], rax
0x180012b58  lea     rax, [rsp+48h+arg_0]
0x180012b5d  mov     [rsp+48h+var_20], rax
0x180012b62  lea     rax, [rsp+48h+arg_10]
0x180012b67  mov     [rsp+48h+var_28], rax
0x180012b6c  mov     [rsp+48h+arg_10], 1000000h
0x180012b75  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180012b7a  add     rsp, 40h
0x180012b7e  pop     rbx
0x180012b7f  retn
```
