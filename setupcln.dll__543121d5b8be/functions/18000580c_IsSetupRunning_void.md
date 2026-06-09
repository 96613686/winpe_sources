# IsSetupRunning(void)

- ea: `0x18000580c`
- end: `0x18000591b`
- name: `?IsSetupRunning@@YAHXZ`
- size: `271`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005b50`

## callees

- `0x1800047ac`
- `0x18000580c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000583b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000585c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000587d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000583b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000585c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000587d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005895`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180005830`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180005851`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180005872`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180005830`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180005851`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180005872`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000588f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000588f`
- `WDSCORE!CurrentIP` at `0x18000589d`
- `WDSCORE!CurrentIP` at `0x18000589d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005903`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005903`

## pseudocode

```c
_BOOL8 IsSetupRunning(void)
{
  BOOL v0; // esi
  HANDLE v1; // rax
  DWORD LastError; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax

  v0 = 1;
  v1 = OpenMutexW(0x80000000, 0, L"Global\\Microsoft.Windows.Setup");
  if ( v1 )
    goto LABEL_7;
  if ( GetLastError() == 2 )
  {
    v1 = OpenMutexW(0x80000000, 0, L"Global\\Microsoft.Windows.Setup");
    if ( v1 )
      goto LABEL_7;
    if ( GetLastError() == 2 )
    {
      v1 = OpenMutexW(0x80000000, 0, L"Microsoft.Windows.Setup.Local");
      if ( !v1 )
      {
        v0 = GetLastError() != 2;
        goto LABEL_8;
      }
LABEL_7:
      CloseHandle(v1);
    }
  }
LABEL_8:
  LastError = GetLastError();
  v3 = CurrentIP();
  v4 = ConstructPartialMsgW(0x4000000, "IsSetupRunning - Setup Running: %x", v0);
  WdsSetupLogMessageW(
    v4,
    0,
    L"D",
    0,
    1252,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"IsSetupRunning",
    v3,
    LastError,
    0,
    0);
  return v0;
}

```

## disassembly

```asm
0x18000580c  mov     [rsp+arg_0], rbx
0x180005811  mov     [rsp+arg_8], rsi
0x180005816  push    rdi
0x180005817  sub     rsp, 60h
0x18000581b  mov     ebx, 80000000h
0x180005820  lea     r8, aGlobalMicrosof; "Global\\Microsoft.Windows.Setup"
0x180005827  mov     ecx, ebx; dwDesiredAccess
0x180005829  xor     edx, edx; bInheritHandle
0x18000582b  mov     esi, 1
0x180005830  call    cs:__imp_OpenMutexW
0x180005836  test    rax, rax
0x180005839  jnz     short loc_18000588C
0x18000583b  call    cs:__imp_GetLastError
0x180005841  cmp     eax, 2
0x180005844  jnz     short loc_180005895
0x180005846  lea     r8, aGlobalMicrosof; "Global\\Microsoft.Windows.Setup"
0x18000584d  xor     edx, edx; bInheritHandle
0x18000584f  mov     ecx, ebx; dwDesiredAccess
0x180005851  call    cs:__imp_OpenMutexW
0x180005857  test    rax, rax
0x18000585a  jnz     short loc_18000588C
0x18000585c  call    cs:__imp_GetLastError
0x180005862  cmp     eax, 2
0x180005865  jnz     short loc_180005895
0x180005867  lea     r8, aMicrosoftWindo; "Microsoft.Windows.Setup.Local"
0x18000586e  xor     edx, edx; bInheritHandle
0x180005870  mov     ecx, ebx; dwDesiredAccess
0x180005872  call    cs:__imp_OpenMutexW
0x180005878  test    rax, rax
0x18000587b  jnz     short loc_18000588C
0x18000587d  call    cs:__imp_GetLastError
0x180005883  cmp     eax, 2
0x180005886  jnz     short loc_180005895
0x180005888  xor     esi, esi
0x18000588a  jmp     short loc_180005895
0x18000588c  mov     rcx, rax; hObject
0x18000588f  call    cs:__imp_CloseHandle
0x180005895  call    cs:__imp_GetLastError
0x18000589b  mov     edi, eax
0x18000589d  call    cs:__imp_CurrentIP
0x1800058a3  mov     r8d, esi
0x1800058a6  lea     rdx, aIssetuprunning; "IsSetupRunning - Setup Running: %x"
0x1800058ad  mov     ecx, 4000000h; unsigned int
0x1800058b2  mov     rbx, rax
0x1800058b5  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800058ba  mov     [rsp+68h+var_18], 0
0x1800058c2  lea     rcx, aIssetuprunning_0; "IsSetupRunning"
0x1800058c9  mov     [rsp+68h+var_20], 0
0x1800058d2  lea     r8, aD; "D"
0x1800058d9  mov     [rsp+68h+var_28], edi
0x1800058dd  xor     r9d, r9d
0x1800058e0  mov     [rsp+68h+var_30], rbx
0x1800058e5  xor     edx, edx
0x1800058e7  mov     [rsp+68h+var_38], rcx
0x1800058ec  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x1800058f3  mov     [rsp+68h+var_40], rcx
0x1800058f8  mov     rcx, rax
0x1800058fb  mov     [rsp+68h+var_48], 4E4h
0x180005903  call    cs:__imp_WdsSetupLogMessageW
0x180005909  mov     rbx, [rsp+68h+arg_0]
0x18000590e  mov     eax, esi
0x180005910  mov     rsi, [rsp+68h+arg_8]
0x180005915  add     rsp, 60h
0x180005919  pop     rdi
0x18000591a  retn
```
