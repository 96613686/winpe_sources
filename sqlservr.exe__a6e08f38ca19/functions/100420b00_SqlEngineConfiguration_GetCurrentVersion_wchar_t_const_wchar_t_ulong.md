# SqlEngineConfiguration::GetCurrentVersion(wchar_t const *,wchar_t *,ulong *)

- ea: `0x100420b00`
- end: `0x100420db1`
- name: `?GetCurrentVersion@SqlEngineConfiguration@@UEAAXPEB_WPEA_WPEAK@Z`
- size: `689`
- prototype: `void(SqlEngineConfiguration *__hidden this, const wchar_t *, wchar_t *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callees

- `0x100401580`
- `0x100401800`
- `0x100401aa0`
- `0x100402080`
- `0x1004021d0`
- `0x10041eac0`
- `0x100420b00`
- `0x100422b20`
- `0x10044aad0`

## import_xrefs

- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100420be0`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100420be0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100420be6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100420cba`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100420d26`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100420be6`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100420cba`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100420d26`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100420c6d`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100420cdd`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100420c6d`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100420cdd`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100420d6f`
- `sqldk!?KillProcess@SOS_OS@@SAXK@Z` at `0x100420d6f`
- `USER32!MessageBoxW` at `0x100420d64`
- `USER32!MessageBoxW` at `0x100420d64`
- `instapi160!IsDefaultInstanceName` at `0x100420c4c`
- `instapi160!IsDefaultInstanceName` at `0x100420c4c`

## string_xrefs

