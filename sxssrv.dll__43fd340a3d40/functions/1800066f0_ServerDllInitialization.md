# ServerDllInitialization

- ea: `0x1800066f0`
- end: `0x180006807`
- name: `ServerDllInitialization`
- size: `279`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800066f0`
- `0x180006834`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x1800067bb`
- `ntdll!RtlInitializeCriticalSection` at `0x1800067bb`
- `ntdll!RtlCreateUnicodeString` at `0x18000676b`
- `ntdll!RtlCreateUnicodeString` at `0x1800067a4`
- `ntdll!RtlCreateUnicodeString` at `0x18000676b`
- `ntdll!RtlCreateUnicodeString` at `0x1800067a4`
- `ntdll!wcscat_s` at `0x18000678c`
- `ntdll!wcscat_s` at `0x18000678c`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18000674b`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18000674b`
- `BASESRV!BaseSrvRegisterSxS` at `0x1800067db`
- `BASESRV!BaseSrvRegisterSxS` at `0x1800067db`

## string_xrefs

- `0x18000677b`: `\system32\sxs.dll`

## pseudocode

```c
NTSTATUS __fastcall ServerDllInitialization(__int64 a1)
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-348h] BYREF
  WCHAR SourceString[400]; // [rsp+30h] [rbp-338h] BYREF

  *(_DWORD *)(a1 + 36) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 64) = 0;
  Destination.Buffer = SourceString;
  *(_QWORD *)&Destination.Length = 52428800;
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
          return BaseSrvRegisterSxS(&functions);
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
0x1800066f0  sub     rsp, 368h
0x1800066f7  mov     rax, cs:__security_cookie
0x1800066fe  xor     rax, rsp
0x180006701  mov     [rsp+368h+var_18], rax
0x180006709  mov     dword ptr [rcx+24h], 0
0x180006710  lea     rax, [rsp+368h+SourceString]
0x180006715  mov     qword ptr [rcx+28h], 0
0x18000671d  lea     r8, [rsp+368h+Destination]; Destination
0x180006722  mov     qword ptr [rcx+30h], 0
0x18000672a  lea     rdx, UnexpandedSystemRootString; Source
0x180006731  mov     dword ptr [rcx+40h], 0
0x180006738  xor     r9d, r9d; Length
0x18000673b  xor     ecx, ecx; Environment
0x18000673d  mov     [rsp+368h+Destination.Buffer], rax
0x180006742  mov     qword ptr [rsp+368h+Destination.Length], 3200000h
0x18000674b  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x180006752  nop     dword ptr [rax+rax+00h]
0x180006757  test    eax, eax
0x180006759  js      loc_1800067EE
0x18000675f  lea     rdx, [rsp+368h+SourceString]; SourceString
0x180006764  lea     rcx, BaseSrvWindowsDirectory; DestinationString
0x18000676b  call    cs:__imp_RtlCreateUnicodeString
0x180006772  nop     dword ptr [rax+rax+00h]
0x180006777  test    al, al
0x180006779  jz      short loc_1800067E9
0x18000677b  lea     r8, aSystem32SxsDll; "\\system32\\sxs.dll"
0x180006782  mov     edx, 190h; SizeInWords
0x180006787  lea     rcx, [rsp+368h+SourceString]; Destination
0x18000678c  call    cs:__imp_wcscat_s
0x180006793  nop     dword ptr [rax+rax+00h]
0x180006798  lea     rdx, [rsp+368h+SourceString]; SourceString
0x18000679d  lea     rcx, BaseSrvSxsDllPath; DestinationString
0x1800067a4  call    cs:__imp_RtlCreateUnicodeString
0x1800067ab  nop     dword ptr [rax+rax+00h]
0x1800067b0  test    al, al
0x1800067b2  jz      short loc_1800067E9
0x1800067b4  lea     rcx, BaseSrvSxsSystemDefaultActivationContextCriticalSection; CriticalSection
0x1800067bb  call    cs:__imp_RtlInitializeCriticalSection
0x1800067c2  nop     dword ptr [rax+rax+00h]
0x1800067c7  test    eax, eax
0x1800067c9  js      short loc_1800067EE
0x1800067cb  call    BaseSrvSxsInitializeActivationContextCache
0x1800067d0  test    eax, eax
0x1800067d2  js      short loc_1800067EE
0x1800067d4  lea     rcx, functions
0x1800067db  call    cs:__imp_BaseSrvRegisterSxS
0x1800067e2  nop     dword ptr [rax+rax+00h]
0x1800067e7  jmp     short loc_1800067EE
0x1800067e9  mov     eax, 0C0000017h
0x1800067ee  mov     rcx, [rsp+368h+var_18]
0x1800067f6  xor     rcx, rsp; StackCookie
0x1800067f9  call    __security_check_cookie
0x1800067fe  add     rsp, 368h
0x180006805  retn
```
