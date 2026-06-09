# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400048fc`
- end: `0x1400049b7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004120`

## callees

- `0x1400036fc`
- `0x1400048fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004952`
- `KERNEL32!GetCurrentThreadId` at `0x140004952`

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
0x1400048fc  mov     [rsp+arg_0], rbx
0x140004901  push    rdi
0x140004902  sub     rsp, 20h
0x140004906  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000490d  xor     ebx, ebx
0x14000490f  test    rdi, rdi
0x140004912  jz      short loc_140004992
0x140004914  cmp     [rdi+8], rbx
0x140004918  jnz     short loc_14000493F
0x14000491a  mov     rcx, [rdi]
0x14000491d  lea     rdx, [rsp+28h+arg_8]
0x140004922  mov     [rsp+28h+arg_8], rbx
0x140004927  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000492c  test    eax, eax
0x14000492e  js      short loc_14000493F
0x140004930  cmp     [rdi+8], rbx
0x140004934  jnz     short loc_14000493F
0x140004936  mov     rax, [rsp+28h+arg_8]
0x14000493b  mov     [rdi+8], rax
0x14000493f  mov     rax, [rdi+8]
0x140004943  lea     rcx, [rax+20h]
0x140004947  neg     rax
0x14000494a  sbb     rdi, rdi
0x14000494d  and     rdi, rcx
0x140004950  jz      short loc_140004992
0x140004952  call    cs:__imp_GetCurrentThreadId
0x140004958  mov     r8d, eax
0x14000495b  mov     r9d, eax
0x14000495e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004968  shr     r8, 2
0x14000496c  mul     r8
0x14000496f  shr     rdx, 3
0x140004973  lea     rcx, [rdx+rdx*4]
0x140004977  add     rcx, rcx
0x14000497a  sub     r8, rcx
0x14000497d  mov     rbx, [rdi+r8*8+8]
0x140004982  jmp     short loc_14000498D
0x140004984  cmp     [rbx], r9d
0x140004987  jz      short loc_1400049A0
0x140004989  mov     rbx, [rbx+8]
0x14000498d  test    rbx, rbx
0x140004990  jnz     short loc_140004984
0x140004992  mov     rax, rbx
0x140004995  mov     rbx, [rsp+28h+arg_0]
0x14000499a  add     rsp, 20h
0x14000499e  pop     rdi
0x14000499f  retn
0x1400049a0  add     rbx, 10h
0x1400049a4  jz      short loc_140004992
0x1400049a6  cmp     qword ptr [rbx+8], 0
0x1400049ab  jnz     short loc_140004992
0x1400049ad  lea     rax, [rdi+4]
0x1400049b1  mov     [rbx+8], rax
0x1400049b5  jmp     short loc_140004992
```
