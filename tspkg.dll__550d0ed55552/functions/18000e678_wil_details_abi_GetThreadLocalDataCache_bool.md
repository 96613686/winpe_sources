# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000e678`
- end: `0x18000e735`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e010`

## callees

- `0x18000d724`
- `0x18000e678`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e6d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e6d2`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

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
0x18000e678  mov     [rsp+arg_0], rbx
0x18000e67d  push    rdi
0x18000e67e  sub     rsp, 20h
0x18000e682  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000e689  xor     ebx, ebx
0x18000e68b  test    rdi, rdi
0x18000e68e  jz      loc_18000E727
0x18000e694  cmp     [rdi+8], rbx
0x18000e698  jnz     short loc_18000E6BF
0x18000e69a  mov     rcx, [rdi]
0x18000e69d  lea     rdx, [rsp+28h+arg_8]
0x18000e6a2  mov     [rsp+28h+arg_8], rbx
0x18000e6a7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000e6ac  test    eax, eax
0x18000e6ae  js      short loc_18000E6BF
0x18000e6b0  cmp     [rdi+8], rbx
0x18000e6b4  jnz     short loc_18000E6BF
0x18000e6b6  mov     rax, [rsp+28h+arg_8]
0x18000e6bb  mov     [rdi+8], rax
0x18000e6bf  mov     rax, [rdi+8]
0x18000e6c3  lea     rcx, [rax+20h]
0x18000e6c7  neg     rax
0x18000e6ca  sbb     rdi, rdi
0x18000e6cd  and     rdi, rcx
0x18000e6d0  jz      short loc_18000E727
0x18000e6d2  call    cs:__imp_GetCurrentThreadId
0x18000e6d8  mov     r8d, eax
0x18000e6db  mov     r9d, eax
0x18000e6de  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000e6e8  shr     r8, 2
0x18000e6ec  mul     r8
0x18000e6ef  shr     rdx, 3
0x18000e6f3  lea     rcx, [rdx+rdx*4]
0x18000e6f7  add     rcx, rcx
0x18000e6fa  sub     r8, rcx
0x18000e6fd  mov     rbx, [rdi+r8*8+8]
0x18000e702  test    rbx, rbx
0x18000e705  jz      short loc_18000E727
0x18000e707  cmp     [rbx], r9d
0x18000e70a  jz      short loc_18000E712
0x18000e70c  mov     rbx, [rbx+8]
0x18000e710  jmp     short loc_18000E702
0x18000e712  add     rbx, 10h
0x18000e716  jz      short loc_18000E727
0x18000e718  cmp     qword ptr [rbx+8], 0
0x18000e71d  jnz     short loc_18000E727
0x18000e71f  lea     rax, [rdi+4]
0x18000e723  mov     [rbx+8], rax
0x18000e727  mov     rax, rbx
0x18000e72a  mov     rbx, [rsp+28h+arg_0]
0x18000e72f  add     rsp, 20h
0x18000e733  pop     rdi
0x18000e734  retn
```
