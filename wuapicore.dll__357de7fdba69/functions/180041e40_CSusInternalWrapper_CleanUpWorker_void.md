# CSusInternalWrapper::CleanUpWorker(void *)

- ea: `0x180041e40`
- end: `0x1800421a0`
- name: `?CleanUpWorker@CSusInternalWrapper@@CAKPEAX@Z`
- size: `864`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180041b28`
- `0x180041e40`
- `0x180043dbc`
- `0x180090bc8`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041ea4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042055`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800420b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041ea4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042055`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800420b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041e85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042001`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004207a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041e85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042001`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004207a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800420ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800420ed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042172`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042172`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041fa4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041fa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800420fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800420fb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180041ee4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180041ee4`

## string_xrefs

- `0x180042125`: `Unable to notify caller for failure in resuming activities after self-update`
- `0x180041f54`: `Self-update completion event timed out.`
- `0x1800420c4`: `self-update/shutdown event ignored during object shutdown`
- `0x180041f63`: `Self-update completed.`
- `0x180041f2a`: `Unable to wait on self-update completion`
- `0x180041f80`: `Attempt to resume activities to the service.`
- `0x180042021`: `no need to reconnect completed download call`

## pseudocode

```c
__int64 __fastcall CSusInternalWrapper::CleanUpWorker(PVOID Parameter)
{
  struct ISusInternal *v1; // rsi
  __int64 v3; // rcx
  int v4; // r15d
  int v5; // r12d
  __int64 v6; // rax
  void *v7; // rbp
  DWORD v8; // eax
  DWORD v9; // ecx
  DWORD v10; // eax
  signed int LastError; // eax
  int v12; // ebx
  const wchar_t *v13; // rax
  int InnerSusInternal; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // r14d
  CSusInternalWrapper::CSusSearchCall *v18; // rcx
  int v19; // eax
  __int64 v21; // [rsp+20h] [rbp-58h]
  struct ISusInternal *v22; // [rsp+30h] [rbp-48h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-40h] BYREF

  v1 = 0;
  v3 = *((_QWORD *)Parameter + 18);
  v4 = 0;
  v5 = 0;
  v22 = 0;
  if ( v3 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 96));
    v6 = *((_QWORD *)Parameter + 18);
    v5 = *(_DWORD *)(v6 + 32);
    *(_DWORD *)(v6 + 32) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)Parameter + 18) + 96LL));
  }
  v7 = (void *)_InterlockedExchange64((volatile __int64 *)Parameter + 1, 0);
  if ( !v7 )
    goto LABEL_37;
  Handles[0] = *((HANDLE *)Parameter + 4);
  Handles[1] = v7;
  v8 = WaitForMultipleObjects(2u, Handles, 0, 0x13880u);
  v9 = v8;
  if ( !v8 )
  {
    WUTrace(0, 0, 0x10000, 5, 0, L"self-update/shutdown event ignored during object shutdown");
LABEL_37:
    v12 = -2145124341;
    goto LABEL_38;
  }
  v10 = v8 - 1;
  if ( v10 )
  {
    if ( v10 != 257 )
    {
      if ( v9 == -1 )
      {
        LastError = GetLastError();
        v12 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v12 = LastError;
        if ( v12 >= 0 )
          v12 = -2147418113;
      }
      else
      {
        v12 = -2145120257;
      }
      v13 = L"Unable to wait on self-update completion";
      goto LABEL_15;
    }
    WUTrace(0, 0, 0x10000, 5, 0, L"Self-update completion event timed out.");
  }
  else
  {
    WUTrace(0, 0, 0x10000, 4, 0, L"Self-update completed.");
  }
  WUTrace(0, 0, 0x10000, 5, 0, L"Attempt to resume activities to the service.");
  v12 = CoInitializeEx(0, 0);
  if ( v12 < 0 )
  {
    v13 = L"clean-up routine";
LABEL_15:
    LODWORD(v21) = v12;
    WUTrace(0, 0, 0x10000, 5, v21, v13);
    goto LABEL_38;
  }
  v4 = 1;
  InnerSusInternal = CSusInternalWrapper::GetInnerSusInternal((CSusInternalWrapper *)Parameter, &v22, 0, 1);
  v1 = v22;
  v12 = InnerSusInternal;
  if ( InnerSusInternal >= 0 )
  {
    v15 = *((_QWORD *)Parameter + 18);
    if ( !v15 )
      goto LABEL_35;
    if ( *((_DWORD *)Parameter + 34) != 3
      || ((EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 96)), v16 = *((_QWORD *)Parameter + 18),
                                                                 *(_DWORD *)(v16 + 28))
       || *(_DWORD *)(v16 + 24)
        ? (WUTrace(0, 0, 0x10000, 5, 0, L"no need to reconnect completed download call"), v12 = 0)
        : (v12 = -2145124325),
          LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)Parameter + 18) + 96LL)),
          v12 >= 0) )
    {
      v17 = 0;
      if ( *((_DWORD *)Parameter + 34) == 2
        && (EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)Parameter + 18) + 96LL)),
            v18 = (CSusInternalWrapper::CSusSearchCall *)*((_QWORD *)Parameter + 18),
            v17 = 1,
            !*((_DWORD *)v18 + 7))
        && !*((_DWORD *)v18 + 6)
        && (v12 = CSusInternalWrapper::CSusSearchCall::Restart(v18, v1), v12 < 0)
        || (v12 = 0, v17) )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)Parameter + 18) + 96LL));
      }
      if ( v12 >= 0 )
LABEL_35:
        v12 = 0;
    }
  }
LABEL_38:
  SetEvent(*((HANDLE *)Parameter + 2));
  if ( v7 )
    CloseHandle(v7);
  if ( v5 )
  {
    if ( v12 < 0 )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)Parameter + 18) + 32LL))(
              *((_QWORD *)Parameter + 18),
              (unsigned int)v12);
      if ( v19 < 0 )
      {
        LODWORD(v21) = v19;
        WUTrace(0, 0, 0x10000, 5, v21, L"Unable to notify caller for failure in resuming activities after self-update");
      }
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 18) + 16LL))(*((_QWORD *)Parameter + 18));
  }
  if ( v1 )
    (*(void (__fastcall **)(struct ISusInternal *))(*(_QWORD *)v1 + 16LL))(v1);
  if ( v4 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180041e40  mov     [rsp+arg_8], rbx
0x180041e45  mov     [rsp+arg_10], rbp
0x180041e4a  push    rsi
0x180041e4b  push    rdi
0x180041e4c  push    r12
0x180041e4e  push    r14
0x180041e50  push    r15
0x180041e52  sub     rsp, 50h
0x180041e56  mov     rax, cs:__security_cookie
0x180041e5d  xor     rax, rsp
0x180041e60  mov     [rsp+78h+var_30], rax
0x180041e65  xor     esi, esi
0x180041e67  mov     rdi, rcx
0x180041e6a  mov     rcx, [rcx+90h]
0x180041e71  xor     r15d, r15d
0x180041e74  xor     r12d, r12d
0x180041e77  mov     [rsp+78h+var_48], rsi
0x180041e7c  test    rcx, rcx
0x180041e7f  jz      short loc_180041EAA
0x180041e81  add     rcx, 60h ; '`'; lpCriticalSection
0x180041e85  call    cs:__imp_EnterCriticalSection
0x180041e8b  mov     rax, [rdi+90h]
0x180041e92  mov     r12d, [rax+20h]
0x180041e96  mov     [rax+20h], esi
0x180041e99  mov     rcx, [rdi+90h]
0x180041ea0  add     rcx, 60h ; '`'; lpCriticalSection
0x180041ea4  call    cs:__imp_LeaveCriticalSection
0x180041eaa  xor     ebp, ebp
0x180041eac  mov     ebx, 10000h
0x180041eb1  xchg    rbp, [rdi+8]
0x180041eb5  mov     r14d, 5
0x180041ebb  test    rbp, rbp
0x180041ebe  jz      loc_1800420E4
0x180041ec4  mov     rax, [rdi+20h]
0x180041ec8  lea     rdx, [rsp+78h+Handles]; lpHandles
0x180041ecd  mov     r9d, 13880h; dwMilliseconds
0x180041ed3  mov     [rsp+78h+Handles], rax
0x180041ed8  xor     r8d, r8d; bWaitAll
0x180041edb  mov     [rsp+78h+var_38], rbp
0x180041ee0  lea     ecx, [r14-3]; nCount
0x180041ee4  call    cs:__imp_WaitForMultipleObjects
0x180041eea  mov     ecx, eax
0x180041eec  test    eax, eax
0x180041eee  jz      loc_1800420C4
0x180041ef4  sub     eax, 1
0x180041ef7  jz      short loc_180041F5D
0x180041ef9  cmp     eax, 101h
0x180041efe  jz      short loc_180041F51
0x180041f00  cmp     ecx, 0FFFFFFFFh
0x180041f03  jnz     short loc_180041F25
0x180041f05  call    cs:__imp_GetLastError
0x180041f0b  movzx   ebx, ax
0x180041f0e  or      ebx, 80070000h
0x180041f14  test    eax, eax
0x180041f16  cmovle  ebx, eax
0x180041f19  mov     eax, 8000FFFFh
0x180041f1e  test    ebx, ebx
0x180041f20  cmovns  ebx, eax
0x180041f23  jmp     short loc_180041F2A
0x180041f25  mov     ebx, 80240FFFh
0x180041f2a  lea     rax, aUnableToWaitOn; "Unable to wait on self-update completio"...
0x180041f31  mov     [rsp+78h+var_50], rax
0x180041f36  mov     r9d, r14d
0x180041f39  xor     edx, edx
0x180041f3b  mov     dword ptr [rsp+78h+var_58], ebx
0x180041f3f  xor     ecx, ecx
0x180041f41  mov     r8d, 10000h
0x180041f47  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041f4c  jmp     loc_1800420E9
0x180041f51  mov     r9d, r14d
0x180041f54  lea     rax, aSelfUpdateComp; "Self-update completion event timed out."
0x180041f5b  jmp     short loc_180041F6A
0x180041f5d  mov     r9d, 4
0x180041f63  lea     rax, aSelfUpdateComp_0; "Self-update completed."
0x180041f6a  mov     [rsp+78h+var_50], rax
0x180041f6f  mov     r8d, ebx
0x180041f72  xor     edx, edx
0x180041f74  mov     [rsp+78h+var_58], rsi
0x180041f79  xor     ecx, ecx
0x180041f7b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041f80  lea     rax, aAttemptToResum; "Attempt to resume activities to the ser"...
0x180041f87  mov     r9d, r14d
0x180041f8a  mov     [rsp+78h+var_50], rax
0x180041f8f  mov     r8d, ebx
0x180041f92  xor     edx, edx
0x180041f94  mov     [rsp+78h+var_58], rsi
0x180041f99  xor     ecx, ecx
0x180041f9b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041fa0  xor     edx, edx; dwCoInit
0x180041fa2  xor     ecx, ecx; pvReserved
0x180041fa4  call    cs:__imp_CoInitializeEx
0x180041faa  mov     ebx, eax
0x180041fac  test    eax, eax
0x180041fae  jns     short loc_180041FBC
0x180041fb0  lea     rax, aCleanUpRoutine; "clean-up routine"
0x180041fb7  jmp     loc_180041F31
0x180041fbc  mov     r15d, 1
0x180041fc2  lea     rdx, [rsp+78h+var_48]; struct ISusInternal **
0x180041fc7  mov     r9d, r15d; int
0x180041fca  xor     r8d, r8d; int
0x180041fcd  mov     rcx, rdi; this
0x180041fd0  call    ?GetInnerSusInternal@CSusInternalWrapper@@AEAAJPEAPEAUISusInternal@@HH@Z; CSusInternalWrapper::GetInnerSusInternal(ISusInternal * *,int,int)
0x180041fd5  mov     rsi, [rsp+78h+var_48]
0x180041fda  mov     ebx, eax
0x180041fdc  test    eax, eax
0x180041fde  js      loc_1800420E9
0x180041fe4  mov     rcx, [rdi+90h]
0x180041feb  test    rcx, rcx
0x180041fee  jz      loc_1800420C0
0x180041ff4  cmp     dword ptr [rdi+88h], 3
0x180041ffb  jnz     short loc_180042063
0x180041ffd  add     rcx, 60h ; '`'; lpCriticalSection
0x180042001  call    cs:__imp_EnterCriticalSection
0x180042007  mov     rax, [rdi+90h]
0x18004200e  cmp     dword ptr [rax+1Ch], 0
0x180042012  jnz     short loc_180042021
0x180042014  cmp     dword ptr [rax+18h], 0
0x180042018  jnz     short loc_180042021
0x18004201a  mov     ebx, 8024001Bh
0x18004201f  jmp     short loc_18004204A
0x180042021  lea     rax, aNoNeedToReconn; "no need to reconnect completed download"...
0x180042028  mov     r9d, r14d
0x18004202b  mov     [rsp+78h+var_50], rax
0x180042030  xor     edx, edx
0x180042032  xor     ecx, ecx
0x180042034  mov     [rsp+78h+var_58], 0
0x18004203d  mov     r8d, 10000h
0x180042043  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180042048  xor     ebx, ebx
0x18004204a  mov     rcx, [rdi+90h]
0x180042051  add     rcx, 60h ; '`'; lpCriticalSection
0x180042055  call    cs:__imp_LeaveCriticalSection
0x18004205b  test    ebx, ebx
0x18004205d  js      loc_1800420E9
0x180042063  xor     r14d, r14d
0x180042066  cmp     dword ptr [rdi+88h], 2
0x18004206d  jnz     short loc_1800420A4
0x18004206f  mov     rcx, [rdi+90h]
0x180042076  add     rcx, 60h ; '`'; lpCriticalSection
0x18004207a  call    cs:__imp_EnterCriticalSection
0x180042080  mov     rcx, [rdi+90h]; this
0x180042087  mov     r14d, r15d
0x18004208a  cmp     dword ptr [rcx+1Ch], 0
0x18004208e  jnz     short loc_1800420A4
0x180042090  cmp     dword ptr [rcx+18h], 0
0x180042094  jnz     short loc_1800420A4
0x180042096  mov     rdx, rsi; struct ISusInternal *
0x180042099  call    ?Restart@CSusSearchCall@CSusInternalWrapper@@QEAAJPEAUISusInternal@@@Z; CSusInternalWrapper::CSusSearchCall::Restart(ISusInternal *)
0x18004209e  mov     ebx, eax
0x1800420a0  test    eax, eax
0x1800420a2  js      short loc_1800420AB
0x1800420a4  xor     ebx, ebx
0x1800420a6  test    r14d, r14d
0x1800420a9  jz      short loc_1800420BC
0x1800420ab  mov     rcx, [rdi+90h]
0x1800420b2  add     rcx, 60h ; '`'; lpCriticalSection
0x1800420b6  call    cs:__imp_LeaveCriticalSection
0x1800420bc  test    ebx, ebx
0x1800420be  js      short loc_1800420E9
0x1800420c0  xor     ebx, ebx
0x1800420c2  jmp     short loc_1800420E9
0x1800420c4  lea     rax, aSelfUpdateShut_0; "self-update/shutdown event ignored duri"...
0x1800420cb  mov     r9d, r14d
0x1800420ce  mov     [rsp+78h+var_50], rax
0x1800420d3  mov     r8d, ebx
0x1800420d6  xor     edx, edx
0x1800420d8  mov     [rsp+78h+var_58], rsi
0x1800420dd  xor     ecx, ecx
0x1800420df  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800420e4  mov     ebx, 8024000Bh
0x1800420e9  mov     rcx, [rdi+10h]; hEvent
0x1800420ed  call    cs:__imp_SetEvent
0x1800420f3  test    rbp, rbp
0x1800420f6  jz      short loc_180042101
0x1800420f8  mov     rcx, rbp; hObject
0x1800420fb  call    cs:__imp_CloseHandle
0x180042101  test    r12d, r12d
0x180042104  jz      short loc_180042159
0x180042106  test    ebx, ebx
0x180042108  jns     short loc_180042146
0x18004210a  mov     rcx, [rdi+90h]
0x180042111  mov     edx, ebx
0x180042113  mov     rax, [rcx]
0x180042116  mov     rax, [rax+20h]
0x18004211a  call    _guard_dispatch_icall
0x18004211f  test    eax, eax
0x180042121  jns     short loc_180042146
0x180042123  xor     edx, edx
0x180042125  lea     rcx, aUnableToNotify; "Unable to notify caller for failure in "...
0x18004212c  mov     [rsp+78h+var_50], rcx
0x180042131  mov     r8d, 10000h
0x180042137  xor     ecx, ecx
0x180042139  mov     dword ptr [rsp+78h+var_58], eax
0x18004213d  lea     r9d, [rdx+5]
0x180042141  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180042146  mov     rcx, [rdi+90h]
0x18004214d  mov     rax, [rcx]
0x180042150  mov     rax, [rax+10h]
0x180042154  call    _guard_dispatch_icall
0x180042159  test    rsi, rsi
0x18004215c  jz      short loc_18004216D
0x18004215e  mov     rax, [rsi]
0x180042161  mov     rcx, rsi
0x180042164  mov     rax, [rax+10h]
0x180042168  call    _guard_dispatch_icall
0x18004216d  test    r15d, r15d
0x180042170  jz      short loc_180042178
0x180042172  call    cs:__imp_CoUninitialize
0x180042178  xor     eax, eax
0x18004217a  mov     rcx, [rsp+78h+var_30]
0x18004217f  xor     rcx, rsp; StackCookie
0x180042182  call    __security_check_cookie
0x180042187  lea     r11, [rsp+78h+var_28]
0x18004218c  mov     rbx, [r11+38h]
0x180042190  mov     rbp, [r11+40h]
0x180042194  mov     rsp, r11
0x180042197  pop     r15
0x180042199  pop     r14
0x18004219b  pop     r12
0x18004219d  pop     rdi
0x18004219e  pop     rsi
0x18004219f  retn
```
