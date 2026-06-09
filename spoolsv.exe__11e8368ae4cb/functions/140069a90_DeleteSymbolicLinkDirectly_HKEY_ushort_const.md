# DeleteSymbolicLinkDirectly(HKEY__ *,ushort const *)

- ea: `0x140069a90`
- end: `0x140069b9b`
- name: `?DeleteSymbolicLinkDirectly@@YAHPEAUHKEY__@@PEBG@Z`
- size: `267`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x140069910`

## callees

- `0x1400140cc`
- `0x140069a90`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x140069b43`
- `ntdll!NtQueryValueKey` at `0x140069b43`
- `ntdll!RtlInitUnicodeString` at `0x140069ac9`
- `ntdll!RtlInitUnicodeString` at `0x140069b21`
- `ntdll!RtlInitUnicodeString` at `0x140069ac9`
- `ntdll!RtlInitUnicodeString` at `0x140069b21`
- `ntdll!NtOpenKeyEx` at `0x140069b02`
- `ntdll!NtOpenKeyEx` at `0x140069b02`
- `ntdll!NtDeleteKey` at `0x140069b59`
- `ntdll!NtDeleteKey` at `0x140069b59`
- `ntdll!NtClose` at `0x140069b80`
- `ntdll!NtClose` at `0x140069b80`

## string_xrefs

- `0x140069b62`: `Found unexpected registry symbolic link %ws.`
- `0x140069b69`: `DeleteSymbolicLinkDirectly`
- `0x140069b12`: `SymbolicLinkValue`

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
0x140069a90  mov     [rsp-18h+arg_8], rbx
0x140069a95  push    rbp
0x140069a96  push    rsi
0x140069a97  push    rdi
0x140069a98  mov     rbp, rsp
0x140069a9b  sub     rsp, 80h
0x140069aa2  xorps   xmm0, xmm0
0x140069aa5  mov     [rbp+KeyHandle], 0
0x140069aad  mov     rbx, rcx
0x140069ab0  mov     rsi, rdx
0x140069ab3  lea     rcx, [rbp+DestinationString]; DestinationString
0x140069ab7  xor     edi, edi
0x140069ab9  movups  [rbp+var_30], xmm0
0x140069abd  movups  [rbp+var_20], xmm0
0x140069ac1  movups  [rbp+var_10], xmm0
0x140069ac5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140069ac9  call    cs:__imp_RtlInitUnicodeString
0x140069acf  lea     rax, [rbp+DestinationString]
0x140069ad3  mov     dword ptr [rbp+var_30], 30h ; '0'
0x140069ada  xorps   xmm0, xmm0
0x140069add  mov     qword ptr [rbp+var_20], rax
0x140069ae1  lea     r9d, [rdi+8]
0x140069ae5  mov     qword ptr [rbp+var_30+8], rbx
0x140069ae9  lea     r8, [rbp+var_30]
0x140069aed  mov     dword ptr [rbp+var_20+8], 140h
0x140069af4  mov     edx, 2000000h
0x140069af9  lea     rcx, [rbp+KeyHandle]
0x140069afd  movdqu  [rbp+var_10], xmm0
0x140069b02  call    cs:__imp_NtOpenKeyEx
0x140069b08  test    eax, eax
0x140069b0a  js      short loc_140069B86
0x140069b0c  xorps   xmm0, xmm0
0x140069b0f  mov     [rbp+arg_0], edi
0x140069b12  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x140069b19  lea     rcx, [rbp+ValueName]; DestinationString
0x140069b1d  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140069b21  call    cs:__imp_RtlInitUnicodeString
0x140069b27  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140069b2b  lea     rax, [rbp+arg_0]
0x140069b2f  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140069b34  lea     r8d, [rdi+2]; KeyValueInformationClass
0x140069b38  xor     r9d, r9d; KeyValueInformation
0x140069b3b  mov     [rsp+80h+Length], edi; Length
0x140069b3f  lea     rdx, [rbp+ValueName]; ValueName
0x140069b43  call    cs:__imp_NtQueryValueKey
0x140069b49  cmp     [rbp+arg_0], edi
0x140069b4c  jbe     short loc_140069B7C
0x140069b4e  cmp     eax, 0C0000034h
0x140069b53  jz      short loc_140069B7C
0x140069b55  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140069b59  call    cs:__imp_NtDeleteKey
0x140069b5f  mov     r8, rsi
0x140069b62  lea     rdx, aFoundUnexpecte; "Found unexpected registry symbolic link"...
0x140069b69  lea     rcx, aDeletesymbolic; "DeleteSymbolicLinkDirectly"
0x140069b70  mov     edi, eax
0x140069b72  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140069b77  not     edi
0x140069b79  shr     edi, 1Fh
0x140069b7c  mov     rcx, [rbp+KeyHandle]; Handle
0x140069b80  call    cs:__imp_NtClose
0x140069b86  mov     rbx, [rsp+80h+arg_8]
0x140069b8e  mov     eax, edi
0x140069b90  add     rsp, 80h
0x140069b97  pop     rdi
0x140069b98  pop     rsi
0x140069b99  pop     rbp
0x140069b9a  retn
```
