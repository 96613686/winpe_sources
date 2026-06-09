# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800085ec`
- end: `0x1800086a7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007470`

## callees

- `0x180005198`
- `0x1800085ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008642`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008642`

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
0x1800085ec  mov     [rsp+arg_0], rbx
0x1800085f1  push    rdi
0x1800085f2  sub     rsp, 20h
0x1800085f6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800085fd  xor     ebx, ebx
0x1800085ff  test    rdi, rdi
0x180008602  jz      short loc_180008682
0x180008604  cmp     [rdi+8], rbx
0x180008608  jnz     short loc_18000862F
0x18000860a  mov     rcx, [rdi]
0x18000860d  lea     rdx, [rsp+28h+arg_8]
0x180008612  mov     [rsp+28h+arg_8], rbx
0x180008617  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000861c  test    eax, eax
0x18000861e  js      short loc_18000862F
0x180008620  cmp     [rdi+8], rbx
0x180008624  jnz     short loc_18000862F
0x180008626  mov     rax, [rsp+28h+arg_8]
0x18000862b  mov     [rdi+8], rax
0x18000862f  mov     rax, [rdi+8]
0x180008633  lea     rcx, [rax+20h]
0x180008637  neg     rax
0x18000863a  sbb     rdi, rdi
0x18000863d  and     rdi, rcx
0x180008640  jz      short loc_180008682
0x180008642  call    cs:__imp_GetCurrentThreadId
0x180008648  mov     r8d, eax
0x18000864b  mov     r9d, eax
0x18000864e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008658  shr     r8, 2
0x18000865c  mul     r8
0x18000865f  shr     rdx, 3
0x180008663  lea     rcx, [rdx+rdx*4]
0x180008667  add     rcx, rcx
0x18000866a  sub     r8, rcx
0x18000866d  mov     rbx, [rdi+r8*8+8]
0x180008672  jmp     short loc_18000867D
0x180008674  cmp     [rbx], r9d
0x180008677  jz      short loc_180008690
0x180008679  mov     rbx, [rbx+8]
0x18000867d  test    rbx, rbx
0x180008680  jnz     short loc_180008674
0x180008682  mov     rax, rbx
0x180008685  mov     rbx, [rsp+28h+arg_0]
0x18000868a  add     rsp, 20h
0x18000868e  pop     rdi
0x18000868f  retn
0x180008690  add     rbx, 10h
0x180008694  jz      short loc_180008682
0x180008696  cmp     qword ptr [rbx+8], 0
0x18000869b  jnz     short loc_180008682
0x18000869d  lea     rax, [rdi+4]
0x1800086a1  mov     [rbx+8], rax
0x1800086a5  jmp     short loc_180008682
```
