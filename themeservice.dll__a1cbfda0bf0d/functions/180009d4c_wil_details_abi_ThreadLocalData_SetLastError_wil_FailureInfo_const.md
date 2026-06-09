# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180009d4c`
- end: `0x180009e1b`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008bf0`

## callees

- `0x180009900`
- `0x180009bd4`
- `0x180009d4c`

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
0x180009d4c  push    rbx
0x180009d4e  push    rbp
0x180009d4f  push    rsi
0x180009d50  push    rdi
0x180009d51  sub     rsp, 28h
0x180009d55  cmp     qword ptr [rcx+18h], 0
0x180009d5a  mov     rsi, rdx
0x180009d5d  mov     edi, [rcx+10h]
0x180009d60  mov     rbx, rcx
0x180009d63  mov     ebp, 50h ; 'P'
0x180009d68  jnz     short loc_180009D9F
0x180009d6a  test    edi, edi
0x180009d6c  jz      short loc_180009D9F
0x180009d6e  mov     edx, 190h; dwBytes
0x180009d73  lea     ecx, [rbp-48h]; dwFlags
0x180009d76  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009d7b  mov     [rbx+18h], rax
0x180009d7f  test    rax, rax
0x180009d82  jz      short loc_180009D9F
0x180009d84  mov     dword ptr [rbx+20h], 5
0x180009d8b  lea     rcx, [rax+190h]
0x180009d92  jmp     short loc_180009D9A
0x180009d94  mov     [rax], bp
0x180009d97  add     rax, rbp
0x180009d9a  cmp     rax, rcx
0x180009d9d  jnz     short loc_180009D94
0x180009d9f  mov     r9, [rbx+18h]
0x180009da3  test    r9, r9
0x180009da6  jz      short loc_180009E12
0x180009da8  test    edi, edi
0x180009daa  jz      short loc_180009DD8
0x180009dac  movzx   eax, word ptr [rbx+20h]
0x180009db0  mov     rcx, r9
0x180009db3  lea     rdx, [rax+rax*4]
0x180009db7  shl     rdx, 4
0x180009dbb  add     rdx, r9
0x180009dbe  cmp     rcx, rdx
0x180009dc1  jz      short loc_180009DD8
0x180009dc3  mov     eax, [rbx+10h]
0x180009dc6  cmp     [rcx+4], eax
0x180009dc9  jbe     short loc_180009DD3
0x180009dcb  mov     eax, [rsi+8]
0x180009dce  cmp     [rcx+8], eax
0x180009dd1  jz      short loc_180009E12
0x180009dd3  add     rcx, rbp
0x180009dd6  jmp     short loc_180009DBE
0x180009dd8  movzx   eax, word ptr [rbx+22h]
0x180009ddc  xor     edx, edx
0x180009dde  movzx   ecx, word ptr [rbx+20h]
0x180009de2  inc     eax
0x180009de4  div     ecx
0x180009de6  mov     rax, [rbx+8]
0x180009dea  mov     r8d, 1
0x180009df0  mov     [rbx+22h], dx
0x180009df4  lock xadd [rax], r8d
0x180009df9  movzx   eax, dx
0x180009dfc  inc     r8d; unsigned int
0x180009dff  mov     rdx, rsi; struct wil::FailureInfo *
0x180009e02  lea     rcx, [rax+rax*4]
0x180009e06  shl     rcx, 4
0x180009e0a  add     rcx, r9; this
0x180009e0d  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180009e12  add     rsp, 28h
0x180009e16  pop     rdi
0x180009e17  pop     rsi
0x180009e18  pop     rbp
0x180009e19  pop     rbx
0x180009e1a  retn
```
