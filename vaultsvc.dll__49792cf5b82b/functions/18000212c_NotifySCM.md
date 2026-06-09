# NotifySCM

- ea: `0x18000212c`
- end: `0x1800021df`
- name: `NotifySCM`
- size: `179`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001aa0`
- `0x180002884`
- `0x18002b940`

## callees

- `0x18000212c`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021a4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000216f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000216f`

## pseudocode

```c
__int64 __fastcall NotifySCM(DWORD a1, DWORD a2, DWORD a3)
{
  DWORD LastError; // ebx

  LastError = 0;
  ServiceStatus.dwCurrentState = a1;
  ServiceStatus.dwWaitHint = a2;
  ServiceStatus.dwWin32ExitCode = a3;
  if ( a1 == 2 )
  {
    ServiceStatus.dwControlsAccepted = 0;
LABEL_8:
    ServiceStatus.dwCheckPoint = dword_18005F3B4++;
    goto LABEL_4;
  }
  ServiceStatus.dwControlsAccepted = 133;
  if ( a1 != 4 && a1 != 1 )
    goto LABEL_8;
  ServiceStatus.dwCheckPoint = 0;
LABEL_4:
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_78b059fac4093813b2646cef9913e025_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000212c  push    rbx
0x18000212e  sub     rsp, 20h
0x180002132  xor     ebx, ebx
0x180002134  mov     cs:ServiceStatus.dwCurrentState, ecx
0x18000213a  mov     cs:ServiceStatus.dwWaitHint, edx
0x180002140  mov     cs:ServiceStatus.dwWin32ExitCode, r8d
0x180002147  cmp     ecx, 2
0x18000214a  jz      short loc_180002181
0x18000214c  mov     cs:ServiceStatus.dwControlsAccepted, 85h
0x180002156  cmp     ecx, 4
0x180002159  jnz     short loc_180002189
0x18000215b  mov     cs:ServiceStatus.dwCheckPoint, ebx
0x180002161  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180002168  lea     rdx, ServiceStatus; lpServiceStatus
0x18000216f  call    cs:__imp_SetServiceStatus
0x180002175  test    eax, eax
0x180002177  jz      short loc_1800021A4
0x180002179  mov     eax, ebx
0x18000217b  add     rsp, 20h
0x18000217f  pop     rbx
0x180002180  retn
0x180002181  mov     cs:ServiceStatus.dwControlsAccepted, ebx
0x180002187  jmp     short loc_18000218E
0x180002189  cmp     ecx, 1
0x18000218c  jz      short loc_18000215B
0x18000218e  mov     eax, cs:dword_18005F3B4
0x180002194  mov     cs:ServiceStatus.dwCheckPoint, eax
0x18000219a  inc     eax
0x18000219c  mov     cs:dword_18005F3B4, eax
0x1800021a2  jmp     short loc_180002161
0x1800021a4  call    cs:__imp_GetLastError
0x1800021aa  mov     ebx, eax
0x1800021ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021b3  lea     rax, WPP_GLOBAL_Control
0x1800021ba  cmp     rcx, rax
0x1800021bd  jz      short loc_180002179
0x1800021bf  test    byte ptr [rcx+1Ch], 2
0x1800021c3  jz      short loc_180002179
0x1800021c5  mov     rcx, [rcx+10h]
0x1800021c9  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x1800021d0  mov     edx, 1Ah
0x1800021d5  mov     r9d, ebx
0x1800021d8  call    WPP_SF_d
0x1800021dd  jmp     short loc_180002179
```
