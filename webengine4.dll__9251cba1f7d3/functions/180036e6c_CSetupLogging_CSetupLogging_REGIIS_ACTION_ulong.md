# CSetupLogging::CSetupLogging(REGIIS_ACTION,ulong)

- ea: `0x180036e6c`
- end: `0x18003700b`
- name: `??0CSetupLogging@@AEAA@W4REGIIS_ACTION@@K@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180039774`

## callees

- `0x180036e6c`
- `0x180037c08`
- `0x180038d2c`
- `0x18003e648`
- `0x18004d030`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180036fd7`
- `KERNEL32!WriteFile` at `0x180036fd7`
- `KERNEL32!InitializeCriticalSection` at `0x180036ea0`
- `KERNEL32!InitializeCriticalSection` at `0x180036ea0`
- `KERNEL32!lstrlenA` at `0x180036fb9`
- `KERNEL32!lstrlenA` at `0x180036fb9`
- `KERNEL32!WideCharToMultiByte` at `0x180036f52`
- `KERNEL32!WideCharToMultiByte` at `0x180036f52`
- `KERNEL32!FlushFileBuffers` at `0x180036fe0`
- `KERNEL32!FlushFileBuffers` at `0x180036fe0`

## string_xrefs

- `0x180036f0d`: `Uninstalling Language Pack:`

## pseudocode

```c
__int64 __fastcall CSetupLogging::CSetupLogging(__int64 a1, int a2, int a3)
{
  int v6; // ebx
  const char *v7; // rbx
  DWORD v8; // eax
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-A0h] BYREF
  CHAR MultiByteStr[272]; // [rsp+D0h] [rbp-30h] BYREF
  CHAR String[1312]; // [rsp+1E0h] [rbp+E0h] BYREF

  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  CSetupLogging::CreateLogFile((CSetupLogging *)a1);
  if ( *(_QWORD *)a1 )
  {
    *(_DWORD *)(a1 + 48) = 0;
    NumberOfBytesWritten = 0;
    memset_0(MultiByteStr, 0, 0x104u);
    memset_0(&Overlapped, 0, 0x64u);
    memset_0(String, 0, 0x515u);
    if ( a2 )
    {
      v6 = a2 - 1;
      if ( v6 )
      {
        if ( v6 == 4 )
          v7 = "Uninstalling Language Pack:";
        else
          v7 = "Other operation:";
      }
      else
      {
        v7 = "Unregistering ASP.NET isapi:";
      }
    }
    else
    {
      v7 = "Registering ASP.NET isapi:";
    }
    WideCharToMultiByte(0, 0, &Names::s_wszIsapiFullPath, -1, MultiByteStr, 260, 0, 0);
    CSetupLogging::GetDateTimeStamp((CSetupLogging *)a1, (char *)&Overlapped, 0x64u);
    StringCchPrintfA(
      String,
      0x515u,
      "********************************************************************************\r\n"
      "**** %s %s\r\n"
      "**** %s %s\r\n"
      "**** %s 0x%08x\r\n"
      "********************************************************************************\r\n"
      "\r\n",
      "Starting ASP.NET Setup at:",
      (const char *)&Overlapped,
      v7,
      MultiByteStr,
      "Internal flags:",
      a3);
    v8 = lstrlenA(String);
    WriteFile(*(HANDLE *)a1, String, v8, &NumberOfBytesWritten, 0);
    FlushFileBuffers(*(HANDLE *)a1);
  }
  return a1;
}

