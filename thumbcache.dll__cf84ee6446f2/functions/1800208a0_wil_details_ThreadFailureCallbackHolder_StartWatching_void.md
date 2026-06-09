# wil::details::ThreadFailureCallbackHolder::StartWatching(void)

- ea: `0x1800208a0`
- end: `0x1800209c1`
- name: `?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `289`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020878`

## callees

- `0x1800208a0`
- `0x180020a84`
- `0x18002ec08`
- `0x1800364ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800208d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020945`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800208d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020945`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StartWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  __int64 v2; // rsi
  DWORD CurrentThreadId; // ebx
  unsigned __int64 v4; // r8
  __int64 v5; // r14
  __int64 i; // rax
  _QWORD *v7; // rcx
  char *v8; // rax
  signed __int64 v9; // rdx
  signed __int64 v10; // rax
  const struct wil::FailureInfo *v11; // rdx
  _BYTE v12[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( *((_DWORD *)this + 6) )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v11);
  }
  v2 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
    v5 = 8 * v4;
    for ( i = *(_QWORD *)(8 * v4 + v2); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == CurrentThreadId )
      {
        v7 = (_QWORD *)(i + 16);
        goto LABEL_8;
      }
    }
    v8 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v4);
    v9 = (signed __int64)v8;
    if ( v8 )
    {
      *(_DWORD *)v8 = CurrentThreadId;
      v7 = v8 + 16;
      *((_DWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 2) = 0;
      do
      {
        v10 = *(_QWORD *)(v5 + v2);
        *(_QWORD *)(v9 + 8) = v10;
      }
      while ( v10 != _InterlockedCompareExchange64((volatile signed __int64 *)(v5 + v2), v9, v10) );
    }
    else
    {
      v7 = 0;
    }
LABEL_8:
    *(_QWORD *)this = v7;
    if ( v7 )
    {
      *((_QWORD *)this + 2) = *v7;
      *v7 = this;
      *((_DWORD *)this + 6) = GetCurrentThreadId();
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800208a0  mov     rax, rsp
0x1800208a3  push    rdi
0x1800208a4  sub     rsp, 0C0h
0x1800208ab  cmp     dword ptr [rcx+18h], 0
0x1800208af  mov     rdi, rcx
0x1800208b2  jnz     loc_18002099B
0x1800208b8  mov     [rax+10h], rsi
0x1800208bc  mov     rsi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800208c3  test    rsi, rsi
0x1800208c6  jz      loc_1800209B8
0x1800208cc  mov     [rax+8], rbx
0x1800208d0  mov     [rax+18h], r14
0x1800208d4  call    cs:__imp_GetCurrentThreadId
0x1800208da  mov     r8d, eax
0x1800208dd  mov     ebx, eax
0x1800208df  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800208e9  shr     r8, 2
0x1800208ed  mul     r8
0x1800208f0  shr     rdx, 3
0x1800208f4  lea     rcx, [rdx+rdx*4]
0x1800208f8  add     rcx, rcx
0x1800208fb  sub     r8, rcx; unsigned __int64
0x1800208fe  lea     r14, ds:0[r8*8]
0x180020906  mov     rax, [r14+rsi]
0x18002090a  nop     word ptr [rax+rax+00h]
0x180020910  test    rax, rax
0x180020913  jz      short loc_18002095F
0x180020915  cmp     [rax], ebx
0x180020917  jz      short loc_18002091F
0x180020919  mov     rax, [rax+8]
0x18002091d  jmp     short loc_180020910
0x18002091f  lea     rcx, [rax+10h]
0x180020923  mov     r14, [rsp+0C8h+arg_10]
0x18002092b  mov     rbx, [rsp+0C8h+arg_0]
0x180020933  mov     [rdi], rcx
0x180020936  test    rcx, rcx
0x180020939  jz      short loc_18002094E
0x18002093b  mov     rax, [rcx]
0x18002093e  mov     [rdi+10h], rax
0x180020942  mov     [rcx], rdi
0x180020945  call    cs:__imp_GetCurrentThreadId
0x18002094b  mov     [rdi+18h], eax
0x18002094e  mov     rsi, [rsp+0C8h+arg_8]
0x180020956  add     rsp, 0C0h
0x18002095d  pop     rdi
0x18002095e  retn
0x18002095f  mov     edx, 18h; dwBytes
0x180020964  xor     ecx, ecx; dwFlags
0x180020966  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002096b  mov     rdx, rax
0x18002096e  test    rax, rax
0x180020971  jz      short loc_180020997
0x180020973  mov     [rax], ebx
0x180020975  lea     rcx, [rdx+10h]
0x180020979  xor     eax, eax
0x18002097b  mov     [rdx+4], eax
0x18002097e  mov     [rdx+8], rax
0x180020982  mov     [rcx], rax
0x180020985  mov     rax, [r14+rsi]
0x180020989  mov     [rdx+8], rax
0x18002098d  lock cmpxchg [r14+rsi], rdx
0x180020993  jz      short loc_180020923
0x180020995  jmp     short loc_180020985
0x180020997  xor     ecx, ecx
0x180020999  jmp     short loc_180020923
0x18002099b  xor     edx, edx; Val
0x18002099d  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800209a2  mov     r8d, 98h; Size
0x1800209a8  call    memset_0
0x1800209ad  lea     rcx, [rsp+0C8h+var_A8]; this
0x1800209b2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800209b8  mov     qword ptr [rcx], 0
0x1800209bf  jmp     short loc_18002094E
```
