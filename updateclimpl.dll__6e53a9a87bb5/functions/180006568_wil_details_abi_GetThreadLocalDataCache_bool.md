# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006568`
- end: `0x18000661f`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006730`

## callees

- `0x180006568`
- `0x180007654`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065be`

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
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
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
0x180006568  mov     [rsp+arg_0], rbx
0x18000656d  push    rdi
0x18000656e  sub     rsp, 20h
0x180006572  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006579  xor     ebx, ebx
0x18000657b  test    rdi, rdi
0x18000657e  jz      short loc_1800065FA
0x180006580  cmp     [rdi+8], rbx
0x180006584  jnz     short loc_1800065AB
0x180006586  mov     rcx, [rdi]
0x180006589  lea     rdx, [rsp+28h+arg_8]
0x18000658e  mov     [rsp+28h+arg_8], rbx
0x180006593  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006598  test    eax, eax
0x18000659a  js      short loc_1800065AB
0x18000659c  cmp     [rdi+8], rbx
0x1800065a0  jnz     short loc_1800065AB
0x1800065a2  mov     rax, [rsp+28h+arg_8]
0x1800065a7  mov     [rdi+8], rax
0x1800065ab  mov     rax, [rdi+8]
0x1800065af  lea     rcx, [rax+20h]
0x1800065b3  neg     rax
0x1800065b6  sbb     rdi, rdi
0x1800065b9  and     rdi, rcx
0x1800065bc  jz      short loc_1800065FA
0x1800065be  call    cs:__imp_GetCurrentThreadId
0x1800065c4  mov     r8d, eax
0x1800065c7  mov     r9d, eax
0x1800065ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800065d4  mul     r9
0x1800065d7  shr     rdx, 3
0x1800065db  lea     rcx, [rdx+rdx*4]
0x1800065df  add     rcx, rcx
0x1800065e2  sub     r8, rcx
0x1800065e5  mov     rbx, [rdi+r8*8+8]
0x1800065ea  jmp     short loc_1800065F5
0x1800065ec  cmp     [rbx], r9d
0x1800065ef  jz      short loc_180006608
0x1800065f1  mov     rbx, [rbx+8]
0x1800065f5  test    rbx, rbx
0x1800065f8  jnz     short loc_1800065EC
0x1800065fa  mov     rax, rbx
0x1800065fd  mov     rbx, [rsp+28h+arg_0]
0x180006602  add     rsp, 20h
0x180006606  pop     rdi
0x180006607  retn
0x180006608  add     rbx, 10h
0x18000660c  jz      short loc_1800065FA
0x18000660e  cmp     qword ptr [rbx+8], 0
0x180006613  jnz     short loc_1800065FA
0x180006615  lea     rax, [rdi+4]
0x180006619  mov     [rbx+8], rax
0x18000661d  jmp     short loc_1800065FA
```
