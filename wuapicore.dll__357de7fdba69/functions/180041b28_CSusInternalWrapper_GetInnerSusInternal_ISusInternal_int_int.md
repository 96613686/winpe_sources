# CSusInternalWrapper::GetInnerSusInternal(ISusInternal * *,int,int)

- ea: `0x180041b28`
- end: `0x180041e35`
- name: `?GetInnerSusInternal@CSusInternalWrapper@@AEAAJPEAPEAUISusInternal@@HH@Z`
- size: `781`
- prototype: `__int64 __fastcall(CSusInternalWrapper *__hidden this, struct ISusInternal **, int, int)`
- caller_count: `49`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002839c`
- `0x180041e40`
- `0x18004248c`
- `0x180042740`
- `0x180042c7c`
- `0x18004452c`
- `0x1800449b8`
- `0x180044f1c`
- `0x180045420`
- `0x18004559c`
- `0x180045778`
- `0x1800459a4`
- `0x180045bb8`
- `0x180045e0c`
- `0x180046074`
- `0x180046244`
- `0x1800463dc`
- `0x180046608`
- `0x1800467e8`
- `0x1800469c8`
- `0x180046b9c`
- `0x180046d7c`
- `0x180046ef0`
- `0x180047068`
- `0x180047200`
- `0x18004737c`
- `0x180047554`
- `0x180047704`
- `0x180047938`
- `0x180047c54`
- `0x180047e84`
- `0x18004810c`
- `0x1800482d0`
- `0x180048494`
- `0x1800486d0`
- `0x180048dd0`
- `0x18004945c`
- `0x180049634`
- `0x180049860`
- `0x18004cb50`
- `0x18004e010`
- `0x18005a160`
- `0x18005a3c0`
- `0x18005a5c0`
- `0x18005b9d0`
- `0x18005bcc0`
- `0x18006e940`
- `0x18006ec50`
- `0x180071cc0`

## callees

- `0x1800419bc`
- `0x180041b28`
- `0x180090bc8`
- `0x1800929bc`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041ba8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041c59`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041ba8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180041c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d28`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041d18`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041d18`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180041b9e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180041b9e`

## string_xrefs

