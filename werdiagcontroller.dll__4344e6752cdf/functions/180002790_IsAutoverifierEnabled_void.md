# IsAutoverifierEnabled(void)

- ea: `0x180002790`
- end: `0x1800028c9`
- name: `?IsAutoverifierEnabled@@YAHXZ`
- size: `313`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000202c`

## callees

- `0x180002790`
- `0x180005990`
- `0x180005d24`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180002896`
- `ntdll!RtlFreeUnicodeString` at `0x180002896`
- `ntdll!RtlInitUnicodeString` at `0x1800028a2`
- `ntdll!RtlInitUnicodeString` at `0x1800028a2`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800027b6`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800027b6`
- `ntdll!NtClose` at `0x1800028b1`
- `ntdll!NtClose` at `0x1800028b1`
- `ntdll!DbgPrintEx` at `0x1800027d1`
- `ntdll!DbgPrintEx` at `0x1800027ec`
- `ntdll!DbgPrintEx` at `0x18000280a`
- `ntdll!DbgPrintEx` at `0x180002885`
- `ntdll!DbgPrintEx` at `0x1800027d1`
- `ntdll!DbgPrintEx` at `0x1800027ec`
- `ntdll!DbgPrintEx` at `0x18000280a`
- `ntdll!DbgPrintEx` at `0x180002885`

## string_xrefs

- `0x1800027c5`: `WERDIAG: AutoVerifier: Failed getting current user registry path. NTSTATUS: %08X\n`
- `0x1800027e0`: `WERDIAG: AutoVerifier: Path is: %S\n`
- `0x1800027f2`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\Autoverifier`
- `0x180002820`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\Autoverifier`
- `0x180002837`: `WERDIAG: AutoVerifier: could not open settings key. NTSTATUS: %08X\n`
- `0x180002862`: `WERDIAG: AutoVerifier: could not read enabled flag. NTSTATUS: %08X\n`

## pseudocode

