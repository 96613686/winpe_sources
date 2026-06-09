# WerpReadPeb32FromProcess

- ea: `0x140016d80`
- end: `0x140016ed8`
- name: `WerpReadPeb32FromProcess`
- size: `344`
- prototype: `signed int __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140016b30`

## callees

- `0x140002fc8`
- `0x140016d80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016e87`
- `ntdll!NtQueryInformationProcess` at `0x140016dc6`
- `ntdll!NtQueryInformationProcess` at `0x140016dc6`
- `ntdll!DbgPrintEx` at `0x140016df4`
- `ntdll!DbgPrintEx` at `0x140016e2d`
- `ntdll!DbgPrintEx` at `0x140016e81`
- `ntdll!DbgPrintEx` at `0x140016ebd`
- `ntdll!DbgPrintEx` at `0x140016df4`
- `ntdll!DbgPrintEx` at `0x140016e2d`
- `ntdll!DbgPrintEx` at `0x140016e81`
- `ntdll!DbgPrintEx` at `0x140016ebd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140016e59`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140016e59`

## string_xrefs

- `0x140016e73`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n`

## pseudocode

```c
signed int __fastcall WerpReadPeb32FromProcess(HANDLE hProcess, LPVOID lpBuffer)
{
  NTSTATUS v4; // ebx
  DWORD v5; // eax
  signed int result; // eax
  DWORD v7; // eax
  DWORD CurrentProcessId_0; // eax
  DWORD v9; // eax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  if ( hProcess && lpBuffer )
  {
    v4 = NtQueryInformationProcess(hProcess, ProcessWow64Information, &v10, 8u, 0);
    if ( v4 >= 0 )
    {
      if ( v10 )
      {
        if ( ReadProcessMemory(hProcess, (LPCVOID)(v10 + 560), lpBuffer, 8u, 0) )
        {
          return 0;
        }
        else
        {
          CurrentProcessId_0 = GetCurrentProcessId_0();
          DbgPrintEx(
            0x96u,
            0,
            "WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n",
            CurrentProcessId_0,
            2970);
          result = GetLastError();
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
      else
      {
        v7 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR No 32 PEB for process\n", v7, 2960);
        return -2147467259;
      }
    }
    else
    {
      v5 = GetCurrentProcessId_0();
      DbgPrintEx(
        0x96u,
        0,
        "WER/CrashAPI/%u:%u: ERROR NtQueryInformationProcess failed with status 0x%x\n",
        v5,
        2952,
        v4);
      return v4 | 0x10000000;
    }
  }
  else
  {
    v9 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid arg\n", v9, 2939);
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x140016d80  mov     rax, rsp
0x140016d83  mov     [rax+10h], rbx
0x140016d87  mov     [rax+18h], rsi
0x140016d8b  push    rdi
0x140016d8c  sub     rsp, 30h
0x140016d90  mov     qword ptr [rax+8], 0
0x140016d98  mov     rsi, rdx
0x140016d9b  mov     rdi, rcx
0x140016d9e  test    rcx, rcx
0x140016da1  jz      loc_140016E9F
0x140016da7  test    rdx, rdx
0x140016daa  jz      loc_140016E9F
0x140016db0  mov     r9d, 8; ProcessInformationLength
0x140016db6  mov     qword ptr [rax-18h], 0
0x140016dbe  lea     r8, [rax+8]; ProcessInformation
0x140016dc2  lea     edx, [r9+12h]; ProcessInformationClass
0x140016dc6  call    cs:__imp_NtQueryInformationProcess
0x140016dcc  mov     ebx, eax
0x140016dce  test    eax, eax
0x140016dd0  jns     short loc_140016E05
0x140016dd2  call    GetCurrentProcessId_0
0x140016dd7  mov     r9d, eax
0x140016dda  mov     [rsp+38h+var_10], ebx
0x140016dde  lea     r8, aWerCrashapiUUE_6; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x140016de5  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B88h
0x140016ded  xor     edx, edx; Level
0x140016def  mov     ecx, 96h; ComponentId
0x140016df4  call    cs:__imp_DbgPrintEx
0x140016dfa  bts     ebx, 1Ch
0x140016dfe  mov     eax, ebx
0x140016e00  jmp     loc_140016EC8
0x140016e05  mov     rdx, [rsp+38h+arg_0]
0x140016e0a  test    rdx, rdx
0x140016e0d  jnz     short loc_140016E3D
0x140016e0f  call    GetCurrentProcessId_0
0x140016e14  mov     r9d, eax
0x140016e17  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B90h
0x140016e1f  lea     r8, aWerCrashapiUUE_7; "WER/CrashAPI/%u:%u: ERROR No 32 PEB for"...
0x140016e26  xor     edx, edx; Level
0x140016e28  mov     ecx, 96h; ComponentId
0x140016e2d  call    cs:__imp_DbgPrintEx
0x140016e33  mov     eax, 80004005h
0x140016e38  jmp     loc_140016EC8
0x140016e3d  add     rdx, 230h; lpBaseAddress
0x140016e44  mov     [rsp+38h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x140016e4d  mov     r9d, 8; nSize
0x140016e53  mov     r8, rsi; lpBuffer
0x140016e56  mov     rcx, rdi; hProcess
0x140016e59  call    cs:__imp_ReadProcessMemory
0x140016e5f  test    eax, eax
0x140016e61  jnz     short loc_140016E9B
0x140016e63  call    GetCurrentProcessId_0
0x140016e68  mov     r9d, eax
0x140016e6b  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B9Ah
0x140016e73  lea     r8, aWerCrashapiUUE_3; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x140016e7a  xor     edx, edx; Level
0x140016e7c  mov     ecx, 96h; ComponentId
0x140016e81  call    cs:__imp_DbgPrintEx
0x140016e87  call    cs:__imp_GetLastError
0x140016e8d  test    eax, eax
0x140016e8f  jle     short loc_140016EC8
0x140016e91  movzx   eax, ax
0x140016e94  or      eax, 80070000h
0x140016e99  jmp     short loc_140016EC8
0x140016e9b  xor     eax, eax
0x140016e9d  jmp     short loc_140016EC8
0x140016e9f  call    GetCurrentProcessId_0
0x140016ea4  mov     r9d, eax
0x140016ea7  mov     dword ptr [rsp+38h+lpNumberOfBytesRead], 0B7Bh
0x140016eaf  lea     r8, aWerCrashapiUUE; "WER/CrashAPI/%u:%u: ERROR Invalid arg\n"
0x140016eb6  xor     edx, edx; Level
0x140016eb8  mov     ecx, 96h; ComponentId
0x140016ebd  call    cs:__imp_DbgPrintEx
0x140016ec3  mov     eax, 80070057h
0x140016ec8  mov     rbx, [rsp+38h+arg_8]
0x140016ecd  mov     rsi, [rsp+38h+arg_10]
0x140016ed2  add     rsp, 30h
0x140016ed6  pop     rdi
0x140016ed7  retn
```
