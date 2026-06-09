# ValidateSigning(ushort const *,int)

- ea: `0x18006cfe4`
- end: `0x18006d171`
- name: `?ValidateSigning@@YAKPEBGH@Z`
- size: `397`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006cbe0`

## callees

- `0x18006a608`
- `0x18006cfe4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d030`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d161`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d161`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006d021`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006d021`
- `ntdll!NtGetCachedSigningLevel` at `0x18006d09f`
- `ntdll!NtGetCachedSigningLevel` at `0x18006d09f`
- `ntdll!NtQuerySystemInformation` at `0x18006d0fb`
- `ntdll!NtQuerySystemInformation` at `0x18006d0fb`

## string_xrefs

- `0x18006d039`: `onecore\ds\security\eas\policyengine\utilregs.cxx`
- `0x18006d143`: `onecore\ds\security\eas\policyengine\utilregs.cxx`
- `0x18006d0b9`: `NtGetCachedSigningLevel`
- `0x18006d05a`: `CreateFile(dllPath)`

## pseudocode

```c
// AFR coverage: ValidateSigning opens HKLM EAS provider path only to query cached signing level; no file content disclosure.
__int64 __fastcall ValidateSigning(const unsigned __int16 *a1, int a2)
{
  const OLECHAR *v2; // rdi
  HANDLE FileW; // rax
  void *v4; // rsi
  DWORD LastError; // eax
  unsigned int CachedSigningLevel; // ebx
  __int64 v8; // [rsp+20h] [rbp-38h]
  __int64 v9; // [rsp+20h] [rbp-38h]
  int v10; // [rsp+68h] [rbp+10h] BYREF
  int v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 SystemInformation; // [rsp+78h] [rbp+20h] BYREF

  v10 = a2;
  v2 = a1;
  LOBYTE(v10) = 0;
  v11 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    CachedSigningLevel = LastError;
    if ( !v2 )
      v2 = &Class;
    LODWORD(v8) = 241;
    DbgPrintfW(
      1u,
      L"(0x%08x) %ws:%u : %ws:%ws\n",
      LastError,
      L"onecore\\ds\\security\\eas\\policyengine\\utilregs.cxx",
      v8,
      L"CreateFile(dllPath)",
      v2);
  }
  else
  {
    CachedSigningLevel = NtGetCachedSigningLevel(FileW, &v11, &v10, 0, 0, 0);
    if ( CachedSigningLevel )
    {
      if ( !v2 )
        v2 = &Class;
      LODWORD(v9) = 262;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        CachedSigningLevel,
        L"onecore\\ds\\security\\eas\\policyengine\\utilregs.cxx",
        v9,
        L"NtGetCachedSigningLevel",
        v2);
    }
    else if ( (unsigned __int8)v10 < 8u )
    {
      SystemInformation = 8;
      if ( NtQuerySystemInformation(MaxSystemInfoClass|SystemProcessInformation, &SystemInformation, 8u, 0) >= 0
        && (SystemInformation & 0x200000000LL) != 0
        && (_BYTE)v10 == 4 )
      {
        CachedSigningLevel = 0;
      }
      else
      {
        CachedSigningLevel = 577;
      }
      if ( !v2 )
        v2 = &Class;
      LODWORD(v9) = 275;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        CachedSigningLevel,
        L"onecore\\ds\\security\\eas\\policyengine\\utilregs.cxx",
        v9,
        L"SE_SIGNING_LEVEL_MICROSOFT > resultSigningLevel",
        v2);
    }
    CloseHandle(v4);
  }
  return CachedSigningLevel;
}

