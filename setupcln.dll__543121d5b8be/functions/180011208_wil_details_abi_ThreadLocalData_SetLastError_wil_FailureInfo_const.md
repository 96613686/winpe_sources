# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180011208`
- end: `0x1800112dc`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `212`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e7e0`

## callees

- `0x18000fe98`
- `0x180010d80`
- `0x180011208`

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
0x180011208  push    rbx
0x18001120a  push    rbp
0x18001120b  push    rsi
0x18001120c  push    rdi
0x18001120d  sub     rsp, 28h
0x180011211  cmp     qword ptr [rcx+18h], 0
0x180011216  mov     rsi, rdx
0x180011219  mov     edi, [rcx+10h]
0x18001121c  mov     rbx, rcx
0x18001121f  mov     ebp, 50h ; 'P'
0x180011224  jnz     short loc_18001125B
0x180011226  test    edi, edi
0x180011228  jz      short loc_18001125B
0x18001122a  mov     edx, 190h; dwBytes
0x18001122f  lea     ecx, [rbp-48h]; dwFlags
0x180011232  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180011237  mov     [rbx+18h], rax
0x18001123b  test    rax, rax
0x18001123e  jz      short loc_18001125B
0x180011240  mov     dword ptr [rbx+20h], 5
0x180011247  lea     rcx, [rax+190h]
0x18001124e  jmp     short loc_180011256
0x180011250  mov     [rax], bp
0x180011253  add     rax, rbp
0x180011256  cmp     rax, rcx
0x180011259  jnz     short loc_180011250
0x18001125b  mov     r9, [rbx+18h]
0x18001125f  test    r9, r9
0x180011262  jz      short loc_1800112D3
0x180011264  test    edi, edi
0x180011266  jz      short loc_180011299
0x180011268  movzx   eax, word ptr [rbx+20h]
0x18001126c  mov     rcx, r9
0x18001126f  lea     rdx, [rax+rax*4]
0x180011273  shl     rdx, 4
0x180011277  add     rdx, r9
0x18001127a  cmp     r9, rdx
0x18001127d  jz      short loc_180011299
0x18001127f  mov     r8d, [rbx+10h]
0x180011283  cmp     [rcx+4], r8d
0x180011287  jbe     short loc_180011291
0x180011289  mov     eax, [rsi+8]
0x18001128c  cmp     [rcx+8], eax
0x18001128f  jz      short loc_1800112D3
0x180011291  add     rcx, rbp
0x180011294  cmp     rcx, rdx
0x180011297  jnz     short loc_180011283
0x180011299  movzx   eax, word ptr [rbx+22h]
0x18001129d  xor     edx, edx
0x18001129f  movzx   ecx, word ptr [rbx+20h]
0x1800112a3  inc     eax
0x1800112a5  div     ecx
0x1800112a7  mov     rax, [rbx+8]
0x1800112ab  mov     r8d, 1
0x1800112b1  mov     [rbx+22h], dx
0x1800112b5  lock xadd [rax], r8d
0x1800112ba  movzx   eax, dx
0x1800112bd  inc     r8d; unsigned int
0x1800112c0  mov     rdx, rsi; struct wil::FailureInfo *
0x1800112c3  lea     rcx, [rax+rax*4]
0x1800112c7  shl     rcx, 4
0x1800112cb  add     rcx, r9; this
0x1800112ce  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800112d3  add     rsp, 28h
0x1800112d7  pop     rdi
0x1800112d8  pop     rsi
0x1800112d9  pop     rbp
0x1800112da  pop     rbx
0x1800112db  retn
```
