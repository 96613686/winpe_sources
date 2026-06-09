# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000c490`
- end: `0x18000c54d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bea0`

## callees

- `0x18000b998`
- `0x18000c490`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c4ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c4ea`

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
0x18000c490  mov     [rsp+arg_0], rbx
0x18000c495  push    rdi
0x18000c496  sub     rsp, 20h
0x18000c49a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000c4a1  xor     ebx, ebx
0x18000c4a3  test    rdi, rdi
0x18000c4a6  jz      loc_18000C53F
0x18000c4ac  cmp     [rdi+8], rbx
0x18000c4b0  jnz     short loc_18000C4D7
0x18000c4b2  mov     rcx, [rdi]
0x18000c4b5  lea     rdx, [rsp+28h+arg_8]
0x18000c4ba  mov     [rsp+28h+arg_8], rbx
0x18000c4bf  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000c4c4  test    eax, eax
0x18000c4c6  js      short loc_18000C4D7
0x18000c4c8  cmp     [rdi+8], rbx
0x18000c4cc  jnz     short loc_18000C4D7
0x18000c4ce  mov     rax, [rsp+28h+arg_8]
0x18000c4d3  mov     [rdi+8], rax
0x18000c4d7  mov     rax, [rdi+8]
0x18000c4db  lea     rcx, [rax+20h]
0x18000c4df  neg     rax
0x18000c4e2  sbb     rdi, rdi
0x18000c4e5  and     rdi, rcx
0x18000c4e8  jz      short loc_18000C53F
0x18000c4ea  call    cs:__imp_GetCurrentThreadId
0x18000c4f0  mov     r8d, eax
0x18000c4f3  mov     r9d, eax
0x18000c4f6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c500  shr     r8, 2
0x18000c504  mul     r8
0x18000c507  shr     rdx, 3
0x18000c50b  lea     rcx, [rdx+rdx*4]
0x18000c50f  add     rcx, rcx
0x18000c512  sub     r8, rcx
0x18000c515  mov     rbx, [rdi+r8*8+8]
0x18000c51a  test    rbx, rbx
0x18000c51d  jz      short loc_18000C53F
0x18000c51f  cmp     [rbx], r9d
0x18000c522  jz      short loc_18000C52A
0x18000c524  mov     rbx, [rbx+8]
0x18000c528  jmp     short loc_18000C51A
0x18000c52a  add     rbx, 10h
0x18000c52e  jz      short loc_18000C53F
0x18000c530  cmp     qword ptr [rbx+8], 0
0x18000c535  jnz     short loc_18000C53F
0x18000c537  lea     rax, [rdi+4]
0x18000c53b  mov     [rbx+8], rax
0x18000c53f  mov     rax, rbx
0x18000c542  mov     rbx, [rsp+28h+arg_0]
0x18000c547  add     rsp, 20h
0x18000c54b  pop     rdi
0x18000c54c  retn
```
