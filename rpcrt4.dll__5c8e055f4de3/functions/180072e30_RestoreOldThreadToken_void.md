# RestoreOldThreadToken(void *)

- ea: `0x180072e30`
- end: `0x180072e95`
- name: `?RestoreOldThreadToken@@YAXPEAX@Z`
- size: `101`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007200c`
- `0x180072be0`

## callees

- `0x180072e30`

## import_xrefs

- `ntdll!NtImpersonateAnonymousToken` at `0x180072e8d`
- `ntdll!NtImpersonateAnonymousToken` at `0x180072e8d`
- `ntdll!NtSetInformationThread` at `0x180072e69`
- `ntdll!NtSetInformationThread` at `0x180072e69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072e79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072e79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072e51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072e84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072e51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180072e84`

## pseudocode

```c
void __fastcall RestoreOldThreadToken(void *a1)
{
  void *v1; // rax
  HANDLE v2; // rax
  HANDLE CurrentThread; // rax
  HANDLE ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 == (void *)4294967294LL )
  {
    CurrentThread = GetCurrentThread();
    NtImpersonateAnonymousToken(CurrentThread);
  }
  else
  {
    v1 = 0;
    if ( a1 != (void *)4294967293LL )
      v1 = a1;
    ThreadInformation = v1;
    v2 = GetCurrentThread();
    NtSetInformationThread(v2, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( ThreadInformation )
      CloseHandle(ThreadInformation);
  }
}

```

## disassembly

```asm
0x180072e30  sub     rsp, 28h
0x180072e34  mov     eax, 0FFFFFFFEh
0x180072e39  cmp     rcx, rax
0x180072e3c  jz      short loc_180072E84
0x180072e3e  xor     eax, eax
0x180072e40  mov     edx, 0FFFFFFFDh
0x180072e45  cmp     rcx, rdx
0x180072e48  cmovnz  rax, rcx
0x180072e4c  mov     [rsp+28h+ThreadInformation], rax
0x180072e51  call    cs:__imp_GetCurrentThread
0x180072e57  mov     r9d, 8; ThreadInformationLength
0x180072e5d  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x180072e62  mov     rcx, rax; ThreadHandle
0x180072e65  lea     edx, [r9-3]; ThreadInformationClass
0x180072e69  call    cs:__imp_NtSetInformationThread
0x180072e6f  mov     rcx, [rsp+28h+ThreadInformation]; hObject
0x180072e74  test    rcx, rcx
0x180072e77  jz      short loc_180072E7F
0x180072e79  call    cs:__imp_CloseHandle
0x180072e7f  add     rsp, 28h
0x180072e83  retn
0x180072e84  call    cs:__imp_GetCurrentThread
0x180072e8a  mov     rcx, rax; Thread
0x180072e8d  call    cs:__imp_NtImpersonateAnonymousToken
0x180072e93  jmp     short loc_180072E7F
```
