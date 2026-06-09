# DeleteSymbolicLink(HKEY__ *,ushort const *)

- ea: `0x140069910`
- end: `0x140069a87`
- name: `?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z`
- size: `375`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400694d8`
- `0x140069f68`
- `0x14006a910`

## callees

- `0x1400140cc`
- `0x140014fc4`
- `0x140023860`
- `0x1400590f0`
- `0x1400631d4`
- `0x140069910`
- `0x140069a90`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x140069a2c`
- `ntdll!NtQueryValueKey` at `0x140069a2c`
- `ntdll!RtlInitUnicodeString` at `0x1400699b0`
- `ntdll!RtlInitUnicodeString` at `0x140069a0a`
- `ntdll!RtlInitUnicodeString` at `0x1400699b0`
- `ntdll!RtlInitUnicodeString` at `0x140069a0a`
- `ntdll!NtOpenKeyEx` at `0x1400699eb`
- `ntdll!NtOpenKeyEx` at `0x1400699eb`
- `ntdll!NtDeleteKey` at `0x140069a42`
- `ntdll!NtDeleteKey` at `0x140069a42`
- `ntdll!NtClose` at `0x140069a6c`
- `ntdll!NtClose` at `0x140069a6c`

## string_xrefs

- `0x140069a4d`: `Found unexpected registry symbolic link %ws.`
- `0x1400699fb`: `SymbolicLinkValue`
- `0x140069965`: `DeleteSymbolicLinkViaBroker failed.  Error hr: 0x%x.`
- `0x14006996c`: `DeleteSymbolicLink`
- `0x140069a5c`: `DeleteSymbolicLink`

## pseudocode

