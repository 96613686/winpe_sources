# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180024cbc`
- end: `0x180024d97`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `219`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bae0`

## callees

- `0x18001f77c`
- `0x1800244ac`
- `0x180024cbc`

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
0x180024cbc  mov     [rsp+arg_10], rbx
0x180024cc1  push    rbp
0x180024cc2  push    rsi
0x180024cc3  push    rdi
0x180024cc4  sub     rsp, 20h
0x180024cc8  cmp     qword ptr [rcx+18h], 0
0x180024ccd  mov     rsi, rdx
0x180024cd0  mov     edi, [rcx+10h]
0x180024cd3  mov     rbx, rcx
0x180024cd6  mov     ebp, 50h ; 'P'
0x180024cdb  jnz     short loc_180024D12
0x180024cdd  test    edi, edi
0x180024cdf  jz      short loc_180024D12
0x180024ce1  mov     edx, 190h; dwBytes
0x180024ce6  lea     ecx, [rbp-48h]; dwFlags
0x180024ce9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180024cee  mov     [rbx+18h], rax
0x180024cf2  test    rax, rax
0x180024cf5  jz      short loc_180024D12
0x180024cf7  mov     dword ptr [rbx+20h], 5
0x180024cfe  lea     rcx, [rax+190h]
0x180024d05  jmp     short loc_180024D0D
0x180024d07  mov     [rax], bp
0x180024d0a  add     rax, rbp
0x180024d0d  cmp     rax, rcx
0x180024d10  jnz     short loc_180024D07
0x180024d12  mov     r9, [rbx+18h]
0x180024d16  test    r9, r9
0x180024d19  jz      short loc_180024D8A
0x180024d1b  test    edi, edi
0x180024d1d  jz      short loc_180024D50
0x180024d1f  movzx   eax, word ptr [rbx+20h]
0x180024d23  mov     rcx, r9
0x180024d26  lea     rdx, [rax+rax*4]
0x180024d2a  shl     rdx, 4
0x180024d2e  add     rdx, r9
0x180024d31  cmp     r9, rdx
0x180024d34  jz      short loc_180024D50
0x180024d36  mov     r8d, [rbx+10h]
0x180024d3a  cmp     [rcx+4], r8d
0x180024d3e  jbe     short loc_180024D48
0x180024d40  mov     eax, [rsi+8]
0x180024d43  cmp     [rcx+8], eax
0x180024d46  jz      short loc_180024D8A
0x180024d48  add     rcx, rbp
0x180024d4b  cmp     rcx, rdx
0x180024d4e  jnz     short loc_180024D3A
0x180024d50  movzx   eax, word ptr [rbx+22h]
0x180024d54  xor     edx, edx
0x180024d56  movzx   ecx, word ptr [rbx+20h]
0x180024d5a  inc     eax
0x180024d5c  div     ecx
0x180024d5e  mov     rax, [rbx+8]
0x180024d62  mov     r8d, 1
0x180024d68  mov     [rbx+22h], dx
0x180024d6c  lock xadd [rax], r8d
0x180024d71  movzx   eax, dx
0x180024d74  inc     r8d; unsigned int
0x180024d77  mov     rdx, rsi; struct wil::FailureInfo *
0x180024d7a  lea     rcx, [rax+rax*4]
0x180024d7e  shl     rcx, 4
0x180024d82  add     rcx, r9; this
0x180024d85  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180024d8a  mov     rbx, [rsp+38h+arg_10]
0x180024d8f  add     rsp, 20h
0x180024d93  pop     rdi
0x180024d94  pop     rsi
0x180024d95  pop     rbp
0x180024d96  retn
```
