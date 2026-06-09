# WJCloseSetTaskStateRetryTimer

- ea: `0x18002d9dc`
- end: `0x18002da93`
- name: `WJCloseSetTaskStateRetryTimer`
- size: `183`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001eb30`
- `0x18001f3f0`
- `0x18002e16c`
- `0x18002e6ac`

## callees

- `0x18002d9dc`
- `0x18002da9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002da4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002da4c`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002da2f`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002da7d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002da2f`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002da7d`

## string_xrefs

- `0x18002da15`: `WJCloseSetTaskStateRetryTimer`
- `0x18002da5c`: `WJCloseSetTaskStateRetryTimer`
- `0x18002da28`: `AutoJoinSvc/%s: Canceling thread pool timer to %s task "%s\%s".`
- `0x18002da67`: `AutoJoinSvc/%s: Thread pool timer to %s task "%s\%s" is cancelled.`

## pseudocode

```c
__int64 __fastcall WJCloseSetTaskStateRetryTimer(_QWORD *a1)
{
  const wchar_t *v2; // rbx
  const wchar_t *v3; // r8
  __int64 result; // rax

  if ( a1 && a1[8] )
  {
    v2 = L"enable";
    v3 = L"enable";
    if ( !*((_WORD *)a1 + 8) )
      v3 = L"disable";
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Canceling thread pool timer to %s task \"%s\\%s\".",
      L"WJCloseSetTaskStateRetryTimer",
      v3,
      *a1,
      a1[1]);
    WJCloseThreadPoolTimer((PTP_TIMER)a1[8]);
    a1[8] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 3));
    if ( !*((_WORD *)a1 + 8) )
      v2 = L"disable";
    return DsrWriteAutoJoinSvcDebugEvent(
             L"AutoJoinSvc/%s: Thread pool timer to %s task \"%s\\%s\" is cancelled.",
             L"WJCloseSetTaskStateRetryTimer",
             v2,
             *a1,
             a1[1]);
  }
  return result;
}

```

## disassembly

```asm
0x18002d9dc  test    rcx, rcx
0x18002d9df  jz      locret_18002DA91
0x18002d9e5  push    rbx
0x18002d9e6  push    rbp
0x18002d9e7  push    rsi
0x18002d9e8  push    rdi
0x18002d9e9  sub     rsp, 38h
0x18002d9ed  xor     ebp, ebp
0x18002d9ef  mov     rdi, rcx
0x18002d9f2  cmp     [rcx+40h], rbp
0x18002d9f6  jz      loc_18002DA89
0x18002d9fc  cmp     [rcx+10h], bp
0x18002da00  lea     rbx, aEnable; "enable"
0x18002da07  mov     rax, [rcx+8]
0x18002da0b  lea     rsi, aDisable; "disable"
0x18002da12  mov     r9, [rcx]
0x18002da15  lea     rdx, aWjclosesettask; "WJCloseSetTaskStateRetryTimer"
0x18002da1c  mov     r8, rbx
0x18002da1f  mov     [rsp+58h+var_38], rax
0x18002da24  cmovz   r8, rsi
0x18002da28  lea     rcx, aAutojoinsvcSCa; "AutoJoinSvc/%s: Canceling thread pool t"...
0x18002da2f  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002da36  nop     dword ptr [rax+rax+00h]
0x18002da3b  mov     rcx, [rdi+40h]; pti
0x18002da3f  call    WJCloseThreadPoolTimer
0x18002da44  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002da48  mov     [rdi+40h], rbp
0x18002da4c  call    cs:__imp_DeleteCriticalSection
0x18002da53  nop     dword ptr [rax+rax+00h]
0x18002da58  cmp     [rdi+10h], bp
0x18002da5c  lea     rdx, aWjclosesettask; "WJCloseSetTaskStateRetryTimer"
0x18002da63  mov     rax, [rdi+8]
0x18002da67  lea     rcx, aAutojoinsvcSTh_0; "AutoJoinSvc/%s: Thread pool timer to %s"...
0x18002da6e  mov     r9, [rdi]
0x18002da71  cmovz   rbx, rsi
0x18002da75  mov     r8, rbx
0x18002da78  mov     [rsp+58h+var_38], rax
0x18002da7d  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002da84  nop     dword ptr [rax+rax+00h]
0x18002da89  add     rsp, 38h
0x18002da8d  pop     rdi
0x18002da8e  pop     rsi
0x18002da8f  pop     rbp
0x18002da90  pop     rbx
0x18002da91  retn
```
