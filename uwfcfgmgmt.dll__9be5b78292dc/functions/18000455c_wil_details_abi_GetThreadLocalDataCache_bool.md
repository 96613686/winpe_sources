# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000455c`
- end: `0x180004617`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d80`

## callees

- `0x1800036bc`
- `0x18000455c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045b2`

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
0x18000455c  mov     [rsp+arg_0], rbx
0x180004561  push    rdi
0x180004562  sub     rsp, 20h
0x180004566  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000456d  xor     ebx, ebx
0x18000456f  test    rdi, rdi
0x180004572  jz      short loc_1800045F2
0x180004574  cmp     [rdi+8], rbx
0x180004578  jnz     short loc_18000459F
0x18000457a  mov     rcx, [rdi]
0x18000457d  lea     rdx, [rsp+28h+arg_8]
0x180004582  mov     [rsp+28h+arg_8], rbx
0x180004587  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000458c  test    eax, eax
0x18000458e  js      short loc_18000459F
0x180004590  cmp     [rdi+8], rbx
0x180004594  jnz     short loc_18000459F
0x180004596  mov     rax, [rsp+28h+arg_8]
0x18000459b  mov     [rdi+8], rax
0x18000459f  mov     rax, [rdi+8]
0x1800045a3  lea     rcx, [rax+20h]
0x1800045a7  neg     rax
0x1800045aa  sbb     rdi, rdi
0x1800045ad  and     rdi, rcx
0x1800045b0  jz      short loc_1800045F2
0x1800045b2  call    cs:__imp_GetCurrentThreadId
0x1800045b8  mov     r8d, eax
0x1800045bb  mov     r9d, eax
0x1800045be  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800045c8  shr     r8, 2
0x1800045cc  mul     r8
0x1800045cf  shr     rdx, 3
0x1800045d3  lea     rcx, [rdx+rdx*4]
0x1800045d7  add     rcx, rcx
0x1800045da  sub     r8, rcx
0x1800045dd  mov     rbx, [rdi+r8*8+8]
0x1800045e2  jmp     short loc_1800045ED
0x1800045e4  cmp     [rbx], r9d
0x1800045e7  jz      short loc_180004600
0x1800045e9  mov     rbx, [rbx+8]
0x1800045ed  test    rbx, rbx
0x1800045f0  jnz     short loc_1800045E4
0x1800045f2  mov     rax, rbx
0x1800045f5  mov     rbx, [rsp+28h+arg_0]
0x1800045fa  add     rsp, 20h
0x1800045fe  pop     rdi
0x1800045ff  retn
0x180004600  add     rbx, 10h
0x180004604  jz      short loc_1800045F2
0x180004606  cmp     qword ptr [rbx+8], 0
0x18000460b  jnz     short loc_1800045F2
0x18000460d  lea     rax, [rdi+4]
0x180004611  mov     [rbx+8], rax
0x180004615  jmp     short loc_1800045F2
```
