# SecondaryLogonCleanupJob

- ea: `0x180002d80`
- end: `0x180002f61`
- name: `SecondaryLogonCleanupJob`
- size: `481`
- prototype: `void __fastcall(int, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002570`
- `0x1800030c0`

## callees

- `0x180002d80`
- `0x180002f70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ead`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ead`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ebb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ebb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ecd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ecd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ef4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ef4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f16`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002e80`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002e80`
- `USERENV!UnloadUserProfile` at `0x180002f07`
- `USERENV!UnloadUserProfile` at `0x180002f07`

## pseudocode

```c
void __fastcall SecondaryLogonCleanupJob(int a1, __int64 a2, _DWORD *a3)
{
  void *v6; // rcx
  void *v7; // rdx
  void *v8; // rcx
  void *v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rdx
  int v12; // eax
  HANDLE ProcessHeap; // rax
  bool v14; // zf

  if ( a1 == 1 )
    EnterCriticalSection(&csForProcessCount);
  if ( *(_QWORD *)a2 )
  {
    CloseHandle(*(HANDLE *)a2);
    *(_QWORD *)a2 = 0;
  }
  v6 = *(void **)(a2 + 8);
  if ( v6 )
  {
    CloseHandle(v6);
    *(_QWORD *)(a2 + 8) = 0;
  }
  v7 = *(void **)(a2 + 24);
  if ( v7 )
  {
    UnloadUserProfile(*(HANDLE *)(a2 + 16), v7);
    *(_QWORD *)(a2 + 24) = 0;
  }
  v8 = *(void **)(a2 + 16);
  if ( v8 )
  {
    CloseHandle(v8);
    *(_QWORD *)(a2 + 16) = 0;
  }
  v9 = *(void **)(a2 + 40);
  if ( v9 )
  {
    Free_SECONDARYLOGONINFOW(v9);
    *(_QWORD *)(a2 + 40) = 0;
  }
  v10 = *(_QWORD *)(a2 + 48);
  if ( *(_QWORD *)(v10 + 8) != a2 + 48 || (v11 = *(_QWORD **)(a2 + 56), *v11 != a2 + 48) )
    __fastfail(3u);
  *v11 = v10;
  *(_QWORD *)(v10 + 8) = v11;
  if ( *(_DWORD *)(a2 + 64) )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)a2);
  }
  if ( (__int128 *)xmmword_1800096E0 == &xmmword_1800096E0 )
  {
    *a3 = 1;
LABEL_19:
    v12 = 0;
    goto LABEL_20;
  }
  v14 = g_fCleanupThreadActive == 0;
  v12 = 1;
  *a3 = 0;
  if ( v14 )
    goto LABEL_19;
LABEL_20:
  g_fCleanupThreadActive = v12;
  EnterCriticalSection(&csForProcessCount);
  g_state.dwServiceType = 32;
  g_state.dwCurrentState = 4;
  g_state.dwControlsAccepted = ((_QWORD)xmmword_1800096E0 == (_QWORD)&xmmword_1800096E0) + 130;
  g_state.dwWin32ExitCode = 0;
  *(_QWORD *)&g_state.dwCheckPoint = 0;
  if ( !SetServiceStatus(hServiceStatus, &g_state) )
    GetLastError();
  LeaveCriticalSection(&csForProcessCount);
  if ( a1 == 1 )
    LeaveCriticalSection(&csForProcessCount);
}

```

## disassembly

