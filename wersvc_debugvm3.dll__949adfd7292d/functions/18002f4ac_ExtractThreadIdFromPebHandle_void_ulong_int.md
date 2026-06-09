# ExtractThreadIdFromPebHandle(void *,ulong *,int)

- ea: `0x18002f4ac`
- end: `0x18002f981`
- name: `?ExtractThreadIdFromPebHandle@@YAJPEAXPEAKH@Z`
- size: `1237`
- prototype: `__int64 __fastcall(HANDLE hProcess, unsigned int *lpBuffer, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f3f4`

## callees

- `0x180011ef8`
- `0x180013df4`
- `0x18001e3c4`
- `0x18002f4ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f5e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f5e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f65c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f7e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f65c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f72a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f7e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8f7`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002f5f2`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002f652`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002f5f2`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002f652`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002f71d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002f7de`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002f8ed`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002f71d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002f7de`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002f8ed`
- `ntdll!NtQueryInformationProcess` at `0x18002f501`
- `ntdll!NtQueryInformationProcess` at `0x18002f56a`
- `ntdll!NtQueryInformationProcess` at `0x18002f501`
- `ntdll!NtQueryInformationProcess` at `0x18002f56a`

## pseudocode

```c
__int64 __fastcall ExtractThreadIdFromPebHandle(HANDLE hProcess, unsigned int *lpBuffer, int a3)
{
  NTSTATUS v5; // ebx
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rax
  NTSTATUS InformationProcess; // ebx
  SIZE_T v12; // rbx
  __int64 v13; // r13
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  bool v16; // sf
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  signed int v20; // eax
  bool v21; // sf
  HANDLE *v22; // r10
  __int64 v23; // rdx
  signed int v24; // eax
  signed int v25; // eax
  char *v26; // rdx
  signed int v27; // eax
  unsigned __int16 v29; // [rsp+30h] [rbp-39h] BYREF
  __int64 ProcessInformation; // [rsp+38h] [rbp-31h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+40h] [rbp-29h] BYREF
  char *Buffer; // [rsp+48h] [rbp-21h] BYREF
  __int64 v33; // [rsp+50h] [rbp-19h] BYREF
  _OWORD v34[6]; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 v35; // [rsp+D8h] [rbp+6Fh] BYREF
  int v36; // [rsp+E0h] [rbp+77h]
  unsigned __int16 v37; // [rsp+E8h] [rbp+7Fh] BYREF

  v36 = a3;
  *lpBuffer = 0;
  NumberOfBytesRead = 0;
  ProcessInformation = 0;
  Buffer = 0;
  v33 = 0;
  memset(v34, 0, 48);
  v5 = NtQueryInformationProcess(hProcess, ProcessWow64Information, &ProcessInformation, 8u, 0);
  if ( v5 < 0 )
  {
    v6 = v5 | 0x10000000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 11;
LABEL_5:
      v9 = v6;
LABEL_6:
      WPP_SF_d(v7[2], v8, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids, v9);
      return v6;
    }
    return v6;
  }
  v10 = ProcessInformation;
  if ( ProcessInformation )
  {
    v12 = 4;
    v13 = 20;
LABEL_14:
    if ( !v10 )
    {
      v37 = 0;
      v35 = 0;
      v29 = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !(unsigned int)IsWow64Process2(CurrentProcess, &v37, &v29) )
      {
        LastError = GetLastError();
        v16 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v16 = LastError < 0;
        }
        if ( !v16 )
          LastError = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids,
            (unsigned int)LastError);
        v37 = 0;
        v29 = 0;
      }
      if ( (unsigned int)IsWow64Process2(hProcess, &v35, 0) )
      {
        v23 = v35;
        v22 = (HANDLE *)WPP_GLOBAL_Control;
      }
      else
      {
        v20 = GetLastError();
        v21 = v20 < 0;
        if ( v20 > 0 )
        {
          v20 = (unsigned __int16)v20 | 0x80070000;
          v21 = v20 < 0;
        }
        v17 = 2147500037LL;
        if ( !v21 )
          v20 = -2147467259;
        v22 = (HANDLE *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids,
            (unsigned int)v20);
          v22 = (HANDLE *)WPP_GLOBAL_Control;
        }
        v23 = 0;
        v35 = 0;
      }
      if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 4) != 0 )
      {
        WPP_SF_DDD(v22[2], 15, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids, (unsigned __int16)v23, v37, v29);
        v23 = v35;
      }
      v10 = ProcessInformation;
      if ( v37 != (_WORD)v23 && !ProcessInformation )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v17, v23, v18, v19);
        v10 = ProcessInformation;
      }
    }
    if ( ReadProcessMemory(hProcess, (LPCVOID)(v10 + v13), &Buffer, v12, &NumberOfBytesRead) )
    {
      if ( NumberOfBytesRead != v12 )
      {
        v9 = 2147942699LL;
        v6 = -2147024597;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 17;
          goto LABEL_6;
        }
        return v6;
      }
      if ( Buffer )
      {
        if ( ReadProcessMemory(hProcess, Buffer, &v33, 8u, &NumberOfBytesRead) )
        {
          if ( NumberOfBytesRead != 8 )
          {
            v9 = 2147942699LL;
            v6 = -2147024597;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 20;
              goto LABEL_6;
            }
            return v6;
          }
          if ( (unsigned int)v33 < 0x498 )
          {
            v9 = 2147943705LL;
            v6 = -2147023591;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 21;
              goto LABEL_6;
            }
            return v6;
          }
          if ( HIDWORD(v33) != 1464157250 )
          {
            v9 = 2147943705LL;
            v6 = -2147023591;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v8 = 22;
              goto LABEL_6;
            }
            return v6;
          }
          if ( v36 )
            v26 = Buffer + 1172;
          else
            v26 = Buffer + 8;
          if ( ReadProcessMemory(hProcess, v26, lpBuffer, 4u, &NumberOfBytesRead) )
          {
            if ( NumberOfBytesRead == 4 )
            {
              if ( !*lpBuffer || (*(_BYTE *)lpBuffer & 3) != 0 )
              {
                *lpBuffer = 0;
                return (unsigned int)-2147023452;
              }
              else
              {
                return 0;
              }
            }
            else
            {
              v9 = 2147942699LL;
              v6 = -2147024597;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v8 = 24;
                goto LABEL_6;
              }
            }
            return v6;
          }
          v27 = GetLastError();
          v6 = v27;
          if ( v27 > 0 )
            v6 = (unsigned __int16)v27 | 0x80070000;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v6;
          v8 = 23;
        }
        else
        {
          v25 = GetLastError();
          v6 = v25;
          if ( v25 > 0 )
            v6 = (unsigned __int16)v25 | 0x80070000;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v6;
          v8 = 19;
        }
      }
      else
      {
        v6 = -2147023728;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return v6;
        v8 = 18;
      }
    }
    else
    {
      v24 = GetLastError();
      v6 = v24;
      if ( v24 > 0 )
        v6 = (unsigned __int16)v24 | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v6;
      v8 = 16;
    }
    v9 = v6;
    goto LABEL_6;
  }
  InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, v34, 0x30u, 0);
  if ( InformationProcess >= 0 )
  {
    v10 = *((_QWORD *)&v34[0] + 1);
    v12 = 8;
    ProcessInformation = *((_QWORD *)&v34[0] + 1);
    v13 = 40;
    goto LABEL_14;
  }
  v6 = InformationProcess | 0x10000000;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 12;
    goto LABEL_5;
  }
  return v6;
}

```

