# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800477dc`
- end: `0x180047899`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180047200`

## callees

- `0x180040ac0`
- `0x1800477dc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180047836`
- `KERNEL32!GetCurrentThreadId` at `0x180047836`

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
0x1800477dc  mov     [rsp+arg_0], rbx
0x1800477e1  push    rdi
0x1800477e2  sub     rsp, 20h
0x1800477e6  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800477ed  xor     ebx, ebx
0x1800477ef  test    rdi, rdi
0x1800477f2  jz      loc_18004788B
0x1800477f8  cmp     [rdi+8], rbx
0x1800477fc  jnz     short loc_180047823
0x1800477fe  mov     rcx, [rdi]
0x180047801  lea     rdx, [rsp+28h+arg_8]
0x180047806  mov     [rsp+28h+arg_8], rbx
0x18004780b  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180047810  test    eax, eax
0x180047812  js      short loc_180047823
0x180047814  cmp     [rdi+8], rbx
0x180047818  jnz     short loc_180047823
0x18004781a  mov     rax, [rsp+28h+arg_8]
0x18004781f  mov     [rdi+8], rax
0x180047823  mov     rax, [rdi+8]
0x180047827  lea     rcx, [rax+20h]
0x18004782b  neg     rax
0x18004782e  sbb     rdi, rdi
0x180047831  and     rdi, rcx
0x180047834  jz      short loc_18004788B
0x180047836  call    cs:__imp_GetCurrentThreadId
0x18004783c  mov     r8d, eax
0x18004783f  mov     r9d, eax
0x180047842  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18004784c  shr     r8, 2
0x180047850  mul     r8
0x180047853  shr     rdx, 3
0x180047857  lea     rcx, [rdx+rdx*4]
0x18004785b  add     rcx, rcx
0x18004785e  sub     r8, rcx
0x180047861  mov     rbx, [rdi+r8*8+8]
0x180047866  test    rbx, rbx
0x180047869  jz      short loc_18004788B
0x18004786b  cmp     [rbx], r9d
0x18004786e  jz      short loc_180047876
0x180047870  mov     rbx, [rbx+8]
0x180047874  jmp     short loc_180047866
0x180047876  add     rbx, 10h
0x18004787a  jz      short loc_18004788B
0x18004787c  cmp     qword ptr [rbx+8], 0
0x180047881  jnz     short loc_18004788B
0x180047883  lea     rax, [rdi+4]
0x180047887  mov     [rbx+8], rax
0x18004788b  mov     rax, rbx
0x18004788e  mov     rbx, [rsp+28h+arg_0]
0x180047893  add     rsp, 20h
0x180047897  pop     rdi
0x180047898  retn
```
