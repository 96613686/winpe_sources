# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002adf4`
- end: `0x18002aeb1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a840`

## callees

- `0x180029e44`
- `0x18002adf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ae4e`

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
0x18002adf4  mov     [rsp+arg_0], rbx
0x18002adf9  push    rdi
0x18002adfa  sub     rsp, 20h
0x18002adfe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002ae05  xor     ebx, ebx
0x18002ae07  test    rdi, rdi
0x18002ae0a  jz      loc_18002AEA3
0x18002ae10  cmp     [rdi+8], rbx
0x18002ae14  jnz     short loc_18002AE3B
0x18002ae16  mov     rcx, [rdi]
0x18002ae19  lea     rdx, [rsp+28h+arg_8]
0x18002ae1e  mov     [rsp+28h+arg_8], rbx
0x18002ae23  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002ae28  test    eax, eax
0x18002ae2a  js      short loc_18002AE3B
0x18002ae2c  cmp     [rdi+8], rbx
0x18002ae30  jnz     short loc_18002AE3B
0x18002ae32  mov     rax, [rsp+28h+arg_8]
0x18002ae37  mov     [rdi+8], rax
0x18002ae3b  mov     rax, [rdi+8]
0x18002ae3f  lea     rcx, [rax+20h]
0x18002ae43  neg     rax
0x18002ae46  sbb     rdi, rdi
0x18002ae49  and     rdi, rcx
0x18002ae4c  jz      short loc_18002AEA3
0x18002ae4e  call    cs:__imp_GetCurrentThreadId
0x18002ae54  mov     r8d, eax
0x18002ae57  mov     r9d, eax
0x18002ae5a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002ae64  shr     r8, 2
0x18002ae68  mul     r8
0x18002ae6b  shr     rdx, 3
0x18002ae6f  lea     rcx, [rdx+rdx*4]
0x18002ae73  add     rcx, rcx
0x18002ae76  sub     r8, rcx
0x18002ae79  mov     rbx, [rdi+r8*8+8]
0x18002ae7e  test    rbx, rbx
0x18002ae81  jz      short loc_18002AEA3
0x18002ae83  cmp     [rbx], r9d
0x18002ae86  jz      short loc_18002AE8E
0x18002ae88  mov     rbx, [rbx+8]
0x18002ae8c  jmp     short loc_18002AE7E
0x18002ae8e  add     rbx, 10h
0x18002ae92  jz      short loc_18002AEA3
0x18002ae94  cmp     qword ptr [rbx+8], 0
0x18002ae99  jnz     short loc_18002AEA3
0x18002ae9b  lea     rax, [rdi+4]
0x18002ae9f  mov     [rbx+8], rax
0x18002aea3  mov     rax, rbx
0x18002aea6  mov     rbx, [rsp+28h+arg_0]
0x18002aeab  add     rsp, 20h
0x18002aeaf  pop     rdi
0x18002aeb0  retn
```