- `0x180041bca`: `Waited too long for self-update completion; continuing to connect to the service.`
- `0x180041be0`: `Ignore external service connection request during object shutdown.`
- `0x180041da9`: `Object is being shut down; aborting call to the service`
- `0x180041d4d`: `Unable to wait for object shutdown or ready signal`
- `0x180041d6a`: `Skipping SelfUpdate due to new connections not being allowed`
- `0x180041c29`: `Waiting for setup to complete before connecting to service.`
- `0x180041c7a`: `Waited too long for setup completion; continuing to connect to the service.`
- `0x180041c15`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Setup\SetupInProgress`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSusInternalWrapper::GetInnerSusInternal(
        CSusInternalWrapper *this,
        struct ISusInternal **a2,
        int a3,
        int a4)
{
  int v8; // esi
  void *v9; // rax
  DWORD v10; // eax
  __int64 v11; // rcx
  DWORD v12; // eax
  const wchar_t *v13; // rax
  int i; // ebx
  DWORD v15; // eax
  int SusInternal; // eax
  unsigned int v17; // ebx
  bool v18; // zf
  signed int LastError; // eax
  __int64 v21; // [rsp+20h] [rbp-58h]
  struct ISusInternal *v22; // [rsp+30h] [rbp-48h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-40h] BYREF

  v22 = 0;
  *a2 = 0;
  v8 = 3;
  while ( 1 )
  {
    --v8;
    if ( a3 )
    {
      v9 = (void *)*((_QWORD *)this + 2);
      Handles[0] = *((HANDLE *)this + 4);
      Handles[1] = v9;
      v10 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    }
    else
    {
      v10 = WaitForSingleObject(*((HANDLE *)this + 4), 0);
    }
    v11 = v10;
    if ( !v10 )
    {
LABEL_41:
      LODWORD(v21) = -2145124341;
      v17 = -2145124341;
      WUTrace(0, 0, 0x10000, 3, v21, L"Object is being shut down; aborting call to the service");
      goto LABEL_42;
    }
    v12 = v10 - 1;
    if ( v12 )
    {
      if ( v12 != 257 )
      {
        v18 = (_DWORD)v11 == -1;
        goto LABEL_30;
      }
      v13 = L"Waited too long for self-update completion; continuing to connect to the service.";
      if ( !a3 )
        v13 = L"Ignore external service connection request during object shutdown.";
      WUTrace(0, 0, 0x10000, 5, 0, v13);
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 10, -1, -1) == -1 )
      break;
LABEL_21:
    SusInternal = CSusInternalWrapper::CreateSusInternal(this, 1, (struct IUnknown **)&v22);
    v17 = SusInternal;
    if ( SusInternal >= 0 )
    {
      v17 = 0;
      *a2 = v22;
      return v17;
    }
    if ( SusInternal != -2145124325
      && SusInternal != -2147220995
      && SusInternal != -2147417848
      && SusInternal != -2145124322
      && SusInternal != -2147221164
      || v8 < 0 )
    {
      goto LABEL_42;
    }
    WUTrace(0, 0, 0x10000, 5, 0, L"sleep 2 seconds before retry cocreating SusInternal");
    Sleep(0x7D0u);
  }
  if ( !a4 )
  {
    WUTrace(0, 0, 0x10000, 4, 0, L"Skipping SelfUpdate due to new connections not being allowed");
    v17 = -2145124340;
    goto LABEL_42;
  }
  for ( i = 16; ; --i )
  {
    if ( (int)RegKeyExists(v11, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Setup\\SetupInProgress") < 0 )
    {
      if ( i )
        goto LABEL_21;
LABEL_20:
      WUTrace(0, 0, 0x10000, 5, 0, L"Waited too long for setup completion; continuing to connect to the service.");
      goto LABEL_21;
    }
    if ( !i )
      goto LABEL_20;
    WUTrace(0, 0, 0x10000, 5, 0, L"Waiting for setup to complete before connecting to service.");
    v15 = WaitForSingleObject(*((HANDLE *)this + 4), 0x1388u);
    if ( !v15 )
      goto LABEL_41;
    if ( v15 != 258 )
      break;
  }
  v18 = v15 == -1;
LABEL_30:
  if ( v18 )
  {
    LastError = GetLastError();
    v17 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v17 = LastError;
    if ( (v17 & 0x80000000) == 0 )
      v17 = -2147418113;
  }
  else
  {
    v17 = -2145120257;
  }
  LODWORD(v21) = v17;
  WUTrace(0, 0, 0x10000, 1, v21, L"Unable to wait for object shutdown or ready signal");
LABEL_42:
  LODWORD(v21) = v17;
  WUTrace("CSusInternalWrapper::GetInnerSusInternal", 600, 0x10000, 1, v21, L"Method failed");
  if ( v22 )
    (*(void (__fastcall **)(struct ISusInternal *))(*(_QWORD *)v22 + 16LL))(v22);
  return v17;
}

```

## disassembly

