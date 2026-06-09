# wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x180020770`
- end: `0x180020872`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `258`
- prototype: ``
- caller_count: `24`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e584`
- `0x18000ef80`
- `0x18000f15c`
- `0x18000f27c`
- `0x18000f5b0`
- `0x18000f7d8`
- `0x18000ff2c`
- `0x1800103ec`
- `0x180011b70`
- `0x180015bd4`
- `0x18001a5c0`
- `0x18001b5ec`
- `0x180024f64`
- `0x18002871c`
- `0x180028e1c`
- `0x18002e2d4`
- `0x1800308dc`
- `0x180033df0`
- `0x18003eee4`
- `0x180041890`
- `0x180041988`
- `0x180041a28`
- `0x180041ac8`
- `0x1800447a0`

## callees

- `0x180020770`
- `0x180020a84`
- `0x18002ec08`
- `0x1800364ac`
- `0x18003a5f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800207a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800207fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800207a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800207fb`

## pseudocode

```c
char __fastcall wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  __int64 v1; // rbx
  char *v2; // rax
  __int64 v3; // rdi
  DWORD CurrentThreadId; // ebp
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rsi
  __int64 i; // rcx
  _QWORD *v9; // rcx
  signed __int64 v10; // rdx
  signed __int64 v11; // rax
  char *v12; // rtt
  const struct wil::FailureInfo *v13; // rdx
  _BYTE v15[200]; // [rsp+20h] [rbp-C8h] BYREF

  v1 = a1 + 288;
  LOBYTE(v2) = wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  if ( !(_BYTE)v2 )
  {
    if ( *(_DWORD *)(v1 + 24) )
    {
      memset_0(v15, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v15, v13);
    }
    v3 = wil::details::g_pThreadFailureCallbacks;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      CurrentThreadId = GetCurrentThreadId();
      v6 = (unsigned __int64)CurrentThreadId >> 2;
      LOBYTE(v2) = -51 * v6;
      v7 = v6 % 0xA;
      for ( i = *(_QWORD *)(v3 + 8 * v7); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v9 = (_QWORD *)(i + 16);
          goto LABEL_9;
        }
      }
      v2 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v5);
      v10 = (signed __int64)v2;
      if ( v2 )
      {
        *(_DWORD *)v2 = CurrentThreadId;
        v9 = v2 + 16;
        *((_DWORD *)v2 + 1) = 0;
        *((_QWORD *)v2 + 1) = 0;
        *((_QWORD *)v2 + 2) = 0;
        do
        {
          v11 = *(_QWORD *)(v3 + 8 * v7);
          *(_QWORD *)(v10 + 8) = v11;
          v12 = (char *)v11;
          v2 = (char *)_InterlockedCompareExchange64((volatile signed __int64 *)(v3 + 8 * v7), v10, v11);
        }
        while ( v12 != v2 );
      }
      else
      {
        v9 = 0;
      }
LABEL_9:
      *(_QWORD *)v1 = v9;
      if ( v9 )
      {
        *(_QWORD *)(v1 + 16) = *v9;
        *v9 = v1;
        LODWORD(v2) = GetCurrentThreadId();
        *(_DWORD *)(v1 + 24) = (_DWORD)v2;
      }
    }
    else
    {
      *(_QWORD *)v1 = 0;
    }
  }
  return (char)v2;
}

```

## disassembly

```asm
0x180020770  push    rbx
0x180020772  push    rbp
0x180020773  push    rsi
0x180020774  push    rdi
0x180020775  sub     rsp, 0C8h
0x18002077c  lea     rbx, [rcx+120h]
0x180020783  mov     rcx, rbx; this
0x180020786  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x18002078b  test    al, al
0x18002078d  jnz     short loc_180020804
0x18002078f  cmp     dword ptr [rbx+18h], 0
0x180020793  jnz     loc_18002084C
0x180020799  mov     rdi, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800207a0  test    rdi, rdi
0x1800207a3  jz      loc_180020869
0x1800207a9  call    cs:__imp_GetCurrentThreadId
0x1800207af  mov     esi, eax
0x1800207b1  mov     ebp, eax
0x1800207b3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800207bd  shr     rsi, 2
0x1800207c1  mul     rsi
0x1800207c4  shr     rdx, 3
0x1800207c8  lea     rcx, [rdx+rdx*4]
0x1800207cc  add     rcx, rcx
0x1800207cf  sub     rsi, rcx
0x1800207d2  mov     rcx, [rdi+rsi*8]
0x1800207d6  test    rcx, rcx
0x1800207d9  jz      short loc_180020810
0x1800207db  cmp     [rcx], ebp
0x1800207dd  jz      short loc_1800207E5
0x1800207df  mov     rcx, [rcx+8]
0x1800207e3  jmp     short loc_1800207D6
0x1800207e5  add     rcx, 10h
0x1800207e9  mov     [rbx], rcx
0x1800207ec  test    rcx, rcx
0x1800207ef  jz      short loc_180020804
0x1800207f1  mov     rax, [rcx]
0x1800207f4  mov     [rbx+10h], rax
0x1800207f8  mov     [rcx], rbx
0x1800207fb  call    cs:__imp_GetCurrentThreadId
0x180020801  mov     [rbx+18h], eax
0x180020804  add     rsp, 0C8h
0x18002080b  pop     rdi
0x18002080c  pop     rsi
0x18002080d  pop     rbp
0x18002080e  pop     rbx
0x18002080f  retn
0x180020810  mov     edx, 18h; dwBytes
0x180020815  xor     ecx, ecx; dwFlags
0x180020817  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002081c  mov     rdx, rax
0x18002081f  test    rax, rax
0x180020822  jz      short loc_180020848
0x180020824  mov     [rax], ebp
0x180020826  lea     rcx, [rdx+10h]
0x18002082a  xor     eax, eax
0x18002082c  mov     [rdx+4], eax
0x18002082f  mov     [rdx+8], rax
0x180020833  mov     [rcx], rax
0x180020836  mov     rax, [rdi+rsi*8]
0x18002083a  mov     [rdx+8], rax
0x18002083e  lock cmpxchg [rdi+rsi*8], rdx
0x180020844  jz      short loc_1800207E9
0x180020846  jmp     short loc_180020836
0x180020848  xor     ecx, ecx
0x18002084a  jmp     short loc_1800207E9
0x18002084c  xor     edx, edx; Val
0x18002084e  lea     rcx, [rsp+0E8h+var_C8]; void *
0x180020853  mov     r8d, 98h; Size
0x180020859  call    memset_0
0x18002085e  lea     rcx, [rsp+0E8h+var_C8]; this
0x180020863  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180020869  mov     qword ptr [rbx], 0
0x180020870  jmp     short loc_180020804
```
