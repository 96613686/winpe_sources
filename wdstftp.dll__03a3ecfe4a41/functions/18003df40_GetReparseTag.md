# GetReparseTag

- ea: `0x18003df40`
- end: `0x18003e0de`
- name: `GetReparseTag`
- size: `414`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18003e0e4`
- `0x18003e138`

## callees

- `0x18003df40`
- `0x18003f704`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18003e00c`
- `KERNEL32!DeviceIoControl` at `0x18003e00c`
- `KERNEL32!HeapFree` at `0x18003e05b`
- `KERNEL32!HeapFree` at `0x18003e08a`
- `KERNEL32!HeapFree` at `0x18003e05b`
- `KERNEL32!HeapFree` at `0x18003e08a`
- `KERNEL32!HeapAlloc` at `0x18003dfce`
- `KERNEL32!HeapAlloc` at `0x18003dfce`
- `KERNEL32!GetLastError` at `0x18003e023`
- `KERNEL32!GetLastError` at `0x18003e098`
- `KERNEL32!GetLastError` at `0x18003e023`
- `KERNEL32!GetLastError` at `0x18003e098`
- `KERNEL32!CloseHandle` at `0x18003e06a`
- `KERNEL32!CloseHandle` at `0x18003e06a`
- `KERNEL32!CreateFileW` at `0x18003df99`
- `KERNEL32!CreateFileW` at `0x18003df99`
- `KERNEL32!SetLastError` at `0x18003e0b2`
- `KERNEL32!SetLastError` at `0x18003e0b2`
- `KERNEL32!GetProcessHeap` at `0x18003dfb6`
- `KERNEL32!GetProcessHeap` at `0x18003e047`
- `KERNEL32!GetProcessHeap` at `0x18003e076`
- `KERNEL32!GetProcessHeap` at `0x18003dfb6`
- `KERNEL32!GetProcessHeap` at `0x18003e047`
- `KERNEL32!GetProcessHeap` at `0x18003e076`

## pseudocode

```c
__int64 __fastcall GetReparseTag(unsigned __int16 *lpFileName, _DWORD *a2)
{
  unsigned int v3; // ebx
  DWORD LastError; // edi
  void *v6; // r15
  HANDLE FileW; // rbp
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rsi
  HANDLE v10; // rax
  HANDLE v11; // rax
  DWORD BytesReturned; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  LastError = 0;
  v6 = (void *)PrepareUnicodePath(lpFileName);
  if ( v6 )
  {
    *a2 = 0;
    FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x2200000u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      BytesReturned = 0;
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 8u, 0x4000u);
      if ( v9 )
      {
        if ( DeviceIoControl(FileW, 0x900A8u, 0, 0, v9, 0x4000u, &BytesReturned, 0) )
        {
          *a2 = *v9;
        }
        else
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 31;
        }
      }
      else
      {
        LastError = 14;
      }
      if ( v9 )
      {
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v9);
      }
      CloseHandle(FileW);
    }
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v6);
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 31;
  }
  SetLastError(LastError);
  LOBYTE(v3) = LastError == 0;
  return v3;
}

```

## disassembly

