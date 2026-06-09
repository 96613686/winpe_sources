# RestoreOldThreadToken(void *)

- ea: `0x180071d4c`
- end: `0x180071dd0`
- name: `?RestoreOldThreadToken@@YAXPEAX@Z`
- size: `132`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180070fec`
- `0x180071ad0`

## callees

- `0x180071d4c`

## import_xrefs

- `ntdll!NtImpersonateAnonymousToken` at `0x180071dc2`
- `ntdll!NtImpersonateAnonymousToken` at `0x180071dc2`
- `ntdll!NtSetInformationThread` at `0x180071d8b`
- `ntdll!NtSetInformationThread` at `0x180071d8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071da1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071da1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071d6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071db3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071d6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071db3`

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
0x180071d4c  sub     rsp, 28h
0x180071d50  mov     eax, 0FFFFFFFEh
0x180071d55  cmp     rcx, rax
0x180071d58  jz      short loc_180071DB3
0x180071d5a  xor     eax, eax
0x180071d5c  mov     edx, 0FFFFFFFDh
0x180071d61  cmp     rcx, rdx
0x180071d64  cmovnz  rax, rcx
0x180071d68  mov     [rsp+28h+ThreadInformation], rax
0x180071d6d  call    cs:__imp_GetCurrentThread
0x180071d74  nop     dword ptr [rax+rax+00h]
0x180071d79  mov     r9d, 8; ThreadInformationLength
0x180071d7f  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x180071d84  mov     rcx, rax; ThreadHandle
0x180071d87  lea     edx, [r9-3]; ThreadInformationClass
0x180071d8b  call    cs:__imp_NtSetInformationThread
0x180071d92  nop     dword ptr [rax+rax+00h]
0x180071d97  mov     rcx, [rsp+28h+ThreadInformation]; hObject
0x180071d9c  test    rcx, rcx
0x180071d9f  jz      short loc_180071DAD
0x180071da1  call    cs:__imp_CloseHandle
0x180071da8  nop     dword ptr [rax+rax+00h]
0x180071dad  add     rsp, 28h
0x180071db1  retn
0x180071db3  call    cs:__imp_GetCurrentThread
0x180071dba  nop     dword ptr [rax+rax+00h]
0x180071dbf  mov     rcx, rax; Thread
0x180071dc2  call    cs:__imp_NtImpersonateAnonymousToken
0x180071dc9  nop     dword ptr [rax+rax+00h]
0x180071dce  jmp     short loc_180071DAD
```
