# COMXProc::_dynamic_atexit_destructor_for__g_csAdviseClient__

- ea: `0x1800331b0`
- end: `0x1800331e7`
- name: `COMXProc::_dynamic_atexit_destructor_for__g_csAdviseClient__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800331b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800331dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800331dc`

## pseudocode

```c
void COMXProc::_dynamic_atexit_destructor_for__g_csAdviseClient__()
{
  COMXProc::g_csAdviseClient = &CCritSectWithResource<CDummyResource>::`vftable';
  if ( dword_18003E4D0 )
  {
    dword_18003E4D0 = 0;
    DeleteCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x1800331b0  sub     rsp, 28h
0x1800331b4  cmp     cs:dword_18003E4D0, 0
0x1800331bb  lea     rax, ??_7?$CCritSectWithResource@VCDummyResource@@@@6B@; const CCritSectWithResource<CDummyResource>::`vftable'
0x1800331c2  mov     cs:?g_csAdviseClient@COMXProc@@3VCCritSect@@A, rax; CCritSect COMXProc::g_csAdviseClient
0x1800331c9  jz      short loc_1800331E2
0x1800331cb  lea     rcx, CriticalSection; lpCriticalSection
0x1800331d2  mov     cs:dword_18003E4D0, 0
0x1800331dc  call    cs:__imp_DeleteCriticalSection
0x1800331e2  add     rsp, 28h
0x1800331e6  retn
```
