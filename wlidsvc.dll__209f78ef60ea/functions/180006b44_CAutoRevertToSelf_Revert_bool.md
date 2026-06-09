# CAutoRevertToSelf::Revert(bool)

- ea: `0x180006b44`
- end: `0x180006c11`
- name: `?Revert@CAutoRevertToSelf@@QEAAJ_N@Z`
- size: `205`
- prototype: `__int64 __fastcall(CAutoRevertToSelf *__hidden this, bool)`
- caller_count: `11`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800057f8`
- `0x1800062e0`
- `0x18002c77c`
- `0x18003a8fc`
- `0x18006be30`
- `0x18006c0c0`
- `0x1800ea1a8`
- `0x1800ea4fc`
- `0x1800ebe48`
- `0x1800ec5c0`
- `0x1800edf40`

## callees

- `0x180006b44`
- `0x18000c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006b58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006b58`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006b7c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006b7c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006b6e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006b6e`

## pseudocode

```c
__int64 __fastcall CAutoRevertToSelf::Revert(void **this)
{
  signed int v2; // edi
  HANDLE CurrentThread; // rax
  BOOL v4; // eax
  signed int v6; // eax
  const char *v7; // rax
  unsigned int v8; // r8d
  signed int LastError; // eax

  v2 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, this + 1) )
  {
    v4 = SetThreadToken(0, 0);
    *(_DWORD *)this = v4;
    if ( !v4 )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 < 0 )
      {
        v7 = "hr = HRESULT_FROM_WIN32(GetLastError())";
        v8 = 113;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v6 = GetLastError();
    if ( v6 != 1008 )
    {
      v2 = v6 > 0 ? (unsigned __int16)v6 | 0x80070000 : v6;
      if ( v2 < 0 )
      {
        v7 = "hr = HRESULT_FROM_WIN32(lastError)";
        v8 = 104;
LABEL_14:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\Live\\identity\\Lib\\TransferImplementation\\transferimp.h",
          "CAutoRevertToSelf::Revert",
          v8,
          v2,
          v7);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006b44  mov     [rsp+arg_0], rbx
0x180006b49  mov     [rsp+arg_8], rsi
0x180006b4e  push    rdi
0x180006b4f  sub     rsp, 30h
0x180006b53  mov     rsi, rcx
0x180006b56  xor     edi, edi
0x180006b58  call    cs:__imp_GetCurrentThread
0x180006b5e  lea     r9, [rsi+8]; TokenHandle
0x180006b62  mov     edx, 0F01FFh; DesiredAccess
0x180006b67  mov     rcx, rax; ThreadHandle
0x180006b6a  lea     r8d, [rdi+1]; OpenAsSelf
0x180006b6e  call    cs:__imp_OpenThreadToken
0x180006b74  test    eax, eax
0x180006b76  jz      short loc_180006B9A
0x180006b78  xor     edx, edx; Token
0x180006b7a  xor     ecx, ecx; Thread
0x180006b7c  call    cs:__imp_SetThreadToken
0x180006b82  mov     [rsi], eax
0x180006b84  test    eax, eax
0x180006b86  jz      short loc_180006BCB
0x180006b88  mov     rbx, [rsp+38h+arg_0]
0x180006b8d  mov     eax, edi
0x180006b8f  mov     rsi, [rsp+38h+arg_8]
0x180006b94  add     rsp, 30h
0x180006b98  pop     rdi
0x180006b99  retn
0x180006b9a  call    cs:__imp_GetLastError
0x180006ba0  cmp     eax, 3F0h
0x180006ba5  jz      short loc_180006B88
0x180006ba7  test    eax, eax
0x180006ba9  jg      short loc_180006BC0
0x180006bab  mov     edi, eax
0x180006bad  test    edi, edi
0x180006baf  jns     short loc_180006B88
0x180006bb1  lea     rax, aHrHresultFromW_27; "hr = HRESULT_FROM_WIN32(lastError)"
0x180006bb8  mov     r8d, 68h ; 'h'
0x180006bbe  jmp     short loc_180006BF1
0x180006bc0  movzx   edi, ax
0x180006bc3  or      edi, 80070000h
0x180006bc9  jmp     short loc_180006BAD
0x180006bcb  call    cs:__imp_GetLastError
0x180006bd1  mov     edi, eax
0x180006bd3  test    eax, eax
0x180006bd5  jle     short loc_180006BE0
0x180006bd7  movzx   edi, ax
0x180006bda  or      edi, 80070000h
0x180006be0  test    edi, edi
0x180006be2  jns     short loc_180006B88
0x180006be4  lea     rax, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180006beb  mov     r8d, 71h ; 'q'; unsigned int
0x180006bf1  mov     r9d, edi; int
0x180006bf4  mov     [rsp+38h+var_18], rax; char *
0x180006bf9  lea     rdx, aCautoreverttos; "CAutoRevertToSelf::Revert"
0x180006c00  lea     rcx, aOnecoreuapDsEx_51; "onecoreuap\\ds\\ext\\Live\\identity\\Li"...
0x180006c07  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180006c0c  jmp     loc_180006B88
```
