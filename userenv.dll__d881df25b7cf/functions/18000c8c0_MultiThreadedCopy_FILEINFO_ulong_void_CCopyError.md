# _MultiThreadedCopy(_FILEINFO *,ulong,void *,CCopyError *)

- ea: `0x18000c8c0`
- end: `0x18000ccd8`
- name: `?_MultiThreadedCopy@@YAKPEAU_FILEINFO@@KPEAXPEAVCCopyError@@@Z`
- size: `1048`
- prototype: `unsigned int __fastcall(struct _FILEINFO *, unsigned int, void *, struct CCopyError *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ab88`

## callees

- `0x180008d00`
- `0x18000c8c0`
- `0x18000da4c`
- `0x18000e640`
- `0x18000efe0`
- `0x180019404`
- `0x18001b704`
- `0x18001b848`
- `0x18001b8a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c9b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000c9b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c998`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000c998`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ca41`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000ca41`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000cad4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000cb73`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000cad4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000cb73`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c959`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c959`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000cc11`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000cc11`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cbe6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cbe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc53`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c9c9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c9c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000c90f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000c90f`

## string_xrefs

- `0x18000caaa`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000cb21`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000cbc0`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000cc74`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall _MultiThreadedCopy(struct _FILEINFO *a1, int a2, void *a3, struct CCopyError *a4)
{
  DWORD dwNumberOfProcessors; // esi
  __int64 v9; // rdx
  __int64 v10; // rcx
  HANDLE EventW; // rax
  void *v12; // r15
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  DWORD v15; // edi
  unsigned int v16; // r14d
  __int64 v17; // rax
  HANDLE v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // ecx
  __int64 v22; // rax
  unsigned int i; // esi
  __int64 v24; // rcx
  unsigned int j; // esi
  __int64 v26; // rcx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  DWORD ThreadId; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v31[2]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v32; // [rsp+48h] [rbp-B8h]
  struct _FILEINFO *v33; // [rsp+50h] [rbp-B0h]
  void *v34; // [rsp+58h] [rbp-A8h]
  struct CCopyError *v35; // [rsp+60h] [rbp-A0h]
  _SYSTEM_INFO SystemInfo; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE Handles[15]; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD *Parameter; // [rsp+120h] [rbp+20h] BYREF
  _DWORD v40[62]; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  dwNumberOfProcessors = 16;
  if ( SystemInfo.dwNumberOfProcessors <= 0x10 )
  {
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
    if ( !SystemInfo.dwNumberOfProcessors )
      __int2c();
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
  {
    McTemplateU0q_EventWriteTransfer(v10, v9, dwNumberOfProcessors);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0xFA5,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)LastError,
      dwCreationFlags);
    goto LABEL_40;
  }
  v33 = a1;
  LastError = 0;
  v31[1] = 0;
  TokenHandle = 0;
  v31[0] = a2;
  v32 = EventW;
  v34 = a3;
  v35 = a4;
  CurrentThread = GetCurrentThread();
  OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle);
  if ( TokenHandle )
    RevertToSelf();
  memset_0(Handles, 0, sizeof(Handles));
  ThreadId = 0;
  Parameter = v31;
  v15 = 0;
  hObject = 0;
  v16 = 1;
  v40[0] = 0;
  if ( dwNumberOfProcessors > 1 )
  {
    while ( 1 )
    {
      v17 = 4LL * v16;
      v40[v17] = 0;
      *(_QWORD *)&v40[v17 - 2] = v31;
      v18 = CreateThread(0, 0, CopyFileFunc, &v40[v17 - 2], 0, &ThreadId);
      if ( !v18 )
        break;
      Handles[v16 - 1] = v18;
      ++v15;
      if ( ++v16 >= dwNumberOfProcessors )
        goto LABEL_18;
    }
    LastError = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
    {
      McTemplateU0qd_EventWriteTransfer(v19, EVENT_MTCOPY_CREATE_THREAD_FAILED, v15, LastError);
    }
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0xF5A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)LastError,
      dwCreationFlags);
  }
