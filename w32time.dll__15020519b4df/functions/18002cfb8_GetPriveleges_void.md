# GetPriveleges(void)

- ea: `0x18002cfb8`
- end: `0x18002d0de`
- name: `?GetPriveleges@@YAJXZ`
- size: `294`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001da40`

## callees

- `0x18002cfb8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d000`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d078`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002cfe4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002cfe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002cfcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002cfcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d0bf`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002d068`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002d068`

## pseudocode

```c
__int64 GetPriveleges(void)
{
  HANDLE CurrentProcess; // rax
  char *v1; // rax
  void *v2; // rdi
  signed int LastError; // eax
  unsigned int v4; // ebx
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h]

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v1 = (char *)LocalAlloc(0x40u, 0x1Cu);
    v2 = v1;
    if ( !v1 )
    {
      v4 = -2147024882;
      goto LABEL_6;
    }
    v7 = 12;
    *(_DWORD *)v1 = 2;
    *(_QWORD *)(v1 + 4) = v7;
    *((_DWORD *)v1 + 3) = 2;
    *((_DWORD *)v1 + 6) = 2;
    v7 = 14;
    *((_QWORD *)v1 + 2) = 14;
    if ( AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)v1, 0, 0, 0) )
    {
      v4 = 0;
      goto LABEL_6;
    }
  }
  else
  {
    v2 = 0;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
LABEL_6:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
    LocalFree(v2);
  return v4;
}

```

## disassembly

```asm
0x18002cfb8  mov     [rsp+arg_10], rbx
0x18002cfbd  push    rdi
0x18002cfbe  sub     rsp, 30h
0x18002cfc2  mov     [rsp+38h+TokenHandle], 0
0x18002cfcb  call    cs:__imp_GetCurrentProcess
0x18002cfd2  nop     dword ptr [rax+rax+00h]
0x18002cfd7  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18002cfdc  mov     edx, 28h ; '('; DesiredAccess
0x18002cfe1  mov     rcx, rax; ProcessHandle
0x18002cfe4  call    cs:__imp_OpenProcessToken
0x18002cfeb  nop     dword ptr [rax+rax+00h]
0x18002cff0  test    eax, eax
0x18002cff2  jz      loc_18002D0B0
0x18002cff8  mov     edx, 1Ch; uBytes
0x18002cffd  lea     ecx, [rdx+24h]; uFlags
0x18002d000  call    cs:__imp_LocalAlloc
0x18002d007  nop     dword ptr [rax+rax+00h]
0x18002d00c  mov     rdi, rax
0x18002d00f  test    rax, rax
0x18002d012  jz      loc_18002D0B4
0x18002d018  mov     ecx, 2
0x18002d01d  mov     [rsp+38h+arg_8], 0Ch
0x18002d026  mov     [rax], ecx
0x18002d028  xor     r9d, r9d; BufferLength
0x18002d02b  mov     rax, [rsp+38h+arg_8]
0x18002d030  mov     r8, rdi; NewState
0x18002d033  mov     [rdi+4], rax
0x18002d037  xor     edx, edx; DisableAllPrivileges
0x18002d039  mov     [rdi+0Ch], ecx
0x18002d03c  mov     [rdi+18h], ecx
0x18002d03f  mov     [rsp+38h+arg_8], 0Eh
0x18002d048  mov     rax, [rsp+38h+arg_8]
0x18002d04d  mov     [rdi+10h], rax
0x18002d051  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18002d056  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x18002d05f  mov     [rsp+38h+PreviousState], 0; PreviousState
0x18002d068  call    cs:__imp_AdjustTokenPrivileges
0x18002d06f  nop     dword ptr [rax+rax+00h]
0x18002d074  test    eax, eax
0x18002d076  jnz     short loc_18002D0BB
0x18002d078  call    cs:__imp_GetLastError
0x18002d07f  nop     dword ptr [rax+rax+00h]
0x18002d084  mov     ebx, eax
0x18002d086  test    eax, eax
0x18002d088  jle     short loc_18002D093
0x18002d08a  movzx   ebx, ax
0x18002d08d  or      ebx, 80070000h
0x18002d093  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18002d098  test    rcx, rcx
0x18002d09b  jnz     short loc_18002D0BF
0x18002d09d  test    rdi, rdi
0x18002d0a0  jnz     short loc_18002D0CD
0x18002d0a2  mov     eax, ebx
0x18002d0a4  mov     rbx, [rsp+38h+arg_10]
0x18002d0a9  add     rsp, 30h
0x18002d0ad  pop     rdi
0x18002d0ae  retn
0x18002d0b0  xor     edi, edi
0x18002d0b2  jmp     short loc_18002D078
0x18002d0b4  mov     ebx, 8007000Eh
0x18002d0b9  jmp     short loc_18002D093
0x18002d0bb  xor     ebx, ebx
0x18002d0bd  jmp     short loc_18002D093
0x18002d0bf  call    cs:__imp_CloseHandle
0x18002d0c6  nop     dword ptr [rax+rax+00h]
0x18002d0cb  jmp     short loc_18002D09D
0x18002d0cd  mov     rcx, rdi; hMem
0x18002d0d0  call    cs:__imp_LocalFree
0x18002d0d7  nop     dword ptr [rax+rax+00h]
0x18002d0dc  jmp     short loc_18002D0A2
```
