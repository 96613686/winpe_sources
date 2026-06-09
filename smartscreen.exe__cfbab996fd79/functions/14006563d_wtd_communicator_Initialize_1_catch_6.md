# _wtd_communicator::Initialize_::_1_::catch$6

- ea: `0x14006563d`
- end: `0x1400656ab`
- name: `_wtd_communicator::Initialize_::_1_::catch$6`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400010cc`
- `0x1400014d0`
- `0x14006563d`

## string_xrefs

- `0x140065670`: `wtd communicator initialize failed`

## pseudocode

```c
__int64 __fastcall wtd_communicator::Initialize_::_1_::catch_6(__int64 a1, __int64 a2)
{
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d

  if ( (unsigned int)dword_140086088 > 2 && (unsigned __int8)tlgKeywordOn(a1, 0x400000000000LL) )
  {
    *(_QWORD *)(a2 + 64) = 0x1000000;
    *(_QWORD *)(a2 + 80) = "wtd communicator initialize failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v3,
      (unsigned int)&byte_140078F17,
      v4,
      v5,
      a2 + 80,
      a2 + 64);
  }
  return 0;
}

```

## disassembly

```asm
0x14006563d  mov     [rsp+arg_8], rdx
0x140065642  push    rbp
0x140065643  sub     rsp, 40h
0x140065647  mov     rbp, rdx
0x14006564a  mov     eax, cs:dword_140086088
0x140065650  cmp     eax, 2
0x140065653  jbe     short loc_14006569A
0x140065655  mov     rdx, 400000000000h
0x14006565f  call    _tlgKeywordOn
0x140065664  test    al, al
0x140065666  jz      short loc_14006569A
0x140065668  mov     qword ptr [rbp+40h], 1000000h
0x140065670  lea     rax, aWtdCommunicato; "wtd communicator initialize failed"
0x140065677  mov     [rbp+50h], rax
0x14006567b  lea     rax, [rbp+40h]
0x14006567f  mov     [rsp+48h+var_20], rax
0x140065684  lea     rax, [rbp+50h]
0x140065688  mov     [rsp+48h+var_28], rax
0x14006568d  lea     rdx, byte_140078F17
0x140065694  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x140065699  nop
0x14006569a  mov     rax, 0
0x1400656a4  add     rsp, 40h
0x1400656a8  pop     rbp
0x1400656a9  retn
```
