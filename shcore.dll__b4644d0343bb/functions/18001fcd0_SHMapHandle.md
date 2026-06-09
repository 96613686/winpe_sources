# SHMapHandle

- ea: `0x18001fcd0`
- end: `0x18001fdc7`
- name: `SHMapHandle`
- size: `247`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, unsigned int, unsigned int, DWORD dwDesiredAccess, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001fe5c`

## callees

- `0x18001fcd0`
- `0x18002009c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fcff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001fcff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fd0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fd26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fd0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fd26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fd9a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001fd5d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001fd5d`

## pseudocode

```c
HANDLE __fastcall SHMapHandle(HANDLE hSourceHandle, DWORD a2, DWORD a3, DWORD dwDesiredAccess, int a5)
{
  __int64 v9; // rdx
  __int64 v10; // rcx
  DWORD CurrentProcessId; // ebx
  HANDLE v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  void *v15; // rdi
  HANDLE CurrentProcess; // rax
  void *v17; // rsi
  HANDLE TargetHandle; // [rsp+70h] [rbp+8h] BYREF

  TargetHandle = 0;
  if ( hSourceHandle )
  {
    CurrentProcessId = GetCurrentProcessId();
    v12 = a2 == CurrentProcessId ? GetCurrentProcess() : OpenProcessLocal(v10, v9, a2);
    v15 = v12;
    if ( v12 )
    {
      if ( a3 == CurrentProcessId )
        CurrentProcess = GetCurrentProcess();
      else
        CurrentProcess = OpenProcessLocal(v14, v13, a3);
      v17 = CurrentProcess;
      if ( CurrentProcess )
      {
        if ( !DuplicateHandle(v15, hSourceHandle, CurrentProcess, &TargetHandle, dwDesiredAccess, 0, a5 | 2) )
          TargetHandle = 0;
        if ( a3 != CurrentProcessId )
          CloseHandle(v17);
      }
      if ( a2 != CurrentProcessId )
        CloseHandle(v15);
    }
  }
  return TargetHandle;
}

```

## disassembly

```asm
0x18001fcd0  mov     [rsp+arg_8], rbx
0x18001fcd5  mov     [rsp+arg_10], rbp
0x18001fcda  push    rsi
0x18001fcdb  push    rdi
0x18001fcdc  push    r12
0x18001fcde  push    r14
0x18001fce0  push    r15
0x18001fce2  sub     rsp, 40h
0x18001fce6  mov     [rsp+68h+TargetHandle], 0
0x18001fcef  mov     r12d, r9d
0x18001fcf2  mov     r14d, r8d
0x18001fcf5  mov     ebp, edx
0x18001fcf7  mov     r15, rcx
0x18001fcfa  test    rcx, rcx
0x18001fcfd  jz      short loc_18001FD79
0x18001fcff  call    cs:__imp_GetCurrentProcessId
0x18001fd05  mov     ebx, eax
0x18001fd07  cmp     ebp, eax
0x18001fd09  jnz     loc_18001FDA2
0x18001fd0f  call    cs:__imp_GetCurrentProcess
0x18001fd15  mov     rdi, rax
0x18001fd18  test    rax, rax
0x18001fd1b  jz      short loc_18001FD79
0x18001fd1d  cmp     r14d, ebx
0x18001fd20  jnz     loc_18001FDAF
0x18001fd26  call    cs:__imp_GetCurrentProcess
0x18001fd2c  mov     rsi, rax
0x18001fd2f  test    rax, rax
0x18001fd32  jz      short loc_18001FD6C
0x18001fd34  mov     eax, [rsp+68h+arg_20]
0x18001fd3b  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18001fd40  or      eax, 2
0x18001fd43  mov     r8, rsi; hTargetProcessHandle
0x18001fd46  mov     [rsp+68h+dwOptions], eax; dwOptions
0x18001fd4a  mov     rdx, r15; hSourceHandle
0x18001fd4d  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18001fd55  mov     rcx, rdi; hSourceProcessHandle
0x18001fd58  mov     [rsp+68h+dwDesiredAccess], r12d; dwDesiredAccess
0x18001fd5d  call    cs:__imp_DuplicateHandle
0x18001fd63  test    eax, eax
0x18001fd65  jz      short loc_18001FDBC
0x18001fd67  cmp     r14d, ebx
0x18001fd6a  jnz     short loc_18001FD97
0x18001fd6c  cmp     ebp, ebx
0x18001fd6e  jz      short loc_18001FD79
0x18001fd70  mov     rcx, rdi; hObject
0x18001fd73  call    cs:__imp_CloseHandle
0x18001fd79  mov     rax, [rsp+68h+TargetHandle]
0x18001fd7e  lea     r11, [rsp+68h+var_28]
0x18001fd83  mov     rbx, [r11+38h]
0x18001fd87  mov     rbp, [r11+40h]
0x18001fd8b  mov     rsp, r11
0x18001fd8e  pop     r15
0x18001fd90  pop     r14
0x18001fd92  pop     r12
0x18001fd94  pop     rdi
0x18001fd95  pop     rsi
0x18001fd96  retn
0x18001fd97  mov     rcx, rsi; hObject
0x18001fd9a  call    cs:__imp_CloseHandle
0x18001fda0  jmp     short loc_18001FD6C
0x18001fda2  mov     r8d, ebp; unsigned int
0x18001fda5  call    ?OpenProcessLocal@@YAPEAXKHK@Z; OpenProcessLocal(ulong,int,ulong)
0x18001fdaa  jmp     loc_18001FD15
0x18001fdaf  mov     r8d, r14d; unsigned int
0x18001fdb2  call    ?OpenProcessLocal@@YAPEAXKHK@Z; OpenProcessLocal(ulong,int,ulong)
0x18001fdb7  jmp     loc_18001FD2C
0x18001fdbc  mov     [rsp+68h+TargetHandle], 0
0x18001fdc5  jmp     short loc_18001FD67
```
