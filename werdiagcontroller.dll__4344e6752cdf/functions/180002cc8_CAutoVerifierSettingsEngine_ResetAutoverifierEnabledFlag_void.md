# CAutoVerifierSettingsEngine::ResetAutoverifierEnabledFlag(void)

- ea: `0x180002cc8`
- end: `0x180002e2d`
- name: `?ResetAutoverifierEnabledFlag@CAutoVerifierSettingsEngine@@AEAAJXZ`
- size: `357`
- prototype: `__int64 __fastcall(CAutoVerifierSettingsEngine *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800028d0`

## callees

- `0x180002234`
- `0x180002cc8`
- `0x180005990`
- `0x180005d24`
- `0x180005fc0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180002dee`
- `ntdll!RtlFreeUnicodeString` at `0x180002dee`
- `ntdll!RtlInitUnicodeString` at `0x180002dfa`
- `ntdll!RtlInitUnicodeString` at `0x180002dfa`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180002cfc`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180002cfc`
- `ntdll!NtClose` at `0x180002e0a`
- `ntdll!NtClose` at `0x180002e1a`
- `ntdll!NtClose` at `0x180002e0a`
- `ntdll!NtClose` at `0x180002e1a`
- `ntdll!DbgPrintEx` at `0x180002d19`
- `ntdll!DbgPrintEx` at `0x180002d7a`
- `ntdll!DbgPrintEx` at `0x180002dd4`
- `ntdll!DbgPrintEx` at `0x180002d19`
- `ntdll!DbgPrintEx` at `0x180002d7a`
- `ntdll!DbgPrintEx` at `0x180002dd4`

## string_xrefs

- `0x180002d34`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\Autoverifier`
- `0x180002d4a`: `WERDIAG: Failed opening registry key. NTSTATUS: %08X\n`
- `0x180002d08`: `WERDIAG: Failed getting current user registry path. NTSTATUS: %08X\n`
- `0x180002d91`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Session Manager`

## pseudocode

