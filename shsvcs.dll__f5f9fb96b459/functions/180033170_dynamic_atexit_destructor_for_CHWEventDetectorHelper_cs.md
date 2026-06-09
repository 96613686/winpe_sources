# _dynamic_atexit_destructor_for__CHWEventDetectorHelper::_cs__

- ea: `0x180033170`
- end: `0x1800331a7`
- name: `_dynamic_atexit_destructor_for__CHWEventDetectorHelper::_cs__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180033170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003319c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003319c`

## pseudocode

```c
void dynamic_atexit_destructor_for__CHWEventDetectorHelper::_cs__()
{
  CHWEventDetectorHelper::_cs = &CCritSectWithResource<CDummyResource>::`vftable';
  if ( dword_18003E3A8 )
  {
    dword_18003E3A8 = 0;
    DeleteCriticalSection(&stru_18003E380);
  }
}

```

## disassembly

```asm
0x180033170  sub     rsp, 28h
0x180033174  cmp     cs:dword_18003E3A8, 0
0x18003317b  lea     rax, ??_7?$CCritSectWithResource@VCDummyResource@@@@6B@; const CCritSectWithResource<CDummyResource>::`vftable'
0x180033182  mov     cs:?_cs@CHWEventDetectorHelper@@0VCCritSect@@A, rax; CCritSect CHWEventDetectorHelper::_cs
0x180033189  jz      short loc_1800331A2
0x18003318b  lea     rcx, stru_18003E380; lpCriticalSection
0x180033192  mov     cs:dword_18003E3A8, 0
0x18003319c  call    cs:__imp_DeleteCriticalSection
0x1800331a2  add     rsp, 28h
0x1800331a6  retn
```
