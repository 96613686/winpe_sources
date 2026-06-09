# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800058dc`
- end: `0x180005997`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005100`

## callees

- `0x180003e4c`
- `0x1800058dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005932`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005932`

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
0x1800058dc  mov     [rsp+arg_0], rbx
0x1800058e1  push    rdi
0x1800058e2  sub     rsp, 20h
0x1800058e6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800058ed  xor     ebx, ebx
0x1800058ef  test    rdi, rdi
0x1800058f2  jz      short loc_180005972
0x1800058f4  cmp     [rdi+8], rbx
0x1800058f8  jnz     short loc_18000591F
0x1800058fa  mov     rcx, [rdi]
0x1800058fd  lea     rdx, [rsp+28h+arg_8]
0x180005902  mov     [rsp+28h+arg_8], rbx
0x180005907  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000590c  test    eax, eax
0x18000590e  js      short loc_18000591F
0x180005910  cmp     [rdi+8], rbx
0x180005914  jnz     short loc_18000591F
0x180005916  mov     rax, [rsp+28h+arg_8]
0x18000591b  mov     [rdi+8], rax
0x18000591f  mov     rax, [rdi+8]
0x180005923  lea     rcx, [rax+20h]
0x180005927  neg     rax
0x18000592a  sbb     rdi, rdi
0x18000592d  and     rdi, rcx
0x180005930  jz      short loc_180005972
0x180005932  call    cs:__imp_GetCurrentThreadId
0x180005938  mov     r8d, eax
0x18000593b  mov     r9d, eax
0x18000593e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005948  shr     r8, 2
0x18000594c  mul     r8
0x18000594f  shr     rdx, 3
0x180005953  lea     rcx, [rdx+rdx*4]
0x180005957  add     rcx, rcx
0x18000595a  sub     r8, rcx
0x18000595d  mov     rbx, [rdi+r8*8+8]
0x180005962  jmp     short loc_18000596D
0x180005964  cmp     [rbx], r9d
0x180005967  jz      short loc_180005980
0x180005969  mov     rbx, [rbx+8]
0x18000596d  test    rbx, rbx
0x180005970  jnz     short loc_180005964
0x180005972  mov     rax, rbx
0x180005975  mov     rbx, [rsp+28h+arg_0]
0x18000597a  add     rsp, 20h
0x18000597e  pop     rdi
0x18000597f  retn
0x180005980  add     rbx, 10h
0x180005984  jz      short loc_180005972
0x180005986  cmp     qword ptr [rbx+8], 0
0x18000598b  jnz     short loc_180005972
0x18000598d  lea     rax, [rdi+4]
0x180005991  mov     [rbx+8], rax
0x180005995  jmp     short loc_180005972
```
