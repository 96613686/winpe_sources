# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180011eec`
- end: `0x180011fa7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011710`

## callees

- `0x18001078c`
- `0x180011eec`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180011f42`
- `KERNEL32!GetCurrentThreadId` at `0x180011f42`

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
0x180011eec  mov     [rsp+arg_0], rbx
0x180011ef1  push    rdi
0x180011ef2  sub     rsp, 20h
0x180011ef6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180011efd  xor     ebx, ebx
0x180011eff  test    rdi, rdi
0x180011f02  jz      short loc_180011F82
0x180011f04  cmp     [rdi+8], rbx
0x180011f08  jnz     short loc_180011F2F
0x180011f0a  mov     rcx, [rdi]
0x180011f0d  lea     rdx, [rsp+28h+arg_8]
0x180011f12  mov     [rsp+28h+arg_8], rbx
0x180011f17  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180011f1c  test    eax, eax
0x180011f1e  js      short loc_180011F2F
0x180011f20  cmp     [rdi+8], rbx
0x180011f24  jnz     short loc_180011F2F
0x180011f26  mov     rax, [rsp+28h+arg_8]
0x180011f2b  mov     [rdi+8], rax
0x180011f2f  mov     rax, [rdi+8]
0x180011f33  lea     rcx, [rax+20h]
0x180011f37  neg     rax
0x180011f3a  sbb     rdi, rdi
0x180011f3d  and     rdi, rcx
0x180011f40  jz      short loc_180011F82
0x180011f42  call    cs:__imp_GetCurrentThreadId
0x180011f48  mov     r8d, eax
0x180011f4b  mov     r9d, eax
0x180011f4e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180011f58  shr     r8, 2
0x180011f5c  mul     r8
0x180011f5f  shr     rdx, 3
0x180011f63  lea     rcx, [rdx+rdx*4]
0x180011f67  add     rcx, rcx
0x180011f6a  sub     r8, rcx
0x180011f6d  mov     rbx, [rdi+r8*8+8]
0x180011f72  jmp     short loc_180011F7D
0x180011f74  cmp     [rbx], r9d
0x180011f77  jz      short loc_180011F90
0x180011f79  mov     rbx, [rbx+8]
0x180011f7d  test    rbx, rbx
0x180011f80  jnz     short loc_180011F74
0x180011f82  mov     rax, rbx
0x180011f85  mov     rbx, [rsp+28h+arg_0]
0x180011f8a  add     rsp, 20h
0x180011f8e  pop     rdi
0x180011f8f  retn
0x180011f90  add     rbx, 10h
0x180011f94  jz      short loc_180011F82
0x180011f96  cmp     qword ptr [rbx+8], 0
0x180011f9b  jnz     short loc_180011F82
0x180011f9d  lea     rax, [rdi+4]
0x180011fa1  mov     [rbx+8], rax
0x180011fa5  jmp     short loc_180011F82
```
