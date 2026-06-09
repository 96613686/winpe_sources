# PfsAppInfoGet

- ea: `0x180085b04`
- end: `0x180085ba1`
- name: `PfsAppInfoGet`
- size: `157`
- prototype: `__int64 __usercall@<rax>(DWORD dwProcessId@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18005ffe4`

## callees

- `0x1800674c8`
- `0x180085b04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085b37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085b82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085b90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085b82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085b90`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180085b4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180085b4c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180085b29`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180085b29`

## pseudocode

```c
__int64 __fastcall PfsAppInfoGet(DWORD dwProcessId, int a2, int a3, int a4, __int64 a5)
{
  HANDLE v8; // rax
  void *v9; // rdi
  DWORD AppInfo; // eax
  DWORD v11; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF

  TokenHandle = 0;
  v8 = OpenProcess(0x1000u, 0, dwProcessId);
  v9 = v8;
  if ( v8 && OpenProcessToken(v8, 8u, &TokenHandle) )
    AppInfo = PfsGetAppInfo((_DWORD)TokenHandle, a2, a3, a4, a5);
  else
    AppInfo = GetLastError();
  v11 = AppInfo;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v9 )
    CloseHandle(v9);
  return v11;
}

```

## disassembly

```asm
0x180085b04  push    rbx
0x180085b06  push    rbp
0x180085b07  push    rsi
0x180085b08  push    rdi
0x180085b09  sub     rsp, 48h
0x180085b0d  mov     rsi, r8
0x180085b10  mov     [rsp+68h+TokenHandle], 0
0x180085b19  mov     r8d, ecx; dwProcessId
0x180085b1c  mov     rbp, rdx
0x180085b1f  mov     ecx, 1000h; dwDesiredAccess
0x180085b24  xor     edx, edx; bInheritHandle
0x180085b26  mov     rbx, r9
0x180085b29  call    cs:__imp_OpenProcess
0x180085b2f  mov     rdi, rax
0x180085b32  test    rax, rax
0x180085b35  jnz     short loc_180085B3F
0x180085b37  call    cs:__imp_GetLastError
0x180085b3d  jmp     short loc_180085B76
0x180085b3f  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x180085b44  mov     edx, 8; DesiredAccess
0x180085b49  mov     rcx, rdi; ProcessHandle
0x180085b4c  call    cs:__imp_OpenProcessToken
0x180085b52  test    eax, eax
0x180085b54  jz      short loc_180085B37
0x180085b56  mov     rax, [rsp+68h+arg_20]
0x180085b5e  mov     r9, rbx
0x180085b61  mov     rcx, [rsp+68h+TokenHandle]
0x180085b66  mov     r8, rsi
0x180085b69  mov     rdx, rbp
0x180085b6c  mov     [rsp+68h+var_48], rax
0x180085b71  call    PfsGetAppInfo
0x180085b76  mov     ebx, eax
0x180085b78  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180085b7d  test    rcx, rcx
0x180085b80  jz      short loc_180085B88
0x180085b82  call    cs:__imp_CloseHandle
0x180085b88  test    rdi, rdi
0x180085b8b  jz      short loc_180085B96
0x180085b8d  mov     rcx, rdi; hObject
0x180085b90  call    cs:__imp_CloseHandle
0x180085b96  mov     eax, ebx
0x180085b98  add     rsp, 48h
0x180085b9c  pop     rdi
0x180085b9d  pop     rsi
0x180085b9e  pop     rbp
0x180085b9f  pop     rbx
0x180085ba0  retn
```
