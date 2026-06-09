# GSM::_dynamic_atexit_destructor_for__g_csQueue__

- ea: `0x180033130`
- end: `0x180033167`
- name: `GSM::_dynamic_atexit_destructor_for__g_csQueue__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180033130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003315c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003315c`

## pseudocode

```c
void GSM::_dynamic_atexit_destructor_for__g_csQueue__()
{
  GSM::g_csQueue = &CCritSectWithResource<CDummyResource>::`vftable';
  if ( dword_18003E418 )
  {
    dword_18003E418 = 0;
    DeleteCriticalSection(&stru_18003E3F0);
  }
}

```

## disassembly

```asm
0x180033130  sub     rsp, 28h
0x180033134  cmp     cs:dword_18003E418, 0
0x18003313b  lea     rax, ??_7?$CCritSectWithResource@VCDummyResource@@@@6B@; const CCritSectWithResource<CDummyResource>::`vftable'
0x180033142  mov     cs:?g_csQueue@GSM@@3VCCritSect@@A, rax; CCritSect GSM::g_csQueue
0x180033149  jz      short loc_180033162
0x18003314b  lea     rcx, stru_18003E3F0; lpCriticalSection
0x180033152  mov     cs:dword_18003E418, 0
0x18003315c  call    cs:__imp_DeleteCriticalSection
0x180033162  add     rsp, 28h
0x180033166  retn
```