```asm
0x18003df40  mov     [rsp+arg_0], rbx
0x18003df45  mov     [rsp+arg_8], rbp
0x18003df4a  mov     [rsp+arg_18], rsi
0x18003df4f  push    rdi
0x18003df50  push    r14
0x18003df52  push    r15
0x18003df54  sub     rsp, 40h
0x18003df58  mov     r14, rdx
0x18003df5b  xor     ebx, ebx
0x18003df5d  xor     edx, edx
0x18003df5f  mov     edi, ebx
0x18003df61  mov     rsi, rcx
0x18003df64  call    PrepareUnicodePath
0x18003df69  mov     r15, rax
0x18003df6c  test    rax, rax
0x18003df6f  jz      loc_18003E098
0x18003df75  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x18003df7a  lea     r8d, [rbx+7]; dwShareMode
0x18003df7e  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003df86  xor     r9d, r9d; lpSecurityAttributes
0x18003df89  xor     edx, edx; dwDesiredAccess
0x18003df8b  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18003df93  mov     rcx, rsi; lpFileName
0x18003df96  mov     [r14], ebx
0x18003df99  call    cs:__imp_CreateFileW
0x18003dfa0  nop     dword ptr [rax+rax+00h]
0x18003dfa5  mov     rbp, rax
0x18003dfa8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003dfac  jz      loc_18003E076
0x18003dfb2  mov     [rsp+58h+BytesReturned], ebx
0x18003dfb6  call    cs:__imp_GetProcessHeap
0x18003dfbd  nop     dword ptr [rax+rax+00h]
0x18003dfc2  lea     edx, [rbx+8]; dwFlags
0x18003dfc5  mov     r8d, 4000h; dwBytes
0x18003dfcb  mov     rcx, rax; hHeap
0x18003dfce  call    cs:__imp_HeapAlloc
0x18003dfd5  nop     dword ptr [rax+rax+00h]
0x18003dfda  mov     rsi, rax
0x18003dfdd  test    rax, rax
0x18003dfe0  jz      short loc_18003E03D
0x18003dfe2  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x18003dfe7  lea     rax, [rsp+58h+BytesReturned]
0x18003dfec  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x18003dff1  xor     r9d, r9d; nInBufferSize
0x18003dff4  mov     [rsp+58h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x18003dffc  xor     r8d, r8d; lpInBuffer
0x18003dfff  mov     edx, 900A8h; dwIoControlCode
0x18003e004  mov     qword ptr [rsp+58h+dwCreationDisposition], rsi; lpOutBuffer
0x18003e009  mov     rcx, rbp; hDevice
0x18003e00c  call    cs:__imp_DeviceIoControl
0x18003e013  nop     dword ptr [rax+rax+00h]
0x18003e018  test    eax, eax
0x18003e01a  jz      short loc_18003E023
0x18003e01c  mov     eax, [rsi]
0x18003e01e  mov     [r14], eax
0x18003e021  jmp     short loc_18003E042
0x18003e023  call    cs:__imp_GetLastError
0x18003e02a  nop     dword ptr [rax+rax+00h]
0x18003e02f  mov     edi, eax
0x18003e031  mov     eax, 1Fh
0x18003e036  test    edi, edi
0x18003e038  cmovz   edi, eax
0x18003e03b  jmp     short loc_18003E042
0x18003e03d  mov     edi, 0Eh
0x18003e042  test    rsi, rsi
0x18003e045  jz      short loc_18003E067
0x18003e047  call    cs:__imp_GetProcessHeap
0x18003e04e  nop     dword ptr [rax+rax+00h]
0x18003e053  mov     r8, rsi; lpMem
0x18003e056  xor     edx, edx; dwFlags
0x18003e058  mov     rcx, rax; hHeap
0x18003e05b  call    cs:__imp_HeapFree
0x18003e062  nop     dword ptr [rax+rax+00h]
0x18003e067  mov     rcx, rbp; hObject
0x18003e06a  call    cs:__imp_CloseHandle
0x18003e071  nop     dword ptr [rax+rax+00h]
0x18003e076  call    cs:__imp_GetProcessHeap
0x18003e07d  nop     dword ptr [rax+rax+00h]
0x18003e082  mov     r8, r15; lpMem
0x18003e085  xor     edx, edx; dwFlags
0x18003e087  mov     rcx, rax; hHeap
0x18003e08a  call    cs:__imp_HeapFree
0x18003e091  nop     dword ptr [rax+rax+00h]
0x18003e096  jmp     short loc_18003E0B0
0x18003e098  call    cs:__imp_GetLastError
0x18003e09f  nop     dword ptr [rax+rax+00h]
0x18003e0a4  mov     edi, eax
0x18003e0a6  mov     eax, 1Fh
0x18003e0ab  test    edi, edi
0x18003e0ad  cmovz   edi, eax
0x18003e0b0  mov     ecx, edi; dwErrCode
0x18003e0b2  call    cs:__imp_SetLastError
0x18003e0b9  nop     dword ptr [rax+rax+00h]
0x18003e0be  mov     rbp, [rsp+58h+arg_8]
0x18003e0c3  test    edi, edi
0x18003e0c5  mov     rsi, [rsp+58h+arg_18]
0x18003e0ca  setz    bl
0x18003e0cd  mov     eax, ebx
0x18003e0cf  mov     rbx, [rsp+58h+arg_0]
0x18003e0d4  add     rsp, 40h
0x18003e0d8  pop     r15
0x18003e0da  pop     r14
0x18003e0dc  pop     rdi
0x18003e0dd  retn
```
