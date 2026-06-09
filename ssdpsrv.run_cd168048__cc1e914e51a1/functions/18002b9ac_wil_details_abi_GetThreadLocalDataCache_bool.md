# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002b9ac`
- end: `0x18002ba70`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002b410`

## callees

- `0x18002aa10`
- `0x18002b9ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ba06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ba06`

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
0x18002b9ac  mov     [rsp+arg_0], rbx
0x18002b9b1  push    rdi
0x18002b9b2  sub     rsp, 20h
0x18002b9b6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002b9bd  xor     ebx, ebx
0x18002b9bf  test    rdi, rdi
0x18002b9c2  jz      loc_18002BA61
0x18002b9c8  cmp     [rdi+8], rbx
0x18002b9cc  jnz     short loc_18002B9F3
0x18002b9ce  mov     rcx, [rdi]
0x18002b9d1  lea     rdx, [rsp+28h+arg_8]
0x18002b9d6  mov     [rsp+28h+arg_8], rbx
0x18002b9db  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002b9e0  test    eax, eax
0x18002b9e2  js      short loc_18002B9F3
0x18002b9e4  cmp     [rdi+8], rbx
0x18002b9e8  jnz     short loc_18002B9F3
0x18002b9ea  mov     rax, [rsp+28h+arg_8]
0x18002b9ef  mov     [rdi+8], rax
0x18002b9f3  mov     rax, [rdi+8]
0x18002b9f7  lea     rcx, [rax+20h]
0x18002b9fb  neg     rax
0x18002b9fe  sbb     rdi, rdi
0x18002ba01  and     rdi, rcx
0x18002ba04  jz      short loc_18002BA61
0x18002ba06  call    cs:__imp_GetCurrentThreadId
0x18002ba0d  nop     dword ptr [rax+rax+00h]
0x18002ba12  mov     r8d, eax
0x18002ba15  mov     r9d, eax
0x18002ba18  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002ba22  shr     r8, 2
0x18002ba26  mul     r8
0x18002ba29  shr     rdx, 3
0x18002ba2d  lea     rcx, [rdx+rdx*4]
0x18002ba31  add     rcx, rcx
0x18002ba34  sub     r8, rcx
0x18002ba37  mov     rbx, [rdi+r8*8+8]
0x18002ba3c  test    rbx, rbx
0x18002ba3f  jz      short loc_18002BA61
0x18002ba41  cmp     [rbx], r9d
0x18002ba44  jz      short loc_18002BA4C
0x18002ba46  mov     rbx, [rbx+8]
0x18002ba4a  jmp     short loc_18002BA3C
0x18002ba4c  add     rbx, 10h
0x18002ba50  jz      short loc_18002BA61
0x18002ba52  cmp     qword ptr [rbx+8], 0
0x18002ba57  jnz     short loc_18002BA61
0x18002ba59  lea     rax, [rdi+4]
0x18002ba5d  mov     [rbx+8], rax
0x18002ba61  mov     rax, rbx
0x18002ba64  mov     rbx, [rsp+28h+arg_0]
0x18002ba69  add     rsp, 20h
0x18002ba6d  pop     rdi
0x18002ba6e  retn
```
