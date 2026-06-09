# WJWorkplaceJoinTaskStateCallback

- ea: `0x18002bfa0`
- end: `0x18002c13a`
- name: `WJWorkplaceJoinTaskStateCallback`
- size: `410`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18002ba14`
- `0x18002bfa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bfd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bfd1`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18002bfde`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18002bfde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c0da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c117`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c0da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c117`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002bfc7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c029`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c079`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c0b2`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c106`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002bfc7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c029`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c079`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c0b2`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c106`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002c133`

## string_xrefs

- `0x18002bfb0`: `WJWorkplaceJoinTaskStateCallback`
- `0x18002c016`: `AutoJoinSvc/%s: Retrying %s task "%s\%s"`
- `0x18002c072`: `AutoJoinSvc/%s: Successfully %s task "%s\%s". Canceling the thread pool timer.`
- `0x18002c0ab`: `AutoJoinSvc/%s: Failed to %s task "%s\%s" with status 0x%08x. Number of retries remained: %d.`
- `0x18002c0e9`: `AutoJoinSvc/%s: Max number of retries reached. Canceling the thread pool timer to %s task "%s\%s".`

## pseudocode

```c
void __fastcall WJWorkplaceJoinTaskStateCallback(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_TIMER Timer)
{
  const wchar_t *v6; // rbx
  const wchar_t *v7; // r8
  int v8; // eax
  __int16 v9; // dx
  __int64 v10; // rcx
  const wchar_t *v11; // r8
  const wchar_t *v12; // r8
  struct _FILETIME pftDueTime; // [rsp+88h] [rbp+10h] BYREF

  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJWorkplaceJoinTaskStateCallback");
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 3));
  LeaveCriticalSectionWhenCallbackReturns(Instance, (PCRITICAL_SECTION)(Context + 3));
  v6 = L"enable";
  if ( *((int *)Context + 5) <= 0 )
    goto LABEL_19;
  v7 = L"enabling";
  if ( !*((_WORD *)Context + 8) )
    v7 = L"disabling";
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: Retrying %s task \"%s\\%s\"",
    L"WJWorkplaceJoinTaskStateCallback",
    v7,
    *Context,
    Context[1]);
  v8 = WJSetScheduledTaskState((OLECHAR *)*Context, (OLECHAR *)Context[1], *((_WORD *)Context + 8), 0);
  v9 = *((_WORD *)Context + 8);
  v10 = Context[1];
  if ( v8 >= 0 )
  {
    v11 = L"enabled";
    if ( !v9 )
      v11 = L"disabled";
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Successfully %s task \"%s\\%s\". Canceling the thread pool timer.",
      L"WJWorkplaceJoinTaskStateCallback",
      v11,
      *Context,
      Context[1]);
    *((_DWORD *)Context + 5) = 0;
LABEL_15:
    SetThreadpoolTimer(Timer, 0, 0, 0);
    goto LABEL_16;
  }
  --*((_DWORD *)Context + 5);
  v12 = L"enable";
  if ( !v9 )
    v12 = L"disable";
  DsrWriteAutoJoinSvcDebugEvent(
    L"AutoJoinSvc/%s: Failed to %s task \"%s\\%s\" with status 0x%08x. Number of retries remained: %d.",
    L"WJWorkplaceJoinTaskStateCallback",
    v12,
    *Context,
    v10,
    v8,
    *((_DWORD *)Context + 5));
  if ( *((int *)Context + 5) <= 0
    || (pftDueTime = (struct _FILETIME)-50000000LL,
        SetThreadpoolTimer(Timer, &pftDueTime, 0, 0),
        *((int *)Context + 5) <= 0) )
  {
LABEL_19:
    if ( !*((_WORD *)Context + 8) )
      v6 = L"disable";
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Max number of retries reached. Canceling the thread pool timer to %s task \"%s\\%s\".",
      L"WJWorkplaceJoinTaskStateCallback",
      v6,
      *Context,
      Context[1]);
    goto LABEL_15;
  }
LABEL_16:
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished", L"WJWorkplaceJoinTaskStateCallback");
}

