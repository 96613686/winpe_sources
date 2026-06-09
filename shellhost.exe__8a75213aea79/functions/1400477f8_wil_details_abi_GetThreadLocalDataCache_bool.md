# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400477f8`
- end: `0x1400478b5`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140047180`

## callees

- `0x14000bf18`
- `0x1400477f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140047852`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140047852`

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
0x1400477f8  mov     [rsp+arg_0], rbx
0x1400477fd  push    rdi
0x1400477fe  sub     rsp, 20h
0x140047802  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140047809  xor     ebx, ebx
0x14004780b  test    rdi, rdi
0x14004780e  jz      loc_1400478A7
0x140047814  cmp     [rdi+8], rbx
0x140047818  jnz     short loc_14004783F
0x14004781a  mov     rcx, [rdi]
0x14004781d  lea     rdx, [rsp+28h+arg_8]
0x140047822  mov     [rsp+28h+arg_8], rbx
0x140047827  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14004782c  test    eax, eax
0x14004782e  js      short loc_14004783F
0x140047830  cmp     [rdi+8], rbx
0x140047834  jnz     short loc_14004783F
0x140047836  mov     rax, [rsp+28h+arg_8]
0x14004783b  mov     [rdi+8], rax
0x14004783f  mov     rax, [rdi+8]
0x140047843  lea     rcx, [rax+20h]
0x140047847  neg     rax
0x14004784a  sbb     rdi, rdi
0x14004784d  and     rdi, rcx
0x140047850  jz      short loc_1400478A7
0x140047852  call    cs:__imp_GetCurrentThreadId
0x140047858  mov     r8d, eax
0x14004785b  mov     r9d, eax
0x14004785e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140047868  shr     r8, 2
0x14004786c  mul     r8
0x14004786f  shr     rdx, 3
0x140047873  lea     rcx, [rdx+rdx*4]
0x140047877  add     rcx, rcx
0x14004787a  sub     r8, rcx
0x14004787d  mov     rbx, [rdi+r8*8+8]
0x140047882  test    rbx, rbx
0x140047885  jz      short loc_1400478A7
0x140047887  cmp     [rbx], r9d
0x14004788a  jz      short loc_140047892
0x14004788c  mov     rbx, [rbx+8]
0x140047890  jmp     short loc_140047882
0x140047892  add     rbx, 10h
0x140047896  jz      short loc_1400478A7
0x140047898  cmp     qword ptr [rbx+8], 0
0x14004789d  jnz     short loc_1400478A7
0x14004789f  lea     rax, [rdi+4]
0x1400478a3  mov     [rbx+8], rax
0x1400478a7  mov     rax, rbx
0x1400478aa  mov     rbx, [rsp+28h+arg_0]
0x1400478af  add     rsp, 20h
0x1400478b3  pop     rdi
0x1400478b4  retn
```
