# DeleteSymbolicLink(HKEY__ *,ushort const *)

- ea: `0x1400702f8`
- end: `0x140070498`
- name: `?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z`
- size: `416`
- prototype: `_BOOL8 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006fe7c`
- `0x1400709e0`
- `0x140071470`

## callees

- `0x140015378`
- `0x140016314`
- `0x1400257ec`
- `0x14005e898`
- `0x1400692c0`
- `0x1400702f8`
- `0x1400704a0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x14007042a`
- `ntdll!NtQueryValueKey` at `0x14007042a`
- `ntdll!RtlInitUnicodeString` at `0x140070398`
- `ntdll!RtlInitUnicodeString` at `0x140070402`
- `ntdll!RtlInitUnicodeString` at `0x140070398`
- `ntdll!RtlInitUnicodeString` at `0x140070402`
- `ntdll!NtOpenKeyEx` at `0x1400703d9`
- `ntdll!NtOpenKeyEx` at `0x1400703d9`
- `ntdll!NtDeleteKey` at `0x140070446`
- `ntdll!NtDeleteKey` at `0x140070446`
- `ntdll!NtClose` at `0x140070476`
- `ntdll!NtClose` at `0x140070476`

## string_xrefs

- `0x14007034d`: `DeleteSymbolicLinkViaBroker failed.  Error hr: 0x%x.`
- `0x1400703f3`: `SymbolicLinkValue`
- `0x140070457`: `Found unexpected registry symbolic link %ws.`
- `0x140070354`: `DeleteSymbolicLink`
- `0x140070466`: `DeleteSymbolicLink`

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
0x1400702f8  mov     [rsp-18h+arg_0], rbx
0x1400702fd  push    rbp
0x1400702fe  push    rsi
0x1400702ff  push    rdi
0x140070300  mov     rbp, rsp
0x140070303  sub     rsp, 80h
0x14007030a  xor     ebx, ebx
0x14007030c  mov     rdi, rdx
0x14007030f  mov     [rbp+arg_10], ebx
0x140070312  mov     rsi, rcx
0x140070315  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14007031c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140070321  test    al, al
0x140070323  jz      short loc_14007037A
0x140070325  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14007032a  test    eax, eax
0x14007032c  jz      short loc_140070368
0x14007032e  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x140070333  test    al, al
0x140070335  jz      short loc_140070368
0x140070337  lea     r8, [rbp+arg_10]; int *
0x14007033b  mov     rdx, rdi; unsigned __int16 *
0x14007033e  mov     rcx, rsi; HKEY
0x140070341  call    ?DeleteSymbolicLinkViaBroker@@YAJPEAUHKEY__@@PEBGPEAH@Z; DeleteSymbolicLinkViaBroker(HKEY__ *,ushort const *,int *)
0x140070346  test    eax, eax
0x140070348  jns     short loc_140070360
0x14007034a  mov     r8d, eax
0x14007034d  lea     rdx, aDeletesymbolic_3; "DeleteSymbolicLinkViaBroker failed.  Er"...
0x140070354  lea     rcx, aDeletesymbolic_0; "DeleteSymbolicLink"
0x14007035b  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140070360  mov     ebx, [rbp+arg_10]
0x140070363  jmp     loc_140070482
0x140070368  mov     rdx, rdi; unsigned __int16 *
0x14007036b  mov     rcx, rsi; HKEY
0x14007036e  call    ?DeleteSymbolicLinkDirectly@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLinkDirectly(HKEY__ *,ushort const *)
0x140070373  mov     ebx, eax
0x140070375  jmp     loc_140070482
0x14007037a  xorps   xmm0, xmm0
0x14007037d  mov     [rbp+KeyHandle], rbx
0x140070381  mov     rdx, rdi; SourceString
0x140070384  lea     rcx, [rbp+DestinationString]; DestinationString
0x140070388  movups  [rbp+var_30], xmm0
0x14007038c  movups  [rbp+var_20], xmm0
0x140070390  movups  [rbp+var_10], xmm0
0x140070394  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140070398  call    cs:__imp_RtlInitUnicodeString
0x14007039f  nop     dword ptr [rax+rax+00h]
0x1400703a4  lea     rax, [rbp+DestinationString]
0x1400703a8  mov     dword ptr [rbp+var_30], 30h ; '0'
0x1400703af  xorps   xmm0, xmm0
0x1400703b2  mov     qword ptr [rbp+var_20], rax
0x1400703b6  mov     r9d, 8
0x1400703bc  mov     qword ptr [rbp+var_30+8], rsi
0x1400703c0  lea     r8, [rbp+var_30]
0x1400703c4  mov     dword ptr [rbp+var_20+8], 140h
0x1400703cb  mov     edx, 2000000h
0x1400703d0  lea     rcx, [rbp+KeyHandle]
0x1400703d4  movdqu  [rbp+var_10], xmm0
0x1400703d9  call    cs:__imp_NtOpenKeyEx
0x1400703e0  nop     dword ptr [rax+rax+00h]
0x1400703e5  test    eax, eax
0x1400703e7  js      loc_140070482
0x1400703ed  xorps   xmm0, xmm0
0x1400703f0  mov     [rbp+arg_10], ebx
0x1400703f3  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1400703fa  lea     rcx, [rbp+ValueName]; DestinationString
0x1400703fe  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x140070402  call    cs:__imp_RtlInitUnicodeString
0x140070409  nop     dword ptr [rax+rax+00h]
0x14007040e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140070412  lea     rax, [rbp+arg_10]
0x140070416  xor     r9d, r9d; KeyValueInformation
0x140070419  mov     [rsp+80h+ResultLength], rax; ResultLength
0x14007041e  lea     rdx, [rbp+ValueName]; ValueName
0x140070422  mov     [rsp+80h+Length], ebx; Length
0x140070426  lea     r8d, [r9+2]; KeyValueInformationClass
0x14007042a  call    cs:__imp_NtQueryValueKey
0x140070431  nop     dword ptr [rax+rax+00h]
0x140070436  cmp     [rbp+arg_10], ebx
0x140070439  jbe     short loc_140070472
0x14007043b  cmp     eax, 0C0000034h
0x140070440  jz      short loc_140070472
0x140070442  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140070446  call    cs:__imp_NtDeleteKey
0x14007044d  nop     dword ptr [rax+rax+00h]
0x140070452  mov     ecx, 1
0x140070457  lea     rdx, aFoundUnexpecte; "Found unexpected registry symbolic link"...
0x14007045e  test    eax, eax
0x140070460  mov     r8, rdi
0x140070463  cmovns  ebx, ecx
0x140070466  lea     rcx, aDeletesymbolic_0; "DeleteSymbolicLink"
0x14007046d  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140070472  mov     rcx, [rbp+KeyHandle]; Handle
0x140070476  call    cs:__imp_NtClose
0x14007047d  nop     dword ptr [rax+rax+00h]
0x140070482  mov     eax, ebx
0x140070484  mov     rbx, [rsp+80h+arg_0]
0x14007048c  add     rsp, 80h
0x140070493  pop     rdi
0x140070494  pop     rsi
0x140070495  pop     rbp
0x140070496  retn
```