```asm
0x180041b28  mov     [rsp+arg_10], rbx
0x180041b2d  mov     [rsp+arg_18], rbp
0x180041b32  push    rsi
0x180041b33  push    rdi
0x180041b34  push    r13
0x180041b36  push    r14
0x180041b38  push    r15
0x180041b3a  sub     rsp, 50h
0x180041b3e  mov     rax, cs:__security_cookie
0x180041b45  xor     rax, rsp
0x180041b48  mov     [rsp+78h+var_30], rax
0x180041b4d  mov     r15d, r9d
0x180041b50  mov     [rsp+78h+var_48], 0
0x180041b59  mov     ebp, r8d
0x180041b5c  mov     qword ptr [rdx], 0
0x180041b63  mov     r14, rdx
0x180041b66  mov     rdi, rcx
0x180041b69  mov     esi, 3
0x180041b6e  mov     r13d, 10000h
0x180041b74  mov     rcx, [rdi+20h]; hHandle
0x180041b78  or      ebx, 0FFFFFFFFh
0x180041b7b  dec     esi
0x180041b7d  test    ebp, ebp
0x180041b7f  jz      short loc_180041BA6
0x180041b81  mov     rax, [rdi+10h]
0x180041b85  lea     rdx, [rsp+78h+Handles]; lpHandles
0x180041b8a  mov     [rsp+78h+Handles], rcx
0x180041b8f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180041b93  lea     ecx, [rbx+3]; nCount
0x180041b96  mov     [rsp+78h+var_38], rax
0x180041b9b  xor     r8d, r8d; bWaitAll
0x180041b9e  call    cs:__imp_WaitForMultipleObjects
0x180041ba4  jmp     short loc_180041BAE
0x180041ba6  xor     edx, edx; dwMilliseconds
0x180041ba8  call    cs:__imp_WaitForSingleObject
0x180041bae  mov     ecx, eax
0x180041bb0  test    eax, eax
0x180041bb2  jz      loc_180041DA4
0x180041bb8  sub     eax, 1
0x180041bbb  jz      short loc_180041BFA
0x180041bbd  cmp     eax, 101h
0x180041bc2  jnz     loc_180041D23
0x180041bc8  xor     edx, edx
0x180041bca  lea     rax, aWaitedTooLongF; "Waited too long for self-update complet"...
0x180041bd1  xor     ecx, ecx
0x180041bd3  mov     r9d, 5
0x180041bd9  mov     r8d, r13d
0x180041bdc  test    ebp, ebp
0x180041bde  jnz     short loc_180041BE7
0x180041be0  lea     rax, aIgnoreExternal; "Ignore external service connection requ"...
0x180041be7  mov     [rsp+78h+var_50], rax
0x180041bec  mov     [rsp+78h+var_58], 0
0x180041bf5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041bfa  mov     eax, ebx
0x180041bfc  lock cmpxchg [rdi+28h], ebx
0x180041c01  jnz     loc_180041CA1
0x180041c07  test    r15d, r15d
0x180041c0a  jz      loc_180041D6A
0x180041c10  mov     ebx, 10h
0x180041c15  lea     rdx, ?c_szAgentSetupInProgressKey@@3QB_WB; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180041c1c  call    ?RegKeyExists@@YAJPEAUHKEY__@@PEB_WW4RegistryHiveType@@@Z; RegKeyExists(HKEY__ *,wchar_t const *,RegistryHiveType)
0x180041c21  test    eax, eax
0x180041c23  js      short loc_180041C76
0x180041c25  test    ebx, ebx
0x180041c27  jz      short loc_180041C7A
0x180041c29  lea     rax, aWaitingForSetu; "Waiting for setup to complete before co"...
0x180041c30  mov     r9d, 5
0x180041c36  mov     [rsp+78h+var_50], rax
0x180041c3b  mov     r8d, r13d
0x180041c3e  xor     edx, edx
0x180041c40  mov     [rsp+78h+var_58], 0
0x180041c49  xor     ecx, ecx
0x180041c4b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041c50  mov     rcx, [rdi+20h]; hHandle
0x180041c54  mov     edx, 1388h; dwMilliseconds
0x180041c59  call    cs:__imp_WaitForSingleObject
0x180041c5f  test    eax, eax
0x180041c61  jz      loc_180041DA4
0x180041c67  cmp     eax, 102h
0x180041c6c  jnz     loc_180041D65
0x180041c72  dec     ebx
0x180041c74  jmp     short loc_180041C15
0x180041c76  test    ebx, ebx
0x180041c78  jnz     short loc_180041CA1
0x180041c7a  lea     rax, aWaitedTooLongF_0; "Waited too long for setup completion; c"...
0x180041c81  mov     r9d, 5
0x180041c87  mov     [rsp+78h+var_50], rax
0x180041c8c  mov     r8d, r13d
0x180041c8f  xor     edx, edx
0x180041c91  mov     [rsp+78h+var_58], 0
0x180041c9a  xor     ecx, ecx
0x180041c9c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041ca1  lea     r8, [rsp+78h+var_48]; struct ISusInternal **
0x180041ca6  mov     edx, 1; int
0x180041cab  mov     rcx, rdi; this
0x180041cae  call    ?CreateSusInternal@CSusInternalWrapper@@AEAAJHPEAPEAUISusInternal@@@Z; CSusInternalWrapper::CreateSusInternal(int,ISusInternal * *)
0x180041cb3  mov     ebx, eax
0x180041cb5  test    eax, eax
0x180041cb7  jns     loc_180041D98
0x180041cbd  cmp     eax, 8024001Bh
0x180041cc2  jz      short loc_180041CE4
0x180041cc4  cmp     eax, 800401FDh
0x180041cc9  jz      short loc_180041CE4
0x180041ccb  cmp     eax, 80010108h
0x180041cd0  jz      short loc_180041CE4
0x180041cd2  cmp     eax, 8024001Eh
0x180041cd7  jz      short loc_180041CE4
0x180041cd9  cmp     eax, 80040154h
0x180041cde  jnz     loc_180041DCD
0x180041ce4  test    esi, esi
0x180041ce6  js      loc_180041DCD
0x180041cec  lea     rax, aSleep2SecondsB; "sleep 2 seconds before retry cocreating"...
0x180041cf3  mov     r9d, 5
0x180041cf9  mov     [rsp+78h+var_50], rax
0x180041cfe  mov     r8d, r13d
0x180041d01  xor     edx, edx
0x180041d03  mov     [rsp+78h+var_58], 0
0x180041d0c  xor     ecx, ecx
0x180041d0e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041d13  mov     ecx, 7D0h; dwMilliseconds
0x180041d18  call    cs:__imp_Sleep
0x180041d1e  jmp     loc_180041B74
0x180041d23  cmp     ecx, 0FFFFFFFFh
0x180041d26  jnz     short loc_180041D48
0x180041d28  call    cs:__imp_GetLastError
0x180041d2e  movzx   ebx, ax
0x180041d31  or      ebx, 80070000h
0x180041d37  test    eax, eax
0x180041d39  cmovle  ebx, eax
0x180041d3c  mov     eax, 8000FFFFh
0x180041d41  test    ebx, ebx
0x180041d43  cmovns  ebx, eax
0x180041d46  jmp     short loc_180041D4D
0x180041d48  mov     ebx, 80240FFFh
0x180041d4d  lea     rax, aUnableToWaitFo; "Unable to wait for object shutdown or r"...
0x180041d54  mov     r9d, 1
0x180041d5a  mov     [rsp+78h+var_50], rax
0x180041d5f  mov     dword ptr [rsp+78h+var_58], ebx
0x180041d63  jmp     short loc_180041DC1
0x180041d65  cmp     eax, 0FFFFFFFFh
0x180041d68  jmp     short loc_180041D26
0x180041d6a  lea     rax, aSkippingSelfup; "Skipping SelfUpdate due to new connecti"...
0x180041d71  mov     r9d, 4
0x180041d77  mov     [rsp+78h+var_50], rax
0x180041d7c  mov     r8d, r13d
0x180041d7f  xor     edx, edx
0x180041d81  mov     [rsp+78h+var_58], 0
0x180041d8a  xor     ecx, ecx
0x180041d8c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041d91  mov     ebx, 8024000Ch
0x180041d96  jmp     short loc_180041DCD
0x180041d98  mov     rax, [rsp+78h+var_48]
0x180041d9d  xor     ebx, ebx
0x180041d9f  mov     [r14], rax
0x180041da2  jmp     short loc_180041E0D
0x180041da4  mov     eax, 8024000Bh
0x180041da9  lea     rcx, aObjectIsBeingS; "Object is being shut down; aborting cal"...
0x180041db0  mov     [rsp+78h+var_50], rcx
0x180041db5  mov     r9d, 3
0x180041dbb  mov     dword ptr [rsp+78h+var_58], eax
0x180041dbf  mov     ebx, eax
0x180041dc1  mov     r8d, r13d
0x180041dc4  xor     edx, edx
0x180041dc6  xor     ecx, ecx
0x180041dc8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041dcd  lea     rax, aMethodFailed; "Method failed"
0x180041dd4  mov     r9d, 1
0x180041dda  mov     [rsp+78h+var_50], rax
0x180041ddf  lea     rcx, aCsusinternalwr_0; "CSusInternalWrapper::GetInnerSusInterna"...
0x180041de6  mov     r8d, r13d
0x180041de9  mov     dword ptr [rsp+78h+var_58], ebx
0x180041ded  mov     edx, 258h
0x180041df2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041df7  mov     rcx, [rsp+78h+var_48]
0x180041dfc  test    rcx, rcx
0x180041dff  jz      short loc_180041E0D
0x180041e01  mov     rdx, [rcx]
0x180041e04  mov     rax, [rdx+10h]
0x180041e08  call    _guard_dispatch_icall
0x180041e0d  mov     eax, ebx
0x180041e0f  mov     rcx, [rsp+78h+var_30]
0x180041e14  xor     rcx, rsp; StackCookie
0x180041e17  call    __security_check_cookie
0x180041e1c  lea     r11, [rsp+78h+var_28]
0x180041e21  mov     rbx, [r11+40h]
0x180041e25  mov     rbp, [r11+48h]
0x180041e29  mov     rsp, r11
0x180041e2c  pop     r15
0x180041e2e  pop     r14
0x180041e30  pop     r13
0x180041e32  pop     rdi
0x180041e33  pop     rsi
0x180041e34  retn
```
