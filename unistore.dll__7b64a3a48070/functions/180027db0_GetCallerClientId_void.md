# GetCallerClientId(void)

- ea: `0x180027db0`
- end: `0x180027e50`
- name: `?GetCallerClientId@@YA?AUCallerId@@XZ`
- size: `160`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006ce0`
- `0x180025b48`
- `0x180025f20`
- `0x1800262d0`
- `0x180026310`
- `0x180026870`
- `0x180026b10`
- `0x180026df8`
- `0x1800270ac`
- `0x1800273a4`
- `0x180027540`
- `0x1800294d0`
- `0x1800327f0`
- `0x18005833c`
- `0x18005ae84`
- `0x180063b90`
- `0x18007da58`
- `0x1800954e0`
- `0x1800955e0`
- `0x1800b5f80`
- `0x1800b6500`
- `0x1800b65c0`
- `0x1800b6700`
- `0x1800bfb40`

## callees

- `0x180027db0`
- `0x1800736c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027e28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027e28`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027dc5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027dc5`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180027e45`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180027e45`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180027dff`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180027dff`

## pseudocode

```c
unsigned __int64 GetCallerClientId()
{
  unsigned __int64 *Value; // rax
  unsigned __int64 result; // rax
  DWORD v2; // eax
  __int64 v3; // rdx

  if ( g_dwCallerClientIdSlot == -1 )
  {
    v2 = TlsAlloc();
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwCallerClientIdSlot, v2, -1) == -1 )
    {
      if ( v2 == -1 )
      {
        Log_AssertionEvent_2(0xFFFFFFFFLL, v3, 1073);
        return ((unsigned __int64)GetCurrentThreadId() << 32) | 0xFFFFFFFE;
      }
    }
    else
    {
      TlsFree(v2);
    }
  }
  Value = (unsigned __int64 *)TlsGetValue(g_dwCallerClientIdSlot);
  if ( !Value )
    return ((unsigned __int64)GetCurrentThreadId() << 32) | 0xFFFFFFFE;
  result = *Value;
  if ( !(_DWORD)result )
    return ((unsigned __int64)GetCurrentThreadId() << 32) | 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x180027db0  sub     rsp, 28h
0x180027db4  mov     eax, cs:?g_dwCallerClientIdSlot@@3KC; ulong volatile g_dwCallerClientIdSlot
0x180027dba  cmp     eax, 0FFFFFFFFh
0x180027dbd  jz      short loc_180027DFF
0x180027dbf  mov     ecx, cs:?g_dwCallerClientIdSlot@@3KC; dwTlsIndex
0x180027dc5  call    cs:__imp_TlsGetValue
0x180027dcb  test    rax, rax
0x180027dce  jz      short loc_180027E28
0x180027dd0  mov     rax, [rax]
0x180027dd3  mov     rcx, rax
0x180027dd6  mov     dword ptr [rsp+28h+arg_0], eax
0x180027dda  shr     rcx, 20h
0x180027dde  mov     dword ptr [rsp+28h+arg_0+4], ecx
0x180027de2  test    eax, eax
0x180027de4  jz      short loc_180027E28
0x180027de6  mov     rcx, [rsp+28h+arg_0]
0x180027deb  shr     rcx, 20h
0x180027def  mov     edx, ecx
0x180027df1  shl     rdx, 20h
0x180027df5  mov     eax, eax
0x180027df7  or      rax, rdx
0x180027dfa  add     rsp, 28h
0x180027dfe  retn
0x180027dff  call    cs:__imp_TlsAlloc
0x180027e05  mov     ecx, eax; dwTlsIndex
0x180027e07  mov     eax, 0FFFFFFFFh
0x180027e0c  lock cmpxchg cs:?g_dwCallerClientIdSlot@@3KC, ecx; ulong volatile g_dwCallerClientIdSlot
0x180027e14  cmp     eax, 0FFFFFFFFh
0x180027e17  jnz     short loc_180027E45
0x180027e19  cmp     ecx, eax
0x180027e1b  jnz     short loc_180027DBF
0x180027e1d  mov     r8d, 431h
0x180027e23  call    Log_AssertionEvent_2
0x180027e28  call    cs:__imp_GetCurrentThreadId
0x180027e2e  mov     ecx, eax
0x180027e30  mov     eax, 0FFFFFFFEh
0x180027e35  mov     edx, ecx
0x180027e37  shl     rdx, 20h
0x180027e3b  mov     eax, eax
0x180027e3d  or      rax, rdx
0x180027e40  add     rsp, 28h
0x180027e44  retn
0x180027e45  call    cs:__imp_TlsFree
0x180027e4b  jmp     loc_180027DBF
```
