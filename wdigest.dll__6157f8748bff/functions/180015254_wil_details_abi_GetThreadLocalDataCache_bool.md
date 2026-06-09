# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180015254`
- end: `0x180015311`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014c20`

## callees

- `0x180014554`
- `0x180015254`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800152ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800152ae`

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
0x180015254  mov     [rsp+arg_0], rbx
0x180015259  push    rdi
0x18001525a  sub     rsp, 20h
0x18001525e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180015265  xor     ebx, ebx
0x180015267  test    rdi, rdi
0x18001526a  jz      loc_180015303
0x180015270  cmp     [rdi+8], rbx
0x180015274  jnz     short loc_18001529B
0x180015276  mov     rcx, [rdi]
0x180015279  lea     rdx, [rsp+28h+arg_8]
0x18001527e  mov     [rsp+28h+arg_8], rbx
0x180015283  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180015288  test    eax, eax
0x18001528a  js      short loc_18001529B
0x18001528c  cmp     [rdi+8], rbx
0x180015290  jnz     short loc_18001529B
0x180015292  mov     rax, [rsp+28h+arg_8]
0x180015297  mov     [rdi+8], rax
0x18001529b  mov     rax, [rdi+8]
0x18001529f  lea     rcx, [rax+20h]
0x1800152a3  neg     rax
0x1800152a6  sbb     rdi, rdi
0x1800152a9  and     rdi, rcx
0x1800152ac  jz      short loc_180015303
0x1800152ae  call    cs:__imp_GetCurrentThreadId
0x1800152b4  mov     r8d, eax
0x1800152b7  mov     r9d, eax
0x1800152ba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800152c4  shr     r8, 2
0x1800152c8  mul     r8
0x1800152cb  shr     rdx, 3
0x1800152cf  lea     rcx, [rdx+rdx*4]
0x1800152d3  add     rcx, rcx
0x1800152d6  sub     r8, rcx
0x1800152d9  mov     rbx, [rdi+r8*8+8]
0x1800152de  test    rbx, rbx
0x1800152e1  jz      short loc_180015303
0x1800152e3  cmp     [rbx], r9d
0x1800152e6  jz      short loc_1800152EE
0x1800152e8  mov     rbx, [rbx+8]
0x1800152ec  jmp     short loc_1800152DE
0x1800152ee  add     rbx, 10h
0x1800152f2  jz      short loc_180015303
0x1800152f4  cmp     qword ptr [rbx+8], 0
0x1800152f9  jnz     short loc_180015303
0x1800152fb  lea     rax, [rdi+4]
0x1800152ff  mov     [rbx+8], rax
0x180015303  mov     rax, rbx
0x180015306  mov     rbx, [rsp+28h+arg_0]
0x18001530b  add     rsp, 20h
0x18001530f  pop     rdi
0x180015310  retn
```
