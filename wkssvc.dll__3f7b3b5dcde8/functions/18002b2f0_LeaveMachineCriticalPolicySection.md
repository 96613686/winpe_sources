# LeaveMachineCriticalPolicySection

- ea: `0x18002b2f0`
- end: `0x18002b33e`
- name: `LeaveMachineCriticalPolicySection`
- size: `78`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001d4c0`

## callees

- `0x18002b2f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b31c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b31c`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002b333`
- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18002b333`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b315`
- `USERENV!LeaveCriticalPolicySection` at `0x18002b2f9`
- `USERENV!LeaveCriticalPolicySection` at `0x18002b2f9`

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
0x18002b2f0  sub     rsp, 28h
0x18002b2f4  test    rcx, rcx
0x18002b2f7  jz      short loc_18002B339
0x18002b2f9  call    cs:__imp_LeaveCriticalPolicySection
0x18002b2ff  test    eax, eax
0x18002b301  jz      short loc_18002B31C
0x18002b303  lea     rdx, aLeavemachinecr; "LeaveMachineCriticalPolicySection"
0x18002b30a  lea     rcx, aAutojoinsvcSMa_2; "AutoJoinSvc/%s: Machine group policy lo"...
0x18002b311  add     rsp, 28h
0x18002b315  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b31c  call    cs:__imp_GetLastError
0x18002b322  mov     r8d, eax
0x18002b325  lea     rdx, aLeavemachinecr; "LeaveMachineCriticalPolicySection"
0x18002b32c  lea     rcx, aAutojoinsvcSFa_0; "AutoJoinSvc/%s: Failed to release machi"...
0x18002b333  call    cs:__imp_DsrWriteAutoJoinSvcAdminEvent
0x18002b339  add     rsp, 28h
0x18002b33d  retn
```
