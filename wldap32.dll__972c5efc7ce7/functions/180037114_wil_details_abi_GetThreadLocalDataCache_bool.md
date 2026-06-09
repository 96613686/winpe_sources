# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180037114`
- end: `0x1800371d8`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180036ad0`

## callees

- `0x180036134`
- `0x180037114`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003716e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003716e`

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
0x180037114  mov     [rsp+arg_0], rbx
0x180037119  push    rdi
0x18003711a  sub     rsp, 20h
0x18003711e  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180037125  xor     ebx, ebx
0x180037127  test    rdi, rdi
0x18003712a  jz      loc_1800371C9
0x180037130  cmp     [rdi+8], rbx
0x180037134  jnz     short loc_18003715B
0x180037136  mov     rcx, [rdi]
0x180037139  lea     rdx, [rsp+28h+arg_8]
0x18003713e  mov     [rsp+28h+arg_8], rbx
0x180037143  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180037148  test    eax, eax
0x18003714a  js      short loc_18003715B
0x18003714c  cmp     [rdi+8], rbx
0x180037150  jnz     short loc_18003715B
0x180037152  mov     rax, [rsp+28h+arg_8]
0x180037157  mov     [rdi+8], rax
0x18003715b  mov     rax, [rdi+8]
0x18003715f  lea     rcx, [rax+20h]
0x180037163  neg     rax
0x180037166  sbb     rdi, rdi
0x180037169  and     rdi, rcx
0x18003716c  jz      short loc_1800371C9
0x18003716e  call    cs:__imp_GetCurrentThreadId
0x180037175  nop     dword ptr [rax+rax+00h]
0x18003717a  mov     r8d, eax
0x18003717d  mov     r9d, eax
0x180037180  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003718a  shr     r8, 2
0x18003718e  mul     r8
0x180037191  shr     rdx, 3
0x180037195  lea     rcx, [rdx+rdx*4]
0x180037199  add     rcx, rcx
0x18003719c  sub     r8, rcx
0x18003719f  mov     rbx, [rdi+r8*8+8]
0x1800371a4  test    rbx, rbx
0x1800371a7  jz      short loc_1800371C9
0x1800371a9  cmp     [rbx], r9d
0x1800371ac  jz      short loc_1800371B4
0x1800371ae  mov     rbx, [rbx+8]
0x1800371b2  jmp     short loc_1800371A4
0x1800371b4  add     rbx, 10h
0x1800371b8  jz      short loc_1800371C9
0x1800371ba  cmp     qword ptr [rbx+8], 0
0x1800371bf  jnz     short loc_1800371C9
0x1800371c1  lea     rax, [rdi+4]
0x1800371c5  mov     [rbx+8], rax
0x1800371c9  mov     rax, rbx
0x1800371cc  mov     rbx, [rsp+28h+arg_0]
0x1800371d1  add     rsp, 20h
0x1800371d5  pop     rdi
0x1800371d6  retn
```
