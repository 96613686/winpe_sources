# InitializePingCritSec(void)

- ea: `0x180016d44`
- end: `0x180016e27`
- name: `?InitializePingCritSec@@YAKXZ`
- size: `227`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017490`

## callees

- `0x180016d44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016df9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016df9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180016d97`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180016d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016da7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016d71`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016d71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e08`

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
0x180016d44  mov     [rsp+arg_8], rbx
0x180016d49  mov     [rsp+arg_10], rsi
0x180016d4e  push    rdi
0x180016d4f  sub     rsp, 30h
0x180016d53  cmp     cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA, 0; _RTL_CRITICAL_SECTION * g_PingCritSec
0x180016d5b  jz      short loc_180016D64
0x180016d5d  xor     eax, eax
0x180016d5f  jmp     loc_180016E16
0x180016d64  xor     edi, edi
0x180016d66  xor     esi, esi
0x180016d68  mov     [rsp+38h+var_18], esi
0x180016d6c  lea     edx, [rdi+28h]; uBytes
0x180016d6f  xor     ecx, ecx; uFlags
0x180016d71  call    cs:__imp_LocalAlloc
0x180016d78  nop     dword ptr [rax+rax+00h]
0x180016d7d  mov     rbx, rax
0x180016d80  mov     [rsp+38h+arg_0], rax
0x180016d85  test    rax, rax
0x180016d88  jnz     short loc_180016D8F
0x180016d8a  lea     edi, [rsi+8]
0x180016d8d  jmp     short loc_180016DED
0x180016d8f  mov     edx, 80000000h; dwSpinCount
0x180016d94  mov     rcx, rax; lpCriticalSection
0x180016d97  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180016d9e  nop     dword ptr [rax+rax+00h]
0x180016da3  test    eax, eax
0x180016da5  jnz     short loc_180016DBB
0x180016da7  call    cs:__imp_GetLastError
0x180016dae  nop     dword ptr [rax+rax+00h]
0x180016db3  mov     edi, eax
0x180016db5  mov     [rsp+38h+var_14], eax
0x180016db9  jmp     short loc_180016DC4
0x180016dbb  mov     esi, 1
0x180016dc0  mov     [rsp+38h+var_18], esi
0x180016dc4  jmp     short loc_180016DD5
0x180016dc6  mov     edi, eax
0x180016dc8  mov     [rsp+38h+var_14], eax
0x180016dcc  mov     rbx, [rsp+38h+arg_0]
0x180016dd1  mov     esi, [rsp+38h+var_18]
0x180016dd5  test    edi, edi
0x180016dd7  jnz     short loc_180016DED
0x180016dd9  xor     eax, eax
0x180016ddb  lock cmpxchg cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA, rbx; _RTL_CRITICAL_SECTION * g_PingCritSec
0x180016de4  neg     rax
0x180016de7  sbb     rcx, rcx
0x180016dea  and     rbx, rcx
0x180016ded  test    rbx, rbx
0x180016df0  jz      short loc_180016E14
0x180016df2  test    esi, esi
0x180016df4  jz      short loc_180016E05
0x180016df6  mov     rcx, rbx; lpCriticalSection
0x180016df9  call    cs:__imp_DeleteCriticalSection
0x180016e00  nop     dword ptr [rax+rax+00h]
0x180016e05  mov     rcx, rbx; hMem
0x180016e08  call    cs:__imp_LocalFree
0x180016e0f  nop     dword ptr [rax+rax+00h]
0x180016e14  mov     eax, edi
0x180016e16  mov     rbx, [rsp+38h+arg_8]
0x180016e1b  mov     rsi, [rsp+38h+arg_10]
0x180016e20  add     rsp, 30h
0x180016e24  pop     rdi
0x180016e25  retn
```
