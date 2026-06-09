# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180010030`
- end: `0x180010107`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `215`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d1f0`

## callees

- `0x18000eb64`
- `0x18000fde8`
- `0x180010030`

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
0x180010030  mov     [rsp+arg_10], rbx
0x180010035  push    rbp
0x180010036  push    rsi
0x180010037  push    rdi
0x180010038  sub     rsp, 20h
0x18001003c  cmp     qword ptr [rcx+18h], 0
0x180010041  mov     rsi, rdx
0x180010044  mov     edi, [rcx+10h]
0x180010047  mov     rbx, rcx
0x18001004a  mov     ebp, 50h ; 'P'
0x18001004f  jnz     short loc_180010086
0x180010051  test    edi, edi
0x180010053  jz      short loc_180010086
0x180010055  mov     edx, 190h; dwBytes
0x18001005a  lea     ecx, [rbp-48h]; dwFlags
0x18001005d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010062  mov     [rbx+18h], rax
0x180010066  test    rax, rax
0x180010069  jz      short loc_180010086
0x18001006b  mov     dword ptr [rbx+20h], 5
0x180010072  lea     rcx, [rax+190h]
0x180010079  jmp     short loc_180010081
0x18001007b  mov     [rax], bp
0x18001007e  add     rax, rbp
0x180010081  cmp     rax, rcx
0x180010084  jnz     short loc_18001007B
0x180010086  mov     r9, [rbx+18h]
0x18001008a  test    r9, r9
0x18001008d  jz      short loc_1800100F9
0x18001008f  test    edi, edi
0x180010091  jz      short loc_1800100BF
0x180010093  movzx   eax, word ptr [rbx+20h]
0x180010097  mov     rcx, r9
0x18001009a  lea     rdx, [rax+rax*4]
0x18001009e  shl     rdx, 4
0x1800100a2  add     rdx, r9
0x1800100a5  cmp     rcx, rdx
0x1800100a8  jz      short loc_1800100BF
0x1800100aa  mov     eax, [rbx+10h]
0x1800100ad  cmp     [rcx+4], eax
0x1800100b0  jbe     short loc_1800100BA
0x1800100b2  mov     eax, [rsi+8]
0x1800100b5  cmp     [rcx+8], eax
0x1800100b8  jz      short loc_1800100F9
0x1800100ba  add     rcx, rbp
0x1800100bd  jmp     short loc_1800100A5
0x1800100bf  movzx   eax, word ptr [rbx+22h]
0x1800100c3  xor     edx, edx
0x1800100c5  movzx   ecx, word ptr [rbx+20h]
0x1800100c9  inc     eax
0x1800100cb  div     ecx
0x1800100cd  mov     rax, [rbx+8]
0x1800100d1  mov     r8d, 1
0x1800100d7  mov     [rbx+22h], dx
0x1800100db  lock xadd [rax], r8d
0x1800100e0  movzx   eax, dx
0x1800100e3  inc     r8d; unsigned int
0x1800100e6  mov     rdx, rsi; struct wil::FailureInfo *
0x1800100e9  lea     rcx, [rax+rax*4]
0x1800100ed  shl     rcx, 4
0x1800100f1  add     rcx, r9; this
0x1800100f4  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800100f9  mov     rbx, [rsp+38h+arg_10]
0x1800100fe  add     rsp, 20h
0x180010102  pop     rdi
0x180010103  pop     rsi
0x180010104  pop     rbp
0x180010105  retn
```
