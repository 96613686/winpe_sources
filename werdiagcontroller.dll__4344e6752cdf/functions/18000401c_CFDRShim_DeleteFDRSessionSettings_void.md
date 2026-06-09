# CFDRShim::DeleteFDRSessionSettings(void)

- ea: `0x18000401c`
- end: `0x1800040ac`
- name: `?DeleteFDRSessionSettings@CFDRShim@@AEAAJXZ`
- size: `144`
- prototype: `__int64 __fastcall(CFDRShim *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003b98`

## callees

- `0x18000401c`
- `0x180005d24`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18000403b`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18000403b`
- `ntdll!NtClose` at `0x18000409e`
- `ntdll!NtClose` at `0x18000409e`
- `ntdll!DbgPrintEx` at `0x18000407b`
- `ntdll!DbgPrintEx` at `0x18000407b`
- `ntdll!NtDeleteKey` at `0x18000408c`
- `ntdll!NtDeleteKey` at `0x18000408c`

## string_xrefs

- `0x180004053`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\FDR\CurrentSession`
- `0x18000406d`: `WERDIAG: Failed opening session registry key. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 __fastcall CFDRShim::DeleteFDRSessionSettings(CFDRShim *this)
{
  int v1; // eax
  int v2; // ebx
  unsigned int v3; // ebx
  struct _UNICODE_STRING v5; // [rsp+30h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+50h] [rbp+8h] BYREF

  KeyHandle = 0;
  v5 = 0;
  RtlFormatCurrentUserKeyPath(&v5);
  v1 = PluginsNtOpenKey(
         0x10002u,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\FDR\\CurrentSession",
         &KeyHandle);
  v2 = v1;
  if ( v1 >= 0 )
  {
    NtDeleteKey(KeyHandle);
    v3 = 0;
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Failed opening session registry key. NTSTATUS: %08X\n", v1);
    v3 = v2 | 0x10000000;
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v3;
}

```

## disassembly

```asm
0x18000401c  mov     rax, rsp
0x18000401f  mov     [rax+8], rcx
0x180004023  push    rbx
0x180004024  sub     rsp, 40h
0x180004028  xorps   xmm0, xmm0
0x18000402b  mov     qword ptr [rax+8], 0
0x180004033  lea     rcx, [rax-18h]; KeyPath
0x180004037  movups  xmmword ptr [rax-18h], xmm0
0x18000403b  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180004041  mov     r8, [rsp+48h+var_10]
0x180004046  lea     rax, [rsp+48h+KeyHandle]
0x18000404b  xor     r9d, r9d
0x18000404e  mov     [rsp+48h+var_28], rax; KeyHandle
0x180004053  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x18000405a  mov     ecx, 10002h; DesiredAccess
0x18000405f  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x180004064  mov     ebx, eax
0x180004066  test    eax, eax
0x180004068  jns     short loc_180004087
0x18000406a  mov     r9d, eax
0x18000406d  lea     r8, aWerdiagFailedO_4; "WERDIAG: Failed opening session registr"...
0x180004074  xor     edx, edx; Level
0x180004076  mov     ecx, 96h; ComponentId
0x18000407b  call    cs:__imp_DbgPrintEx
0x180004081  bts     ebx, 1Ch
0x180004085  jmp     short loc_180004094
0x180004087  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x18000408c  call    cs:__imp_NtDeleteKey
0x180004092  xor     ebx, ebx
0x180004094  mov     rcx, [rsp+48h+KeyHandle]; Handle
0x180004099  test    rcx, rcx
0x18000409c  jz      short loc_1800040A4
0x18000409e  call    cs:__imp_NtClose
0x1800040a4  mov     eax, ebx
0x1800040a6  add     rsp, 40h
0x1800040aa  pop     rbx
0x1800040ab  retn
```
