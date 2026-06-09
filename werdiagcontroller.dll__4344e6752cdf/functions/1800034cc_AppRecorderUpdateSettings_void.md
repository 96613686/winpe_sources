# AppRecorderUpdateSettings(void)

- ea: `0x1800034cc`
- end: `0x180003832`
- name: `?AppRecorderUpdateSettings@@YAJXZ`
- size: `870`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800030b0`

## callees

- `0x180001400`
- `0x180001cd4`
- `0x1800034cc`
- `0x180005990`
- `0x180005a9c`
- `0x180005d24`
- `0x180005fc0`
- `0x18000606c`
- `0x1800063c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800036c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800036c1`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x1800036d8`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x1800036ec`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x1800036d8`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x1800036ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800035d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800035d4`
- `ntdll!RtlFreeUnicodeString` at `0x180003788`
- `ntdll!RtlFreeUnicodeString` at `0x180003788`
- `ntdll!RtlInitUnicodeString` at `0x180003763`
- `ntdll!RtlInitUnicodeString` at `0x180003795`
- `ntdll!RtlInitUnicodeString` at `0x180003763`
- `ntdll!RtlInitUnicodeString` at `0x180003795`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180003534`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180003534`
- `ntdll!NtClose` at `0x1800037b2`
- `ntdll!NtClose` at `0x1800037c2`
- `ntdll!NtClose` at `0x1800037b2`
- `ntdll!NtClose` at `0x1800037c2`
- `ntdll!DbgPrintEx` at `0x18000354f`
- `ntdll!DbgPrintEx` at `0x1800035f5`
- `ntdll!DbgPrintEx` at `0x180003677`
- `ntdll!DbgPrintEx` at `0x18000354f`
- `ntdll!DbgPrintEx` at `0x1800035f5`
- `ntdll!DbgPrintEx` at `0x180003677`
- `ntdll!NtDeleteKey` at `0x1800035c1`
- `ntdll!NtDeleteKey` at `0x1800035c1`
- `ntdll!NtDeleteValueKey` at `0x180003773`
- `ntdll!NtDeleteValueKey` at `0x180003773`

## string_xrefs

- `0x18000353e`: `WERDIAG: AppRecorder: Failed getting current user registry path. NTSTATUS: %08X\n`
- `0x18000356c`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`
- `0x18000362e`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x180003642`: `WERDIAG: AppRecorder: Failed to open App Recorder layer key. NTSTATUS: %08X\n`
- `0x180003669`: `WERDIAG: AppRecorder: Failed to get application appcompat layers. NTSTATUS: %08X\n`
- `0x180003803`: `WERDIAG: AppRecorder: Failed to update application appcompat layers. NTSTATUS: %08X\n`
- `0x180003826`: `WERDIAG: AppRecorder: Failed to update App Recorder run count. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 AppRecorderUpdateSettings(void)
{
  wchar_t *v0; // rbx
  unsigned int v1; // r14d
  NTSTATUS v2; // eax
  int v3; // eax
  int RegDwordValue; // eax
  DWORD LastError; // eax
  signed int v6; // eax
  int v7; // eax
  int RegStringValue; // eax
  __int64 v9; // rdi
  unsigned int v10; // esi
  __int64 v11; // r15
  __int64 v12; // rcx
  unsigned int v13; // edi
  bool v14; // zf
  wchar_t *v15; // rcx
  __int64 v16; // r8
  wchar_t *v17; // rdx
  int v19; // eax
  int v20; // eax
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v24; // [rsp+48h] [rbp-B8h]
  struct _UNICODE_STRING KeyPath; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF

  KeyHandle = 0;
  Handle = 0;
  v0 = 0;
  v21 = 0;
  v24 = 0;
  v1 = -2147467259;
  KeyPath = 0;
  Filename[0] = 0;
  DestinationString = 0;
  v2 = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( v2 < 0 )
  {
    DbgPrintEx(
      0x96u,
      0,
      "WERDIAG: AppRecorder: Failed getting current user registry path. NTSTATUS: %08X\n",
      (unsigned int)v2);
    goto LABEL_37;
  }
  v3 = PluginsNtOpenKey(
         0x10003u,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder",
         &KeyHandle);
  if ( v3 < 0 )
  {
    DbgPrintEx(
      0x96u,
      0,
      "WERDIAG: AppRecorder: AppRecorder settings key is not present. NTSTATUS: %08X\n",
      (unsigned int)v3);
    goto LABEL_37;
  }
  RegDwordValue = PluginsNtGetRegDwordValue(KeyHandle, L"AppRecorderCount", &v21);
  if ( RegDwordValue < 0 )
  {
    DbgPrintEx(
      0x96u,
      0,
      "WERDIAG: AppRecorder: AppRecorder enabled flag is not present. NTSTATUS: %08X\n",
      (unsigned int)RegDwordValue);
    goto LABEL_37;
  }
  if ( v21 > 1 )
  {
    v20 = PluginsNtSetRegDwordValue(KeyHandle, L"AppRecorderCount", v21 - 1);
    if ( v20 < 0 )
    {
      DbgPrintEx(
        0x96u,
        0,
        "WERDIAG: AppRecorder: Failed to update App Recorder run count. NTSTATUS: %08X\n",
        (unsigned int)v20);
      goto LABEL_37;
    }
LABEL_36:
    v1 = 0;
    goto LABEL_37;
  }
  NtDeleteKey(KeyHandle);
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v7 = PluginsNtOpenKey(3u, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers", &Handle);
    if ( v7 < 0 )
    {
      DbgPrintEx(
        0x96u,
        0,
        "WERDIAG: AppRecorder: Failed to open App Recorder layer key. NTSTATUS: %08X\n",
        (unsigned int)v7);
      goto LABEL_37;
    }
    RegStringValue = PluginsNtGetRegStringValue(Handle);
    if ( RegStringValue < 0 )
    {
      DbgPrintEx(
        0x96u,
        0,
        "WERDIAG: AppRecorder: Failed to get application appcompat layers. NTSTATUS: %08X\n",
        RegStringValue);
      v0 = v24;
      goto LABEL_37;
    }
    v0 = v24;
    v9 = -1;
    do
      ++v9;
    while ( v24[v9] );
    if ( (unsigned int)v9 >= 0xB )
    {
      v10 = 0;
      v21 = v9 - 11;
      while ( 1 )
      {
        if ( !(unsigned int)_o__wcsnicmp(&v0[v10], L"AppRecorder", 11) )
        {
          v11 = v10 - 1;
          if ( (!v10 || (unsigned int)_o_isspace(v0[v11])) && ((unsigned int)_o_isspace(v0[v10 + 11]) || !v0[v10 + 11]) )
            break;
        }
        if ( ++v10 > v21 )
          goto LABEL_34;
      }
      v12 = v10;
      if ( v10 )
        v12 = (unsigned int)v11;
      if ( v10 + 11 < (unsigned int)v9 )
      {
        v13 = v9 - v10 - 11;
        v14 = (_DWORD)v12 == 0;
        v15 = &v0[v12];
        if ( v14 )
        {
          v16 = v13;
          v17 = v0 + 12;
        }
        else
        {
          v16 = v13 + 1;
          v17 = v0 + 11;
        }
        memmove_0(v15, &v17[v10], 2 * v16);
      }
      else
      {
        v0[v12] = 0;
      }
    }
LABEL_34:
    if ( *v0 )
    {
      v19 = PluginsNtSetRegStringValue(Handle, Filename, v0);
      if ( v19 < 0 )
      {
        DbgPrintEx(
          0x96u,
          0,
          "WERDIAG: AppRecorder: Failed to update application appcompat layers. NTSTATUS: %08X\n",
          (unsigned int)v19);
        goto LABEL_37;
      }
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, Filename);
      NtDeleteValueKey(Handle, &DestinationString);
    }
    goto LABEL_36;
  }
  LastError = GetLastError();
  DbgPrintEx(0x96u, 0, "WERDIAG: AppRecorder: Failed to get current process name. Win32 error: %08X\n", LastError);
  v6 = GetLastError();
  v1 = v6;
  if ( v6 > 0 )
    v1 = (unsigned __int16)v6 | 0x80070000;
