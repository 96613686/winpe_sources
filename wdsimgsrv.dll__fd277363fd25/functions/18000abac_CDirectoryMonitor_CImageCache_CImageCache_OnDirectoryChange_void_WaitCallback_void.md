# CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::WaitCallback(void)

- ea: `0x18000abac`
- end: `0x18000acd8`
- name: `?WaitCallback@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@AEAAKXZ`
- size: `300`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ad60`

## callees

- `0x1800025f0`
- `0x18000277c`
- `0x18000a944`
- `0x18000abac`
- `0x18000aeac`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ac38`
- `KERNEL32!GetLastError` at `0x18000ac7f`
- `KERNEL32!GetLastError` at `0x18000ac38`
- `KERNEL32!GetLastError` at `0x18000ac7f`
- `KERNEL32!ChangeTimerQueueTimer` at `0x18000ac28`
- `KERNEL32!ChangeTimerQueueTimer` at `0x18000ac28`
- `KERNEL32!FindNextChangeNotification` at `0x18000ac6f`
- `KERNEL32!FindNextChangeNotification` at `0x18000ac6f`

## pseudocode

```c
__int64 __fastcall CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::WaitCallback(
        PVOID Context)
{
  unsigned int LastError; // ebx
  ULONG v3; // ebp
  __int64 v4; // rdx
  DWORD v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rdx
  _BYTE v9[24]; // [rsp+20h] [rbp-18h] BYREF

  LastError = 0;
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)Context + 10, 0) )
  {
    if ( g_ErrLibTraceFunction )
      g_ErrLibTraceFunction(L"DirMon - Change Notification for [%s]", *((_QWORD *)Context + 7));
    v3 = *((_DWORD *)Context + 16);
    CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>((__int64)v9, (__int64)Context + 88);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Context + 32, 0) == 1 )
    {
      LastError = 5023;
    }
    else if ( !ChangeTimerQueueTimer(*((HANDLE *)Context + 13), *((HANDLE *)Context + 14), v3, 0xFFFFFFFE) )
    {
      LastError = GetLastError();
    }
    CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(v9);
    if ( !(unsigned int)ElValidateWin32_0(
                          LastError,
                          v4,
                          "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h",
                          349) )
    {
      if ( FindNextChangeNotification(*((HANDLE *)Context + 9)) )
      {
        LastError = CDirectoryMonitor<CImageCache,&public: unsigned long CImageCache::OnDirectoryChange(void)>::RegisterWait((char *)Context);
        ElValidateWin32_0(LastError, v7, "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h", 357);
      }
      else
      {
        v5 = GetLastError();
        LastError = ElValidateWin32_0(v5, v6, "onecore\\internal\\base\\inc\\private\\eco\\wds\\DirMon.h", 353);
        if ( !LastError )
          return 31;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000abac  mov     [rsp+arg_0], rbx
0x18000abb1  mov     [rsp+arg_8], rbp
0x18000abb6  mov     [rsp+arg_10], rsi
0x18000abbb  push    rdi
0x18000abbc  sub     rsp, 30h
0x18000abc0  xor     ebx, ebx
0x18000abc2  mov     rdi, rcx
0x18000abc5  xor     eax, eax
0x18000abc7  lock xadd [rcx+28h], eax
0x18000abcc  test    eax, eax
0x18000abce  jnz     loc_18000ACC0
0x18000abd4  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000abdb  test    rax, rax
0x18000abde  jz      short loc_18000ABF0
0x18000abe0  mov     rdx, [rcx+38h]
0x18000abe4  lea     rcx, aDirmonChangeNo; "DirMon - Change Notification for [%s]"
0x18000abeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abf0  mov     ebp, [rdi+40h]
0x18000abf3  lea     rdx, [rdi+58h]
0x18000abf7  lea     rcx, [rsp+38h+var_18]
0x18000abfc  call    ??0?$CAutoTypeLock@VCSpinLock@@@@QEAA@PEAVCSpinLock@@H@Z; CAutoTypeLock<CSpinLock>::CAutoTypeLock<CSpinLock>(CSpinLock *,int)
0x18000ac01  xor     eax, eax
0x18000ac03  lock xadd [rdi+80h], eax
0x18000ac0b  cmp     eax, 1
0x18000ac0e  jnz     short loc_18000AC17
0x18000ac10  mov     ebx, 139Fh
0x18000ac15  jmp     short loc_18000AC46
0x18000ac17  mov     rdx, [rdi+70h]; Timer
0x18000ac1b  mov     r9d, 0FFFFFFFEh; Period
0x18000ac21  mov     rcx, [rdi+68h]; TimerQueue
0x18000ac25  mov     r8d, ebp; DueTime
0x18000ac28  call    cs:__imp_ChangeTimerQueueTimer
0x18000ac2f  nop     dword ptr [rax+rax+00h]
0x18000ac34  test    eax, eax
0x18000ac36  jnz     short loc_18000AC46
0x18000ac38  call    cs:__imp_GetLastError
0x18000ac3f  nop     dword ptr [rax+rax+00h]
0x18000ac44  mov     ebx, eax
0x18000ac46  lea     rcx, [rsp+38h+var_18]
0x18000ac4b  call    ??1?$CAutoTypeLock@VCSpinLock@@@@QEAA@XZ; CAutoTypeLock<CSpinLock>::~CAutoTypeLock<CSpinLock>(void)
0x18000ac50  lea     rsi, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\private\\"...
0x18000ac57  mov     r9d, 15Dh
0x18000ac5d  mov     r8, rsi
0x18000ac60  mov     ecx, ebx
0x18000ac62  call    ElValidateWin32_0
0x18000ac67  test    eax, eax
0x18000ac69  jnz     short loc_18000ACC0
0x18000ac6b  mov     rcx, [rdi+48h]; hChangeHandle
0x18000ac6f  call    cs:__imp_FindNextChangeNotification
0x18000ac76  nop     dword ptr [rax+rax+00h]
0x18000ac7b  test    eax, eax
0x18000ac7d  jnz     short loc_18000ACA6
0x18000ac7f  call    cs:__imp_GetLastError
0x18000ac86  nop     dword ptr [rax+rax+00h]
0x18000ac8b  mov     r9d, 161h
0x18000ac91  mov     r8, rsi
0x18000ac94  mov     ecx, eax
0x18000ac96  call    ElValidateWin32_0
0x18000ac9b  mov     ebx, eax
0x18000ac9d  test    eax, eax
0x18000ac9f  jnz     short loc_18000ACC0
0x18000aca1  lea     ebx, [rax+1Fh]
0x18000aca4  jmp     short loc_18000ACC0
0x18000aca6  mov     rcx, rdi; Context
0x18000aca9  call    ?RegisterWait@?$CDirectoryMonitor@VCImageCache@@$1?OnDirectoryChange@1@QEAAKXZ@@AEAAKXZ; CDirectoryMonitor<CImageCache,&CImageCache::OnDirectoryChange(void)>::RegisterWait(void)
0x18000acae  mov     r9d, 165h
0x18000acb4  mov     r8, rsi
0x18000acb7  mov     ecx, eax
0x18000acb9  mov     ebx, eax
0x18000acbb  call    ElValidateWin32_0
0x18000acc0  mov     rbp, [rsp+38h+arg_8]
0x18000acc5  mov     eax, ebx
0x18000acc7  mov     rbx, [rsp+38h+arg_0]
0x18000accc  mov     rsi, [rsp+38h+arg_10]
0x18000acd1  add     rsp, 30h
0x18000acd5  pop     rdi
0x18000acd6  retn
```
