# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180048cb8`
- end: `0x180048d7c`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800486a0`

## callees

- `0x180042164`
- `0x180048cb8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180048d12`
- `KERNEL32!GetCurrentThreadId` at `0x180048d12`

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
0x180048cb8  mov     [rsp+arg_0], rbx
0x180048cbd  push    rdi
0x180048cbe  sub     rsp, 20h
0x180048cc2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180048cc9  xor     ebx, ebx
0x180048ccb  test    rdi, rdi
0x180048cce  jz      loc_180048D6D
0x180048cd4  cmp     [rdi+8], rbx
0x180048cd8  jnz     short loc_180048CFF
0x180048cda  mov     rcx, [rdi]
0x180048cdd  lea     rdx, [rsp+28h+arg_8]
0x180048ce2  mov     [rsp+28h+arg_8], rbx
0x180048ce7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180048cec  test    eax, eax
0x180048cee  js      short loc_180048CFF
0x180048cf0  cmp     [rdi+8], rbx
0x180048cf4  jnz     short loc_180048CFF
0x180048cf6  mov     rax, [rsp+28h+arg_8]
0x180048cfb  mov     [rdi+8], rax
0x180048cff  mov     rax, [rdi+8]
0x180048d03  lea     rcx, [rax+20h]
0x180048d07  neg     rax
0x180048d0a  sbb     rdi, rdi
0x180048d0d  and     rdi, rcx
0x180048d10  jz      short loc_180048D6D
0x180048d12  call    cs:__imp_GetCurrentThreadId
0x180048d19  nop     dword ptr [rax+rax+00h]
0x180048d1e  mov     r8d, eax
0x180048d21  mov     r9d, eax
0x180048d24  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180048d2e  shr     r8, 2
0x180048d32  mul     r8
0x180048d35  shr     rdx, 3
0x180048d39  lea     rcx, [rdx+rdx*4]
0x180048d3d  add     rcx, rcx
0x180048d40  sub     r8, rcx
0x180048d43  mov     rbx, [rdi+r8*8+8]
0x180048d48  test    rbx, rbx
0x180048d4b  jz      short loc_180048D6D
0x180048d4d  cmp     [rbx], r9d
0x180048d50  jz      short loc_180048D58
0x180048d52  mov     rbx, [rbx+8]
0x180048d56  jmp     short loc_180048D48
0x180048d58  add     rbx, 10h
0x180048d5c  jz      short loc_180048D6D
0x180048d5e  cmp     qword ptr [rbx+8], 0
0x180048d63  jnz     short loc_180048D6D
0x180048d65  lea     rax, [rdi+4]
0x180048d69  mov     [rbx+8], rax
0x180048d6d  mov     rax, rbx
0x180048d70  mov     rbx, [rsp+28h+arg_0]
0x180048d75  add     rsp, 20h
0x180048d79  pop     rdi
0x180048d7a  retn
```
