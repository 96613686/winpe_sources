# ResumeLoggingToFile

- ea: `0x140002ba0`
- end: `0x140002c18`
- name: `ResumeLoggingToFile`
- size: `120`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002678`
- `0x140002ba0`
- `0x140003944`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140002bf6`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140002bf6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002bb0`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002bb0`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140002c05`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140002c05`

## string_xrefs

- `0x140002be3`: `Log location moved to %wZ; switched back to file logging`

## pseudocode

```c
void __fastcall ResumeLoggingToFile(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)
{
  __int64 v4; // rdx
  __int64 v5; // rcx

  if ( ExAcquireRundownProtection(&FilterRundownRef) )
  {
    LOBYTE(v4) = 1;
    LOBYTE(v5) = 1;
    if ( (int)OpenLog(v5, v4, 0, &String2) >= 0 )
      WriteLogMessage(1, L"Log location moved to %wZ; switched back to file logging", &String2);
    ExReleaseRundownProtection(&FilterRundownRef);
  }
  FltFreeGenericWorkItem(FltWorkItem);
}

```

## disassembly

```asm
0x140002ba0  push    rbx
0x140002ba2  sub     rsp, 20h
0x140002ba6  mov     rbx, rcx
0x140002ba9  lea     rcx, ?FilterRundownRef@@3U_EX_RUNDOWN_REF@@A; RunRef
0x140002bb0  call    cs:__imp_ExAcquireRundownProtection
0x140002bb7  nop     dword ptr [rax+rax+00h]
0x140002bbc  test    al, al
0x140002bbe  jz      short loc_140002C02
0x140002bc0  mov     dl, 1
0x140002bc2  lea     r9, String2
0x140002bc9  mov     cl, dl
0x140002bcb  xor     r8d, r8d
0x140002bce  call    OpenLog
0x140002bd3  test    eax, eax
0x140002bd5  js      short loc_140002BEF
0x140002bd7  lea     r8, String2
0x140002bde  mov     ecx, 1
0x140002be3  lea     rdx, aLogLocationMov; "Log location moved to %wZ; switched bac"...
0x140002bea  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140002bef  lea     rcx, ?FilterRundownRef@@3U_EX_RUNDOWN_REF@@A; RunRef
0x140002bf6  call    cs:__imp_ExReleaseRundownProtection
0x140002bfd  nop     dword ptr [rax+rax+00h]
0x140002c02  mov     rcx, rbx; FltWorkItem
0x140002c05  call    cs:__imp_FltFreeGenericWorkItem
0x140002c0c  nop     dword ptr [rax+rax+00h]
0x140002c11  add     rsp, 20h
0x140002c15  pop     rbx
0x140002c16  retn
```
