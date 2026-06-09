# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180008a6c`
- end: `0x180008b3b`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006720`

## callees

- `0x180007a58`
- `0x1800086d4`
- `0x180008a6c`

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
0x180008a6c  push    rbx
0x180008a6e  push    rbp
0x180008a6f  push    rsi
0x180008a70  push    rdi
0x180008a71  sub     rsp, 28h
0x180008a75  cmp     qword ptr [rcx+18h], 0
0x180008a7a  mov     rsi, rdx
0x180008a7d  mov     edi, [rcx+10h]
0x180008a80  mov     rbx, rcx
0x180008a83  mov     ebp, 50h ; 'P'
0x180008a88  jnz     short loc_180008ABF
0x180008a8a  test    edi, edi
0x180008a8c  jz      short loc_180008ABF
0x180008a8e  mov     edx, 190h; dwBytes
0x180008a93  lea     ecx, [rbp-48h]; dwFlags
0x180008a96  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008a9b  mov     [rbx+18h], rax
0x180008a9f  test    rax, rax
0x180008aa2  jz      short loc_180008ABF
0x180008aa4  mov     dword ptr [rbx+20h], 5
0x180008aab  lea     rcx, [rax+190h]
0x180008ab2  jmp     short loc_180008ABA
0x180008ab4  mov     [rax], bp
0x180008ab7  add     rax, rbp
0x180008aba  cmp     rax, rcx
0x180008abd  jnz     short loc_180008AB4
0x180008abf  mov     r9, [rbx+18h]
0x180008ac3  test    r9, r9
0x180008ac6  jz      short loc_180008B32
0x180008ac8  test    edi, edi
0x180008aca  jz      short loc_180008AF8
0x180008acc  movzx   eax, word ptr [rbx+20h]
0x180008ad0  mov     rcx, r9
0x180008ad3  lea     rdx, [rax+rax*4]
0x180008ad7  shl     rdx, 4
0x180008adb  add     rdx, r9
0x180008ade  cmp     rcx, rdx
0x180008ae1  jz      short loc_180008AF8
0x180008ae3  mov     eax, [rbx+10h]
0x180008ae6  cmp     [rcx+4], eax
0x180008ae9  jbe     short loc_180008AF3
0x180008aeb  mov     eax, [rsi+8]
0x180008aee  cmp     [rcx+8], eax
0x180008af1  jz      short loc_180008B32
0x180008af3  add     rcx, rbp
0x180008af6  jmp     short loc_180008ADE
0x180008af8  movzx   eax, word ptr [rbx+22h]
0x180008afc  xor     edx, edx
0x180008afe  movzx   ecx, word ptr [rbx+20h]
0x180008b02  inc     eax
0x180008b04  div     ecx
0x180008b06  mov     rax, [rbx+8]
0x180008b0a  mov     r8d, 1
0x180008b10  mov     [rbx+22h], dx
0x180008b14  lock xadd [rax], r8d
0x180008b19  movzx   eax, dx
0x180008b1c  inc     r8d; unsigned int
0x180008b1f  mov     rdx, rsi; struct wil::FailureInfo *
0x180008b22  lea     rcx, [rax+rax*4]
0x180008b26  shl     rcx, 4
0x180008b2a  add     rcx, r9; this
0x180008b2d  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180008b32  add     rsp, 28h
0x180008b36  pop     rdi
0x180008b37  pop     rsi
0x180008b38  pop     rbp
0x180008b39  pop     rbx
0x180008b3a  retn
```