LABEL_18:
  if ( TokenHandle )
  {
    if ( !SetThreadToken(0, TokenHandle) )
    {
      LastError = GetLastError();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
      {
        McTemplateU0d_EventWriteTransfer(v20, EVENT_MTCOPY_REVERT_THREAD_TOKEN_FAILED, LastError);
      }
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0xF6C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)LastError,
        dwCreationFlags);
      v40[0] = 1;
      v21 = 1;
      if ( v15 )
      {
        do
        {
          v22 = v21++;
          v40[4 * v22] = 1;
        }
        while ( v21 <= v15 );
        for ( i = 1; i <= v15; ++i )
        {
LABEL_27:
          if ( !SetThreadToken(&Handles[i - 1], TokenHandle) )
          {
            LastError = GetLastError();
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
              && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
            {
              McTemplateU0d_EventWriteTransfer(v24, EVENT_MTCOPY_SET_THREAD_TOKEN_FAILED, LastError);
            }
            wil::details::in1diag3::Log_Win32(
              retaddr,
              (void *)0xF80,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
              (const char *)LastError,
              dwCreationFlags);
            v40[4 * i] = 1;
          }
        }
        goto LABEL_33;
      }
    }
    i = 1;
    if ( v15 )
      goto LABEL_27;
  }
