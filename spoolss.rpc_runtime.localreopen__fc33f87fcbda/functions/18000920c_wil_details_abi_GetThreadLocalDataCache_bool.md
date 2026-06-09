# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000920c`
- end: `0x1800092d0`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800088e0`

## callees

- `0x1800078cc`
- `0x18000920c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009266`

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
0x18000920c  mov     [rsp+arg_0], rbx
0x180009211  push    rdi
0x180009212  sub     rsp, 20h
0x180009216  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000921d  xor     ebx, ebx
0x18000921f  test    rdi, rdi
0x180009222  jz      loc_1800092C1
0x180009228  cmp     [rdi+8], rbx
0x18000922c  jnz     short loc_180009253
0x18000922e  mov     rcx, [rdi]
0x180009231  lea     rdx, [rsp+28h+arg_8]
0x180009236  mov     [rsp+28h+arg_8], rbx
0x18000923b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180009240  test    eax, eax
0x180009242  js      short loc_180009253
0x180009244  cmp     [rdi+8], rbx
0x180009248  jnz     short loc_180009253
0x18000924a  mov     rax, [rsp+28h+arg_8]
0x18000924f  mov     [rdi+8], rax
0x180009253  mov     rax, [rdi+8]
0x180009257  lea     rcx, [rax+20h]
0x18000925b  neg     rax
0x18000925e  sbb     rdi, rdi
0x180009261  and     rdi, rcx
0x180009264  jz      short loc_1800092C1
0x180009266  call    cs:__imp_GetCurrentThreadId
0x18000926d  nop     dword ptr [rax+rax+00h]
0x180009272  mov     r8d, eax
0x180009275  mov     r9d, eax
0x180009278  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009282  shr     r8, 2
0x180009286  mul     r8
0x180009289  shr     rdx, 3
0x18000928d  lea     rcx, [rdx+rdx*4]
0x180009291  add     rcx, rcx
0x180009294  sub     r8, rcx
0x180009297  mov     rbx, [rdi+r8*8+8]
0x18000929c  test    rbx, rbx
0x18000929f  jz      short loc_1800092C1
0x1800092a1  cmp     [rbx], r9d
0x1800092a4  jz      short loc_1800092AC
0x1800092a6  mov     rbx, [rbx+8]
0x1800092aa  jmp     short loc_18000929C
0x1800092ac  add     rbx, 10h
0x1800092b0  jz      short loc_1800092C1
0x1800092b2  cmp     qword ptr [rbx+8], 0
0x1800092b7  jnz     short loc_1800092C1
0x1800092b9  lea     rax, [rdi+4]
0x1800092bd  mov     [rbx+8], rax
0x1800092c1  mov     rax, rbx
0x1800092c4  mov     rbx, [rsp+28h+arg_0]
0x1800092c9  add     rsp, 20h
0x1800092cd  pop     rdi
0x1800092ce  retn
```
