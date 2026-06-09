# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002d04c`
- end: `0x18002d109`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002ca70`

## callees

- `0x180026b64`
- `0x18002d04c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d0a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d0a6`

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
0x18002d04c  mov     [rsp+arg_0], rbx
0x18002d051  push    rdi
0x18002d052  sub     rsp, 20h
0x18002d056  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002d05d  xor     ebx, ebx
0x18002d05f  test    rdi, rdi
0x18002d062  jz      loc_18002D0FB
0x18002d068  cmp     [rdi+8], rbx
0x18002d06c  jnz     short loc_18002D093
0x18002d06e  mov     rcx, [rdi]
0x18002d071  lea     rdx, [rsp+28h+arg_8]
0x18002d076  mov     [rsp+28h+arg_8], rbx
0x18002d07b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002d080  test    eax, eax
0x18002d082  js      short loc_18002D093
0x18002d084  cmp     [rdi+8], rbx
0x18002d088  jnz     short loc_18002D093
0x18002d08a  mov     rax, [rsp+28h+arg_8]
0x18002d08f  mov     [rdi+8], rax
0x18002d093  mov     rax, [rdi+8]
0x18002d097  lea     rcx, [rax+20h]
0x18002d09b  neg     rax
0x18002d09e  sbb     rdi, rdi
0x18002d0a1  and     rdi, rcx
0x18002d0a4  jz      short loc_18002D0FB
0x18002d0a6  call    cs:__imp_GetCurrentThreadId
0x18002d0ac  mov     r8d, eax
0x18002d0af  mov     r9d, eax
0x18002d0b2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002d0bc  shr     r8, 2
0x18002d0c0  mul     r8
0x18002d0c3  shr     rdx, 3
0x18002d0c7  lea     rcx, [rdx+rdx*4]
0x18002d0cb  add     rcx, rcx
0x18002d0ce  sub     r8, rcx
0x18002d0d1  mov     rbx, [rdi+r8*8+8]
0x18002d0d6  test    rbx, rbx
0x18002d0d9  jz      short loc_18002D0FB
0x18002d0db  cmp     [rbx], r9d
0x18002d0de  jz      short loc_18002D0E6
0x18002d0e0  mov     rbx, [rbx+8]
0x18002d0e4  jmp     short loc_18002D0D6
0x18002d0e6  add     rbx, 10h
0x18002d0ea  jz      short loc_18002D0FB
0x18002d0ec  cmp     qword ptr [rbx+8], 0
0x18002d0f1  jnz     short loc_18002D0FB
0x18002d0f3  lea     rax, [rdi+4]
0x18002d0f7  mov     [rbx+8], rax
0x18002d0fb  mov     rax, rbx
0x18002d0fe  mov     rbx, [rsp+28h+arg_0]
0x18002d103  add     rsp, 20h
0x18002d107  pop     rdi
0x18002d108  retn
```
