# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800055b4`
- end: `0x180005683`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003d70`

## callees

- `0x180004d98`
- `0x18000521c`
- `0x1800055b4`

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
0x1800055b4  push    rbx
0x1800055b6  push    rbp
0x1800055b7  push    rsi
0x1800055b8  push    rdi
0x1800055b9  sub     rsp, 28h
0x1800055bd  cmp     qword ptr [rcx+18h], 0
0x1800055c2  mov     rsi, rdx
0x1800055c5  mov     edi, [rcx+10h]
0x1800055c8  mov     rbx, rcx
0x1800055cb  mov     ebp, 50h ; 'P'
0x1800055d0  jnz     short loc_180005607
0x1800055d2  test    edi, edi
0x1800055d4  jz      short loc_180005607
0x1800055d6  mov     edx, 190h; dwBytes
0x1800055db  lea     ecx, [rbp-48h]; dwFlags
0x1800055de  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800055e3  mov     [rbx+18h], rax
0x1800055e7  test    rax, rax
0x1800055ea  jz      short loc_180005607
0x1800055ec  mov     dword ptr [rbx+20h], 5
0x1800055f3  lea     rcx, [rax+190h]
0x1800055fa  jmp     short loc_180005602
0x1800055fc  mov     [rax], bp
0x1800055ff  add     rax, rbp
0x180005602  cmp     rax, rcx
0x180005605  jnz     short loc_1800055FC
0x180005607  mov     r9, [rbx+18h]
0x18000560b  test    r9, r9
0x18000560e  jz      short loc_18000567A
0x180005610  test    edi, edi
0x180005612  jz      short loc_180005640
0x180005614  movzx   eax, word ptr [rbx+20h]
0x180005618  mov     rcx, r9
0x18000561b  lea     rdx, [rax+rax*4]
0x18000561f  shl     rdx, 4
0x180005623  add     rdx, r9
0x180005626  cmp     rcx, rdx
0x180005629  jz      short loc_180005640
0x18000562b  mov     eax, [rbx+10h]
0x18000562e  cmp     [rcx+4], eax
0x180005631  jbe     short loc_18000563B
0x180005633  mov     eax, [rsi+8]
0x180005636  cmp     [rcx+8], eax
0x180005639  jz      short loc_18000567A
0x18000563b  add     rcx, rbp
0x18000563e  jmp     short loc_180005626
0x180005640  movzx   eax, word ptr [rbx+22h]
0x180005644  xor     edx, edx
0x180005646  movzx   ecx, word ptr [rbx+20h]
0x18000564a  inc     eax
0x18000564c  div     ecx
0x18000564e  mov     rax, [rbx+8]
0x180005652  mov     r8d, 1
0x180005658  mov     [rbx+22h], dx
0x18000565c  lock xadd [rax], r8d
0x180005661  movzx   eax, dx
0x180005664  inc     r8d; unsigned int
0x180005667  mov     rdx, rsi; struct wil::FailureInfo *
0x18000566a  lea     rcx, [rax+rax*4]
0x18000566e  shl     rcx, 4
0x180005672  add     rcx, r9; this
0x180005675  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000567a  add     rsp, 28h
0x18000567e  pop     rdi
0x18000567f  pop     rsi
0x180005680  pop     rbp
0x180005681  pop     rbx
0x180005682  retn
```
