# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000c080`
- end: `0x18000c145`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `197`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b610`

## callees

- `0x18000a204`
- `0x18000c080`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000c0da`
- `KERNEL32!GetCurrentThreadId` at `0x18000c0da`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 i; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  v2 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v10 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v10) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v10;
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
          v7 = i == -16;
          v8 = i + 16;
          v2 = v8;
          if ( !v7 && !*(_QWORD *)(v8 + 8) )
            *(_QWORD *)(v8 + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)v2;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v2;
}

```

## disassembly

```asm
0x18000c080  mov     [rsp+arg_0], rbx
0x18000c085  push    rdi
0x18000c086  sub     rsp, 20h
0x18000c08a  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000c091  xor     edi, edi
0x18000c093  test    rbx, rbx
0x18000c096  jz      loc_18000C136
0x18000c09c  cmp     [rbx+8], rdi
0x18000c0a0  jnz     short loc_18000C0C7
0x18000c0a2  mov     rcx, [rbx]
0x18000c0a5  lea     rdx, [rsp+28h+arg_8]
0x18000c0aa  and     [rsp+28h+arg_8], rdi
0x18000c0af  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000c0b4  test    eax, eax
0x18000c0b6  js      short loc_18000C0C7
0x18000c0b8  cmp     [rbx+8], rdi
0x18000c0bc  jnz     short loc_18000C0C7
0x18000c0be  mov     rax, [rsp+28h+arg_8]
0x18000c0c3  mov     [rbx+8], rax
0x18000c0c7  mov     rax, [rbx+8]
0x18000c0cb  lea     rcx, [rax+20h]
0x18000c0cf  neg     rax
0x18000c0d2  sbb     rbx, rbx
0x18000c0d5  and     rbx, rcx
0x18000c0d8  jz      short loc_18000C136
0x18000c0da  call    cs:__imp_GetCurrentThreadId
0x18000c0e1  nop     dword ptr [rax+rax+00h]
0x18000c0e6  mov     r8d, eax
0x18000c0e9  mov     r9d, eax
0x18000c0ec  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c0f6  mul     r9
0x18000c0f9  shr     rdx, 3
0x18000c0fd  lea     rcx, [rdx+rdx*4]
0x18000c101  add     rcx, rcx
0x18000c104  sub     r8, rcx
0x18000c107  mov     rcx, [rbx+r8*8+8]
0x18000c10c  jmp     short loc_18000C117
0x18000c10e  cmp     [rcx], r9d
0x18000c111  jz      short loc_18000C11E
0x18000c113  mov     rcx, [rcx+8]
0x18000c117  test    rcx, rcx
0x18000c11a  jnz     short loc_18000C10E
0x18000c11c  jmp     short loc_18000C136
0x18000c11e  add     rcx, 10h
0x18000c122  mov     rdi, rcx
0x18000c125  jz      short loc_18000C136
0x18000c127  cmp     qword ptr [rcx+8], 0
0x18000c12c  jnz     short loc_18000C136
0x18000c12e  lea     rax, [rbx+4]
0x18000c132  mov     [rcx+8], rax
0x18000c136  mov     rbx, [rsp+28h+arg_0]
0x18000c13b  mov     rax, rdi
0x18000c13e  add     rsp, 20h
0x18000c142  pop     rdi
0x18000c143  retn
```
