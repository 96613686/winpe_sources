# WJRegistryKeyChangedCallback

- ea: `0x18001f650`
- end: `0x18001f7d8`
- name: `WJRegistryKeyChangedCallback`
- size: `392`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18001f650`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001f775`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001f775`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f6ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f6ad`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18001f6c0`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18001f6c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f74f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f74f`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f798`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001f798`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f678`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f693`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f6e5`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f707`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f733`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f678`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f693`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f6e5`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f707`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f733`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001f7cc`

## string_xrefs

- `0x18001f78b`: `AutoJoinSvc/%s: Failed to re-register change notification for %s registry key with status 0x%08x.`
- `0x18001f65e`: `WJRegistryKeyChangedCallback`
- `0x18001f6fc`: `AutoJoinSvc/%s: %s registry key changed.`
- `0x18001f6f3`: `AutoJoinSvc/%s: %s registry key change wait timed out.`
- `0x18001f726`: `AutoJoinSvc/%s: %s registry key callback failed with status 0x%08x.`

## pseudocode

```c
void __fastcall WJRegistryKeyChangedCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // eax
  int v11; // esi

  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJRegistryKeyChangedCallback");
  if ( Context )
  {
    EnterCriticalSection(*((LPCRITICAL_SECTION *)Context + 5));
    LeaveCriticalSectionWhenCallbackReturns(Instance, *((PCRITICAL_SECTION *)Context + 5));
    if ( WaitResult )
    {
      if ( WaitResult == 258 )
        DsrWriteAutoJoinSvcDebugEvent(
          L"AutoJoinSvc/%s: %s registry key change wait timed out.",
          L"WJRegistryKeyChangedCallback",
          *((_QWORD *)Context + 4));
      else
        DsrWriteAutoJoinSvcDebugEvent(
          L"AutoJoinSvc/%s: Unexpected wait result: %lu.",
          L"WJRegistryKeyChangedCallback",
          WaitResult);
    }
    else
    {
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: %s registry key changed.",
        L"WJRegistryKeyChangedCallback",
        *((_QWORD *)Context + 4));
    }
    v9 = (*((__int64 (**)(void))Context + 6))();
    v8 = v9;
    if ( v9 < 0 )
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: %s registry key callback failed with status 0x%08x.",
        L"WJRegistryKeyChangedCallback",
        *((_QWORD *)Context + 4),
        (unsigned int)v9);
    if ( *(_QWORD *)Context )
    {
      SetThreadpoolWait(Wait, *((HANDLE *)Context + 1), 0);
      if ( !WaitResult )
      {
        v10 = RegNotifyChangeKeyValue(
                *(HKEY *)Context,
                *((_DWORD *)Context + 6),
                *((_DWORD *)Context + 7),
                *((HANDLE *)Context + 1),
                1);
        v11 = v10;
        if ( v10 )
        {
          DsrWriteAutoJoinSvcAdminEvent(
            L"AutoJoinSvc/%s: Failed to re-register change notification for %s registry key with status 0x%08x.",
            L"WJRegistryKeyChangedCallback",
            *((_QWORD *)Context + 4),
            v10);
          if ( v11 > 0 )
            v8 = (unsigned __int16)v11 | 0x80070000;
          else
            v8 = v11;
        }
      }
    }
  }
  else
  {
    DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: Context is null", L"WJRegistryKeyChangedCallback");
    v8 = -2147024809;
  }
  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished - hr: 0x%08x", L"WJRegistryKeyChangedCallback", v8);
}

