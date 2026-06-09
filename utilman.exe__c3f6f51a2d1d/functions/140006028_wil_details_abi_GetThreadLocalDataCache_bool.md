# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140006028`
- end: `0x1400060ec`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `196`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400058a0`

## callees

- `0x140004dac`
- `0x140006028`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006082`
- `KERNEL32!GetCurrentThreadId` at `0x140006082`

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
0x140006028  mov     [rsp+arg_0], rbx
0x14000602d  push    rdi
0x14000602e  sub     rsp, 20h
0x140006032  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140006039  xor     ebx, ebx
0x14000603b  test    rdi, rdi
0x14000603e  jz      loc_1400060DD
0x140006044  cmp     [rdi+8], rbx
0x140006048  jnz     short loc_14000606F
0x14000604a  mov     rcx, [rdi]
0x14000604d  lea     rdx, [rsp+28h+arg_8]
0x140006052  mov     [rsp+28h+arg_8], rbx
0x140006057  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x14000605c  test    eax, eax
0x14000605e  js      short loc_14000606F
0x140006060  cmp     [rdi+8], rbx
0x140006064  jnz     short loc_14000606F
0x140006066  mov     rax, [rsp+28h+arg_8]
0x14000606b  mov     [rdi+8], rax
0x14000606f  mov     rax, [rdi+8]
0x140006073  lea     rcx, [rax+20h]
0x140006077  neg     rax
0x14000607a  sbb     rdi, rdi
0x14000607d  and     rdi, rcx
0x140006080  jz      short loc_1400060DD
0x140006082  call    cs:__imp_GetCurrentThreadId
0x140006089  nop     dword ptr [rax+rax+00h]
0x14000608e  mov     r8d, eax
0x140006091  mov     r9d, eax
0x140006094  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000609e  shr     r8, 2
0x1400060a2  mul     r8
0x1400060a5  shr     rdx, 3
0x1400060a9  lea     rcx, [rdx+rdx*4]
0x1400060ad  add     rcx, rcx
0x1400060b0  sub     r8, rcx
0x1400060b3  mov     rbx, [rdi+r8*8+8]
0x1400060b8  test    rbx, rbx
0x1400060bb  jz      short loc_1400060DD
0x1400060bd  cmp     [rbx], r9d
0x1400060c0  jz      short loc_1400060C8
0x1400060c2  mov     rbx, [rbx+8]
0x1400060c6  jmp     short loc_1400060B8
0x1400060c8  add     rbx, 10h
0x1400060cc  jz      short loc_1400060DD
0x1400060ce  cmp     qword ptr [rbx+8], 0
0x1400060d3  jnz     short loc_1400060DD
0x1400060d5  lea     rax, [rdi+4]
0x1400060d9  mov     [rbx+8], rax
0x1400060dd  mov     rax, rbx
0x1400060e0  mov     rbx, [rsp+28h+arg_0]
0x1400060e5  add     rsp, 20h
0x1400060e9  pop     rdi
0x1400060ea  retn
```
