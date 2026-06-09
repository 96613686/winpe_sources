# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18002680c`
- end: `0x1800268c9`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025c70`

## callees

- `0x18001f014`
- `0x18002680c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026866`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026866`

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
0x18002680c  mov     [rsp+arg_0], rbx
0x180026811  push    rdi
0x180026812  sub     rsp, 20h
0x180026816  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18002681d  xor     ebx, ebx
0x18002681f  test    rdi, rdi
0x180026822  jz      loc_1800268BB
0x180026828  cmp     [rdi+8], rbx
0x18002682c  jnz     short loc_180026853
0x18002682e  mov     rcx, [rdi]
0x180026831  lea     rdx, [rsp+28h+arg_8]
0x180026836  mov     [rsp+28h+arg_8], rbx
0x18002683b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180026840  test    eax, eax
0x180026842  js      short loc_180026853
0x180026844  cmp     [rdi+8], rbx
0x180026848  jnz     short loc_180026853
0x18002684a  mov     rax, [rsp+28h+arg_8]
0x18002684f  mov     [rdi+8], rax
0x180026853  mov     rax, [rdi+8]
0x180026857  lea     rcx, [rax+20h]
0x18002685b  neg     rax
0x18002685e  sbb     rdi, rdi
0x180026861  and     rdi, rcx
0x180026864  jz      short loc_1800268BB
0x180026866  call    cs:__imp_GetCurrentThreadId
0x18002686c  mov     r8d, eax
0x18002686f  mov     r9d, eax
0x180026872  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002687c  shr     r8, 2
0x180026880  mul     r8
0x180026883  shr     rdx, 3
0x180026887  lea     rcx, [rdx+rdx*4]
0x18002688b  add     rcx, rcx
0x18002688e  sub     r8, rcx
0x180026891  mov     rbx, [rdi+r8*8+8]
0x180026896  test    rbx, rbx
0x180026899  jz      short loc_1800268BB
0x18002689b  cmp     [rbx], r9d
0x18002689e  jz      short loc_1800268A6
0x1800268a0  mov     rbx, [rbx+8]
0x1800268a4  jmp     short loc_180026896
0x1800268a6  add     rbx, 10h
0x1800268aa  jz      short loc_1800268BB
0x1800268ac  cmp     qword ptr [rbx+8], 0
0x1800268b1  jnz     short loc_1800268BB
0x1800268b3  lea     rax, [rdi+4]
0x1800268b7  mov     [rbx+8], rax
0x1800268bb  mov     rax, rbx
0x1800268be  mov     rbx, [rsp+28h+arg_0]
0x1800268c3  add     rsp, 20h
0x1800268c7  pop     rdi
0x1800268c8  retn
```
