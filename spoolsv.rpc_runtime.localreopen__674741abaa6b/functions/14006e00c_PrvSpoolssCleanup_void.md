# PrvSpoolssCleanup(void)

- ea: `0x14006e00c`
- end: `0x14006e130`
- name: `?PrvSpoolssCleanup@@YAXXZ`
- size: `292`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14006e138`

## callees

- `0x140008550`
- `0x14006c330`
- `0x14006c3b8`
- `0x14006c3e8`
- `0x14006e00c`
- `0x14007652c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006e038`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006e0b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006e0db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006e038`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006e0b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006e0db`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x14006e11e`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x14006e11e`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x14006e0fc`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x14006e0fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006e050`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006e050`

## pseudocode

```c
void __fastcall PrvSpoolssCleanup(struct _TMSTATEVAR *a1, struct NCoreLibrary::TReferenceCount *a2)
{
  if ( dword_1400D2D48 )
  {
    TMDestroy(a1);
    dword_1400D2D48 = 0;
  }
  if ( dword_1400D2D50 )
  {
    DeleteCriticalSection(&RouterNotifySection);
    if ( hEventPoll )
      CloseHandle(hEventPoll);
    dword_1400D2D50 = 0;
  }
  if ( gpUserTokenTable )
    NRouter::TUserTokenTable::`scalar deleting destructor'(gpUserTokenTable, (unsigned int)a2);
  if ( gpSessionReg )
    NRouter::TSessionRegistration::`scalar deleting destructor'(gpSessionReg, (unsigned int)a2);
  if ( gpSessionCS )
    NCoreLibrary::TCriticalSection::`scalar deleting destructor'(gpSessionCS, (unsigned int)a2);
  NCoreLibrary::EasyRelease(pEventInit, a2);
  if ( dword_1400D2D54 )
  {
    DeleteCriticalSection(&DeviceArrivalCS);
    dword_1400D2D54 = 0;
  }
  if ( dword_1400D2D4C )
  {
    DeleteCriticalSection(&RouterCriticalSection);
    dword_1400D2D4C = 0;
  }
  if ( gdwTlsGetPrinterIndex != -1 )
  {
    TlsFree(gdwTlsGetPrinterIndex);
    gdwTlsGetPrinterIndex = -1;
  }
  if ( g_hSpoolssHeap )
    HeapDestroy(g_hSpoolssHeap);
}

```

## disassembly

```asm
0x14006e00c  sub     rsp, 28h
0x14006e010  cmp     cs:dword_1400D2D48, 0
0x14006e017  jz      short loc_14006E028
0x14006e019  call    ?TMDestroy@@YAHPEAU_TMSTATEVAR@@@Z; TMDestroy(_TMSTATEVAR *)
0x14006e01e  mov     cs:dword_1400D2D48, 0
0x14006e028  cmp     cs:dword_1400D2D50, 0
0x14006e02f  jz      short loc_14006E066
0x14006e031  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006e038  call    cs:__imp_DeleteCriticalSection
0x14006e03f  nop     dword ptr [rax+rax+00h]
0x14006e044  mov     rcx, cs:?hEventPoll@@3PEAXEA; hObject
0x14006e04b  test    rcx, rcx
0x14006e04e  jz      short loc_14006E05C
0x14006e050  call    cs:__imp_CloseHandle
0x14006e057  nop     dword ptr [rax+rax+00h]
0x14006e05c  mov     cs:dword_1400D2D50, 0
0x14006e066  mov     rcx, cs:?gpUserTokenTable@@3PEAVTUserTokenTable@NRouter@@EA; this
0x14006e06d  test    rcx, rcx
0x14006e070  jz      short loc_14006E077
0x14006e072  call    ??_GTUserTokenTable@NRouter@@QEAAPEAXI@Z; NRouter::TUserTokenTable::`scalar deleting destructor'(uint)
0x14006e077  mov     rcx, cs:?gpSessionReg@@3PEAVTSessionRegistration@NRouter@@EA; this
0x14006e07e  test    rcx, rcx
0x14006e081  jz      short loc_14006E088
0x14006e083  call    ??_GTSessionRegistration@NRouter@@QEAAPEAXI@Z; NRouter::TSessionRegistration::`scalar deleting destructor'(uint)
0x14006e088  mov     rcx, cs:?gpSessionCS@@3PEAVTCriticalSection@NCoreLibrary@@EA; this
0x14006e08f  test    rcx, rcx
0x14006e092  jz      short loc_14006E099
0x14006e094  call    ??_GTCriticalSection@NCoreLibrary@@QEAAPEAXI@Z; NCoreLibrary::TCriticalSection::`scalar deleting destructor'(uint)
0x14006e099  mov     rcx, cs:?pEventInit@@3PEAVTAutoHandle@NCoreLibrary@@EA; this
0x14006e0a0  call    ?EasyRelease@NCoreLibrary@@YAXPEAVTReferenceCount@1@@Z; NCoreLibrary::EasyRelease(NCoreLibrary::TReferenceCount *)
0x14006e0a5  cmp     cs:dword_1400D2D54, 0
0x14006e0ac  jz      short loc_14006E0CB
0x14006e0ae  lea     rcx, ?DeviceArrivalCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006e0b5  call    cs:__imp_DeleteCriticalSection
0x14006e0bc  nop     dword ptr [rax+rax+00h]
0x14006e0c1  mov     cs:dword_1400D2D54, 0
0x14006e0cb  cmp     cs:dword_1400D2D4C, 0
0x14006e0d2  jz      short loc_14006E0F1
0x14006e0d4  lea     rcx, ?RouterCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14006e0db  call    cs:__imp_DeleteCriticalSection
0x14006e0e2  nop     dword ptr [rax+rax+00h]
0x14006e0e7  mov     cs:dword_1400D2D4C, 0
0x14006e0f1  mov     ecx, cs:?gdwTlsGetPrinterIndex@@3KA; dwTlsIndex
0x14006e0f7  cmp     ecx, 0FFFFFFFFh
0x14006e0fa  jz      short loc_14006E112
0x14006e0fc  call    cs:__imp_TlsFree
0x14006e103  nop     dword ptr [rax+rax+00h]
0x14006e108  mov     cs:?gdwTlsGetPrinterIndex@@3KA, 0FFFFFFFFh; ulong gdwTlsGetPrinterIndex
0x14006e112  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006e119  test    rcx, rcx
0x14006e11c  jz      short loc_14006E12A
0x14006e11e  call    cs:__imp_HeapDestroy
0x14006e125  nop     dword ptr [rax+rax+00h]
0x14006e12a  add     rsp, 28h
0x14006e12e  retn
```
