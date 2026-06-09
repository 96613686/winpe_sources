# BfspPrintFileOwnerProcess

- ea: `0x180031b50`
- end: `0x180031e70`
- name: `BfspPrintFileOwnerProcess`
- size: `800`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800318b0`
- `0x180032518`
- `0x180033eb0`
- `0x18003527c`
- `0x180036ca8`
- `0x180036dd4`

## callees

- `0x180031344`
- `0x180031b50`
- `0x1800366b8`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180031c61`
- `ntdll!NtQueryInformationFile` at `0x180031c61`
- `ntdll!NtClose` at `0x180031dde`
- `ntdll!NtClose` at `0x180031dde`
- `ntdll!NtOpenProcess` at `0x180031cf7`
- `ntdll!NtOpenProcess` at `0x180031cf7`
- `ntdll!NtQueryInformationProcess` at `0x180031d32`
- `ntdll!NtQueryInformationProcess` at `0x180031d9e`
- `ntdll!NtQueryInformationProcess` at `0x180031d32`
- `ntdll!NtQueryInformationProcess` at `0x180031d9e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031bf3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031bf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031c28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031d59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031c28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031d59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031e4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031c39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031d6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031c39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031d6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031dfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031dfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031e58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031e27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031e27`

## string_xrefs

- `0x180031bbb`: `BfspPrintFileOwnerProcess: Failed to acquire debugprivilege`
- `0x180031c0b`: `BfspPrintFileOwnerProcess: Failed to open file!Last Error = %#x`
- `0x180031d01`: `BfspPrintFileOwnerProcess: NtOpenProcess failed!Status = %#x`

## pseudocode

```c
int __fastcall BfspPrintFileOwnerProcess(LPCWSTR lpFileName)
{
  int result; // eax
  HANDLE FileW; // r14
  DWORD LastError; // eax
  HANDLE ProcessHeap; // rax
  _DWORD *v6; // rax
  _DWORD *v7; // rsi
  NTSTATUS v8; // eax
  const wchar_t *v9; // rdx
  _QWORD *v10; // rbx
  int v11; // r15d
  NTSTATUS v12; // eax
  const wchar_t *v13; // rdx
  ULONG v14; // ebx
  HANDLE v15; // rax
  const wchar_t *v16; // r8
  HANDLE v17; // rax
  HANDLE v18; // rax
  void *v19; // rbx
  HANDLE v20; // rax
  _CLIENT_ID ClientId; // [rsp+40h] [rbp-29h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  ULONG Length; // [rsp+D0h] [rbp+67h] BYREF
  void *ProcessHandle; // [rsp+D8h] [rbp+6Fh] BYREF
  LPVOID lpMem; // [rsp+E0h] [rbp+77h] BYREF

  result = 0;
  ProcessHandle = 0;
  Length = 0;
  lpMem = 0;
  ClientId = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !lpFileName || !LogEnabled )
    return result;
  if ( !(unsigned int)BfspAdjustDebugPrivilege(1, &lpMem) )
  {
    result = BfspLogMessage(4, L"BfspPrintFileOwnerProcess: Failed to acquire debugprivilege");
    goto LABEL_36;
  }
  FileW = CreateFileW(lpFileName, 0x100080u, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    result = BfspLogMessage(4, L"BfspPrintFileOwnerProcess: Failed to open file!Last Error = %#x", LastError);
    goto LABEL_36;
  }
  Length = 1024;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, 0x400u);
  v7 = v6;
  if ( v6 )
  {
    v8 = NtQueryInformationFile(FileW, &IoStatusBlock, v6, Length, FileProcessIdsUsingFileInformation);
    if ( v8 < 0 )
    {
      BfspLogMessage(4, L"BfspPrintFileOwnerProcess: NtQueryInformationFilefailed! Status = %#x", (unsigned int)v8);
LABEL_34:
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v7);
      goto LABEL_35;
    }
    v9 = L"Printing processes using %s file.";
    if ( !*v7 )
      v9 = L"No process found using %s file.";
    BfspLogMessage(4, v9, lpFileName);
    ProcessHandle = 0;
    v10 = 0;
    v11 = 0;
    if ( !*v7 )
      goto LABEL_34;
    while ( 1 )
    {
      ClientId.UniqueThread = 0;
      ClientId.UniqueProcess = *(HANDLE *)&v7[2 * v11 + 2];
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v12 = NtOpenProcess(&ProcessHandle, 0x1000u, &ObjectAttributes, &ClientId);
      if ( v12 < 0 )
        break;
      Length = 0;
      v12 = NtQueryInformationProcess(ProcessHandle, ProcessImageFileName, 0, 0, &Length);
      if ( v12 != -2147483643 && v12 != -1073741789 && v12 != -1073741820 )
      {
        v13 = L"BfspPrintFileOwnerProcess: NtQueryInformationProcessfailed in unexpected manner! Status = %#x";
        goto LABEL_15;
      }
      v14 = Length;
      v15 = GetProcessHeap();
      v10 = HeapAlloc(v15, 8u, v14);
      if ( v10 )
      {
        v12 = NtQueryInformationProcess(ProcessHandle, ProcessImageFileName, v10, Length, &Length);
        if ( v12 >= 0 )
        {
          if ( *(_WORD *)v10 )
            v16 = (const wchar_t *)v10[1];
          else
            v16 = L"System";
          BfspLogMessage(4, L"Process Name = %s", v16);
          goto LABEL_29;
        }
        v13 = L"BfspPrintFileOwnerProcess: NtQueryInformationProcessfailed! Status = %#x";
        goto LABEL_15;
      }
      BfspLogMessage(4, L"BfspPrintFileOwnerProcess: Malloc failed!Size = %#x", Length);
LABEL_29:
      if ( ProcessHandle )
      {
        NtClose(ProcessHandle);
        ProcessHandle = 0;
      }
      if ( v10 )
      {
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v10);
        v10 = 0;
      }
      if ( (unsigned int)++v11 >= *v7 )
        goto LABEL_34;
    }
    v13 = L"BfspPrintFileOwnerProcess: NtOpenProcess failed!Status = %#x";
LABEL_15:
    BfspLogMessage(4, v13, (unsigned int)v12);
    goto LABEL_29;
  }
LABEL_35:
  result = CloseHandle(FileW);
LABEL_36:
  v19 = lpMem;
  if ( lpMem )
  {
    if ( *(_DWORD *)lpMem != 1 || (*((_BYTE *)lpMem + 12) & 2) == 0 )
      BfspAdjustDebugPrivilege(0, 0);
    v20 = GetProcessHeap();
    return HeapFree(v20, 0, v19);
  }
  return result;
}

```

