# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000477c`
- end: `0x180004837`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003fa0`

## callees

- `0x18000383c`
- `0x18000477c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047d2`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x18000477c  mov     [rsp+arg_0], rbx
0x180004781  push    rdi
0x180004782  sub     rsp, 20h
0x180004786  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000478d  xor     ebx, ebx
0x18000478f  test    rdi, rdi
0x180004792  jz      short loc_180004812
0x180004794  cmp     [rdi+8], rbx
0x180004798  jnz     short loc_1800047BF
0x18000479a  mov     rcx, [rdi]
0x18000479d  lea     rdx, [rsp+28h+arg_8]
0x1800047a2  mov     [rsp+28h+arg_8], rbx
0x1800047a7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800047ac  test    eax, eax
0x1800047ae  js      short loc_1800047BF
0x1800047b0  cmp     [rdi+8], rbx
0x1800047b4  jnz     short loc_1800047BF
0x1800047b6  mov     rax, [rsp+28h+arg_8]
0x1800047bb  mov     [rdi+8], rax
0x1800047bf  mov     rax, [rdi+8]
0x1800047c3  lea     rcx, [rax+20h]
0x1800047c7  neg     rax
0x1800047ca  sbb     rdi, rdi
0x1800047cd  and     rdi, rcx
0x1800047d0  jz      short loc_180004812
0x1800047d2  call    cs:__imp_GetCurrentThreadId
0x1800047d8  mov     r8d, eax
0x1800047db  mov     r9d, eax
0x1800047de  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800047e8  shr     r8, 2
0x1800047ec  mul     r8
0x1800047ef  shr     rdx, 3
0x1800047f3  lea     rcx, [rdx+rdx*4]
0x1800047f7  add     rcx, rcx
0x1800047fa  sub     r8, rcx
0x1800047fd  mov     rbx, [rdi+r8*8+8]
0x180004802  jmp     short loc_18000480D
0x180004804  cmp     [rbx], r9d
0x180004807  jz      short loc_180004820
0x180004809  mov     rbx, [rbx+8]
0x18000480d  test    rbx, rbx
0x180004810  jnz     short loc_180004804
0x180004812  mov     rax, rbx
0x180004815  mov     rbx, [rsp+28h+arg_0]
0x18000481a  add     rsp, 20h
0x18000481e  pop     rdi
0x18000481f  retn
0x180004820  add     rbx, 10h
0x180004824  jz      short loc_180004812
0x180004826  cmp     qword ptr [rbx+8], 0
0x18000482b  jnz     short loc_180004812
0x18000482d  lea     rax, [rdi+4]
0x180004831  mov     [rbx+8], rax
0x180004835  jmp     short loc_180004812
```
