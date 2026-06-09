# StartAddress

- ea: `0x1800344f0`
- end: `0x18003455c`
- name: `StartAddress`
- size: `108`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800313f0`
- `0x180033f08`
- `0x1800344f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18003454a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18003454a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034519`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034519`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180034524`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180034524`

## pseudocode

```c
__int64 __fastcall StartAddress(_QWORD *Parameter)
{
  __int64 v1; // r14
  __int64 (__fastcall *v3)(__int64); // rbp
  HMODULE v4; // rdi
  int v5; // esi
  HANDLE CurrentThread; // rax
  __int64 result; // rax

  v1 = Parameter[2];
  v3 = (__int64 (__fastcall *)(__int64))Parameter[1];
  v4 = (HMODULE)Parameter[3];
  Parameter[3] = 0;
  v5 = *((_DWORD *)Parameter + 8);
  if ( v5 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v5);
  }
  sub_180033F08(Parameter);
  result = v3(v1);
  if ( v4 )
    FreeLibraryAndExitThread(v4, result);
  return result;
}

```

## disassembly

```asm
0x1800344f0  push    rbx
0x1800344f2  push    rbp
0x1800344f3  push    rsi
0x1800344f4  push    rdi
0x1800344f5  push    r14
0x1800344f7  sub     rsp, 20h
0x1800344fb  mov     r14, [rcx+10h]
0x1800344ff  mov     rbx, rcx
0x180034502  mov     rbp, [rcx+8]
0x180034506  mov     rdi, [rcx+18h]
0x18003450a  mov     qword ptr [rcx+18h], 0
0x180034512  mov     esi, [rcx+20h]
0x180034515  test    esi, esi
0x180034517  jz      short loc_18003452A
0x180034519  call    cs:GetCurrentThread
0x18003451f  mov     rcx, rax; hThread
0x180034522  mov     edx, esi; nPriority
0x180034524  call    cs:SetThreadPriority
0x18003452a  mov     rcx, rbx
0x18003452d  call    sub_180033F08
0x180034532  mov     rcx, rbp
0x180034535  call    cs:__guard_check_icall_fptr
0x18003453b  mov     rcx, r14
0x18003453e  call    rbp
0x180034540  test    rdi, rdi
0x180034543  jz      short loc_180034551
0x180034545  mov     edx, eax; dwExitCode
0x180034547  mov     rcx, rdi; hLibModule
0x18003454a  call    cs:FreeLibraryAndExitThread
0x180034550  int     3; Trap to Debugger
0x180034551  add     rsp, 20h
0x180034555  pop     r14
0x180034557  pop     rdi
0x180034558  pop     rsi
0x180034559  pop     rbp
0x18003455a  pop     rbx
0x18003455b  retn
```
