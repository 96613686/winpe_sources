# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140004550`
- end: `0x140004607`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `183`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004710`

## callees

- `0x140004550`
- `0x140005738`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400045a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400045a6`

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
0x140004550  mov     [rsp+arg_0], rbx
0x140004555  push    rdi
0x140004556  sub     rsp, 20h
0x14000455a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140004561  xor     ebx, ebx
0x140004563  test    rdi, rdi
0x140004566  jz      short loc_1400045E2
0x140004568  cmp     [rdi+8], rbx
0x14000456c  jnz     short loc_140004593
0x14000456e  mov     rcx, [rdi]
0x140004571  lea     rdx, [rsp+28h+arg_8]
0x140004576  mov     [rsp+28h+arg_8], rbx
0x14000457b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140004580  test    eax, eax
0x140004582  js      short loc_140004593
0x140004584  cmp     [rdi+8], rbx
0x140004588  jnz     short loc_140004593
0x14000458a  mov     rax, [rsp+28h+arg_8]
0x14000458f  mov     [rdi+8], rax
0x140004593  mov     rax, [rdi+8]
0x140004597  lea     rcx, [rax+20h]
0x14000459b  neg     rax
0x14000459e  sbb     rdi, rdi
0x1400045a1  and     rdi, rcx
0x1400045a4  jz      short loc_1400045E2
0x1400045a6  call    cs:__imp_GetCurrentThreadId
0x1400045ac  mov     r8d, eax
0x1400045af  mov     r9d, eax
0x1400045b2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400045bc  mul     r9
0x1400045bf  shr     rdx, 3
0x1400045c3  lea     rcx, [rdx+rdx*4]
0x1400045c7  add     rcx, rcx
0x1400045ca  sub     r8, rcx
0x1400045cd  mov     rbx, [rdi+r8*8+8]
0x1400045d2  jmp     short loc_1400045DD
0x1400045d4  cmp     [rbx], r9d
0x1400045d7  jz      short loc_1400045F0
0x1400045d9  mov     rbx, [rbx+8]
0x1400045dd  test    rbx, rbx
0x1400045e0  jnz     short loc_1400045D4
0x1400045e2  mov     rax, rbx
0x1400045e5  mov     rbx, [rsp+28h+arg_0]
0x1400045ea  add     rsp, 20h
0x1400045ee  pop     rdi
0x1400045ef  retn
0x1400045f0  add     rbx, 10h
0x1400045f4  jz      short loc_1400045E2
0x1400045f6  cmp     qword ptr [rbx+8], 0
0x1400045fb  jnz     short loc_1400045E2
0x1400045fd  lea     rax, [rdi+4]
0x140004601  mov     [rbx+8], rax
0x140004605  jmp     short loc_1400045E2
```
