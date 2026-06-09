# CSecureProcessDump::Init(ulong,ulong,_MINIDUMP_TYPE,tlx::unique_any<tlx::file_handle_traits>,tlx::unique_any<tlx::file_handle_traits>)

- ea: `0x14000628c`
- end: `0x14000641f`
- name: `?Init@CSecureProcessDump@@QEAAJKKW4_MINIDUMP_TYPE@@V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@1@Z`
- size: `403`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, DWORD dwProcessId, unsigned int, LONG, HANDLE *, HANDLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400068c0`

## callees

- `0x140005128`
- `0x1400060a4`
- `0x14000628c`
- `0x14000f334`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400062e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006318`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400063f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000640a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400062e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006318`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400063f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000640a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140006327`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140006327`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400062a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400062a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400063e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400063e4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140006345`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140006345`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400063be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400063be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000635e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000635e`

## string_xrefs

- `0x14000638a`: `Couldn't create threadpool wait`

## pseudocode

```c
__int64 __fastcall CSecureProcessDump::Init(
        LPCRITICAL_SECTION lpCriticalSection,
        DWORD dwProcessId,
        unsigned int a3,
        LONG a4,
        HANDLE *a5,
        HANDLE *a6)
{
  HANDLE v10; // rax
  HANDLE OwningThread; // rcx
  HANDLE v12; // rax
  HANDLE LockSemaphore; // rcx
  signed int v14; // ebx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *SpinCount; // rcx
  struct _TP_WAIT *v17; // rcx
  signed int LastError; // eax
  wil::details *v20; // [rsp+20h] [rbp-48h]
  const char *v21; // [rsp+30h] [rbp-38h]
  wil::details::in1diag4 *retaddr; // [rsp+68h] [rbp+0h]

  EnterCriticalSection(lpCriticalSection);
  LODWORD(lpCriticalSection[62].DebugInfo) = dwProcessId;
  HIDWORD(lpCriticalSection[62].DebugInfo) = a3;
  lpCriticalSection[62].LockCount = a4;
  v10 = *a5;
  *a5 = 0;
  OwningThread = lpCriticalSection[62].OwningThread;
  lpCriticalSection[62].OwningThread = v10;
  if ( (unsigned __int64)OwningThread + 1 > 1 )
    CloseHandle(OwningThread);
  v12 = *a6;
  *a6 = 0;
  LockSemaphore = lpCriticalSection[62].LockSemaphore;
  lpCriticalSection[62].LockSemaphore = v12;
  if ( (unsigned __int64)LockSemaphore + 1 > 1 )
    CloseHandle(LockSemaphore);
  if ( WaitForSingleObject(lpCriticalSection[62].LockSemaphore, 0) )
  {
    ThreadpoolWait = CreateThreadpoolWait(CSecureProcessDump::StaticCancelCallback, lpCriticalSection, 0);
    SpinCount = (struct _TP_WAIT *)lpCriticalSection[62].SpinCount;
    lpCriticalSection[62].SpinCount = (ULONG_PTR)ThreadpoolWait;
    if ( SpinCount )
      CloseThreadpoolWait(SpinCount);
    v17 = (struct _TP_WAIT *)lpCriticalSection[62].SpinCount;
    if ( v17 )
    {
      SetThreadpoolWait(v17, lpCriticalSection[62].LockSemaphore, 0);
      v14 = CDumpCollection::Init((CDumpCollection *)&lpCriticalSection[1].LockCount, dwProcessId, a3);
    }
    else
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v20) = v14;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x14C,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\exe\\secure\\securedump.cpp",
        "CSecureProcessDump::Init",
        v20,
        (int)"Couldn't create threadpool wait",
        v21);
    }
    if ( v14 < 0 )
      CSecureProcessDump::Cleanup(lpCriticalSection);
  }
  else
  {
    v14 = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( (unsigned __int64)*a5 + 1 > 1 )
    CloseHandle(*a5);
  if ( (unsigned __int64)*a6 + 1 > 1 )
    CloseHandle(*a6);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000628c  push    rbx
0x14000628e  push    rbp
0x14000628f  push    rsi
0x140006290  push    rdi
0x140006291  push    r14
0x140006293  push    r15
0x140006295  sub     rsp, 38h
0x140006299  mov     ebx, r9d
0x14000629c  mov     ebp, r8d
0x14000629f  mov     r15d, edx
0x1400062a2  mov     rdi, rcx
0x1400062a5  call    cs:__imp_EnterCriticalSection
0x1400062ab  mov     r14, [rsp+68h+arg_20]
0x1400062b3  mov     [rdi+9B0h], r15d
0x1400062ba  mov     [rdi+9B4h], ebp
0x1400062c0  mov     [rdi+9B8h], ebx
0x1400062c6  mov     rax, [r14]
0x1400062c9  mov     qword ptr [r14], 0
0x1400062d0  mov     rcx, [rdi+9C0h]; hObject
0x1400062d7  mov     [rdi+9C0h], rax
0x1400062de  lea     rax, [rcx+1]
0x1400062e2  cmp     rax, 1
0x1400062e6  jbe     short loc_1400062EE
0x1400062e8  call    cs:__imp_CloseHandle
0x1400062ee  mov     rsi, [rsp+68h+arg_28]
0x1400062f6  mov     rax, [rsi]
0x1400062f9  mov     qword ptr [rsi], 0
0x140006300  mov     rcx, [rdi+9C8h]; hObject
0x140006307  mov     [rdi+9C8h], rax
0x14000630e  lea     rax, [rcx+1]
0x140006312  cmp     rax, 1
0x140006316  jbe     short loc_14000631E
0x140006318  call    cs:__imp_CloseHandle
0x14000631e  mov     rcx, [rdi+9C8h]; hHandle
0x140006325  xor     edx, edx; dwMilliseconds
0x140006327  call    cs:__imp_WaitForSingleObject
0x14000632d  test    eax, eax
0x14000632f  jnz     short loc_140006338
0x140006331  xor     ebx, ebx
0x140006333  jmp     loc_1400063E1
0x140006338  xor     r8d, r8d; pcbe
0x14000633b  lea     rcx, ?StaticCancelCallback@CSecureProcessDump@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x140006342  mov     rdx, rdi; pv
0x140006345  call    cs:__imp_CreateThreadpoolWait
0x14000634b  mov     rcx, [rdi+9D0h]; pwa
0x140006352  mov     [rdi+9D0h], rax
0x140006359  test    rcx, rcx
0x14000635c  jz      short loc_140006364
0x14000635e  call    cs:__imp_CloseThreadpoolWait
0x140006364  mov     rcx, [rdi+9D0h]; pwa
0x14000636b  test    rcx, rcx
0x14000636e  jnz     short loc_1400063B4
0x140006370  call    cs:__imp_GetLastError
0x140006376  mov     ebx, eax
0x140006378  test    eax, eax
0x14000637a  jle     short loc_140006385
0x14000637c  movzx   ebx, ax
0x14000637f  or      ebx, 80070000h
0x140006385  mov     rcx, [rsp+68h]; this
0x14000638a  lea     rax, aCouldnTCreateT; "Couldn't create threadpool wait"
0x140006391  mov     qword ptr [rsp+68h+var_40], rax; int
0x140006396  lea     r9, aCsecureprocess_0; "CSecureProcessDump::Init"
0x14000639d  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\werfa"...
0x1400063a4  mov     dword ptr [rsp+68h+var_48], ebx; wil::details *
0x1400063a8  mov     edx, 14Ch; void *
0x1400063ad  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400063b2  jmp     short loc_1400063D5
0x1400063b4  mov     rdx, [rdi+9C8h]; h
0x1400063bb  xor     r8d, r8d; pftTimeout
0x1400063be  call    cs:__imp_SetThreadpoolWait
0x1400063c4  lea     rcx, [rdi+30h]; this
0x1400063c8  mov     r8d, ebp; unsigned int
0x1400063cb  mov     edx, r15d; dwProcessId
0x1400063ce  call    ?Init@CDumpCollection@@QEAAJKK@Z; CDumpCollection::Init(ulong,ulong)
0x1400063d3  mov     ebx, eax
0x1400063d5  test    ebx, ebx
0x1400063d7  jns     short loc_1400063E1
0x1400063d9  mov     rcx, rdi; lpCriticalSection
0x1400063dc  call    ?Cleanup@CSecureProcessDump@@QEAAXXZ; CSecureProcessDump::Cleanup(void)
0x1400063e1  mov     rcx, rdi; lpCriticalSection
0x1400063e4  call    cs:__imp_LeaveCriticalSection
0x1400063ea  mov     rcx, [r14]; hObject
0x1400063ed  lea     rdx, [rcx+1]
0x1400063f1  cmp     rdx, 1
0x1400063f5  jbe     short loc_1400063FD
0x1400063f7  call    cs:__imp_CloseHandle
0x1400063fd  mov     rcx, [rsi]; hObject
0x140006400  lea     rax, [rcx+1]
0x140006404  cmp     rax, 1
0x140006408  jbe     short loc_140006410
0x14000640a  call    cs:__imp_CloseHandle
0x140006410  mov     eax, ebx
0x140006412  add     rsp, 38h
0x140006416  pop     r15
0x140006418  pop     r14
0x14000641a  pop     rdi
0x14000641b  pop     rsi
0x14000641c  pop     rbp
0x14000641d  pop     rbx
0x14000641e  retn
```
