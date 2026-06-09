# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180006998`
- end: `0x180006a5d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `197`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006120`

## callees

- `0x180003b34`
- `0x180006998`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800069f2`
- `KERNEL32!GetCurrentThreadId` at `0x1800069f2`

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
0x180006998  mov     [rsp+arg_0], rbx
0x18000699d  push    rdi
0x18000699e  sub     rsp, 20h
0x1800069a2  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800069a9  xor     edi, edi
0x1800069ab  test    rbx, rbx
0x1800069ae  jz      loc_180006A4E
0x1800069b4  cmp     [rbx+8], rdi
0x1800069b8  jnz     short loc_1800069DF
0x1800069ba  mov     rcx, [rbx]
0x1800069bd  lea     rdx, [rsp+28h+arg_8]
0x1800069c2  and     [rsp+28h+arg_8], rdi
0x1800069c7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800069cc  test    eax, eax
0x1800069ce  js      short loc_1800069DF
0x1800069d0  cmp     [rbx+8], rdi
0x1800069d4  jnz     short loc_1800069DF
0x1800069d6  mov     rax, [rsp+28h+arg_8]
0x1800069db  mov     [rbx+8], rax
0x1800069df  mov     rax, [rbx+8]
0x1800069e3  lea     rcx, [rax+20h]
0x1800069e7  neg     rax
0x1800069ea  sbb     rbx, rbx
0x1800069ed  and     rbx, rcx
0x1800069f0  jz      short loc_180006A4E
0x1800069f2  call    cs:__imp_GetCurrentThreadId
0x1800069f9  nop     dword ptr [rax+rax+00h]
0x1800069fe  mov     r8d, eax
0x180006a01  mov     r9d, eax
0x180006a04  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006a0e  mul     r9
0x180006a11  shr     rdx, 3
0x180006a15  lea     rcx, [rdx+rdx*4]
0x180006a19  add     rcx, rcx
0x180006a1c  sub     r8, rcx
0x180006a1f  mov     rcx, [rbx+r8*8+8]
0x180006a24  jmp     short loc_180006A2F
0x180006a26  cmp     [rcx], r9d
0x180006a29  jz      short loc_180006A36
0x180006a2b  mov     rcx, [rcx+8]
0x180006a2f  test    rcx, rcx
0x180006a32  jnz     short loc_180006A26
0x180006a34  jmp     short loc_180006A4E
0x180006a36  add     rcx, 10h
0x180006a3a  mov     rdi, rcx
0x180006a3d  jz      short loc_180006A4E
0x180006a3f  cmp     qword ptr [rcx+8], 0
0x180006a44  jnz     short loc_180006A4E
0x180006a46  lea     rax, [rbx+4]
0x180006a4a  mov     [rcx+8], rax
0x180006a4e  mov     rbx, [rsp+28h+arg_0]
0x180006a53  mov     rax, rdi
0x180006a56  add     rsp, 20h
0x180006a5a  pop     rdi
0x180006a5b  retn
```
