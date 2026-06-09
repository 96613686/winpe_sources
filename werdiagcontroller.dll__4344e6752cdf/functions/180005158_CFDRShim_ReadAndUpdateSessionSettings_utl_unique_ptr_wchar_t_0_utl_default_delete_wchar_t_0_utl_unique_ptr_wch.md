# CFDRShim::ReadAndUpdateSessionSettings(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)

- ea: `0x180005158`
- end: `0x1800052ca`
- name: `?ReadAndUpdateSessionSettings@CFDRShim@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@0@Z`
- size: `370`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003b98`
- `0x180005488`

## callees

- `0x180005158`
- `0x180005a9c`
- `0x180005d24`
- `0x180005fc0`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180005197`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180005197`
- `ntdll!NtClose` at `0x180005287`
- `ntdll!NtClose` at `0x1800052af`
- `ntdll!NtClose` at `0x180005287`
- `ntdll!NtClose` at `0x1800052af`
- `ntdll!DbgPrintEx` at `0x1800051d6`
- `ntdll!DbgPrintEx` at `0x18000524b`
- `ntdll!DbgPrintEx` at `0x18000529f`
- `ntdll!DbgPrintEx` at `0x1800051d6`
- `ntdll!DbgPrintEx` at `0x18000524b`
- `ntdll!DbgPrintEx` at `0x18000529f`

## string_xrefs

- `0x1800051c5`: `WERDIAG: Failed opening registry key. NTSTATUS: %08X\n`
- `0x1800051af`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\FDR\CurrentSession`
- `0x1800051ff`: `WERDIAG: Failed reading FDR settings value from registry. NTSTATUS: %08X\n`
- `0x18000520d`: `LogPath`
- `0x180005222`: `WERDIAG: Failed reading log file path value from registry. NTSTATUS: %08X\n`
- `0x18000526f`: `WERDIAG: Failed writing process ID to registry. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 __fastcall CFDRShim::ReadAndUpdateSessionSettings(__int64 a1, __int64 a2, __int64 a3)
{
  int RegStringValue; // ebx
  unsigned int v4; // ebx
  unsigned int UniqueProcess; // r8d
  struct _UNICODE_STRING v7; // [rsp+30h] [rbp-18h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp+8h] BYREF

  Handle = 0;
  v7 = 0;
  if ( a2 && a3 )
  {
    RtlFormatCurrentUserKeyPath(&v7);
    RegStringValue = PluginsNtOpenKey(
                       3u,
                       L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\FDR\\CurrentSession",
                       &Handle);
    if ( RegStringValue >= 0 )
    {
      RegStringValue = PluginsNtGetRegStringValue(Handle);
      if ( RegStringValue >= 0 )
      {
        RegStringValue = PluginsNtGetRegStringValue(Handle);
        if ( RegStringValue >= 0 )
        {
          UniqueProcess = (unsigned int)NtCurrentTeb()->ClientId.UniqueProcess;
          if ( !UniqueProcess )
          {
            DbgPrintEx(0x96u, 0, "WERDIAG: Get current process ID failed\n");
            v4 = -2147467259;
            goto LABEL_15;
          }
          RegStringValue = PluginsNtSetRegDwordValue(Handle, L"ProcID", UniqueProcess);
          if ( RegStringValue >= 0 )
          {
            v4 = 0;
            goto LABEL_15;
          }
          DbgPrintEx(
            0x96u,
            0,
            "WERDIAG: Failed writing process ID to registry. NTSTATUS: %08X\n",
            (unsigned int)RegStringValue);
        }
        else
        {
          DbgPrintEx(
            0x96u,
            0,
            "WERDIAG: Failed reading log file path value from registry. NTSTATUS: %08X\n",
            (unsigned int)RegStringValue);
        }
      }
      else
      {
        DbgPrintEx(
          0x96u,
          0,
          "WERDIAG: Failed reading FDR settings value from registry. NTSTATUS: %08X\n",
          (unsigned int)RegStringValue);
      }
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Failed opening registry key. NTSTATUS: %08X\n", (unsigned int)RegStringValue);
    }
    v4 = RegStringValue | 0x10000000;
LABEL_15:
    if ( Handle )
      NtClose(Handle);
    return v4;
  }
  DbgPrintEx(0x96u, 0, "WERDIAG: Invalid arguments; pointer to string buffer cannot be null\n");
  if ( Handle )
    NtClose(Handle);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180005158  mov     rax, rsp
0x18000515b  mov     [rax+10h], rbx
0x18000515f  mov     [rax+18h], rsi
0x180005163  mov     [rax+8], rcx
0x180005167  push    rdi
0x180005168  sub     rsp, 40h
0x18000516c  mov     qword ptr [rax+8], 0
0x180005174  xorps   xmm0, xmm0
0x180005177  mov     rdi, r8
0x18000517a  mov     rsi, rdx
0x18000517d  movups  xmmword ptr [rax-18h], xmm0
0x180005181  test    rdx, rdx
0x180005184  jz      loc_180005291
0x18000518a  test    r8, r8
0x18000518d  jz      loc_180005291
0x180005193  lea     rcx, [rax-18h]; KeyPath
0x180005197  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18000519d  mov     r8, [rsp+48h+var_10]
0x1800051a2  lea     rax, [rsp+48h+Handle]
0x1800051a7  xor     r9d, r9d
0x1800051aa  mov     [rsp+48h+KeyHandle], rax; KeyHandle
0x1800051af  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x1800051b6  lea     ecx, [r9+3]; DesiredAccess
0x1800051ba  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x1800051bf  mov     ebx, eax
0x1800051c1  test    eax, eax
0x1800051c3  jns     short loc_1800051E5
0x1800051c5  lea     r8, aWerdiagFailedO_5; "WERDIAG: Failed opening registry key. N"...
0x1800051cc  mov     r9d, ebx
0x1800051cf  xor     edx, edx; Level
0x1800051d1  mov     ecx, 96h; ComponentId
0x1800051d6  call    cs:__imp_DbgPrintEx
0x1800051dc  bts     ebx, 1Ch
0x1800051e0  jmp     loc_18000527D
0x1800051e5  mov     rcx, [rsp+48h+Handle]; KeyHandle
0x1800051ea  lea     rdx, aSessionsetting; "SessionSettings"
0x1800051f1  mov     r8, rsi
0x1800051f4  call    ?PluginsNtGetRegStringValue@@YAJPEAXPEB_WPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; PluginsNtGetRegStringValue(void *,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x1800051f9  mov     ebx, eax
0x1800051fb  test    eax, eax
0x1800051fd  jns     short loc_180005208
0x1800051ff  lea     r8, aWerdiagFailedR_3; "WERDIAG: Failed reading FDR settings va"...
0x180005206  jmp     short loc_1800051CC
0x180005208  mov     rcx, [rsp+48h+Handle]; KeyHandle
0x18000520d  lea     rdx, aLogpath; "LogPath"
0x180005214  mov     r8, rdi
0x180005217  call    ?PluginsNtGetRegStringValue@@YAJPEAXPEB_WPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; PluginsNtGetRegStringValue(void *,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x18000521c  mov     ebx, eax
0x18000521e  test    eax, eax
0x180005220  jns     short loc_18000522B
0x180005222  lea     r8, aWerdiagFailedR_1; "WERDIAG: Failed reading log file path v"...
0x180005229  jmp     short loc_1800051CC
0x18000522b  mov     rax, gs:30h
0x180005234  mov     r8d, [rax+40h]; unsigned int
0x180005238  test    r8d, r8d
0x18000523b  jnz     short loc_180005258
0x18000523d  lea     r8, aWerdiagGetCurr; "WERDIAG: Get current process ID failed"...
0x180005244  xor     edx, edx; Level
0x180005246  mov     ecx, 96h; ComponentId
0x18000524b  call    cs:__imp_DbgPrintEx
0x180005251  mov     ebx, 80004005h
0x180005256  jmp     short loc_18000527D
0x180005258  mov     rcx, [rsp+48h+Handle]; KeyHandle
0x18000525d  lea     rdx, aProcid; "ProcID"
0x180005264  call    ?PluginsNtSetRegDwordValue@@YAJPEAXPEB_WK@Z; PluginsNtSetRegDwordValue(void *,wchar_t const *,ulong)
0x180005269  mov     ebx, eax
0x18000526b  test    eax, eax
0x18000526d  jns     short loc_18000527B
0x18000526f  lea     r8, aWerdiagFailedW_2; "WERDIAG: Failed writing process ID to r"...
0x180005276  jmp     loc_1800051CC
0x18000527b  xor     ebx, ebx
0x18000527d  mov     rcx, [rsp+48h+Handle]; Handle
0x180005282  test    rcx, rcx
0x180005285  jz      short loc_18000528D
0x180005287  call    cs:__imp_NtClose
0x18000528d  mov     eax, ebx
0x18000528f  jmp     short loc_1800052BA
0x180005291  lea     r8, aWerdiagInvalid_6; "WERDIAG: Invalid arguments; pointer to "...
0x180005298  xor     edx, edx; Level
0x18000529a  mov     ecx, 96h; ComponentId
0x18000529f  call    cs:__imp_DbgPrintEx
0x1800052a5  mov     rcx, [rsp+48h+Handle]; Handle
0x1800052aa  test    rcx, rcx
0x1800052ad  jz      short loc_1800052B5
0x1800052af  call    cs:__imp_NtClose
0x1800052b5  mov     eax, 80070057h
0x1800052ba  mov     rbx, [rsp+48h+arg_8]
0x1800052bf  mov     rsi, [rsp+48h+arg_10]
0x1800052c4  add     rsp, 40h
0x1800052c8  pop     rdi
0x1800052c9  retn
```
