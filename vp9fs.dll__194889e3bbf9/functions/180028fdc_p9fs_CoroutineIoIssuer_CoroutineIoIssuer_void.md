# p9fs::CoroutineIoIssuer::CoroutineIoIssuer(void *)

- ea: `0x180028fdc`
- end: `0x1800290a9`
- name: `??0CoroutineIoIssuer@p9fs@@QEAA@PEAX@Z`
- size: `205`
- prototype: `__int64 __fastcall(PVOID pv, HANDLE FileHandle)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001e730`
- `0x1800200e0`
- `0x18002b190`
- `0x18002b720`

## callees

- `0x1800286fc`
- `0x180028fdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029043`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029025`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180029014`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x180029014`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18002903b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18002903b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180029032`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180029032`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x180029060`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x180029060`

## string_xrefs

- `0x180029085`: `onecore\vm\dv\storage\plan9\dll\windows\p9io.cpp`
- `0x180029097`: `onecore\vm\dv\storage\plan9\dll\windows\p9io.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PTP_IO *__fastcall p9fs::CoroutineIoIssuer::CoroutineIoIssuer(PTP_IO *pv, struct _TP_IO *FileHandle)
{
  PTP_IO ThreadpoolIo; // rsi
  const char *v5; // r9
  struct _TP_IO *v6; // rbp
  DWORD LastError; // ebx
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *pv = 0;
  pv[1] = FileHandle;
  ThreadpoolIo = CreateThreadpoolIo(FileHandle, p9fs::CoroutineIoIssuer::Callback, pv, 0);
  v6 = *pv;
  if ( *pv )
  {
    LastError = GetLastError();
    WaitForThreadpoolIoCallbacks(v6, 0);
    CloseThreadpoolIo(v6);
    SetLastError(LastError);
  }
  *pv = ThreadpoolIo;
  if ( !ThreadpoolIo )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9io.cpp",
      v5);
  if ( !SetFileCompletionNotificationModes(FileHandle, 3u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9io.cpp",
      v8);
  return pv;
}

```

## disassembly

```asm
0x180028fdc  mov     [rsp+arg_8], rbx
0x180028fe1  mov     [rsp+arg_10], rbp
0x180028fe6  mov     [rsp+arg_0], rcx
0x180028feb  push    rsi
0x180028fec  push    rdi
0x180028fed  push    r14
0x180028fef  sub     rsp, 20h
0x180028ff3  mov     r14, rdx
0x180028ff6  mov     rdi, rcx
0x180028ff9  mov     qword ptr [rcx], 0
0x180029000  mov     [rcx+8], rdx
0x180029004  xor     r9d, r9d; pcbe
0x180029007  mov     r8, rcx; pv
0x18002900a  lea     rdx, ?Callback@CoroutineIoIssuer@p9fs@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x180029011  mov     rcx, r14; fl
0x180029014  call    cs:__imp_CreateThreadpoolIo
0x18002901a  mov     rsi, rax
0x18002901d  mov     rbp, [rdi]
0x180029020  test    rbp, rbp
0x180029023  jz      short loc_180029049
0x180029025  call    cs:__imp_GetLastError
0x18002902b  mov     ebx, eax
0x18002902d  xor     edx, edx; fCancelPendingCallbacks
0x18002902f  mov     rcx, rbp; pio
0x180029032  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180029038  mov     rcx, rbp; pio
0x18002903b  call    cs:__imp_CloseThreadpoolIo
0x180029041  mov     ecx, ebx; dwErrCode
0x180029043  call    cs:__imp_SetLastError
0x180029049  mov     [rdi], rsi
0x18002904c  test    rsi, rsi
0x18002904f  setz    al
0x180029052  mov     rcx, [rsp+38h]; this
0x180029057  test    al, al
0x180029059  jnz     short loc_180029097
0x18002905b  mov     dl, 3; Flags
0x18002905d  mov     rcx, r14; FileHandle
0x180029060  call    cs:__imp_SetFileCompletionNotificationModes
0x180029066  mov     rcx, [rsp+38h]; this
0x18002906b  test    eax, eax
0x18002906d  jz      short loc_180029085
0x18002906f  mov     rax, rdi
0x180029072  mov     rbx, [rsp+38h+arg_8]
0x180029077  mov     rbp, [rsp+38h+arg_10]
0x18002907c  add     rsp, 20h
0x180029080  pop     r14
0x180029082  pop     rdi
0x180029083  pop     rsi
0x180029084  retn
0x180029085  lea     r8, aOnecoreVmDvSto_4; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002908c  mov     edx, 0Ch; void *
0x180029091  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180029097  lea     r8, aOnecoreVmDvSto_4; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002909e  mov     edx, 0Bh; void *
0x1800290a3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
