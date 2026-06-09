# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180015ac8`
- end: `0x180015b85`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015880`

## callees

- `0x180015490`
- `0x180015ac8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180015b22`
- `KERNEL32!GetCurrentThreadId` at `0x180015b22`

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
0x180015ac8  mov     [rsp+arg_0], rbx
0x180015acd  push    rdi
0x180015ace  sub     rsp, 20h
0x180015ad2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180015ad9  xor     ebx, ebx
0x180015adb  test    rdi, rdi
0x180015ade  jz      loc_180015B77
0x180015ae4  cmp     [rdi+8], rbx
0x180015ae8  jnz     short loc_180015B0F
0x180015aea  mov     rcx, [rdi]
0x180015aed  lea     rdx, [rsp+28h+arg_8]
0x180015af2  mov     [rsp+28h+arg_8], rbx
0x180015af7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180015afc  test    eax, eax
0x180015afe  js      short loc_180015B0F
0x180015b00  cmp     [rdi+8], rbx
0x180015b04  jnz     short loc_180015B0F
0x180015b06  mov     rax, [rsp+28h+arg_8]
0x180015b0b  mov     [rdi+8], rax
0x180015b0f  mov     rax, [rdi+8]
0x180015b13  lea     rcx, [rax+20h]
0x180015b17  neg     rax
0x180015b1a  sbb     rdi, rdi
0x180015b1d  and     rdi, rcx
0x180015b20  jz      short loc_180015B77
0x180015b22  call    cs:__imp_GetCurrentThreadId
0x180015b28  mov     r8d, eax
0x180015b2b  mov     r9d, eax
0x180015b2e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180015b38  shr     r8, 2
0x180015b3c  mul     r8
0x180015b3f  shr     rdx, 3
0x180015b43  lea     rcx, [rdx+rdx*4]
0x180015b47  add     rcx, rcx
0x180015b4a  sub     r8, rcx
0x180015b4d  mov     rbx, [rdi+r8*8+8]
0x180015b52  test    rbx, rbx
0x180015b55  jz      short loc_180015B77
0x180015b57  cmp     [rbx], r9d
0x180015b5a  jz      short loc_180015B62
0x180015b5c  mov     rbx, [rbx+8]
0x180015b60  jmp     short loc_180015B52
0x180015b62  add     rbx, 10h
0x180015b66  jz      short loc_180015B77
0x180015b68  cmp     qword ptr [rbx+8], 0
0x180015b6d  jnz     short loc_180015B77
0x180015b6f  lea     rax, [rdi+4]
0x180015b73  mov     [rbx+8], rax
0x180015b77  mov     rax, rbx
0x180015b7a  mov     rbx, [rsp+28h+arg_0]
0x180015b7f  add     rsp, 20h
0x180015b83  pop     rdi
0x180015b84  retn
```
