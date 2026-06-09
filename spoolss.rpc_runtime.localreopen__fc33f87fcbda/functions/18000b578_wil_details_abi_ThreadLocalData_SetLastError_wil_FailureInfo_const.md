# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000b578`
- end: `0x18000b648`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `208`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800088e0`

## callees

- `0x180009e24`
- `0x18000b1c4`
- `0x18000b578`

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
0x18000b578  push    rbx
0x18000b57a  push    rbp
0x18000b57b  push    rsi
0x18000b57c  push    rdi
0x18000b57d  sub     rsp, 28h
0x18000b581  cmp     qword ptr [rcx+18h], 0
0x18000b586  mov     rsi, rdx
0x18000b589  mov     edi, [rcx+10h]
0x18000b58c  mov     rbx, rcx
0x18000b58f  mov     ebp, 50h ; 'P'
0x18000b594  jnz     short loc_18000B5CB
0x18000b596  test    edi, edi
0x18000b598  jz      short loc_18000B5CB
0x18000b59a  mov     edx, 190h; dwBytes
0x18000b59f  lea     ecx, [rbp-48h]; dwFlags
0x18000b5a2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b5a7  mov     [rbx+18h], rax
0x18000b5ab  test    rax, rax
0x18000b5ae  jz      short loc_18000B5CB
0x18000b5b0  mov     dword ptr [rbx+20h], 5
0x18000b5b7  lea     rcx, [rax+190h]
0x18000b5be  jmp     short loc_18000B5C6
0x18000b5c0  mov     [rax], bp
0x18000b5c3  add     rax, rbp
0x18000b5c6  cmp     rax, rcx
0x18000b5c9  jnz     short loc_18000B5C0
0x18000b5cb  mov     r9, [rbx+18h]
0x18000b5cf  test    r9, r9
0x18000b5d2  jz      short loc_18000B63E
0x18000b5d4  test    edi, edi
0x18000b5d6  jz      short loc_18000B604
0x18000b5d8  movzx   eax, word ptr [rbx+20h]
0x18000b5dc  mov     rcx, r9
0x18000b5df  lea     rdx, [rax+rax*4]
0x18000b5e3  shl     rdx, 4
0x18000b5e7  add     rdx, r9
0x18000b5ea  cmp     rcx, rdx
0x18000b5ed  jz      short loc_18000B604
0x18000b5ef  mov     eax, [rbx+10h]
0x18000b5f2  cmp     [rcx+4], eax
0x18000b5f5  jbe     short loc_18000B5FF
0x18000b5f7  mov     eax, [rsi+8]
0x18000b5fa  cmp     [rcx+8], eax
0x18000b5fd  jz      short loc_18000B63E
0x18000b5ff  add     rcx, rbp
0x18000b602  jmp     short loc_18000B5EA
0x18000b604  movzx   eax, word ptr [rbx+22h]
0x18000b608  xor     edx, edx
0x18000b60a  movzx   ecx, word ptr [rbx+20h]
0x18000b60e  inc     eax
0x18000b610  div     ecx
0x18000b612  mov     rax, [rbx+8]
0x18000b616  mov     r8d, 1
0x18000b61c  mov     [rbx+22h], dx
0x18000b620  lock xadd [rax], r8d
0x18000b625  movzx   eax, dx
0x18000b628  inc     r8d; unsigned int
0x18000b62b  mov     rdx, rsi; struct wil::FailureInfo *
0x18000b62e  lea     rcx, [rax+rax*4]
0x18000b632  shl     rcx, 4
0x18000b636  add     rcx, r9; this
0x18000b639  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000b63e  add     rsp, 28h
0x18000b642  pop     rdi
0x18000b643  pop     rsi
0x18000b644  pop     rbp
0x18000b645  pop     rbx
0x18000b646  retn
```
