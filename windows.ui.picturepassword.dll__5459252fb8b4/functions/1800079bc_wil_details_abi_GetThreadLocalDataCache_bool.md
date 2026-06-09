# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800079bc`
- end: `0x180007a79`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006ec0`

## callees

- `0x180005fe8`
- `0x1800079bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a16`

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
0x1800079bc  mov     [rsp+arg_0], rbx
0x1800079c1  push    rdi
0x1800079c2  sub     rsp, 20h
0x1800079c6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800079cd  xor     ebx, ebx
0x1800079cf  test    rdi, rdi
0x1800079d2  jz      loc_180007A6B
0x1800079d8  cmp     [rdi+8], rbx
0x1800079dc  jnz     short loc_180007A03
0x1800079de  mov     rcx, [rdi]
0x1800079e1  lea     rdx, [rsp+28h+arg_8]
0x1800079e6  mov     [rsp+28h+arg_8], rbx
0x1800079eb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800079f0  test    eax, eax
0x1800079f2  js      short loc_180007A03
0x1800079f4  cmp     [rdi+8], rbx
0x1800079f8  jnz     short loc_180007A03
0x1800079fa  mov     rax, [rsp+28h+arg_8]
0x1800079ff  mov     [rdi+8], rax
0x180007a03  mov     rax, [rdi+8]
0x180007a07  lea     rcx, [rax+20h]
0x180007a0b  neg     rax
0x180007a0e  sbb     rdi, rdi
0x180007a11  and     rdi, rcx
0x180007a14  jz      short loc_180007A6B
0x180007a16  call    cs:__imp_GetCurrentThreadId
0x180007a1c  mov     r8d, eax
0x180007a1f  mov     r9d, eax
0x180007a22  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007a2c  shr     r8, 2
0x180007a30  mul     r8
0x180007a33  shr     rdx, 3
0x180007a37  lea     rcx, [rdx+rdx*4]
0x180007a3b  add     rcx, rcx
0x180007a3e  sub     r8, rcx
0x180007a41  mov     rbx, [rdi+r8*8+8]
0x180007a46  test    rbx, rbx
0x180007a49  jz      short loc_180007A6B
0x180007a4b  cmp     [rbx], r9d
0x180007a4e  jz      short loc_180007A56
0x180007a50  mov     rbx, [rbx+8]
0x180007a54  jmp     short loc_180007A46
0x180007a56  add     rbx, 10h
0x180007a5a  jz      short loc_180007A6B
0x180007a5c  cmp     qword ptr [rbx+8], 0
0x180007a61  jnz     short loc_180007A6B
0x180007a63  lea     rax, [rdi+4]
0x180007a67  mov     [rbx+8], rax
0x180007a6b  mov     rax, rbx
0x180007a6e  mov     rbx, [rsp+28h+arg_0]
0x180007a73  add     rsp, 20h
0x180007a77  pop     rdi
0x180007a78  retn
```