```asm
0x180002d80  push    rbx
0x180002d82  push    rbp
0x180002d83  push    rsi
0x180002d84  push    rdi
0x180002d85  sub     rsp, 28h
0x180002d89  mov     rsi, r8
0x180002d8c  mov     rbx, rdx
0x180002d8f  mov     edi, ecx
0x180002d91  cmp     ecx, 1
0x180002d94  jz      loc_180002EC6
0x180002d9a  mov     rcx, [rbx]; hObject
0x180002d9d  xor     ebp, ebp
0x180002d9f  test    rcx, rcx
0x180002da2  jnz     loc_180002EE6
0x180002da8  mov     rcx, [rbx+8]; hObject
0x180002dac  test    rcx, rcx
0x180002daf  jnz     loc_180002EF4
0x180002db5  mov     rdx, [rbx+18h]; hProfile
0x180002db9  test    rdx, rdx
0x180002dbc  jnz     loc_180002F03
0x180002dc2  mov     rcx, [rbx+10h]; hObject
0x180002dc6  test    rcx, rcx
0x180002dc9  jnz     loc_180002F16
0x180002dcf  mov     rcx, [rbx+28h]; lpMem
0x180002dd3  test    rcx, rcx
0x180002dd6  jnz     loc_180002ED8
0x180002ddc  mov     rcx, [rbx+30h]
0x180002de0  lea     rax, [rbx+30h]
0x180002de4  cmp     [rcx+8], rax
0x180002de8  jnz     loc_180002F5A
0x180002dee  mov     rdx, [rax+8]
0x180002df2  cmp     [rdx], rax
0x180002df5  jnz     loc_180002F5A
0x180002dfb  mov     [rdx], rcx
0x180002dfe  mov     [rcx+8], rdx
0x180002e02  cmp     [rbx+40h], ebp
0x180002e05  jnz     loc_180002EAD
0x180002e0b  lea     rbx, xmmword_1800096E0
0x180002e12  cmp     qword ptr cs:xmmword_1800096E0, rbx
0x180002e19  jnz     loc_180002F25
0x180002e1f  mov     dword ptr [rsi], 1
0x180002e25  mov     eax, ebp
0x180002e27  lea     rcx, csForProcessCount; lpCriticalSection
0x180002e2e  mov     cs:g_fCleanupThreadActive, eax
0x180002e34  call    cs:__imp_EnterCriticalSection
0x180002e3a  cmp     qword ptr cs:xmmword_1800096E0, rbx
0x180002e41  lea     rdx, g_state; lpServiceStatus
0x180002e48  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x180002e4f  mov     eax, ebp
0x180002e51  setz    al
0x180002e54  mov     cs:g_state.dwServiceType, 20h ; ' '
0x180002e5e  add     eax, 82h
0x180002e63  mov     cs:g_state.dwCurrentState, 4
0x180002e6d  mov     cs:g_state.dwControlsAccepted, eax
0x180002e73  mov     cs:g_state.dwWin32ExitCode, ebp
0x180002e79  mov     qword ptr cs:g_state.dwCheckPoint, rbp
0x180002e80  call    cs:__imp_SetServiceStatus
0x180002e86  test    eax, eax
0x180002e88  jz      loc_180002F3D
0x180002e8e  lea     rcx, csForProcessCount; lpCriticalSection
0x180002e95  call    cs:__imp_LeaveCriticalSection
0x180002e9b  cmp     edi, 1
0x180002e9e  jz      loc_180002F48
0x180002ea4  add     rsp, 28h
0x180002ea8  pop     rdi
0x180002ea9  pop     rsi
0x180002eaa  pop     rbp
0x180002eab  pop     rbx
0x180002eac  retn
0x180002ead  call    cs:__imp_GetProcessHeap
0x180002eb3  mov     r8, rbx; lpMem
0x180002eb6  xor     edx, edx; dwFlags
0x180002eb8  mov     rcx, rax; hHeap
0x180002ebb  call    cs:__imp_HeapFree
0x180002ec1  jmp     loc_180002E0B
0x180002ec6  lea     rcx, csForProcessCount; lpCriticalSection
0x180002ecd  call    cs:__imp_EnterCriticalSection
0x180002ed3  jmp     loc_180002D9A
0x180002ed8  call    Free_SECONDARYLOGONINFOW
0x180002edd  mov     [rbx+28h], rbp
0x180002ee1  jmp     loc_180002DDC
0x180002ee6  call    cs:__imp_CloseHandle
0x180002eec  mov     [rbx], rbp
0x180002eef  jmp     loc_180002DA8
0x180002ef4  call    cs:__imp_CloseHandle
0x180002efa  mov     [rbx+8], rbp
0x180002efe  jmp     loc_180002DB5
0x180002f03  mov     rcx, [rbx+10h]; hToken
0x180002f07  call    cs:__imp_UnloadUserProfile
0x180002f0d  mov     [rbx+18h], rbp
0x180002f11  jmp     loc_180002DC2
0x180002f16  call    cs:__imp_CloseHandle
0x180002f1c  mov     [rbx+10h], rbp
0x180002f20  jmp     loc_180002DCF
0x180002f25  cmp     cs:g_fCleanupThreadActive, ebp
0x180002f2b  mov     eax, 1
0x180002f30  mov     [rsi], ebp
0x180002f32  jnz     loc_180002E27
0x180002f38  jmp     loc_180002E25
0x180002f3d  call    cs:__imp_GetLastError
0x180002f43  jmp     loc_180002E8E
0x180002f48  lea     rcx, csForProcessCount; lpCriticalSection
0x180002f4f  call    cs:__imp_LeaveCriticalSection
0x180002f55  jmp     loc_180002EA4
0x180002f5a  mov     ecx, 3
0x180002f5f  int     29h; Win8: RtlFailFast(ecx)
```
