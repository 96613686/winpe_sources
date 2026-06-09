# _tlgWriteActivityAutoStop<0,5>(_tlgProvider_t const *,_GUID const *)

- ea: `0x180006494`
- end: `0x1800064b3`
- name: `??$_tlgWriteActivityAutoStop@$0A@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z`
- size: `31`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006858`

## callees

- `0x1800010b0`
- `0x180006494`

## pseudocode

```c
__int64 __fastcall _tlgWriteActivityAutoStop<0,5>(unsigned int *a1, __int64 a2)
{
  __int64 result; // rax

  result = *a1;
  if ( (unsigned int)result > 5 )
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
             a1,
             byte_18003ECF1,
             a2);
  return result;
}

```

## disassembly

```asm
0x180006494  sub     rsp, 28h
0x180006498  mov     eax, [rcx]
0x18000649a  cmp     eax, 5
0x18000649d  jbe     short loc_1800064AE
0x18000649f  mov     r8, rdx
0x1800064a2  lea     rdx, byte_18003ECF1
0x1800064a9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800064ae  add     rsp, 28h
0x1800064b2  retn
```
