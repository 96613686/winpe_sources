# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000e194`
- end: `0x18000e263`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ca60`

## callees

- `0x18000dc48`
- `0x18000e01c`
- `0x18000e194`

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
0x18000e194  push    rbx
0x18000e196  push    rbp
0x18000e197  push    rsi
0x18000e198  push    rdi
0x18000e199  sub     rsp, 28h
0x18000e19d  cmp     qword ptr [rcx+18h], 0
0x18000e1a2  mov     rsi, rdx
0x18000e1a5  mov     edi, [rcx+10h]
0x18000e1a8  mov     rbx, rcx
0x18000e1ab  mov     ebp, 50h ; 'P'
0x18000e1b0  jnz     short loc_18000E1E7
0x18000e1b2  test    edi, edi
0x18000e1b4  jz      short loc_18000E1E7
0x18000e1b6  mov     edx, 190h; dwBytes
0x18000e1bb  lea     ecx, [rbp-48h]; dwFlags
0x18000e1be  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e1c3  mov     [rbx+18h], rax
0x18000e1c7  test    rax, rax
0x18000e1ca  jz      short loc_18000E1E7
0x18000e1cc  mov     dword ptr [rbx+20h], 5
0x18000e1d3  lea     rcx, [rax+190h]
0x18000e1da  jmp     short loc_18000E1E2
0x18000e1dc  mov     [rax], bp
0x18000e1df  add     rax, rbp
0x18000e1e2  cmp     rax, rcx
0x18000e1e5  jnz     short loc_18000E1DC
0x18000e1e7  mov     r9, [rbx+18h]
0x18000e1eb  test    r9, r9
0x18000e1ee  jz      short loc_18000E25A
0x18000e1f0  test    edi, edi
0x18000e1f2  jz      short loc_18000E220
0x18000e1f4  movzx   eax, word ptr [rbx+20h]
0x18000e1f8  mov     rcx, r9
0x18000e1fb  lea     rdx, [rax+rax*4]
0x18000e1ff  shl     rdx, 4
0x18000e203  add     rdx, r9
0x18000e206  cmp     rcx, rdx
0x18000e209  jz      short loc_18000E220
0x18000e20b  mov     eax, [rbx+10h]
0x18000e20e  cmp     [rcx+4], eax
0x18000e211  jbe     short loc_18000E21B
0x18000e213  mov     eax, [rsi+8]
0x18000e216  cmp     [rcx+8], eax
0x18000e219  jz      short loc_18000E25A
0x18000e21b  add     rcx, rbp
0x18000e21e  jmp     short loc_18000E206
0x18000e220  movzx   eax, word ptr [rbx+22h]
0x18000e224  xor     edx, edx
0x18000e226  movzx   ecx, word ptr [rbx+20h]
0x18000e22a  inc     eax
0x18000e22c  div     ecx
0x18000e22e  mov     rax, [rbx+8]
0x18000e232  mov     r8d, 1
0x18000e238  mov     [rbx+22h], dx
0x18000e23c  lock xadd [rax], r8d
0x18000e241  movzx   eax, dx
0x18000e244  inc     r8d; unsigned int
0x18000e247  mov     rdx, rsi; struct wil::FailureInfo *
0x18000e24a  lea     rcx, [rax+rax*4]
0x18000e24e  shl     rcx, 4
0x18000e252  add     rcx, r9; this
0x18000e255  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000e25a  add     rsp, 28h
0x18000e25e  pop     rdi
0x18000e25f  pop     rsi
0x18000e260  pop     rbp
0x18000e261  pop     rbx
0x18000e262  retn
```
