# XProcHelpers::_dynamic_atexit_destructor_for__g_cs__

- ea: `0x1800330f0`
- end: `0x180033127`
- name: `XProcHelpers::_dynamic_atexit_destructor_for__g_cs__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800330f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003311c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003311c`

## pseudocode

```c
void XProcHelpers::_dynamic_atexit_destructor_for__g_cs__()
{
  XProcHelpers::g_cs = &CCritSectWithResource<CDummyResource>::`vftable';
  if ( dword_18003E3E0 )
  {
    dword_18003E3E0 = 0;
    DeleteCriticalSection(&stru_18003E3B8);
  }
}

```

## disassembly

```asm
0x1800330f0  sub     rsp, 28h
0x1800330f4  cmp     cs:dword_18003E3E0, 0
0x1800330fb  lea     rax, ??_7?$CCritSectWithResource@VCDummyResource@@@@6B@; const CCritSectWithResource<CDummyResource>::`vftable'
0x180033102  mov     cs:?g_cs@XProcHelpers@@3VCCritSect@@A, rax; CCritSect XProcHelpers::g_cs
0x180033109  jz      short loc_180033122
0x18003310b  lea     rcx, stru_18003E3B8; lpCriticalSection
0x180033112  mov     cs:dword_18003E3E0, 0
0x18003311c  call    cs:__imp_DeleteCriticalSection
0x180033122  add     rsp, 28h
0x180033126  retn
```
