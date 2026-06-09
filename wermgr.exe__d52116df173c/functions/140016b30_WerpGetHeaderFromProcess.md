# WerpGetHeaderFromProcess

- ea: `0x140016b30`
- end: `0x140016d7a`
- name: `WerpGetHeaderFromProcess`
- size: `586`
- prototype: `signed int __fastcall(HANDLE hProcess, _WORD *lpBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400170a4`

## callees

- `0x140002fc8`
- `0x140016b30`
- `0x140016d80`
- `0x140016ee0`
- `0x140017034`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140016b8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140016b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016cf0`
- `ntdll!DbgPrintEx` at `0x140016c2f`
- `ntdll!DbgPrintEx` at `0x140016c6e`
- `ntdll!DbgPrintEx` at `0x140016cea`
- `ntdll!DbgPrintEx` at `0x140016d2e`
- `ntdll!DbgPrintEx` at `0x140016d64`
- `ntdll!DbgPrintEx` at `0x140016c2f`
- `ntdll!DbgPrintEx` at `0x140016c6e`
- `ntdll!DbgPrintEx` at `0x140016cea`
- `ntdll!DbgPrintEx` at `0x140016d2e`
- `ntdll!DbgPrintEx` at `0x140016d64`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140016cc2`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140016cc2`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016b70`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016b97`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016bb1`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016b70`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016b97`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140016bb1`

## string_xrefs

- `0x140016bea`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x140016c21`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x140016c60`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`
- `0x140016cdc`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`

## pseudocode

```c
signed int __fastcall WerpGetHeaderFromProcess(HANDLE hProcess, _WORD *lpBuffer)
{
  int v4; // eax
  BOOL v5; // edi
  HANDLE CurrentProcess; // rax
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  int v9; // eax
  DWORD v10; // eax
  int v11; // r14d
  DWORD v12; // eax
  signed int result; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD CurrentProcessId_0; // eax
  WINBOOL Wow64Process; // [rsp+60h] [rbp+30h] BYREF
  WINBOOL v20; // [rsp+70h] [rbp+40h] BYREF
  LPCVOID lpBaseAddress; // [rsp+78h] [rbp+48h] BYREF

  lpBaseAddress = 0;
  Wow64Process = 0;
  v20 = 0;
  if ( !hProcess || !lpBuffer )
  {
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid arguments\n", CurrentProcessId_0, 3168);
    return -2147024809;
  }
  v4 = IsWow64Process(hProcess, &Wow64Process);
  if ( v4 )
    v4 = Wow64Process;
  else
    Wow64Process = 0;
  v5 = v4 == 0;
  CurrentProcess = GetCurrentProcess();
  if ( !IsWow64Process(CurrentProcess, &v20) )
    v20 = 0;
  if ( v20 )
  {
    v9 = IsWow64Process(hProcess, &Wow64Process);
    if ( v9 )
      v9 = Wow64Process;
    else
      Wow64Process = 0;
    if ( !v9 )
    {
      v5 = 1;
LABEL_17:
      if ( v20 && v5 )
      {
        v10 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n", v10, 3215);
        return -2147024809;
      }
      v11 = WerpReadPebFromProcess(hProcess, &lpBaseAddress, v7, v8);
      if ( v11 < 0 )
      {
        v12 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n", v12, 3236);
        return v11;
      }
      goto LABEL_23;
    }
    v5 = 0;
  }
  else
  {
    v9 = Wow64Process;
  }
  if ( !v9 )
    goto LABEL_17;
  v11 = WerpReadPeb32FromProcess(hProcess, &lpBaseAddress);
  if ( v11 < 0 )
  {
    v15 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n", v15, 3255);
    return v11;
  }
LABEL_23:
  if ( !lpBaseAddress )
    return -2147023728;
  if ( v20 && v5 )
  {
    v14 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n",
      v14,
      3284);
    return -805306367;
  }
  else if ( ReadProcessMemory(hProcess, lpBaseAddress, lpBuffer, 0x968u, 0) )
  {
    if ( (int)WerpValidatePebHeader(lpBuffer) >= 0 )
    {
      result = 0;
      lpBuffer[1107] = 0;
    }
    else
    {
      v17 = GetCurrentProcessId_0();
      DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR WerpValidatePebHeader failed\n", v17, 3308);
      return -2147467259;
    }
  }
  else
  {
    v16 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      0,
      "WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n",
      v16,
      3299);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x140016b30  push    rbp
