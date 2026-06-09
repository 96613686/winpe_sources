# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000b868`
- end: `0x18000b923`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b0a0`

## callees

- `0x180009b78`
- `0x18000b868`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b8be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b8be`

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
0x18000b868  mov     [rsp+arg_0], rbx
0x18000b86d  push    rdi
0x18000b86e  sub     rsp, 20h
0x18000b872  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000b879  xor     ebx, ebx
0x18000b87b  test    rdi, rdi
0x18000b87e  jz      short loc_18000B8FE
0x18000b880  cmp     [rdi+8], rbx
0x18000b884  jnz     short loc_18000B8AB
0x18000b886  mov     rcx, [rdi]; int
0x18000b889  lea     rdx, [rsp+28h+arg_8]
0x18000b88e  mov     [rsp+28h+arg_8], rbx
0x18000b893  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000b898  test    eax, eax
0x18000b89a  js      short loc_18000B8AB
0x18000b89c  cmp     [rdi+8], rbx
0x18000b8a0  jnz     short loc_18000B8AB
0x18000b8a2  mov     rax, [rsp+28h+arg_8]
0x18000b8a7  mov     [rdi+8], rax
0x18000b8ab  mov     rax, [rdi+8]
0x18000b8af  lea     rcx, [rax+20h]
0x18000b8b3  neg     rax
0x18000b8b6  sbb     rdi, rdi
0x18000b8b9  and     rdi, rcx
0x18000b8bc  jz      short loc_18000B8FE
0x18000b8be  call    cs:__imp_GetCurrentThreadId
0x18000b8c4  mov     r8d, eax
0x18000b8c7  mov     r9d, eax
0x18000b8ca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b8d4  shr     r8, 2
0x18000b8d8  mul     r8
0x18000b8db  shr     rdx, 3
0x18000b8df  lea     rcx, [rdx+rdx*4]
0x18000b8e3  add     rcx, rcx
0x18000b8e6  sub     r8, rcx
0x18000b8e9  mov     rbx, [rdi+r8*8+8]
0x18000b8ee  jmp     short loc_18000B8F9
0x18000b8f0  cmp     [rbx], r9d
0x18000b8f3  jz      short loc_18000B90C
0x18000b8f5  mov     rbx, [rbx+8]
0x18000b8f9  test    rbx, rbx
0x18000b8fc  jnz     short loc_18000B8F0
0x18000b8fe  mov     rax, rbx
0x18000b901  mov     rbx, [rsp+28h+arg_0]
0x18000b906  add     rsp, 20h
0x18000b90a  pop     rdi
0x18000b90b  retn
0x18000b90c  add     rbx, 10h
0x18000b910  jz      short loc_18000B8FE
0x18000b912  cmp     qword ptr [rbx+8], 0
0x18000b917  jnz     short loc_18000B8FE
0x18000b919  lea     rax, [rdi+4]
0x18000b91d  mov     [rbx+8], rax
0x18000b921  jmp     short loc_18000B8FE
```