- `0x100420cc0`: `SQL Server could not find the default instance (%ls) - error %d.Please specify the name of an existing instance on the invocation of sqlservr.exe.\n\nIf you believe that your installation is corrupt or has been tampered with, uninstall then re-run setup to correct this problem.`
- `0x100420d2c`: `SQL Server could not find the specified named instance (%ls) - error %dplease specify the name of an existing instance on the invocation of sqlservr.exe.\n\nIf you believe that your installation is corrupt or has been tampered with, uninstall then re-run setup to correct this problem.`
- `0x100420bf3`: `SQL Registry CurrentVersion Failure`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SqlEngineConfiguration::GetCurrentVersion(
        SqlEngineConfiguration *this,
        const wchar_t *a2,
        BYTE *a3,
        unsigned int *a4)
{
  const WCHAR *v7; // rax
  LSTATUS v8; // esi
  int Value; // eax
  int v10; // ebx
  struct __crt_locale_pointers *v11; // rax
  __int64 v12; // rbx
  IErrorReportingManager *v13; // rax
  struct __crt_locale_pointers *DefaultLocale; // rax
  const wchar_t *v15; // r8
  __int64 v16; // rbx
  IErrorReportingManager *ErrorReportingManager; // rax
  LPBYTE v18; // [rsp+20h] [rbp-A88h]
  LPDWORD v19; // [rsp+28h] [rbp-A80h]
  LPDWORD v20; // [rsp+28h] [rbp-A80h]
  HKEY v21; // [rsp+50h] [rbp-A58h] BYREF
  HKEY v22[3]; // [rsp+58h] [rbp-A50h] BYREF
  char Buffer[512]; // [rsp+70h] [rbp-A38h] BYREF
  WCHAR Text[1024]; // [rsp+270h] [rbp-838h] BYREF

  v22[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v22[0] = 0;
  v21 = 0;
  v7 = (const WCHAR *)(*(__int64 (__fastcall **)(SqlEngineConfiguration *))(*(_QWORD *)this + 272LL))(this);
  if ( IniRegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, v22) )
    goto LABEL_22;
  v8 = IniRegOpenKeyExW(v22[0], (const WCHAR *)L"CurrentVersion", 0, 0x20019u, &v21);
  if ( v8 )
  {
    if ( *((_DWORD *)qword_10049F360 + 3636) || !(unsigned int)IsDefaultInstanceName(a2) )
    {
      v16 = -1;
      do
        ++v16;
      while ( a2[v16] );
      ErrorReportingManager = GetErrorReportingManager();
      LODWORD(v18) = 20;
      if ( (int)IErrorReportingManager::CwchCallFormatToBuffer(
                  ErrorReportingManager,
                  18599,
                  Text,
                  1024,
                  v18,
                  L"SQL Server",
                  2 * (int)v16,
                  a2,
                  v8) > 0 )
        goto LABEL_21;
      _mm_lfence();
      DefaultLocale = GetDefaultLocale();
      v15 = L"SQL Server could not find the specified named instance (%ls) - error %dplease specify the name of an existin"
             "g instance on the invocation of sqlservr.exe.\n"
             "\n"
             "If you believe that your installation is corrupt or has been tampered with, uninstall then re-run setup to "
             "correct this problem.";
    }
    else
    {
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      v13 = GetErrorReportingManager();
      LODWORD(v18) = 20;
      if ( (int)IErrorReportingManager::CwchCallFormatToBuffer(
                  v13,
                  18598,
                  Text,
                  1024,
                  v18,
                  L"SQL Server",
                  2 * (int)v12,
                  a2,
                  v8) > 0 )
        goto LABEL_21;
      _mm_lfence();
      DefaultLocale = GetDefaultLocale();
      v15 = L"SQL Server could not find the default instance (%ls) - error %d.Please specify the name of an existing insta"
             "nce on the invocation of sqlservr.exe.\n"
             "\n"
             "If you believe that your installation is corrupt or has been tampered with, uninstall then re-run setup to "
             "correct this problem.";
    }
    LODWORD(v20) = v8;
    StringCchPrintf_lW(Text, 1024, v15, DefaultLocale, a2, v20);
LABEL_21:
    MessageBoxW(0, Text, L"SQL Server", 0x210010u);
    SOS_OS::KillProcess(0x416u);
    goto LABEL_22;
  }
  Value = IniRegQueryValueExW((int)v21, (int)L"CurrentVersion", 0, 0, a3, a4);
  v10 = Value;
  if ( Value )
  {
    if ( Value > 0 )
      v10 = (unsigned __int16)Value | 0x80070000;
    if ( v10 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v10);
      v11 = GetDefaultLocale();
      LODWORD(v19) = v10;
      if ( (int)StringCchPrintf_lA(Buffer, 512, "%hs (HRESULT 0x%x)", v11, "SQL Registry CurrentVersion Failure", v19) >= 0 )
        FailAndExit(Buffer);
      else
        FailAndExit("SQL Registry CurrentVersion Failure");
    }
  }
LABEL_22:
  if ( v21 )
    IniRegCloseKey(v21);
  if ( v22[0] )
    IniRegCloseKey(v22[0]);
}

