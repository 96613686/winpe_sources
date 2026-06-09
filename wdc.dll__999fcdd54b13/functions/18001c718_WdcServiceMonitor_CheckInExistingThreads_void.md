# WdcServiceMonitor::CheckInExistingThreads(void)

- ea: `0x18001c718`
- end: `0x18001c9ab`
- name: `?CheckInExistingThreads@WdcServiceMonitor@@QEAAJXZ`
- size: `659`
- prototype: `__int64 __fastcall(WdcThreadStat **this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180035ad0`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x1800156f0`
- `0x18001c718`
- `0x18001c9b4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001c79d`
- `ntdll!RtlNtStatusToDosError` at `0x18001c79d`
- `ntdll!NtQuerySystemInformation` at `0x18001c75f`
- `ntdll!NtQuerySystemInformation` at `0x18001c75f`
- `KERNEL32!CloseHandle` at `0x18001c82d`
- `KERNEL32!CloseHandle` at `0x18001c985`
- `KERNEL32!CloseHandle` at `0x18001c82d`
- `KERNEL32!CloseHandle` at `0x18001c985`
- `KERNEL32!GetLastError` at `0x18001c8ca`
- `KERNEL32!GetLastError` at `0x18001c90a`
- `KERNEL32!GetLastError` at `0x18001c8ca`
- `KERNEL32!GetLastError` at `0x18001c90a`
- `KERNEL32!IsWow64Process` at `0x18001c867`
- `KERNEL32!IsWow64Process` at `0x18001c867`
- `KERNEL32!ReadProcessMemory` at `0x18001c8bc`
- `KERNEL32!ReadProcessMemory` at `0x18001c8fc`
- `KERNEL32!ReadProcessMemory` at `0x18001c8bc`
- `KERNEL32!ReadProcessMemory` at `0x18001c8fc`

## string_xrefs

- `0x18001c7f0`: `base\diagnosis\pdui\perfmon\mon\service.cpp`
- `0x18001c7e9`: `WdcServiceMonitor::CheckInExistingThreads`

## pseudocode

```c
__int64 __fastcall WdcServiceMonitor::CheckInExistingThreads(WdcThreadStat **this)
{
  char *v1; // rsi
  union _LARGE_INTEGER *v2; // r15
  ULONG v3; // r12d
  union _LARGE_INTEGER *v4; // rdi
  ULONG v5; // r8d
  const char *QuadPart; // rdx
  NTSTATUS v7; // ebx
  int v8; // r8d
  signed int v9; // eax
  union _LARGE_INTEGER *v10; // rdi
  int v11; // eax
  unsigned int v12; // r13d
  union _LARGE_INTEGER *v13; // r14
  signed int LastError; // eax
  signed int v15; // eax
  unsigned int LowPart; // [rsp+30h] [rbp-28h]
  HANDLE hProcess; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v19[2]; // [rsp+40h] [rbp-18h] BYREF
  union _LARGE_INTEGER *v20; // [rsp+48h] [rbp-10h]
  ULONG ReturnLength; // [rsp+A8h] [rbp+50h] BYREF
  unsigned int Buffer; // [rsp+B0h] [rbp+58h] BYREF
  WINBOOL Wow64Process; // [rsp+B8h] [rbp+60h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v20 = 0;
  v4 = 0;
  hProcess = 0;
  v5 = 0;
  Buffer = 0;
  ReturnLength = 0;
  Wow64Process = 0;
  *(_QWORD *)v19 = 0;
  while ( 1 )
  {
    v7 = NtQuerySystemInformation(SystemExtendedProcessInformation, v4, v5, &ReturnLength);
    if ( v7 >= 0 )
      break;
    if ( v4 )
      WdcFree(v4, QuadPart, v8);
    if ( v7 != -1073741820 )
      goto LABEL_9;
    v4 = (union _LARGE_INTEGER *)WdcAlloc(ReturnLength, QuadPart, v8);
    if ( !v4 )
    {
      v7 = -1073741801;
      goto LABEL_9;
    }
    v5 = ReturnLength;
  }
  v3 = ReturnLength;
  v2 = v4;
  v20 = v4;
  if ( v7 )
  {
LABEL_9:
    v9 = RtlNtStatusToDosError(v7);
    v7 = 0;
    if ( v9 )
    {
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      else
        v7 = v9;
    }
    if ( v7 < 0 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mon\\service.cpp",
        "WdcServiceMonitor::CheckInExistingThreads",
        0,
        L"FAILURE: 0x%08x",
        v7);
      goto LABEL_50;
    }
  }
  if ( v3 < 0x100 )
  {
    v7 = 0;
    goto LABEL_50;
  }
  v10 = v2;