```c
__int64 __fastcall CAutoVerifierSettingsEngine::ResetAutoverifierEnabledFlag(CAutoVerifierSettingsEngine *this)
{
  NTSTATUS v1; // eax
  int v2; // ebx
  int v3; // eax
  CAutoVerifierSettingsEngine *v4; // rcx
  struct _UNICODE_STRING KeyPath; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v7; // [rsp+50h] [rbp+10h] BYREF
  int v8; // [rsp+54h] [rbp+14h]
  HANDLE Handle; // [rsp+58h] [rbp+18h] BYREF
  HANDLE KeyHandle; // [rsp+60h] [rbp+20h] BYREF

  v8 = HIDWORD(this);
  KeyHandle = 0;
  Handle = 0;
  KeyPath = 0;
  v7 = 0;
  v1 = RtlFormatCurrentUserKeyPath(&KeyPath);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v3 = PluginsNtOpenKey(
           2u,
           L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\Autoverifier",
           KeyPath.Buffer,
           0,
           &KeyHandle);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v2 = PluginsNtSetRegDwordValue(KeyHandle, L"AutoverifierEnabled", 0);
      if ( v2 >= 0 )
      {
        if ( (int)PluginsNtOpenKey(
                    1u,
                    L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Session Manager",
                    0,
                    0,
                    &Handle) >= 0
          && (int)PluginsNtGetRegDwordValue(Handle, L"ImageExecutionOptions", &v7) >= 0
          && v7 )
        {
          DbgPrintEx(0x96u, 3u, "WERDIAG: Not disabling HKCU IFEO look-up because its statically enabled.\n");
        }
        else
        {
          CAutoVerifierSettingsEngine::DisableHKCULookupForIFEO(v4);
        }
        v2 = 0;
      }
      else
      {
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed writing key value\n");
      }
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Failed opening registry key. NTSTATUS: %08X\n", (unsigned int)v3);
    }
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Failed getting current user registry path. NTSTATUS: %08X\n", (unsigned int)v1);
  }
  if ( KeyPath.Buffer )
  {
    RtlFreeUnicodeString(&KeyPath);
    RtlInitUnicodeString(&KeyPath, 0);
  }
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002cc8  mov     [rsp-8+arg_18], rbx
0x180002ccd  mov     qword ptr [rsp-8+arg_0], rcx
0x180002cd2  push    rbp
0x180002cd3  mov     rbp, rsp
0x180002cd6  sub     rsp, 40h
0x180002cda  mov     [rbp+KeyHandle], 0
0x180002ce2  mov     [rbp+Handle], 0
0x180002cea  xorps   xmm0, xmm0
0x180002ced  movups  xmmword ptr [rbp+KeyPath.Length], xmm0
0x180002cf1  mov     [rbp+arg_0], 0
0x180002cf8  lea     rcx, [rbp+KeyPath]; KeyPath
0x180002cfc  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180002d02  mov     ebx, eax
0x180002d04  test    eax, eax
0x180002d06  jns     short loc_180002D24
0x180002d08  lea     r8, aWerdiagFailedG; "WERDIAG: Failed getting current user re"...
0x180002d0f  mov     r9d, eax
0x180002d12  xor     edx, edx; Level
0x180002d14  mov     ecx, 96h; ComponentId
0x180002d19  call    cs:__imp_DbgPrintEx
0x180002d1f  jmp     loc_180002DE3
0x180002d24  lea     rax, [rbp+KeyHandle]
0x180002d28  mov     [rsp+40h+var_20], rax; KeyHandle
0x180002d2d  xor     r9d, r9d
0x180002d30  mov     r8, [rbp+KeyPath.Buffer]
0x180002d34  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x180002d3b  lea     ecx, [r9+2]; DesiredAccess
0x180002d3f  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x180002d44  mov     ebx, eax
0x180002d46  test    eax, eax
0x180002d48  jns     short loc_180002D53
0x180002d4a  lea     r8, aWerdiagFailedO_5; "WERDIAG: Failed opening registry key. N"...
0x180002d51  jmp     short loc_180002D0F
0x180002d53  xor     r8d, r8d; unsigned int
0x180002d56  lea     rdx, aAutoverifieren; "AutoverifierEnabled"
0x180002d5d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180002d61  call    ?PluginsNtSetRegDwordValue@@YAJPEAXPEB_WK@Z; PluginsNtSetRegDwordValue(void *,wchar_t const *,ulong)
0x180002d66  mov     ebx, eax
0x180002d68  test    eax, eax
0x180002d6a  jns     short loc_180002D82
0x180002d6c  lea     r8, aWerdiagFailedW; "WERDIAG: Failed writing key value\n"
0x180002d73  xor     edx, edx; Level
0x180002d75  mov     ecx, 96h; ComponentId
0x180002d7a  call    cs:__imp_DbgPrintEx
0x180002d80  jmp     short loc_180002DE3
0x180002d82  lea     rax, [rbp+Handle]
0x180002d86  mov     [rsp+40h+var_20], rax; KeyHandle
0x180002d8b  xor     r9d, r9d
0x180002d8e  xor     r8d, r8d
0x180002d91  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180002d98  lea     ecx, [r9+1]; DesiredAccess
0x180002d9c  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x180002da1  test    eax, eax
0x180002da3  js      short loc_180002DDC
0x180002da5  lea     r8, [rbp+arg_0]; unsigned int *
0x180002da9  lea     rdx, aImageexecution; "ImageExecutionOptions"
0x180002db0  mov     rcx, [rbp+Handle]; KeyHandle
0x180002db4  call    ?PluginsNtGetRegDwordValue@@YAJPEAXPEB_WPEAK@Z; PluginsNtGetRegDwordValue(void *,wchar_t const *,ulong *)
0x180002db9  test    eax, eax
0x180002dbb  js      short loc_180002DDC
0x180002dbd  cmp     [rbp+arg_0], 0
0x180002dc1  jz      short loc_180002DDC
0x180002dc3  lea     r8, aWerdiagNotDisa; "WERDIAG: Not disabling HKCU IFEO look-u"...
0x180002dca  mov     edx, 3; Level
0x180002dcf  mov     ecx, 96h; ComponentId
0x180002dd4  call    cs:__imp_DbgPrintEx
0x180002dda  jmp     short loc_180002DE1
0x180002ddc  call    ?DisableHKCULookupForIFEO@CAutoVerifierSettingsEngine@@AEAAJXZ; CAutoVerifierSettingsEngine::DisableHKCULookupForIFEO(void)
0x180002de1  xor     ebx, ebx
0x180002de3  cmp     [rbp+KeyPath.Buffer], 0
0x180002de8  jz      short loc_180002E01
0x180002dea  lea     rcx, [rbp+KeyPath]; UnicodeString
0x180002dee  call    cs:__imp_RtlFreeUnicodeString
0x180002df4  xor     edx, edx; SourceString
0x180002df6  lea     rcx, [rbp+KeyPath]; DestinationString
0x180002dfa  call    cs:__imp_RtlInitUnicodeString
0x180002e00  nop
0x180002e01  mov     rcx, [rbp+Handle]; Handle
0x180002e05  test    rcx, rcx
0x180002e08  jz      short loc_180002E11
0x180002e0a  call    cs:__imp_NtClose
0x180002e10  nop
0x180002e11  mov     rcx, [rbp+KeyHandle]; Handle
0x180002e15  test    rcx, rcx
0x180002e18  jz      short loc_180002E20
0x180002e1a  call    cs:__imp_NtClose
0x180002e20  mov     eax, ebx
0x180002e22  mov     rbx, [rsp+40h+arg_18]
0x180002e27  add     rsp, 40h
0x180002e2b  pop     rbp
0x180002e2c  retn
```
