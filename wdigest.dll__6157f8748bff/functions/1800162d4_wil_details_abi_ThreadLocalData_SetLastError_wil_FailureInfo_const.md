# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800162d4`
- end: `0x1800163a3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014c20`

## callees

- `0x180015c30`
- `0x180016198`
- `0x1800162d4`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v3; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // r9
  __int64 i; // rcx
  unsigned __int16 v9; // dx
  volatile signed __int32 *v10; // rax

  v3 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v3 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( v3 )
    {
      for ( i = *((_QWORD *)this + 3); i != v7 + 80LL * *((unsigned __int16 *)this + 16); i += 80 )
      {
        if ( *(_DWORD *)(i + 4) > *((_DWORD *)this + 4) && *(_DWORD *)(i + 8) == *((_DWORD *)a2 + 2) )
          return;
      }
    }
    v9 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
    v10 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    *((_WORD *)this + 17) = v9;
    wil::details_abi::ThreadLocalFailureInfo::Set(
      (wil::details_abi::ThreadLocalFailureInfo *)(v7 + 80LL * v9),
      a2,
      _InterlockedIncrement(v10));
  }
}

```

## disassembly

```asm
0x1800162d4  push    rbx
0x1800162d6  push    rbp
0x1800162d7  push    rsi
0x1800162d8  push    rdi
0x1800162d9  sub     rsp, 28h
0x1800162dd  cmp     qword ptr [rcx+18h], 0
0x1800162e2  mov     rsi, rdx
0x1800162e5  mov     edi, [rcx+10h]
0x1800162e8  mov     rbx, rcx
0x1800162eb  mov     ebp, 50h ; 'P'
0x1800162f0  jnz     short loc_180016327
0x1800162f2  test    edi, edi
0x1800162f4  jz      short loc_180016327
0x1800162f6  mov     edx, 190h; dwBytes
0x1800162fb  lea     ecx, [rbp-48h]; dwFlags
0x1800162fe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180016303  mov     [rbx+18h], rax
0x180016307  test    rax, rax
0x18001630a  jz      short loc_180016327
0x18001630c  mov     dword ptr [rbx+20h], 5
0x180016313  lea     rcx, [rax+190h]
0x18001631a  jmp     short loc_180016322
0x18001631c  mov     [rax], bp
0x18001631f  add     rax, rbp
0x180016322  cmp     rax, rcx
0x180016325  jnz     short loc_18001631C
0x180016327  mov     r9, [rbx+18h]
0x18001632b  test    r9, r9
0x18001632e  jz      short loc_18001639A
0x180016330  test    edi, edi
0x180016332  jz      short loc_180016360
0x180016334  movzx   eax, word ptr [rbx+20h]
0x180016338  mov     rcx, r9
0x18001633b  lea     rdx, [rax+rax*4]
0x18001633f  shl     rdx, 4
0x180016343  add     rdx, r9
0x180016346  cmp     rcx, rdx
0x180016349  jz      short loc_180016360
0x18001634b  mov     eax, [rbx+10h]
0x18001634e  cmp     [rcx+4], eax
0x180016351  jbe     short loc_18001635B
0x180016353  mov     eax, [rsi+8]
0x180016356  cmp     [rcx+8], eax
0x180016359  jz      short loc_18001639A
0x18001635b  add     rcx, rbp
0x18001635e  jmp     short loc_180016346
0x180016360  movzx   eax, word ptr [rbx+22h]
0x180016364  xor     edx, edx
0x180016366  movzx   ecx, word ptr [rbx+20h]
0x18001636a  inc     eax
0x18001636c  div     ecx
0x18001636e  mov     rax, [rbx+8]
0x180016372  mov     r8d, 1
0x180016378  mov     [rbx+22h], dx
0x18001637c  lock xadd [rax], r8d
0x180016381  movzx   eax, dx
0x180016384  inc     r8d; unsigned int
0x180016387  mov     rdx, rsi; struct wil::FailureInfo *
0x18001638a  lea     rcx, [rax+rax*4]
0x18001638e  shl     rcx, 4
0x180016392  add     rcx, r9; this
0x180016395  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001639a  add     rsp, 28h
0x18001639e  pop     rdi
0x18001639f  pop     rsi
0x1800163a0  pop     rbp
0x1800163a1  pop     rbx
0x1800163a2  retn
```
