# WJRegistryKeyChangedCallback

- ea: `0x18001dee0`
- end: `0x18001e027`
- name: `WJRegistryKeyChangedCallback`
- size: `327`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18001dee0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001dfd5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001dfd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001df31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001df31`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18001df3e`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18001df3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001dfb5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001dfb5`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001dff2`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001dff2`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df08`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df1d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df5d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df79`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df9f`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df08`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df1d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df5d`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df79`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001df9f`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18001e020`

## string_xrefs

- `0x18001dfe5`: `AutoJoinSvc/%s: Failed to re-register change notification for %s registry key with status 0x%08x.`
- `0x18001deee`: `WJRegistryKeyChangedCallback`
- `0x18001df6e`: `AutoJoinSvc/%s: %s registry key changed.`
- `0x18001df65`: `AutoJoinSvc/%s: %s registry key change wait timed out.`
- `0x18001df92`: `AutoJoinSvc/%s: %s registry key callback failed with status 0x%08x.`

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
0x18001dee0  push    rbx
0x18001dee2  push    rbp
0x18001dee3  push    rsi
0x18001dee4  push    rdi
0x18001dee5  push    r14
0x18001dee7  sub     rsp, 30h
0x18001deeb  mov     rdi, rdx
0x18001deee  lea     r14, aWjregistrykeyc; "WJRegistryKeyChangedCallback"
0x18001def5  mov     rbx, rcx
0x18001def8  mov     rdx, r14
0x18001defb  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18001df02  mov     esi, r9d
0x18001df05  mov     rbp, r8
0x18001df08  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001df0e  test    rdi, rdi
0x18001df11  jnz     short loc_18001DF2D
0x18001df13  mov     rdx, r14
0x18001df16  lea     rcx, aAutojoinsvcSCo; "AutoJoinSvc/%s: Context is null"
0x18001df1d  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001df23  mov     ebx, 80070057h
0x18001df28  jmp     loc_18001E009
0x18001df2d  mov     rcx, [rdi+28h]; lpCriticalSection
0x18001df31  call    cs:__imp_EnterCriticalSection
0x18001df37  mov     rdx, [rdi+28h]; pcs
0x18001df3b  mov     rcx, rbx; pci
0x18001df3e  call    cs:__imp_LeaveCriticalSectionWhenCallbackReturns
0x18001df44  mov     rdx, r14
0x18001df47  test    esi, esi
0x18001df49  jz      short loc_18001DF6E
0x18001df4b  cmp     esi, 102h
0x18001df51  jz      short loc_18001DF65
0x18001df53  mov     r8d, esi
0x18001df56  lea     rcx, aAutojoinsvcSUn; "AutoJoinSvc/%s: Unexpected wait result:"...
0x18001df5d  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001df63  jmp     short loc_18001DF7F
0x18001df65  lea     rcx, aAutojoinsvcSSR_0; "AutoJoinSvc/%s: %s registry key change "...
0x18001df6c  jmp     short loc_18001DF75
0x18001df6e  lea     rcx, aAutojoinsvcSSR; "AutoJoinSvc/%s: %s registry key changed"...
0x18001df75  mov     r8, [rdi+20h]
0x18001df79  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001df7f  mov     rax, [rdi+30h]
0x18001df83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df88  mov     ebx, eax
0x18001df8a  test    eax, eax
0x18001df8c  jns     short loc_18001DFA5
0x18001df8e  mov     r8, [rdi+20h]
0x18001df92  lea     rcx, aAutojoinsvcSSR_1; "AutoJoinSvc/%s: %s registry key callbac"...
0x18001df99  mov     r9d, eax
0x18001df9c  mov     rdx, r14
0x18001df9f  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18001dfa5  cmp     qword ptr [rdi], 0
0x18001dfa9  jz      short loc_18001E009
0x18001dfab  mov     rdx, [rdi+8]; h
0x18001dfaf  xor     r8d, r8d; pftTimeout
0x18001dfb2  mov     rcx, rbp; pwa
0x18001dfb5  call    cs:__imp_SetThreadpoolWait
0x18001dfbb  test    esi, esi
0x18001dfbd  jnz     short loc_18001E009
0x18001dfbf  mov     r9, [rdi+8]; hEvent
0x18001dfc3  mov     r8d, [rdi+1Ch]; dwNotifyFilter
0x18001dfc7  mov     edx, [rdi+18h]; bWatchSubtree
0x18001dfca  mov     rcx, [rdi]; hKey
0x18001dfcd  mov     [rsp+58h+fAsynchronous], 1; fAsynchronous
0x18001dfd5  call    cs:__imp_RegNotifyChangeKeyValue
0x18001dfdb  mov     esi, eax
0x18001dfdd  test    eax, eax
0x18001dfdf  jz      short loc_18001E009
0x18001dfe1  mov     r8, [rdi+20h]
0x18001dfe5  lea     rcx, aAutojoinsvcSFa_20; "AutoJoinSvc/%s: Failed to re-register c"...
0x18001dfec  mov     r9d, eax
0x18001dfef  mov     rdx, r14
0x18001dff2  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18001dff8  test    esi, esi
0x18001dffa  jg      short loc_18001E000
0x18001dffc  mov     ebx, esi
0x18001dffe  jmp     short loc_18001E009
0x18001e000  movzx   ebx, si
0x18001e003  or      ebx, 80070000h
0x18001e009  mov     r8d, ebx
0x18001e00c  lea     rcx, aAutojoinsvcSFi_2; "AutoJoinSvc/%s: finished - hr: 0x%08x"
0x18001e013  mov     rdx, r14
0x18001e016  add     rsp, 30h
0x18001e01a  pop     r14
0x18001e01c  pop     rdi
0x18001e01d  pop     rsi
0x18001e01e  pop     rbp
0x18001e01f  pop     rbx
0x18001e020  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
