# WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfSubscribe(void)

- ea: `0x1800128c0`
- end: `0x18001297d`
- name: `?WnfSubscribe@?$WnfNoStateSubscription@$1?WNF_SHEL_LOGON_COMPLETE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@AEAAPEAU_WNF_USER_SUBSCRIPTION@@XZ`
- size: `189`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010784`

## callees

- `0x18000144c`
- `0x18000166c`
- `0x1800128c0`

## import_xrefs

- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180012930`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180012930`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800128ff`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800128ff`

## pseudocode

```c
__int64 __fastcall WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfSubscribe(
        __int64 a1)
{
  int v1; // ebx
  __int64 v2; // r8
  const unsigned __int16 *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v8[3]; // [rsp+40h] [rbp-18h] BYREF
  int v9; // [rsp+68h] [rbp+10h] BYREF
  __int64 v10; // [rsp+70h] [rbp+18h] BYREF
  const unsigned __int16 *v11; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  v1 = RtlSubscribeWnfStateChangeNotification(
         &v10,
         WNF_SHEL_LOGON_COMPLETE,
         0,
         WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfCallback,
         a1,
         0,
         0,
         0);
  if ( v1 < 0
    && (unsigned int)dword_180030000 > 5
    && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180030000, 0x200000000000LL, v2) )
  {
    v3 = (const unsigned __int16 *)type_info::name((type_info *)&WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&private: void LocationDataSource::WnfNoStateSubscriptionCallback(void)> `RTTI Type Descriptor');
    v9 = v1;
    v11 = v3;
    v8[0] = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v4,
      (__int64)byte_1800295A1,
      v5,
      v6,
      (__int64)v8,
      (__int64)&v9,
      &v11);
  }
  return v10;
}

```

## disassembly

```asm
0x1800128c0  mov     rax, rsp
0x1800128c3  push    rbx
0x1800128c4  sub     rsp, 50h
0x1800128c8  mov     rdx, cs:WNF_SHEL_LOGON_COMPLETE
0x1800128cf  lea     r9, ?WnfCallback@?$WnfNoStateSubscription@$1?WNF_SHEL_LOGON_COMPLETE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)>::WnfCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800128d6  mov     dword ptr [rax-20h], 0
0x1800128dd  xor     r8d, r8d
0x1800128e0  mov     dword ptr [rax-28h], 0
0x1800128e7  mov     qword ptr [rax-30h], 0
0x1800128ef  mov     [rax-38h], rcx
0x1800128f3  lea     rcx, [rax+18h]
0x1800128f7  mov     qword ptr [rax+18h], 0
0x1800128ff  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180012905  mov     ebx, eax
0x180012907  test    eax, eax
0x180012909  jns     short loc_180012972
0x18001290b  mov     ecx, cs:dword_180030000
0x180012911  cmp     ecx, 5
0x180012914  jbe     short loc_180012972
0x180012916  mov     rdx, 200000000000h
0x180012920  call    _tlgKeywordOn
0x180012925  test    al, al
0x180012927  jz      short loc_180012972
0x180012929  lea     rcx, ??_R0?AV?$WnfNoStateSubscription@$1?WNF_SHEL_LOGON_COMPLETE@@3U_WNF_STATE_NAME@@BVLocationDataSource@@$1?WnfNoStateSubscriptionCallback@3@AEAAXXZ@@@8; WnfNoStateSubscription<&_WNF_STATE_NAME const WNF_SHEL_LOGON_COMPLETE,LocationDataSource,&LocationDataSource::WnfNoStateSubscriptionCallback(void)> `RTTI Type Descriptor'
0x180012930  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x180012936  lea     rdx, byte_1800295A1
0x18001293d  mov     [rsp+58h+arg_8], ebx
0x180012941  mov     [rsp+58h+arg_18], rax
0x180012946  lea     rax, [rsp+58h+arg_18]
0x18001294b  mov     [rsp+58h+var_28], rax
0x180012950  lea     rax, [rsp+58h+arg_8]
0x180012955  mov     [rsp+58h+var_30], rax
0x18001295a  lea     rax, [rsp+58h+var_18]
0x18001295f  mov     [rsp+58h+var_38], rax
0x180012964  mov     [rsp+58h+var_18], 1000000h
0x18001296d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180012972  mov     rax, [rsp+58h+arg_10]
0x180012977  add     rsp, 50h
0x18001297b  pop     rbx
0x18001297c  retn
```
