# WnfSubscription<WNF_CELL_NITZ_INFO_TYPE,&_WNF_STATE_NAME const WNF_CELL_NITZ_INFO,NitzDataSource,&NitzDataSource::WnfCellNetworkTimeCallback(WNF_CELL_NITZ_INFO_TYPE const &)>::WnfUnsubscribe(void)

- ea: `0x18000a84c`
- end: `0x18000a8d4`
- name: `?WnfUnsubscribe@?$WnfSubscription@UWNF_CELL_NITZ_INFO_TYPE@@$1?WNF_CELL_NITZ_INFO@@3U_WNF_STATE_NAME@@BVNitzDataSource@@$1?WnfCellNetworkTimeCallback@4@AEAAXAEBU1@@Z@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800044a4`
- `0x1800048d8`

## callees

- `0x18000144c`
- `0x18000166c`
- `0x18000a84c`

## import_xrefs

- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x18000a88c`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x18000a88c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000a85b`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000a85b`

## pseudocode

```c
void __fastcall WnfSubscription<WNF_CELL_NITZ_INFO_TYPE,&_WNF_STATE_NAME const WNF_CELL_NITZ_INFO,NitzDataSource,&private: void NitzDataSource::WnfCellNetworkTimeCallback(WNF_CELL_NITZ_INFO_TYPE const &)>::WnfUnsubscribe(
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
        v3 = (const unsigned __int16 *)type_info::name((type_info *)&WnfSubscription<WNF_CELL_NITZ_INFO_TYPE,&_WNF_STATE_NAME const WNF_CELL_NITZ_INFO,NitzDataSource,&private: void NitzDataSource::WnfCellNetworkTimeCallback(WNF_CELL_NITZ_INFO_TYPE const &)> `RTTI Type Descriptor');
        v7 = v1;
        v8 = v3;
        v9 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v4,
          (__int64)byte_1800283BB,
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
0x18000a84c  push    rbx
0x18000a84e  sub     rsp, 40h
0x18000a852  mov     rcx, [rcx+8]
0x18000a856  test    rcx, rcx
0x18000a859  jz      short loc_18000A8CE
0x18000a85b  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000a861  mov     ebx, eax
0x18000a863  test    eax, eax
0x18000a865  jns     short loc_18000A8CE
0x18000a867  mov     ecx, cs:dword_180030000
0x18000a86d  cmp     ecx, 5
0x18000a870  jbe     short loc_18000A8CE
0x18000a872  mov     rdx, 200000000000h
0x18000a87c  call    _tlgKeywordOn
0x18000a881  test    al, al
0x18000a883  jz      short loc_18000A8CE
0x18000a885  lea     rcx, ??_R0?AV?$WnfSubscription@UWNF_CELL_NITZ_INFO_TYPE@@$1?WNF_CELL_NITZ_INFO@@3U_WNF_STATE_NAME@@BVNitzDataSource@@$1?WnfCellNetworkTimeCallback@4@AEAAXAEBU1@@Z@@@8; WnfSubscription<WNF_CELL_NITZ_INFO_TYPE,&_WNF_STATE_NAME const WNF_CELL_NITZ_INFO,NitzDataSource,&NitzDataSource::WnfCellNetworkTimeCallback(WNF_CELL_NITZ_INFO_TYPE const &)> `RTTI Type Descriptor'
0x18000a88c  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x18000a892  lea     rdx, byte_1800283BB
0x18000a899  mov     [rsp+48h+arg_0], ebx
0x18000a89d  mov     [rsp+48h+arg_8], rax
0x18000a8a2  lea     rax, [rsp+48h+arg_8]
0x18000a8a7  mov     [rsp+48h+var_18], rax
0x18000a8ac  lea     rax, [rsp+48h+arg_0]
0x18000a8b1  mov     [rsp+48h+var_20], rax
0x18000a8b6  lea     rax, [rsp+48h+arg_10]
0x18000a8bb  mov     [rsp+48h+var_28], rax
0x18000a8c0  mov     [rsp+48h+arg_10], 1000000h
0x18000a8c9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000a8ce  add     rsp, 40h
0x18000a8d2  pop     rbx
0x18000a8d3  retn
```
