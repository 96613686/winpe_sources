# ValidateSigning(ushort const *,int)

- ea: `0x140099208`
- end: `0x140099395`
- name: `?ValidateSigning@@YAKPEBGH@Z`
- size: `397`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140098d9c`

## callees

- `0x140038250`
- `0x140099208`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140099254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140099254`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140099385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140099385`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140099245`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140099245`
- `ntdll!NtGetCachedSigningLevel` at `0x1400992c3`
- `ntdll!NtGetCachedSigningLevel` at `0x1400992c3`
- `ntdll!NtQuerySystemInformation` at `0x14009931f`
- `ntdll!NtQuerySystemInformation` at `0x14009931f`

## string_xrefs

- `0x14009925d`: `onecore\ds\security\eas\policyengine\utilregs.cxx`
- `0x140099367`: `onecore\ds\security\eas\policyengine\utilregs.cxx`
- `0x1400992dd`: `NtGetCachedSigningLevel`
- `0x14009927e`: `CreateFile(dllPath)`

## pseudocode

```c
__int64 __fastcall ValidateSigning(const BYTE *a1, int a2)
{
  const BYTE *v2; // rdi
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
  FileW = CreateFileW((LPCWSTR)a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    CachedSigningLevel = LastError;
    if ( !v2 )
      v2 = &pPassword;
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
        v2 = &pPassword;
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
        v2 = &pPassword;
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
0x140099208  mov     rax, rsp
0x14009920b  mov     [rax+10h], edx
0x14009920e  push    rbx
0x14009920f  push    rsi
0x140099210  push    rdi
0x140099211  sub     rsp, 40h
0x140099215  mov     qword ptr [rax-28h], 0
0x14009921d  xor     r9d, r9d; lpSecurityAttributes
0x140099220  mov     dword ptr [rax-30h], 80h
0x140099227  mov     edx, 80000000h; dwDesiredAccess
0x14009922c  mov     rdi, rcx
0x14009922f  mov     byte ptr [rax+10h], 0
0x140099233  mov     dword ptr [rax+18h], 0
0x14009923a  lea     r8d, [r9+1]; dwShareMode
0x14009923e  mov     dword ptr [rax-38h], 3
0x140099245  call    cs:__imp_CreateFileW
0x14009924b  mov     rsi, rax
0x14009924e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140099252  jnz     short loc_1400992A1
0x140099254  call    cs:__imp_GetLastError
0x14009925a  test    rdi, rdi
0x14009925d  lea     r9, aOnecoreDsSecur_5; "onecore\\ds\\security\\eas\\policyengin"...
0x140099264  mov     ebx, eax
0x140099266  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x14009926d  lea     rax, pPassword
0x140099274  mov     r8d, ebx
0x140099277  cmovz   rdi, rax
0x14009927b  lea     ecx, [rsi+2]; unsigned int
0x14009927e  lea     rax, aCreatefileDllp; "CreateFile(dllPath)"
0x140099285  mov     [rsp+58h+var_28], rdi
0x14009928a  mov     [rsp+58h+var_30], rax
0x14009928f  mov     dword ptr [rsp+58h+var_38], 0F1h
0x140099297  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x14009929c  jmp     loc_14009938B
0x1400992a1  mov     [rsp+58h+var_30], 0
0x1400992aa  lea     r8, [rsp+58h+arg_8]
0x1400992af  xor     r9d, r9d
0x1400992b2  mov     [rsp+58h+var_38], 0
0x1400992bb  lea     rdx, [rsp+58h+arg_10]
0x1400992c0  mov     rcx, rsi
0x1400992c3  call    cs:__imp_NtGetCachedSigningLevel
0x1400992c9  mov     ebx, eax
0x1400992cb  test    eax, eax
0x1400992cd  jz      short loc_1400992F8
0x1400992cf  lea     rax, pPassword
0x1400992d6  test    rdi, rdi
0x1400992d9  cmovz   rdi, rax
0x1400992dd  lea     rax, aNtgetcachedsig; "NtGetCachedSigningLevel"
0x1400992e4  mov     [rsp+58h+var_28], rdi
0x1400992e9  mov     [rsp+58h+var_30], rax
0x1400992ee  mov     dword ptr [rsp+58h+var_38], 106h
0x1400992f6  jmp     short loc_140099367
0x1400992f8  mov     r8d, 8; SystemInformationLength
0x1400992fe  cmp     byte ptr [rsp+58h+arg_8], r8b
0x140099303  jnb     short loc_140099382
0x140099305  mov     [rsp+58h+SystemInformation], 0
0x14009930e  lea     rdx, [rsp+58h+SystemInformation]; SystemInformation
0x140099313  xor     r9d, r9d; ReturnLength
0x140099316  mov     dword ptr [rsp+58h+SystemInformation], r8d
0x14009931b  lea     ecx, [r8+5Fh]; SystemInformationClass
0x14009931f  call    cs:__imp_NtQuerySystemInformation
0x140099325  test    eax, eax
0x140099327  js      short loc_14009933B
0x140099329  test    byte ptr [rsp+58h+SystemInformation+4], 2
0x14009932e  jz      short loc_14009933B
0x140099330  cmp     byte ptr [rsp+58h+arg_8], 4
0x140099335  jnz     short loc_14009933B
0x140099337  xor     ebx, ebx
0x140099339  jmp     short loc_140099340
0x14009933b  mov     ebx, 241h
0x140099340  lea     rax, pPassword
0x140099347  test    rdi, rdi
0x14009934a  cmovz   rdi, rax
0x14009934e  lea     rax, aSeSigningLevel; "SE_SIGNING_LEVEL_MICROSOFT > resultSign"...
0x140099355  mov     [rsp+58h+var_28], rdi
0x14009935a  mov     [rsp+58h+var_30], rax
0x14009935f  mov     dword ptr [rsp+58h+var_38], 113h
0x140099367  lea     r9, aOnecoreDsSecur_5; "onecore\\ds\\security\\eas\\policyengin"...
0x14009936e  mov     r8d, ebx
0x140099371  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140099378  mov     ecx, 1; unsigned int
0x14009937d  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140099382  mov     rcx, rsi; hObject
0x140099385  call    cs:__imp_CloseHandle
0x14009938b  mov     eax, ebx
0x14009938d  add     rsp, 40h
0x140099391  pop     rdi
0x140099392  pop     rsi
0x140099393  pop     rbx
0x140099394  retn
```
