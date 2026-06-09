# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000a8a4`
- end: `0x18000a95f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a4f0`

## callees

- `0x18000900c`
- `0x18000a8a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a8fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a8fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000a8a4  mov     [rsp+arg_0], rbx
0x18000a8a9  push    rdi
0x18000a8aa  sub     rsp, 20h
0x18000a8ae  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000a8b5  xor     ebx, ebx
0x18000a8b7  test    rdi, rdi
0x18000a8ba  jz      short loc_18000A93A
0x18000a8bc  cmp     [rdi+8], rbx
0x18000a8c0  jnz     short loc_18000A8E7
0x18000a8c2  mov     rcx, [rdi]
0x18000a8c5  lea     rdx, [rsp+28h+arg_8]
0x18000a8ca  mov     [rsp+28h+arg_8], rbx
0x18000a8cf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000a8d4  test    eax, eax
0x18000a8d6  js      short loc_18000A8E7
0x18000a8d8  cmp     [rdi+8], rbx
0x18000a8dc  jnz     short loc_18000A8E7
0x18000a8de  mov     rax, [rsp+28h+arg_8]
0x18000a8e3  mov     [rdi+8], rax
0x18000a8e7  mov     rax, [rdi+8]
0x18000a8eb  lea     rcx, [rax+20h]
0x18000a8ef  neg     rax
0x18000a8f2  sbb     rdi, rdi
0x18000a8f5  and     rdi, rcx
0x18000a8f8  jz      short loc_18000A93A
0x18000a8fa  call    cs:__imp_GetCurrentThreadId
0x18000a900  mov     r8d, eax
0x18000a903  mov     r9d, eax
0x18000a906  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a910  shr     r8, 2
0x18000a914  mul     r8
0x18000a917  shr     rdx, 3
0x18000a91b  lea     rcx, [rdx+rdx*4]
0x18000a91f  add     rcx, rcx
0x18000a922  sub     r8, rcx
0x18000a925  mov     rbx, [rdi+r8*8+8]
0x18000a92a  jmp     short loc_18000A935
0x18000a92c  cmp     [rbx], r9d
0x18000a92f  jz      short loc_18000A948
0x18000a931  mov     rbx, [rbx+8]
0x18000a935  test    rbx, rbx
0x18000a938  jnz     short loc_18000A92C
0x18000a93a  mov     rax, rbx
0x18000a93d  mov     rbx, [rsp+28h+arg_0]
0x18000a942  add     rsp, 20h
0x18000a946  pop     rdi
0x18000a947  retn
0x18000a948  add     rbx, 10h
0x18000a94c  jz      short loc_18000A93A
0x18000a94e  cmp     qword ptr [rbx+8], 0
0x18000a953  jnz     short loc_18000A93A
0x18000a955  lea     rax, [rdi+4]
0x18000a959  mov     [rbx+8], rax
0x18000a95d  jmp     short loc_18000A93A
```
