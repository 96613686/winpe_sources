# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180025b40`
- end: `0x180025c0e`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `206`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800253b0`

## callees

- `0x180024a60`
- `0x180025b40`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180025ba2`
- `KERNEL32!GetCurrentThreadId` at `0x180025ba2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v3 + 4;
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
0x180025b40  mov     rax, rsp
0x180025b43  push    rdi
0x180025b44  sub     rsp, 30h
0x180025b48  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180025b50  mov     [rax+8], rbx
0x180025b54  xor     ebx, ebx
0x180025b56  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180025b5d  test    rdi, rdi
0x180025b60  jz      loc_180025BE8
0x180025b66  cmp     [rdi+8], rbx
0x180025b6a  jnz     short loc_180025B8F
0x180025b6c  mov     [rax+10h], rbx
0x180025b70  lea     rdx, [rax+10h]
0x180025b74  mov     rcx, [rdi]
0x180025b77  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180025b7c  test    eax, eax
0x180025b7e  js      short loc_180025B8F
0x180025b80  cmp     [rdi+8], rbx
0x180025b84  jnz     short loc_180025B8F
0x180025b86  mov     rax, [rsp+38h+arg_8]
0x180025b8b  mov     [rdi+8], rax
0x180025b8f  mov     rcx, [rdi+8]
0x180025b93  lea     rax, [rcx+20h]
0x180025b97  neg     rcx
0x180025b9a  sbb     rdi, rdi
0x180025b9d  and     rdi, rax
0x180025ba0  jz      short loc_180025BE8
0x180025ba2  call    cs:__imp_GetCurrentThreadId
0x180025ba9  nop     dword ptr [rax+rax+00h]
0x180025bae  mov     r9d, eax
0x180025bb1  mov     r8d, eax
0x180025bb4  shr     r8, 2
0x180025bb8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180025bc2  mul     r8
0x180025bc5  shr     rdx, 3
0x180025bc9  lea     rcx, [rdx+rdx*4]
0x180025bcd  add     rcx, rcx
0x180025bd0  sub     r8, rcx
0x180025bd3  mov     rbx, [rdi+r8*8+8]
0x180025bd8  jmp     short loc_180025BE3
0x180025bda  cmp     [rbx], r9d
0x180025bdd  jz      short loc_180025BF7
0x180025bdf  mov     rbx, [rbx+8]
0x180025be3  test    rbx, rbx
0x180025be6  jnz     short loc_180025BDA
0x180025be8  mov     rax, rbx
0x180025beb  mov     rbx, [rsp+38h+arg_0]
0x180025bf0  add     rsp, 30h
0x180025bf4  pop     rdi
0x180025bf5  retn
0x180025bf7  add     rbx, 10h
0x180025bfb  jz      short loc_180025BE8
0x180025bfd  cmp     qword ptr [rbx+8], 0
0x180025c02  jnz     short loc_180025BE8
0x180025c04  lea     rax, [rdi+4]
0x180025c08  mov     [rbx+8], rax
0x180025c0c  jmp     short loc_180025BE8
```
