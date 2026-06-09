# ValidateFile

- ea: `0x18000ada0`
- end: `0x18000b005`
- name: `ValidateFile`
- size: `613`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, DWORD, DWORD dwCreationDisposition, __int64, LPWSTR *, DWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180004610`
- `0x1800061d0`
- `0x180008d90`
- `0x1800090d0`

## callees

- `0x180005730`
- `0x18000ada0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000aeef`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000aeef`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000aff4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000aff4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ae30`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ae30`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000af4b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000af4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af5b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000afb1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000afb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afd3`
- `ntdll!RtlFreeHeap` at `0x18000ae6e`
- `ntdll!RtlFreeHeap` at `0x18000ae6e`
- `ntdll!RtlAllocateHeap` at `0x18000aebd`
- `ntdll!RtlAllocateHeap` at `0x18000aebd`

## pseudocode

```c
__int64 __fastcall ValidateFile(
        LPCWSTR lpFileName,
        DWORD a2,
        DWORD dwCreationDisposition,
        __int64 a4,
        LPWSTR *a5,
        DWORD *a6)
{
  HANDLE FileW; // rsi
  DWORD LastError; // ebx
  WCHAR *Heap; // rax
  int v12; // ebx
  DWORD FinalPathNameByHandleW; // eax
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  _WORD InBuffer[2]; // [rsp+40h] [rbp-69h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-65h] BYREF
  DWORD dwFlags[6]; // [rsp+48h] [rbp-61h]
  __int128 v19; // [rsp+60h] [rbp-49h]
  int v20; // [rsp+70h] [rbp-39h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-31h] BYREF

  dwFlags[2] = 8;
  BytesReturned = 0;
  InBuffer[0] = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v20 = 0;
  dwFlags[0] = 0;
  v19 = 0;
  dwFlags[1] = 1;
  dwFlags[3] = 9;
  dwFlags[4] = 10;
  FileW = CreateFileW(lpFileName, a2, 7u, 0, dwCreationDisposition, 0x100080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    goto LABEL_3;
  }
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xFFFEu);
  *a5 = Heap;
  if ( !Heap )
  {
    LastError = 14;
    goto LABEL_26;
  }
  v12 = 0;
  while ( 1 )
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, *a5, 0x7FFFu, dwFlags[v12]);
    *a6 = FinalPathNameByHandleW;
    if ( FinalPathNameByHandleW )
      break;
    if ( (unsigned int)++v12 >= 5 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 2;
      goto LABEL_26;
    }
  }
  v14 = FinalPathNameByHandleW + 1;
  if ( (unsigned int)v14 < FinalPathNameByHandleW )
  {
    *a6 = -1;
    goto LABEL_25;
  }
  v15 = 2 * v14;
  if ( v15 > 0xFFFFFFFF )
  {
    *a6 = -1;
LABEL_25:
    LastError = 534;
    goto LABEL_26;
  }
  *a6 = v15;
  if ( GetFileInformationByHandle(FileW, &FileInformation) )
  {
    if ( (FileInformation.dwFileAttributes & 0x10) != 0 )
    {
      LastError = 267;
    }
    else
    {
      if ( dwCreationDisposition == 1 )
        DeviceIoControl(FileW, 0x9C040u, InBuffer, 2u, 0, 0, &BytesReturned, 0);
      LastError = 0;
    }
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_26:
  CloseHandle(FileW);
  if ( dwCreationDisposition != 1 )
  {
LABEL_3:
    if ( !LastError )
      return LastError;
    goto LABEL_4;
  }
  if ( !LastError )
    return LastError;
  DeleteFileW(lpFileName);
LABEL_4:
  if ( *a5 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a5);
    *a5 = 0;
    *a6 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000ada0  push    rbp
0x18000ada2  push    rbx
0x18000ada3  push    rsi
0x18000ada4  push    rdi
0x18000ada5  push    r12
0x18000ada7  push    r14
0x18000ada9  push    r15
0x18000adab  lea     rbp, [rsp-17h]
0x18000adb0  sub     rsp, 0C0h
0x18000adb7  mov     rax, cs:__security_cookie
0x18000adbe  xor     rax, rsp
0x18000adc1  mov     [rbp+47h+var_40], rax
0x18000adc5  mov     r14, [rbp+47h+arg_20]
0x18000adc9  xor     eax, eax
0x18000adcb  mov     rdi, [rbp+47h+arg_28]
0x18000adcf  xorps   xmm0, xmm0
0x18000add2  mov     [rsp+0F0h+hTemplateFile], rax; hTemplateFile
0x18000add7  mov     r15d, r8d
0x18000adda  mov     [rsp+0F0h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18000ade2  xor     r9d, r9d; lpSecurityAttributes
0x18000ade5  lea     ebx, [rax+8]
0x18000ade8  mov     [rsp+0F0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000aded  lea     r8d, [rax+7]; dwShareMode
0x18000adf1  mov     [rbp+47h+var_A0], ebx
0x18000adf4  mov     r12, rcx
0x18000adf7  mov     [rbp+47h+BytesReturned], 0
0x18000adfe  mov     [rbp+47h+InBuffer], ax
0x18000ae02  movups  xmmword ptr [rbp+47h+FileInformation.dwFileAttributes], xmm0
0x18000ae06  mov     [rbp+47h+FileInformation.nFileIndexLow], eax
0x18000ae09  movups  xmmword ptr [rbp+47h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18000ae0d  mov     [rbp+47h+var_80], eax
0x18000ae10  movups  xmmword ptr [rbp+47h+FileInformation.nFileSizeHigh], xmm0
0x18000ae14  mov     [rbp+47h+dwFlags], eax
0x18000ae17  movups  [rbp+47h+var_90], xmm0
0x18000ae1b  mov     [rbp+47h+var_A4], 1
0x18000ae22  mov     [rbp+47h+var_9C], 9
0x18000ae29  mov     [rbp+47h+var_98], 0Ah
0x18000ae30  call    cs:__imp_CreateFileW
0x18000ae37  nop     dword ptr [rax+rax+00h]
0x18000ae3c  mov     rsi, rax
0x18000ae3f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ae43  jnz     short loc_18000AEA8
0x18000ae45  call    cs:__imp_GetLastError
0x18000ae4c  nop     dword ptr [rax+rax+00h]
0x18000ae51  mov     ebx, eax
0x18000ae53  test    ebx, ebx
0x18000ae55  jz      short loc_18000AE87
0x18000ae57  mov     r8, [r14]; P
0x18000ae5a  test    r8, r8
0x18000ae5d  jz      short loc_18000AE87
0x18000ae5f  mov     rcx, gs:60h
0x18000ae68  xor     edx, edx; Flags
0x18000ae6a  mov     rcx, [rcx+30h]; HeapHandle
0x18000ae6e  call    cs:__imp_RtlFreeHeap
0x18000ae75  nop     dword ptr [rax+rax+00h]
0x18000ae7a  mov     qword ptr [r14], 0
0x18000ae81  mov     dword ptr [rdi], 0
0x18000ae87  mov     eax, ebx
0x18000ae89  mov     rcx, [rbp+47h+var_40]
0x18000ae8d  xor     rcx, rsp; StackCookie
0x18000ae90  call    __security_check_cookie
0x18000ae95  add     rsp, 0C0h
0x18000ae9c  pop     r15
0x18000ae9e  pop     r14
0x18000aea0  pop     r12
0x18000aea2  pop     rdi
0x18000aea3  pop     rsi
0x18000aea4  pop     rbx
0x18000aea5  pop     rbp
0x18000aea6  retn
0x18000aea8  mov     rcx, gs:60h
0x18000aeb1  mov     r8d, 0FFFEh; Size
0x18000aeb7  mov     edx, ebx; Flags
0x18000aeb9  mov     rcx, [rcx+30h]; HeapHandle
0x18000aebd  call    cs:__imp_RtlAllocateHeap
0x18000aec4  nop     dword ptr [rax+rax+00h]
0x18000aec9  mov     [r14], rax
0x18000aecc  test    rax, rax
0x18000aecf  jnz     short loc_18000AED9
0x18000aed1  lea     ebx, [rax+0Eh]
0x18000aed4  jmp     loc_18000AFD0
0x18000aed9  xor     ebx, ebx
0x18000aedb  mov     rdx, [r14]; lpszFilePath
0x18000aede  mov     r8d, 7FFFh; cchFilePath
0x18000aee4  movsxd  r9, ebx
0x18000aee7  mov     rcx, rsi; hFile
0x18000aeea  mov     r9d, [rbp+r9*4+47h+dwFlags]; dwFlags
0x18000aeef  call    cs:__imp_GetFinalPathNameByHandleW
0x18000aef6  nop     dword ptr [rax+rax+00h]
0x18000aefb  mov     [rdi], eax
0x18000aefd  test    eax, eax
0x18000aeff  jnz     short loc_18000AF2A
0x18000af01  inc     ebx
0x18000af03  cmp     ebx, 5
0x18000af06  jb      short loc_18000AEDB
0x18000af08  test    eax, eax
0x18000af0a  jnz     short loc_18000AF2A
0x18000af0c  call    cs:__imp_GetLastError
0x18000af13  nop     dword ptr [rax+rax+00h]
0x18000af18  mov     ebx, eax
0x18000af1a  test    eax, eax
0x18000af1c  jnz     loc_18000AFD0
0x18000af22  lea     ebx, [rax+2]
0x18000af25  jmp     loc_18000AFD0
0x18000af2a  lea     ecx, [rax+1]
0x18000af2d  cmp     ecx, eax
0x18000af2f  jb      loc_18000AFC5
0x18000af35  add     rcx, rcx
0x18000af38  mov     eax, 0FFFFFFFFh
0x18000af3d  cmp     rcx, rax
0x18000af40  ja      short loc_18000AFC1
0x18000af42  mov     [rdi], ecx
0x18000af44  lea     rdx, [rbp+47h+FileInformation]; lpFileInformation
0x18000af48  mov     rcx, rsi; hFile
0x18000af4b  call    cs:__imp_GetFileInformationByHandle
0x18000af52  nop     dword ptr [rax+rax+00h]
0x18000af57  test    eax, eax
0x18000af59  jnz     short loc_18000AF6B
0x18000af5b  call    cs:__imp_GetLastError
0x18000af62  nop     dword ptr [rax+rax+00h]
0x18000af67  mov     ebx, eax
0x18000af69  jmp     short loc_18000AFD0
0x18000af6b  test    byte ptr [rbp+47h+FileInformation.dwFileAttributes], 10h
0x18000af6f  jz      short loc_18000AF78
0x18000af71  mov     ebx, 10Bh
0x18000af76  jmp     short loc_18000AFD0
0x18000af78  cmp     r15d, 1
0x18000af7c  jnz     short loc_18000AFBD
0x18000af7e  mov     [rsp+0F0h+lpOverlapped], 0; lpOverlapped
0x18000af87  lea     rax, [rbp+47h+BytesReturned]
0x18000af8b  mov     [rsp+0F0h+hTemplateFile], rax; lpBytesReturned
0x18000af90  lea     r9d, [r15+1]; nInBufferSize
0x18000af94  mov     [rsp+0F0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18000af9c  lea     r8, [rbp+47h+InBuffer]; lpInBuffer
0x18000afa0  mov     edx, 9C040h; dwIoControlCode
0x18000afa5  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; lpOutBuffer
0x18000afae  mov     rcx, rsi; hDevice
0x18000afb1  call    cs:__imp_DeviceIoControl
0x18000afb8  nop     dword ptr [rax+rax+00h]
0x18000afbd  xor     ebx, ebx
0x18000afbf  jmp     short loc_18000AFD0
0x18000afc1  mov     [rdi], eax
0x18000afc3  jmp     short loc_18000AFCB
0x18000afc5  mov     dword ptr [rdi], 0FFFFFFFFh
0x18000afcb  mov     ebx, 216h
0x18000afd0  mov     rcx, rsi; hObject
0x18000afd3  call    cs:__imp_CloseHandle
0x18000afda  nop     dword ptr [rax+rax+00h]
0x18000afdf  cmp     r15d, 1
0x18000afe3  jnz     loc_18000AE53
0x18000afe9  test    ebx, ebx
0x18000afeb  jz      loc_18000AE87
0x18000aff1  mov     rcx, r12; lpFileName
0x18000aff4  call    cs:__imp_DeleteFileW
0x18000affb  nop     dword ptr [rax+rax+00h]
0x18000b000  jmp     loc_18000AE57
```
