# ServerDllInitialization

- ea: `0x180006620`
- end: `0x18000672c`
- name: `ServerDllInitialization`
- size: `268`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180006620`
- `0x180006764`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x1800066df`
- `ntdll!RtlInitializeCriticalSection` at `0x1800066df`
- `ntdll!RtlCreateUnicodeString` at `0x18000668f`
- `ntdll!RtlCreateUnicodeString` at `0x1800066c8`
- `ntdll!RtlCreateUnicodeString` at `0x18000668f`
- `ntdll!RtlCreateUnicodeString` at `0x1800066c8`
- `ntdll!wcscat_s` at `0x1800066b0`
- `ntdll!wcscat_s` at `0x1800066b0`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18000666f`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18000666f`
- `BASESRV!BaseSrvRegisterSxS` at `0x1800066ff`
- `BASESRV!BaseSrvRegisterSxS` at `0x1800066ff`

## string_xrefs

- `0x18000669f`: `\system32\sxs.dll`

## pseudocode

```c
NTSTATUS __fastcall ServerDllInitialization(__int64 a1)
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-348h] BYREF
  WCHAR SourceString[400]; // [rsp+30h] [rbp-338h] BYREF

  *(_QWORD *)&Destination.Length = 52428800;
  *(_DWORD *)(a1 + 36) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 64) = 0;
  Destination.Buffer = SourceString;
  result = RtlExpandEnvironmentStrings_U(0, &UnexpandedSystemRootString, &Destination, 0);
  if ( result >= 0 )
  {
    if ( RtlCreateUnicodeString(&BaseSrvWindowsDirectory, SourceString)
      && (wcscat_s(SourceString, 0x190u, L"\\system32\\sxs.dll"),
          RtlCreateUnicodeString(&BaseSrvSxsDllPath, SourceString)) )
    {
      result = RtlInitializeCriticalSection(&BaseSrvSxsSystemDefaultActivationContextCriticalSection);
      if ( result >= 0 )
      {
        result = BaseSrvSxsInitializeActivationContextCache();
        if ( result >= 0 )
          return BaseSrvRegisterSxS(functions);
      }
    }
    else
    {
      return -1073741801;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006620  push    rbx
0x180006622  sub     rsp, 360h
0x180006629  mov     rax, cs:__security_cookie
0x180006630  xor     rax, rsp
0x180006633  mov     [rsp+368h+var_18], rax
0x18000663b  xor     ebx, ebx
0x18000663d  mov     qword ptr [rsp+368h+Destination.Length], 3200000h
0x180006646  mov     [rcx+24h], ebx
0x180006649  lea     rax, [rsp+368h+SourceString]
0x18000664e  mov     [rcx+28h], rbx
0x180006652  lea     r8, [rsp+368h+Destination]; Destination
0x180006657  mov     [rcx+30h], rbx
0x18000665b  lea     rdx, UnexpandedSystemRootString; Source
0x180006662  mov     [rcx+40h], ebx
0x180006665  xor     r9d, r9d; Length
0x180006668  xor     ecx, ecx; Environment
0x18000666a  mov     [rsp+368h+Destination.Buffer], rax
0x18000666f  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x180006676  nop     dword ptr [rax+rax+00h]
0x18000667b  test    eax, eax
0x18000667d  js      loc_180006712
0x180006683  lea     rdx, [rsp+368h+SourceString]; SourceString
0x180006688  lea     rcx, BaseSrvWindowsDirectory; DestinationString
0x18000668f  call    cs:__imp_RtlCreateUnicodeString
0x180006696  nop     dword ptr [rax+rax+00h]
0x18000669b  test    al, al
0x18000669d  jz      short loc_18000670D
0x18000669f  lea     r8, aSystem32SxsDll; "\\system32\\sxs.dll"
0x1800066a6  mov     edx, 190h; SizeInWords
0x1800066ab  lea     rcx, [rsp+368h+SourceString]; Destination
0x1800066b0  call    cs:__imp_wcscat_s
0x1800066b7  nop     dword ptr [rax+rax+00h]
0x1800066bc  lea     rdx, [rsp+368h+SourceString]; SourceString
0x1800066c1  lea     rcx, BaseSrvSxsDllPath; DestinationString
0x1800066c8  call    cs:__imp_RtlCreateUnicodeString
0x1800066cf  nop     dword ptr [rax+rax+00h]
0x1800066d4  test    al, al
0x1800066d6  jz      short loc_18000670D
0x1800066d8  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x1800066df  call    cs:__imp_RtlInitializeCriticalSection
0x1800066e6  nop     dword ptr [rax+rax+00h]
0x1800066eb  test    eax, eax
0x1800066ed  js      short loc_180006712
0x1800066ef  call    BaseSrvSxsInitializeActivationContextCache
0x1800066f4  test    eax, eax
0x1800066f6  js      short loc_180006712
0x1800066f8  lea     rcx, functions
0x1800066ff  call    cs:__imp_BaseSrvRegisterSxS
0x180006706  nop     dword ptr [rax+rax+00h]
0x18000670b  jmp     short loc_180006712
0x18000670d  mov     eax, 0C0000017h
0x180006712  mov     rcx, [rsp+368h+var_18]
0x18000671a  xor     rcx, rsp; StackCookie
0x18000671d  call    __security_check_cookie
0x180006722  add     rsp, 360h
0x180006729  pop     rbx
0x18000672a  retn
```
