# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002492c`
- end: `0x1800249e9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180024310`

## callees

- `0x180023ea8`
- `0x18002492c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180024986`
- `KERNEL32!GetCurrentThreadId` at `0x180024986`

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
0x18002492c  mov     [rsp+arg_0], rbx
0x180024931  push    rdi
0x180024932  sub     rsp, 20h
0x180024936  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002493d  xor     ebx, ebx
0x18002493f  test    rdi, rdi
0x180024942  jz      loc_1800249DB
0x180024948  cmp     [rdi+8], rbx
0x18002494c  jnz     short loc_180024973
0x18002494e  mov     rcx, [rdi]
0x180024951  lea     rdx, [rsp+28h+arg_8]
0x180024956  mov     [rsp+28h+arg_8], rbx
0x18002495b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180024960  test    eax, eax
0x180024962  js      short loc_180024973
0x180024964  cmp     [rdi+8], rbx
0x180024968  jnz     short loc_180024973
0x18002496a  mov     rax, [rsp+28h+arg_8]
0x18002496f  mov     [rdi+8], rax
0x180024973  mov     rax, [rdi+8]
0x180024977  lea     rcx, [rax+20h]
0x18002497b  neg     rax
0x18002497e  sbb     rdi, rdi
0x180024981  and     rdi, rcx
0x180024984  jz      short loc_1800249DB
0x180024986  call    cs:__imp_GetCurrentThreadId
0x18002498c  mov     r8d, eax
0x18002498f  mov     r9d, eax
0x180024992  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002499c  shr     r8, 2
0x1800249a0  mul     r8
0x1800249a3  shr     rdx, 3
0x1800249a7  lea     rcx, [rdx+rdx*4]
0x1800249ab  add     rcx, rcx
0x1800249ae  sub     r8, rcx
0x1800249b1  mov     rbx, [rdi+r8*8+8]
0x1800249b6  test    rbx, rbx
0x1800249b9  jz      short loc_1800249DB
0x1800249bb  cmp     [rbx], r9d
0x1800249be  jz      short loc_1800249C6
0x1800249c0  mov     rbx, [rbx+8]
0x1800249c4  jmp     short loc_1800249B6
0x1800249c6  add     rbx, 10h
0x1800249ca  jz      short loc_1800249DB
0x1800249cc  cmp     qword ptr [rbx+8], 0
0x1800249d1  jnz     short loc_1800249DB
0x1800249d3  lea     rax, [rdi+4]
0x1800249d7  mov     [rbx+8], rax
0x1800249db  mov     rax, rbx
0x1800249de  mov     rbx, [rsp+28h+arg_0]
0x1800249e3  add     rsp, 20h
0x1800249e7  pop     rdi
0x1800249e8  retn
```
