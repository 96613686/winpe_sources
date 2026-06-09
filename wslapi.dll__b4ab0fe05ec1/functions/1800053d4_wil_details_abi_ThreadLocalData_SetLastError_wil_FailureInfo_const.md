# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800053d4`
- end: `0x1800054aa`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `214`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b20`

## callees

- `0x180004ba4`
- `0x18000503c`
- `0x1800053d4`

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
0x1800053d4  mov     [rsp+arg_10], rbx
0x1800053d9  push    rbp
0x1800053da  push    rsi
0x1800053db  push    rdi
0x1800053dc  sub     rsp, 20h
0x1800053e0  cmp     qword ptr [rcx+18h], 0
0x1800053e5  mov     rsi, rdx
0x1800053e8  mov     edi, [rcx+10h]
0x1800053eb  mov     rbx, rcx
0x1800053ee  mov     ebp, 50h ; 'P'
0x1800053f3  jnz     short loc_18000542A
0x1800053f5  test    edi, edi
0x1800053f7  jz      short loc_18000542A
0x1800053f9  mov     edx, 190h; dwBytes
0x1800053fe  lea     ecx, [rbp-48h]; dwFlags
0x180005401  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005406  mov     [rbx+18h], rax
0x18000540a  test    rax, rax
0x18000540d  jz      short loc_18000542A
0x18000540f  mov     dword ptr [rbx+20h], 5
0x180005416  lea     rcx, [rax+190h]
0x18000541d  jmp     short loc_180005425
0x18000541f  mov     [rax], bp
0x180005422  add     rax, rbp
0x180005425  cmp     rax, rcx
0x180005428  jnz     short loc_18000541F
0x18000542a  mov     r9, [rbx+18h]
0x18000542e  test    r9, r9
0x180005431  jz      short loc_18000549D
0x180005433  test    edi, edi
0x180005435  jz      short loc_180005463
0x180005437  movzx   eax, word ptr [rbx+20h]
0x18000543b  mov     rcx, r9
0x18000543e  lea     rdx, [rax+rax*4]
0x180005442  shl     rdx, 4
0x180005446  add     rdx, r9
0x180005449  cmp     rcx, rdx
0x18000544c  jz      short loc_180005463
0x18000544e  mov     eax, [rbx+10h]
0x180005451  cmp     [rcx+4], eax
0x180005454  jbe     short loc_18000545E
0x180005456  mov     eax, [rsi+8]
0x180005459  cmp     [rcx+8], eax
0x18000545c  jz      short loc_18000549D
0x18000545e  add     rcx, rbp
0x180005461  jmp     short loc_180005449
0x180005463  movzx   eax, word ptr [rbx+22h]
0x180005467  xor     edx, edx
0x180005469  movzx   ecx, word ptr [rbx+20h]
0x18000546d  inc     eax
0x18000546f  div     ecx
0x180005471  mov     rax, [rbx+8]
0x180005475  mov     r8d, 1
0x18000547b  mov     [rbx+22h], dx
0x18000547f  lock xadd [rax], r8d
0x180005484  movzx   eax, dx
0x180005487  inc     r8d; unsigned int
0x18000548a  mov     rdx, rsi; struct wil::FailureInfo *
0x18000548d  lea     rcx, [rax+rax*4]
0x180005491  shl     rcx, 4
0x180005495  add     rcx, r9; this
0x180005498  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000549d  mov     rbx, [rsp+38h+arg_10]
0x1800054a2  add     rsp, 20h
0x1800054a6  pop     rdi
0x1800054a7  pop     rsi
0x1800054a8  pop     rbp
0x1800054a9  retn
```
