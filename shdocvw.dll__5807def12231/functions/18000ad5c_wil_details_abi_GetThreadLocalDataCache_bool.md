# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000ad5c`
- end: `0x18000ae19`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a820`

## callees

- `0x18000a368`
- `0x18000ad5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000adb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000adb6`

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
0x18000ad5c  mov     [rsp+arg_0], rbx
0x18000ad61  push    rdi
0x18000ad62  sub     rsp, 20h
0x18000ad66  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000ad6d  xor     ebx, ebx
0x18000ad6f  test    rdi, rdi
0x18000ad72  jz      loc_18000AE0B
0x18000ad78  cmp     [rdi+8], rbx
0x18000ad7c  jnz     short loc_18000ADA3
0x18000ad7e  mov     rcx, [rdi]
0x18000ad81  lea     rdx, [rsp+28h+arg_8]
0x18000ad86  mov     [rsp+28h+arg_8], rbx
0x18000ad8b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000ad90  test    eax, eax
0x18000ad92  js      short loc_18000ADA3
0x18000ad94  cmp     [rdi+8], rbx
0x18000ad98  jnz     short loc_18000ADA3
0x18000ad9a  mov     rax, [rsp+28h+arg_8]
0x18000ad9f  mov     [rdi+8], rax
0x18000ada3  mov     rax, [rdi+8]
0x18000ada7  lea     rcx, [rax+20h]
0x18000adab  neg     rax
0x18000adae  sbb     rdi, rdi
0x18000adb1  and     rdi, rcx
0x18000adb4  jz      short loc_18000AE0B
0x18000adb6  call    cs:__imp_GetCurrentThreadId
0x18000adbc  mov     r8d, eax
0x18000adbf  mov     r9d, eax
0x18000adc2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000adcc  shr     r8, 2
0x18000add0  mul     r8
0x18000add3  shr     rdx, 3
0x18000add7  lea     rcx, [rdx+rdx*4]
0x18000addb  add     rcx, rcx
0x18000adde  sub     r8, rcx
0x18000ade1  mov     rbx, [rdi+r8*8+8]
0x18000ade6  test    rbx, rbx
0x18000ade9  jz      short loc_18000AE0B
0x18000adeb  cmp     [rbx], r9d
0x18000adee  jz      short loc_18000ADF6
0x18000adf0  mov     rbx, [rbx+8]
0x18000adf4  jmp     short loc_18000ADE6
0x18000adf6  add     rbx, 10h
0x18000adfa  jz      short loc_18000AE0B
0x18000adfc  cmp     qword ptr [rbx+8], 0
0x18000ae01  jnz     short loc_18000AE0B
0x18000ae03  lea     rax, [rdi+4]
0x18000ae07  mov     [rbx+8], rax
0x18000ae0b  mov     rax, rbx
0x18000ae0e  mov     rbx, [rsp+28h+arg_0]
0x18000ae13  add     rsp, 20h
0x18000ae17  pop     rdi
0x18000ae18  retn
```
