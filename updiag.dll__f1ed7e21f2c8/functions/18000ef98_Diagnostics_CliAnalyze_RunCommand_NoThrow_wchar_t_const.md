# Diagnostics::CliAnalyze::RunCommand_NoThrow(wchar_t const *)

- ea: `0x18000ef98`
- end: `0x18000f1fb`
- name: `?RunCommand_NoThrow@CliAnalyze@Diagnostics@@SAJPEB_W@Z`
- size: `611`
- prototype: `__int64 __fastcall(LPCWSTR lpCmdLine)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008a90`

## callees

- `0x18000897c`
- `0x18000c5c8`
- `0x18000e86c`
- `0x18000ef98`
- `0x18000f290`
- `0x18000fcbc`
- `0x1800105fc`
- `0x180018988`
- `0x18008fc1c`
- `0x18008fe00`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0c8`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000f09a`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000f09a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f0b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f0b5`

## string_xrefs

- `0x18000f12d`: `Error parsing command line argument %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Diagnostics::CliAnalyze::RunCommand_NoThrow(LPCWSTR lpCmdLine)
{
  void *Instance; // rax
  wchar_t *v3; // rdi
  int v4; // ecx
  const wchar_t **v5; // rax
  void *v6; // rcx
  signed int LastError; // eax
  unsigned __int64 v8; // r9
  const char *v9; // rax
  int v10; // eax
  const char *v11; // r9
  __int64 result; // rax
  const struct wil::FailureInfo *v13; // rdx
  unsigned __int64 v14; // [rsp+20h] [rbp-378h]
  wchar_t *v15; // [rsp+38h] [rbp-360h] BYREF
  _QWORD v16[4]; // [rsp+40h] [rbp-358h] BYREF
  _BYTE v17[160]; // [rsp+60h] [rbp-338h] BYREF
  int pNumArgs[4]; // [rsp+100h] [rbp-298h] BYREF
  _QWORD v19[78]; // [rsp+110h] [rbp-288h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  if ( wil::details::g_pfnLoggingCallback
    && (void (__fastcall *)(const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != Diagnostics::CliAnalyze::FallbackLoggingCallback )
  {
    memset(v17, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v17, v13);
  }
  wil::details::g_pfnLoggingCallback = (__int64)Diagnostics::CliAnalyze::FallbackLoggingCallback;
  memset(v19, 0, sizeof(v19));
  try
  {
    v19[1] = 0;
    v19[0] = &Diagnostics::CliAnalyze::`vftable';
    LOWORD(v19[67]) = 0;
    LOWORD(v19[71]) = 0;
    BYTE2(v19[71]) = 0;
    LOBYTE(v19[75]) = 0;
    v16[0] = 24;
    v16[1] = 1;
    v16[2] = 0x180000000uLL;
    Instance = UpdateDiagImpl::CreateInstance((const struct UpdateDiagnostics::DiagContext *)v16);
    v19[76] = &UpdateDiagnostics::update_diagnostics::`vftable';
    v19[77] = Instance;
    v3 = 0;
    v15 = 0;
    v4 = 0;
    pNumArgs[0] = 0;
    if ( lpCmdLine && *lpCmdLine )
    {
      v5 = (const wchar_t **)CommandLineToArgvW(lpCmdLine, pNumArgs);
      v6 = (void *)v19[1];
      v19[1] = v5;
      if ( v6 )
      {
        LocalFree(v6);
        v5 = (const wchar_t **)v19[1];
      }
      if ( !v5 )
      {
        LastError = GetLastError();
        v8 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v8 = (unsigned int)LastError;
        goto LABEL_15;
      }
      v4 = pNumArgs[0];
    }
    else
    {
      v5 = (const wchar_t **)v19[1];
    }
    v8 = (unsigned int)CommandLineBase::Parse((CommandLineBase *)v19, v5, v4, (const wchar_t **)&v15, v14);
    v3 = v15;
LABEL_15:
    v9 = (const char *)&psz;
    if ( v3 )
      v9 = (const char *)v3;
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x8A,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\cmdline\\CliAnalyze.hpp",
      (const char *)v8,
      (int)"Error parsing command line argument %ws",
      v9);
    if ( !v19[2]
      || (v10 = wcsicmp(Diagnostics::CliAnalyze::_actionGeneric, (const wchar_t *)v19[2]), LOBYTE(v19[75]) = 1, !v10) )
    {
      LOBYTE(v19[75]) = 0;
    }
    Diagnostics::CliAnalyze::GetOutputType(v19, 1);
    Diagnostics::CliAnalyze::Run((Diagnostics::CliAnalyze *)v19);
    Diagnostics::CliAnalyze::~CliAnalyze((Diagnostics::CliAnalyze *)v19);
    wil::details::g_pfnLoggingCallback = 0;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7B,
                           (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\cmdline\\CliAnalyze.hpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18000ef98  mov     [rsp+arg_0], rbx
0x18000ef9d  mov     [rsp+arg_8], rsi
0x18000efa2  push    rdi
0x18000efa3  sub     rsp, 390h
0x18000efaa  mov     rax, cs:__security_cookie
0x18000efb1  xor     rax, rsp
0x18000efb4  mov     [rsp+398h+var_18], rax
0x18000efbc  mov     rbx, rcx
0x18000efbf  mov     rcx, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000efc6  xor     esi, esi
0x18000efc8  lea     rax, ?FallbackLoggingCallback@CliAnalyze@Diagnostics@@SAXAEBUFailureInfo@wil@@@Z; Diagnostics::CliAnalyze::FallbackLoggingCallback(wil::FailureInfo const &)
0x18000efcf  test    rcx, rcx
0x18000efd2  jz      short loc_18000EFDD
0x18000efd4  cmp     rcx, rax
0x18000efd7  jnz     loc_18000F1DD
0x18000efdd  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rax
0x18000efe4  mov     [rsp+398h+var_367], 1
0x18000efe9  xor     edx, edx; Val
0x18000efeb  mov     r8d, 270h; Size
0x18000eff1  lea     rcx, [rsp+398h+var_288]; void *
0x18000eff9  call    memset
0x18000effe  mov     [rsp+398h+hMem], rsi
0x18000f006  lea     rax, ??_7CliAnalyze@Diagnostics@@6B@; const Diagnostics::CliAnalyze::`vftable'
0x18000f00d  mov     [rsp+398h+var_288], rax
0x18000f015  mov     [rsp+398h+var_70], si
0x18000f01d  mov     [rsp+398h+var_50], si
0x18000f025  mov     [rsp+398h+var_4E], sil
0x18000f02d  mov     [rsp+398h+var_30], sil
0x18000f035  mov     [rsp+398h+var_358], 18h
0x18000f03e  mov     [rsp+398h+var_350], 1
0x18000f047  lea     rax, cs:180000000h
0x18000f04e  mov     [rsp+398h+var_348], rax
0x18000f053  lea     rcx, [rsp+398h+var_358]; struct UpdateDiagnostics::DiagContext *
0x18000f058  call    ?CreateInstance@UpdateDiagImpl@@SAPEAXPEBUDiagContext@UpdateDiagnostics@@@Z; UpdateDiagImpl::CreateInstance(UpdateDiagnostics::DiagContext const *)
0x18000f05d  lea     rcx, ??_7update_diagnostics@UpdateDiagnostics@@6B@; const UpdateDiagnostics::update_diagnostics::`vftable'
0x18000f064  mov     [rsp+398h+var_28], rcx
0x18000f06c  mov     [rsp+398h+var_20], rax
0x18000f074  mov     rdi, rsi
0x18000f077  mov     [rsp+398h+var_360], rsi
0x18000f07c  mov     ecx, esi
0x18000f07e  mov     [rsp+398h+pNumArgs], ecx
0x18000f085  test    rbx, rbx
0x18000f088  jz      short loc_18000F0EA
0x18000f08a  cmp     [rbx], si
0x18000f08d  jz      short loc_18000F0EA
0x18000f08f  lea     rdx, [rsp+398h+pNumArgs]; pNumArgs
0x18000f097  mov     rcx, rbx; lpCmdLine
0x18000f09a  call    cs:__imp_CommandLineToArgvW
0x18000f0a0  mov     rcx, [rsp+398h+hMem]; hMem
0x18000f0a8  mov     [rsp+398h+hMem], rax
0x18000f0b0  test    rcx, rcx
0x18000f0b3  jz      short loc_18000F0C3
0x18000f0b5  call    cs:__imp_LocalFree
0x18000f0bb  mov     rax, [rsp+398h+hMem]
0x18000f0c3  test    rax, rax
0x18000f0c6  jnz     short loc_18000F0E1
0x18000f0c8  call    cs:__imp_GetLastError
0x18000f0ce  movzx   r9d, ax
0x18000f0d2  or      r9d, 80070000h
0x18000f0d9  test    eax, eax
0x18000f0db  cmovle  r9d, eax
0x18000f0df  jmp     short loc_18000F112
0x18000f0e1  mov     ecx, [rsp+398h+pNumArgs]
0x18000f0e8  jmp     short loc_18000F0F2
0x18000f0ea  mov     rax, [rsp+398h+hMem]
0x18000f0f2  movsxd  r8, ecx; unsigned __int64
0x18000f0f5  lea     r9, [rsp+398h+var_360]; wchar_t **
0x18000f0fa  mov     rdx, rax; wchar_t **
0x18000f0fd  lea     rcx, [rsp+398h+var_288]; this
0x18000f105  call    ?Parse@CommandLineBase@@QEAAJPEAPEB_W_K01@Z; CommandLineBase::Parse(wchar_t const * *,unsigned __int64,wchar_t const * *,unsigned __int64)
0x18000f10a  mov     r9d, eax; char *
0x18000f10d  mov     rdi, [rsp+398h+var_360]
0x18000f112  lea     rax, psz
0x18000f119  test    rdi, rdi
0x18000f11c  cmovnz  rax, rdi
0x18000f120  mov     rcx, [rsp+398h]; this
0x18000f128  mov     [rsp+398h+var_370], rax; char *
0x18000f12d  lea     rax, aErrorParsingCo; "Error parsing command line argument %ws"
0x18000f134  mov     qword ptr [rsp+398h+var_378], rax; int
0x18000f139  lea     r8, aCW1SSrcCalliop_3; "C:\\__w\\1\\s\\src\\Calliope\\libs\\cmd"...
0x18000f140  mov     edx, 8Ah; void *
0x18000f145  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000f14a  mov     rdx, [rsp+398h+String2]; String2
0x18000f152  test    rdx, rdx
0x18000f155  jz      short loc_18000F16F
0x18000f157  mov     rcx, cs:?_actionGeneric@CliAnalyze@Diagnostics@@0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@B; String1
0x18000f15e  call    _wcsicmp
0x18000f163  test    eax, eax
0x18000f165  mov     [rsp+398h+var_30], 1
0x18000f16d  jnz     short loc_18000F177
0x18000f16f  mov     [rsp+398h+var_30], sil
0x18000f177  mov     edx, 1
0x18000f17c  lea     rcx, [rsp+398h+var_288]
0x18000f184  call    ?GetOutputType@CliAnalyze@Diagnostics@@AEBA?AW4OutputType@12@W4312@@Z; Diagnostics::CliAnalyze::GetOutputType(Diagnostics::CliAnalyze::OutputType)
0x18000f189  nop
0x18000f18a  lea     rcx, [rsp+398h+var_288]; this
0x18000f192  call    ?Run@CliAnalyze@Diagnostics@@QEAAXXZ; Diagnostics::CliAnalyze::Run(void)
0x18000f197  nop
0x18000f198  lea     rcx, [rsp+398h+var_288]; this
0x18000f1a0  call    ??1CliAnalyze@Diagnostics@@QEAA@XZ; Diagnostics::CliAnalyze::~CliAnalyze(void)
0x18000f1a5  nop
0x18000f1a6  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rsi
0x18000f1ad  xor     eax, eax
0x18000f1af  jmp     short loc_18000F1B8
0x18000f1b1  mov     eax, [rsp+398h+pNumArgs]
0x18000f1b8  mov     rcx, [rsp+398h+var_18]
0x18000f1c0  xor     rcx, rsp; StackCookie
0x18000f1c3  call    __security_check_cookie
0x18000f1c8  lea     r11, [rsp+398h+var_8]
0x18000f1d0  mov     rbx, [r11+10h]
0x18000f1d4  mov     rsi, [r11+18h]
0x18000f1d8  mov     rsp, r11
0x18000f1db  pop     rdi
0x18000f1dc  retn
0x18000f1dd  xor     edx, edx; Val
0x18000f1df  mov     r8d, 98h; Size
0x18000f1e5  lea     rcx, [rsp+398h+var_338]; void *
0x18000f1ea  call    memset
0x18000f1ef  lea     rcx, [rsp+398h+var_338]; this
0x18000f1f4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