```c
_BOOL8 IsAutoverifierEnabled(void)
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
    DbgPrintEx(0x96u, 3u, "WERDIAG: AutoVerifier: Path is: %S\n", KeyPath.Buffer);
    DbgPrintEx(
      0x96u,
      3u,
      "WERDIAG: AutoVerifier: Subkey is: %S\n",
      L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\Autoverifier");
    v2 = PluginsNtOpenKey(
           1u,
           L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\Autoverifier",
           KeyPath.Buffer,
           0,
           &Handle);
    if ( v2 >= 0 )
    {
      RegDwordValue = PluginsNtGetRegDwordValue(Handle, L"AutoverifierEnabled", &v6);
      if ( RegDwordValue >= 0 )
      {
        v0 = v6 == 1;
        DbgPrintEx(0x96u, 3u, "WERDIAG: AutoVerifier: Enabled flag: %u\n", v6 == 1);
      }
      else
      {
        DbgPrintEx(
          0x96u,
          0,
          "WERDIAG: AutoVerifier: could not read enabled flag. NTSTATUS: %08X\n",
          (unsigned int)RegDwordValue);
      }
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: AutoVerifier: could not open settings key. NTSTATUS: %08X\n", (unsigned int)v2);
    }
  }
  else
  {
    DbgPrintEx(
      0x96u,
      0,
      "WERDIAG: AutoVerifier: Failed getting current user registry path. NTSTATUS: %08X\n",
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
0x180002790  mov     [rsp-8+arg_10], rbx
0x180002795  mov     [rsp-8+arg_18], r14
0x18000279a  push    rbp
0x18000279b  mov     rbp, rsp
0x18000279e  sub     rsp, 40h
0x1800027a2  xor     ebx, ebx
0x1800027a4  lea     rcx, [rbp+KeyPath]; KeyPath
0x1800027a8  xorps   xmm0, xmm0
0x1800027ab  mov     [rbp+Handle], rbx
0x1800027af  mov     [rbp+arg_0], ebx
0x1800027b2  movups  xmmword ptr [rbp+KeyPath.Length], xmm0
0x1800027b6  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800027bc  mov     ecx, 96h; ComponentId
0x1800027c1  test    eax, eax
0x1800027c3  jns     short loc_1800027DC
0x1800027c5  lea     r8, aWerdiagAutover; "WERDIAG: AutoVerifier: Failed getting c"...
0x1800027cc  mov     r9d, eax
0x1800027cf  xor     edx, edx; Level
0x1800027d1  call    cs:__imp_DbgPrintEx
0x1800027d7  jmp     loc_18000288B
0x1800027dc  mov     r9, [rbp+KeyPath.Buffer]
0x1800027e0  lea     r8, aWerdiagAutover_3; "WERDIAG: AutoVerifier: Path is: %S\n"
0x1800027e7  mov     edx, 3; Level
0x1800027ec  call    cs:__imp_DbgPrintEx
0x1800027f2  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800027f9  mov     edx, 3; Level
0x1800027fe  lea     r8, aWerdiagAutover_1; "WERDIAG: AutoVerifier: Subkey is: %S\n"
0x180002805  mov     ecx, 96h; ComponentId
0x18000280a  call    cs:__imp_DbgPrintEx
0x180002810  mov     r8, [rbp+KeyPath.Buffer]
0x180002814  lea     rax, [rbp+Handle]
0x180002818  xor     r9d, r9d
0x18000281b  mov     [rsp+40h+KeyHandle], rax; KeyHandle
0x180002820  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x180002827  lea     r14d, [r9+1]
0x18000282b  mov     ecx, r14d; DesiredAccess
0x18000282e  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x180002833  test    eax, eax
0x180002835  jns     short loc_180002845
0x180002837  lea     r8, aWerdiagAutover_4; "WERDIAG: AutoVerifier: could not open s"...
0x18000283e  mov     ecx, 96h
0x180002843  jmp     short loc_1800027CC
0x180002845  mov     rcx, [rbp+Handle]; KeyHandle
0x180002849  lea     r8, [rbp+arg_0]; unsigned int *
0x18000284d  lea     rdx, aAutoverifieren; "AutoverifierEnabled"
0x180002854  call    ?PluginsNtGetRegDwordValue@@YAJPEAXPEB_WPEAK@Z; PluginsNtGetRegDwordValue(void *,wchar_t const *,ulong *)
0x180002859  mov     ecx, 96h; ComponentId
0x18000285e  test    eax, eax
0x180002860  jns     short loc_18000286E
0x180002862  lea     r8, aWerdiagAutover_2; "WERDIAG: AutoVerifier: could not read e"...
0x180002869  jmp     loc_1800027CC
0x18000286e  cmp     [rbp+arg_0], r14d
0x180002872  lea     r8, aWerdiagAutover_0; "WERDIAG: AutoVerifier: Enabled flag: %u"...
0x180002879  mov     edx, 3; Level
0x18000287e  cmovz   ebx, r14d
0x180002882  mov     r9d, ebx
0x180002885  call    cs:__imp_DbgPrintEx
0x18000288b  cmp     [rbp+KeyPath.Buffer], 0
0x180002890  jz      short loc_1800028A8
0x180002892  lea     rcx, [rbp+KeyPath]; UnicodeString
0x180002896  call    cs:__imp_RtlFreeUnicodeString
0x18000289c  xor     edx, edx; SourceString
0x18000289e  lea     rcx, [rbp+KeyPath]; DestinationString
0x1800028a2  call    cs:__imp_RtlInitUnicodeString
0x1800028a8  mov     rcx, [rbp+Handle]; Handle
0x1800028ac  test    rcx, rcx
0x1800028af  jz      short loc_1800028B7
0x1800028b1  call    cs:__imp_NtClose
0x1800028b7  mov     r14, [rsp+40h+arg_18]
0x1800028bc  mov     eax, ebx
0x1800028be  mov     rbx, [rsp+40h+arg_10]
0x1800028c3  add     rsp, 40h
0x1800028c7  pop     rbp
0x1800028c8  retn
```
