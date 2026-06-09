# _MultiThreadedCopy(_FILEINFO *,ulong,void *,CCopyError *)

- ea: `0x18000bdd8`
- end: `0x18000c185`
- name: `?_MultiThreadedCopy@@YAKPEAU_FILEINFO@@KPEAXPEAVCCopyError@@@Z`
- size: `941`
- prototype: `__int64 __fastcall(struct _FILEINFO *, int, void *, struct CCopyError *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000a200`

## callees

- `0x1800084f0`
- `0x18000bdd8`
- `0x18000cdf0`
- `0x18000d9b0`
- `0x18000e330`
- `0x180017a94`
- `0x180019c58`
- `0x180019d94`
- `0x180019df0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bebc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bebc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bea4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bea4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000bf3b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000bf3b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000bfc2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c051`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000bfc2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c051`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000be6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000be6b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000c0dd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000c0dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c0b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c0b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c05b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c05b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c115`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c10d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c10d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bec9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000bec9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000be27`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000be27`

## string_xrefs

- `0x18000bf98`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000c003`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000c092`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000c122`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

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
      (void *)0xFA1,
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
      v18 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CopyFileFunc, &v40[v17 - 2], 0, &ThreadId);
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
      (void *)0xF56,
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
        (void *)0xF68,
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
              (void *)0xF7C,
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
0x18000bdd8  push    rbp
0x18000bdda  push    rbx
0x18000bddb  push    rsi
0x18000bddc  push    rdi
0x18000bddd  push    r12
0x18000bddf  push    r13
0x18000bde1  push    r14
0x18000bde3  push    r15
0x18000bde5  lea     rbp, [rsp-138h]
0x18000bded  sub     rsp, 238h
0x18000bdf4  mov     rax, cs:__security_cookie
0x18000bdfb  xor     rax, rsp
0x18000bdfe  mov     [rbp+170h+var_50], rax
0x18000be05  xorps   xmm0, xmm0
0x18000be08  mov     r13, rcx
0x18000be0b  lea     rcx, [rsp+270h+SystemInfo]; lpSystemInfo
0x18000be10  mov     rdi, r9
0x18000be13  movups  xmmword ptr [rsp+270h+SystemInfo], xmm0
0x18000be18  mov     r14, r8
0x18000be1b  mov     r12d, edx
0x18000be1e  movups  xmmword ptr [rsp+270h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000be23  movups  xmmword ptr [rbp+170h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000be27  call    cs:__imp_GetSystemInfo
0x18000be2d  mov     esi, 10h
0x18000be32  cmp     [rbp+170h+SystemInfo.dwNumberOfProcessors], esi
0x18000be35  ja      short loc_18000BE40
0x18000be37  mov     esi, [rbp+170h+SystemInfo.dwNumberOfProcessors]
0x18000be3a  test    esi, esi
0x18000be3c  jnz     short loc_18000BE40
0x18000be3e  int     2Ch; Windows NT - assertion failure
0x18000be40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000be47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000be4c  test    al, al
0x18000be4e  jz      short loc_18000BE61
0x18000be50  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000be57  jz      short loc_18000BE61
0x18000be59  mov     r8d, esi
0x18000be5c  call    McTemplateU0q_EventWriteTransfer
0x18000be61  xor     r9d, r9d; lpName
0x18000be64  xor     r8d, r8d; bInitialState
0x18000be67  xor     edx, edx; bManualReset
0x18000be69  xor     ecx, ecx; lpEventAttributes
0x18000be6b  call    cs:__imp_CreateEventW
0x18000be71  mov     r15, rax
0x18000be74  test    rax, rax
0x18000be77  jz      loc_18000C115
0x18000be7d  mov     [rsp+270h+var_220], r13
0x18000be82  xor     ebx, ebx
0x18000be84  xor     r13d, r13d
0x18000be87  mov     [rsp+270h+var_22C], ebx
0x18000be8b  mov     [rsp+270h+TokenHandle], r13
0x18000be90  mov     [rsp+270h+var_230], r12d
0x18000be95  mov     [rsp+270h+var_228], rax
0x18000be9a  mov     [rsp+270h+var_218], r14
0x18000be9f  mov     [rsp+270h+var_210], rdi
0x18000bea4  call    cs:__imp_GetCurrentThread
0x18000beaa  lea     r12d, [rbx+1]
0x18000beae  mov     rcx, rax; ThreadHandle
0x18000beb1  mov     r8d, r12d; OpenAsSelf
0x18000beb4  lea     r9, [rsp+270h+TokenHandle]; TokenHandle
0x18000beb9  lea     edx, [rbx+0Eh]; DesiredAccess
0x18000bebc  call    cs:__imp_OpenThreadToken
0x18000bec2  cmp     [rsp+270h+TokenHandle], r13
0x18000bec7  jz      short loc_18000BECF
0x18000bec9  call    cs:__imp_RevertToSelf
0x18000becf  xor     edx, edx; Val
0x18000bed1  lea     rcx, [rbp+170h+Handles]; void *
0x18000bed5  lea     r8d, [rdx+78h]; Size
0x18000bed9  call    memset_0
0x18000bede  mov     [rsp+270h+ThreadId], r13d
0x18000bee3  lea     rax, [rsp+270h+var_230]
0x18000bee8  mov     [rbp+170h+Parameter], rax
0x18000beec  mov     edi, r13d
0x18000beef  mov     [rbp+170h+hObject], r13
0x18000bef3  mov     r14d, r12d
0x18000bef6  mov     [rbp+170h+var_148], r13d
0x18000befa  cmp     esi, r12d
0x18000befd  jbe     loc_18000BFB2
0x18000bf03  lea     rcx, [rsp+270h+var_230]
0x18000bf08  mov     eax, r14d
0x18000bf0b  shl     rax, 4
0x18000bf0f  lea     r9, [rbp+170h+Parameter]
0x18000bf13  add     r9, rax; lpParameter
0x18000bf16  mov     r12d, r14d
0x18000bf19  lea     r8, ?CopyFileFunc@@YAKPEAX@Z; lpStartAddress
0x18000bf20  xor     edx, edx; dwStackSize
0x18000bf22  mov     [rbp+rax+170h+var_148], r13d
0x18000bf27  lea     rax, [rsp+270h+ThreadId]
0x18000bf2c  mov     [r9], rcx
0x18000bf2f  xor     ecx, ecx; lpThreadAttributes
0x18000bf31  mov     [rsp+270h+lpThreadId], rax; lpThreadId
0x18000bf36  mov     [rsp+270h+dwCreationFlags], r13d; unsigned int
0x18000bf3b  call    cs:__imp_CreateThread
0x18000bf41  test    rax, rax
0x18000bf44  jz      short loc_18000BF5E
0x18000bf46  mov     [rbp+r12*8+170h+hObject], rax
0x18000bf4b  mov     r12d, 1
0x18000bf51  add     edi, r12d
0x18000bf54  add     r14d, r12d
0x18000bf57  cmp     r14d, esi
0x18000bf5a  jb      short loc_18000BF03
0x18000bf5c  jmp     short loc_18000BFB2
0x18000bf5e  call    cs:__imp_GetLastError
0x18000bf64  mov     ebx, eax
0x18000bf66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000bf6d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000bf72  test    al, al
0x18000bf74  jz      short loc_18000BF91
0x18000bf76  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000bf7d  jz      short loc_18000BF91
0x18000bf7f  mov     r9d, ebx
0x18000bf82  lea     rdx, EVENT_MTCOPY_CREATE_THREAD_FAILED
0x18000bf89  mov     r8d, edi
0x18000bf8c  call    McTemplateU0qd_EventWriteTransfer
0x18000bf91  mov     rcx, [rbp+178h]; this
0x18000bf98  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000bf9f  mov     r9d, ebx; char *
0x18000bfa2  mov     edx, 0F56h; void *
0x18000bfa7  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000bfac  mov     r12d, 1
0x18000bfb2  mov     rdx, [rsp+270h+TokenHandle]; Token
0x18000bfb7  test    rdx, rdx
0x18000bfba  jz      loc_18000C0B5
0x18000bfc0  xor     ecx, ecx; Thread
0x18000bfc2  call    cs:__imp_SetThreadToken
0x18000bfc8  test    eax, eax
0x18000bfca  jnz     short loc_18000C039
0x18000bfcc  call    cs:__imp_GetLastError
0x18000bfd2  mov     ebx, eax
0x18000bfd4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000bfdb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000bfe0  test    al, al
0x18000bfe2  jz      short loc_18000BFFC
0x18000bfe4  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000bfeb  jz      short loc_18000BFFC
0x18000bfed  mov     r8d, ebx
0x18000bff0  lea     rdx, EVENT_MTCOPY_REVERT_THREAD_TOKEN_FAILED
0x18000bff7  call    McTemplateU0d_EventWriteTransfer
0x18000bffc  mov     rcx, [rbp+178h]; this
0x18000c003  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000c00a  mov     r9d, ebx; char *
0x18000c00d  mov     edx, 0F68h; void *
0x18000c012  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000c017  mov     [rbp+170h+var_148], r12d
0x18000c01b  mov     ecx, r12d
0x18000c01e  cmp     edi, r12d
0x18000c021  jb      short loc_18000C039
0x18000c023  mov     eax, ecx
0x18000c025  add     ecx, r12d
0x18000c028  add     rax, rax
0x18000c02b  mov     [rbp+rax*8+170h+var_148], r12d
0x18000c030  cmp     ecx, edi
0x18000c032  jbe     short loc_18000C023
0x18000c034  mov     esi, r12d
0x18000c037  jmp     short loc_18000C041
0x18000c039  mov     esi, r12d
0x18000c03c  cmp     edi, r12d
0x18000c03f  jb      short loc_18000C0B5
0x18000c041  mov     rdx, [rsp+270h+TokenHandle]; Token
0x18000c046  lea     rcx, [rbp+170h+hObject]
0x18000c04a  mov     r14d, esi
0x18000c04d  lea     rcx, [rcx+r14*8]; Thread
0x18000c051  call    cs:__imp_SetThreadToken
0x18000c057  test    eax, eax
0x18000c059  jnz     short loc_18000C0AE
0x18000c05b  call    cs:__imp_GetLastError
0x18000c061  mov     ebx, eax
0x18000c063  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000c06a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000c06f  test    al, al
0x18000c071  jz      short loc_18000C08B
0x18000c073  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18000c07a  jz      short loc_18000C08B
0x18000c07c  mov     r8d, ebx
0x18000c07f  lea     rdx, EVENT_MTCOPY_SET_THREAD_TOKEN_FAILED
0x18000c086  call    McTemplateU0d_EventWriteTransfer
0x18000c08b  mov     rcx, [rbp+178h]; this
0x18000c092  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000c099  mov     r9d, ebx; char *
0x18000c09c  mov     edx, 0F7Ch; void *
0x18000c0a1  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000c0a6  add     r14, r14
0x18000c0a9  mov     [rbp+r14*8+170h+var_148], r12d
0x18000c0ae  add     esi, r12d
0x18000c0b1  cmp     esi, edi
0x18000c0b3  jbe     short loc_18000C041
0x18000c0b5  mov     rcx, r15; hEvent
0x18000c0b8  call    cs:__imp_SetEvent
0x18000c0be  lea     rcx, [rbp+170h+Parameter]; Parameter
0x18000c0c2  call    ?CopyFileFunc@@YAKPEAX@Z; CopyFileFunc(void *)
0x18000c0c7  test    edi, edi
0x18000c0c9  jz      short loc_18000C0FA
0x18000c0cb  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000c0cf  mov     [rsp+270h+dwCreationFlags], r13d; bAlertable
0x18000c0d4  mov     r8d, r12d; bWaitAll
0x18000c0d7  lea     rdx, [rbp+170h+Handles]; lpHandles
0x18000c0db  mov     ecx, edi; nCount
0x18000c0dd  call    cs:__imp_WaitForMultipleObjectsEx
0x18000c0e3  mov     esi, r12d
0x18000c0e6  mov     ecx, esi
0x18000c0e8  mov     rcx, [rbp+rcx*8+170h+hObject]; hObject
0x18000c0ed  call    cs:__imp_CloseHandle
0x18000c0f3  add     esi, r12d
0x18000c0f6  cmp     esi, edi
0x18000c0f8  jbe     short loc_18000C0E6
0x18000c0fa  mov     rcx, [rsp+270h+TokenHandle]; hObject
0x18000c0ff  test    rcx, rcx
0x18000c102  jz      short loc_18000C10A
0x18000c104  call    cs:__imp_CloseHandle
0x18000c10a  mov     rcx, r15; hObject
0x18000c10d  call    cs:__imp_CloseHandle
0x18000c113  jmp     short loc_18000C138
0x18000c115  call    cs:__imp_GetLastError
0x18000c11b  mov     rcx, [rbp+178h]; this
0x18000c122  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000c129  mov     r9d, eax; char *
0x18000c12c  mov     edx, 0FA1h; void *
0x18000c131  mov     ebx, eax
0x18000c133  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18000c138  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18000c13f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18000c144  test    al, al
0x18000c146  jz      short loc_18000C160
0x18000c148  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18000c14f  jz      short loc_18000C160
0x18000c151  mov     r8d, ebx
0x18000c154  lea     rdx, EVENT_MTCOPY_END
0x18000c15b  call    McTemplateU0d_EventWriteTransfer
0x18000c160  mov     eax, ebx
0x18000c162  mov     rcx, [rbp+170h+var_50]
0x18000c169  xor     rcx, rsp; StackCookie
0x18000c16c  call    __security_check_cookie
0x18000c171  add     rsp, 238h
0x18000c178  pop     r15
0x18000c17a  pop     r14
0x18000c17c  pop     r13
0x18000c17e  pop     r12
0x18000c180  pop     rdi
0x18000c181  pop     rsi
0x18000c182  pop     rbx
0x18000c183  pop     rbp
0x18000c184  retn
```
