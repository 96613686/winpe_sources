# LeaveMachineCriticalPolicySection

- ea: `0x18002d908`
- end: `0x18002d96e`
- name: `LeaveMachineCriticalPolicySection`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001eb30`

## callees

- `0x18002d908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d93f`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002d95c`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002d95c`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002d933`
- `USERENV!LeaveCriticalPolicySection` at `0x18002d911`
- `USERENV!LeaveCriticalPolicySection` at `0x18002d911`

## pseudocode

```c
void __fastcall LeaveMachineCriticalPolicySection(void *a1)
{
  DWORD LastError; // eax

  if ( a1 )
  {
    if ( LeaveCriticalPolicySection(a1) )
    {
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: Machine group policy lock successfully released",
        L"LeaveMachineCriticalPolicySection");
    }
    else
    {
      LastError = GetLastError();
      DsrWriteAutoJoinSvcAdminEvent(
        L"AutoJoinSvc/%s: Failed to release machine group policy lock with error 0x%08x.",
        L"LeaveMachineCriticalPolicySection",
        LastError);
    }
  }
}

```

## disassembly

```asm
0x18002d908  sub     rsp, 28h
0x18002d90c  test    rcx, rcx
0x18002d90f  jz      short loc_18002D968
0x18002d911  call    cs:__imp_LeaveCriticalPolicySection
0x18002d918  nop     dword ptr [rax+rax+00h]
0x18002d91d  test    eax, eax
0x18002d91f  jz      short loc_18002D93F
0x18002d921  lea     rdx, aLeavemachinecr; "LeaveMachineCriticalPolicySection"
0x18002d928  lea     rcx, aAutojoinsvcSMa_2; "AutoJoinSvc/%s: Machine group policy lo"...
0x18002d92f  add     rsp, 28h
0x18002d933  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002d93f  call    cs:__imp_GetLastError
0x18002d946  nop     dword ptr [rax+rax+00h]
0x18002d94b  mov     r8d, eax
0x18002d94e  lea     rdx, aLeavemachinecr; "LeaveMachineCriticalPolicySection"
0x18002d955  lea     rcx, aAutojoinsvcSFa_0; "AutoJoinSvc/%s: Failed to release machi"...
0x18002d95c  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002d963  nop     dword ptr [rax+rax+00h]
0x18002d968  add     rsp, 28h
0x18002d96c  retn
```
