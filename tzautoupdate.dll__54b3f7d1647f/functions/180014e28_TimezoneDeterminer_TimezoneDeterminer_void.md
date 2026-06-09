# TimezoneDeterminer::~TimezoneDeterminer(void)

- ea: `0x180014e28`
- end: `0x180014e84`
- name: `??1TimezoneDeterminer@@QEAA@XZ`
- size: `92`
- prototype: `void __fastcall(TimezoneDeterminer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800049c8`
- `0x18001b58a`

## callees

- `0x18000ad08`
- `0x180014e28`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180014e60`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014e60`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014e44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014e44`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014e3a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014e3a`

## pseudocode

```c
void __fastcall TimezoneDeterminer::~TimezoneDeterminer(TimezoneDeterminer *this)
{
  __int64 v2; // rcx
  __int64 v3; // rdx

  WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 5), 1);
  CloseThreadpoolTimer(*((PTP_TIMER *)this + 5));
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
  {
    std::vector<std::unique_ptr<Finder>>::_Destroy(v2, v3, *((_QWORD *)this + 2));
    operator delete(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180014e28  push    rbx
0x180014e2a  sub     rsp, 20h
0x180014e2e  mov     rbx, rcx
0x180014e31  mov     edx, 1; fCancelPendingCallbacks
0x180014e36  mov     rcx, [rcx+28h]; pti
0x180014e3a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014e40  mov     rcx, [rbx+28h]; pti
0x180014e44  call    cs:__imp_CloseThreadpoolTimer
0x180014e4a  mov     rdx, [rbx+8]
0x180014e4e  test    rdx, rdx
0x180014e51  jz      short loc_180014E7E
0x180014e53  mov     r8, [rbx+10h]
0x180014e57  call    ?_Destroy@?$vector@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@V?$allocator@V?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VFinder@@U?$default_delete@VFinder@@@std@@@2@0@Z; std::vector<std::unique_ptr<Finder>>::_Destroy(std::unique_ptr<Finder> *,std::unique_ptr<Finder> *)
0x180014e5c  mov     rcx, [rbx+8]
0x180014e60  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014e66  mov     qword ptr [rbx+8], 0
0x180014e6e  mov     qword ptr [rbx+10h], 0
0x180014e76  mov     qword ptr [rbx+18h], 0
0x180014e7e  add     rsp, 20h
0x180014e82  pop     rbx
0x180014e83  retn
```