LABEL_37:
  if ( KeyPath.Buffer )
  {
    RtlFreeUnicodeString(&KeyPath);
    RtlInitUnicodeString(&KeyPath, 0);
  }
  if ( v0 )
    operator delete[](v0);
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v1;
}

```

## disassembly

```asm
0x1800034cc  push    rbp
0x1800034ce  push    rbx
0x1800034cf  push    rsi
0x1800034d0  push    rdi
0x1800034d1  push    r12
0x1800034d3  push    r13
0x1800034d5  push    r14
0x1800034d7  push    r15
0x1800034d9  lea     rbp, [rsp-198h]
0x1800034e1  sub     rsp, 298h
0x1800034e8  mov     rax, cs:__security_cookie
0x1800034ef  xor     rax, rsp
0x1800034f2  mov     [rbp+1D0h+var_50], rax
0x1800034f9  xor     r13d, r13d
0x1800034fc  lea     rcx, [rsp+2D0h+KeyPath]; KeyPath
0x180003501  xorps   xmm0, xmm0
0x180003504  mov     [rsp+2D0h+KeyHandle], r13
0x180003509  xorps   xmm1, xmm1
0x18000350c  mov     [rsp+2D0h+Handle], r13
0x180003511  mov     ebx, r13d
0x180003514  mov     [rsp+2D0h+var_2A0], r13d
0x180003519  mov     [rsp+2D0h+var_288], rbx
0x18000351e  mov     r14d, 80004005h
0x180003524  movups  xmmword ptr [rsp+2D0h+KeyPath.Length], xmm0
0x180003529  mov     [rsp+2D0h+Filename], r13w
0x18000352f  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm1
0x180003534  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18000353a  test    eax, eax
0x18000353c  jns     short loc_18000355A
0x18000353e  lea     r8, aWerdiagAppreco_17; "WERDIAG: AppRecorder: Failed getting cu"...
0x180003545  mov     r9d, eax
0x180003548  xor     edx, edx; Level
0x18000354a  mov     ecx, 96h; ComponentId
0x18000354f  call    cs:__imp_DbgPrintEx
0x180003555  jmp     loc_18000377C
0x18000355a  mov     r8, [rsp+2D0h+KeyPath.Buffer]
0x18000355f  lea     rax, [rsp+2D0h+KeyHandle]
0x180003564  xor     r9d, r9d
0x180003567  mov     [rsp+2D0h+var_2B0], rax; KeyHandle
0x18000356c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\Windows E"...
0x180003573  mov     ecx, 10003h; DesiredAccess
0x180003578  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x18000357d  test    eax, eax
0x18000357f  jns     short loc_18000358A
0x180003581  lea     r8, aWerdiagAppreco_5; "WERDIAG: AppRecorder: AppRecorder setti"...
0x180003588  jmp     short loc_180003545
0x18000358a  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x18000358f  lea     r8, [rsp+2D0h+var_2A0]; unsigned int *
0x180003594  lea     rdx, aApprecordercou; "AppRecorderCount"
0x18000359b  call    ?PluginsNtGetRegDwordValue@@YAJPEAXPEB_WPEAK@Z; PluginsNtGetRegDwordValue(void *,wchar_t const *,ulong *)
0x1800035a0  test    eax, eax
0x1800035a2  jns     short loc_1800035AD
0x1800035a4  lea     r8, aWerdiagAppreco_3; "WERDIAG: AppRecorder: AppRecorder enabl"...
0x1800035ab  jmp     short loc_180003545
0x1800035ad  mov     r8d, [rsp+2D0h+var_2A0]
0x1800035b2  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x1800035b7  cmp     r8d, 1
0x1800035bb  ja      loc_18000380F
0x1800035c1  call    cs:__imp_NtDeleteKey
0x1800035c7  mov     r8d, 104h; nSize
0x1800035cd  lea     rdx, [rsp+2D0h+Filename]; lpFilename
0x1800035d2  xor     ecx, ecx; hModule
0x1800035d4  call    cs:__imp_GetModuleFileNameW
0x1800035da  test    eax, eax
0x1800035dc  jnz     short loc_18000361C
0x1800035de  call    cs:__imp_GetLastError
0x1800035e4  lea     r8, aWerdiagAppreco_7; "WERDIAG: AppRecorder: Failed to get cur"...
0x1800035eb  xor     edx, edx; Level
0x1800035ed  mov     r9d, eax
0x1800035f0  mov     ecx, 96h; ComponentId
0x1800035f5  call    cs:__imp_DbgPrintEx
0x1800035fb  call    cs:__imp_GetLastError
0x180003601  mov     r14d, eax
0x180003604  test    eax, eax
0x180003606  jle     loc_18000377C
0x18000360c  movzx   r14d, ax
0x180003610  or      r14d, 80070000h
0x180003617  jmp     loc_18000377C
0x18000361c  mov     r8, [rsp+2D0h+KeyPath.Buffer]
0x180003621  lea     rax, [rsp+2D0h+Handle]
0x180003626  xor     r9d, r9d
0x180003629  mov     [rsp+2D0h+var_2B0], rax; KeyHandle
0x18000362e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003635  lea     ecx, [r9+3]; DesiredAccess
0x180003639  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x18000363e  test    eax, eax
0x180003640  jns     short loc_18000364E
0x180003642  lea     r8, aWerdiagAppreco_11; "WERDIAG: AppRecorder: Failed to open Ap"...
0x180003649  jmp     loc_180003545
0x18000364e  mov     rcx, [rsp+2D0h+Handle]; KeyHandle
0x180003653  lea     r8, [rsp+2D0h+var_288]
0x180003658  lea     rdx, [rsp+2D0h+Filename]
0x18000365d  call    ?PluginsNtGetRegStringValue@@YAJPEAXPEB_WPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; PluginsNtGetRegStringValue(void *,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x180003662  test    eax, eax
0x180003664  jns     short loc_180003687
0x180003666  mov     r9d, eax
0x180003669  lea     r8, aWerdiagAppreco_15; "WERDIAG: AppRecorder: Failed to get app"...
0x180003670  xor     edx, edx; Level
0x180003672  mov     ecx, 96h; ComponentId
0x180003677  call    cs:__imp_DbgPrintEx
0x18000367d  mov     rbx, [rsp+2D0h+var_288]
0x180003682  jmp     loc_18000377C
0x180003687  mov     rbx, [rsp+2D0h+var_288]
0x18000368c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003690  inc     rdi
0x180003693  cmp     [rbx+rdi*2], r13w
0x180003698  jnz     short loc_180003690
0x18000369a  cmp     edi, 0Bh
0x18000369d  jb      loc_18000374F
0x1800036a3  lea     eax, [rdi-0Bh]
0x1800036a6  mov     esi, r13d
0x1800036a9  mov     [rsp+2D0h+var_2A0], eax
0x1800036ad  mov     r12d, esi
0x1800036b0  lea     rdx, aApprecorder; "AppRecorder"
0x1800036b7  mov     r8d, 0Bh
0x1800036bd  lea     rcx, [rbx+r12*2]
0x1800036c1  call    cs:__imp__o__wcsnicmp
0x1800036c7  test    eax, eax
0x1800036c9  jnz     short loc_180003702
0x1800036cb  lea     r15d, [rsi-1]
0x1800036cf  test    esi, esi
0x1800036d1  jz      short loc_1800036E2
0x1800036d3  movzx   ecx, word ptr [rbx+r15*2]
0x1800036d8  call    cs:__imp__o_isspace
0x1800036de  test    eax, eax
0x1800036e0  jz      short loc_180003702
0x1800036e2  lea     eax, [rsi+0Bh]
0x1800036e5  movzx   ecx, word ptr [rbx+rax*2]
0x1800036e9  mov     r13d, eax
0x1800036ec  call    cs:__imp__o_isspace
0x1800036f2  xor     ecx, ecx
0x1800036f4  test    eax, eax
0x1800036f6  jnz     short loc_18000370C
0x1800036f8  cmp     [rbx+r13*2], cx
0x1800036fd  jz      short loc_18000370C
0x1800036ff  xor     r13d, r13d
0x180003702  inc     esi
0x180003704  cmp     esi, [rsp+2D0h+var_2A0]
0x180003708  jbe     short loc_1800036AD
0x18000370a  jmp     short loc_18000374F
0x18000370c  xor     r13d, r13d
0x18000370f  lea     eax, [rsi+0Bh]
0x180003712  test    esi, esi
0x180003714  mov     ecx, esi
0x180003716  cmovnz  ecx, r15d
0x18000371a  cmp     eax, edi
0x18000371c  jb      short loc_180003725
0x18000371e  mov     [rbx+rcx*2], r13w
0x180003723  jmp     short loc_18000374F
0x180003725  sub     edi, esi
0x180003727  add     edi, 0FFFFFFF5h
0x18000372a  test    ecx, ecx
0x18000372c  lea     rcx, [rbx+rcx*2]; void *
0x180003730  jz      short loc_18000373C
0x180003732  lea     r8d, [rdi+1]
0x180003736  lea     rdx, [rbx+16h]
0x18000373a  jmp     short loc_180003743
0x18000373c  mov     r8d, edi
0x18000373f  lea     rdx, [rbx+18h]
0x180003743  add     r8, r8; Size
0x180003746  lea     rdx, [rdx+r12*2]; Src
0x18000374a  call    memmove_0
0x18000374f  lea     rdx, [rsp+2D0h+Filename]; wchar_t *
0x180003754  cmp     [rbx], r13w
0x180003758  jnz     loc_1800037EE
0x18000375e  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x180003763  call    cs:__imp_RtlInitUnicodeString
0x180003769  mov     rcx, [rsp+2D0h+Handle]; KeyHandle
0x18000376e  lea     rdx, [rsp+2D0h+DestinationString]; ValueName
0x180003773  call    cs:__imp_NtDeleteValueKey
0x180003779  mov     r14d, r13d
0x18000377c  cmp     [rsp+2D0h+KeyPath.Buffer], r13
0x180003781  jz      short loc_18000379B
0x180003783  lea     rcx, [rsp+2D0h+KeyPath]; UnicodeString
0x180003788  call    cs:__imp_RtlFreeUnicodeString
0x18000378e  xor     edx, edx; SourceString
0x180003790  lea     rcx, [rsp+2D0h+KeyPath]; DestinationString
0x180003795  call    cs:__imp_RtlInitUnicodeString
0x18000379b  test    rbx, rbx
0x18000379e  jz      short loc_1800037A8
0x1800037a0  mov     rcx, rbx; void *
0x1800037a3  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800037a8  mov     rcx, [rsp+2D0h+Handle]; Handle
0x1800037ad  test    rcx, rcx
0x1800037b0  jz      short loc_1800037B8
0x1800037b2  call    cs:__imp_NtClose
0x1800037b8  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x1800037bd  test    rcx, rcx
0x1800037c0  jz      short loc_1800037C8
0x1800037c2  call    cs:__imp_NtClose
0x1800037c8  mov     eax, r14d
0x1800037cb  mov     rcx, [rbp+1D0h+var_50]
0x1800037d2  xor     rcx, rsp; StackCookie
0x1800037d5  call    __security_check_cookie
0x1800037da  add     rsp, 298h
0x1800037e1  pop     r15
0x1800037e3  pop     r14
0x1800037e5  pop     r13
0x1800037e7  pop     r12
0x1800037e9  pop     rdi
0x1800037ea  pop     rsi
0x1800037eb  pop     rbx
0x1800037ec  pop     rbp
0x1800037ed  retn
0x1800037ee  mov     rcx, [rsp+2D0h+Handle]; KeyHandle
0x1800037f3  mov     r8, rbx; wchar_t *
0x1800037f6  call    ?PluginsNtSetRegStringValue@@YAJPEAXPEB_W1@Z; PluginsNtSetRegStringValue(void *,wchar_t const *,wchar_t const *)
0x1800037fb  test    eax, eax
0x1800037fd  jns     loc_180003779
0x180003803  lea     r8, aWerdiagAppreco; "WERDIAG: AppRecorder: Failed to update "...
0x18000380a  jmp     loc_180003545
0x18000380f  dec     r8d; unsigned int
0x180003812  lea     rdx, aApprecordercou; "AppRecorderCount"
0x180003819  call    ?PluginsNtSetRegDwordValue@@YAJPEAXPEB_WK@Z; PluginsNtSetRegDwordValue(void *,wchar_t const *,ulong)
0x18000381e  test    eax, eax
0x180003820  jns     loc_180003779
0x180003826  lea     r8, aWerdiagAppreco_2; "WERDIAG: AppRecorder: Failed to update "...
0x18000382d  jmp     loc_180003545
```