LABEL_19:
  while ( v10->LowPart )
  {
    v10 = (union _LARGE_INTEGER *)((char *)v10 + v10->LowPart);
    if ( (int)v10 - (int)v2 > v3 )
    {
      v7 = 0;
      break;
    }
    if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v1);
      hProcess = 0;
    }
    v11 = WdcSafeOpenProcess(0x1010u, (int)QuadPart, v10[10].LowPart, v10[4], &hProcess);
    v1 = (char *)hProcess;
    v7 = v11;
    if ( v11 >= 0 )
    {
      if ( IsWow64Process(hProcess, &Wow64Process) )
      {
        v12 = 0;
        v13 = v10 + 32;
        if ( v10->HighPart )
        {
          while ( 1 )
          {
            QuadPart = (const char *)v13[13].QuadPart;
            if ( QuadPart )
            {
              LowPart = v13[6].LowPart;
              if ( Wow64Process )
              {
                if ( ReadProcessMemory(v1, QuadPart + 12128, &Buffer, 4u, 0) )
                {
                  v7 = 0;
LABEL_34:
                  v8 = Buffer;
                  goto LABEL_42;
                }
                LastError = GetLastError();
                v7 = LastError;
                if ( LastError )
                {
                  if ( LastError > 0 )
                    v7 = (unsigned __int16)LastError | 0x80070000;
                  if ( v7 < 0 )
                    goto LABEL_45;
                  goto LABEL_34;
                }
              }
              else
              {
                if ( ReadProcessMemory(v1, QuadPart + 5920, v19, 8u, 0) )
                {
                  v7 = 0;
                  goto LABEL_41;
                }
                v15 = GetLastError();
                v7 = v15;
                if ( v15 )
                {
                  if ( v15 > 0 )
                    v7 = (unsigned __int16)v15 | 0x80070000;
                  if ( v7 < 0 )
                    goto LABEL_45;
LABEL_41:
                  v8 = v19[0];
                  Buffer = v19[0];
LABEL_42:
                  if ( v8 )
                  {
                    WdcThreadStat::CheckIn(this[1168], LowPart, v8, 0, v13->QuadPart + v13[1].QuadPart);
                    v7 = 0;
                  }
                  goto LABEL_45;
                }
              }
              v7 = -2147467259;
            }
LABEL_45:
            ++v12;
            v13 += 17;
            if ( v12 >= v10->HighPart )
            {
              v2 = v20;
              goto LABEL_19;
            }
          }
        }
      }
    }
  }
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v1);
LABEL_50:
  if ( v2 )
    WdcFree(v2, QuadPart, v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001c718  mov     [rsp-40h+arg_0], rcx
0x18001c71d  push    rbp
0x18001c71e  push    rbx
0x18001c71f  push    rsi
0x18001c720  push    rdi
0x18001c721  push    r12
0x18001c723  push    r13
0x18001c725  push    r14
0x18001c727  push    r15
0x18001c729  mov     rbp, rsp
0x18001c72c  sub     rsp, 58h
0x18001c730  xor     esi, esi
0x18001c732  xor     r15d, r15d
0x18001c735  xor     r12d, r12d
0x18001c738  mov     [rbp+var_10], r15
0x18001c73c  xor     edi, edi
0x18001c73e  mov     [rbp+hProcess], rsi
0x18001c742  xor     r8d, r8d; SystemInformationLength
0x18001c745  mov     [rbp+Buffer], esi
0x18001c748  mov     [rbp+ReturnLength], r8d
0x18001c74c  mov     [rbp+Wow64Process], esi
0x18001c74f  mov     qword ptr [rbp+var_18], rsi
0x18001c753  lea     r9, [rbp+ReturnLength]; ReturnLength
0x18001c757  mov     rdx, rdi; SystemInformation
0x18001c75a  mov     ecx, 39h ; '9'; SystemInformationClass
0x18001c75f  call    cs:__imp_NtQuerySystemInformation
0x18001c765  mov     ebx, eax
0x18001c767  test    eax, eax
0x18001c769  jns     short loc_18001C7AF
0x18001c76b  test    rdi, rdi
0x18001c76e  jz      short loc_18001C778
0x18001c770  mov     rcx, rdi; void *
0x18001c773  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18001c778  cmp     ebx, 0C0000004h
0x18001c77e  jnz     short loc_18001C79B
0x18001c780  mov     ecx, [rbp+ReturnLength]; dwBytes
0x18001c783  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18001c788  mov     rdi, rax
0x18001c78b  test    rax, rax
0x18001c78e  jz      short loc_18001C796
0x18001c790  mov     r8d, [rbp+ReturnLength]
0x18001c794  jmp     short loc_18001C753
0x18001c796  mov     ebx, 0C0000017h
0x18001c79b  mov     ecx, ebx; Status
0x18001c79d  call    cs:__imp_RtlNtStatusToDosError
0x18001c7a3  xor     ebx, ebx
0x18001c7a5  test    eax, eax
0x18001c7a7  jz      short loc_18001C7D7
0x18001c7a9  jg      short loc_18001C7CE
0x18001c7ab  mov     ebx, eax
0x18001c7ad  jmp     short loc_18001C7D7
0x18001c7af  mov     r12d, [rbp+ReturnLength]
0x18001c7b3  mov     r15, rdi
0x18001c7b6  mov     [rbp+var_10], rdi
0x18001c7ba  test    ebx, ebx
0x18001c7bc  jnz     short loc_18001C79B
0x18001c7be  cmp     r12d, 100h
0x18001c7c5  jnb     short loc_18001C801
0x18001c7c7  xor     ebx, ebx
0x18001c7c9  jmp     loc_18001C98B
0x18001c7ce  movzx   ebx, ax
0x18001c7d1  or      ebx, 80070000h
0x18001c7d7  test    ebx, ebx
0x18001c7d9  jns     short loc_18001C7BE
0x18001c7db  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001c7e2  mov     dword ptr [rsp+58h+lpNumberOfBytesRead], ebx
0x18001c7e6  xor     r8d, r8d; int
0x18001c7e9  lea     rdx, aWdcservicemoni_7; "WdcServiceMonitor::CheckInExistingThrea"...
0x18001c7f0  lea     rcx, aBaseDiagnosisP_45; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001c7f7  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001c7fc  jmp     loc_18001C98B
0x18001c801  mov     rdi, r15
0x18001c804  cmp     dword ptr [rdi], 0
0x18001c807  jz      loc_18001C978
0x18001c80d  mov     eax, [rdi]
0x18001c80f  add     rdi, rax
0x18001c812  mov     eax, edi
0x18001c814  sub     eax, r15d
0x18001c817  cmp     eax, r12d
0x18001c81a  ja      loc_18001C976
0x18001c820  lea     rax, [rsi-1]
0x18001c824  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c828  ja      short loc_18001C83B
0x18001c82a  mov     rcx, rsi; hObject
0x18001c82d  call    cs:__imp_CloseHandle
0x18001c833  mov     [rbp+hProcess], 0
0x18001c83b  mov     r9, [rdi+20h]; union _LARGE_INTEGER
0x18001c83f  lea     rax, [rbp+hProcess]
0x18001c843  mov     r8d, [rdi+50h]; unsigned int
0x18001c847  mov     ecx, 1010h; unsigned int
0x18001c84c  mov     [rsp+58h+lpNumberOfBytesRead], rax; void **
0x18001c851  call    ?WdcSafeOpenProcess@@YAJKHKT_LARGE_INTEGER@@PEAPEAX@Z; WdcSafeOpenProcess(ulong,int,ulong,_LARGE_INTEGER,void * *)
0x18001c856  mov     rsi, [rbp+hProcess]
0x18001c85a  mov     ebx, eax
0x18001c85c  test    eax, eax
0x18001c85e  js      short loc_18001C804
0x18001c860  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x18001c864  mov     rcx, rsi; hProcess
0x18001c867  call    cs:__imp_IsWow64Process
0x18001c86d  test    eax, eax
0x18001c86f  jz      short loc_18001C804
0x18001c871  xor     r13d, r13d
0x18001c874  lea     r14, [rdi+100h]
0x18001c87b  cmp     [rdi+4], r13d
0x18001c87f  jbe     short loc_18001C804
0x18001c881  mov     r15, [rbp+arg_0]
0x18001c885  mov     rdx, [r14+68h]
0x18001c889  test    rdx, rdx
0x18001c88c  jz      loc_18001C959
0x18001c892  cmp     [rbp+Wow64Process], 0
0x18001c896  mov     rcx, rsi; hProcess
0x18001c899  mov     eax, [r14+30h]
0x18001c89d  mov     [rbp+var_28], eax
0x18001c8a0  mov     [rsp+58h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18001c8a9  jz      short loc_18001C8EB
0x18001c8ab  add     rdx, 2F60h; lpBaseAddress
0x18001c8b2  lea     r8, [rbp+Buffer]; lpBuffer
0x18001c8b6  mov     r9d, 4; nSize
0x18001c8bc  call    cs:__imp_ReadProcessMemory
0x18001c8c2  test    eax, eax
0x18001c8c4  jz      short loc_18001C8CA
0x18001c8c6  xor     ebx, ebx
0x18001c8c8  jmp     short loc_18001C8E5
0x18001c8ca  call    cs:__imp_GetLastError
0x18001c8d0  mov     ebx, eax
0x18001c8d2  test    eax, eax
0x18001c8d4  jz      short loc_18001C954
0x18001c8d6  jle     short loc_18001C8E1
0x18001c8d8  movzx   ebx, ax
0x18001c8db  or      ebx, 80070000h
0x18001c8e1  test    ebx, ebx
0x18001c8e3  js      short loc_18001C959
0x18001c8e5  mov     r8d, [rbp+Buffer]
0x18001c8e9  jmp     short loc_18001C92D
0x18001c8eb  add     rdx, 1720h; lpBaseAddress
0x18001c8f2  lea     r8, [rbp+var_18]; lpBuffer
0x18001c8f6  mov     r9d, 8; nSize
0x18001c8fc  call    cs:__imp_ReadProcessMemory
0x18001c902  test    eax, eax
0x18001c904  jz      short loc_18001C90A
0x18001c906  xor     ebx, ebx
0x18001c908  jmp     short loc_18001C925
0x18001c90a  call    cs:__imp_GetLastError
0x18001c910  mov     ebx, eax
0x18001c912  test    eax, eax
0x18001c914  jz      short loc_18001C954
0x18001c916  jle     short loc_18001C921
0x18001c918  movzx   ebx, ax
0x18001c91b  or      ebx, 80070000h
0x18001c921  test    ebx, ebx
0x18001c923  js      short loc_18001C959
0x18001c925  mov     r8d, [rbp+var_18]; unsigned int
0x18001c929  mov     [rbp+Buffer], r8d
0x18001c92d  test    r8d, r8d
0x18001c930  jz      short loc_18001C959
0x18001c932  mov     rax, [r14+8]
0x18001c936  xor     r9d, r9d; unsigned int
0x18001c939  add     rax, [r14]
0x18001c93c  mov     edx, [rbp+var_28]; unsigned int
0x18001c93f  mov     rcx, [r15+2480h]; this
0x18001c946  mov     [rsp+58h+lpNumberOfBytesRead], rax; __int64
0x18001c94b  call    ?CheckIn@WdcThreadStat@@QEAAJKKK_J@Z; WdcThreadStat::CheckIn(ulong,ulong,ulong,__int64)
0x18001c950  xor     ebx, ebx
0x18001c952  jmp     short loc_18001C959
0x18001c954  mov     ebx, 80004005h
0x18001c959  inc     r13d
0x18001c95c  add     r14, 88h
0x18001c963  cmp     r13d, [rdi+4]
0x18001c967  jb      loc_18001C885
0x18001c96d  mov     r15, [rbp+var_10]
0x18001c971  jmp     loc_18001C804
0x18001c976  xor     ebx, ebx
0x18001c978  lea     rax, [rsi-1]
0x18001c97c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c980  ja      short loc_18001C98B
0x18001c982  mov     rcx, rsi; hObject
0x18001c985  call    cs:__imp_CloseHandle
0x18001c98b  test    r15, r15
0x18001c98e  jz      short loc_18001C998
0x18001c990  mov     rcx, r15; void *
0x18001c993  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18001c998  mov     eax, ebx
0x18001c99a  add     rsp, 58h
0x18001c99e  pop     r15
0x18001c9a0  pop     r14
0x18001c9a2  pop     r13
0x18001c9a4  pop     r12
0x18001c9a6  pop     rdi
0x18001c9a7  pop     rsi
0x18001c9a8  pop     rbx
0x18001c9a9  pop     rbp
0x18001c9aa  retn
```
