# WUComTimeout::ComTimeout::SetTimer(ulong)

- ea: `0x18003170c`
- end: `0x1800317a3`
- name: `?SetTimer@ComTimeout@WUComTimeout@@QEAAJK@Z`
- size: `151`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800236c4`
- `0x18002e66c`

## callees

- `0x180003974`
- `0x18003170c`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003174a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003174a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031788`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031734`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180031734`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180031726`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180031726`

## string_xrefs

- `0x18003175d`: `C:\__w\1\s\src\Client\lib\util\ComTimeout.cpp`

## pseudocode

```c
__int64 __fastcall WUComTimeout::ComTimeout::SetTimer(_BYTE *pv)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  const char *v3; // r9
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( CoEnableCallCancellation(0) >= 0 )
  {
    pv[12] = 1;
    *((_DWORD *)pv + 2) = GetCurrentThreadId();
    ThreadpoolTimer = CreateThreadpoolTimer(WUComTimeout::ComTimeout::s_TimerCallback, pv, 0);
    *(_QWORD *)pv = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x2B,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\ComTimeout.cpp",
               v3);
    pftDueTime = (struct _FILETIME)-300000000LL;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x3E8u, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18003170c  push    rbx
0x18003170e  sub     rsp, 30h
0x180031712  mov     rax, cs:__security_cookie
0x180031719  xor     rax, rsp
0x18003171c  mov     [rsp+38h+var_10], rax
0x180031721  mov     rbx, rcx
0x180031724  xor     ecx, ecx; pReserved
0x180031726  call    cs:__imp_CoEnableCallCancellation
0x18003172c  test    eax, eax
0x18003172e  js      short loc_18003178E
0x180031730  mov     byte ptr [rbx+0Ch], 1
0x180031734  call    cs:__imp_GetCurrentThreadId
0x18003173a  xor     r8d, r8d; pcbe
0x18003173d  lea     rcx, ?s_TimerCallback@ComTimeout@WUComTimeout@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180031744  mov     rdx, rbx; pv
0x180031747  mov     [rbx+8], eax
0x18003174a  call    cs:__imp_CreateThreadpoolTimer
0x180031750  mov     [rbx], rax
0x180031753  test    rax, rax
0x180031756  jnz     short loc_18003176E
0x180031758  mov     rcx, [rsp+38h]; this
0x18003175d  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180031764  lea     edx, [rax+2Bh]; void *
0x180031767  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003176c  jmp     short loc_180031790
0x18003176e  xor     r9d, r9d; msWindowLength
0x180031771  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x18003177a  mov     r8d, 3E8h; msPeriod
0x180031780  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180031785  mov     rcx, rax; pti
0x180031788  call    cs:__imp_SetThreadpoolTimer
0x18003178e  xor     eax, eax
0x180031790  mov     rcx, [rsp+38h+var_10]
0x180031795  xor     rcx, rsp; StackCookie
0x180031798  call    __security_check_cookie
0x18003179d  add     rsp, 30h
0x1800317a1  pop     rbx
0x1800317a2  retn
```
