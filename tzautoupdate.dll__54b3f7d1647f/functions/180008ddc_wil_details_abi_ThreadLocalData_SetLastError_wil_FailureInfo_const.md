# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180008ddc`
- end: `0x180008eab`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005b30`

## callees

- `0x1800073e0`
- `0x180008954`
- `0x180008ddc`

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
0x180008ddc  push    rbx
0x180008dde  push    rbp
0x180008ddf  push    rsi
0x180008de0  push    rdi
0x180008de1  sub     rsp, 28h
0x180008de5  cmp     qword ptr [rcx+18h], 0
0x180008dea  mov     rsi, rdx
0x180008ded  mov     edi, [rcx+10h]
0x180008df0  mov     rbx, rcx
0x180008df3  mov     ebp, 50h ; 'P'
0x180008df8  jnz     short loc_180008E2F
0x180008dfa  test    edi, edi
0x180008dfc  jz      short loc_180008E2F
0x180008dfe  mov     edx, 190h; dwBytes
0x180008e03  lea     ecx, [rbp-48h]; dwFlags
0x180008e06  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008e0b  mov     [rbx+18h], rax
0x180008e0f  test    rax, rax
0x180008e12  jz      short loc_180008E2F
0x180008e14  mov     dword ptr [rbx+20h], 5
0x180008e1b  lea     rcx, [rax+190h]
0x180008e22  jmp     short loc_180008E2A
0x180008e24  mov     [rax], bp
0x180008e27  add     rax, rbp
0x180008e2a  cmp     rax, rcx
0x180008e2d  jnz     short loc_180008E24
0x180008e2f  mov     r9, [rbx+18h]
0x180008e33  test    r9, r9
0x180008e36  jz      short loc_180008EA2
0x180008e38  test    edi, edi
0x180008e3a  jz      short loc_180008E68
0x180008e3c  movzx   eax, word ptr [rbx+20h]
0x180008e40  mov     rcx, r9
0x180008e43  lea     rdx, [rax+rax*4]
0x180008e47  shl     rdx, 4
0x180008e4b  add     rdx, r9
0x180008e4e  cmp     rcx, rdx
0x180008e51  jz      short loc_180008E68
0x180008e53  mov     eax, [rbx+10h]
0x180008e56  cmp     [rcx+4], eax
0x180008e59  jbe     short loc_180008E63
0x180008e5b  mov     eax, [rsi+8]
0x180008e5e  cmp     [rcx+8], eax
0x180008e61  jz      short loc_180008EA2
0x180008e63  add     rcx, rbp
0x180008e66  jmp     short loc_180008E4E
0x180008e68  movzx   eax, word ptr [rbx+22h]
0x180008e6c  xor     edx, edx
0x180008e6e  movzx   ecx, word ptr [rbx+20h]
0x180008e72  inc     eax
0x180008e74  div     ecx
0x180008e76  mov     rax, [rbx+8]
0x180008e7a  mov     r8d, 1
0x180008e80  mov     [rbx+22h], dx
0x180008e84  lock xadd [rax], r8d
0x180008e89  movzx   eax, dx
0x180008e8c  inc     r8d; unsigned int
0x180008e8f  mov     rdx, rsi; struct wil::FailureInfo *
0x180008e92  lea     rcx, [rax+rax*4]
0x180008e96  shl     rcx, 4
0x180008e9a  add     rcx, r9; this
0x180008e9d  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180008ea2  add     rsp, 28h
0x180008ea6  pop     rdi
0x180008ea7  pop     rsi
0x180008ea8  pop     rbp
0x180008ea9  pop     rbx
0x180008eaa  retn
```
