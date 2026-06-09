# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000b080`
- end: `0x18000b154`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `212`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008950`

## callees

- `0x180009f14`
- `0x18000ae54`
- `0x18000b080`

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
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned __int16 v10; // dx
  volatile signed __int32 *v11; // rax

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
    if ( !v3 || (v8 = *((_QWORD *)this + 3), v9 = v7 + 80LL * *((unsigned __int16 *)this + 16), v7 == v9) )
    {
LABEL_13:
      v10 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      v11 = (volatile signed __int32 *)*((_QWORD *)this + 1);
      *((_WORD *)this + 17) = v10;
      wil::details_abi::ThreadLocalFailureInfo::Set(
        (wil::details_abi::ThreadLocalFailureInfo *)(v7 + 80LL * v10),
        a2,
        _InterlockedIncrement(v11));
    }
    else
    {
      while ( *(_DWORD *)(v8 + 4) <= *((_DWORD *)this + 4) || *(_DWORD *)(v8 + 8) != *((_DWORD *)a2 + 2) )
      {
        v8 += 80;
        if ( v8 == v9 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x18000b080  push    rbx
0x18000b082  push    rbp
0x18000b083  push    rsi
0x18000b084  push    rdi
0x18000b085  sub     rsp, 28h
0x18000b089  cmp     qword ptr [rcx+18h], 0
0x18000b08e  mov     rsi, rdx
0x18000b091  mov     edi, [rcx+10h]
0x18000b094  mov     rbx, rcx
0x18000b097  mov     ebp, 50h ; 'P'
0x18000b09c  jnz     short loc_18000B0D3
0x18000b09e  test    edi, edi
0x18000b0a0  jz      short loc_18000B0D3
0x18000b0a2  mov     edx, 190h; dwBytes
0x18000b0a7  lea     ecx, [rbp-48h]; dwFlags
0x18000b0aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b0af  mov     [rbx+18h], rax
0x18000b0b3  test    rax, rax
0x18000b0b6  jz      short loc_18000B0D3
0x18000b0b8  mov     dword ptr [rbx+20h], 5
0x18000b0bf  lea     rcx, [rax+190h]
0x18000b0c6  jmp     short loc_18000B0CE
0x18000b0c8  mov     [rax], bp
0x18000b0cb  add     rax, rbp
0x18000b0ce  cmp     rax, rcx
0x18000b0d1  jnz     short loc_18000B0C8
0x18000b0d3  mov     r9, [rbx+18h]
0x18000b0d7  test    r9, r9
0x18000b0da  jz      short loc_18000B14B
0x18000b0dc  test    edi, edi
0x18000b0de  jz      short loc_18000B111
0x18000b0e0  movzx   eax, word ptr [rbx+20h]
0x18000b0e4  mov     rcx, r9
0x18000b0e7  lea     rdx, [rax+rax*4]
0x18000b0eb  shl     rdx, 4
0x18000b0ef  add     rdx, r9
0x18000b0f2  cmp     r9, rdx
0x18000b0f5  jz      short loc_18000B111
0x18000b0f7  mov     r8d, [rbx+10h]
0x18000b0fb  cmp     [rcx+4], r8d
0x18000b0ff  jbe     short loc_18000B109
0x18000b101  mov     eax, [rsi+8]
0x18000b104  cmp     [rcx+8], eax
0x18000b107  jz      short loc_18000B14B
0x18000b109  add     rcx, rbp
0x18000b10c  cmp     rcx, rdx
0x18000b10f  jnz     short loc_18000B0FB
0x18000b111  movzx   eax, word ptr [rbx+22h]
0x18000b115  xor     edx, edx
0x18000b117  movzx   ecx, word ptr [rbx+20h]
0x18000b11b  inc     eax
0x18000b11d  div     ecx
0x18000b11f  mov     rax, [rbx+8]
0x18000b123  mov     r8d, 1
0x18000b129  mov     [rbx+22h], dx
0x18000b12d  lock xadd [rax], r8d
0x18000b132  movzx   eax, dx
0x18000b135  inc     r8d; unsigned int
0x18000b138  mov     rdx, rsi; struct wil::FailureInfo *
0x18000b13b  lea     rcx, [rax+rax*4]
0x18000b13f  shl     rcx, 4
0x18000b143  add     rcx, r9; this
0x18000b146  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000b14b  add     rsp, 28h
0x18000b14f  pop     rdi
0x18000b150  pop     rsi
0x18000b151  pop     rbp
0x18000b152  pop     rbx
0x18000b153  retn
```
