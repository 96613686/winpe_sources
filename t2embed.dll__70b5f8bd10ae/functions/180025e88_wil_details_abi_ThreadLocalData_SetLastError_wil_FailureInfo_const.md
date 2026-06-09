# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180025e88`
- end: `0x180025f57`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180024310`

## callees

- `0x18002551c`
- `0x180025aec`
- `0x180025e88`

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
0x180025e88  push    rbx
0x180025e8a  push    rbp
0x180025e8b  push    rsi
0x180025e8c  push    rdi
0x180025e8d  sub     rsp, 28h
0x180025e91  cmp     qword ptr [rcx+18h], 0
0x180025e96  mov     rsi, rdx
0x180025e99  mov     edi, [rcx+10h]
0x180025e9c  mov     rbx, rcx
0x180025e9f  mov     ebp, 50h ; 'P'
0x180025ea4  jnz     short loc_180025EDB
0x180025ea6  test    edi, edi
0x180025ea8  jz      short loc_180025EDB
0x180025eaa  mov     edx, 190h; dwBytes
0x180025eaf  lea     ecx, [rbp-48h]; dwFlags
0x180025eb2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180025eb7  mov     [rbx+18h], rax
0x180025ebb  test    rax, rax
0x180025ebe  jz      short loc_180025EDB
0x180025ec0  mov     dword ptr [rbx+20h], 5
0x180025ec7  lea     rcx, [rax+190h]
0x180025ece  jmp     short loc_180025ED6
0x180025ed0  mov     [rax], bp
0x180025ed3  add     rax, rbp
0x180025ed6  cmp     rax, rcx
0x180025ed9  jnz     short loc_180025ED0
0x180025edb  mov     r9, [rbx+18h]
0x180025edf  test    r9, r9
0x180025ee2  jz      short loc_180025F4E
0x180025ee4  test    edi, edi
0x180025ee6  jz      short loc_180025F14
0x180025ee8  movzx   eax, word ptr [rbx+20h]
0x180025eec  mov     rcx, r9
0x180025eef  lea     rdx, [rax+rax*4]
0x180025ef3  shl     rdx, 4
0x180025ef7  add     rdx, r9
0x180025efa  cmp     rcx, rdx
0x180025efd  jz      short loc_180025F14
0x180025eff  mov     eax, [rbx+10h]
0x180025f02  cmp     [rcx+4], eax
0x180025f05  jbe     short loc_180025F0F
0x180025f07  mov     eax, [rsi+8]
0x180025f0a  cmp     [rcx+8], eax
0x180025f0d  jz      short loc_180025F4E
0x180025f0f  add     rcx, rbp
0x180025f12  jmp     short loc_180025EFA
0x180025f14  movzx   eax, word ptr [rbx+22h]
0x180025f18  xor     edx, edx
0x180025f1a  movzx   ecx, word ptr [rbx+20h]
0x180025f1e  inc     eax
0x180025f20  div     ecx
0x180025f22  mov     rax, [rbx+8]
0x180025f26  mov     r8d, 1
0x180025f2c  mov     [rbx+22h], dx
0x180025f30  lock xadd [rax], r8d
0x180025f35  movzx   eax, dx
0x180025f38  inc     r8d; unsigned int
0x180025f3b  mov     rdx, rsi; struct wil::FailureInfo *
0x180025f3e  lea     rcx, [rax+rax*4]
0x180025f42  shl     rcx, 4
0x180025f46  add     rcx, r9; this
0x180025f49  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180025f4e  add     rsp, 28h
0x180025f52  pop     rdi
0x180025f53  pop     rsi
0x180025f54  pop     rbp
0x180025f55  pop     rbx
0x180025f56  retn
```