```c
_BOOL8 __fastcall DeleteSymbolicLink(HKEY a1, const unsigned __int16 *a2)
{
  BOOL v2; // ebx
  const unsigned __int16 *v5; // rdx
  ProcessUtils *v6; // rcx
  int v7; // eax
  NTSTATUS v8; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  __int128 v12; // [rsp+50h] [rbp-30h] BYREF
  __int128 v13; // [rsp+60h] [rbp-20h]
  __int128 v14; // [rsp+70h] [rbp-10h]
  ULONG ResultLength; // [rsp+B0h] [rbp+30h] BYREF
  HANDLE KeyHandle; // [rsp+B8h] [rbp+38h] BYREF

  v2 = 0;
  ResultLength = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)IsWindowsProtectedPrintEnabled() && ProcessUtils::IsCurrentProcess(v6, v5) )
    {
      v7 = DeleteSymbolicLinkViaBroker(a1, a2, (int *)&ResultLength);
      if ( v7 < 0 )
        PrvSpoolssTelemetry::WriteDbgTraceError(
          "DeleteSymbolicLink",
          L"DeleteSymbolicLinkViaBroker failed.  Error hr: 0x%x.",
          (unsigned int)v7);
      return (BOOL)ResultLength;
    }
    else
    {
      return (BOOL)DeleteSymbolicLinkDirectly(a1, a2);
    }
  }
  else
  {
    KeyHandle = 0;
    v12 = 0;
    v13 = 0;
    v14 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    LODWORD(v12) = 48;
    *(_QWORD *)&v13 = &DestinationString;
    *((_QWORD *)&v12 + 1) = a1;
    DWORD2(v13) = 320;
    v14 = 0;
    if ( (int)NtOpenKeyEx(&KeyHandle, 0x2000000, &v12, 8) >= 0 )
    {
      ResultLength = 0;
      ValueName = 0;
      RtlInitUnicodeString(&ValueName, L"SymbolicLinkValue");
      v8 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
      if ( ResultLength && v8 != -1073741772 )
      {
        v2 = NtDeleteKey(KeyHandle) >= 0;
        PrvSpoolssTelemetry::WriteDbgTraceError(
          "DeleteSymbolicLink",
          L"Found unexpected registry symbolic link %ws.",
          a2);
      }
      NtClose(KeyHandle);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140069910  mov     [rsp-18h+arg_0], rbx
0x140069915  push    rbp
0x140069916  push    rsi
0x140069917  push    rdi
0x140069918  mov     rbp, rsp
0x14006991b  sub     rsp, 80h
0x140069922  xor     ebx, ebx
0x140069924  mov     rdi, rdx
0x140069927  mov     [rbp+arg_10], ebx
0x14006992a  mov     rsi, rcx
0x14006992d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140069934  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140069939  test    al, al
0x14006993b  jz      short loc_140069992
0x14006993d  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140069942  test    eax, eax
0x140069944  jz      short loc_140069980
0x140069946  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x14006994b  test    al, al
0x14006994d  jz      short loc_140069980
0x14006994f  lea     r8, [rbp+arg_10]; int *
0x140069953  mov     rdx, rdi; unsigned __int16 *
0x140069956  mov     rcx, rsi; HKEY
0x140069959  call    ?DeleteSymbolicLinkViaBroker@@YAJPEAUHKEY__@@PEBGPEAH@Z; DeleteSymbolicLinkViaBroker(HKEY__ *,ushort const *,int *)
0x14006995e  test    eax, eax
0x140069960  jns     short loc_140069978
0x140069962  mov     r8d, eax
0x140069965  lea     rdx, aDeletesymbolic_3; "DeleteSymbolicLinkViaBroker failed.  Er"...
0x14006996c  lea     rcx, aDeletesymbolic_0; "DeleteSymbolicLink"
0x140069973  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140069978  mov     ebx, [rbp+arg_10]
0x14006997b  jmp     loc_140069A72
0x140069980  mov     rdx, rdi; unsigned __int16 *
0x140069983  mov     rcx, rsi; HKEY
0x140069986  call    ?DeleteSymbolicLinkDirectly@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLinkDirectly(HKEY__ *,ushort const *)
0x14006998b  mov     ebx, eax
0x14006998d  jmp     loc_140069A72
0x140069992  xorps   xmm0, xmm0
0x140069995  mov     [rbp+KeyHandle], rbx
0x140069999  mov     rdx, rdi; SourceString
0x14006999c  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400699a0  movups  [rbp+var_30], xmm0
0x1400699a4  movups  [rbp+var_20], xmm0
0x1400699a8  movups  [rbp+var_10], xmm0
0x1400699ac  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400699b0  call    cs:__imp_RtlInitUnicodeString
0x1400699b6  lea     rax, [rbp+DestinationString]
0x1400699ba  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1400699c1  xorps   xmm0, xmm0
0x1400699c4  mov     qword ptr [rbp+var_20], rax
0x1400699c8  mov     r9d, 8
0x1400699ce  mov     qword ptr [rbp+var_30+8], rsi
0x1400699d2  lea     r8, [rbp+var_30]
0x1400699d6  mov     dword ptr [rbp+var_20+8], 140h
0x1400699dd  mov     edx, 2000000h
0x1400699e2  lea     rcx, [rbp+KeyHandle]
0x1400699e6  movdqu  [rbp+var_10], xmm0
0x1400699eb  call    cs:__imp_NtOpenKeyEx
0x1400699f1  test    eax, eax
0x1400699f3  js      short loc_140069A72
0x1400699f5  xorps   xmm0, xmm0
0x1400699f8  mov     [rbp+arg_10], ebx
0x1400699fb  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x140069a02  lea     rcx, [rbp+ValueName]; DestinationString
0x140069a06  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140069a0a  call    cs:__imp_RtlInitUnicodeString
0x140069a10  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140069a14  lea     rax, [rbp+arg_10]
0x140069a18  xor     r9d, r9d; KeyValueInformation
0x140069a1b  mov     [rsp+80h+ResultLength], rax; ResultLength
0x140069a20  lea     rdx, [rbp+ValueName]; ValueName
0x140069a24  mov     [rsp+80h+Length], ebx; Length
0x140069a28  lea     r8d, [r9+2]; KeyValueInformationClass
0x140069a2c  call    cs:__imp_NtQueryValueKey
0x140069a32  cmp     [rbp+arg_10], ebx
0x140069a35  jbe     short loc_140069A68
0x140069a37  cmp     eax, 0C0000034h
0x140069a3c  jz      short loc_140069A68
0x140069a3e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140069a42  call    cs:__imp_NtDeleteKey
0x140069a48  mov     ecx, 1
0x140069a4d  lea     rdx, aFoundUnexpecte; "Found unexpected registry symbolic link"...
0x140069a54  test    eax, eax
0x140069a56  mov     r8, rdi
0x140069a59  cmovns  ebx, ecx
0x140069a5c  lea     rcx, aDeletesymbolic_0; "DeleteSymbolicLink"
0x140069a63  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140069a68  mov     rcx, [rbp+KeyHandle]; Handle
0x140069a6c  call    cs:__imp_NtClose
0x140069a72  mov     eax, ebx
0x140069a74  mov     rbx, [rsp+80h+arg_0]
0x140069a7c  add     rsp, 80h
0x140069a83  pop     rdi
0x140069a84  pop     rsi
0x140069a85  pop     rbp
0x140069a86  retn
```
