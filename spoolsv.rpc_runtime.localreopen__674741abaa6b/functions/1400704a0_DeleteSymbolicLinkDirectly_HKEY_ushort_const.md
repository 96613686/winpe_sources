# DeleteSymbolicLinkDirectly(HKEY__ *,ushort const *)

- ea: `0x1400704a0`
- end: `0x1400705d4`
- name: `?DeleteSymbolicLinkDirectly@@YAHPEAUHKEY__@@PEBG@Z`
- size: `308`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x1400702f8`

## callees

- `0x140015378`
- `0x1400704a0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x140070569`
- `ntdll!NtQueryValueKey` at `0x140070569`
- `ntdll!RtlInitUnicodeString` at `0x1400704d9`
- `ntdll!RtlInitUnicodeString` at `0x140070541`
- `ntdll!RtlInitUnicodeString` at `0x1400704d9`
- `ntdll!RtlInitUnicodeString` at `0x140070541`
- `ntdll!NtOpenKeyEx` at `0x140070518`
- `ntdll!NtOpenKeyEx` at `0x140070518`
- `ntdll!NtDeleteKey` at `0x140070585`
- `ntdll!NtDeleteKey` at `0x140070585`
- `ntdll!NtClose` at `0x1400705b2`
- `ntdll!NtClose` at `0x1400705b2`

## string_xrefs

- `0x14007059b`: `DeleteSymbolicLinkDirectly`
- `0x140070532`: `SymbolicLinkValue`
- `0x140070594`: `Found unexpected registry symbolic link %ws.`

## pseudocode

```c
_BOOL8 __fastcall DeleteSymbolicLinkDirectly(HKEY a1, const unsigned __int16 *a2)
{
  BOOL v4; // edi
  NTSTATUS v5; // eax
  NTSTATUS v6; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  __int128 v10; // [rsp+50h] [rbp-30h] BYREF
  __int128 v11; // [rsp+60h] [rbp-20h]
  __int128 v12; // [rsp+70h] [rbp-10h]
  ULONG ResultLength; // [rsp+A0h] [rbp+20h] BYREF
  HANDLE KeyHandle; // [rsp+B0h] [rbp+30h] BYREF

  KeyHandle = 0;
  v4 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  LODWORD(v10) = 48;
  *(_QWORD *)&v11 = &DestinationString;
  *((_QWORD *)&v10 + 1) = a1;
  DWORD2(v11) = 320;
  v12 = 0;
  if ( (int)NtOpenKeyEx(&KeyHandle, 0x2000000, &v10, 8) >= 0 )
  {
    ResultLength = 0;
    ValueName = 0;
    RtlInitUnicodeString(&ValueName, L"SymbolicLinkValue");
    v5 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( ResultLength && v5 != -1073741772 )
    {
      v6 = NtDeleteKey(KeyHandle);
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "DeleteSymbolicLinkDirectly",
        L"Found unexpected registry symbolic link %ws.",
        a2);
      v4 = v6 >= 0;
    }
    NtClose(KeyHandle);
  }
  return v4;
}

```

## disassembly

```asm
0x1400704a0  mov     [rsp-18h+arg_8], rbx
0x1400704a5  push    rbp
0x1400704a6  push    rsi
0x1400704a7  push    rdi
0x1400704a8  mov     rbp, rsp
0x1400704ab  sub     rsp, 80h
0x1400704b2  xorps   xmm0, xmm0
0x1400704b5  mov     [rbp+KeyHandle], 0
0x1400704bd  mov     rbx, rcx
0x1400704c0  mov     rsi, rdx
0x1400704c3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400704c7  xor     edi, edi
0x1400704c9  movups  [rbp+var_30], xmm0
0x1400704cd  movups  [rbp+var_20], xmm0
0x1400704d1  movups  [rbp+var_10], xmm0
0x1400704d5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400704d9  call    cs:__imp_RtlInitUnicodeString
0x1400704e0  nop     dword ptr [rax+rax+00h]
0x1400704e5  lea     rax, [rbp+DestinationString]
0x1400704e9  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1400704f0  xorps   xmm0, xmm0
0x1400704f3  mov     qword ptr [rbp+var_20], rax
0x1400704f7  lea     r9d, [rdi+8]
0x1400704fb  mov     qword ptr [rbp+var_30+8], rbx
0x1400704ff  lea     r8, [rbp+var_30]
0x140070503  mov     dword ptr [rbp+var_20+8], 140h
0x14007050a  mov     edx, 2000000h
0x14007050f  lea     rcx, [rbp+KeyHandle]
0x140070513  movdqu  [rbp+var_10], xmm0
0x140070518  call    cs:__imp_NtOpenKeyEx
0x14007051f  nop     dword ptr [rax+rax+00h]
0x140070524  test    eax, eax
0x140070526  js      loc_1400705BE
0x14007052c  xorps   xmm0, xmm0
0x14007052f  mov     [rbp+arg_0], edi
0x140070532  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x140070539  lea     rcx, [rbp+ValueName]; DestinationString
0x14007053d  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140070541  call    cs:__imp_RtlInitUnicodeString
0x140070548  nop     dword ptr [rax+rax+00h]
0x14007054d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140070551  lea     rax, [rbp+arg_0]
0x140070555  mov     [rsp+80h+ResultLength], rax; ResultLength
0x14007055a  lea     r8d, [rdi+2]; KeyValueInformationClass
0x14007055e  xor     r9d, r9d; KeyValueInformation
0x140070561  mov     [rsp+80h+Length], edi; Length
0x140070565  lea     rdx, [rbp+ValueName]; ValueName
0x140070569  call    cs:__imp_NtQueryValueKey
0x140070570  nop     dword ptr [rax+rax+00h]
0x140070575  cmp     [rbp+arg_0], edi
0x140070578  jbe     short loc_1400705AE
0x14007057a  cmp     eax, 0C0000034h
0x14007057f  jz      short loc_1400705AE
0x140070581  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140070585  call    cs:__imp_NtDeleteKey
0x14007058c  nop     dword ptr [rax+rax+00h]
0x140070591  mov     r8, rsi
0x140070594  lea     rdx, aFoundUnexpecte; "Found unexpected registry symbolic link"...
0x14007059b  lea     rcx, aDeletesymbolic; "DeleteSymbolicLinkDirectly"
0x1400705a2  mov     edi, eax
0x1400705a4  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400705a9  not     edi
0x1400705ab  shr     edi, 1Fh
0x1400705ae  mov     rcx, [rbp+KeyHandle]; Handle
0x1400705b2  call    cs:__imp_NtClose
0x1400705b9  nop     dword ptr [rax+rax+00h]
0x1400705be  mov     rbx, [rsp+80h+arg_8]
0x1400705c6  mov     eax, edi
0x1400705c8  add     rsp, 80h
0x1400705cf  pop     rdi
0x1400705d0  pop     rsi
0x1400705d1  pop     rbp
0x1400705d2  retn
```