```

## disassembly

```asm
0x100420b00  push    rbx
0x100420b02  push    rbp
0x100420b03  push    rsi
0x100420b04  push    rdi
0x100420b05  sub     rsp, 0A88h
0x100420b0c  mov     [rsp+0AA8h+var_A48], 0FFFFFFFFFFFFFFFEh
0x100420b15  mov     rax, cs:__security_cookie
0x100420b1c  xor     rax, rsp
0x100420b1f  mov     [rsp+0AA8h+var_38], rax
0x100420b27  mov     rbp, r9
0x100420b2a  mov     rbx, r8
0x100420b2d  mov     rdi, rdx
0x100420b30  xor     eax, eax
0x100420b32  mov     [rsp+0AA8h+var_A50], rax
0x100420b37  mov     [rsp+0AA8h+var_A58], rax
0x100420b3c  mov     rax, [rcx]
0x100420b3f  call    qword ptr [rax+110h]
0x100420b45  mov     rdx, rax; int
0x100420b48  lea     rax, [rsp+0AA8h+var_A50]
0x100420b4d  mov     [rsp+0AA8h+var_A88], rax; PHKEY
0x100420b52  mov     r9d, 20019h; int
0x100420b58  xor     r8d, r8d; int
0x100420b5b  mov     rcx, 0FFFFFFFF80000002h; int
0x100420b62  call    IniRegOpenKeyExW
0x100420b67  test    eax, eax
0x100420b69  jnz     loc_100420D76
0x100420b6f  lea     rax, [rsp+0AA8h+var_A58]
0x100420b74  mov     [rsp+0AA8h+var_A88], rax; PHKEY
0x100420b79  mov     r9d, 20019h; int
0x100420b7f  xor     r8d, r8d; int
0x100420b82  lea     rdx, aCurrentversion; "CurrentVersion"
0x100420b89  mov     rcx, [rsp+0AA8h+var_A50]; int
0x100420b8e  call    IniRegOpenKeyExW
0x100420b93  mov     esi, eax
0x100420b95  test    eax, eax
0x100420b97  jnz     loc_100420C35
0x100420b9d  mov     [rsp+0AA8h+var_A80], rbp; LPDWORD
0x100420ba2  mov     [rsp+0AA8h+var_A88], rbx; LPBYTE
0x100420ba7  xor     r9d, r9d; int
0x100420baa  xor     r8d, r8d; int
0x100420bad  lea     rdx, aCurrentversion; "CurrentVersion"
0x100420bb4  mov     rcx, [rsp+0AA8h+var_A58]; int
0x100420bb9  call    IniRegQueryValueExW
0x100420bbe  mov     ebx, eax
0x100420bc0  test    eax, eax
0x100420bc2  jz      loc_100420D76
0x100420bc8  jle     short loc_100420BD3
0x100420bca  movzx   ebx, ax
0x100420bcd  or      ebx, 80070000h
0x100420bd3  test    ebx, ebx
0x100420bd5  jns     loc_100420D76
0x100420bdb  lfence
0x100420bde  mov     ecx, ebx
0x100420be0  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x100420be6  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100420bec  mov     r9, rax; struct __crt_locale_pointers *
0x100420bef  mov     dword ptr [rsp+0AA8h+var_A80], ebx
0x100420bf3  lea     rbx, aSqlRegistryCur; "SQL Registry CurrentVersion Failure"
0x100420bfa  mov     [rsp+0AA8h+var_A88], rbx
0x100420bff  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x100420c06  mov     edx, 200h; unsigned __int64
0x100420c0b  lea     rcx, [rsp+0AA8h+Buffer]; Buffer
0x100420c10  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100420c15  test    eax, eax
0x100420c17  jns     short loc_100420C26
0x100420c19  mov     rcx, rbx; char *
0x100420c1c  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100420c21  jmp     loc_100420D76
0x100420c26  lea     rcx, [rsp+0AA8h+Buffer]; char *
0x100420c2b  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100420c30  jmp     loc_100420D76
0x100420c35  mov     rax, cs:qword_10049F360
0x100420c3c  cmp     dword ptr [rax+38D0h], 0
0x100420c43  jnz     loc_100420CC9
0x100420c49  mov     rcx, rdi
0x100420c4c  call    cs:__imp_IsDefaultInstanceName
0x100420c52  test    eax, eax
0x100420c54  jz      short loc_100420CC9
0x100420c56  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100420c5d  nop     dword ptr [rax]
0x100420c60  inc     rbx
0x100420c63  cmp     word ptr [rdi+rbx*2], 0
0x100420c68  jnz     short loc_100420C60
0x100420c6a  add     rbx, rbx
0x100420c6d  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x100420c73  mov     rcx, rax; this
0x100420c76  mov     [rsp+0AA8h+var_A68], esi
0x100420c7a  mov     [rsp+0AA8h+var_A70], rdi
0x100420c7f  mov     [rsp+0AA8h+var_A78], ebx
0x100420c83  lea     rbx, Caption; "SQL Server"
0x100420c8a  mov     [rsp+0AA8h+var_A80], rbx
0x100420c8f  mov     dword ptr [rsp+0AA8h+var_A88], 14h
0x100420c97  mov     r9d, 400h; int
0x100420c9d  lea     r8, [rsp+0AA8h+Text]; wchar_t *
0x100420ca5  mov     edx, 48A6h; int
0x100420caa  call    ?CwchCallFormatToBuffer@IErrorReportingManager@@QEAAHHPEA_WHZZ; IErrorReportingManager::CwchCallFormatToBuffer(int,wchar_t *,int,...)
0x100420caf  test    eax, eax
0x100420cb1  jg      loc_100420D51
0x100420cb7  lfence
0x100420cba  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100420cc0  lea     r8, aSqlServerCould_0; "SQL Server could not find the default i"...
0x100420cc7  jmp     short loc_100420D33
0x100420cc9  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100420cd0  inc     rbx
0x100420cd3  cmp     word ptr [rdi+rbx*2], 0
0x100420cd8  jnz     short loc_100420CD0
0x100420cda  add     rbx, rbx
0x100420cdd  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x100420ce3  mov     rcx, rax; this
0x100420ce6  mov     [rsp+0AA8h+var_A68], esi
0x100420cea  mov     [rsp+0AA8h+var_A70], rdi
0x100420cef  mov     [rsp+0AA8h+var_A78], ebx
0x100420cf3  lea     rbx, Caption; "SQL Server"
0x100420cfa  mov     [rsp+0AA8h+var_A80], rbx
0x100420cff  mov     dword ptr [rsp+0AA8h+var_A88], 14h
0x100420d07  mov     r9d, 400h; int
0x100420d0d  lea     r8, [rsp+0AA8h+Text]; wchar_t *
0x100420d15  mov     edx, 48A7h; int
0x100420d1a  call    ?CwchCallFormatToBuffer@IErrorReportingManager@@QEAAHHPEA_WHZZ; IErrorReportingManager::CwchCallFormatToBuffer(int,wchar_t *,int,...)
0x100420d1f  test    eax, eax
0x100420d21  jg      short loc_100420D51
0x100420d23  lfence
0x100420d26  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100420d2c  lea     r8, aSqlServerCould; "SQL Server could not find the specified"...
0x100420d33  mov     dword ptr [rsp+0AA8h+var_A80], esi
0x100420d37  mov     [rsp+0AA8h+var_A88], rdi
0x100420d3c  mov     r9, rax; struct __crt_locale_pointers *
0x100420d3f  mov     edx, 400h; unsigned __int64
0x100420d44  lea     rcx, [rsp+0AA8h+Text]; Buffer
0x100420d4c  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100420d51  mov     r9d, 210010h; uType
0x100420d57  mov     r8, rbx; lpCaption
0x100420d5a  lea     rdx, [rsp+0AA8h+Text]; lpText
0x100420d62  xor     ecx, ecx; hWnd
0x100420d64  call    cs:__imp_MessageBoxW
0x100420d6a  mov     ecx, 416h
0x100420d6f  call    cs:__imp_?KillProcess@SOS_OS@@SAXK@Z; SOS_OS::KillProcess(ulong)
0x100420d75  nop
0x100420d76  mov     rcx, [rsp+0AA8h+var_A58]
0x100420d7b  test    rcx, rcx
0x100420d7e  jz      short loc_100420D86
0x100420d80  call    IniRegCloseKey
0x100420d85  nop
0x100420d86  mov     rcx, [rsp+0AA8h+var_A50]
0x100420d8b  test    rcx, rcx
0x100420d8e  jz      short loc_100420D95
0x100420d90  call    IniRegCloseKey
0x100420d95  mov     rcx, [rsp+0AA8h+var_38]
0x100420d9d  xor     rcx, rsp; StackCookie
0x100420da0  call    __security_check_cookie
0x100420da5  add     rsp, 0A88h
0x100420dac  pop     rdi
0x100420dad  pop     rsi
0x100420dae  pop     rbp
0x100420daf  pop     rbx
0x100420db0  retn
```