0x140016b32  push    rbx
0x140016b33  push    rsi
0x140016b34  push    rdi
0x140016b35  push    r14
0x140016b37  mov     rbp, rsp
0x140016b3a  sub     rsp, 30h
0x140016b3e  mov     [rbp+lpBaseAddress], 0
0x140016b46  mov     rsi, rdx
0x140016b49  mov     [rbp+Wow64Process], 0
0x140016b50  mov     rbx, rcx
0x140016b53  mov     [rbp+arg_10], 0
0x140016b5a  test    rcx, rcx
0x140016b5d  jz      loc_140016D46
0x140016b63  test    rdx, rdx
0x140016b66  jz      loc_140016D46
0x140016b6c  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x140016b70  call    cs:__imp_IsWow64Process
0x140016b76  test    eax, eax
0x140016b78  jnz     short loc_140016B7F
0x140016b7a  mov     [rbp+Wow64Process], eax
0x140016b7d  jmp     short loc_140016B82
0x140016b7f  mov     eax, [rbp+Wow64Process]
0x140016b82  xor     edi, edi
0x140016b84  test    eax, eax
0x140016b86  setz    dil
0x140016b8a  call    cs:__imp_GetCurrentProcess
0x140016b90  mov     rcx, rax; hProcess
0x140016b93  lea     rdx, [rbp+arg_10]; Wow64Process
0x140016b97  call    cs:__imp_IsWow64Process
0x140016b9d  test    eax, eax
0x140016b9f  jnz     short loc_140016BA4
0x140016ba1  mov     [rbp+arg_10], eax
0x140016ba4  cmp     [rbp+arg_10], 0
0x140016ba8  jz      short loc_140016BD0
0x140016baa  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x140016bae  mov     rcx, rbx; hProcess
0x140016bb1  call    cs:__imp_IsWow64Process
0x140016bb7  test    eax, eax
0x140016bb9  jnz     short loc_140016BC0
0x140016bbb  mov     [rbp+Wow64Process], eax
0x140016bbe  jmp     short loc_140016BC3
0x140016bc0  mov     eax, [rbp+Wow64Process]
0x140016bc3  test    eax, eax
0x140016bc5  jnz     short loc_140016BCC
0x140016bc7  lea     edi, [rax+1]
0x140016bca  jmp     short loc_140016BDB
0x140016bcc  xor     edi, edi
0x140016bce  jmp     short loc_140016BD3
0x140016bd0  mov     eax, [rbp+Wow64Process]
0x140016bd3  test    eax, eax
0x140016bd5  jnz     loc_140016C7E
0x140016bdb  cmp     [rbp+arg_10], 0
0x140016bdf  jz      short loc_140016BFE
0x140016be1  test    edi, edi
0x140016be3  jz      short loc_140016BFE
0x140016be5  call    GetCurrentProcessId_0
0x140016bea  lea     r8, Format; "WER/CrashAPI/%u:%u: ERROR Failed to rea"...
0x140016bf1  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0C8Fh
0x140016bf9  jmp     loc_140016D5A
0x140016bfe  lea     rdx, [rbp+lpBaseAddress]; lpBuffer
0x140016c02  mov     rcx, rbx; hProcess
0x140016c05  call    ?WerpReadPebFromProcess@@YAJPEAX0KK@Z; WerpReadPebFromProcess(void *,void *,ulong,ulong)
0x140016c0a  mov     r14d, eax
0x140016c0d  test    eax, eax
0x140016c0f  jns     short loc_140016C3D
0x140016c11  call    GetCurrentProcessId_0
0x140016c16  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CA4h
0x140016c1e  mov     r9d, eax
0x140016c21  lea     r8, Format; "WER/CrashAPI/%u:%u: ERROR Failed to rea"...
0x140016c28  xor     edx, edx; Level
0x140016c2a  mov     ecx, 96h; ComponentId
0x140016c2f  call    cs:__imp_DbgPrintEx
0x140016c35  mov     eax, r14d
0x140016c38  jmp     loc_140016D6F
0x140016c3d  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x140016c41  test    rdx, rdx
0x140016c44  jz      short loc_140016CA3
0x140016c46  cmp     [rbp+arg_10], 0
0x140016c4a  jz      short loc_140016CAD
0x140016c4c  test    edi, edi
0x140016c4e  jz      short loc_140016CAD
0x140016c50  call    GetCurrentProcessId_0
0x140016c55  mov     r9d, eax
0x140016c58  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CD4h
0x140016c60  lea     r8, aWerCrashapiUUE_0; "WER/CrashAPI/%u:%u: ERROR WerpNtWow64Re"...
0x140016c67  xor     edx, edx; Level
0x140016c69  mov     ecx, 96h; ComponentId
0x140016c6e  call    cs:__imp_DbgPrintEx
0x140016c74  mov     eax, 0D0000001h
0x140016c79  jmp     loc_140016D6F
0x140016c7e  lea     rdx, [rbp+lpBaseAddress]; lpBuffer
0x140016c82  mov     rcx, rbx; hProcess
0x140016c85  call    WerpReadPeb32FromProcess
0x140016c8a  mov     r14d, eax
0x140016c8d  test    eax, eax
0x140016c8f  jns     short loc_140016C3D
0x140016c91  call    GetCurrentProcessId_0
0x140016c96  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CB7h
0x140016c9e  jmp     loc_140016C1E
0x140016ca3  mov     eax, 80070490h
0x140016ca8  jmp     loc_140016D6F
0x140016cad  mov     r9d, 968h; nSize
0x140016cb3  mov     [rsp+30h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x140016cbc  mov     r8, rsi; lpBuffer
0x140016cbf  mov     rcx, rbx; hProcess
0x140016cc2  call    cs:__imp_ReadProcessMemory
0x140016cc8  test    eax, eax
0x140016cca  jnz     short loc_140016D04
0x140016ccc  call    GetCurrentProcessId_0
0x140016cd1  mov     r9d, eax
0x140016cd4  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CE3h
0x140016cdc  lea     r8, aWerCrashapiUUE_2; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x140016ce3  xor     edx, edx; Level
0x140016ce5  mov     ecx, 96h; ComponentId
0x140016cea  call    cs:__imp_DbgPrintEx
0x140016cf0  call    cs:__imp_GetLastError
0x140016cf6  test    eax, eax
0x140016cf8  jle     short loc_140016D6F
0x140016cfa  movzx   eax, ax
0x140016cfd  or      eax, 80070000h
0x140016d02  jmp     short loc_140016D6F
0x140016d04  mov     rcx, rsi
0x140016d07  call    WerpValidatePebHeader
0x140016d0c  test    eax, eax
0x140016d0e  jns     short loc_140016D3B
0x140016d10  call    GetCurrentProcessId_0
0x140016d15  mov     r9d, eax
0x140016d18  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0CECh
0x140016d20  lea     r8, aWerCrashapiUUE_8; "WER/CrashAPI/%u:%u: ERROR WerpValidateP"...
0x140016d27  xor     edx, edx; Level
0x140016d29  mov     ecx, 96h; ComponentId
0x140016d2e  call    cs:__imp_DbgPrintEx
0x140016d34  mov     eax, 80004005h
0x140016d39  jmp     short loc_140016D6F
0x140016d3b  xor     eax, eax
0x140016d3d  mov     [rsi+8A6h], ax
0x140016d44  jmp     short loc_140016D6F
0x140016d46  call    GetCurrentProcessId_0
0x140016d4b  lea     r8, aWerCrashapiUUE_9; "WER/CrashAPI/%u:%u: ERROR Invalid argum"...
0x140016d52  mov     dword ptr [rsp+30h+lpNumberOfBytesRead], 0C60h
0x140016d5a  mov     r9d, eax
0x140016d5d  xor     edx, edx; Level
0x140016d5f  mov     ecx, 96h; ComponentId
0x140016d64  call    cs:__imp_DbgPrintEx
0x140016d6a  mov     eax, 80070057h
0x140016d6f  add     rsp, 30h
0x140016d73  pop     r14
0x140016d75  pop     rdi
0x140016d76  pop     rsi
0x140016d77  pop     rbx
0x140016d78  pop     rbp
0x140016d79  retn
```