```

## disassembly

```asm
0x18006cfe4  mov     rax, rsp; AFR coverage: ValidateSigning opens HKLM EAS provider path only to query cached signing level; no file content disclosure.
0x18006cfe7  mov     [rax+10h], edx
0x18006cfea  push    rbx
0x18006cfeb  push    rsi
0x18006cfec  push    rdi
0x18006cfed  sub     rsp, 40h
0x18006cff1  mov     qword ptr [rax-28h], 0
0x18006cff9  xor     r9d, r9d; lpSecurityAttributes
0x18006cffc  mov     dword ptr [rax-30h], 80h
0x18006d003  mov     edx, 80000000h; dwDesiredAccess
0x18006d008  mov     rdi, rcx
0x18006d00b  mov     byte ptr [rax+10h], 0
0x18006d00f  mov     dword ptr [rax+18h], 0
0x18006d016  lea     r8d, [r9+1]; dwShareMode
0x18006d01a  mov     dword ptr [rax-38h], 3
0x18006d021  call    cs:__imp_CreateFileW
0x18006d027  mov     rsi, rax
0x18006d02a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006d02e  jnz     short loc_18006D07D
0x18006d030  call    cs:__imp_GetLastError
0x18006d036  test    rdi, rdi
0x18006d039  lea     r9, aOnecoreDsSecur_4; "onecore\\ds\\security\\eas\\policyengin"...
0x18006d040  mov     ebx, eax
0x18006d042  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006d049  lea     rax, Class
0x18006d050  mov     r8d, ebx
0x18006d053  cmovz   rdi, rax
0x18006d057  lea     ecx, [rsi+2]; unsigned int
0x18006d05a  lea     rax, aCreatefileDllp; "CreateFile(dllPath)"
0x18006d061  mov     [rsp+58h+var_28], rdi
0x18006d066  mov     [rsp+58h+var_30], rax
0x18006d06b  mov     dword ptr [rsp+58h+var_38], 0F1h
0x18006d073  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006d078  jmp     loc_18006D167
0x18006d07d  mov     [rsp+58h+var_30], 0
0x18006d086  lea     r8, [rsp+58h+arg_8]
0x18006d08b  xor     r9d, r9d
0x18006d08e  mov     [rsp+58h+var_38], 0
0x18006d097  lea     rdx, [rsp+58h+arg_10]
0x18006d09c  mov     rcx, rsi
0x18006d09f  call    cs:__imp_NtGetCachedSigningLevel
0x18006d0a5  mov     ebx, eax
0x18006d0a7  test    eax, eax
0x18006d0a9  jz      short loc_18006D0D4
0x18006d0ab  lea     rax, Class
0x18006d0b2  test    rdi, rdi
0x18006d0b5  cmovz   rdi, rax
0x18006d0b9  lea     rax, aNtgetcachedsig; "NtGetCachedSigningLevel"
0x18006d0c0  mov     [rsp+58h+var_28], rdi
0x18006d0c5  mov     [rsp+58h+var_30], rax
0x18006d0ca  mov     dword ptr [rsp+58h+var_38], 106h
0x18006d0d2  jmp     short loc_18006D143
0x18006d0d4  mov     r8d, 8; SystemInformationLength
0x18006d0da  cmp     byte ptr [rsp+58h+arg_8], r8b
0x18006d0df  jnb     short loc_18006D15E
0x18006d0e1  mov     [rsp+58h+SystemInformation], 0
0x18006d0ea  lea     rdx, [rsp+58h+SystemInformation]; SystemInformation
0x18006d0ef  xor     r9d, r9d; ReturnLength
0x18006d0f2  mov     dword ptr [rsp+58h+SystemInformation], r8d
0x18006d0f7  lea     ecx, [r8+5Fh]; SystemInformationClass
0x18006d0fb  call    cs:__imp_NtQuerySystemInformation
0x18006d101  test    eax, eax
0x18006d103  js      short loc_18006D117
0x18006d105  test    byte ptr [rsp+58h+SystemInformation+4], 2
0x18006d10a  jz      short loc_18006D117
0x18006d10c  cmp     byte ptr [rsp+58h+arg_8], 4
0x18006d111  jnz     short loc_18006D117
0x18006d113  xor     ebx, ebx
0x18006d115  jmp     short loc_18006D11C
0x18006d117  mov     ebx, 241h
0x18006d11c  lea     rax, Class
0x18006d123  test    rdi, rdi
0x18006d126  cmovz   rdi, rax
0x18006d12a  lea     rax, aSeSigningLevel; "SE_SIGNING_LEVEL_MICROSOFT > resultSign"...
0x18006d131  mov     [rsp+58h+var_28], rdi
0x18006d136  mov     [rsp+58h+var_30], rax
0x18006d13b  mov     dword ptr [rsp+58h+var_38], 113h
0x18006d143  lea     r9, aOnecoreDsSecur_4; "onecore\\ds\\security\\eas\\policyengin"...
0x18006d14a  mov     r8d, ebx
0x18006d14d  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006d154  mov     ecx, 1; unsigned int
0x18006d159  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006d15e  mov     rcx, rsi; hObject
0x18006d161  call    cs:__imp_CloseHandle
0x18006d167  mov     eax, ebx
0x18006d169  add     rsp, 40h
0x18006d16d  pop     rdi
0x18006d16e  pop     rsi
0x18006d16f  pop     rbx
0x18006d170  retn
```
