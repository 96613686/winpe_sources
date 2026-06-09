# FileManager::~FileManager(void)

- ea: `0x1800b3cdc`
- end: `0x1800b3d5b`
- name: `??1FileManager@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(FileManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a1ea4`
- `0x1800d98c0`

## callees

- `0x180028314`
- `0x1800b3cdc`
- `0x1800b3e64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b3d1e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b3d1e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b3d35`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b3d35`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b3d2c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b3d2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b3cf2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b3cf2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b3d08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b3d08`

## pseudocode

```c
void __fastcall FileManager::~FileManager(RTL_SRWLOCK *this)
{
  struct _TP_TIMER *Ptr; // rsi

  AcquireSRWLockExclusive(this + 4);
  Ptr = (struct _TP_TIMER *)this[5].Ptr;
  this[5].Ptr = 0;
  ReleaseSRWLockExclusive(this + 4);
  if ( Ptr )
  {
    SetThreadpoolTimer(Ptr, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(Ptr, 1);
    CloseThreadpoolTimer(Ptr);
  }
  utl::vector<wmi::AutoRef<File>,utl::allocator<wmi::AutoRef<File>>>::_Uninit(&this[6]);
  utl::vector<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::allocator<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>>::_Uninit(this);
}

```

## disassembly

```asm
0x1800b3cdc  mov     [rsp+arg_0], rbx
0x1800b3ce1  mov     [rsp+arg_8], rsi
0x1800b3ce6  push    rdi
0x1800b3ce7  sub     rsp, 20h
0x1800b3ceb  mov     rdi, rcx
0x1800b3cee  add     rcx, 20h ; ' '; SRWLock
0x1800b3cf2  call    cs:__imp_AcquireSRWLockExclusive
0x1800b3cf8  mov     rsi, [rdi+28h]
0x1800b3cfc  lea     rcx, [rdi+20h]; SRWLock
0x1800b3d00  mov     qword ptr [rdi+28h], 0
0x1800b3d08  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b3d0e  test    rsi, rsi
0x1800b3d11  jz      short loc_1800B3D3B
0x1800b3d13  xor     r9d, r9d; msWindowLength
0x1800b3d16  xor     r8d, r8d; msPeriod
0x1800b3d19  xor     edx, edx; pftDueTime
0x1800b3d1b  mov     rcx, rsi; pti
0x1800b3d1e  call    cs:__imp_SetThreadpoolTimer
0x1800b3d24  mov     edx, 1; fCancelPendingCallbacks
0x1800b3d29  mov     rcx, rsi; pti
0x1800b3d2c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b3d32  mov     rcx, rsi; pti
0x1800b3d35  call    cs:__imp_CloseThreadpoolTimer
0x1800b3d3b  lea     rcx, [rdi+30h]
0x1800b3d3f  call    ?_Uninit@?$vector@V?$AutoRef@VFile@@@wmi@@V?$allocator@V?$AutoRef@VFile@@@wmi@@@utl@@@utl@@AEAAXXZ; utl::vector<wmi::AutoRef<File>,utl::allocator<wmi::AutoRef<File>>>::_Uninit(void)
0x1800b3d44  mov     rcx, rdi
0x1800b3d47  mov     rbx, [rsp+28h+arg_0]
0x1800b3d4c  mov     rsi, [rsp+28h+arg_8]
0x1800b3d51  add     rsp, 20h
0x1800b3d55  pop     rdi
0x1800b3d56  jmp     ?_Uninit@?$vector@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::allocator<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>>::_Uninit(void)
```
