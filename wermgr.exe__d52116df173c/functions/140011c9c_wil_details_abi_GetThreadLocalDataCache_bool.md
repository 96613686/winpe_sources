# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140011c9c`
- end: `0x140011d57`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400117e0`

## callees

- `0x140010778`
- `0x140011c9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011cf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011cf2`

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
0x140011c9c  mov     [rsp+arg_0], rbx
0x140011ca1  push    rdi
0x140011ca2  sub     rsp, 20h
0x140011ca6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140011cad  xor     ebx, ebx
0x140011caf  test    rdi, rdi
0x140011cb2  jz      short loc_140011D32
0x140011cb4  cmp     [rdi+8], rbx
0x140011cb8  jnz     short loc_140011CDF
0x140011cba  mov     rcx, [rdi]; int
0x140011cbd  lea     rdx, [rsp+28h+arg_8]
0x140011cc2  mov     [rsp+28h+arg_8], rbx
0x140011cc7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140011ccc  test    eax, eax
0x140011cce  js      short loc_140011CDF
0x140011cd0  cmp     [rdi+8], rbx
0x140011cd4  jnz     short loc_140011CDF
0x140011cd6  mov     rax, [rsp+28h+arg_8]
0x140011cdb  mov     [rdi+8], rax
0x140011cdf  mov     rax, [rdi+8]
0x140011ce3  lea     rcx, [rax+20h]
0x140011ce7  neg     rax
0x140011cea  sbb     rdi, rdi
0x140011ced  and     rdi, rcx
0x140011cf0  jz      short loc_140011D32
0x140011cf2  call    cs:__imp_GetCurrentThreadId
0x140011cf8  mov     r8d, eax
0x140011cfb  mov     r9d, eax
0x140011cfe  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140011d08  shr     r8, 2
0x140011d0c  mul     r8
0x140011d0f  shr     rdx, 3
0x140011d13  lea     rcx, [rdx+rdx*4]
0x140011d17  add     rcx, rcx
0x140011d1a  sub     r8, rcx
0x140011d1d  mov     rbx, [rdi+r8*8+8]
0x140011d22  jmp     short loc_140011D2D
0x140011d24  cmp     [rbx], r9d
0x140011d27  jz      short loc_140011D40
0x140011d29  mov     rbx, [rbx+8]
0x140011d2d  test    rbx, rbx
0x140011d30  jnz     short loc_140011D24
0x140011d32  mov     rax, rbx
0x140011d35  mov     rbx, [rsp+28h+arg_0]
0x140011d3a  add     rsp, 20h
0x140011d3e  pop     rdi
0x140011d3f  retn
0x140011d40  add     rbx, 10h
0x140011d44  jz      short loc_140011D32
0x140011d46  cmp     qword ptr [rbx+8], 0
0x140011d4b  jnz     short loc_140011D32
0x140011d4d  lea     rax, [rdi+4]
0x140011d51  mov     [rbx+8], rax
0x140011d55  jmp     short loc_140011D32
```
