# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006420`
- end: `0x1800064dd`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d60`

## callees

- `0x1800054a8`
- `0x180006420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000647a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000647a`

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
0x180006420  mov     [rsp+arg_0], rbx
0x180006425  push    rdi
0x180006426  sub     rsp, 20h
0x18000642a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180006431  xor     ebx, ebx
0x180006433  test    rdi, rdi
0x180006436  jz      loc_1800064CF
0x18000643c  cmp     [rdi+8], rbx
0x180006440  jnz     short loc_180006467
0x180006442  mov     rcx, [rdi]
0x180006445  lea     rdx, [rsp+28h+arg_8]
0x18000644a  mov     [rsp+28h+arg_8], rbx
0x18000644f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180006454  test    eax, eax
0x180006456  js      short loc_180006467
0x180006458  cmp     [rdi+8], rbx
0x18000645c  jnz     short loc_180006467
0x18000645e  mov     rax, [rsp+28h+arg_8]
0x180006463  mov     [rdi+8], rax
0x180006467  mov     rax, [rdi+8]
0x18000646b  lea     rcx, [rax+20h]
0x18000646f  neg     rax
0x180006472  sbb     rdi, rdi
0x180006475  and     rdi, rcx
0x180006478  jz      short loc_1800064CF
0x18000647a  call    cs:__imp_GetCurrentThreadId
0x180006480  mov     r8d, eax
0x180006483  mov     r9d, eax
0x180006486  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006490  shr     r8, 2
0x180006494  mul     r8
0x180006497  shr     rdx, 3
0x18000649b  lea     rcx, [rdx+rdx*4]
0x18000649f  add     rcx, rcx
0x1800064a2  sub     r8, rcx
0x1800064a5  mov     rbx, [rdi+r8*8+8]
0x1800064aa  test    rbx, rbx
0x1800064ad  jz      short loc_1800064CF
0x1800064af  cmp     [rbx], r9d
0x1800064b2  jz      short loc_1800064BA
0x1800064b4  mov     rbx, [rbx+8]
0x1800064b8  jmp     short loc_1800064AA
0x1800064ba  add     rbx, 10h
0x1800064be  jz      short loc_1800064CF
0x1800064c0  cmp     qword ptr [rbx+8], 0
0x1800064c5  jnz     short loc_1800064CF
0x1800064c7  lea     rax, [rdi+4]
0x1800064cb  mov     [rbx+8], rax
0x1800064cf  mov     rax, rbx
0x1800064d2  mov     rbx, [rsp+28h+arg_0]
0x1800064d7  add     rsp, 20h
0x1800064db  pop     rdi
0x1800064dc  retn
```
