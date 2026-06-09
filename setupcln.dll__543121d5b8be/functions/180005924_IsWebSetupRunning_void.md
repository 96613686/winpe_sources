# IsWebSetupRunning(void)

- ea: `0x180005924`
- end: `0x1800059ef`
- name: `?IsWebSetupRunning@@YAHXZ`
- size: `203`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005b50`

## callees

- `0x1800047ac`
- `0x180005924`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005969`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180005946`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180005946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005963`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005963`
- `WDSCORE!CurrentIP` at `0x180005971`
- `WDSCORE!CurrentIP` at `0x180005971`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800059d7`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800059d7`

## pseudocode

```c
_BOOL8 IsWebSetupRunning(void)
{
  BOOL v0; // esi
  HANDLE v1; // rax
  DWORD LastError; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax

  v0 = 1;
  v1 = OpenMutexW(0x80000000, 0, L"Global\\Microsoft.Windows.Websetup");
  if ( v1 )
    CloseHandle(v1);
  else
    v0 = GetLastError() != 2;
  LastError = GetLastError();
  v3 = CurrentIP();
  v4 = ConstructPartialMsgW(0x4000000, "IsWebSetupRunning - WebSetup Running: %x", v0);
  WdsSetupLogMessageW(
    v4,
    0,
    L"D",
    0,
    1213,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"IsWebSetupRunning",
    v3,
    LastError,
    0,
    0);
  return v0;
}

```

## disassembly

```asm
0x180005924  mov     [rsp+arg_0], rbx
0x180005929  mov     [rsp+arg_8], rsi
0x18000592e  push    rdi
0x18000592f  sub     rsp, 60h
0x180005933  lea     r8, aGlobalMicrosof_0; "Global\\Microsoft.Windows.Websetup"
0x18000593a  xor     edx, edx; bInheritHandle
0x18000593c  mov     ecx, 80000000h; dwDesiredAccess
0x180005941  mov     esi, 1
0x180005946  call    cs:__imp_OpenMutexW
0x18000594c  test    rax, rax
0x18000594f  jnz     short loc_180005960
0x180005951  call    cs:__imp_GetLastError
0x180005957  cmp     eax, 2
0x18000595a  jnz     short loc_180005969
0x18000595c  xor     esi, esi
0x18000595e  jmp     short loc_180005969
0x180005960  mov     rcx, rax; hObject
0x180005963  call    cs:__imp_CloseHandle
0x180005969  call    cs:__imp_GetLastError
0x18000596f  mov     edi, eax
0x180005971  call    cs:__imp_CurrentIP
0x180005977  mov     r8d, esi
0x18000597a  lea     rdx, aIswebsetuprunn; "IsWebSetupRunning - WebSetup Running: %"...
0x180005981  mov     ecx, 4000000h; unsigned int
0x180005986  mov     rbx, rax
0x180005989  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000598e  mov     [rsp+68h+var_18], 0
0x180005996  lea     rcx, aIswebsetuprunn_0; "IsWebSetupRunning"
0x18000599d  mov     [rsp+68h+var_20], 0
0x1800059a6  lea     r8, aD; "D"
0x1800059ad  mov     [rsp+68h+var_28], edi
0x1800059b1  xor     r9d, r9d
0x1800059b4  mov     [rsp+68h+var_30], rbx
0x1800059b9  xor     edx, edx
0x1800059bb  mov     [rsp+68h+var_38], rcx
0x1800059c0  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x1800059c7  mov     [rsp+68h+var_40], rcx
0x1800059cc  mov     rcx, rax
0x1800059cf  mov     [rsp+68h+var_48], 4BDh
0x1800059d7  call    cs:__imp_WdsSetupLogMessageW
0x1800059dd  mov     rbx, [rsp+68h+arg_0]
0x1800059e2  mov     eax, esi
0x1800059e4  mov     rsi, [rsp+68h+arg_8]
0x1800059e9  add     rsp, 60h
0x1800059ed  pop     rdi
0x1800059ee  retn
```
