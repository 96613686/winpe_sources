# SetLogConfig

- ea: `0x140001a10`
- end: `0x140001a8d`
- name: `SetLogConfig`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x140001674`
- `0x140001748`

## callees

- `0x140001a10`
- `0x140003944`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x140001a5c`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140001a5c`

## string_xrefs

- `0x140001a71`: `Failed to set registry log configuration (0x%08X)`
- `0x140001a4b`: `LogConfig`

## pseudocode

```c
__int64 __fastcall SetLogConfig(__int64 a1)
{
  ULONG ValueLength; // ebx
  void *ValueData; // rax
  NTSTATUS v4; // eax
  unsigned int v5; // ebx

  ValueLength = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  ValueData = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  v4 = RtlWriteRegistryValue(2u, L"WinSetupMon", L"LogConfig", 3u, ValueData, ValueLength);
  v5 = v4;
  if ( v4 < 0 )
    WriteLogMessage(3, L"Failed to set registry log configuration (0x%08X)", (unsigned int)v4);
  return v5;
}

```

## disassembly

```asm
0x140001a10  mov     [rsp+arg_0], rbx
0x140001a15  push    rdi
0x140001a16  sub     rsp, 30h
0x140001a1a  mov     rax, [rcx]
0x140001a1d  mov     rdi, rcx
0x140001a20  mov     rax, [rax+18h]
0x140001a24  call    _guard_dispatch_icall
0x140001a29  mov     rdx, [rdi]
0x140001a2c  mov     ebx, eax
0x140001a2e  mov     rcx, rdi
0x140001a31  mov     rax, [rdx+10h]
0x140001a35  call    _guard_dispatch_icall
0x140001a3a  mov     edi, 3
0x140001a3f  mov     [rsp+38h+ValueLength], ebx; ValueLength
0x140001a43  mov     r9d, edi; ValueType
0x140001a46  mov     [rsp+38h+ValueData], rax; ValueData
0x140001a4b  lea     r8, ValueName; "LogConfig"
0x140001a52  lea     rdx, Path; "WinSetupMon"
0x140001a59  lea     ecx, [rdi-1]; RelativeTo
0x140001a5c  call    cs:__imp_RtlWriteRegistryValue
0x140001a63  nop     dword ptr [rax+rax+00h]
0x140001a68  mov     ebx, eax
0x140001a6a  test    eax, eax
0x140001a6c  jns     short loc_140001A7F
0x140001a6e  mov     r8d, eax
0x140001a71  lea     rdx, aFailedToSetReg; "Failed to set registry log configuratio"...
0x140001a78  mov     ecx, edi
0x140001a7a  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140001a7f  mov     eax, ebx
0x140001a81  mov     rbx, [rsp+38h+arg_0]
0x140001a86  add     rsp, 30h
0x140001a8a  pop     rdi
0x140001a8b  retn
```
