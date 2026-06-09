# ResetPrivilege(_TOKEN_PRIVILEGES *,ulong)

- ea: `0x18001d278`
- end: `0x18001d300`
- name: `?ResetPrivilege@@YAHPEAU_TOKEN_PRIVILEGES@@K@Z`
- size: `136`
- prototype: `__int64 __fastcall(HLOCAL hMem, ULONG BufferLength)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001ce90`

## callees

- `0x18001d278`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d2e8`
- `ntdll!NtOpenProcessToken` at `0x18001d2a3`
- `ntdll!NtOpenProcessToken` at `0x18001d2a3`
- `ntdll!NtAdjustPrivilegesToken` at `0x18001d2cd`
- `ntdll!NtAdjustPrivilegesToken` at `0x18001d2cd`
- `ntdll!NtClose` at `0x18001d2da`
- `ntdll!NtClose` at `0x18001d2da`

## pseudocode

```c
_BOOL8 __fastcall ResetPrivilege(struct _TOKEN_PRIVILEGES *hMem, ULONG BufferLength)
{
  BOOL v2; // ebx
  NTSTATUS v5; // ebx
  ULONG ReturnLength; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  if ( hMem )
  {
    TokenHandle = 0;
    if ( NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, &TokenHandle) >= 0 )
    {
      ReturnLength = 0;
      v5 = NtAdjustPrivilegesToken(TokenHandle, 0, hMem, BufferLength, 0, &ReturnLength);
      NtClose(TokenHandle);
      v2 = v5 >= 0;
    }
    LocalFree(hMem);
  }
  return v2;
}

```

## disassembly

```asm
0x18001d278  mov     rax, rsp
0x18001d27b  mov     [rax+10h], rbx
0x18001d27f  mov     [rax+20h], rsi
0x18001d283  push    rdi
0x18001d284  sub     rsp, 30h
0x18001d288  xor     ebx, ebx
0x18001d28a  mov     esi, edx
0x18001d28c  mov     rdi, rcx
0x18001d28f  test    rcx, rcx
0x18001d292  jz      short loc_18001D2EE
0x18001d294  lea     r8, [rax+18h]; TokenHandle
0x18001d298  mov     [rax+18h], rbx
0x18001d29c  lea     edx, [rbx+28h]; DesiredAccess
0x18001d29f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001d2a3  call    cs:__imp_NtOpenProcessToken
0x18001d2a9  test    eax, eax
0x18001d2ab  js      short loc_18001D2E5
0x18001d2ad  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18001d2b2  lea     rax, [rsp+38h+arg_0]
0x18001d2b7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001d2bc  mov     r9d, esi; BufferLength
0x18001d2bf  mov     r8, rdi; NewState
0x18001d2c2  mov     [rsp+38h+PreviousState], rbx; PreviousState
0x18001d2c7  xor     edx, edx; DisableAllPrivileges
0x18001d2c9  mov     [rsp+38h+arg_0], ebx
0x18001d2cd  call    cs:__imp_NtAdjustPrivilegesToken
0x18001d2d3  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x18001d2d8  mov     ebx, eax
0x18001d2da  call    cs:__imp_NtClose
0x18001d2e0  not     ebx
0x18001d2e2  shr     ebx, 1Fh
0x18001d2e5  mov     rcx, rdi; hMem
0x18001d2e8  call    cs:__imp_LocalFree
0x18001d2ee  mov     rsi, [rsp+38h+arg_18]
0x18001d2f3  mov     eax, ebx
0x18001d2f5  mov     rbx, [rsp+38h+arg_8]
0x18001d2fa  add     rsp, 30h
0x18001d2fe  pop     rdi
0x18001d2ff  retn
```
