# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18001ae4c`
- end: `0x18001af07`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a590`

## callees

- `0x180019cb8`
- `0x18001ae4c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001aea2`
- `KERNEL32!GetCurrentThreadId` at `0x18001aea2`

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
0x18001ae4c  mov     [rsp+arg_0], rbx
0x18001ae51  push    rdi
0x18001ae52  sub     rsp, 20h
0x18001ae56  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18001ae5d  xor     ebx, ebx
0x18001ae5f  test    rdi, rdi
0x18001ae62  jz      short loc_18001AEE2
0x18001ae64  cmp     [rdi+8], rbx
0x18001ae68  jnz     short loc_18001AE8F
0x18001ae6a  mov     rcx, [rdi]
0x18001ae6d  lea     rdx, [rsp+28h+arg_8]
0x18001ae72  mov     [rsp+28h+arg_8], rbx
0x18001ae77  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18001ae7c  test    eax, eax
0x18001ae7e  js      short loc_18001AE8F
0x18001ae80  cmp     [rdi+8], rbx
0x18001ae84  jnz     short loc_18001AE8F
0x18001ae86  mov     rax, [rsp+28h+arg_8]
0x18001ae8b  mov     [rdi+8], rax
0x18001ae8f  mov     rax, [rdi+8]
0x18001ae93  lea     rcx, [rax+20h]
0x18001ae97  neg     rax
0x18001ae9a  sbb     rdi, rdi
0x18001ae9d  and     rdi, rcx
0x18001aea0  jz      short loc_18001AEE2
0x18001aea2  call    cs:__imp_GetCurrentThreadId
0x18001aea8  mov     r8d, eax
0x18001aeab  mov     r9d, eax
0x18001aeae  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001aeb8  shr     r8, 2
0x18001aebc  mul     r8
0x18001aebf  shr     rdx, 3
0x18001aec3  lea     rcx, [rdx+rdx*4]
0x18001aec7  add     rcx, rcx
0x18001aeca  sub     r8, rcx
0x18001aecd  mov     rbx, [rdi+r8*8+8]
0x18001aed2  jmp     short loc_18001AEDD
0x18001aed4  cmp     [rbx], r9d
0x18001aed7  jz      short loc_18001AEF0
0x18001aed9  mov     rbx, [rbx+8]
0x18001aedd  test    rbx, rbx
0x18001aee0  jnz     short loc_18001AED4
0x18001aee2  mov     rax, rbx
0x18001aee5  mov     rbx, [rsp+28h+arg_0]
0x18001aeea  add     rsp, 20h
0x18001aeee  pop     rdi
0x18001aeef  retn
0x18001aef0  add     rbx, 10h
0x18001aef4  jz      short loc_18001AEE2
0x18001aef6  cmp     qword ptr [rbx+8], 0
0x18001aefb  jnz     short loc_18001AEE2
0x18001aefd  lea     rax, [rdi+4]
0x18001af01  mov     [rbx+8], rax
0x18001af05  jmp     short loc_18001AEE2
```
