# WJWorkplaceJoinTaskStateCallback

- ea: `0x18002e790`
- end: `0x18002e965`
- name: `WJWorkplaceJoinTaskStateCallback`
- size: `469`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18002e16c`
- `0x18002e790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e7c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e7c7`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18002e7da`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18002e7da`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e8ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e937`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e8ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e937`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e7b7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e82b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e881`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e8c0`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e920`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e7b7`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e82b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e881`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e8c0`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e920`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002e959`

## string_xrefs

- `0x18002e7a0`: `WJWorkplaceJoinTaskStateCallback`
- `0x18002e818`: `AutoJoinSvc/%s: Retrying %s task "%s\%s"`
- `0x18002e87a`: `AutoJoinSvc/%s: Successfully %s task "%s\%s". Canceling the thread pool timer.`
- `0x18002e8b9`: `AutoJoinSvc/%s: Failed to %s task "%s\%s" with status 0x%08x. Number of retries remained: %d.`
- `0x18002e903`: `AutoJoinSvc/%s: Max number of retries reached. Canceling the thread pool timer to %s task "%s\%s".`

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
0x18002e790  push    rbx
0x18002e792  push    rbp
0x18002e793  push    rsi
0x18002e794  push    rdi
0x18002e795  push    r14
0x18002e797  push    r15
0x18002e799  sub     rsp, 48h
0x18002e79d  mov     rsi, rdx
0x18002e7a0  lea     r14, aWjworkplacejoi_0; "WJWorkplaceJoinTaskStateCallback"
0x18002e7a7  mov     rdi, rcx
0x18002e7aa  mov     rdx, r14
0x18002e7ad  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18002e7b4  mov     rbp, r8
0x18002e7b7  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e7be  nop     dword ptr [rax+rax+00h]
0x18002e7c3  lea     rcx, [rsi+18h]; lpCriticalSection
0x18002e7c7  call    cs:__imp_EnterCriticalSection
0x18002e7ce  nop     dword ptr [rax+rax+00h]
0x18002e7d3  lea     rdx, [rsi+18h]; pcs
0x18002e7d7  mov     rcx, rdi; pci
0x18002e7da  call    cs:__imp_LeaveCriticalSectionWhenCallbackReturns
0x18002e7e1  nop     dword ptr [rax+rax+00h]
0x18002e7e6  xor     edi, edi
0x18002e7e8  lea     r15, aDisable; "disable"
0x18002e7ef  lea     rbx, aEnable; "enable"
0x18002e7f6  cmp     [rsi+14h], edi
0x18002e7f9  jle     loc_18002E8FF
0x18002e7ff  cmp     [rsi+10h], di
0x18002e803  lea     rax, aDisabling; "disabling"
0x18002e80a  mov     r9, [rsi]
0x18002e80d  lea     r8, aEnabling; "enabling"
0x18002e814  cmovz   r8, rax
0x18002e818  lea     rcx, aAutojoinsvcSRe; "AutoJoinSvc/%s: Retrying %s task \"%s\\"...
0x18002e81f  mov     rax, [rsi+8]
0x18002e823  mov     rdx, r14
0x18002e826  mov     [rsp+78h+var_58], rax
0x18002e82b  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e832  nop     dword ptr [rax+rax+00h]
0x18002e837  movzx   r8d, word ptr [rsi+10h]
0x18002e83c  xor     r9d, r9d
0x18002e83f  mov     rdx, [rsi+8]; OLECHAR *
0x18002e843  mov     rcx, [rsi]; psz
0x18002e846  call    WJSetScheduledTaskState
0x18002e84b  movzx   edx, word ptr [rsi+10h]
0x18002e84f  mov     r9d, eax
0x18002e852  mov     rcx, [rsi+8]
0x18002e856  test    eax, eax
0x18002e858  js      short loc_18002E895
0x18002e85a  mov     r9, [rsi]
0x18002e85d  lea     rax, aDisabled; "disabled"
0x18002e864  test    dx, dx
0x18002e867  mov     [rsp+78h+var_58], rcx
0x18002e86c  lea     r8, aEnabled; "enabled"
0x18002e873  mov     rdx, r14
0x18002e876  cmovz   r8, rax
0x18002e87a  lea     rcx, aAutojoinsvcSSu_1; "AutoJoinSvc/%s: Successfully %s task \""...
0x18002e881  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e888  nop     dword ptr [rax+rax+00h]
0x18002e88d  mov     [rsi+14h], edi
0x18002e890  jmp     loc_18002E92C
0x18002e895  dec     dword ptr [rsi+14h]
0x18002e898  mov     r8, rbx
0x18002e89b  mov     eax, [rsi+14h]
0x18002e89e  test    dx, dx
0x18002e8a1  mov     [rsp+78h+var_48], eax
0x18002e8a5  mov     rdx, r14
0x18002e8a8  mov     [rsp+78h+var_50], r9d
0x18002e8ad  cmovz   r8, r15
0x18002e8b1  mov     r9, [rsi]
0x18002e8b4  mov     [rsp+78h+var_58], rcx
0x18002e8b9  lea     rcx, aAutojoinsvcSFa_12; "AutoJoinSvc/%s: Failed to %s task \"%s"...
0x18002e8c0  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e8c7  nop     dword ptr [rax+rax+00h]
0x18002e8cc  cmp     [rsi+14h], edi
0x18002e8cf  jle     short loc_18002E8FF
0x18002e8d1  xor     r9d, r9d; msWindowLength
0x18002e8d4  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18002e8e0  xor     r8d, r8d; msPeriod
0x18002e8e3  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18002e8eb  mov     rcx, rbp; pti
0x18002e8ee  call    cs:__imp_SetThreadpoolTimer
0x18002e8f5  nop     dword ptr [rax+rax+00h]
0x18002e8fa  cmp     [rsi+14h], edi
0x18002e8fd  jg      short loc_18002E943
0x18002e8ff  cmp     [rsi+10h], di
0x18002e903  lea     rcx, aAutojoinsvcSMa_1; "AutoJoinSvc/%s: Max number of retries r"...
0x18002e90a  mov     rax, [rsi+8]
0x18002e90e  mov     rdx, r14
0x18002e911  mov     r9, [rsi]
0x18002e914  cmovz   rbx, r15
0x18002e918  mov     r8, rbx
0x18002e91b  mov     [rsp+78h+var_58], rax
0x18002e920  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002e927  nop     dword ptr [rax+rax+00h]
0x18002e92c  xor     r9d, r9d; msWindowLength
0x18002e92f  xor     r8d, r8d; msPeriod
0x18002e932  xor     edx, edx; pftDueTime
0x18002e934  mov     rcx, rbp; pti
0x18002e937  call    cs:__imp_SetThreadpoolTimer
0x18002e93e  nop     dword ptr [rax+rax+00h]
0x18002e943  mov     rdx, r14
0x18002e946  lea     rcx, aAutojoinsvcSFi; "AutoJoinSvc/%s: finished"
0x18002e94d  add     rsp, 48h
0x18002e951  pop     r15
0x18002e953  pop     r14
0x18002e955  pop     rdi
0x18002e956  pop     rsi
0x18002e957  pop     rbp
0x18002e958  pop     rbx
0x18002e959  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
