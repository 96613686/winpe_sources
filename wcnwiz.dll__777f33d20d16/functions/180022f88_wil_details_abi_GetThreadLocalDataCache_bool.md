# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180022f88`
- end: `0x180023045`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022910`

## callees

- `0x18002245c`
- `0x180022f88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022fe2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022fe2`

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
0x180022f88  mov     [rsp+arg_0], rbx
0x180022f8d  push    rdi
0x180022f8e  sub     rsp, 20h
0x180022f92  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180022f99  xor     ebx, ebx
0x180022f9b  test    rdi, rdi
0x180022f9e  jz      loc_180023037
0x180022fa4  cmp     [rdi+8], rbx
0x180022fa8  jnz     short loc_180022FCF
0x180022faa  mov     rcx, [rdi]
0x180022fad  lea     rdx, [rsp+28h+arg_8]
0x180022fb2  mov     [rsp+28h+arg_8], rbx
0x180022fb7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180022fbc  test    eax, eax
0x180022fbe  js      short loc_180022FCF
0x180022fc0  cmp     [rdi+8], rbx
0x180022fc4  jnz     short loc_180022FCF
0x180022fc6  mov     rax, [rsp+28h+arg_8]
0x180022fcb  mov     [rdi+8], rax
0x180022fcf  mov     rax, [rdi+8]
0x180022fd3  lea     rcx, [rax+20h]
0x180022fd7  neg     rax
0x180022fda  sbb     rdi, rdi
0x180022fdd  and     rdi, rcx
0x180022fe0  jz      short loc_180023037
0x180022fe2  call    cs:__imp_GetCurrentThreadId
0x180022fe8  mov     r8d, eax
0x180022feb  mov     r9d, eax
0x180022fee  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180022ff8  shr     r8, 2
0x180022ffc  mul     r8
0x180022fff  shr     rdx, 3
0x180023003  lea     rcx, [rdx+rdx*4]
0x180023007  add     rcx, rcx
0x18002300a  sub     r8, rcx
0x18002300d  mov     rbx, [rdi+r8*8+8]
0x180023012  test    rbx, rbx
0x180023015  jz      short loc_180023037
0x180023017  cmp     [rbx], r9d
0x18002301a  jz      short loc_180023022
0x18002301c  mov     rbx, [rbx+8]
0x180023020  jmp     short loc_180023012
0x180023022  add     rbx, 10h
0x180023026  jz      short loc_180023037
0x180023028  cmp     qword ptr [rbx+8], 0
0x18002302d  jnz     short loc_180023037
0x18002302f  lea     rax, [rdi+4]
0x180023033  mov     [rbx+8], rax
0x180023037  mov     rax, rbx
0x18002303a  mov     rbx, [rsp+28h+arg_0]
0x18002303f  add     rsp, 20h
0x180023043  pop     rdi
0x180023044  retn
```
