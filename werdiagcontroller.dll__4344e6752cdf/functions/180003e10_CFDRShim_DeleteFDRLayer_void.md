# CFDRShim::DeleteFDRLayer(void)

- ea: `0x180003e10`
- end: `0x180004016`
- name: `?DeleteFDRLayer@CFDRShim@@QEAAJXZ`
- size: `518`
- prototype: `__int64 __fastcall(CFDRShim *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000202c`
- `0x180003b98`

## callees

- `0x180001cd4`
- `0x180003e10`
- `0x1800052d0`
- `0x180005a9c`
- `0x180005d24`
- `0x18000606c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180003f78`
- `ntdll!RtlInitUnicodeString` at `0x180003fbd`
- `ntdll!RtlInitUnicodeString` at `0x180003f78`
- `ntdll!RtlInitUnicodeString` at `0x180003fbd`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180003e52`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180003e52`
- `ntdll!NtClose` at `0x180004001`
- `ntdll!NtClose` at `0x180004001`
- `ntdll!DbgPrintEx` at `0x180003f02`
- `ntdll!DbgPrintEx` at `0x180003f38`
- `ntdll!DbgPrintEx` at `0x180003fa2`
- `ntdll!DbgPrintEx` at `0x180003f02`
- `ntdll!DbgPrintEx` at `0x180003f38`
- `ntdll!DbgPrintEx` at `0x180003fa2`
- `ntdll!NtDeleteValueKey` at `0x180003f86`
- `ntdll!NtDeleteValueKey` at `0x180003fcb`
- `ntdll!NtDeleteValueKey` at `0x180003f86`
- `ntdll!NtDeleteValueKey` at `0x180003fcb`

## string_xrefs

