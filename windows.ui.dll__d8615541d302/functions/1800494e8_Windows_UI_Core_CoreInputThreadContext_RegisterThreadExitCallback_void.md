# Windows::UI::Core::CoreInputThreadContext::RegisterThreadExitCallback(void)

- ea: `0x1800494e8`
- end: `0x1800495cc`
- name: `?RegisterThreadExitCallback@CoreInputThreadContext@Core@UI@Windows@@AEAAXXZ`
- size: `228`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180049450`

## callees

- `0x1800494e8`
- `0x180050360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049580`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800495c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180049571`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180049571`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800494fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800494fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180049503`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180049503`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004952e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004952e`

## string_xrefs

- `0x18004954f`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\inputthreadcontext.cpp`
- `0x180049597`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\inputthreadcontext.cpp`

## pseudocode

```c
void __fastcall Windows::UI::Core::CoreInputThreadContext::RegisterThreadExitCallback(HANDLE *pv)
{
  HANDLE CurrentProcess; // rbx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int v6; // eax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  if ( !DuplicateHandle(CurrentProcess, CurrentThread, CurrentProcess, pv + 5, 0, 0, 2u) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\inputthreadcontext.cpp",
      (const char *)(unsigned int)LastError,
      dwDesiredAccess);
  }
  ThreadpoolWait = CreateThreadpoolWait(Windows::UI::Core::CoreInputThreadContext::OnThreadExit, pv, 0);
  pv[6] = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\inputthreadcontext.cpp",
      (const char *)(unsigned int)v6,
      dwDesiredAccess);
  }
  SetThreadpoolWait(ThreadpoolWait, pv[5], 0);
}

```

## disassembly

```asm
0x1800494e8  mov     [rsp+arg_0], rbx
0x1800494ed  mov     [rsp+arg_8], rsi
0x1800494f2  push    rdi
0x1800494f3  sub     rsp, 40h
0x1800494f7  mov     rdi, rcx
0x1800494fa  call    cs:__imp_GetCurrentProcess
0x180049500  mov     rbx, rax
0x180049503  call    cs:__imp_GetCurrentThread
0x180049509  mov     [rsp+48h+dwOptions], 2; dwOptions
0x180049511  lea     r9, [rdi+28h]; lpTargetHandle
0x180049515  mov     rdx, rax; hSourceHandle
0x180049518  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x180049520  mov     r8, rbx; hTargetProcessHandle
0x180049523  mov     [rsp+48h+dwDesiredAccess], 0; int
0x18004952b  mov     rcx, rbx; hSourceProcessHandle
0x18004952e  call    cs:__imp_DuplicateHandle
0x180049534  test    eax, eax
0x180049536  jnz     short loc_180049564
0x180049538  call    cs:__imp_GetLastError
0x18004953e  test    eax, eax
0x180049540  jle     short loc_18004954A
0x180049542  movzx   eax, ax
0x180049545  or      eax, 80070000h
0x18004954a  mov     rcx, [rsp+48h]; this
0x18004954f  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180049556  mov     r9d, eax; char *
0x180049559  mov     edx, 16Dh; void *
0x18004955e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180049564  xor     r8d, r8d; pcbe
0x180049567  lea     rcx, ?OnThreadExit@CoreInputThreadContext@Core@UI@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18004956e  mov     rdx, rdi; pv
0x180049571  call    cs:__imp_CreateThreadpoolWait
0x180049577  mov     [rdi+30h], rax
0x18004957b  test    rax, rax
0x18004957e  jnz     short loc_1800495AC
0x180049580  call    cs:__imp_GetLastError
0x180049586  test    eax, eax
0x180049588  jle     short loc_180049592
0x18004958a  movzx   eax, ax
0x18004958d  or      eax, 80070000h
0x180049592  mov     rcx, [rsp+48h]; this
0x180049597  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004959e  mov     r9d, eax; char *
0x1800495a1  mov     edx, 178h; void *
0x1800495a6  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800495ac  mov     rdx, [rdi+28h]
0x1800495b0  xor     r8d, r8d
0x1800495b3  mov     rcx, rax
0x1800495b6  mov     rbx, [rsp+48h+arg_0]
0x1800495bb  mov     rsi, [rsp+48h+arg_8]
0x1800495c0  add     rsp, 40h
0x1800495c4  pop     rdi
0x1800495c5  jmp     cs:__imp_SetThreadpoolWait
```
