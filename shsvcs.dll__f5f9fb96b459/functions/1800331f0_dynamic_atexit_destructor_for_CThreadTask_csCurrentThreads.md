# _dynamic_atexit_destructor_for__CThreadTask::_csCurrentThreads__

- ea: `0x1800331f0`
- end: `0x180033227`
- name: `_dynamic_atexit_destructor_for__CThreadTask::_csCurrentThreads__`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800331f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003321c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003321c`

## pseudocode

```c
void dynamic_atexit_destructor_for__CThreadTask::_csCurrentThreads__()
{
  CThreadTask::_csCurrentThreads = &CCritSectWithResource<CDummyResource>::`vftable';
  if ( dword_18003E460 )
  {
    dword_18003E460 = 0;
    DeleteCriticalSection(&stru_18003E438);
  }
}

```

## disassembly

```asm
0x1800331f0  sub     rsp, 28h
0x1800331f4  cmp     cs:dword_18003E460, 0
0x1800331fb  lea     rax, ??_7?$CCritSectWithResource@VCDummyResource@@@@6B@; const CCritSectWithResource<CDummyResource>::`vftable'
0x180033202  mov     cs:?_csCurrentThreads@CThreadTask@@0V?$CCritSectWithResource@V?$CCurrentThreads@$0BE@@@@@A, rax; CCritSectWithResource<CCurrentThreads<20>> CThreadTask::_csCurrentThreads
0x180033209  jz      short loc_180033222
0x18003320b  lea     rcx, stru_18003E438; lpCriticalSection
0x180033212  mov     cs:dword_18003E460, 0
0x18003321c  call    cs:__imp_DeleteCriticalSection
0x180033222  add     rsp, 28h
0x180033226  retn
```
