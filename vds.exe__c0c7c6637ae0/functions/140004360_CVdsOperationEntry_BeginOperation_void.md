# CVdsOperationEntry::BeginOperation(void)

- ea: `0x140004360`
- end: `0x140004451`
- name: `?BeginOperation@CVdsOperationEntry@@QEAAJXZ`
- size: `241`
- prototype: `signed int __fastcall(CVdsOperationEntry *this)`
- caller_count: `92`
- callee_count: `1`
- tags: ``

## callers

- `0x1400023b0`
- `0x1400037a0`
- `0x140004250`
- `0x140004a80`
- `0x140005b1c`
- `0x14000e920`
- `0x140010b40`
- `0x1400113f0`
- `0x140011aa0`
- `0x140013f50`
- `0x140017ec0`
- `0x140018100`
- `0x140019180`
- `0x140019350`
- `0x140019a10`
- `0x14001a570`
- `0x14001b958`
- `0x14001cb30`
- `0x14001cee0`
- `0x14001d0a0`
- `0x14001d210`
- `0x14001d390`
- `0x14001d530`
- `0x14001dab0`
- `0x14001e6c0`
- `0x14001ec70`
- `0x14001f300`
- `0x14001f450`
- `0x14001fe40`
- `0x140020260`
- `0x140020bb0`
- `0x140020e70`
- `0x1400210b0`
- `0x140021b50`
- `0x140022400`
- `0x140022e80`
- `0x140023320`
- `0x140023470`
- `0x140023620`
- `0x140024b70`
- `0x140025000`
- `0x140026a10`
- `0x140027330`
- `0x140027890`
- `0x140027cd8`
- `0x140027e20`
- `0x1400280d0`
- `0x140028340`
- `0x140029050`
- `0x140029600`

## callees

- `0x140004360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400043e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004436`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400043e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004436`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400043c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400043f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400043c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400043f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400043a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400043a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400043fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400043fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000438e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004440`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000438e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004440`
- `vdsutil!AcquireRundownProtection` at `0x140004370`
- `vdsutil!AcquireRundownProtection` at `0x140004370`

## pseudocode

```c
signed int __fastcall CVdsOperationEntry::BeginOperation(CVdsOperationEntry *this)
{
  bool v2; // zf
  int v3; // eax
  signed int result; // eax

  if ( !(unsigned __int8)AcquireRundownProtection(&g_RundownRef) )
    return -2146959352;
  v2 = *(_DWORD *)this == 0;
  *((_DWORD *)this + 2) = 1;
  if ( v2 )
  {
    if ( g_dwThreadIdExclusiveLock == GetCurrentThreadId() )
      return 1;
    EnterCriticalSection(&g_OpsInFlight);
    v3 = g_lOperationsInFly;
    if ( g_lOperationsInFly )
      goto LABEL_5;
    if ( !WaitForSingleObject(g_hExclusiveOperationSem, 0xFFFFFFFF) )
    {
      v3 = g_lOperationsInFly;
LABEL_5:
      g_lOperationsInFly = v3 + 1;
      LeaveCriticalSection(&g_OpsInFlight);
LABEL_6:
      result = 0;
      *((_DWORD *)this + 1) = 1;
      return result;
    }
    LeaveCriticalSection(&g_OpsInFlight);
  }
  else if ( !WaitForSingleObject(g_hExclusiveOperationSem, 0xFFFFFFFF) )
  {
    g_dwThreadIdExclusiveLock = GetCurrentThreadId();
    goto LABEL_6;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140004360  push    rbx
0x140004362  sub     rsp, 20h
0x140004366  mov     rbx, rcx
0x140004369  lea     rcx, ?g_RundownRef@@3U_RUNDOWN_REF@@A; _RUNDOWN_REF g_RundownRef
0x140004370  call    cs:__imp_AcquireRundownProtection
0x140004376  test    al, al
0x140004378  jz      loc_140004423
0x14000437e  cmp     dword ptr [rbx], 0
0x140004381  mov     dword ptr [rbx+8], 1
0x140004388  jnz     loc_14000442A
0x14000438e  call    cs:__imp_GetCurrentThreadId
0x140004394  mov     ecx, cs:?g_dwThreadIdExclusiveLock@@3KC; ulong volatile g_dwThreadIdExclusiveLock
0x14000439a  cmp     ecx, eax
0x14000439c  jz      short loc_140004410
0x14000439e  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400043a5  call    cs:__imp_EnterCriticalSection
0x1400043ab  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x1400043b1  test    eax, eax
0x1400043b3  jz      short loc_1400043D9
0x1400043b5  inc     eax
0x1400043b7  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400043be  mov     cs:?g_lOperationsInFly@@3JA, eax; long g_lOperationsInFly
0x1400043c4  call    cs:__imp_LeaveCriticalSection
0x1400043ca  xor     eax, eax
0x1400043cc  mov     dword ptr [rbx+4], 1
0x1400043d3  add     rsp, 20h
0x1400043d7  pop     rbx
0x1400043d8  retn
0x1400043d9  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hHandle
0x1400043e0  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1400043e5  call    cs:__imp_WaitForSingleObject
0x1400043eb  test    eax, eax
0x1400043ed  jz      short loc_14000441B
0x1400043ef  lea     rcx, ?g_OpsInFlight@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400043f6  call    cs:__imp_LeaveCriticalSection
0x1400043fc  call    cs:__imp_GetLastError
0x140004402  test    eax, eax
0x140004404  jle     short loc_1400043D3
0x140004406  movzx   eax, ax
0x140004409  or      eax, 80070000h
0x14000440e  jmp     short loc_1400043D3
0x140004410  mov     eax, 1
0x140004415  add     rsp, 20h
0x140004419  pop     rbx
0x14000441a  retn
0x14000441b  mov     eax, cs:?g_lOperationsInFly@@3JA; long g_lOperationsInFly
0x140004421  jmp     short loc_1400043B5
0x140004423  mov     eax, 80080008h
0x140004428  jmp     short loc_1400043D3
0x14000442a  mov     rcx, cs:?g_hExclusiveOperationSem@@3PEAXEA; hHandle
0x140004431  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140004436  call    cs:__imp_WaitForSingleObject
0x14000443c  test    eax, eax
0x14000443e  jnz     short loc_1400043FC
0x140004440  call    cs:__imp_GetCurrentThreadId
0x140004446  mov     cs:?g_dwThreadIdExclusiveLock@@3KC, eax; ulong volatile g_dwThreadIdExclusiveLock
0x14000444c  jmp     loc_1400043CA
```
