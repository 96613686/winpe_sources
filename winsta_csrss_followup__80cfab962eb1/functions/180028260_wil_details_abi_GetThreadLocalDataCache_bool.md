# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180028260`
- end: `0x180028324`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027660`

## callees

- `0x180020678`
- `0x180028260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800282ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800282ba`

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
0x180028260  mov     [rsp+arg_0], rbx
0x180028265  push    rdi
0x180028266  sub     rsp, 20h
0x18002826a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180028271  xor     ebx, ebx
0x180028273  test    rdi, rdi
0x180028276  jz      loc_180028315
0x18002827c  cmp     [rdi+8], rbx
0x180028280  jnz     short loc_1800282A7
0x180028282  mov     rcx, [rdi]
0x180028285  lea     rdx, [rsp+28h+arg_8]
0x18002828a  mov     [rsp+28h+arg_8], rbx
0x18002828f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180028294  test    eax, eax
0x180028296  js      short loc_1800282A7
0x180028298  cmp     [rdi+8], rbx
0x18002829c  jnz     short loc_1800282A7
0x18002829e  mov     rax, [rsp+28h+arg_8]
0x1800282a3  mov     [rdi+8], rax
0x1800282a7  mov     rax, [rdi+8]
0x1800282ab  lea     rcx, [rax+20h]
0x1800282af  neg     rax
0x1800282b2  sbb     rdi, rdi
0x1800282b5  and     rdi, rcx
0x1800282b8  jz      short loc_180028315
0x1800282ba  call    cs:__imp_GetCurrentThreadId
0x1800282c1  nop     dword ptr [rax+rax+00h]
0x1800282c6  mov     r8d, eax
0x1800282c9  mov     r9d, eax
0x1800282cc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800282d6  shr     r8, 2
0x1800282da  mul     r8
0x1800282dd  shr     rdx, 3
0x1800282e1  lea     rcx, [rdx+rdx*4]
0x1800282e5  add     rcx, rcx
0x1800282e8  sub     r8, rcx
0x1800282eb  mov     rbx, [rdi+r8*8+8]
0x1800282f0  test    rbx, rbx
0x1800282f3  jz      short loc_180028315
0x1800282f5  cmp     [rbx], r9d
0x1800282f8  jz      short loc_180028300
0x1800282fa  mov     rbx, [rbx+8]
0x1800282fe  jmp     short loc_1800282F0
0x180028300  add     rbx, 10h
0x180028304  jz      short loc_180028315
0x180028306  cmp     qword ptr [rbx+8], 0
0x18002830b  jnz     short loc_180028315
0x18002830d  lea     rax, [rdi+4]
0x180028311  mov     [rbx+8], rax
0x180028315  mov     rax, rbx
0x180028318  mov     rbx, [rsp+28h+arg_0]
0x18002831d  add     rsp, 20h
0x180028321  pop     rdi
0x180028322  retn
```
