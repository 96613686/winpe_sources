# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800098c8`
- end: `0x18000998d`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `197`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009020`

## callees

- `0x18000794c`
- `0x1800098c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180009922`
- `KERNEL32!GetCurrentThreadId` at `0x180009922`

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
0x1800098c8  mov     [rsp+arg_0], rbx
0x1800098cd  push    rdi
0x1800098ce  sub     rsp, 20h
0x1800098d2  mov     rbx, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800098d9  xor     edi, edi
0x1800098db  test    rbx, rbx
0x1800098de  jz      loc_18000997E
0x1800098e4  cmp     [rbx+8], rdi
0x1800098e8  jnz     short loc_18000990F
0x1800098ea  mov     rcx, [rbx]
0x1800098ed  lea     rdx, [rsp+28h+arg_8]
0x1800098f2  and     [rsp+28h+arg_8], rdi
0x1800098f7  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800098fc  test    eax, eax
0x1800098fe  js      short loc_18000990F
0x180009900  cmp     [rbx+8], rdi
0x180009904  jnz     short loc_18000990F
0x180009906  mov     rax, [rsp+28h+arg_8]
0x18000990b  mov     [rbx+8], rax
0x18000990f  mov     rax, [rbx+8]
0x180009913  lea     rcx, [rax+20h]
0x180009917  neg     rax
0x18000991a  sbb     rbx, rbx
0x18000991d  and     rbx, rcx
0x180009920  jz      short loc_18000997E
0x180009922  call    cs:__imp_GetCurrentThreadId
0x180009929  nop     dword ptr [rax+rax+00h]
0x18000992e  mov     r8d, eax
0x180009931  mov     r9d, eax
0x180009934  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000993e  mul     r9
0x180009941  shr     rdx, 3
0x180009945  lea     rcx, [rdx+rdx*4]
0x180009949  add     rcx, rcx
0x18000994c  sub     r8, rcx
0x18000994f  mov     rcx, [rbx+r8*8+8]
0x180009954  jmp     short loc_18000995F
0x180009956  cmp     [rcx], r9d
0x180009959  jz      short loc_180009966
0x18000995b  mov     rcx, [rcx+8]
0x18000995f  test    rcx, rcx
0x180009962  jnz     short loc_180009956
0x180009964  jmp     short loc_18000997E
0x180009966  add     rcx, 10h
0x18000996a  mov     rdi, rcx
0x18000996d  jz      short loc_18000997E
0x18000996f  cmp     qword ptr [rcx+8], 0
0x180009974  jnz     short loc_18000997E
0x180009976  lea     rax, [rbx+4]
0x18000997a  mov     [rcx+8], rax
0x18000997e  mov     rbx, [rsp+28h+arg_0]
0x180009983  mov     rax, rdi
0x180009986  add     rsp, 20h
0x18000998a  pop     rdi
0x18000998b  retn
```
