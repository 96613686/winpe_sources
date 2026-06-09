# _ServiceMain_::_1_::catch$6

- ea: `0x18001c4a4`
- end: `0x18001c4fe`
- name: `_ServiceMain_::_1_::catch$6`
- size: `90`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1800010bc`
- `0x18000166c`
- `0x18001c4a4`

## pseudocode

```c
__int64 __fastcall ServiceMain_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9

  if ( (unsigned int)dword_180030000 > 5 && (unsigned __int8)tlgKeywordOn(a1, 0x200000000000LL, a3) )
  {
    *(_QWORD *)(a2 + 64) = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v4,
      (__int64)&word_180029B2E,
      v5,
      v6,
      a2 + 64);
  }
  return 0;
}

```

## disassembly

```asm
0x18001c4a4  mov     [rsp+arg_8], rdx
0x18001c4a9  push    rbp
0x18001c4aa  sub     rsp, 40h
0x18001c4ae  mov     rbp, rdx
0x18001c4b1  mov     eax, cs:dword_180030000
0x18001c4b7  cmp     eax, 5
0x18001c4ba  jbe     short loc_18001C4ED
0x18001c4bc  mov     rdx, 200000000000h
0x18001c4c6  call    _tlgKeywordOn
0x18001c4cb  test    al, al
0x18001c4cd  jz      short loc_18001C4ED
0x18001c4cf  mov     qword ptr [rbp+40h], 1000000h
0x18001c4d7  lea     rax, [rbp+40h]
0x18001c4db  mov     [rsp+48h+var_28], rax
0x18001c4e0  lea     rdx, word_180029B2E
0x18001c4e7  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18001c4ec  nop
0x18001c4ed  mov     rax, 0
0x18001c4f7  add     rsp, 40h
0x18001c4fb  pop     rbp
0x18001c4fc  retn
```