## disassembly

```asm
0x180031b50  push    rbp
0x180031b52  push    rbx
0x180031b53  push    rsi
0x180031b54  push    rdi
0x180031b55  push    r12
0x180031b57  push    r14
0x180031b59  push    r15
0x180031b5b  lea     rbp, [rsp-27h]
0x180031b60  sub     rsp, 90h
0x180031b67  xorps   xmm0, xmm0
0x180031b6a  xor     r12d, r12d
0x180031b6d  xor     eax, eax
0x180031b6f  mov     [rbp+57h+ProcessHandle], r12
0x180031b73  mov     [rbp+57h+Length], r12d
0x180031b77  xorps   xmm1, xmm1
0x180031b7a  mov     [rbp+57h+lpMem], r12
0x180031b7e  mov     rbx, rcx
0x180031b81  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180031b85  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180031b89  movups  xmmword ptr [rbp+57h+ClientId.UniqueProcess], xmm0
0x180031b8d  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x180031b91  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180031b95  test    rcx, rcx
0x180031b98  jz      loc_180031E5E
0x180031b9e  cmp     cs:LogEnabled, r12d
0x180031ba5  jz      loc_180031E5E
0x180031bab  lea     rdx, [rbp+57h+lpMem]
0x180031baf  lea     ecx, [rax+1]
0x180031bb2  call    BfspAdjustDebugPrivilege
0x180031bb7  test    eax, eax
0x180031bb9  jnz     short loc_180031BCF
0x180031bbb  lea     rdx, aBfspprintfileo_1; "BfspPrintFileOwnerProcess: Failed to ac"...
0x180031bc2  lea     ecx, [rax+4]
0x180031bc5  call    BfspLogMessage
0x180031bca  jmp     loc_180031E2D
0x180031bcf  xor     r9d, r9d; lpSecurityAttributes
0x180031bd2  mov     [rsp+0C0h+hTemplateFile], r12; hTemplateFile
0x180031bd7  mov     [rsp+0C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180031bdf  mov     edx, 100080h; dwDesiredAccess
0x180031be4  mov     rcx, rbx; lpFileName
0x180031be7  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180031bef  lea     r8d, [r9+7]; dwShareMode
0x180031bf3  call    cs:__imp_CreateFileW
0x180031bf9  mov     r14, rax
0x180031bfc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031c00  jnz     short loc_180031C20
0x180031c02  call    cs:__imp_GetLastError
0x180031c08  mov     r8d, eax
0x180031c0b  lea     rdx, aBfspprintfileo_2; "BfspPrintFileOwnerProcess: Failed to op"...
0x180031c12  lea     ecx, [r14+5]
0x180031c16  call    BfspLogMessage
0x180031c1b  jmp     loc_180031E2D
0x180031c20  mov     edi, 400h
0x180031c25  mov     [rbp+57h+Length], edi
0x180031c28  call    cs:__imp_GetProcessHeap
0x180031c2e  mov     r8d, edi; dwBytes
0x180031c31  mov     edx, 8; dwFlags
0x180031c36  mov     rcx, rax; hHeap
0x180031c39  call    cs:__imp_HeapAlloc
0x180031c3f  mov     rsi, rax
0x180031c42  test    rax, rax
0x180031c45  jz      loc_180031E24
0x180031c4b  mov     r9d, [rbp+57h+Length]; Length
0x180031c4f  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180031c53  mov     r8, rax; FileInformation
0x180031c56  mov     [rsp+0C0h+dwCreationDisposition], 2Fh ; '/'; FileInformationClass
0x180031c5e  mov     rcx, r14; FileHandle
0x180031c61  call    cs:__imp_NtQueryInformationFile
0x180031c67  test    eax, eax
0x180031c69  jns     short loc_180031C84
0x180031c6b  mov     r8d, eax
0x180031c6e  lea     rdx, aBfspprintfileo_0; "BfspPrintFileOwnerProcess: NtQueryInfor"...
0x180031c75  mov     ecx, 4
0x180031c7a  call    BfspLogMessage
0x180031c7f  jmp     loc_180031E10
0x180031c84  cmp     [rsi], r12d
0x180031c87  lea     rax, aNoProcessFound; "No process found using %s file."
0x180031c8e  lea     rdx, aPrintingProces; "Printing processes using %s file."
0x180031c95  mov     edi, 4
0x180031c9a  cmovbe  rdx, rax
0x180031c9e  mov     r8, rbx
0x180031ca1  mov     ecx, edi
0x180031ca3  call    BfspLogMessage
0x180031ca8  mov     [rbp+57h+ProcessHandle], r12
0x180031cac  mov     rbx, r12
0x180031caf  mov     r15d, r12d
0x180031cb2  cmp     [rsi], r12d
0x180031cb5  jbe     loc_180031E10
0x180031cbb  mov     eax, r15d
0x180031cbe  lea     r9, [rbp+57h+ClientId]; ClientId
0x180031cc2  mov     [rbp+57h+ClientId.UniqueThread], r12
0x180031cc6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180031cca  xorps   xmm0, xmm0
0x180031ccd  mov     edx, 1000h; DesiredAccess
0x180031cd2  mov     rcx, [rsi+rax*8+8]
0x180031cd7  mov     [rbp+57h+ClientId.UniqueProcess], rcx
0x180031cdb  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180031cdf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180031ce6  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180031cea  mov     [rbp+57h+ObjectAttributes.Attributes], r12d
0x180031cee  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x180031cf2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180031cf7  call    cs:__imp_NtOpenProcess
0x180031cfd  test    eax, eax
0x180031cff  jns     short loc_180031D17
0x180031d01  lea     rdx, aBfspprintfileo; "BfspPrintFileOwnerProcess: NtOpenProces"...
0x180031d08  mov     r8d, eax
0x180031d0b  mov     ecx, edi
0x180031d0d  call    BfspLogMessage
0x180031d12  jmp     loc_180031DD5
0x180031d17  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180031d1b  lea     rax, [rbp+57h+Length]
0x180031d1f  xor     r9d, r9d; ProcessInformationLength
0x180031d22  mov     [rbp+57h+Length], r12d
0x180031d26  xor     r8d, r8d; ProcessInformation
0x180031d29  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; ReturnLength
0x180031d2e  lea     edx, [r9+1Bh]; ProcessInformationClass
0x180031d32  call    cs:__imp_NtQueryInformationProcess
0x180031d38  cmp     eax, 80000005h
0x180031d3d  jz      short loc_180031D56
0x180031d3f  cmp     eax, 0C0000023h
0x180031d44  jz      short loc_180031D56
0x180031d46  cmp     eax, 0C0000004h
0x180031d4b  jz      short loc_180031D56
0x180031d4d  lea     rdx, aBfspprintfileo_5; "BfspPrintFileOwnerProcess: NtQueryInfor"...
0x180031d54  jmp     short loc_180031D08
0x180031d56  mov     ebx, [rbp+57h+Length]
0x180031d59  call    cs:__imp_GetProcessHeap
0x180031d5f  mov     r8d, ebx; dwBytes
0x180031d62  mov     edx, 8; dwFlags
0x180031d67  mov     rcx, rax; hHeap
0x180031d6a  call    cs:__imp_HeapAlloc
0x180031d70  mov     rbx, rax
0x180031d73  test    rax, rax
0x180031d76  jnz     short loc_180031D85
0x180031d78  mov     r8d, [rbp+57h+Length]
0x180031d7c  lea     rdx, aBfspprintfileo_3; "BfspPrintFileOwnerProcess: Malloc faile"...
0x180031d83  jmp     short loc_180031D0B
0x180031d85  mov     r9d, [rbp+57h+Length]; ProcessInformationLength
0x180031d89  lea     rax, [rbp+57h+Length]
0x180031d8d  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x180031d91  mov     r8, rbx; ProcessInformation
0x180031d94  mov     edx, 1Bh; ProcessInformationClass
0x180031d99  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rax; ReturnLength
0x180031d9e  call    cs:__imp_NtQueryInformationProcess
0x180031da4  test    eax, eax
0x180031da6  jns     short loc_180031DB4
0x180031da8  lea     rdx, aBfspprintfileo_4; "BfspPrintFileOwnerProcess: NtQueryInfor"...
0x180031daf  jmp     loc_180031D08
0x180031db4  lea     rdx, aProcessNameS; "Process Name = %s"
0x180031dbb  mov     ecx, edi
0x180031dbd  cmp     [rbx], r12w
0x180031dc1  jbe     short loc_180031DC9
0x180031dc3  mov     r8, [rbx+8]
0x180031dc7  jmp     short loc_180031DD0
0x180031dc9  lea     r8, aSystem; "System"
0x180031dd0  call    BfspLogMessage
0x180031dd5  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x180031dd9  test    rcx, rcx
0x180031ddc  jz      short loc_180031DE8
0x180031dde  call    cs:__imp_NtClose
0x180031de4  mov     [rbp+57h+ProcessHandle], r12
0x180031de8  test    rbx, rbx
0x180031deb  jz      short loc_180031E04
0x180031ded  call    cs:__imp_GetProcessHeap
0x180031df3  mov     r8, rbx; lpMem
0x180031df6  xor     edx, edx; dwFlags
0x180031df8  mov     rcx, rax; hHeap
0x180031dfb  call    cs:__imp_HeapFree
0x180031e01  mov     rbx, r12
0x180031e04  inc     r15d
0x180031e07  cmp     r15d, [rsi]
0x180031e0a  jb      loc_180031CBB
0x180031e10  call    cs:__imp_GetProcessHeap
0x180031e16  mov     r8, rsi; lpMem
0x180031e19  xor     edx, edx; dwFlags
0x180031e1b  mov     rcx, rax; hHeap
0x180031e1e  call    cs:__imp_HeapFree
0x180031e24  mov     rcx, r14; hObject
0x180031e27  call    cs:__imp_CloseHandle
0x180031e2d  mov     rbx, [rbp+57h+lpMem]
0x180031e31  test    rbx, rbx
0x180031e34  jz      short loc_180031E5E
0x180031e36  cmp     dword ptr [rbx], 1
0x180031e39  jnz     short loc_180031E41
0x180031e3b  test    byte ptr [rbx+0Ch], 2
0x180031e3f  jnz     short loc_180031E4A
0x180031e41  xor     edx, edx
0x180031e43  xor     ecx, ecx
0x180031e45  call    BfspAdjustDebugPrivilege
0x180031e4a  call    cs:__imp_GetProcessHeap
0x180031e50  mov     r8, rbx; lpMem
0x180031e53  xor     edx, edx; dwFlags
0x180031e55  mov     rcx, rax; hHeap
0x180031e58  call    cs:__imp_HeapFree
0x180031e5e  add     rsp, 90h
0x180031e65  pop     r15
0x180031e67  pop     r14
0x180031e69  pop     r12
0x180031e6b  pop     rdi
0x180031e6c  pop     rsi
0x180031e6d  pop     rbx
0x180031e6e  pop     rbp
0x180031e6f  retn
```
