# WerpReadPebFromProcess(void *,void *,ulong,ulong)

- ea: `0x140016ee0`
- end: `0x14001702d`
- name: `?WerpReadPebFromProcess@@YAJPEAX0KK@Z`
- size: `333`
- prototype: `signed int __fastcall(HANDLE hProcess, void *lpBuffer)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140016b30`

## callees

- `0x140002fc8`
- `0x140016ee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016fe1`
- `ntdll!NtQueryInformationProcess` at `0x140016f27`
- `ntdll!NtQueryInformationProcess` at `0x140016f27`
- `ntdll!DbgPrintEx` at `0x140016f4f`
- `ntdll!DbgPrintEx` at `0x140016f87`
- `ntdll!DbgPrintEx` at `0x140016fdb`
- `ntdll!DbgPrintEx` at `0x140017017`
- `ntdll!DbgPrintEx` at `0x140016f4f`
- `ntdll!DbgPrintEx` at `0x140016f87`
- `ntdll!DbgPrintEx` at `0x140016fdb`
- `ntdll!DbgPrintEx` at `0x140017017`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140016fb3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140016fb3`

## string_xrefs

- `0x140016fcd`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n`

## pseudocode

```c
signed int __fastcall WerpReadPebFromProcess(HANDLE hProcess, void *lpBuffer)
{
  DWORD v4; // eax
  signed int result; // eax
  DWORD v6; // eax
  DWORD CurrentProcessId_0; // eax
  DWORD v8; // eax
  _QWORD v9[7]; // [rsp+30h] [rbp-38h] BYREF

  memset(v9, 0, 48);
  if ( hProcess && lpBuffer )
  {
    if ( NtQueryInformationProcess(hProcess, ProcessBasicInformation, v9, 0x30u, 0) >= 0 )
    {
      if ( v9[1] )
      {
        if ( ReadProcessMemory(hProcess, (LPCVOID)(v9[1] + 856LL), lpBuffer, 8u, 0) )
        {
          return 0;
        }
        else
        {
          CurrentProcessId_0 = GetCurrentProcessId_0();
          DbgPrintEx(
            0x96u,
            0,
            "WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n",
            CurrentProcessId_0,
            3126);
          result = GetLastError();
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
      else
      {
        v6 = GetCurrentProcessId_0();
        DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR No PEB for process\n", v6, 3116);
        return -2147467259;
      }
    }
    else
    {
      v4 = GetCurrentProcessId_0();
      DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR NtQueryInformationProcess failed\n", v4, 3108);
      return -2147024890;
    }
  }
  else
  {
    v8 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid arg\n", v8, 3098);
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x140016ee0  mov     rax, rsp
0x140016ee3  mov     [rax+8], rbx
0x140016ee7  push    rdi
0x140016ee8  sub     rsp, 60h
0x140016eec  xorps   xmm0, xmm0
0x140016eef  mov     rdi, rdx
0x140016ef2  mov     rbx, rcx
0x140016ef5  movups  xmmword ptr [rax-38h], xmm0
0x140016ef9  movups  xmmword ptr [rax-28h], xmm0
0x140016efd  movups  xmmword ptr [rax-18h], xmm0
0x140016f01  test    rcx, rcx
0x140016f04  jz      loc_140016FF9
0x140016f0a  test    rdx, rdx
0x140016f0d  jz      loc_140016FF9
0x140016f13  mov     r9d, 30h ; '0'; ProcessInformationLength
0x140016f19  mov     qword ptr [rax-48h], 0
0x140016f21  lea     r8, [rax-38h]; ProcessInformation
0x140016f25  xor     edx, edx; ProcessInformationClass
0x140016f27  call    cs:__imp_NtQueryInformationProcess
0x140016f2d  test    eax, eax
0x140016f2f  jns     short loc_140016F5F
0x140016f31  call    GetCurrentProcessId_0
0x140016f36  mov     r9d, eax
0x140016f39  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C24h
0x140016f41  lea     r8, aWerCrashapiUUE_5; "WER/CrashAPI/%u:%u: ERROR NtQueryInform"...
0x140016f48  xor     edx, edx; Level
0x140016f4a  mov     ecx, 96h; ComponentId
0x140016f4f  call    cs:__imp_DbgPrintEx
0x140016f55  mov     eax, 80070006h
0x140016f5a  jmp     loc_140017022
0x140016f5f  mov     rdx, [rsp+68h+var_30]
0x140016f64  test    rdx, rdx
0x140016f67  jnz     short loc_140016F97
0x140016f69  call    GetCurrentProcessId_0
0x140016f6e  mov     r9d, eax
0x140016f71  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C2Ch
0x140016f79  lea     r8, aWerCrashapiUUE_10; "WER/CrashAPI/%u:%u: ERROR No PEB for pr"...
0x140016f80  xor     edx, edx; Level
0x140016f82  mov     ecx, 96h; ComponentId
0x140016f87  call    cs:__imp_DbgPrintEx
0x140016f8d  mov     eax, 80004005h
0x140016f92  jmp     loc_140017022
0x140016f97  add     rdx, 358h; lpBaseAddress
0x140016f9e  mov     [rsp+68h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x140016fa7  mov     r9d, 8; nSize
0x140016fad  mov     r8, rdi; lpBuffer
0x140016fb0  mov     rcx, rbx; hProcess
0x140016fb3  call    cs:__imp_ReadProcessMemory
0x140016fb9  test    eax, eax
0x140016fbb  jnz     short loc_140016FF5
0x140016fbd  call    GetCurrentProcessId_0
0x140016fc2  mov     r9d, eax
0x140016fc5  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C36h
0x140016fcd  lea     r8, aWerCrashapiUUE_4; "WER/CrashAPI/%u:%u: ERROR ReadProcessMe"...
0x140016fd4  xor     edx, edx; Level
0x140016fd6  mov     ecx, 96h; ComponentId
0x140016fdb  call    cs:__imp_DbgPrintEx
0x140016fe1  call    cs:__imp_GetLastError
0x140016fe7  test    eax, eax
0x140016fe9  jle     short loc_140017022
0x140016feb  movzx   eax, ax
0x140016fee  or      eax, 80070000h
0x140016ff3  jmp     short loc_140017022
0x140016ff5  xor     eax, eax
0x140016ff7  jmp     short loc_140017022
0x140016ff9  call    GetCurrentProcessId_0
0x140016ffe  mov     r9d, eax
0x140017001  mov     dword ptr [rsp+68h+lpNumberOfBytesRead], 0C1Ah
0x140017009  lea     r8, aWerCrashapiUUE; "WER/CrashAPI/%u:%u: ERROR Invalid arg\n"
0x140017010  xor     edx, edx; Level
0x140017012  mov     ecx, 96h; ComponentId
0x140017017  call    cs:__imp_DbgPrintEx
0x14001701d  mov     eax, 80070057h
0x140017022  mov     rbx, [rsp+68h+arg_0]
0x140017027  add     rsp, 60h
0x14001702b  pop     rdi
0x14001702c  retn
```
