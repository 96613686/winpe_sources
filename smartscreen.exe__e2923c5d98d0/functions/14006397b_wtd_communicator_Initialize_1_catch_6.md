# _wtd_communicator::Initialize_::_1_::catch$6

- ea: `0x14006397b`
- end: `0x1400639e9`
- name: `_wtd_communicator::Initialize_::_1_::catch$6`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400010cc`
- `0x1400014c4`
- `0x14006397b`

## string_xrefs

- `0x1400639ae`: `wtd communicator initialize failed`

## pseudocode

```c
__int64 __fastcall wtd_communicator::Initialize_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d

  if ( (unsigned int)dword_140084088 > 2 && (unsigned __int8)tlgKeywordOn(a1, 0x400000000000LL, a3) )
  {
    *(_QWORD *)(a2 + 64) = 0x1000000;
    *(_QWORD *)(a2 + 80) = "wtd communicator initialize failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v4,
      (unsigned int)&byte_140076F1F,
      v5,
      v6,
      a2 + 80,
      a2 + 64);
  }
  return 0;
}

```

## disassembly

```asm
0x14006397b  mov     [rsp+arg_8], rdx
0x140063980  push    rbp
0x140063981  sub     rsp, 40h
0x140063985  mov     rbp, rdx
0x140063988  mov     eax, cs:dword_140084088
0x14006398e  cmp     eax, 2
0x140063991  jbe     short loc_1400639D8
0x140063993  mov     rdx, 400000000000h
0x14006399d  call    _tlgKeywordOn
0x1400639a2  test    al, al
0x1400639a4  jz      short loc_1400639D8
0x1400639a6  mov     qword ptr [rbp+40h], 1000000h
0x1400639ae  lea     rax, aWtdCommunicato; "wtd communicator initialize failed"
0x1400639b5  mov     [rbp+50h], rax
0x1400639b9  lea     rax, [rbp+40h]
0x1400639bd  mov     [rsp+48h+var_20], rax
0x1400639c2  lea     rax, [rbp+50h]
0x1400639c6  mov     [rsp+48h+var_28], rax
0x1400639cb  lea     rdx, byte_140076F1F
0x1400639d2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1400639d7  nop
0x1400639d8  mov     rax, 0
0x1400639e2  add     rsp, 40h
0x1400639e6  pop     rbp
0x1400639e7  retn
```
