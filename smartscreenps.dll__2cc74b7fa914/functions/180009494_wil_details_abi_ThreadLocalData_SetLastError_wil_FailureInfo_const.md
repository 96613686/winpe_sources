# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180009494`
- end: `0x18000956a`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `214`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007cb0`

## callees

- `0x180008c78`
- `0x1800090fc`
- `0x180009494`

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
0x180009494  mov     [rsp+arg_10], rbx
0x180009499  push    rbp
0x18000949a  push    rsi
0x18000949b  push    rdi
0x18000949c  sub     rsp, 20h
0x1800094a0  cmp     qword ptr [rcx+18h], 0
0x1800094a5  mov     rsi, rdx
0x1800094a8  mov     edi, [rcx+10h]
0x1800094ab  mov     rbx, rcx
0x1800094ae  mov     ebp, 50h ; 'P'
0x1800094b3  jnz     short loc_1800094EA
0x1800094b5  test    edi, edi
0x1800094b7  jz      short loc_1800094EA
0x1800094b9  mov     edx, 190h; dwBytes
0x1800094be  lea     ecx, [rbp-48h]; dwFlags
0x1800094c1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800094c6  mov     [rbx+18h], rax
0x1800094ca  test    rax, rax
0x1800094cd  jz      short loc_1800094EA
0x1800094cf  mov     dword ptr [rbx+20h], 5
0x1800094d6  lea     rcx, [rax+190h]
0x1800094dd  jmp     short loc_1800094E5
0x1800094df  mov     [rax], bp
0x1800094e2  add     rax, rbp
0x1800094e5  cmp     rax, rcx
0x1800094e8  jnz     short loc_1800094DF
0x1800094ea  mov     r9, [rbx+18h]
0x1800094ee  test    r9, r9
0x1800094f1  jz      short loc_18000955D
0x1800094f3  test    edi, edi
0x1800094f5  jz      short loc_180009523
0x1800094f7  movzx   eax, word ptr [rbx+20h]
0x1800094fb  mov     rcx, r9
0x1800094fe  lea     rdx, [rax+rax*4]
0x180009502  shl     rdx, 4
0x180009506  add     rdx, r9
0x180009509  cmp     rcx, rdx
0x18000950c  jz      short loc_180009523
0x18000950e  mov     eax, [rbx+10h]
0x180009511  cmp     [rcx+4], eax
0x180009514  jbe     short loc_18000951E
0x180009516  mov     eax, [rsi+8]
0x180009519  cmp     [rcx+8], eax
0x18000951c  jz      short loc_18000955D
0x18000951e  add     rcx, rbp
0x180009521  jmp     short loc_180009509
0x180009523  movzx   eax, word ptr [rbx+22h]
0x180009527  xor     edx, edx
0x180009529  movzx   ecx, word ptr [rbx+20h]
0x18000952d  inc     eax
0x18000952f  div     ecx
0x180009531  mov     rax, [rbx+8]
0x180009535  mov     r8d, 1
0x18000953b  mov     [rbx+22h], dx
0x18000953f  lock xadd [rax], r8d
0x180009544  movzx   eax, dx
0x180009547  inc     r8d; unsigned int
0x18000954a  mov     rdx, rsi; struct wil::FailureInfo *
0x18000954d  lea     rcx, [rax+rax*4]
0x180009551  shl     rcx, 4
0x180009555  add     rcx, r9; this
0x180009558  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000955d  mov     rbx, [rsp+38h+arg_10]
0x180009562  add     rsp, 20h
0x180009566  pop     rdi
0x180009567  pop     rsi
0x180009568  pop     rbp
0x180009569  retn
```
