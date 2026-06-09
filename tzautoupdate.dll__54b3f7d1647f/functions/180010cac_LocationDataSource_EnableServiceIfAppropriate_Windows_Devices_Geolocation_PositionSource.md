# LocationDataSource::EnableServiceIfAppropriate(Windows::Devices::Geolocation::PositionSource)

- ea: `0x180010cac`
- end: `0x180010d87`
- name: `?EnableServiceIfAppropriate@LocationDataSource@@QEAAXW4PositionSource@Geolocation@Devices@Windows@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18001126c`

## callees

- `0x1800010bc`
- `0x18000166c`
- `0x1800018fc`
- `0x18000bf20`
- `0x180010cac`

## pseudocode

```c
__int64 __fastcall LocationDataSource::EnableServiceIfAppropriate(__int64 a1, int a2, __int64 a3)
{
  int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  bool v6; // sf
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // [rsp+40h] [rbp+8h] BYREF
  int v16; // [rsp+48h] [rbp+10h] BYREF

  v15 = a1;
  if ( a2 == 1 )
  {
    v3 = EnableTimeZoneAutoUpdate();
    v5 = (unsigned int)v3;
    v6 = v3 < 0;
    result = (unsigned int)dword_180030000;
    if ( v6 )
    {
      if ( (unsigned int)dword_180030000 > 5 )
      {
        result = tlgKeywordOn(v4, 0x200000000000LL, v5);
        if ( (_BYTE)result )
        {
          v16 = v13;
          v15 = 0x1000000;
          return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                   v12,
                   (__int64)&unk_180028D98,
                   v13,
                   v14,
                   (__int64)&v15,
                   (__int64)&v16);
        }
      }
    }
    else if ( (unsigned int)dword_180030000 > 5 )
    {
      result = tlgKeywordOn(v4, 0x200000000000LL, v5);
      if ( (_BYTE)result )
      {
        v11 = byte_180028DEB;
LABEL_12:
        v15 = 0x1000000;
        return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
                 v8,
                 (__int64)v11,
                 v9,
                 v10,
                 (__int64)&v15);
      }
    }
  }
  else
  {
    result = (unsigned int)dword_180030000;
    if ( (unsigned int)dword_180030000 > 5 )
    {
      result = tlgKeywordOn(a1, 0x200000000000LL, a3);
      if ( (_BYTE)result )
      {
        v11 = byte_180029535;
        goto LABEL_12;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010cac  mov     [rsp+arg_0], rcx
0x180010cb1  sub     rsp, 38h
0x180010cb5  cmp     edx, 1
0x180010cb8  jnz     loc_180010D45
0x180010cbe  call    EnableTimeZoneAutoUpdate
0x180010cc3  mov     r8d, eax
0x180010cc6  test    eax, eax
0x180010cc8  mov     eax, cs:dword_180030000
0x180010cce  js      short loc_180010CF9
0x180010cd0  cmp     eax, 5
0x180010cd3  jbe     loc_180010D82
0x180010cd9  mov     rdx, 200000000000h
0x180010ce3  call    _tlgKeywordOn
0x180010ce8  test    al, al
0x180010cea  jz      loc_180010D82
0x180010cf0  lea     rdx, byte_180028DEB
0x180010cf7  jmp     short loc_180010D6A
0x180010cf9  cmp     eax, 5
0x180010cfc  jbe     loc_180010D82
0x180010d02  mov     rdx, 200000000000h
0x180010d0c  call    _tlgKeywordOn
0x180010d11  test    al, al
0x180010d13  jz      short loc_180010D82
0x180010d15  lea     rax, [rsp+38h+arg_8]
0x180010d1a  mov     [rsp+38h+arg_8], r8d
0x180010d1f  mov     [rsp+38h+var_10], rax
0x180010d24  lea     rdx, unk_180028D98
0x180010d2b  lea     rax, [rsp+38h+arg_0]
0x180010d30  mov     [rsp+38h+arg_0], 1000000h
0x180010d39  mov     [rsp+38h+var_18], rax
0x180010d3e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180010d43  jmp     short loc_180010D82
0x180010d45  mov     eax, cs:dword_180030000
0x180010d4b  cmp     eax, 5
0x180010d4e  jbe     short loc_180010D82
0x180010d50  mov     rdx, 200000000000h
0x180010d5a  call    _tlgKeywordOn
0x180010d5f  test    al, al
0x180010d61  jz      short loc_180010D82
0x180010d63  lea     rdx, byte_180029535
0x180010d6a  lea     rax, [rsp+38h+arg_0]
0x180010d6f  mov     [rsp+38h+var_18], rax
0x180010d74  mov     [rsp+38h+arg_0], 1000000h
0x180010d7d  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180010d82  add     rsp, 38h
0x180010d86  retn
```
