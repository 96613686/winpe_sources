# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x14000363c`
- end: `0x1400036f7`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002e60`

## callees

- `0x1400026bc`
- `0x14000363c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003692`
- `KERNEL32!GetCurrentThreadId` at `0x140003692`

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
0x14000363c  mov     [rsp+arg_0], rbx
0x140003641  push    rdi
0x140003642  sub     rsp, 20h
0x140003646  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x14000364d  xor     ebx, ebx
0x14000364f  test    rdi, rdi
0x140003652  jz      short loc_1400036D2
0x140003654  cmp     [rdi+8], rbx
0x140003658  jnz     short loc_14000367F
0x14000365a  mov     rcx, [rdi]
0x14000365d  lea     rdx, [rsp+28h+arg_8]
0x140003662  mov     [rsp+28h+arg_8], rbx
0x140003667  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000366c  test    eax, eax
0x14000366e  js      short loc_14000367F
0x140003670  cmp     [rdi+8], rbx
0x140003674  jnz     short loc_14000367F
0x140003676  mov     rax, [rsp+28h+arg_8]
0x14000367b  mov     [rdi+8], rax
0x14000367f  mov     rax, [rdi+8]
0x140003683  lea     rcx, [rax+20h]
0x140003687  neg     rax
0x14000368a  sbb     rdi, rdi
0x14000368d  and     rdi, rcx
0x140003690  jz      short loc_1400036D2
0x140003692  call    cs:__imp_GetCurrentThreadId
0x140003698  mov     r8d, eax
0x14000369b  mov     r9d, eax
0x14000369e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400036a8  shr     r8, 2
0x1400036ac  mul     r8
0x1400036af  shr     rdx, 3
0x1400036b3  lea     rcx, [rdx+rdx*4]
0x1400036b7  add     rcx, rcx
0x1400036ba  sub     r8, rcx
0x1400036bd  mov     rbx, [rdi+r8*8+8]
0x1400036c2  jmp     short loc_1400036CD
0x1400036c4  cmp     [rbx], r9d
0x1400036c7  jz      short loc_1400036E0
0x1400036c9  mov     rbx, [rbx+8]
0x1400036cd  test    rbx, rbx
0x1400036d0  jnz     short loc_1400036C4
0x1400036d2  mov     rax, rbx
0x1400036d5  mov     rbx, [rsp+28h+arg_0]
0x1400036da  add     rsp, 20h
0x1400036de  pop     rdi
0x1400036df  retn
0x1400036e0  add     rbx, 10h
0x1400036e4  jz      short loc_1400036D2
0x1400036e6  cmp     qword ptr [rbx+8], 0
0x1400036eb  jnz     short loc_1400036D2
0x1400036ed  lea     rax, [rdi+4]
0x1400036f1  mov     [rbx+8], rax
0x1400036f5  jmp     short loc_1400036D2
```
