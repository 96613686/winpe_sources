# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140006dbc`
- end: `0x140006e77`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400065e0`

## callees

- `0x1400054ac`
- `0x140006dbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006e12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006e12`

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
0x140006dbc  mov     [rsp+arg_0], rbx
0x140006dc1  push    rdi
0x140006dc2  sub     rsp, 20h
0x140006dc6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140006dcd  xor     ebx, ebx
0x140006dcf  test    rdi, rdi
0x140006dd2  jz      short loc_140006E52
0x140006dd4  cmp     [rdi+8], rbx
0x140006dd8  jnz     short loc_140006DFF
0x140006dda  mov     rcx, [rdi]
0x140006ddd  lea     rdx, [rsp+28h+arg_8]
0x140006de2  mov     [rsp+28h+arg_8], rbx
0x140006de7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140006dec  test    eax, eax
0x140006dee  js      short loc_140006DFF
0x140006df0  cmp     [rdi+8], rbx
0x140006df4  jnz     short loc_140006DFF
0x140006df6  mov     rax, [rsp+28h+arg_8]
0x140006dfb  mov     [rdi+8], rax
0x140006dff  mov     rax, [rdi+8]
0x140006e03  lea     rcx, [rax+20h]
0x140006e07  neg     rax
0x140006e0a  sbb     rdi, rdi
0x140006e0d  and     rdi, rcx
0x140006e10  jz      short loc_140006E52
0x140006e12  call    cs:__imp_GetCurrentThreadId
0x140006e18  mov     r8d, eax
0x140006e1b  mov     r9d, eax
0x140006e1e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006e28  shr     r8, 2
0x140006e2c  mul     r8
0x140006e2f  shr     rdx, 3
0x140006e33  lea     rcx, [rdx+rdx*4]
0x140006e37  add     rcx, rcx
0x140006e3a  sub     r8, rcx
0x140006e3d  mov     rbx, [rdi+r8*8+8]
0x140006e42  jmp     short loc_140006E4D
0x140006e44  cmp     [rbx], r9d
0x140006e47  jz      short loc_140006E60
0x140006e49  mov     rbx, [rbx+8]
0x140006e4d  test    rbx, rbx
0x140006e50  jnz     short loc_140006E44
0x140006e52  mov     rax, rbx
0x140006e55  mov     rbx, [rsp+28h+arg_0]
0x140006e5a  add     rsp, 20h
0x140006e5e  pop     rdi
0x140006e5f  retn
0x140006e60  add     rbx, 10h
0x140006e64  jz      short loc_140006E52
0x140006e66  cmp     qword ptr [rbx+8], 0
0x140006e6b  jnz     short loc_140006E52
0x140006e6d  lea     rax, [rdi+4]
0x140006e71  mov     [rbx+8], rax
0x140006e75  jmp     short loc_140006E52
```
