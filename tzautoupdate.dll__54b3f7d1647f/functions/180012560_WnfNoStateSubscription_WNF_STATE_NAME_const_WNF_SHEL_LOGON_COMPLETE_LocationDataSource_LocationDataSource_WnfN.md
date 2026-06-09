# WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180012560`
- end: `0x180012588`
- name: `?WnfCallback@?$WnfNoStateSubscription@$1?WNF_SHEL_LOGON_COMPLETE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, LocationDataSource **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012560`
- `0x180012628`

## pseudocode

```c
__int64 __fastcall WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfCallback(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        LocationDataSource **a4)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // [rsp+58h] [rbp+20h] BYREF

  if ( !a4 )
    return 0;
  LODWORD(v13) = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    LocationDataSource::WnfLockScreenActiveCallback(*a4, (const unsigned int *)&v13);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5) )
      {
        v13 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          v7,
          (__int64)byte_180028D1D,
          v8,
          v9,
          (__int64)&v13);
      }
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180012586);
      return 0;
    }
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5) )
      {
        v13 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
          v10,
          (__int64)byte_18002912B,
          v11,
          v12,
          (__int64)&v13);
      }
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_18001257F);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012560  sub     rsp, 38h
0x180012564  test    r9, r9
0x180012567  jz      short loc_18001257F
0x180012569  mov     dword ptr [rsp+38h+arg_18], 0
0x180012571  lea     rdx, [rsp+38h+arg_18]; unsigned int *
0x180012576  mov     rcx, [r9]; this
0x180012579  call    ?WnfLockScreenActiveCallback@LocationDataSource@@AEAAXAEBK@Z; LocationDataSource::WnfLockScreenActiveCallback(ulong const &)
0x18001257e  nop
0x18001257f  xor     eax, eax
0x180012581  add     rsp, 38h
0x180012585  retn
0x180012586  jmp     short loc_18001257F
```