LABEL_33:
  SetEvent(v12);
  CopyFileFunc(&Parameter);
  if ( v15 )
  {
    WaitForMultipleObjectsEx(v15, Handles, 1, 0xFFFFFFFF, 0);
    for ( j = 1; j <= v15; ++j )
      CloseHandle(Handles[j - 1]);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  CloseHandle(v12);
LABEL_40:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
  {
    McTemplateU0d_EventWriteTransfer(v26, EVENT_MTCOPY_END, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000c8c0  push    rbp
0x18000c8c2  push    rbx
0x18000c8c3  push    rsi
0x18000c8c4  push    rdi
0x18000c8c5  push    r12
0x18000c8c7  push    r13
0x18000c8c9  push    r14
0x18000c8cb  push    r15
0x18000c8cd  lea     rbp, [rsp-138h]
0x18000c8d5  sub     rsp, 238h
0x18000c8dc  mov     rax, cs:__security_cookie
0x18000c8e3  xor     rax, rsp
0x18000c8e6  mov     [rbp+170h+var_50], rax
0x18000c8ed  xorps   xmm0, xmm0
0x18000c8f0  mov     r13, rcx
0x18000c8f3  lea     rcx, [rsp+270h+SystemInfo]; lpSystemInfo
0x18000c8f8  mov     rdi, r9
0x18000c8fb  movups  xmmword ptr [rsp+270h+SystemInfo], xmm0
0x18000c900  mov     r14, r8
0x18000c903  mov     r12d, edx
0x18000c906  movups  xmmword ptr [rsp+270h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000c90b  movups  xmmword ptr [rbp+170h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000c90f  call    cs:__imp_GetSystemInfo
0x18000c916  nop     dword ptr [rax+rax+00h]
0x18000c91b  mov     esi, 10h
0x18000c920  cmp     [rbp+170h+SystemInfo.dwNumberOfProcessors], esi
0x18000c923  ja      short loc_18000C92E
0x18000c925  mov     esi, [rbp+170h+SystemInfo.dwNumberOfProcessors]
0x18000c928  test    esi, esi
0x18000c92a  jnz     short loc_18000C92E
0x18000c92c  int     2Ch; Windows NT - assertion failure
0x18000c92e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000c935  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000c93a  test    al, al
0x18000c93c  jz      short loc_18000C94F
0x18000c93e  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000c945  jz      short loc_18000C94F
0x18000c947  mov     r8d, esi
0x18000c94a  call    McTemplateU0q_EventWriteTransfer
0x18000c94f  xor     r9d, r9d; lpName
0x18000c952  xor     r8d, r8d; bInitialState
0x18000c955  xor     edx, edx; bManualReset
0x18000c957  xor     ecx, ecx; lpEventAttributes
0x18000c959  call    cs:__imp_CreateEventW
0x18000c960  nop     dword ptr [rax+rax+00h]
0x18000c965  mov     r15, rax
0x18000c968  test    rax, rax
0x18000c96b  jz      loc_18000CC61
0x18000c971  mov     [rsp+270h+var_220], r13
0x18000c976  xor     ebx, ebx
0x18000c978  xor     r13d, r13d
0x18000c97b  mov     [rsp+270h+var_22C], ebx
0x18000c97f  mov     [rsp+270h+TokenHandle], r13
0x18000c984  mov     [rsp+270h+var_230], r12d
0x18000c989  mov     [rsp+270h+var_228], rax
0x18000c98e  mov     [rsp+270h+var_218], r14
0x18000c993  mov     [rsp+270h+var_210], rdi
0x18000c998  call    cs:__imp_GetCurrentThread
0x18000c99f  nop     dword ptr [rax+rax+00h]
0x18000c9a4  lea     r12d, [rbx+1]
0x18000c9a8  mov     rcx, rax; ThreadHandle
0x18000c9ab  mov     r8d, r12d; OpenAsSelf
0x18000c9ae  lea     r9, [rsp+270h+TokenHandle]; TokenHandle
0x18000c9b3  lea     edx, [rbx+0Eh]; DesiredAccess
0x18000c9b6  call    cs:__imp_OpenThreadToken
0x18000c9bd  nop     dword ptr [rax+rax+00h]
0x18000c9c2  cmp     [rsp+270h+TokenHandle], r13
0x18000c9c7  jz      short loc_18000C9D5
0x18000c9c9  call    cs:__imp_RevertToSelf
0x18000c9d0  nop     dword ptr [rax+rax+00h]
0x18000c9d5  xor     edx, edx; Val
0x18000c9d7  lea     rcx, [rbp+170h+Handles]; void *
0x18000c9db  lea     r8d, [rdx+78h]; Size
0x18000c9df  call    memset_0
0x18000c9e4  mov     [rsp+270h+ThreadId], r13d
0x18000c9e9  lea     rax, [rsp+270h+var_230]
0x18000c9ee  mov     [rbp+170h+Parameter], rax
0x18000c9f2  mov     edi, r13d
0x18000c9f5  mov     [rbp+170h+hObject], r13
0x18000c9f9  mov     r14d, r12d
0x18000c9fc  mov     [rbp+170h+var_148], r13d
0x18000ca00  cmp     esi, r12d
0x18000ca03  jbe     loc_18000CAC4
0x18000ca09  lea     rcx, [rsp+270h+var_230]
0x18000ca0e  mov     eax, r14d
0x18000ca11  shl     rax, 4
0x18000ca15  lea     r9, [rbp+170h+Parameter]
0x18000ca19  add     r9, rax; lpParameter
0x18000ca1c  mov     r12d, r14d
0x18000ca1f  lea     r8, ?CopyFileFunc@@YAKPEAX@Z; lpStartAddress
0x18000ca26  xor     edx, edx; dwStackSize
0x18000ca28  mov     [rbp+rax+170h+var_148], r13d
0x18000ca2d  lea     rax, [rsp+270h+ThreadId]
0x18000ca32  mov     [r9], rcx
0x18000ca35  xor     ecx, ecx; lpThreadAttributes
0x18000ca37  mov     [rsp+270h+lpThreadId], rax; lpThreadId
0x18000ca3c  mov     [rsp+270h+dwCreationFlags], r13d; unsigned int
0x18000ca41  call    cs:__imp_CreateThread
0x18000ca48  nop     dword ptr [rax+rax+00h]
0x18000ca4d  test    rax, rax
0x18000ca50  jz      short loc_18000CA6A
0x18000ca52  mov     [rbp+r12*8+170h+hObject], rax
0x18000ca57  mov     r12d, 1
0x18000ca5d  add     edi, r12d
0x18000ca60  add     r14d, r12d
0x18000ca63  cmp     r14d, esi
0x18000ca66  jb      short loc_18000CA09
0x18000ca68  jmp     short loc_18000CAC4
0x18000ca6a  call    cs:__imp_GetLastError
0x18000ca71  nop     dword ptr [rax+rax+00h]
0x18000ca76  mov     ebx, eax
0x18000ca78  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000ca7f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000ca84  test    al, al
0x18000ca86  jz      short loc_18000CAA3
0x18000ca88  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000ca8f  jz      short loc_18000CAA3
0x18000ca91  mov     r9d, ebx
0x18000ca94  lea     rdx, EVENT_MTCOPY_CREATE_THREAD_FAILED
0x18000ca9b  mov     r8d, edi
0x18000ca9e  call    McTemplateU0qd_EventWriteTransfer
0x18000caa3  mov     rcx, [rbp+178h]; this
0x18000caaa  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000cab1  mov     r9d, ebx; char *
0x18000cab4  mov     edx, 0F5Ah; void *
0x18000cab9  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000cabe  mov     r12d, 1
0x18000cac4  mov     rdx, [rsp+270h+TokenHandle]; Token
0x18000cac9  test    rdx, rdx
0x18000cacc  jz      loc_18000CBE3
0x18000cad2  xor     ecx, ecx; Thread
0x18000cad4  call    cs:__imp_SetThreadToken
0x18000cadb  nop     dword ptr [rax+rax+00h]
0x18000cae0  test    eax, eax
0x18000cae2  jnz     short loc_18000CB57
0x18000cae4  call    cs:__imp_GetLastError
0x18000caeb  nop     dword ptr [rax+rax+00h]
0x18000caf0  mov     ebx, eax
0x18000caf2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000caf9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000cafe  test    al, al
0x18000cb00  jz      short loc_18000CB1A
0x18000cb02  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000cb09  jz      short loc_18000CB1A
0x18000cb0b  mov     r8d, ebx
0x18000cb0e  lea     rdx, EVENT_MTCOPY_REVERT_THREAD_TOKEN_FAILED
0x18000cb15  call    McTemplateU0d_EventWriteTransfer
0x18000cb1a  mov     rcx, [rbp+178h]; this
0x18000cb21  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000cb28  mov     r9d, ebx; char *
0x18000cb2b  mov     edx, 0F6Ch; void *
0x18000cb30  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000cb35  mov     [rbp+170h+var_148], r12d
0x18000cb39  mov     ecx, r12d
0x18000cb3c  cmp     edi, r12d
0x18000cb3f  jb      short loc_18000CB57
0x18000cb41  mov     eax, ecx
0x18000cb43  add     ecx, r12d
0x18000cb46  add     rax, rax
0x18000cb49  mov     [rbp+rax*8+170h+var_148], r12d
0x18000cb4e  cmp     ecx, edi
0x18000cb50  jbe     short loc_18000CB41
0x18000cb52  mov     esi, r12d
0x18000cb55  jmp     short loc_18000CB63
0x18000cb57  mov     esi, r12d
0x18000cb5a  cmp     edi, r12d
0x18000cb5d  jb      loc_18000CBE3
0x18000cb63  mov     rdx, [rsp+270h+TokenHandle]; Token
0x18000cb68  lea     rcx, [rbp+170h+hObject]
0x18000cb6c  mov     r14d, esi
0x18000cb6f  lea     rcx, [rcx+r14*8]; Thread
0x18000cb73  call    cs:__imp_SetThreadToken
0x18000cb7a  nop     dword ptr [rax+rax+00h]
0x18000cb7f  test    eax, eax
0x18000cb81  jnz     short loc_18000CBDC
0x18000cb83  call    cs:__imp_GetLastError
0x18000cb8a  nop     dword ptr [rax+rax+00h]
0x18000cb8f  mov     ebx, eax
0x18000cb91  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000cb98  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000cb9d  test    al, al
0x18000cb9f  jz      short loc_18000CBB9
0x18000cba1  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000cba8  jz      short loc_18000CBB9
0x18000cbaa  mov     r8d, ebx
0x18000cbad  lea     rdx, EVENT_MTCOPY_SET_THREAD_TOKEN_FAILED
0x18000cbb4  call    McTemplateU0d_EventWriteTransfer
0x18000cbb9  mov     rcx, [rbp+178h]; this
0x18000cbc0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000cbc7  mov     r9d, ebx; char *
0x18000cbca  mov     edx, 0F80h; void *
0x18000cbcf  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000cbd4  add     r14, r14
0x18000cbd7  mov     [rbp+r14*8+170h+var_148], r12d
0x18000cbdc  add     esi, r12d
0x18000cbdf  cmp     esi, edi
0x18000cbe1  jbe     short loc_18000CB63
0x18000cbe3  mov     rcx, r15; hEvent
0x18000cbe6  call    cs:__imp_SetEvent
0x18000cbed  nop     dword ptr [rax+rax+00h]
0x18000cbf2  lea     rcx, [rbp+170h+Parameter]; Parameter
0x18000cbf6  call    ?CopyFileFunc@@YAKPEAX@Z; CopyFileFunc(void *)
0x18000cbfb  test    edi, edi
0x18000cbfd  jz      short loc_18000CC3A
0x18000cbff  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000cc03  mov     [rsp+270h+dwCreationFlags], r13d; bAlertable
0x18000cc08  mov     r8d, r12d; bWaitAll
0x18000cc0b  lea     rdx, [rbp+170h+Handles]; lpHandles
0x18000cc0f  mov     ecx, edi; nCount
0x18000cc11  call    cs:__imp_WaitForMultipleObjectsEx
0x18000cc18  nop     dword ptr [rax+rax+00h]
0x18000cc1d  mov     esi, r12d
0x18000cc20  mov     ecx, esi
0x18000cc22  mov     rcx, [rbp+rcx*8+170h+hObject]; hObject
0x18000cc27  call    cs:__imp_CloseHandle
0x18000cc2e  nop     dword ptr [rax+rax+00h]
0x18000cc33  add     esi, r12d
0x18000cc36  cmp     esi, edi
0x18000cc38  jbe     short loc_18000CC20
0x18000cc3a  mov     rcx, [rsp+270h+TokenHandle]; hObject
0x18000cc3f  test    rcx, rcx
0x18000cc42  jz      short loc_18000CC50
0x18000cc44  call    cs:__imp_CloseHandle
0x18000cc4b  nop     dword ptr [rax+rax+00h]
0x18000cc50  mov     rcx, r15; hObject
0x18000cc53  call    cs:__imp_CloseHandle
0x18000cc5a  nop     dword ptr [rax+rax+00h]
0x18000cc5f  jmp     short loc_18000CC8A
0x18000cc61  call    cs:__imp_GetLastError
0x18000cc68  nop     dword ptr [rax+rax+00h]
0x18000cc6d  mov     rcx, [rbp+178h]; this
0x18000cc74  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000cc7b  mov     r9d, eax; char *
0x18000cc7e  mov     edx, 0FA5h; void *
0x18000cc83  mov     ebx, eax
0x18000cc85  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000cc8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000cc91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000cc96  test    al, al
0x18000cc98  jz      short loc_18000CCB2
0x18000cc9a  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000cca1  jz      short loc_18000CCB2
0x18000cca3  mov     r8d, ebx
0x18000cca6  lea     rdx, EVENT_MTCOPY_END
0x18000ccad  call    McTemplateU0d_EventWriteTransfer
0x18000ccb2  mov     eax, ebx
0x18000ccb4  mov     rcx, [rbp+170h+var_50]
0x18000ccbb  xor     rcx, rsp; StackCookie
0x18000ccbe  call    __security_check_cookie
0x18000ccc3  add     rsp, 238h
0x18000ccca  pop     r15
0x18000cccc  pop     r14
0x18000ccce  pop     r13
0x18000ccd0  pop     r12
0x18000ccd2  pop     rdi
0x18000ccd3  pop     rsi
0x18000ccd4  pop     rbx
0x18000ccd5  pop     rbp
0x18000ccd6  retn
```
