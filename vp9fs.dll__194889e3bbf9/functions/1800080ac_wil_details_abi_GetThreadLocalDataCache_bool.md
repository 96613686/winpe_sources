# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800080ac`
- end: `0x180008167`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800078a0`

## callees

- `0x18000671c`
- `0x1800080ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008102`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008102`

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
0x1800080ac  mov     [rsp+arg_0], rbx
0x1800080b1  push    rdi
0x1800080b2  sub     rsp, 20h
0x1800080b6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800080bd  xor     ebx, ebx
0x1800080bf  test    rdi, rdi
0x1800080c2  jz      short loc_180008142
0x1800080c4  cmp     [rdi+8], rbx
0x1800080c8  jnz     short loc_1800080EF
0x1800080ca  mov     rcx, [rdi]
0x1800080cd  lea     rdx, [rsp+28h+arg_8]
0x1800080d2  mov     [rsp+28h+arg_8], rbx
0x1800080d7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800080dc  test    eax, eax
0x1800080de  js      short loc_1800080EF
0x1800080e0  cmp     [rdi+8], rbx
0x1800080e4  jnz     short loc_1800080EF
0x1800080e6  mov     rax, [rsp+28h+arg_8]
0x1800080eb  mov     [rdi+8], rax
0x1800080ef  mov     rax, [rdi+8]
0x1800080f3  lea     rcx, [rax+20h]
0x1800080f7  neg     rax
0x1800080fa  sbb     rdi, rdi
0x1800080fd  and     rdi, rcx
0x180008100  jz      short loc_180008142
0x180008102  call    cs:__imp_GetCurrentThreadId
0x180008108  mov     r8d, eax
0x18000810b  mov     r9d, eax
0x18000810e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008118  shr     r8, 2
0x18000811c  mul     r8
0x18000811f  shr     rdx, 3
0x180008123  lea     rcx, [rdx+rdx*4]
0x180008127  add     rcx, rcx
0x18000812a  sub     r8, rcx
0x18000812d  mov     rbx, [rdi+r8*8+8]
0x180008132  jmp     short loc_18000813D
0x180008134  cmp     [rbx], r9d
0x180008137  jz      short loc_180008150
0x180008139  mov     rbx, [rbx+8]
0x18000813d  test    rbx, rbx
0x180008140  jnz     short loc_180008134
0x180008142  mov     rax, rbx
0x180008145  mov     rbx, [rsp+28h+arg_0]
0x18000814a  add     rsp, 20h
0x18000814e  pop     rdi
0x18000814f  retn
0x180008150  add     rbx, 10h
0x180008154  jz      short loc_180008142
0x180008156  cmp     qword ptr [rbx+8], 0
0x18000815b  jnz     short loc_180008142
0x18000815d  lea     rax, [rdi+4]
0x180008161  mov     [rbx+8], rax
0x180008165  jmp     short loc_180008142
```
