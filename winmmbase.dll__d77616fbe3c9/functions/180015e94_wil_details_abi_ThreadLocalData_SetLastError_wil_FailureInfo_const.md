# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180015e94`
- end: `0x180015f68`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `212`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800143b0`

## callees

- `0x18001541c`
- `0x180015afc`
- `0x180015e94`

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
0x180015e94  push    rbx
0x180015e96  push    rbp
0x180015e97  push    rsi
0x180015e98  push    rdi
0x180015e99  sub     rsp, 28h
0x180015e9d  cmp     qword ptr [rcx+18h], 0
0x180015ea2  mov     rsi, rdx
0x180015ea5  mov     edi, [rcx+10h]
0x180015ea8  mov     rbx, rcx
0x180015eab  mov     ebp, 50h ; 'P'
0x180015eb0  jnz     short loc_180015EE7
0x180015eb2  test    edi, edi
0x180015eb4  jz      short loc_180015EE7
0x180015eb6  mov     edx, 190h; dwBytes
0x180015ebb  lea     ecx, [rbp-48h]; dwFlags
0x180015ebe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015ec3  mov     [rbx+18h], rax
0x180015ec7  test    rax, rax
0x180015eca  jz      short loc_180015EE7
0x180015ecc  mov     dword ptr [rbx+20h], 5
0x180015ed3  lea     rcx, [rax+190h]
0x180015eda  jmp     short loc_180015EE2
0x180015edc  mov     [rax], bp
0x180015edf  add     rax, rbp
0x180015ee2  cmp     rax, rcx
0x180015ee5  jnz     short loc_180015EDC
0x180015ee7  mov     r9, [rbx+18h]
0x180015eeb  test    r9, r9
0x180015eee  jz      short loc_180015F5F
0x180015ef0  test    edi, edi
0x180015ef2  jz      short loc_180015F25
0x180015ef4  movzx   eax, word ptr [rbx+20h]
0x180015ef8  mov     rcx, r9
0x180015efb  lea     rdx, [rax+rax*4]
0x180015eff  shl     rdx, 4
0x180015f03  add     rdx, r9
0x180015f06  cmp     r9, rdx
0x180015f09  jz      short loc_180015F25
0x180015f0b  mov     r8d, [rbx+10h]
0x180015f0f  cmp     [rcx+4], r8d
0x180015f13  jbe     short loc_180015F1D
0x180015f15  mov     eax, [rsi+8]
0x180015f18  cmp     [rcx+8], eax
0x180015f1b  jz      short loc_180015F5F
0x180015f1d  add     rcx, rbp
0x180015f20  cmp     rcx, rdx
0x180015f23  jnz     short loc_180015F0F
0x180015f25  movzx   eax, word ptr [rbx+22h]
0x180015f29  xor     edx, edx
0x180015f2b  movzx   ecx, word ptr [rbx+20h]
0x180015f2f  inc     eax
0x180015f31  div     ecx
0x180015f33  mov     rax, [rbx+8]
0x180015f37  mov     r8d, 1
0x180015f3d  mov     [rbx+22h], dx
0x180015f41  lock xadd [rax], r8d
0x180015f46  movzx   eax, dx
0x180015f49  inc     r8d; unsigned int
0x180015f4c  mov     rdx, rsi; struct wil::FailureInfo *
0x180015f4f  lea     rcx, [rax+rax*4]
0x180015f53  shl     rcx, 4
0x180015f57  add     rcx, r9; this
0x180015f5a  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180015f5f  add     rsp, 28h
0x180015f63  pop     rdi
0x180015f64  pop     rsi
0x180015f65  pop     rbp
0x180015f66  pop     rbx
0x180015f67  retn
```
