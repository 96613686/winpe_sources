# WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfUnsubscribe(void)

- ea: `0x180012c18`
- end: `0x180012ca0`
- name: `?WnfUnsubscribe@?$WnfNoStateSubscription@$1?WNF_SHEL_LOGON_COMPLETE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010acc`
- `0x180010b54`

## callees

- `0x18000144c`
- `0x18000166c`
- `0x180012c18`

## import_xrefs

- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180012c58`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180012c58`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012c27`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012c27`

## pseudocode

```c
void __fastcall WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfUnsubscribe(
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
        v3 = (const unsigned __int16 *)type_info::name((type_info *)&WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)> `RTTI Type Descriptor');
        v7 = v1;
        v8 = v3;
        v9 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v4,
          (__int64)&dword_1800293F4,
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
0x180012c18  push    rbx
0x180012c1a  sub     rsp, 40h
0x180012c1e  mov     rcx, [rcx+8]
0x180012c22  test    rcx, rcx
0x180012c25  jz      short loc_180012C9A
0x180012c27  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180012c2d  mov     ebx, eax
0x180012c2f  test    eax, eax
0x180012c31  jns     short loc_180012C9A
0x180012c33  mov     ecx, cs:dword_180030000
0x180012c39  cmp     ecx, 5
0x180012c3c  jbe     short loc_180012C9A
0x180012c3e  mov     rdx, 200000000000h
0x180012c48  call    _tlgKeywordOn
0x180012c4d  test    al, al
0x180012c4f  jz      short loc_180012C9A
0x180012c51  lea     rcx, ??_R0?AV?$WnfNoStateSubscription@$1?WNF_SHEL_LOGON_COMPLETE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@@8; WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)> `RTTI Type Descriptor'
0x180012c58  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x180012c5e  lea     rdx, dword_1800293F4
0x180012c65  mov     [rsp+48h+arg_0], ebx
0x180012c69  mov     [rsp+48h+arg_8], rax
0x180012c6e  lea     rax, [rsp+48h+arg_8]
0x180012c73  mov     [rsp+48h+var_18], rax
0x180012c78  lea     rax, [rsp+48h+arg_0]
0x180012c7d  mov     [rsp+48h+var_20], rax
0x180012c82  lea     rax, [rsp+48h+arg_10]
0x180012c87  mov     [rsp+48h+var_28], rax
0x180012c8c  mov     [rsp+48h+arg_10], 1000000h
0x180012c95  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180012c9a  add     rsp, 40h
0x180012c9e  pop     rbx
0x180012c9f  retn
```
