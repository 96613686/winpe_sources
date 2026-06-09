# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180004070`
- end: `0x180004127`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004230`

## callees

- `0x180004070`
- `0x180004dfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040c6`

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
      for ( i = *(_QWORD *)(v4 + 8 * (CurrentThreadId % 0xAuLL) + 8); i; i = *(_QWORD *)(i + 8) )
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
0x180004070  mov     [rsp+arg_0], rbx
0x180004075  push    rdi
0x180004076  sub     rsp, 20h
0x18000407a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180004081  xor     ebx, ebx
0x180004083  test    rdi, rdi
0x180004086  jz      short loc_180004102
0x180004088  cmp     [rdi+8], rbx
0x18000408c  jnz     short loc_1800040B3
0x18000408e  mov     rcx, [rdi]
0x180004091  lea     rdx, [rsp+28h+arg_8]
0x180004096  mov     [rsp+28h+arg_8], rbx
0x18000409b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800040a0  test    eax, eax
0x1800040a2  js      short loc_1800040B3
0x1800040a4  cmp     [rdi+8], rbx
0x1800040a8  jnz     short loc_1800040B3
0x1800040aa  mov     rax, [rsp+28h+arg_8]
0x1800040af  mov     [rdi+8], rax
0x1800040b3  mov     rax, [rdi+8]
0x1800040b7  lea     rcx, [rax+20h]
0x1800040bb  neg     rax
0x1800040be  sbb     rdi, rdi
0x1800040c1  and     rdi, rcx
0x1800040c4  jz      short loc_180004102
0x1800040c6  call    cs:__imp_GetCurrentThreadId
0x1800040cc  mov     r8d, eax
0x1800040cf  mov     r9d, eax
0x1800040d2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800040dc  mul     r9
0x1800040df  shr     rdx, 3
0x1800040e3  lea     rcx, [rdx+rdx*4]
0x1800040e7  add     rcx, rcx
0x1800040ea  sub     r8, rcx
0x1800040ed  mov     rbx, [rdi+r8*8+8]
0x1800040f2  jmp     short loc_1800040FD
0x1800040f4  cmp     [rbx], r9d
0x1800040f7  jz      short loc_180004110
0x1800040f9  mov     rbx, [rbx+8]
0x1800040fd  test    rbx, rbx
0x180004100  jnz     short loc_1800040F4
0x180004102  mov     rax, rbx
0x180004105  mov     rbx, [rsp+28h+arg_0]
0x18000410a  add     rsp, 20h
0x18000410e  pop     rdi
0x18000410f  retn
0x180004110  add     rbx, 10h
0x180004114  jz      short loc_180004102
0x180004116  cmp     qword ptr [rbx+8], 0
0x18000411b  jnz     short loc_180004102
0x18000411d  lea     rax, [rdi+4]
0x180004121  mov     [rbx+8], rax
0x180004125  jmp     short loc_180004102
```
