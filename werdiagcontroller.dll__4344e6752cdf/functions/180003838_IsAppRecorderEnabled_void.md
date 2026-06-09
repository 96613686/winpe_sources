# IsAppRecorderEnabled(void)

- ea: `0x180003838`
- end: `0x180003915`
- name: `?IsAppRecorderEnabled@@YAHXZ`
- size: `221`
- prototype: `_BOOL8(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000202c`
- `0x180003a70`

## callees

- `0x180003838`
- `0x180005990`
- `0x180005d24`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800038e2`
- `ntdll!RtlFreeUnicodeString` at `0x1800038e2`
- `ntdll!RtlInitUnicodeString` at `0x1800038ee`
- `ntdll!RtlInitUnicodeString` at `0x1800038ee`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18000385e`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18000385e`
- `ntdll!NtClose` at `0x1800038fd`
- `ntdll!NtClose` at `0x1800038fd`
- `ntdll!DbgPrintEx` at `0x180003879`
- `ntdll!DbgPrintEx` at `0x180003879`

## string_xrefs

- `0x180003868`: `WERDIAG: AppRecorder: Failed getting current user registry path. NTSTATUS: %08X\n`
- `0x180003891`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`

## pseudocode

```c
_BOOL8 IsAppRecorderEnabled(void)
{
  BOOL v0; // ebx
  NTSTATUS v1; // eax
  int v2; // eax
  int RegDwordValue; // eax
  struct _UNICODE_STRING KeyPath; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v6; // [rsp+50h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp+18h] BYREF

  v0 = 0;
  Handle = 0;
  v6 = 0;
  KeyPath = 0;
  v1 = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( v1 >= 0 )
  {
    v2 = PluginsNtOpenKey(1u, L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder", &Handle);
    if ( v2 >= 0 )
    {
      RegDwordValue = PluginsNtGetRegDwordValue(Handle, L"AppRecorderEnabled", &v6);
      if ( RegDwordValue >= 0 )
        v0 = v6 == 1;
      else
        DbgPrintEx(
          0x96u,
          0,
          "WERDIAG: AppRecorder: AppRecorder enabled flag is not present. NTSTATUS: %08X\n",
          (unsigned int)RegDwordValue);
    }
    else
    {
      DbgPrintEx(
        0x96u,
        0,
        "WERDIAG: AppRecorder: AppRecorder settings key is not present. NTSTATUS: %08X\n",
        (unsigned int)v2);
    }
  }
  else
  {
    DbgPrintEx(
      0x96u,
      0,
      "WERDIAG: AppRecorder: Failed getting current user registry path. NTSTATUS: %08X\n",
      (unsigned int)v1);
  }
  if ( KeyPath.Buffer )
  {
    RtlFreeUnicodeString(&KeyPath);
    RtlInitUnicodeString(&KeyPath, 0);
  }
  if ( Handle )
    NtClose(Handle);
  return v0;
}

```

## disassembly

```asm
0x180003838  mov     [rsp-8+arg_10], rbx
0x18000383d  mov     [rsp-8+arg_18], rsi
0x180003842  push    rbp
0x180003843  mov     rbp, rsp
0x180003846  sub     rsp, 40h
0x18000384a  xor     ebx, ebx
0x18000384c  lea     rcx, [rbp+KeyPath]; KeyPath
0x180003850  xorps   xmm0, xmm0
0x180003853  mov     [rbp+Handle], rbx
0x180003857  mov     [rbp+arg_0], ebx
0x18000385a  movups  xmmword ptr [rbp+KeyPath.Length], xmm0
0x18000385e  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180003864  test    eax, eax
0x180003866  jns     short loc_180003881
0x180003868  lea     r8, aWerdiagAppreco_17; "WERDIAG: AppRecorder: Failed getting cu"...
0x18000386f  mov     r9d, eax
0x180003872  xor     edx, edx; Level
0x180003874  mov     ecx, 96h; ComponentId
0x180003879  call    cs:__imp_DbgPrintEx
0x18000387f  jmp     short loc_1800038D7
0x180003881  mov     r8, [rbp+KeyPath.Buffer]
0x180003885  lea     rax, [rbp+Handle]
0x180003889  xor     r9d, r9d
0x18000388c  mov     [rsp+40h+KeyHandle], rax; KeyHandle
0x180003891  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\Windows E"...
0x180003898  lea     esi, [r9+1]
0x18000389c  mov     ecx, esi; DesiredAccess
0x18000389e  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x1800038a3  test    eax, eax
0x1800038a5  jns     short loc_1800038B0
0x1800038a7  lea     r8, aWerdiagAppreco_5; "WERDIAG: AppRecorder: AppRecorder setti"...
0x1800038ae  jmp     short loc_18000386F
0x1800038b0  mov     rcx, [rbp+Handle]; KeyHandle
0x1800038b4  lea     r8, [rbp+arg_0]; unsigned int *
0x1800038b8  lea     rdx, aApprecorderena; "AppRecorderEnabled"
0x1800038bf  call    ?PluginsNtGetRegDwordValue@@YAJPEAXPEB_WPEAK@Z; PluginsNtGetRegDwordValue(void *,wchar_t const *,ulong *)
0x1800038c4  test    eax, eax
0x1800038c6  jns     short loc_1800038D1
0x1800038c8  lea     r8, aWerdiagAppreco_3; "WERDIAG: AppRecorder: AppRecorder enabl"...
0x1800038cf  jmp     short loc_18000386F
0x1800038d1  cmp     [rbp+arg_0], esi
0x1800038d4  cmovz   ebx, esi
0x1800038d7  cmp     [rbp+KeyPath.Buffer], 0
0x1800038dc  jz      short loc_1800038F4
0x1800038de  lea     rcx, [rbp+KeyPath]; UnicodeString
0x1800038e2  call    cs:__imp_RtlFreeUnicodeString
0x1800038e8  xor     edx, edx; SourceString
0x1800038ea  lea     rcx, [rbp+KeyPath]; DestinationString
0x1800038ee  call    cs:__imp_RtlInitUnicodeString
0x1800038f4  mov     rcx, [rbp+Handle]; Handle
0x1800038f8  test    rcx, rcx
0x1800038fb  jz      short loc_180003903
0x1800038fd  call    cs:__imp_NtClose
0x180003903  mov     rsi, [rsp+40h+arg_18]
0x180003908  mov     eax, ebx
0x18000390a  mov     rbx, [rsp+40h+arg_10]
0x18000390f  add     rsp, 40h
0x180003913  pop     rbp
0x180003914  retn
```
