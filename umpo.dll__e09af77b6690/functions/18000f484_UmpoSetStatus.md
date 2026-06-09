# UmpoSetStatus

- ea: `0x18000f484`
- end: `0x18000f4ee`
- name: `UmpoSetStatus`
- size: `106`
- prototype: `BOOL __fastcall(DWORD, DWORD, DWORD, DWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000c4a0`
- `0x18000ed10`
- `0x180015280`

## callees

- `0x18000f484`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000f4e3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000f4e3`

## pseudocode

```c
BOOL __fastcall UmpoSetStatus(DWORD a1, DWORD a2, DWORD a3, DWORD a4)
{
  BOOL result; // eax

  if ( UmpoHandle )
  {
    UmpoStatus.dwCurrentState = a1;
    UmpoStatus.dwWin32ExitCode = a2;
    UmpoStatus.dwControlsAccepted = a4;
    if ( a1 == 4 || a1 == 1 )
    {
      *(_QWORD *)&UmpoStatus.dwCheckPoint = 0;
    }
    else
    {
      UmpoStatus.dwCheckPoint = dword_180024408++;
      UmpoStatus.dwWaitHint = a3;
    }
    return SetServiceStatus(UmpoHandle, &UmpoStatus);
  }
  return result;
}

```

## disassembly

```asm
0x18000f484  sub     rsp, 28h
0x18000f488  mov     r10, cs:UmpoHandle
0x18000f48f  test    r10, r10
0x18000f492  jz      short loc_18000F4E9
0x18000f494  mov     cs:UmpoStatus.dwCurrentState, ecx
0x18000f49a  mov     cs:UmpoStatus.dwWin32ExitCode, edx
0x18000f4a0  mov     cs:UmpoStatus.dwControlsAccepted, r9d
0x18000f4a7  cmp     ecx, 4
0x18000f4aa  jz      short loc_18000F4CE
0x18000f4ac  cmp     ecx, 1
0x18000f4af  jz      short loc_18000F4CE
0x18000f4b1  mov     eax, cs:dword_180024408
0x18000f4b7  mov     cs:UmpoStatus.dwCheckPoint, eax
0x18000f4bd  inc     eax
0x18000f4bf  mov     cs:dword_180024408, eax
0x18000f4c5  mov     cs:UmpoStatus.dwWaitHint, r8d
0x18000f4cc  jmp     short loc_18000F4D9
0x18000f4ce  mov     qword ptr cs:UmpoStatus.dwCheckPoint, 0
0x18000f4d9  lea     rdx, UmpoStatus; lpServiceStatus
0x18000f4e0  mov     rcx, r10; hServiceStatus
0x18000f4e3  call    cs:__imp_SetServiceStatus
0x18000f4e9  add     rsp, 28h
0x18000f4ed  retn
```
