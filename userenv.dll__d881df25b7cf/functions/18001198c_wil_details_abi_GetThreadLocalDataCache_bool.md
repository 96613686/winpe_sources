# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001198c`
- end: `0x180011a50`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dd28`

## callees

- `0x1800114e8`
- `0x18001198c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800119e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800119e6`

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
0x18001198c  mov     [rsp+arg_0], rbx
0x180011991  push    rdi
0x180011992  sub     rsp, 20h
0x180011996  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001199d  xor     ebx, ebx
0x18001199f  test    rdi, rdi
0x1800119a2  jz      loc_180011A41
0x1800119a8  cmp     [rdi+8], rbx
0x1800119ac  jnz     short loc_1800119D3
0x1800119ae  mov     rcx, [rdi]
0x1800119b1  lea     rdx, [rsp+28h+arg_8]
0x1800119b6  mov     [rsp+28h+arg_8], rbx
0x1800119bb  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800119c0  test    eax, eax
0x1800119c2  js      short loc_1800119D3
0x1800119c4  cmp     [rdi+8], rbx
0x1800119c8  jnz     short loc_1800119D3
0x1800119ca  mov     rax, [rsp+28h+arg_8]
0x1800119cf  mov     [rdi+8], rax
0x1800119d3  mov     rax, [rdi+8]
0x1800119d7  lea     rcx, [rax+20h]
0x1800119db  neg     rax
0x1800119de  sbb     rdi, rdi
0x1800119e1  and     rdi, rcx
0x1800119e4  jz      short loc_180011A41
0x1800119e6  call    cs:__imp_GetCurrentThreadId
0x1800119ed  nop     dword ptr [rax+rax+00h]
0x1800119f2  mov     r8d, eax
0x1800119f5  mov     r9d, eax
0x1800119f8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180011a02  shr     r8, 2
0x180011a06  mul     r8
0x180011a09  shr     rdx, 3
0x180011a0d  lea     rcx, [rdx+rdx*4]
0x180011a11  add     rcx, rcx
0x180011a14  sub     r8, rcx
0x180011a17  mov     rbx, [rdi+r8*8+8]
0x180011a1c  test    rbx, rbx
0x180011a1f  jz      short loc_180011A41
0x180011a21  cmp     [rbx], r9d
0x180011a24  jz      short loc_180011A2C
0x180011a26  mov     rbx, [rbx+8]
0x180011a2a  jmp     short loc_180011A1C
0x180011a2c  add     rbx, 10h
0x180011a30  jz      short loc_180011A41
0x180011a32  cmp     qword ptr [rbx+8], 0
0x180011a37  jnz     short loc_180011A41
0x180011a39  lea     rax, [rdi+4]
0x180011a3d  mov     [rbx+8], rax
0x180011a41  mov     rax, rbx
0x180011a44  mov     rbx, [rsp+28h+arg_0]
0x180011a49  add     rsp, 20h
0x180011a4d  pop     rdi
0x180011a4e  retn
```
