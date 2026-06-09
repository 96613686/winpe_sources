# windiag::lua_exec_state_t::thread_cpu_time_100ns(uint,void *)

- ea: `0x1800791f8`
- end: `0x180079284`
- name: `?thread_cpu_time_100ns@lua_exec_state_t@windiag@@SA_JIPEAX@Z`
- size: `140`
- prototype: `__int64 __fastcall(DWORD dwThreadId, HANDLE hObject)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18007917c`
- `0x18008fe78`

## callees

- `0x1800791f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180079219`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180079219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079273`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079273`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x180079257`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadTimes` at `0x180079257`

## pseudocode

```c
__int64 __fastcall windiag::lua_exec_state_t::thread_cpu_time_100ns(DWORD dwThreadId, HANDLE hObject)
{
  __int64 v2; // rsi
  HANDLE v4; // rbx
  struct _FILETIME CreationTime; // [rsp+30h] [rbp-28h] BYREF
  struct _FILETIME KernelTime; // [rsp+68h] [rbp+10h] BYREF
  struct _FILETIME UserTime; // [rsp+70h] [rbp+18h] BYREF
  struct _FILETIME ExitTime; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  if ( hObject )
  {
    v4 = hObject;
  }
  else
  {
    v4 = OpenThread(0x800u, 0, dwThreadId);
    if ( !v4 )
      return v2;
  }
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  if ( GetThreadTimes(v4, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
    v2 = *(_QWORD *)&KernelTime + *(_QWORD *)&UserTime;
  if ( v4 != hObject )
    CloseHandle(v4);
  return v2;
}

```

## disassembly

```asm
0x1800791f8  push    rbx
0x1800791fa  push    rsi
0x1800791fb  push    rdi
0x1800791fc  sub     rsp, 40h
0x180079200  xor     esi, esi
0x180079202  mov     rdi, rdx
0x180079205  test    rdx, rdx
0x180079208  jz      short loc_18007920F
0x18007920a  mov     rbx, rdx
0x18007920d  jmp     short loc_180079227
0x18007920f  mov     r8d, ecx; dwThreadId
0x180079212  xor     edx, edx; bInheritHandle
0x180079214  mov     ecx, 800h; dwDesiredAccess
0x180079219  call    cs:__imp_OpenThread
0x18007921f  mov     rbx, rax
0x180079222  test    rax, rax
0x180079225  jz      short loc_180079279
0x180079227  lea     rax, [rsp+58h+UserTime]
0x18007922c  mov     qword ptr [rsp+58h+CreationTime.dwLowDateTime], rsi
0x180079231  lea     r9, [rsp+58h+KernelTime]; lpKernelTime
0x180079236  mov     [rsp+58h+lpUserTime], rax; lpUserTime
0x18007923b  lea     r8, [rsp+58h+ExitTime]; lpExitTime
0x180079240  mov     qword ptr [rsp+58h+ExitTime.dwLowDateTime], rsi
0x180079245  lea     rdx, [rsp+58h+CreationTime]; lpCreationTime
0x18007924a  mov     qword ptr [rsp+58h+KernelTime.dwLowDateTime], rsi
0x18007924f  mov     rcx, rbx; hThread
0x180079252  mov     qword ptr [rsp+58h+UserTime.dwLowDateTime], rsi
0x180079257  call    cs:__imp_GetThreadTimes
0x18007925d  test    eax, eax
0x18007925f  jz      short loc_18007926B
0x180079261  mov     rsi, qword ptr [rsp+58h+UserTime.dwLowDateTime]
0x180079266  add     rsi, qword ptr [rsp+58h+KernelTime.dwLowDateTime]
0x18007926b  cmp     rbx, rdi
0x18007926e  jz      short loc_180079279
0x180079270  mov     rcx, rbx; hObject
0x180079273  call    cs:__imp_CloseHandle
0x180079279  mov     rax, rsi
0x18007927c  add     rsp, 40h
0x180079280  pop     rdi
0x180079281  pop     rsi
0x180079282  pop     rbx
0x180079283  retn
```
