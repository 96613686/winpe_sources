# InitializePingCritSec(void)

- ea: `0x180015618`
- end: `0x1800156dc`
- name: `?InitializePingCritSec@@YAKXZ`
- size: `196`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015cb0`

## callees

- `0x180015618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800156bb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800156bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180015665`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180015665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001566f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001566f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015645`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015645`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156c4`

## pseudocode

```c
__int64 InitializePingCritSec(void)
{
  DWORD LastError; // edi
  int v2; // esi
  struct _RTL_CRITICAL_SECTION *v3; // rax
  signed __int64 v4; // rbx

  if ( g_PingCritSec )
    return 0;
  LastError = 0;
  v2 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)LocalAlloc(0, 0x28u);
  v4 = (signed __int64)v3;
  if ( v3 )
  {
    if ( InitializeCriticalSectionAndSpinCount(v3, 0x80000000) )
      v2 = 1;
    else
      LastError = GetLastError();
    if ( !LastError )
      v4 &= -(__int64)(_InterlockedCompareExchange64((volatile signed __int64 *)&g_PingCritSec, v4, 0) != 0);
  }
  else
  {
    LastError = 8;
  }
  if ( v4 )
  {
    if ( v2 )
      DeleteCriticalSection((LPCRITICAL_SECTION)v4);
    LocalFree((HLOCAL)v4);
  }
  return LastError;
}

```

## disassembly

```asm
0x180015618  mov     [rsp+arg_8], rbx
0x18001561d  mov     [rsp+arg_10], rsi
0x180015622  push    rdi
0x180015623  sub     rsp, 30h
0x180015627  cmp     cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA, 0; _RTL_CRITICAL_SECTION * g_PingCritSec
0x18001562f  jz      short loc_180015638
0x180015631  xor     eax, eax
0x180015633  jmp     loc_1800156CC
0x180015638  xor     edi, edi
0x18001563a  xor     esi, esi
0x18001563c  mov     [rsp+38h+var_18], esi
0x180015640  lea     edx, [rdi+28h]; uBytes
0x180015643  xor     ecx, ecx; uFlags
0x180015645  call    cs:__imp_LocalAlloc
0x18001564b  mov     rbx, rax
0x18001564e  mov     [rsp+38h+arg_0], rax
0x180015653  test    rax, rax
0x180015656  jnz     short loc_18001565D
0x180015658  lea     edi, [rsi+8]
0x18001565b  jmp     short loc_1800156AF
0x18001565d  mov     edx, 80000000h; dwSpinCount
0x180015662  mov     rcx, rax; lpCriticalSection
0x180015665  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001566b  test    eax, eax
0x18001566d  jnz     short loc_18001567D
0x18001566f  call    cs:__imp_GetLastError
0x180015675  mov     edi, eax
0x180015677  mov     [rsp+38h+var_14], eax
0x18001567b  jmp     short loc_180015686
0x18001567d  mov     esi, 1
0x180015682  mov     [rsp+38h+var_18], esi
0x180015686  jmp     short loc_180015697
0x180015688  mov     edi, eax
0x18001568a  mov     [rsp+38h+var_14], eax
0x18001568e  mov     rbx, [rsp+38h+arg_0]
0x180015693  mov     esi, [rsp+38h+var_18]
0x180015697  test    edi, edi
0x180015699  jnz     short loc_1800156AF
0x18001569b  xor     eax, eax
0x18001569d  lock cmpxchg cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA, rbx; _RTL_CRITICAL_SECTION * g_PingCritSec
0x1800156a6  neg     rax
0x1800156a9  sbb     rcx, rcx
0x1800156ac  and     rbx, rcx
0x1800156af  test    rbx, rbx
0x1800156b2  jz      short loc_1800156CA
0x1800156b4  test    esi, esi
0x1800156b6  jz      short loc_1800156C1
0x1800156b8  mov     rcx, rbx; lpCriticalSection
0x1800156bb  call    cs:__imp_DeleteCriticalSection
0x1800156c1  mov     rcx, rbx; hMem
0x1800156c4  call    cs:__imp_LocalFree
0x1800156ca  mov     eax, edi
0x1800156cc  mov     rbx, [rsp+38h+arg_8]
0x1800156d1  mov     rsi, [rsp+38h+arg_10]
0x1800156d6  add     rsp, 30h
0x1800156da  pop     rdi
0x1800156db  retn
```
