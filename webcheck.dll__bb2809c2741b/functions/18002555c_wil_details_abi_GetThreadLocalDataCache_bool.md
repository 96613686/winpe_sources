# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002555c`
- end: `0x180025619`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025010`

## callees

- `0x180024acc`
- `0x18002555c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800255b6`
- `KERNEL32!GetCurrentThreadId` at `0x1800255b6`

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
0x18002555c  mov     [rsp+arg_0], rbx
0x180025561  push    rdi
0x180025562  sub     rsp, 20h
0x180025566  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002556d  xor     ebx, ebx
0x18002556f  test    rdi, rdi
0x180025572  jz      loc_18002560B
0x180025578  cmp     [rdi+8], rbx
0x18002557c  jnz     short loc_1800255A3
0x18002557e  mov     rcx, [rdi]
0x180025581  lea     rdx, [rsp+28h+arg_8]
0x180025586  mov     [rsp+28h+arg_8], rbx
0x18002558b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180025590  test    eax, eax
0x180025592  js      short loc_1800255A3
0x180025594  cmp     [rdi+8], rbx
0x180025598  jnz     short loc_1800255A3
0x18002559a  mov     rax, [rsp+28h+arg_8]
0x18002559f  mov     [rdi+8], rax
0x1800255a3  mov     rax, [rdi+8]
0x1800255a7  lea     rcx, [rax+20h]
0x1800255ab  neg     rax
0x1800255ae  sbb     rdi, rdi
0x1800255b1  and     rdi, rcx
0x1800255b4  jz      short loc_18002560B
0x1800255b6  call    cs:__imp_GetCurrentThreadId
0x1800255bc  mov     r8d, eax
0x1800255bf  mov     r9d, eax
0x1800255c2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800255cc  shr     r8, 2
0x1800255d0  mul     r8
0x1800255d3  shr     rdx, 3
0x1800255d7  lea     rcx, [rdx+rdx*4]
0x1800255db  add     rcx, rcx
0x1800255de  sub     r8, rcx
0x1800255e1  mov     rbx, [rdi+r8*8+8]
0x1800255e6  test    rbx, rbx
0x1800255e9  jz      short loc_18002560B
0x1800255eb  cmp     [rbx], r9d
0x1800255ee  jz      short loc_1800255F6
0x1800255f0  mov     rbx, [rbx+8]
0x1800255f4  jmp     short loc_1800255E6
0x1800255f6  add     rbx, 10h
0x1800255fa  jz      short loc_18002560B
0x1800255fc  cmp     qword ptr [rbx+8], 0
0x180025601  jnz     short loc_18002560B
0x180025603  lea     rax, [rdi+4]
0x180025607  mov     [rbx+8], rax
0x18002560b  mov     rax, rbx
0x18002560e  mov     rbx, [rsp+28h+arg_0]
0x180025613  add     rsp, 20h
0x180025617  pop     rdi
0x180025618  retn
```
