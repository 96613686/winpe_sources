# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18001a630`
- end: `0x18001a704`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `212`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180018170`

## callees

- `0x1800195a8`
- `0x18001a404`
- `0x18001a630`

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
0x18001a630  push    rbx
0x18001a632  push    rbp
0x18001a633  push    rsi
0x18001a634  push    rdi
0x18001a635  sub     rsp, 28h
0x18001a639  cmp     qword ptr [rcx+18h], 0
0x18001a63e  mov     rsi, rdx
0x18001a641  mov     edi, [rcx+10h]
0x18001a644  mov     rbx, rcx
0x18001a647  mov     ebp, 50h ; 'P'
0x18001a64c  jnz     short loc_18001A683
0x18001a64e  test    edi, edi
0x18001a650  jz      short loc_18001A683
0x18001a652  mov     edx, 190h; dwBytes
0x18001a657  lea     ecx, [rbp-48h]; dwFlags
0x18001a65a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001a65f  mov     [rbx+18h], rax
0x18001a663  test    rax, rax
0x18001a666  jz      short loc_18001A683
0x18001a668  mov     dword ptr [rbx+20h], 5
0x18001a66f  lea     rcx, [rax+190h]
0x18001a676  jmp     short loc_18001A67E
0x18001a678  mov     [rax], bp
0x18001a67b  add     rax, rbp
0x18001a67e  cmp     rax, rcx
0x18001a681  jnz     short loc_18001A678
0x18001a683  mov     r9, [rbx+18h]
0x18001a687  test    r9, r9
0x18001a68a  jz      short loc_18001A6FB
0x18001a68c  test    edi, edi
0x18001a68e  jz      short loc_18001A6C1
0x18001a690  movzx   eax, word ptr [rbx+20h]
0x18001a694  mov     rcx, r9
0x18001a697  lea     rdx, [rax+rax*4]
0x18001a69b  shl     rdx, 4
0x18001a69f  add     rdx, r9
0x18001a6a2  cmp     r9, rdx
0x18001a6a5  jz      short loc_18001A6C1
0x18001a6a7  mov     r8d, [rbx+10h]
0x18001a6ab  cmp     [rcx+4], r8d
0x18001a6af  jbe     short loc_18001A6B9
0x18001a6b1  mov     eax, [rsi+8]
0x18001a6b4  cmp     [rcx+8], eax
0x18001a6b7  jz      short loc_18001A6FB
0x18001a6b9  add     rcx, rbp
0x18001a6bc  cmp     rcx, rdx
0x18001a6bf  jnz     short loc_18001A6AB
0x18001a6c1  movzx   eax, word ptr [rbx+22h]
0x18001a6c5  xor     edx, edx
0x18001a6c7  movzx   ecx, word ptr [rbx+20h]
0x18001a6cb  inc     eax
0x18001a6cd  div     ecx
0x18001a6cf  mov     rax, [rbx+8]
0x18001a6d3  mov     r8d, 1
0x18001a6d9  mov     [rbx+22h], dx
0x18001a6dd  lock xadd [rax], r8d
0x18001a6e2  movzx   eax, dx
0x18001a6e5  inc     r8d; unsigned int
0x18001a6e8  mov     rdx, rsi; struct wil::FailureInfo *
0x18001a6eb  lea     rcx, [rax+rax*4]
0x18001a6ef  shl     rcx, 4
0x18001a6f3  add     rcx, r9; this
0x18001a6f6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001a6fb  add     rsp, 28h
0x18001a6ff  pop     rdi
0x18001a700  pop     rsi
0x18001a701  pop     rbp
0x18001a702  pop     rbx
0x18001a703  retn
```
