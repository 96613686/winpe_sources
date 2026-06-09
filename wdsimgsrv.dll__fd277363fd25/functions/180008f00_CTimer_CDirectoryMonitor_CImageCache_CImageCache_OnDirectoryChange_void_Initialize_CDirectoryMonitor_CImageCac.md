# CTimer<CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>>::Initialize(CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)> *,void *,ulong,ulong,void *,ulong)

- ea: `0x180008f00`
- end: `0x180008f93`
- name: `?Initialize@?$CTimer@V?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@@@QEAAKPEAV?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@PEAXKK1K@Z`
- size: `147`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008de8`

## callees

- `0x1800025f0`
- `0x18000277c`
- `0x180008f00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008f68`
- `KERNEL32!GetLastError` at `0x180008f68`
- `KERNEL32!CreateTimerQueueTimer` at `0x180008f58`
- `KERNEL32!CreateTimerQueueTimer` at `0x180008f58`

## pseudocode

```c
__int64 __fastcall CTimer<CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>>::Initialize(
        __int64 Parameter,
        __int64 a2)
{
  DWORD LastError; // esi
  _BYTE v6[24]; // [rsp+40h] [rbp-18h] BYREF

  LastError = 0;
  CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>((__int64)v6, Parameter);
  *(_QWORD *)(Parameter + 16) = 0;
  *(_QWORD *)(Parameter + 32) = a2;
  *(_QWORD *)(Parameter + 48) = 0;
  *(_DWORD *)(Parameter + 40) = 0;
  if ( !CreateTimerQueueTimer(
          (PHANDLE)(Parameter + 24),
          0,
          CTimer<CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>>::_TimerCallback,
          (PVOID)Parameter,
          0xFFFFFFFE,
          0xFFFFFFFE,
          1u) )
    LastError = GetLastError();
  CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(v6);
  return LastError;
}

```

## disassembly

```asm
0x180008f00  mov     [rsp+arg_0], rbx
0x180008f05  mov     [rsp+arg_8], rsi
0x180008f0a  push    rdi
0x180008f0b  sub     rsp, 50h
0x180008f0f  mov     rbx, rdx
0x180008f12  mov     rdi, rcx
0x180008f15  mov     rdx, rcx
0x180008f18  xor     esi, esi
0x180008f1a  lea     rcx, [rsp+58h+var_18]
0x180008f1f  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x180008f24  mov     eax, 0FFFFFFFEh
0x180008f29  mov     [rsp+58h+Flags], 1; Flags
0x180008f31  mov     [rsp+58h+Period], eax; Period
0x180008f35  lea     rcx, [rdi+18h]; phNewTimer
0x180008f39  mov     r9, rdi; Parameter
0x180008f3c  mov     [rsp+58h+DueTime], eax; DueTime
0x180008f40  lea     r8, ?_TimerCallback@?$CTimer@V?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@@@SAXPEAXE@Z; Callback
0x180008f47  mov     [rdi+10h], rsi
0x180008f4b  xor     edx, edx; TimerQueue
0x180008f4d  mov     [rdi+20h], rbx
0x180008f51  mov     [rdi+30h], rsi
0x180008f55  mov     [rdi+28h], esi
0x180008f58  call    cs:__imp_CreateTimerQueueTimer
0x180008f5f  nop     dword ptr [rax+rax+00h]
0x180008f64  test    eax, eax
0x180008f66  jnz     short loc_180008F76
0x180008f68  call    cs:__imp_GetLastError
0x180008f6f  nop     dword ptr [rax+rax+00h]
0x180008f74  mov     esi, eax
0x180008f76  lea     rcx, [rsp+58h+var_18]
0x180008f7b  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x180008f80  mov     rbx, [rsp+58h+arg_0]
0x180008f85  mov     eax, esi
0x180008f87  mov     rsi, [rsp+58h+arg_8]
0x180008f8c  add     rsp, 50h
0x180008f90  pop     rdi
0x180008f91  retn
```