```

## disassembly

```asm
0x18002bfa0  push    rbx
0x18002bfa2  push    rbp
0x18002bfa3  push    rsi
0x18002bfa4  push    rdi
0x18002bfa5  push    r14
0x18002bfa7  push    r15
0x18002bfa9  sub     rsp, 48h
0x18002bfad  mov     rsi, rdx
0x18002bfb0  lea     r14, aWjworkplacejoi_0; "WJWorkplaceJoinTaskStateCallback"
0x18002bfb7  mov     rdi, rcx
0x18002bfba  mov     rdx, r14
0x18002bfbd  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18002bfc4  mov     rbp, r8
0x18002bfc7  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002bfcd  lea     rcx, [rsi+18h]; lpCriticalSection
0x18002bfd1  call    cs:__imp_EnterCriticalSection
0x18002bfd7  lea     rdx, [rsi+18h]; pcs
0x18002bfdb  mov     rcx, rdi; pci
0x18002bfde  call    cs:__imp_LeaveCriticalSectionWhenCallbackReturns
0x18002bfe4  xor     edi, edi
0x18002bfe6  lea     r15, aDisable; "disable"
0x18002bfed  lea     rbx, aEnable; "enable"
0x18002bff4  cmp     [rsi+14h], edi
0x18002bff7  jle     loc_18002C0E5
0x18002bffd  cmp     [rsi+10h], di
0x18002c001  lea     rax, aDisabling; "disabling"
0x18002c008  mov     r9, [rsi]
0x18002c00b  lea     r8, aEnabling; "enabling"
0x18002c012  cmovz   r8, rax
0x18002c016  lea     rcx, aAutojoinsvcSRe; "AutoJoinSvc/%s: Retrying %s task \"%s\\"...
0x18002c01d  mov     rax, [rsi+8]
0x18002c021  mov     rdx, r14
0x18002c024  mov     [rsp+78h+var_58], rax
0x18002c029  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002c02f  movzx   r8d, word ptr [rsi+10h]
0x18002c034  xor     r9d, r9d
0x18002c037  mov     rdx, [rsi+8]; OLECHAR *
0x18002c03b  mov     rcx, [rsi]; psz
0x18002c03e  call    WJSetScheduledTaskState
0x18002c043  movzx   edx, word ptr [rsi+10h]
0x18002c047  mov     r9d, eax
0x18002c04a  mov     rcx, [rsi+8]
0x18002c04e  test    eax, eax
0x18002c050  js      short loc_18002C087
0x18002c052  mov     r9, [rsi]
0x18002c055  lea     rax, aDisabled; "disabled"
0x18002c05c  test    dx, dx
0x18002c05f  mov     [rsp+78h+var_58], rcx
0x18002c064  lea     r8, aEnabled; "enabled"
0x18002c06b  mov     rdx, r14
0x18002c06e  cmovz   r8, rax
0x18002c072  lea     rcx, aAutojoinsvcSSu_1; "AutoJoinSvc/%s: Successfully %s task \""...
0x18002c079  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002c07f  mov     [rsi+14h], edi
0x18002c082  jmp     loc_18002C10C
0x18002c087  dec     dword ptr [rsi+14h]
0x18002c08a  mov     r8, rbx
0x18002c08d  mov     eax, [rsi+14h]
0x18002c090  test    dx, dx
0x18002c093  mov     [rsp+78h+var_48], eax
0x18002c097  mov     rdx, r14
0x18002c09a  mov     [rsp+78h+var_50], r9d
0x18002c09f  cmovz   r8, r15
0x18002c0a3  mov     r9, [rsi]
0x18002c0a6  mov     [rsp+78h+var_58], rcx
0x18002c0ab  lea     rcx, aAutojoinsvcSFa_12; "AutoJoinSvc/%s: Failed to %s task \"%s"...
0x18002c0b2  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002c0b8  cmp     [rsi+14h], edi
0x18002c0bb  jle     short loc_18002C0E5
0x18002c0bd  xor     r9d, r9d; msWindowLength
0x18002c0c0  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18002c0cc  xor     r8d, r8d; msPeriod
0x18002c0cf  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18002c0d7  mov     rcx, rbp; pti
0x18002c0da  call    cs:__imp_SetThreadpoolTimer
0x18002c0e0  cmp     [rsi+14h], edi
0x18002c0e3  jg      short loc_18002C11D
0x18002c0e5  cmp     [rsi+10h], di
0x18002c0e9  lea     rcx, aAutojoinsvcSMa_1; "AutoJoinSvc/%s: Max number of retries r"...
0x18002c0f0  mov     rax, [rsi+8]
0x18002c0f4  mov     rdx, r14
0x18002c0f7  mov     r9, [rsi]
0x18002c0fa  cmovz   rbx, r15
0x18002c0fe  mov     r8, rbx
0x18002c101  mov     [rsp+78h+var_58], rax
0x18002c106  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002c10c  xor     r9d, r9d; msWindowLength
0x18002c10f  xor     r8d, r8d; msPeriod
0x18002c112  xor     edx, edx; pftDueTime
0x18002c114  mov     rcx, rbp; pti
0x18002c117  call    cs:__imp_SetThreadpoolTimer
0x18002c11d  mov     rdx, r14
0x18002c120  lea     rcx, aAutojoinsvcSFi; "AutoJoinSvc/%s: finished"
0x18002c127  add     rsp, 48h
0x18002c12b  pop     r15
0x18002c12d  pop     r14
0x18002c12f  pop     rdi
0x18002c130  pop     rsi
0x18002c131  pop     rbp
0x18002c132  pop     rbx
0x18002c133  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