```

## disassembly

```asm
0x180036e6c  mov     [rsp-8+arg_8], rbx
0x180036e71  push    rbp
0x180036e72  push    rsi
0x180036e73  push    rdi
0x180036e74  lea     rbp, [rsp-610h]
0x180036e7c  sub     rsp, 710h
0x180036e83  mov     rax, cs:__security_cookie
0x180036e8a  xor     rax, rsp
0x180036e8d  mov     [rbp+620h+var_20], rax
0x180036e94  mov     rdi, rcx
0x180036e97  mov     esi, r8d
0x180036e9a  add     rcx, 8; lpCriticalSection
0x180036e9e  mov     ebx, edx
0x180036ea0  call    cs:__imp_InitializeCriticalSection
0x180036ea6  mov     rcx, rdi; this
0x180036ea9  call    ?CreateLogFile@CSetupLogging@@AEAAXXZ; CSetupLogging::CreateLogFile(void)
0x180036eae  cmp     qword ptr [rdi], 0
0x180036eb2  jz      loc_180036FE6
0x180036eb8  and     dword ptr [rdi+30h], 0
0x180036ebc  lea     rcx, [rbp+620h+MultiByteStr]; void *
0x180036ec0  and     [rsp+720h+NumberOfBytesWritten], 0
0x180036ec5  xor     edx, edx; Val
0x180036ec7  mov     r8d, 104h; Size
0x180036ecd  call    memset_0
0x180036ed2  xor     edx, edx; Val
0x180036ed4  lea     rcx, [rsp+720h+Overlapped]; void *
0x180036ed9  lea     r8d, [rdx+64h]; Size
0x180036edd  call    memset_0
0x180036ee2  xor     edx, edx; Val
0x180036ee4  lea     rcx, [rbp+620h+String]; void *
0x180036eeb  mov     r8d, 515h; Size
0x180036ef1  call    memset_0
0x180036ef6  test    ebx, ebx
0x180036ef8  jz      short loc_180036F1F
0x180036efa  sub     ebx, 1
0x180036efd  jz      short loc_180036F16
0x180036eff  cmp     ebx, 4
0x180036f02  jz      short loc_180036F0D
0x180036f04  lea     rbx, aOtherOperation; "Other operation:"
0x180036f0b  jmp     short loc_180036F26
0x180036f0d  lea     rbx, aUninstallingLa; "Uninstalling Language Pack:"
0x180036f14  jmp     short loc_180036F26
0x180036f16  lea     rbx, aUnregisteringA; "Unregistering ASP.NET isapi:"
0x180036f1d  jmp     short loc_180036F26
0x180036f1f  lea     rbx, aRegisteringAsp; "Registering ASP.NET isapi:"
0x180036f26  and     [rsp+720h+var_6E8], 0
0x180036f2c  lea     rax, [rbp+620h+MultiByteStr]
0x180036f30  and     [rsp+720h+var_6F0], 0
0x180036f36  lea     r8, ?s_wszIsapiFullPath@Names@@0PAGA; lpWideCharStr
0x180036f3d  mov     [rsp+720h+cbMultiByte], 104h; cbMultiByte
0x180036f45  or      r9d, 0FFFFFFFFh; cchWideChar
0x180036f49  xor     edx, edx; dwFlags
0x180036f4b  mov     [rsp+720h+lpMultiByteStr], rax; lpMultiByteStr
0x180036f50  xor     ecx, ecx; CodePage
0x180036f52  call    cs:__imp_WideCharToMultiByte
0x180036f58  mov     r8d, 64h ; 'd'; unsigned int
0x180036f5e  lea     rdx, [rsp+720h+Overlapped]; char *
0x180036f63  mov     rcx, rdi; this
0x180036f66  call    ?GetDateTimeStamp@CSetupLogging@@AEAAXPEADK@Z; CSetupLogging::GetDateTimeStamp(char *,ulong)
0x180036f6b  mov     [rsp+720h+var_6E0], esi
0x180036f6f  lea     rax, aInternalFlags; "Internal flags:"
0x180036f76  mov     [rsp+720h+var_6E8], rax
0x180036f7b  lea     r9, aStartingAspNet; "Starting ASP.NET Setup at:"
0x180036f82  lea     rax, [rbp+620h+MultiByteStr]
0x180036f86  mov     edx, 515h; unsigned __int64
0x180036f8b  mov     [rsp+720h+var_6F0], rax
0x180036f90  lea     r8, asc_180075830; "***************************************"...
0x180036f97  lea     rax, [rsp+720h+Overlapped]
0x180036f9c  mov     qword ptr [rsp+720h+cbMultiByte], rbx
0x180036fa1  lea     rcx, [rbp+620h+String]; Buffer
0x180036fa8  mov     [rsp+720h+lpMultiByteStr], rax; lpOverlapped
0x180036fad  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180036fb2  lea     rcx, [rbp+620h+String]; lpString
0x180036fb9  call    cs:__imp_lstrlenA
0x180036fbf  mov     rcx, [rdi]; hFile
0x180036fc2  lea     r9, [rsp+720h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180036fc7  and     [rsp+720h+lpMultiByteStr], 0
0x180036fcd  lea     rdx, [rbp+620h+String]; lpBuffer
0x180036fd4  mov     r8d, eax; nNumberOfBytesToWrite
0x180036fd7  call    cs:__imp_WriteFile
0x180036fdd  mov     rcx, [rdi]; hFile
0x180036fe0  call    cs:__imp_FlushFileBuffers
0x180036fe6  mov     rax, rdi
0x180036fe9  mov     rcx, [rbp+620h+var_20]
0x180036ff0  xor     rcx, rsp; StackCookie
0x180036ff3  call    __security_check_cookie
0x180036ff8  mov     rbx, [rsp+720h+arg_8]
0x180037000  add     rsp, 710h
0x180037007  pop     rdi
0x180037008  pop     rsi
0x180037009  pop     rbp
0x18003700a  retn
```
