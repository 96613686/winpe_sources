# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800164a0`
- end: `0x18001656f`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015880`

## callees

- `0x180016128`
- `0x180016364`
- `0x1800164a0`

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
0x1800164a0  push    rbx
0x1800164a2  push    rbp
0x1800164a3  push    rsi
0x1800164a4  push    rdi
0x1800164a5  sub     rsp, 28h
0x1800164a9  cmp     qword ptr [rcx+18h], 0
0x1800164ae  mov     rsi, rdx
0x1800164b1  mov     edi, [rcx+10h]
0x1800164b4  mov     rbx, rcx
0x1800164b7  mov     ebp, 50h ; 'P'
0x1800164bc  jnz     short loc_1800164F3
0x1800164be  test    edi, edi
0x1800164c0  jz      short loc_1800164F3
0x1800164c2  mov     edx, 190h; dwBytes
0x1800164c7  lea     ecx, [rbp-48h]; dwFlags
0x1800164ca  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800164cf  mov     [rbx+18h], rax
0x1800164d3  test    rax, rax
0x1800164d6  jz      short loc_1800164F3
0x1800164d8  mov     dword ptr [rbx+20h], 5
0x1800164df  lea     rcx, [rax+190h]
0x1800164e6  jmp     short loc_1800164EE
0x1800164e8  mov     [rax], bp
0x1800164eb  add     rax, rbp
0x1800164ee  cmp     rax, rcx
0x1800164f1  jnz     short loc_1800164E8
0x1800164f3  mov     r9, [rbx+18h]
0x1800164f7  test    r9, r9
0x1800164fa  jz      short loc_180016566
0x1800164fc  test    edi, edi
0x1800164fe  jz      short loc_18001652C
0x180016500  movzx   eax, word ptr [rbx+20h]
0x180016504  mov     rcx, r9
0x180016507  lea     rdx, [rax+rax*4]
0x18001650b  shl     rdx, 4
0x18001650f  add     rdx, r9
0x180016512  cmp     rcx, rdx
0x180016515  jz      short loc_18001652C
0x180016517  mov     eax, [rbx+10h]
0x18001651a  cmp     [rcx+4], eax
0x18001651d  jbe     short loc_180016527
0x18001651f  mov     eax, [rsi+8]
0x180016522  cmp     [rcx+8], eax
0x180016525  jz      short loc_180016566
0x180016527  add     rcx, rbp
0x18001652a  jmp     short loc_180016512
0x18001652c  movzx   eax, word ptr [rbx+22h]
0x180016530  xor     edx, edx
0x180016532  movzx   ecx, word ptr [rbx+20h]
0x180016536  inc     eax
0x180016538  div     ecx
0x18001653a  mov     rax, [rbx+8]
0x18001653e  mov     r8d, 1
0x180016544  mov     [rbx+22h], dx
0x180016548  lock xadd [rax], r8d
0x18001654d  movzx   eax, dx
0x180016550  inc     r8d; unsigned int
0x180016553  mov     rdx, rsi; struct wil::FailureInfo *
0x180016556  lea     rcx, [rax+rax*4]
0x18001655a  shl     rcx, 4
0x18001655e  add     rcx, r9; this
0x180016561  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180016566  add     rsp, 28h
0x18001656a  pop     rdi
0x18001656b  pop     rsi
0x18001656c  pop     rbp
0x18001656d  pop     rbx
0x18001656e  retn
```
