# WnfSubscription<ulong,&_WNF_STATE_NAME const WNF_SHEL_LOCKSCREEN_ACTIVE,LocationDataSource,&LocationDataSource::WnfLockScreenActiveCallback(ulong const &)>::WnfUnsubscribe(void)

- ea: `0x180012ca8`
- end: `0x180012d30`
- name: `?WnfUnsubscribe@?$WnfSubscription@K$1?WNF_SHEL_LOCKSCREEN_ACTIVE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfLockScreenActiveCallback@3@AEAAXAEBK@Z@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010ae4`
- `0x180010b54`

## callees

- `0x18000144c`
- `0x18000166c`
- `0x180012ca8`

## import_xrefs

- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180012ce8`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180012ce8`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012cb7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180012cb7`

## pseudocode

```c
void __fastcall WnfSubscription<unsigned long,&_WNF_STATE_NAME const WNF_SHEL_LOCKSCREEN_ACTIVE,LocationDataSource,&private: void LocationDataSource::WnfLockScreenActiveCallback(unsigned long const &)>::WnfUnsubscribe(
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
        v3 = (const unsigned __int16 *)type_info::name((type_info *)&WnfSubscription<unsigned long,&_WNF_STATE_NAME const WNF_SHEL_LOCKSCREEN_ACTIVE,LocationDataSource,&private: void LocationDataSource::WnfLockScreenActiveCallback(unsigned long const &)> `RTTI Type Descriptor');
        v7 = v1;
        v8 = v3;
        v9 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v4,
          (__int64)word_180028F1A,
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
0x180012ca8  push    rbx
0x180012caa  sub     rsp, 40h
0x180012cae  mov     rcx, [rcx+8]
0x180012cb2  test    rcx, rcx
0x180012cb5  jz      short loc_180012D2A
0x180012cb7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180012cbd  mov     ebx, eax
0x180012cbf  test    eax, eax
0x180012cc1  jns     short loc_180012D2A
0x180012cc3  mov     ecx, cs:dword_180030000
0x180012cc9  cmp     ecx, 5
0x180012ccc  jbe     short loc_180012D2A
0x180012cce  mov     rdx, 200000000000h
0x180012cd8  call    _tlgKeywordOn
0x180012cdd  test    al, al
0x180012cdf  jz      short loc_180012D2A
0x180012ce1  lea     rcx, ??_R0?AV?$WnfSubscription@K$1?WNF_SHEL_LOCKSCREEN_ACTIVE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfLockScreenActiveCallback@3@AEAAXAEBK@Z@@@8; WnfSubscription<ulong,&_WNF_STATE_NAME const WNF_SHEL_LOCKSCREEN_ACTIVE,LocationDataSource,&LocationDataSource::WnfLockScreenActiveCallback(ulong const &)> `RTTI Type Descriptor'
0x180012ce8  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x180012cee  lea     rdx, word_180028F1A
0x180012cf5  mov     [rsp+48h+arg_0], ebx
0x180012cf9  mov     [rsp+48h+arg_8], rax
0x180012cfe  lea     rax, [rsp+48h+arg_8]
0x180012d03  mov     [rsp+48h+var_18], rax
0x180012d08  lea     rax, [rsp+48h+arg_0]
0x180012d0d  mov     [rsp+48h+var_20], rax
0x180012d12  lea     rax, [rsp+48h+arg_10]
0x180012d17  mov     [rsp+48h+var_28], rax
0x180012d1c  mov     [rsp+48h+arg_10], 1000000h
0x180012d25  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180012d2a  add     rsp, 40h
0x180012d2e  pop     rbx
0x180012d2f  retn
```
