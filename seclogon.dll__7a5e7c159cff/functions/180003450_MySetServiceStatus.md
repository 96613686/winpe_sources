# MySetServiceStatus

- ea: `0x180003450`
- end: `0x180003550`
- name: `MySetServiceStatus`
- size: `256`
- prototype: `__int64 __fastcall(DWORD, DWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180002570`
- `0x180002fd0`
- `0x180003150`
- `0x1800042d4`

## callees

- `0x180003450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000352c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000352c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000346a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000346a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800034da`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800034c7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800034c7`

## pseudocode

```c
__int64 __fastcall MySetServiceStatus(DWORD a1, DWORD a2)
{
  DWORD v4; // ecx
  DWORD v5; // edx
  DWORD LastError; // ebx

  EnterCriticalSection(&csForProcessCount);
  if ( (__int128 *)xmmword_1800096E0 == &xmmword_1800096E0 )
  {
    v4 = 131;
    v5 = 129;
  }
  else
  {
    v4 = 130;
    v5 = 128;
  }
  g_state.dwServiceType = 32;
  g_state.dwCurrentState = a1;
  if ( a1 == 7 )
  {
LABEL_4:
    g_state.dwControlsAccepted = v4;
  }
  else
  {
    switch ( a1 )
    {
      case 1u:
      case 3u:
        g_state.dwControlsAccepted = 0;
        break;
      case 2u:
      case 5u:
      case 6u:
        g_state.dwControlsAccepted = v5;
        break;
      case 4u:
        goto LABEL_4;
      default:
        break;
    }
  }
  g_state.dwWin32ExitCode = 0;
  g_state.dwCheckPoint = a2;
  g_state.dwWaitHint = 0;
  if ( SetServiceStatus(hServiceStatus, &g_state) )
    LastError = 0;
  else
    LastError = GetLastError();
  LeaveCriticalSection(&csForProcessCount);
  return LastError;
}

```

## disassembly

```asm
0x180003450  mov     [rsp+arg_0], rbx
0x180003455  mov     [rsp+arg_8], rsi
0x18000345a  push    rdi
0x18000345b  sub     rsp, 20h
0x18000345f  mov     ebx, ecx
0x180003461  mov     edi, edx
0x180003463  lea     rcx, csForProcessCount; lpCriticalSection
0x18000346a  call    cs:__imp_EnterCriticalSection
0x180003470  lea     rax, xmmword_1800096E0
0x180003477  cmp     qword ptr cs:xmmword_1800096E0, rax
0x18000347e  jnz     short loc_1800034F2
0x180003480  mov     ecx, 83h
0x180003485  mov     edx, 81h
0x18000348a  xor     esi, esi
0x18000348c  mov     cs:g_state.dwServiceType, 20h ; ' '
0x180003496  mov     cs:g_state.dwCurrentState, ebx
0x18000349c  cmp     ebx, 7
0x18000349f  jnz     short loc_1800034FE
0x1800034a1  mov     cs:g_state.dwControlsAccepted, ecx; jumptable 0000000180003517 case 4
0x1800034a7  mov     rcx, qword ptr cs:hServiceStatus; jumptable 0000000180003517 default case
0x1800034ae  lea     rdx, g_state; lpServiceStatus
0x1800034b5  mov     cs:g_state.dwWin32ExitCode, esi
0x1800034bb  mov     cs:g_state.dwCheckPoint, edi
0x1800034c1  mov     cs:g_state.dwWaitHint, esi
0x1800034c7  call    cs:__imp_SetServiceStatus
0x1800034cd  test    eax, eax
0x1800034cf  jz      short loc_18000352C
0x1800034d1  mov     ebx, esi
0x1800034d3  lea     rcx, csForProcessCount; lpCriticalSection
0x1800034da  call    cs:__imp_LeaveCriticalSection
0x1800034e0  mov     rsi, [rsp+28h+arg_8]
0x1800034e5  mov     eax, ebx
0x1800034e7  mov     rbx, [rsp+28h+arg_0]
0x1800034ec  add     rsp, 20h
0x1800034f0  pop     rdi
0x1800034f1  retn
0x1800034f2  mov     ecx, 82h
0x1800034f7  mov     edx, 80h
0x1800034fc  jmp     short loc_18000348A
0x1800034fe  dec     ebx; switch 6 cases
0x180003500  cmp     ebx, 5
0x180003503  ja      short def_180003517; jumptable 0000000180003517 default case
0x180003505  lea     r8, __ImageBase
0x18000350c  mov     eax, ds:(jpt_180003517 - 180000000h)[r8+rbx*4]
0x180003514  add     rax, r8
0x180003517  jmp     rax; switch jump
0x180003519  mov     cs:g_state.dwControlsAccepted, esi; jumptable 0000000180003517 cases 1,3
0x18000351f  jmp     short def_180003517; jumptable 0000000180003517 default case
0x180003521  mov     cs:g_state.dwControlsAccepted, edx; jumptable 0000000180003517 cases 2,5,6
0x180003527  jmp     def_180003517; jumptable 0000000180003517 default case
0x18000352c  call    cs:__imp_GetLastError
0x180003532  mov     ebx, eax
0x180003534  jmp     short loc_1800034D3
```
