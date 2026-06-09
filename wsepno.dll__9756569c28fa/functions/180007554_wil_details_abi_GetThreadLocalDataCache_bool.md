# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180007554`
- end: `0x18000760f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800071a0`

## callees

- `0x18000558c`
- `0x180007554`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075aa`

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
0x180007554  mov     [rsp+arg_0], rbx
0x180007559  push    rdi
0x18000755a  sub     rsp, 20h
0x18000755e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180007565  xor     ebx, ebx
0x180007567  test    rdi, rdi
0x18000756a  jz      short loc_1800075EA
0x18000756c  cmp     [rdi+8], rbx
0x180007570  jnz     short loc_180007597
0x180007572  mov     rcx, [rdi]
0x180007575  lea     rdx, [rsp+28h+arg_8]
0x18000757a  mov     [rsp+28h+arg_8], rbx
0x18000757f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180007584  test    eax, eax
0x180007586  js      short loc_180007597
0x180007588  cmp     [rdi+8], rbx
0x18000758c  jnz     short loc_180007597
0x18000758e  mov     rax, [rsp+28h+arg_8]
0x180007593  mov     [rdi+8], rax
0x180007597  mov     rax, [rdi+8]
0x18000759b  lea     rcx, [rax+20h]
0x18000759f  neg     rax
0x1800075a2  sbb     rdi, rdi
0x1800075a5  and     rdi, rcx
0x1800075a8  jz      short loc_1800075EA
0x1800075aa  call    cs:__imp_GetCurrentThreadId
0x1800075b0  mov     r8d, eax
0x1800075b3  mov     r9d, eax
0x1800075b6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800075c0  shr     r8, 2
0x1800075c4  mul     r8
0x1800075c7  shr     rdx, 3
0x1800075cb  lea     rcx, [rdx+rdx*4]
0x1800075cf  add     rcx, rcx
0x1800075d2  sub     r8, rcx
0x1800075d5  mov     rbx, [rdi+r8*8+8]
0x1800075da  jmp     short loc_1800075E5
0x1800075dc  cmp     [rbx], r9d
0x1800075df  jz      short loc_1800075F8
0x1800075e1  mov     rbx, [rbx+8]
0x1800075e5  test    rbx, rbx
0x1800075e8  jnz     short loc_1800075DC
0x1800075ea  mov     rax, rbx
0x1800075ed  mov     rbx, [rsp+28h+arg_0]
0x1800075f2  add     rsp, 20h
0x1800075f6  pop     rdi
0x1800075f7  retn
0x1800075f8  add     rbx, 10h
0x1800075fc  jz      short loc_1800075EA
0x1800075fe  cmp     qword ptr [rbx+8], 0
0x180007603  jnz     short loc_1800075EA
0x180007605  lea     rax, [rdi+4]
0x180007609  mov     [rbx+8], rax
0x18000760d  jmp     short loc_1800075EA
```