```

## disassembly

```asm
0x18001f650  push    rbx
0x18001f652  push    rbp
0x18001f653  push    rsi
0x18001f654  push    rdi
0x18001f655  push    r14
0x18001f657  sub     rsp, 30h
0x18001f65b  mov     rdi, rdx
0x18001f65e  lea     r14, aWjregistrykeyc; "WJRegistryKeyChangedCallback"
0x18001f665  mov     rbx, rcx
0x18001f668  mov     rdx, r14
0x18001f66b  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001f672  mov     esi, r9d
0x18001f675  mov     rbp, r8
0x18001f678  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001f67f  nop     dword ptr [rax+rax+00h]
0x18001f684  test    rdi, rdi
0x18001f687  jnz     short loc_18001F6A9
0x18001f689  mov     rdx, r14
0x18001f68c  lea     rcx, aAutojoinsvcSCo; "AutoJoinSvc/%s: Context is null"
0x18001f693  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001f69a  nop     dword ptr [rax+rax+00h]
0x18001f69f  mov     ebx, 80070057h
0x18001f6a4  jmp     loc_18001F7B5
0x18001f6a9  mov     rcx, [rdi+28h]; lpCriticalSection
0x18001f6ad  call    cs:__imp_EnterCriticalSection
0x18001f6b4  nop     dword ptr [rax+rax+00h]
0x18001f6b9  mov     rdx, [rdi+28h]; pcs
0x18001f6bd  mov     rcx, rbx; pci
0x18001f6c0  call    cs:__imp_LeaveCriticalSectionWhenCallbackReturns
0x18001f6c7  nop     dword ptr [rax+rax+00h]
0x18001f6cc  mov     rdx, r14
0x18001f6cf  test    esi, esi
0x18001f6d1  jz      short loc_18001F6FC
0x18001f6d3  cmp     esi, 102h
0x18001f6d9  jz      short loc_18001F6F3
0x18001f6db  mov     r8d, esi
0x18001f6de  lea     rcx, aAutojoinsvcSUn; "AutoJoinSvc/%s: Unexpected wait result:"...
0x18001f6e5  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001f6ec  nop     dword ptr [rax+rax+00h]
0x18001f6f1  jmp     short loc_18001F713
0x18001f6f3  lea     rcx, aAutojoinsvcSSR_0; "AutoJoinSvc/%s: %s registry key change "...
0x18001f6fa  jmp     short loc_18001F703
0x18001f6fc  lea     rcx, aAutojoinsvcSSR; "AutoJoinSvc/%s: %s registry key changed"...
0x18001f703  mov     r8, [rdi+20h]
0x18001f707  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001f70e  nop     dword ptr [rax+rax+00h]
0x18001f713  mov     rax, [rdi+30h]
0x18001f717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f71c  mov     ebx, eax
0x18001f71e  test    eax, eax
0x18001f720  jns     short loc_18001F73F
0x18001f722  mov     r8, [rdi+20h]
0x18001f726  lea     rcx, aAutojoinsvcSSR_1; "AutoJoinSvc/%s: %s registry key callbac"...
0x18001f72d  mov     r9d, eax
0x18001f730  mov     rdx, r14
0x18001f733  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001f73a  nop     dword ptr [rax+rax+00h]
0x18001f73f  cmp     qword ptr [rdi], 0
0x18001f743  jz      short loc_18001F7B5
0x18001f745  mov     rdx, [rdi+8]; h
0x18001f749  xor     r8d, r8d; pftTimeout
0x18001f74c  mov     rcx, rbp; pwa
0x18001f74f  call    cs:__imp_SetThreadpoolWait
0x18001f756  nop     dword ptr [rax+rax+00h]
0x18001f75b  test    esi, esi
0x18001f75d  jnz     short loc_18001F7B5
0x18001f75f  mov     r9, [rdi+8]; hEvent
0x18001f763  mov     r8d, [rdi+1Ch]; dwNotifyFilter
0x18001f767  mov     edx, [rdi+18h]; bWatchSubtree
0x18001f76a  mov     rcx, [rdi]; hKey
0x18001f76d  mov     [rsp+58h+fAsynchronous], 1; fAsynchronous
0x18001f775  call    cs:__imp_RegNotifyChangeKeyValue
0x18001f77c  nop     dword ptr [rax+rax+00h]
0x18001f781  mov     esi, eax
0x18001f783  test    eax, eax
0x18001f785  jz      short loc_18001F7B5
0x18001f787  mov     r8, [rdi+20h]
0x18001f78b  lea     rcx, aAutojoinsvcSFa_20; "AutoJoinSvc/%s: Failed to re-register c"...
0x18001f792  mov     r9d, eax
0x18001f795  mov     rdx, r14
0x18001f798  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001f79f  nop     dword ptr [rax+rax+00h]
0x18001f7a4  test    esi, esi
0x18001f7a6  jg      short loc_18001F7AC
0x18001f7a8  mov     ebx, esi
0x18001f7aa  jmp     short loc_18001F7B5
0x18001f7ac  movzx   ebx, si
0x18001f7af  or      ebx, 80070000h
0x18001f7b5  mov     r8d, ebx
0x18001f7b8  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001f7bf  mov     rdx, r14
0x18001f7c2  add     rsp, 30h
0x18001f7c6  pop     r14
0x18001f7c8  pop     rdi
0x18001f7c9  pop     rsi
0x18001f7ca  pop     rbp
0x18001f7cb  pop     rbx
0x18001f7cc  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
