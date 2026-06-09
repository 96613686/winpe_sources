# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002d498`
- end: `0x18002d553`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002c1b0`

## callees

- `0x180027620`
- `0x18002d498`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002d4ee`
- `KERNEL32!GetCurrentThreadId` at `0x18002d4ee`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  unsigned __int64 v7; // [rsp+38h] [rbp+10h] BYREF

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
0x18002d498  mov     [rsp+arg_0], rbx
0x18002d49d  push    rdi
0x18002d49e  sub     rsp, 20h
0x18002d4a2  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002d4a9  xor     ebx, ebx
0x18002d4ab  test    rdi, rdi
0x18002d4ae  jz      short loc_18002D52E
0x18002d4b0  cmp     [rdi+8], rbx
0x18002d4b4  jnz     short loc_18002D4DB
0x18002d4b6  mov     rcx, [rdi]
0x18002d4b9  lea     rdx, [rsp+28h+arg_8]
0x18002d4be  mov     [rsp+28h+arg_8], rbx
0x18002d4c3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18002d4c8  test    eax, eax
0x18002d4ca  js      short loc_18002D4DB
0x18002d4cc  cmp     [rdi+8], rbx
0x18002d4d0  jnz     short loc_18002D4DB
0x18002d4d2  mov     rax, [rsp+28h+arg_8]
0x18002d4d7  mov     [rdi+8], rax
0x18002d4db  mov     rax, [rdi+8]
0x18002d4df  lea     rcx, [rax+20h]
0x18002d4e3  neg     rax
0x18002d4e6  sbb     rdi, rdi
0x18002d4e9  and     rdi, rcx
0x18002d4ec  jz      short loc_18002D52E
0x18002d4ee  call    cs:__imp_GetCurrentThreadId
0x18002d4f4  mov     r8d, eax
0x18002d4f7  mov     r9d, eax
0x18002d4fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002d504  shr     r8, 2
0x18002d508  mul     r8
0x18002d50b  shr     rdx, 3
0x18002d50f  lea     rcx, [rdx+rdx*4]
0x18002d513  add     rcx, rcx
0x18002d516  sub     r8, rcx
0x18002d519  mov     rbx, [rdi+r8*8+8]
0x18002d51e  jmp     short loc_18002D529
0x18002d520  cmp     [rbx], r9d
0x18002d523  jz      short loc_18002D53C
0x18002d525  mov     rbx, [rbx+8]
0x18002d529  test    rbx, rbx
0x18002d52c  jnz     short loc_18002D520
0x18002d52e  mov     rax, rbx
0x18002d531  mov     rbx, [rsp+28h+arg_0]
0x18002d536  add     rsp, 20h
0x18002d53a  pop     rdi
0x18002d53b  retn
0x18002d53c  add     rbx, 10h
0x18002d540  jz      short loc_18002D52E
0x18002d542  cmp     qword ptr [rbx+8], 0
0x18002d547  jnz     short loc_18002D52E
0x18002d549  lea     rax, [rdi+4]
0x18002d54d  mov     [rbx+8], rax
0x18002d551  jmp     short loc_18002D52E
```
