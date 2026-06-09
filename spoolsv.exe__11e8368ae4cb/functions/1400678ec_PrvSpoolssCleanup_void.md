# PrvSpoolssCleanup(void)

- ea: `0x1400678ec`
- end: `0x1400679eb`
- name: `?PrvSpoolssCleanup@@YAXXZ`
- size: `255`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400679f4`

## callees

- `0x1400079f0`
- `0x140065e20`
- `0x140065ea4`
- `0x140065ed4`
- `0x1400678ec`
- `0x14006f674`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140067918`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140067989`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400679a9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140067918`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140067989`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400679a9`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1400679e0`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x1400679e0`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1400679c4`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1400679c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006792a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006792a`

## pseudocode

```c
void __fastcall PrvSpoolssCleanup(struct _TMSTATEVAR *a1, struct NCoreLibrary::TReferenceCount *a2)
{
  if ( dword_1400CBBD8 )
  {
    TMDestroy(a1);
    dword_1400CBBD8 = 0;
  }
  if ( dword_1400CBBD0 )
  {
    DeleteCriticalSection(&RouterNotifySection);
    if ( hEventPoll )
      CloseHandle(hEventPoll);
    dword_1400CBBD0 = 0;
  }
  if ( gpUserTokenTable )
    NRouter::TUserTokenTable::`scalar deleting destructor'(gpUserTokenTable, (unsigned int)a2);
  if ( gpSessionReg )
    NRouter::TSessionRegistration::`scalar deleting destructor'(gpSessionReg, (unsigned int)a2);
  if ( gpSessionCS )
    NCoreLibrary::TCriticalSection::`scalar deleting destructor'(gpSessionCS, (unsigned int)a2);
  NCoreLibrary::EasyRelease(pEventInit, a2);
  if ( dword_1400CBBD4 )
  {
    DeleteCriticalSection(&DeviceArrivalCS);
    dword_1400CBBD4 = 0;
  }
  if ( dword_1400CBBDC )
  {
    DeleteCriticalSection(&RouterCriticalSection);
    dword_1400CBBDC = 0;
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
0x1400678ec  sub     rsp, 28h
0x1400678f0  cmp     cs:dword_1400CBBD8, 0
0x1400678f7  jz      short loc_140067908
0x1400678f9  call    ?TMDestroy@@YAHPEAU_TMSTATEVAR@@@Z; TMDestroy(_TMSTATEVAR *)
0x1400678fe  mov     cs:dword_1400CBBD8, 0
0x140067908  cmp     cs:dword_1400CBBD0, 0
0x14006790f  jz      short loc_14006793A
0x140067911  lea     rcx, ?RouterNotifySection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140067918  call    cs:__imp_DeleteCriticalSection
0x14006791e  mov     rcx, cs:?hEventPoll@@3PEAXEA; hObject
0x140067925  test    rcx, rcx
0x140067928  jz      short loc_140067930
0x14006792a  call    cs:__imp_CloseHandle
0x140067930  mov     cs:dword_1400CBBD0, 0
0x14006793a  mov     rcx, cs:?gpUserTokenTable@@3PEAVTUserTokenTable@NRouter@@EA; this
0x140067941  test    rcx, rcx
0x140067944  jz      short loc_14006794B
0x140067946  call    ??_GTUserTokenTable@NRouter@@QEAAPEAXI@Z; NRouter::TUserTokenTable::`scalar deleting destructor'(uint)
0x14006794b  mov     rcx, cs:?gpSessionReg@@3PEAVTSessionRegistration@NRouter@@EA; this
0x140067952  test    rcx, rcx
0x140067955  jz      short loc_14006795C
0x140067957  call    ??_GTSessionRegistration@NRouter@@QEAAPEAXI@Z; NRouter::TSessionRegistration::`scalar deleting destructor'(uint)
0x14006795c  mov     rcx, cs:?gpSessionCS@@3PEAVTCriticalSection@NCoreLibrary@@EA; this
0x140067963  test    rcx, rcx
0x140067966  jz      short loc_14006796D
0x140067968  call    ??_GTCriticalSection@NCoreLibrary@@QEAAPEAXI@Z; NCoreLibrary::TCriticalSection::`scalar deleting destructor'(uint)
0x14006796d  mov     rcx, cs:?pEventInit@@3PEAVTAutoHandle@NCoreLibrary@@EA; this
0x140067974  call    ?EasyRelease@NCoreLibrary@@YAXPEAVTReferenceCount@1@@Z; NCoreLibrary::EasyRelease(NCoreLibrary::TReferenceCount *)
0x140067979  cmp     cs:dword_1400CBBD4, 0
0x140067980  jz      short loc_140067999
0x140067982  lea     rcx, ?DeviceArrivalCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140067989  call    cs:__imp_DeleteCriticalSection
0x14006798f  mov     cs:dword_1400CBBD4, 0
0x140067999  cmp     cs:dword_1400CBBDC, 0
0x1400679a0  jz      short loc_1400679B9
0x1400679a2  lea     rcx, ?RouterCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400679a9  call    cs:__imp_DeleteCriticalSection
0x1400679af  mov     cs:dword_1400CBBDC, 0
0x1400679b9  mov     ecx, cs:?gdwTlsGetPrinterIndex@@3KA; dwTlsIndex
0x1400679bf  cmp     ecx, 0FFFFFFFFh
0x1400679c2  jz      short loc_1400679D4
0x1400679c4  call    cs:__imp_TlsFree
0x1400679ca  mov     cs:?gdwTlsGetPrinterIndex@@3KA, 0FFFFFFFFh; ulong gdwTlsGetPrinterIndex
0x1400679d4  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x1400679db  test    rcx, rcx
0x1400679de  jz      short loc_1400679E6
0x1400679e0  call    cs:__imp_HeapDestroy
0x1400679e6  add     rsp, 28h
0x1400679ea  retn
```
