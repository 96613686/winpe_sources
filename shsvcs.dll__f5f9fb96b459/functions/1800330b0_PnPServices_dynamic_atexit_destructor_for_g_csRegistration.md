# PnPServices::_dynamic_atexit_destructor_for__g_csRegistration__

- ea: `0x1800330b0`
- end: `0x1800330e7`
- name: `PnPServices::_dynamic_atexit_destructor_for__g_csRegistration__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800330b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800330dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800330dc`

## pseudocode

```c
void PnPServices::_dynamic_atexit_destructor_for__g_csRegistration__()
{
  PnPServices::g_csRegistration = &CCritSectWithResource<CDummyResource>::`vftable';
  if ( dword_18003E498 )
  {
    dword_18003E498 = 0;
    DeleteCriticalSection(&stru_18003E470);
  }
}

```

## disassembly

```asm
0x1800330b0  sub     rsp, 28h
0x1800330b4  cmp     cs:dword_18003E498, 0
0x1800330bb  lea     rax, ??_7?$CCritSectWithResource@VCDummyResource@@@@6B@; const CCritSectWithResource<CDummyResource>::`vftable'
0x1800330c2  mov     cs:?g_csRegistration@PnPServices@@3VCCritSect@@A, rax; CCritSect PnPServices::g_csRegistration
0x1800330c9  jz      short loc_1800330E2
0x1800330cb  lea     rcx, stru_18003E470; lpCriticalSection
0x1800330d2  mov     cs:dword_18003E498, 0
0x1800330dc  call    cs:__imp_DeleteCriticalSection
0x1800330e2  add     rsp, 28h
0x1800330e6  retn
```
