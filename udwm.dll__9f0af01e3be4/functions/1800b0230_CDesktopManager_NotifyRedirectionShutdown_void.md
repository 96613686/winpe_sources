# CDesktopManager::NotifyRedirectionShutdown(void)

- ea: `0x1800b0230`
- end: `0x1800b0408`
- name: `?NotifyRedirectionShutdown@CDesktopManager@@QEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(CDesktopManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006e044`

## callees

- `0x18001f43c`
- `0x18003aad0`
- `0x180073af8`
- `0x1800757e0`
- `0x1800881d0`
- `0x18008ed74`
- `0x180095130`
- `0x1800b0230`
- `0x1800b053c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0376`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b0376`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0328`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0328`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b030f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b030f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b037e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b037e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b02d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0318`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b02d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0318`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b03d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b03d4`
- `USER32!PostThreadMessageW` at `0x1800b02ea`
- `USER32!PostThreadMessageW` at `0x1800b02ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDesktopManager::NotifyRedirectionShutdown(CDesktopManager *this)
{
  int v2; // eax
  signed int v3; // ebx
  bool v4; // si
  unsigned int v5; // ecx
  void *v6; // rcx
  __int64 v7; // r8
  signed int LastError; // eax
  signed int v9; // eax
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+30h] [rbp-48h] BYREF

  *((_BYTE *)this + 20) = 1;
  v2 = CDesktopManager::EnableMonitorRenderTargets(this, 0);
  v3 = v2;
  if ( v2 < 0 )
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, 0x210u, 0);
  CDesktopManager::ReleaseDCompResources(this);
  v4 = CDesktopManager::CheckAnyPreference(0x10u);
  CDesktopManager::SetPreferences(v5);
  if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      &Microsoft_Windows_Dwm_Udwm_Provider_Context,
      (__int64)UdwmShutdownMessage_Info,
      v7,
      1,
      (__int64)&v11);
  if ( *((_QWORD *)this + 142) )
  {
    SetLastError(0);
    if ( PostThreadMessageW(*((_DWORD *)this + 282), 0x12u, 0, 0) )
    {
      if ( v3 >= 0 )
      {
        v11 = &CDesktopManager::s_csDwmInstance;
        LeaveCriticalSection(&CDesktopManager::s_csDwmInstance);
        SetLastError(0);
        if ( WaitForSingleObject(*((HANDLE *)this + 142), 0xFFFFFFFF) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          if ( v3 >= 0 )
            v3 = -2003304445;
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v3, 0x224u, 0);
        }
        EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
      }
    }
    else
    {
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      if ( v3 >= 0 )
        v3 = -2003304445;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v3, 0x21Cu, 0);
    }
    *((_DWORD *)this + 282) = 0;
    v6 = (void *)*((_QWORD *)this + 142);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)this + 142) = 0;
    }
  }
  if ( !v4 )
    CDesktopManager::ClearPreferences((unsigned int)v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800b0230  push    rbx
0x1800b0232  push    rsi
0x1800b0233  push    rdi
0x1800b0234  push    r14
0x1800b0236  sub     rsp, 58h
0x1800b023a  mov     rax, cs:__security_cookie
0x1800b0241  xor     rax, rsp
0x1800b0244  mov     [rsp+78h+var_38], rax
0x1800b0249  mov     rdi, rcx
0x1800b024c  mov     byte ptr [rcx+14h], 1
0x1800b0250  xor     edx, edx; bool
0x1800b0252  call    ?EnableMonitorRenderTargets@CDesktopManager@@QEAAJ_N@Z; CDesktopManager::EnableMonitorRenderTargets(bool)
0x1800b0257  mov     ebx, eax
0x1800b0259  test    eax, eax
0x1800b025b  jns     short loc_1800B027E
0x1800b025d  mov     [rsp+78h+var_50], 0; void *
0x1800b0266  mov     [rsp+78h+var_58], 210h; unsigned int
0x1800b026e  mov     r9d, eax; int
0x1800b0271  xor     r8d, r8d; unsigned int
0x1800b0274  xor     edx, edx; int *
0x1800b0276  lea     ecx, [rdx+14h]; unsigned int
0x1800b0279  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800b027e  mov     rcx, rdi; this
0x1800b0281  call    ?ReleaseDCompResources@CDesktopManager@@AEAAXXZ; CDesktopManager::ReleaseDCompResources(void)
0x1800b0286  mov     ecx, 10h; unsigned int
0x1800b028b  call    ?CheckAnyPreference@CDesktopManager@@SA_NK@Z; CDesktopManager::CheckAnyPreference(ulong)
0x1800b0290  mov     sil, al
0x1800b0293  call    ?SetPreferences@CDesktopManager@@SAXK@Z; CDesktopManager::SetPreferences(ulong)
0x1800b0298  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x1800b029f  jz      short loc_1800B02C4
0x1800b02a1  lea     rax, [rsp+78h+var_48]
0x1800b02a6  mov     qword ptr [rsp+78h+var_58], rax
0x1800b02ab  mov     r9d, 1
0x1800b02b1  lea     rdx, UdwmShutdownMessage_Info
0x1800b02b8  lea     rcx, Microsoft_Windows_Dwm_Udwm_Provider_Context
0x1800b02bf  call    McGenEventWrite_EtwEventWriteTransfer
0x1800b02c4  cmp     qword ptr [rdi+470h], 0
0x1800b02cc  jz      loc_1800B03E5
0x1800b02d2  xor     ecx, ecx; dwErrCode
0x1800b02d4  call    cs:__imp_SetLastError
0x1800b02da  xor     r9d, r9d; lParam
0x1800b02dd  xor     r8d, r8d; wParam
0x1800b02e0  lea     edx, [r9+12h]; Msg
0x1800b02e4  mov     ecx, [rdi+468h]; idThread
0x1800b02ea  call    cs:__imp_PostThreadMessageW
0x1800b02f0  test    eax, eax
0x1800b02f2  jz      loc_1800B037E
0x1800b02f8  test    ebx, ebx
0x1800b02fa  js      loc_1800B03BE
0x1800b0300  lea     r14, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; CDwmCS CDesktopManager::s_csDwmInstance
0x1800b0307  mov     [rsp+78h+var_48], r14
0x1800b030c  mov     rcx, r14; lpCriticalSection
0x1800b030f  call    cs:__imp_LeaveCriticalSection
0x1800b0315  nop
0x1800b0316  xor     ecx, ecx; dwErrCode
0x1800b0318  call    cs:__imp_SetLastError
0x1800b031e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b0321  mov     rcx, [rdi+470h]; hHandle
0x1800b0328  call    cs:__imp_WaitForSingleObject
0x1800b032e  test    eax, eax
0x1800b0330  jz      short loc_1800B0373
0x1800b0332  call    cs:__imp_GetLastError
0x1800b0338  mov     ebx, eax
0x1800b033a  test    eax, eax
0x1800b033c  jle     short loc_1800B0347
0x1800b033e  movzx   ebx, ax
0x1800b0341  or      ebx, 80070000h
0x1800b0347  mov     eax, 88980003h
0x1800b034c  test    ebx, ebx
0x1800b034e  cmovns  ebx, eax
0x1800b0351  mov     [rsp+78h+var_50], 0; void *
0x1800b035a  mov     [rsp+78h+var_58], 224h; unsigned int
0x1800b0362  mov     r9d, ebx; int
0x1800b0365  xor     r8d, r8d; unsigned int
0x1800b0368  xor     edx, edx; int *
0x1800b036a  lea     ecx, [rdx+14h]; unsigned int
0x1800b036d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800b0372  nop
0x1800b0373  mov     rcx, r14; lpCriticalSection
0x1800b0376  call    cs:__imp_EnterCriticalSection
0x1800b037c  jmp     short loc_1800B03BE
0x1800b037e  call    cs:__imp_GetLastError
0x1800b0384  mov     ebx, eax
0x1800b0386  test    eax, eax
0x1800b0388  jle     short loc_1800B0393
0x1800b038a  movzx   ebx, ax
0x1800b038d  or      ebx, 80070000h
0x1800b0393  mov     eax, 88980003h
0x1800b0398  test    ebx, ebx
0x1800b039a  cmovns  ebx, eax
0x1800b039d  mov     [rsp+78h+var_50], 0; void *
0x1800b03a6  mov     [rsp+78h+var_58], 21Ch; unsigned int
0x1800b03ae  mov     r9d, ebx; int
0x1800b03b1  xor     r8d, r8d; unsigned int
0x1800b03b4  xor     edx, edx; int *
0x1800b03b6  lea     ecx, [rdx+14h]; unsigned int
0x1800b03b9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800b03be  mov     dword ptr [rdi+468h], 0
0x1800b03c8  mov     rcx, [rdi+470h]; hObject
0x1800b03cf  test    rcx, rcx
0x1800b03d2  jz      short loc_1800B03E5
0x1800b03d4  call    cs:__imp_CloseHandle
0x1800b03da  mov     qword ptr [rdi+470h], 0
0x1800b03e5  test    sil, sil
0x1800b03e8  jnz     short loc_1800B03EF
0x1800b03ea  call    ?ClearPreferences@CDesktopManager@@SAXK@Z; CDesktopManager::ClearPreferences(ulong)
0x1800b03ef  mov     eax, ebx
0x1800b03f1  mov     rcx, [rsp+78h+var_38]
0x1800b03f6  xor     rcx, rsp; StackCookie
0x1800b03f9  call    __security_check_cookie
0x1800b03fe  add     rsp, 58h
0x1800b0402  pop     r14
0x1800b0404  pop     rdi
0x1800b0405  pop     rsi
0x1800b0406  pop     rbx
0x1800b0407  retn
```
