# CSxDiagnostics::Initialize(ushort const *)

- ea: `0x18002d8f4`
- end: `0x18002dae9`
- name: `?Initialize@CSxDiagnostics@@QEAAJPEBG@Z`
- size: `501`
- prototype: `__int64 __fastcall(CSxDiagnostics *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180008b10`

## callees

- `0x1800268b4`
- `0x1800269ac`
- `0x18002d8f4`
- `0x18002e6e0`
- `0x180035b00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002d9d1`
- `msvcrt!_wcsicmp` at `0x18002d9d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d9fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002daa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dac1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d9fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002da6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002daa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dac1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d980`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002da37`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d980`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002da37`

## string_xrefs

- `0x18002d938`: `SYSTEM\CurrentControlSet\Services\VSS\Diag`

## pseudocode

```c
__int64 __fastcall CSxDiagnostics::Initialize(CSxDiagnostics *this, unsigned __int16 *a2)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  __int16 v5; // ax
  __int16 v6; // ax
  LSTATUS v7; // eax
  HKEY v8; // rcx
  __int64 v9; // r8
  char *v10; // rdx
  wchar_t *String1[2]; // [rsp+50h] [rbp-9h] BYREF
  int v13; // [rsp+60h] [rbp+7h] BYREF
  __int16 v14; // [rsp+64h] [rbp+Bh]
  __int16 v15; // [rsp+66h] [rbp+Dh]
  HKEY hKey; // [rsp+C8h] [rbp+6Fh] BYREF
  HKEY phkResult; // [rsp+D0h] [rbp+77h] BYREF

  hKey = (HKEY)a2;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "CSxDiagnostics::Initialize", 41, 1);
  String1[0] = (wchar_t *)&FileName;
  phkResult = 0;
  hKey = 0;
  v14 = 48;
  String1[1] = 0;
  v13 = 0;
  v3 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Diag",
         0,
         0,
         0,
         0x2001Fu,
         0,
         &phkResult,
         0);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  v13 = v4;
  v5 = 66;
  if ( v4 < 0 )
    goto LABEL_4;
  v14 = 66;
  if ( (int)SxRegReadString(phkResult, &word_18003B6A0, (struct CBsString *)String1) < 0
    || _wcsicmp(String1[0], L"disabled") )
  {
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v7 = RegCreateKeyExW(phkResult, L"SPP", 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    v13 = v4;
    v5 = 88;
    if ( v4 < 0 )
    {
LABEL_4:
      v15 = v5;
      goto LABEL_17;
    }
    v8 = (HKEY)*((_QWORD *)this + 1);
    v14 = 88;
    if ( (unsigned __int64)v8 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(v8);
      *((_QWORD *)this + 1) = 0;
    }
    *((_QWORD *)this + 1) = hKey;
    hKey = 0;
    v13 = 0;
    v6 = 96;
    v4 = 0;
  }
  else
  {
    v6 = 74;
    v13 = 1;
    v4 = 1;
  }
  v14 = v6;
LABEL_17:
  CBsString::_Release(String1);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v10 = (char *)phkResult - 1;
  if ( (unsigned __int64)phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, (__int64)v10, v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002d8f4  mov     [rsp-8+arg_0], rbx
0x18002d8f9  mov     [rsp-8+hKey], rdx
0x18002d8fe  push    rbp
0x18002d8ff  push    rsi
0x18002d900  push    rdi
0x18002d901  lea     rbp, [rsp-47h]
0x18002d906  sub     rsp, 0A0h
0x18002d90d  mov     r9d, 1; unsigned __int16
0x18002d913  lea     rdx, aCsxdiagnostics_0; "CSxDiagnostics::Initialize"
0x18002d91a  mov     rdi, rcx
0x18002d91d  lea     rcx, [rbp+57h+var_50]; this
0x18002d921  lea     r8d, [r9+28h]; unsigned __int16
0x18002d925  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002d92a  xor     esi, esi
0x18002d92c  lea     rax, FileName
0x18002d933  mov     [rsp+0B0h+lpdwDisposition], rsi; lpdwDisposition
0x18002d938  lea     rdx, c_wszDiagnosticsKey; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x18002d93f  mov     [rbp+57h+String1], rax
0x18002d943  xor     r9d, r9d; lpClass
0x18002d946  xor     r8d, r8d; Reserved
0x18002d949  mov     [rbp+57h+arg_10], rsi
0x18002d94d  lea     eax, [rsi+30h]
0x18002d950  mov     [rbp+57h+hKey], rsi
0x18002d954  mov     [rbp+57h+var_4C], ax
0x18002d958  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d95f  lea     rax, [rbp+57h+arg_10]
0x18002d963  mov     [rbp+57h+var_58], rsi
0x18002d967  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18002d96c  mov     [rsp+0B0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002d971  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x18002d979  mov     [rsp+0B0h+dwOptions], esi; dwOptions
0x18002d97d  mov     [rbp+57h+var_50], esi
0x18002d980  call    cs:__imp_RegCreateKeyExW
0x18002d986  mov     ebx, eax
0x18002d988  test    eax, eax
0x18002d98a  jle     short loc_18002D995
0x18002d98c  movzx   ebx, ax
0x18002d98f  or      ebx, 80070000h
0x18002d995  mov     [rbp+57h+var_50], ebx
0x18002d998  mov     eax, 42h ; 'B'
0x18002d99d  test    ebx, ebx
0x18002d99f  jns     short loc_18002D9AA
0x18002d9a1  mov     [rbp+57h+var_4A], ax
0x18002d9a5  jmp     loc_18002DA92
0x18002d9aa  mov     rcx, [rbp+57h+arg_10]; hKey
0x18002d9ae  lea     r8, [rbp+57h+String1]; this
0x18002d9b2  lea     rdx, word_18003B6A0; lpValueName
0x18002d9b9  mov     [rbp+57h+var_4C], ax
0x18002d9bd  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x18002d9c2  test    eax, eax
0x18002d9c4  js      short loc_18002D9EF
0x18002d9c6  mov     rcx, [rbp+57h+String1]; String1
0x18002d9ca  lea     rdx, aDisabled; "disabled"
0x18002d9d1  call    cs:__imp__wcsicmp
0x18002d9d7  test    eax, eax
0x18002d9d9  jnz     short loc_18002D9EF
0x18002d9db  mov     eax, 4Ah ; 'J'
0x18002d9e0  mov     [rbp+57h+var_50], 1
0x18002d9e7  lea     ebx, [rax-49h]
0x18002d9ea  jmp     loc_18002DA8E
0x18002d9ef  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d9f3  lea     rax, [rcx-1]
0x18002d9f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d9fb  ja      short loc_18002DA07
0x18002d9fd  call    cs:__imp_RegCloseKey
0x18002da03  mov     [rbp+57h+hKey], rsi
0x18002da07  mov     rcx, [rbp+57h+arg_10]; hKey
0x18002da0b  lea     rax, [rbp+57h+hKey]
0x18002da0f  mov     [rsp+0B0h+lpdwDisposition], rsi; lpdwDisposition
0x18002da14  lea     rdx, aSpp; "SPP"
0x18002da1b  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18002da20  xor     r9d, r9d; lpClass
0x18002da23  mov     [rsp+0B0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002da28  xor     r8d, r8d; Reserved
0x18002da2b  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x18002da33  mov     [rsp+0B0h+dwOptions], esi; dwOptions
0x18002da37  call    cs:__imp_RegCreateKeyExW
0x18002da3d  mov     ebx, eax
0x18002da3f  test    eax, eax
0x18002da41  jle     short loc_18002DA4C
0x18002da43  movzx   ebx, ax
0x18002da46  or      ebx, 80070000h
0x18002da4c  mov     [rbp+57h+var_50], ebx
0x18002da4f  mov     eax, 58h ; 'X'
0x18002da54  test    ebx, ebx
0x18002da56  js      loc_18002D9A1
0x18002da5c  mov     rcx, [rdi+8]; hKey
0x18002da60  mov     [rbp+57h+var_4C], ax
0x18002da64  lea     rax, [rcx-1]
0x18002da68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002da6c  ja      short loc_18002DA78
0x18002da6e  call    cs:__imp_RegCloseKey
0x18002da74  mov     [rdi+8], rsi
0x18002da78  mov     rax, [rbp+57h+hKey]
0x18002da7c  mov     [rdi+8], rax
0x18002da80  mov     [rbp+57h+hKey], rsi
0x18002da84  mov     [rbp+57h+var_50], esi
0x18002da87  mov     eax, 60h ; '`'
0x18002da8c  mov     ebx, esi
0x18002da8e  mov     [rbp+57h+var_4C], ax
0x18002da92  lea     rcx, [rbp+57h+String1]; this
0x18002da96  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002da9b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002da9f  lea     rax, [rcx-1]
0x18002daa3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002daa7  ja      short loc_18002DAB3
0x18002daa9  call    cs:__imp_RegCloseKey
0x18002daaf  mov     [rbp+57h+hKey], rsi
0x18002dab3  mov     rcx, [rbp+57h+arg_10]; hKey
0x18002dab7  lea     rdx, [rcx-1]
0x18002dabb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002dabf  ja      short loc_18002DACB
0x18002dac1  call    cs:__imp_RegCloseKey
0x18002dac7  mov     [rbp+57h+arg_10], rsi
0x18002dacb  lea     rcx, [rbp+57h+var_50]; this
0x18002dacf  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002dad4  mov     eax, ebx
0x18002dad6  mov     rbx, [rsp+0B0h+arg_0]
0x18002dade  add     rsp, 0A0h
0x18002dae5  pop     rdi
0x18002dae6  pop     rsi
0x18002dae7  pop     rbp
0x18002dae8  retn
```
