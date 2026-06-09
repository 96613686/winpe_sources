# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400048e0`
- end: `0x14000499b`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004100`

## callees

- `0x140003a18`
- `0x1400048e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004936`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004936`

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
0x1400048e0  mov     [rsp+arg_0], rbx
0x1400048e5  push    rdi
0x1400048e6  sub     rsp, 20h
0x1400048ea  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400048f1  xor     ebx, ebx
0x1400048f3  test    rdi, rdi
0x1400048f6  jz      short loc_140004976
0x1400048f8  cmp     [rdi+8], rbx
0x1400048fc  jnz     short loc_140004923
0x1400048fe  mov     rcx, [rdi]
0x140004901  lea     rdx, [rsp+28h+arg_8]
0x140004906  mov     [rsp+28h+arg_8], rbx
0x14000490b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004910  test    eax, eax
0x140004912  js      short loc_140004923
0x140004914  cmp     [rdi+8], rbx
0x140004918  jnz     short loc_140004923
0x14000491a  mov     rax, [rsp+28h+arg_8]
0x14000491f  mov     [rdi+8], rax
0x140004923  mov     rax, [rdi+8]
0x140004927  lea     rcx, [rax+20h]
0x14000492b  neg     rax
0x14000492e  sbb     rdi, rdi
0x140004931  and     rdi, rcx
0x140004934  jz      short loc_140004976
0x140004936  call    cs:__imp_GetCurrentThreadId
0x14000493c  mov     r8d, eax
0x14000493f  mov     r9d, eax
0x140004942  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000494c  shr     r8, 2
0x140004950  mul     r8
0x140004953  shr     rdx, 3
0x140004957  lea     rcx, [rdx+rdx*4]
0x14000495b  add     rcx, rcx
0x14000495e  sub     r8, rcx
0x140004961  mov     rbx, [rdi+r8*8+8]
0x140004966  jmp     short loc_140004971
0x140004968  cmp     [rbx], r9d
0x14000496b  jz      short loc_140004984
0x14000496d  mov     rbx, [rbx+8]
0x140004971  test    rbx, rbx
0x140004974  jnz     short loc_140004968
0x140004976  mov     rax, rbx
0x140004979  mov     rbx, [rsp+28h+arg_0]
0x14000497e  add     rsp, 20h
0x140004982  pop     rdi
0x140004983  retn
0x140004984  add     rbx, 10h
0x140004988  jz      short loc_140004976
0x14000498a  cmp     qword ptr [rbx+8], 0
0x14000498f  jnz     short loc_140004976
0x140004991  lea     rax, [rdi+4]
0x140004995  mov     [rbx+8], rax
0x140004999  jmp     short loc_140004976
```