- `0x180003e7e`: `WERDIAG: Failed opening registry key. NTSTATUS: %08X\n`
- `0x180003ef4`: `WERDIAG: PluginsNtGetRegStringValue failed. NTSTATUS: %08X\n`
- `0x180003ec5`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x180003e68`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\FDR\CurrentSession`
- `0x180003e92`: `AppPath`
- `0x180003f91`: `WERDIAG: Failed reading string value from registry. NTSTATUS: %08X\n`
- `0x180003f2a`: `WERDIAG: UtilRemoveAppCompatLayerFromList failed. HRESULT: %08X\n`
- `0x180003f68`: `WERDIAG: PluginsNtSetRegStringValue failed. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 __fastcall CFDRShim::DeleteFDRLayer(CFDRShim *this)
{
  wchar_t *v1; // rdi
  void *v2; // r14
  wchar_t *v3; // rsi
  int v4; // eax
  int v5; // ebx
  int RegStringValue; // eax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+40h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+90h] [rbp+38h] BYREF
  void *v17; // [rsp+98h] [rbp+40h]
  wchar_t *v18; // [rsp+A0h] [rbp+48h] BYREF
  PCWSTR SourceString; // [rsp+A8h] [rbp+50h]

  KeyHandle = 0;
  SourceString = 0;
  KeyPath = 0;
  v1 = 0;
  v2 = 0;
  DestinationString = 0;
  v17 = 0;
  v3 = 0;
  v18 = 0;
  RtlFormatCurrentUserKeyPath(&KeyPath);
  v4 = PluginsNtOpenKey(
         3u,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\FDR\\CurrentSession",
         &KeyHandle);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_2;
  RegStringValue = PluginsNtGetRegStringValue(KeyHandle);
  v1 = (wchar_t *)SourceString;
  v5 = RegStringValue;
  if ( RegStringValue < 0 || !SourceString )
  {
    DbgPrintEx(
      0x96u,
      0,
      "WERDIAG: Failed reading string value from registry. NTSTATUS: %08X\n",
      (unsigned int)RegStringValue);
LABEL_17:
    v11 = v5 | 0x10000000;
    if ( v11 >= 0 )
      goto LABEL_20;
    goto LABEL_18;
  }
  v4 = PluginsNtOpenKey(3u, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers", &KeyHandle);
  v5 = v4;
  if ( v4 < 0 )
  {
LABEL_2:
    DbgPrintEx(0x96u, 0, "WERDIAG: Failed opening registry key. NTSTATUS: %08X\n", (unsigned int)v4);
    goto LABEL_17;
  }
  v7 = PluginsNtGetRegStringValue(KeyHandle);
  v5 = v7;
  if ( v7 < 0 )
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: PluginsNtGetRegStringValue failed. NTSTATUS: %08X\n", v7);
    v2 = v17;
    goto LABEL_17;
  }
  v2 = v17;
  v10 = RemoveAppCompatLayerFromList(v17, v8, v9, &v18);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v3 = v18;
    if ( v18 && *v18 )
    {
      v12 = PluginsNtSetRegStringValue(KeyHandle, v1, v18);
      v5 = v12;
      if ( v12 < 0 )
      {
        DbgPrintEx(0x96u, 0, "WERDIAG: PluginsNtSetRegStringValue failed. NTSTATUS: %08X\n", (unsigned int)v12);
        goto LABEL_17;
      }
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, v1);
      NtDeleteValueKey(KeyHandle, &DestinationString);
    }
    v11 = 0;
    goto LABEL_20;
  }
  DbgPrintEx(0x96u, 0, "WERDIAG: UtilRemoveAppCompatLayerFromList failed. HRESULT: %08X\n", v10);
  v3 = v18;
LABEL_18:
  if ( KeyHandle )
  {
    RtlInitUnicodeString(&DestinationString, v1);
    NtDeleteValueKey(KeyHandle, &DestinationString);
  }
LABEL_20:
  if ( v3 )
    operator delete[](v3);
  if ( v2 )
    operator delete[](v2);
  if ( v1 )
    operator delete[](v1);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003e10  mov     [rsp-30h+KeyHandle], rcx
0x180003e15  push    rbp
0x180003e16  push    rbx
0x180003e17  push    rsi
0x180003e18  push    rdi
0x180003e19  push    r14
0x180003e1b  push    r15
0x180003e1d  mov     rbp, rsp
0x180003e20  sub     rsp, 58h
0x180003e24  xor     r15d, r15d
0x180003e27  lea     rcx, [rbp+KeyPath]; KeyPath
0x180003e2b  xorps   xmm0, xmm0
0x180003e2e  mov     [rbp+KeyHandle], r15
0x180003e32  xorps   xmm1, xmm1
0x180003e35  mov     [rbp+SourceString], r15
0x180003e39  movups  xmmword ptr [rbp+KeyPath.Length], xmm0
0x180003e3d  mov     edi, r15d
0x180003e40  mov     r14d, r15d
0x180003e43  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180003e47  mov     [rbp+arg_8], r15
0x180003e4b  mov     esi, r15d
0x180003e4e  mov     [rbp+arg_10], r15
0x180003e52  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180003e58  mov     r8, [rbp+KeyPath.Buffer]
0x180003e5c  lea     rax, [rbp+KeyHandle]
0x180003e60  xor     r9d, r9d
0x180003e63  mov     [rsp+58h+var_38], rax; KeyHandle
0x180003e68  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x180003e6f  lea     ecx, [r15+3]; DesiredAccess
0x180003e73  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x180003e78  mov     ebx, eax
0x180003e7a  test    eax, eax
0x180003e7c  jns     short loc_180003E8A
0x180003e7e  lea     r8, aWerdiagFailedO_5; "WERDIAG: Failed opening registry key. N"...
0x180003e85  jmp     loc_180003F98
0x180003e8a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180003e8e  lea     r8, [rbp+SourceString]
0x180003e92  lea     rdx, aApppath; "AppPath"
0x180003e99  call    ?PluginsNtGetRegStringValue@@YAJPEAXPEB_WPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; PluginsNtGetRegStringValue(void *,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x180003e9e  mov     rdi, [rbp+SourceString]
0x180003ea2  mov     ebx, eax
0x180003ea4  test    eax, eax
0x180003ea6  js      loc_180003F91
0x180003eac  test    rdi, rdi
0x180003eaf  jz      loc_180003F91
0x180003eb5  mov     r8, [rbp+KeyPath.Buffer]
0x180003eb9  lea     rax, [rbp+KeyHandle]
0x180003ebd  xor     r9d, r9d
0x180003ec0  mov     [rsp+58h+var_38], rax; KeyHandle
0x180003ec5  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x180003ecc  lea     ecx, [r9+3]; DesiredAccess
0x180003ed0  call    ?PluginsNtOpenKey@@YAJKPEB_WPEA_WPEAXPEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; PluginsNtOpenKey(ulong,wchar_t const *,wchar_t *,void *,tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&NtClose(void *),0>> *)
0x180003ed5  mov     ebx, eax
0x180003ed7  test    eax, eax
0x180003ed9  js      short loc_180003E7E
0x180003edb  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180003edf  lea     r8, [rbp+arg_8]
0x180003ee3  mov     rdx, rdi
0x180003ee6  call    ?PluginsNtGetRegStringValue@@YAJPEAXPEB_WPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; PluginsNtGetRegStringValue(void *,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x180003eeb  mov     ebx, eax
0x180003eed  test    eax, eax
0x180003eef  jns     short loc_180003F11
0x180003ef1  mov     r9d, eax
0x180003ef4  lea     r8, aWerdiagPlugins; "WERDIAG: PluginsNtGetRegStringValue fai"...
0x180003efb  xor     edx, edx; Level
0x180003efd  mov     ecx, 96h; ComponentId
0x180003f02  call    cs:__imp_DbgPrintEx
0x180003f08  mov     r14, [rbp+arg_8]
0x180003f0c  jmp     loc_180003FA8
0x180003f11  mov     r14, [rbp+arg_8]
0x180003f15  lea     r9, [rbp+arg_10]
0x180003f19  mov     rcx, r14
0x180003f1c  call    RemoveAppCompatLayerFromList
0x180003f21  mov     ebx, eax
0x180003f23  test    eax, eax
0x180003f25  jns     short loc_180003F44
0x180003f27  mov     r9d, eax
0x180003f2a  lea     r8, aWerdiagUtilrem; "WERDIAG: UtilRemoveAppCompatLayerFromLi"...
0x180003f31  xor     edx, edx; Level
0x180003f33  mov     ecx, 96h; ComponentId
0x180003f38  call    cs:__imp_DbgPrintEx
0x180003f3e  mov     rsi, [rbp+arg_10]
0x180003f42  jmp     short loc_180003FB0
0x180003f44  mov     rsi, [rbp+arg_10]
0x180003f48  test    rsi, rsi
0x180003f4b  jz      short loc_180003F71
0x180003f4d  cmp     [rsi], r15w
0x180003f51  jz      short loc_180003F71
0x180003f53  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180003f57  mov     r8, rsi; wchar_t *
0x180003f5a  mov     rdx, rdi; wchar_t *
0x180003f5d  call    ?PluginsNtSetRegStringValue@@YAJPEAXPEB_W1@Z; PluginsNtSetRegStringValue(void *,wchar_t const *,wchar_t const *)
0x180003f62  mov     ebx, eax
0x180003f64  test    eax, eax
0x180003f66  jns     short loc_180003F8C
0x180003f68  lea     r8, aWerdiagPlugins_0; "WERDIAG: PluginsNtSetRegStringValue fai"...
0x180003f6f  jmp     short loc_180003F98
0x180003f71  mov     rdx, rdi; SourceString
0x180003f74  lea     rcx, [rbp+DestinationString]; DestinationString
0x180003f78  call    cs:__imp_RtlInitUnicodeString
0x180003f7e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180003f82  lea     rdx, [rbp+DestinationString]; ValueName
0x180003f86  call    cs:__imp_NtDeleteValueKey
0x180003f8c  mov     ebx, r15d
0x180003f8f  jmp     short loc_180003FD1
0x180003f91  lea     r8, aWerdiagFailedR; "WERDIAG: Failed reading string value fr"...
0x180003f98  mov     r9d, eax
0x180003f9b  xor     edx, edx; Level
0x180003f9d  mov     ecx, 96h; ComponentId
0x180003fa2  call    cs:__imp_DbgPrintEx
0x180003fa8  or      ebx, 10000000h
0x180003fae  jge     short loc_180003FD1
0x180003fb0  cmp     [rbp+KeyHandle], r15
0x180003fb4  jz      short loc_180003FD1
0x180003fb6  mov     rdx, rdi; SourceString
0x180003fb9  lea     rcx, [rbp+DestinationString]; DestinationString
0x180003fbd  call    cs:__imp_RtlInitUnicodeString
0x180003fc3  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180003fc7  lea     rdx, [rbp+DestinationString]; ValueName
0x180003fcb  call    cs:__imp_NtDeleteValueKey
0x180003fd1  test    rsi, rsi
0x180003fd4  jz      short loc_180003FDE
0x180003fd6  mov     rcx, rsi; void *
0x180003fd9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003fde  test    r14, r14
0x180003fe1  jz      short loc_180003FEB
0x180003fe3  mov     rcx, r14; void *
0x180003fe6  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003feb  test    rdi, rdi
0x180003fee  jz      short loc_180003FF8
0x180003ff0  mov     rcx, rdi; void *
0x180003ff3  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003ff8  mov     rcx, [rbp+KeyHandle]; Handle
0x180003ffc  test    rcx, rcx
0x180003fff  jz      short loc_180004007
0x180004001  call    cs:__imp_NtClose
0x180004007  mov     eax, ebx
0x180004009  add     rsp, 58h
0x18000400d  pop     r15
0x18000400f  pop     r14
0x180004011  pop     rdi
0x180004012  pop     rsi
0x180004013  pop     rbx
0x180004014  pop     rbp
0x180004015  retn
```
