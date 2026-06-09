# StartAddress

- ea: `0x18000fc40`
- end: `0x18000fcac`
- name: `StartAddress`
- size: `108`
- prototype: `__int64 __fastcall(_QWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000bae0`
- `0x18000eeb0`
- `0x18000fc40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000fc9a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000fc9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fc69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fc69`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000fc74`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000fc74`

## pseudocode

```c
__int64 __fastcall StartAddress(_QWORD *lpThreadParameter)
{
  __int64 v1; // r14
  __int64 (__fastcall *v3)(__int64); // rbp
  HMODULE v4; // rdi
  int v5; // esi
  HANDLE CurrentThread; // rax
  __int64 result; // rax

  v1 = lpThreadParameter[2];
  v3 = (__int64 (__fastcall *)(__int64))lpThreadParameter[1];
  v4 = (HMODULE)lpThreadParameter[3];
  lpThreadParameter[3] = 0;
  v5 = *((_DWORD *)lpThreadParameter + 8);
  if ( v5 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v5);
  }
  sub_18000BAE0(lpThreadParameter);
  result = v3(v1);
  if ( v4 )
    FreeLibraryAndExitThread(v4, result);
  return result;
}

```

## disassembly

```asm
0x18000fc40  push    rbx
0x18000fc42  push    rbp
0x18000fc43  push    rsi
0x18000fc44  push    rdi
0x18000fc45  push    r14
0x18000fc47  sub     rsp, 20h
0x18000fc4b  mov     r14, [rcx+10h]
0x18000fc4f  mov     rbx, rcx
0x18000fc52  mov     rbp, [rcx+8]
0x18000fc56  mov     rdi, [rcx+18h]
0x18000fc5a  mov     qword ptr [rcx+18h], 0
0x18000fc62  mov     esi, [rcx+20h]
0x18000fc65  test    esi, esi
0x18000fc67  jz      short loc_18000FC7A
0x18000fc69  call    cs:GetCurrentThread
0x18000fc6f  mov     rcx, rax; hThread
0x18000fc72  mov     edx, esi; nPriority
0x18000fc74  call    cs:SetThreadPriority
0x18000fc7a  mov     rcx, rbx
0x18000fc7d  call    sub_18000BAE0
0x18000fc82  mov     rcx, rbp
0x18000fc85  call    cs:__guard_check_icall_fptr
0x18000fc8b  mov     rcx, r14
0x18000fc8e  call    rbp
0x18000fc90  test    rdi, rdi
0x18000fc93  jz      short loc_18000FCA1
0x18000fc95  mov     edx, eax; dwExitCode
0x18000fc97  mov     rcx, rdi; hLibModule
0x18000fc9a  call    cs:FreeLibraryAndExitThread
0x18000fca0  int     3; Trap to Debugger
0x18000fca1  add     rsp, 20h
0x18000fca5  pop     r14
0x18000fca7  pop     rdi
0x18000fca8  pop     rsi
0x18000fca9  pop     rbp
0x18000fcaa  pop     rbx
0x18000fcab  retn
```
