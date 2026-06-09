# Windows::UI::Core::CDispatcher::RegisterThreadExitCallback(void)

- ea: `0x1800379f0`
- end: `0x180037adc`
- name: `?RegisterThreadExitCallback@CDispatcher@Core@UI@Windows@@AEAAXXZ`
- size: `236`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180037760`

## callees

- `0x1800379f0`
- `0x180050360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ab0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180037a7d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180037a53`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180037a53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180037a02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180037a02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037a12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180037a12`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180037a3c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180037a3c`

## string_xrefs

- `0x180037a9b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`
- `0x180037ac7`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\dispatcher.cpp`

## pseudocode

```c
void __fastcall Windows::UI::Core::CDispatcher::RegisterThreadExitCallback(HANDLE *pv)
{
  HANDLE CurrentProcess; // rbx
  HANDLE CurrentThread; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int LastError; // eax
  signed int v6; // eax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  if ( !DuplicateHandle(CurrentProcess, CurrentThread, CurrentProcess, pv + 29, 0, 0, 2u) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x6F7,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
      (const char *)(unsigned int)LastError,
      dwDesiredAccess);
  }
  ThreadpoolWait = CreateThreadpoolWait(Windows::UI::Core::CoreInputThreadContext::OnThreadExit, pv, 0);
  pv[30] = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x702,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\dispatcher.cpp",
      (const char *)(unsigned int)v6,
      dwDesiredAccess);
  }
  SetThreadpoolWait(ThreadpoolWait, pv[29], 0);
}

```

## disassembly

```asm
0x1800379f0  mov     [rsp+arg_0], rbx
0x1800379f5  mov     [rsp+arg_8], rsi
0x1800379fa  push    rdi
0x1800379fb  sub     rsp, 40h
0x1800379ff  mov     rdi, rcx
0x180037a02  call    cs:__imp_GetCurrentProcess
0x180037a08  mov     rbx, rax
0x180037a0b  lea     rsi, [rdi+0E8h]
0x180037a12  call    cs:__imp_GetCurrentThread
0x180037a18  mov     [rsp+48h+dwOptions], 2; dwOptions
0x180037a20  mov     r9, rsi; lpTargetHandle
0x180037a23  mov     rdx, rax; hSourceHandle
0x180037a26  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x180037a2e  mov     r8, rbx; hTargetProcessHandle
0x180037a31  mov     [rsp+48h+dwDesiredAccess], 0; int
0x180037a39  mov     rcx, rbx; hSourceProcessHandle
0x180037a3c  call    cs:__imp_DuplicateHandle
0x180037a42  test    eax, eax
0x180037a44  jz      short loc_180037A84
0x180037a46  xor     r8d, r8d; pcbe
0x180037a49  lea     rcx, ?OnThreadExit@CoreInputThreadContext@Core@UI@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180037a50  mov     rdx, rdi; pv
0x180037a53  call    cs:__imp_CreateThreadpoolWait
0x180037a59  mov     [rdi+0F0h], rax
0x180037a60  test    rax, rax
0x180037a63  jz      short loc_180037AB0
0x180037a65  mov     rdx, [rsi]
0x180037a68  xor     r8d, r8d
0x180037a6b  mov     rcx, rax
0x180037a6e  mov     rbx, [rsp+48h+arg_0]
0x180037a73  mov     rsi, [rsp+48h+arg_8]
0x180037a78  add     rsp, 40h
0x180037a7c  pop     rdi
0x180037a7d  jmp     cs:__imp_SetThreadpoolWait
0x180037a84  call    cs:__imp_GetLastError
0x180037a8a  test    eax, eax
0x180037a8c  jle     short loc_180037A96
0x180037a8e  movzx   eax, ax
0x180037a91  or      eax, 80070000h
0x180037a96  mov     rcx, [rsp+48h]; this
0x180037a9b  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180037aa2  mov     r9d, eax; char *
0x180037aa5  mov     edx, 6F7h; void *
0x180037aaa  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180037ab0  call    cs:__imp_GetLastError
0x180037ab6  test    eax, eax
0x180037ab8  jle     short loc_180037AC2
0x180037aba  movzx   eax, ax
0x180037abd  or      eax, 80070000h
0x180037ac2  mov     rcx, [rsp+48h]; this
0x180037ac7  lea     r8, aOnecoreuapWind_14; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180037ace  mov     r9d, eax; char *
0x180037ad1  mov     edx, 702h; void *
0x180037ad6  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
