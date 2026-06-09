# Common::GetProcessWorkingDirectoryByPID(ulong,bool,ushort *,ulong *)

- ea: `0x18039aeac`
- end: `0x18039b0e3`
- name: `?GetProcessWorkingDirectoryByPID@Common@@YAJK_NPEAGPEAK@Z`
- size: `567`
- prototype: `__int64 __fastcall(DWORD dwProcessId, unsigned int, bool, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1802d7a10`
- `0x180300e04`

## callees

- `0x1800cae14`
- `0x180356360`
- `0x180356edc`
- `0x18039aeac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039af4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039aff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039b039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039b08b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039af4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039aff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039b039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039b08b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039b0b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039b0b3`
- `ntdll!NtQueryInformationProcess` at `0x18039afb7`
- `ntdll!NtQueryInformationProcess` at `0x18039afb7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18039af3d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18039af3d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18039afed`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18039b02f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18039b081`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18039afed`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18039b02f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18039b081`

## pseudocode

```c
__int64 __fastcall Common::GetProcessWorkingDirectoryByPID(
        DWORD dwProcessId,
        char a2,
        unsigned int *a3,
        unsigned __int16 *a4)
{
  HANDLE v8; // rdi
  signed int LastError; // eax
  int v10; // ebx
  NTSTATUS InformationProcess; // ebx
  signed int v13; // eax
  signed int v14; // eax
  SIZE_T v15; // r9
  signed int v16; // eax
  unsigned int *v17; // [rsp+28h] [rbp-D8h]
  _OWORD ProcessInformation[3]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[56]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v20; // [rsp+98h] [rbp-68h]
  LPCVOID v21; // [rsp+A0h] [rbp-60h]
  _BYTE Buffer[32]; // [rsp+4B0h] [rbp+3B0h] BYREF
  LPCVOID lpBaseAddress; // [rsp+4D0h] [rbp+3D0h]

  memset_0(Buffer, 0, 0x7D0u);
  memset_0(v19, 0, 0x450u);
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  if ( a3 && a4 )
  {
    *(_WORD *)a3 = 0;
    v8 = OpenProcess(0x1010u, 0, dwProcessId);
    if ( v8 )
      goto LABEL_10;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError == 5 )
    {
      if ( a2 )
        return Common::GetProcessImageInfoByPID(dwProcessId, 0, 0, a3, a4, v17);
    }
    else if ( LastError <= 0 )
    {
      goto LABEL_9;
    }
    v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_9:
    if ( v10 < 0 )
      return (unsigned int)v10;
LABEL_10:
    InformationProcess = NtQueryInformationProcess(v8, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
    if ( InformationProcess < 0 )
    {
      v10 = InformationProcess | 0x10000000;
      if ( v10 < 0 )
        goto LABEL_30;
    }
    if ( !ReadProcessMemory(v8, *((LPCVOID *)&ProcessInformation[0] + 1), Buffer, 0x7D0u, 0) )
    {
      v13 = GetLastError();
      v10 = v13;
      if ( v13 > 0 )
        v10 = (unsigned __int16)v13 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_30;
    }
    if ( ReadProcessMemory(v8, lpBaseAddress, v19, 0x450u, 0) )
    {
      v10 = 0;
    }
    else
    {
      v14 = GetLastError();
      v10 = v14;
      if ( v14 > 0 )
        v10 = (unsigned __int16)v14 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_30;
    }
    if ( v21 )
    {
      v15 = 2LL * *(unsigned int *)a4;
      if ( v20 < v15 )
      {
        if ( ReadProcessMemory(v8, v21, a3, v15, 0) )
        {
          v10 = 0;
        }
        else
        {
          v16 = GetLastError();
          v10 = v16;
          if ( v16 > 0 )
            v10 = (unsigned __int16)v16 | 0x80070000;
        }
      }
      else
      {
        v10 = -2147024774;
      }
      *(_DWORD *)a4 = (v20 >> 1) + 1;
    }
LABEL_30:
    if ( v8 )
      CloseHandle(v8);
    return (unsigned int)v10;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18039aeac  push    rbp
0x18039aeae  push    rbx
0x18039aeaf  push    rsi
0x18039aeb0  push    rdi
0x18039aeb1  push    r12
0x18039aeb3  push    r14
0x18039aeb5  push    r15
0x18039aeb7  lea     rbp, [rsp-0B90h]
0x18039aebf  sub     rsp, 0C90h
0x18039aec6  mov     rax, cs:__security_cookie
0x18039aecd  xor     rax, rsp
0x18039aed0  mov     [rbp+0BC0h+var_40], rax
0x18039aed7  mov     r15, r8
0x18039aeda  mov     r12b, dl
0x18039aedd  mov     r14d, ecx
0x18039aee0  xor     edx, edx; Val
0x18039aee2  mov     r8d, 7D0h; Size
0x18039aee8  lea     rcx, [rbp+0BC0h+Buffer]; void *
0x18039aeef  mov     rsi, r9
0x18039aef2  call    memset_0
0x18039aef7  xor     edx, edx; Val
0x18039aef9  lea     rcx, [rsp+0CC0h+var_C60]; void *
0x18039aefe  mov     r8d, 450h; Size
0x18039af04  call    memset_0
0x18039af09  xorps   xmm0, xmm0
0x18039af0c  movups  [rsp+0CC0h+ProcessInformation], xmm0
0x18039af11  movups  [rsp+0CC0h+var_C80], xmm0
0x18039af16  movups  [rsp+0CC0h+var_C70], xmm0
0x18039af1b  test    r15, r15
0x18039af1e  jz      loc_18039B0BD
0x18039af24  test    rsi, rsi
0x18039af27  jz      loc_18039B0BD
0x18039af2d  xor     eax, eax
0x18039af2f  mov     r8d, r14d; dwProcessId
0x18039af32  xor     edx, edx; bInheritHandle
0x18039af34  mov     [r15], ax
0x18039af38  mov     ecx, 1010h; dwDesiredAccess
0x18039af3d  call    cs:__imp_OpenProcess
0x18039af43  mov     rdi, rax
0x18039af46  test    rax, rax
0x18039af49  jnz     short loc_18039AF98
0x18039af4b  call    cs:__imp_GetLastError
0x18039af51  mov     ebx, eax
0x18039af53  cmp     eax, 5
0x18039af56  jnz     short loc_18039AF77
0x18039af58  test    r12b, r12b
0x18039af5b  jz      short loc_18039AF83
0x18039af5d  mov     r9, r15; unsigned int *
0x18039af60  mov     [rsp+0CC0h+ReturnLength], rsi; unsigned __int16 *
0x18039af65  xor     r8d, r8d; unsigned __int16 *
0x18039af68  xor     edx, edx; pszDest
0x18039af6a  mov     ecx, r14d; dwProcessId
0x18039af6d  call    ?GetProcessImageInfoByPID@Common@@YAJKPEAGPEAK01@Z; Common::GetProcessImageInfoByPID(ulong,ushort *,ulong *,ushort *,ulong *)
0x18039af72  jmp     loc_18039B0C2
0x18039af77  test    eax, eax
0x18039af79  jg      short loc_18039AF83
0x18039af7b  mov     r14d, 80070000h
0x18039af81  jmp     short loc_18039AF8F
0x18039af83  movzx   ebx, ax
0x18039af86  mov     r14d, 80070000h
0x18039af8c  or      ebx, r14d
0x18039af8f  test    ebx, ebx
0x18039af91  jns     short loc_18039AF9E
0x18039af93  jmp     loc_18039B0B9
0x18039af98  mov     r14d, 80070000h
0x18039af9e  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18039afa4  mov     [rsp+0CC0h+ReturnLength], 0; ReturnLength
0x18039afad  lea     r8, [rsp+0CC0h+ProcessInformation]; ProcessInformation
0x18039afb2  xor     edx, edx; ProcessInformationClass
0x18039afb4  mov     rcx, rdi; ProcessHandle
0x18039afb7  call    cs:__imp_NtQueryInformationProcess
0x18039afbd  mov     ebx, eax
0x18039afbf  test    eax, eax
0x18039afc1  jns     short loc_18039AFCF
0x18039afc3  or      ebx, 10000000h
0x18039afc9  jl      loc_18039B0AB
0x18039afcf  mov     rdx, qword ptr [rsp+0CC0h+ProcessInformation+8]; lpBaseAddress
0x18039afd4  lea     r8, [rbp+0BC0h+Buffer]; lpBuffer
0x18039afdb  mov     r9d, 7D0h; nSize
0x18039afe1  mov     [rsp+0CC0h+ReturnLength], 0; lpNumberOfBytesRead
0x18039afea  mov     rcx, rdi; hProcess
0x18039afed  call    cs:__imp_ReadProcessMemory
0x18039aff3  test    eax, eax
0x18039aff5  jnz     short loc_18039B011
0x18039aff7  call    cs:__imp_GetLastError
0x18039affd  mov     ebx, eax
0x18039afff  test    eax, eax
0x18039b001  jle     short loc_18039B009
0x18039b003  movzx   ebx, ax
0x18039b006  or      ebx, r14d
0x18039b009  test    ebx, ebx
0x18039b00b  js      loc_18039B0AB
0x18039b011  mov     rdx, [rbp+0BC0h+lpBaseAddress]; lpBaseAddress
0x18039b018  lea     r8, [rsp+0CC0h+var_C60]; lpBuffer
0x18039b01d  mov     r9d, 450h; nSize
0x18039b023  mov     [rsp+0CC0h+ReturnLength], 0; lpNumberOfBytesRead
0x18039b02c  mov     rcx, rdi; hProcess
0x18039b02f  call    cs:__imp_ReadProcessMemory
0x18039b035  test    eax, eax
0x18039b037  jnz     short loc_18039B051
0x18039b039  call    cs:__imp_GetLastError
0x18039b03f  mov     ebx, eax
0x18039b041  test    eax, eax
0x18039b043  jle     short loc_18039B04B
0x18039b045  movzx   ebx, ax
0x18039b048  or      ebx, r14d
0x18039b04b  test    ebx, ebx
0x18039b04d  js      short loc_18039B0AB
0x18039b04f  jmp     short loc_18039B053
0x18039b051  xor     ebx, ebx
0x18039b053  mov     rdx, [rbp+0BC0h+var_C20]; lpBaseAddress
0x18039b057  test    rdx, rdx
0x18039b05a  jz      short loc_18039B0AB
0x18039b05c  mov     r9d, [rsi]
0x18039b05f  movzx   eax, [rbp+0BC0h+var_C28]
0x18039b063  add     r9, r9; nSize
0x18039b066  cmp     rax, r9
0x18039b069  jb      short loc_18039B072
0x18039b06b  mov     ebx, 8007007Ah
0x18039b070  jmp     short loc_18039B0A1
0x18039b072  mov     r8, r15; lpBuffer
0x18039b075  mov     [rsp+0CC0h+ReturnLength], 0; lpNumberOfBytesRead
0x18039b07e  mov     rcx, rdi; hProcess
0x18039b081  call    cs:__imp_ReadProcessMemory
0x18039b087  test    eax, eax
0x18039b089  jnz     short loc_18039B09F
0x18039b08b  call    cs:__imp_GetLastError
0x18039b091  mov     ebx, eax
0x18039b093  test    eax, eax
0x18039b095  jle     short loc_18039B0A1
0x18039b097  movzx   ebx, ax
0x18039b09a  or      ebx, r14d
0x18039b09d  jmp     short loc_18039B0A1
0x18039b09f  xor     ebx, ebx
0x18039b0a1  movzx   ecx, [rbp+0BC0h+var_C28]
0x18039b0a5  shr     ecx, 1
0x18039b0a7  inc     ecx
0x18039b0a9  mov     [rsi], ecx
0x18039b0ab  test    rdi, rdi
0x18039b0ae  jz      short loc_18039B0B9
0x18039b0b0  mov     rcx, rdi; hObject
0x18039b0b3  call    cs:__imp_CloseHandle
0x18039b0b9  mov     eax, ebx
0x18039b0bb  jmp     short loc_18039B0C2
0x18039b0bd  mov     eax, 80004003h
0x18039b0c2  mov     rcx, [rbp+0BC0h+var_40]
0x18039b0c9  xor     rcx, rsp; StackCookie
0x18039b0cc  call    __security_check_cookie
0x18039b0d1  add     rsp, 0C90h
0x18039b0d8  pop     r15
0x18039b0da  pop     r14
0x18039b0dc  pop     r12
0x18039b0de  pop     rdi
0x18039b0df  pop     rsi
0x18039b0e0  pop     rbx
0x18039b0e1  pop     rbp
0x18039b0e2  retn
```