## disassembly

```asm
0x18002f4ac  mov     [rsp-8+arg_10], r8d
0x18002f4b1  push    rbp
0x18002f4b2  push    rbx
0x18002f4b3  push    rdi
0x18002f4b4  push    r12
0x18002f4b6  push    r13
0x18002f4b8  push    r14
0x18002f4ba  push    r15
0x18002f4bc  lea     rbp, [rsp-27h]
0x18002f4c1  sub     rsp, 90h
0x18002f4c8  xor     edi, edi
0x18002f4ca  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x18002f4ce  xorps   xmm0, xmm0
0x18002f4d1  mov     [rdx], edi
0x18002f4d3  mov     r15, rdx
0x18002f4d6  mov     [rbp+57h+NumberOfBytesRead], rdi
0x18002f4da  mov     r12, rcx
0x18002f4dd  mov     [rbp+57h+ProcessInformation], rdi
0x18002f4e1  lea     r9d, [rdi+8]; ProcessInformationLength
0x18002f4e5  mov     [rbp+57h+Buffer], rdi
0x18002f4e9  lea     edx, [rdi+1Ah]; ProcessInformationClass
0x18002f4ec  mov     [rbp+57h+var_70], rdi
0x18002f4f0  movups  [rbp+57h+var_68], xmm0
0x18002f4f4  mov     [rsp+0C0h+ReturnLength], rdi; ReturnLength
0x18002f4f9  movups  [rbp+57h+var_58], xmm0
0x18002f4fd  movups  [rbp+57h+var_48], xmm0
0x18002f501  call    cs:__imp_NtQueryInformationProcess
0x18002f507  mov     ebx, eax
0x18002f509  test    eax, eax
0x18002f50b  jns     short loc_18002F54F
0x18002f50d  bts     ebx, 1Ch
0x18002f511  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f518  lea     rdi, WPP_GLOBAL_Control
0x18002f51f  cmp     rcx, rdi
0x18002f522  jz      loc_18002F96C
0x18002f528  test    byte ptr [rcx+1Ch], 1
0x18002f52c  jz      loc_18002F96C
0x18002f532  mov     edx, 0Bh
0x18002f537  mov     r9d, ebx
0x18002f53a  lea     r8, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids
0x18002f541  mov     rcx, [rcx+10h]
0x18002f545  call    WPP_SF_d
0x18002f54a  jmp     loc_18002F96C
0x18002f54f  mov     rax, [rbp+57h+ProcessInformation]
0x18002f553  test    rax, rax
0x18002f556  jnz     short loc_18002F5B5
0x18002f558  lea     r9d, [rax+30h]; ProcessInformationLength
0x18002f55c  mov     [rsp+0C0h+ReturnLength], rdi; ReturnLength
0x18002f561  lea     r8, [rbp+57h+var_68]; ProcessInformation
0x18002f565  xor     edx, edx; ProcessInformationClass
0x18002f567  mov     rcx, r12; ProcessHandle
0x18002f56a  call    cs:__imp_NtQueryInformationProcess
0x18002f570  mov     ebx, eax
0x18002f572  test    eax, eax
0x18002f574  jns     short loc_18002F5A2
0x18002f576  bts     ebx, 1Ch
0x18002f57a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f581  lea     rdi, WPP_GLOBAL_Control
0x18002f588  cmp     rcx, rdi
0x18002f58b  jz      loc_18002F96C
0x18002f591  test    byte ptr [rcx+1Ch], 1
0x18002f595  jz      loc_18002F96C
0x18002f59b  mov     edx, 0Ch
0x18002f5a0  jmp     short loc_18002F537
0x18002f5a2  mov     rax, qword ptr [rbp+57h+var_68+8]
0x18002f5a6  mov     ebx, 8
0x18002f5ab  mov     [rbp+57h+ProcessInformation], rax
0x18002f5af  lea     r13d, [rbx+20h]
0x18002f5b3  jmp     short loc_18002F5BE
0x18002f5b5  mov     ebx, 4
0x18002f5ba  lea     r13d, [rbx+10h]
0x18002f5be  lea     rdi, WPP_GLOBAL_Control
0x18002f5c5  lea     r14, WPP_4b3d6779bd5133ece3b4f77e9ebe8779_Traceguids
0x18002f5cc  test    rax, rax
0x18002f5cf  jnz     loc_18002F706
0x18002f5d5  mov     [rbp+57h+arg_18], ax
0x18002f5d9  mov     [rbp+57h+arg_8], ax
0x18002f5dd  mov     [rbp+57h+var_90], ax
0x18002f5e1  call    cs:__imp_GetCurrentProcess
0x18002f5e7  mov     rcx, rax
0x18002f5ea  lea     r8, [rbp+57h+var_90]
0x18002f5ee  lea     rdx, [rbp+57h+arg_18]
0x18002f5f2  call    cs:__imp_IsWow64Process2
0x18002f5f8  test    eax, eax
0x18002f5fa  jnz     short loc_18002F648
0x18002f5fc  call    cs:__imp_GetLastError
0x18002f602  test    eax, eax
0x18002f604  jle     short loc_18002F610
0x18002f606  movzx   eax, ax
0x18002f609  or      eax, 80070000h
0x18002f60e  test    eax, eax
0x18002f610  mov     ecx, 80004005h
0x18002f615  cmovns  eax, ecx
0x18002f618  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f61f  cmp     rcx, rdi
0x18002f622  jz      short loc_18002F63E
0x18002f624  test    byte ptr [rcx+1Ch], 1
0x18002f628  jz      short loc_18002F63E
0x18002f62a  mov     rcx, [rcx+10h]
0x18002f62e  mov     edx, 0Dh
0x18002f633  mov     r9d, eax
0x18002f636  mov     r8, r14
0x18002f639  call    WPP_SF_d
0x18002f63e  xor     eax, eax
0x18002f640  mov     [rbp+57h+arg_18], ax
0x18002f644  mov     [rbp+57h+var_90], ax
0x18002f648  xor     r8d, r8d
0x18002f64b  lea     rdx, [rbp+57h+arg_8]
0x18002f64f  mov     rcx, r12
0x18002f652  call    cs:__imp_IsWow64Process2
0x18002f658  test    eax, eax
0x18002f65a  jnz     short loc_18002F6AE
0x18002f65c  call    cs:__imp_GetLastError
0x18002f662  test    eax, eax
0x18002f664  jle     short loc_18002F670
0x18002f666  movzx   eax, ax
0x18002f669  or      eax, 80070000h
0x18002f66e  test    eax, eax
0x18002f670  mov     ecx, 80004005h
0x18002f675  cmovns  eax, ecx
0x18002f678  mov     r10, cs:WPP_GLOBAL_Control
0x18002f67f  cmp     r10, rdi
0x18002f682  jz      short loc_18002F6A6
0x18002f684  test    byte ptr [r10+1Ch], 1
0x18002f689  jz      short loc_18002F6A6
0x18002f68b  mov     rcx, [r10+10h]
0x18002f68f  mov     edx, 0Eh
0x18002f694  mov     r9d, eax
0x18002f697  mov     r8, r14
0x18002f69a  call    WPP_SF_d
0x18002f69f  mov     r10, cs:WPP_GLOBAL_Control
0x18002f6a6  xor     edx, edx
0x18002f6a8  mov     [rbp+57h+arg_8], dx
0x18002f6ac  jmp     short loc_18002F6B9
0x18002f6ae  movzx   edx, [rbp+57h+arg_8]
0x18002f6b2  mov     r10, cs:WPP_GLOBAL_Control
0x18002f6b9  cmp     r10, rdi
0x18002f6bc  jz      short loc_18002F6EE
0x18002f6be  test    byte ptr [r10+1Ch], 4
0x18002f6c3  jz      short loc_18002F6EE
0x18002f6c5  movzx   ecx, [rbp+57h+arg_18]
0x18002f6c9  mov     r8, r14
0x18002f6cc  movzx   eax, [rbp+57h+var_90]
0x18002f6d0  mov     [rsp+0C0h+var_98], eax
0x18002f6d4  mov     dword ptr [rsp+0C0h+ReturnLength], ecx
0x18002f6d8  mov     rcx, [r10+10h]
0x18002f6dc  movzx   r9d, dx
0x18002f6e0  mov     edx, 0Fh
0x18002f6e5  call    WPP_SF_DDD
0x18002f6ea  movzx   edx, [rbp+57h+arg_8]
0x18002f6ee  mov     rax, [rbp+57h+ProcessInformation]
0x18002f6f2  cmp     [rbp+57h+arg_18], dx
0x18002f6f6  jz      short loc_18002F706
0x18002f6f8  test    rax, rax
0x18002f6fb  jnz     short loc_18002F706
0x18002f6fd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002f702  mov     rax, [rbp+57h+ProcessInformation]
0x18002f706  lea     rdx, [rax+r13]; lpBaseAddress
0x18002f70a  mov     r9, rbx; nSize
0x18002f70d  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18002f711  mov     rcx, r12; hProcess
0x18002f714  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18002f718  mov     [rsp+0C0h+ReturnLength], rax; lpNumberOfBytesRead
0x18002f71d  call    cs:__imp_ReadProcessMemory
0x18002f723  xor     r13d, r13d
0x18002f726  test    eax, eax
0x18002f728  jnz     short loc_18002F769
0x18002f72a  call    cs:__imp_GetLastError
0x18002f730  mov     ebx, eax
0x18002f732  test    eax, eax
0x18002f734  jle     short loc_18002F73F
0x18002f736  movzx   ebx, ax
0x18002f739  or      ebx, 80070000h
0x18002f73f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f746  cmp     rcx, rdi
0x18002f749  jz      loc_18002F96C
0x18002f74f  test    byte ptr [rcx+1Ch], 1
0x18002f753  jz      loc_18002F96C
0x18002f759  mov     edx, 10h
0x18002f75e  mov     r9d, ebx
0x18002f761  mov     r8, r14
0x18002f764  jmp     loc_18002F541
0x18002f769  cmp     [rbp+57h+NumberOfBytesRead], rbx
0x18002f76d  jz      short loc_18002F799
0x18002f76f  mov     r9d, 8007012Bh
0x18002f775  mov     ebx, r9d
0x18002f778  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f77f  cmp     rcx, rdi
0x18002f782  jz      loc_18002F96C
0x18002f788  test    byte ptr [rcx+1Ch], 1
0x18002f78c  jz      loc_18002F96C
0x18002f792  mov     edx, 11h
0x18002f797  jmp     short loc_18002F761
0x18002f799  mov     rdx, [rbp+57h+Buffer]; lpBaseAddress
0x18002f79d  test    rdx, rdx
0x18002f7a0  jnz     short loc_18002F7C8
0x18002f7a2  mov     ebx, 80070490h
0x18002f7a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7ae  cmp     rcx, rdi
0x18002f7b1  jz      loc_18002F96C
0x18002f7b7  test    byte ptr [rcx+1Ch], 2
0x18002f7bb  jz      loc_18002F96C
0x18002f7c1  mov     edx, 12h
0x18002f7c6  jmp     short loc_18002F75E
0x18002f7c8  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18002f7cc  mov     r9d, 8; nSize
0x18002f7d2  lea     r8, [rbp+57h+var_70]; lpBuffer
0x18002f7d6  mov     [rsp+0C0h+ReturnLength], rax; lpNumberOfBytesRead
0x18002f7db  mov     rcx, r12; hProcess
0x18002f7de  call    cs:__imp_ReadProcessMemory
0x18002f7e4  test    eax, eax
0x18002f7e6  jnz     short loc_18002F821
0x18002f7e8  call    cs:__imp_GetLastError
0x18002f7ee  mov     ebx, eax
0x18002f7f0  test    eax, eax
0x18002f7f2  jle     short loc_18002F7FD
0x18002f7f4  movzx   ebx, ax
0x18002f7f7  or      ebx, 80070000h
0x18002f7fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f804  cmp     rcx, rdi
0x18002f807  jz      loc_18002F96C
0x18002f80d  test    byte ptr [rcx+1Ch], 1
0x18002f811  jz      loc_18002F96C
0x18002f817  mov     edx, 13h
0x18002f81c  jmp     loc_18002F75E
0x18002f821  cmp     [rbp+57h+NumberOfBytesRead], 8
0x18002f826  jz      short loc_18002F855
0x18002f828  mov     r9d, 8007012Bh
0x18002f82e  mov     ebx, r9d
0x18002f831  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f838  cmp     rcx, rdi
0x18002f83b  jz      loc_18002F96C
0x18002f841  test    byte ptr [rcx+1Ch], 1
0x18002f845  jz      loc_18002F96C
0x18002f84b  mov     edx, 14h
0x18002f850  jmp     loc_18002F761
0x18002f855  cmp     dword ptr [rbp+57h+var_70], 498h
0x18002f85c  jnb     short loc_18002F88B
0x18002f85e  mov     r9d, 80070519h
0x18002f864  mov     ebx, r9d
0x18002f867  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f86e  cmp     rcx, rdi
0x18002f871  jz      loc_18002F96C
0x18002f877  test    byte ptr [rcx+1Ch], 1
0x18002f87b  jz      loc_18002F96C
0x18002f881  mov     edx, 15h
0x18002f886  jmp     loc_18002F761
0x18002f88b  cmp     dword ptr [rbp+57h+var_70+4], 57454442h
0x18002f892  jz      short loc_18002F8C1
0x18002f894  mov     r9d, 80070519h
0x18002f89a  mov     ebx, r9d
0x18002f89d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8a4  cmp     rcx, rdi
0x18002f8a7  jz      loc_18002F96C
0x18002f8ad  test    byte ptr [rcx+1Ch], 1
0x18002f8b1  jz      loc_18002F96C
0x18002f8b7  mov     edx, 16h
0x18002f8bc  jmp     loc_18002F761
0x18002f8c1  mov     rdx, [rbp+57h+Buffer]
0x18002f8c5  cmp     [rbp+57h+arg_10], r13d
0x18002f8c9  jz      short loc_18002F8D4
0x18002f8cb  add     rdx, 494h
0x18002f8d2  jmp     short loc_18002F8D8
0x18002f8d4  add     rdx, 8; lpBaseAddress
0x18002f8d8  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18002f8dc  mov     r9d, 4; nSize
0x18002f8e2  mov     r8, r15; lpBuffer
0x18002f8e5  mov     [rsp+0C0h+ReturnLength], rax; lpNumberOfBytesRead
0x18002f8ea  mov     rcx, r12; hProcess
0x18002f8ed  call    cs:__imp_ReadProcessMemory
0x18002f8f3  test    eax, eax
0x18002f8f5  jnz     short loc_18002F928
0x18002f8f7  call    cs:__imp_GetLastError
0x18002f8fd  mov     ebx, eax
0x18002f8ff  test    eax, eax
0x18002f901  jle     short loc_18002F90C
0x18002f903  movzx   ebx, ax
0x18002f906  or      ebx, 80070000h
0x18002f90c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f913  cmp     rcx, rdi
0x18002f916  jz      short loc_18002F96C
0x18002f918  test    byte ptr [rcx+1Ch], 1
0x18002f91c  jz      short loc_18002F96C
0x18002f91e  mov     edx, 17h
0x18002f923  jmp     loc_18002F75E
0x18002f928  cmp     [rbp+57h+NumberOfBytesRead], 4
0x18002f92d  jz      short loc_18002F954
0x18002f92f  mov     r9d, 8007012Bh
0x18002f935  mov     ebx, r9d
0x18002f938  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f93f  cmp     rcx, rdi
0x18002f942  jz      short loc_18002F96C
0x18002f944  test    byte ptr [rcx+1Ch], 1
0x18002f948  jz      short loc_18002F96C
0x18002f94a  mov     edx, 18h
0x18002f94f  jmp     loc_18002F761
0x18002f954  cmp     [r15], r13d
0x18002f957  jz      short loc_18002F964
0x18002f959  test    byte ptr [r15], 3
0x18002f95d  jnz     short loc_18002F964
  ... truncated ...
```
