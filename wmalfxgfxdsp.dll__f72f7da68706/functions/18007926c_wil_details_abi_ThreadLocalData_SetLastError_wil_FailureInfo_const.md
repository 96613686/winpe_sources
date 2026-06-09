# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18007926c`
- end: `0x18007933b`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014cc4`

## callees

- `0x18007892c`
- `0x180078fcc`
- `0x18007926c`

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
0x18007926c  push    rbx
0x18007926e  push    rbp
0x18007926f  push    rsi
0x180079270  push    rdi
0x180079271  sub     rsp, 28h
0x180079275  cmp     qword ptr [rcx+18h], 0
0x18007927a  mov     rsi, rdx
0x18007927d  mov     edi, [rcx+10h]
0x180079280  mov     rbx, rcx
0x180079283  mov     ebp, 50h ; 'P'
0x180079288  jnz     short loc_1800792BF
0x18007928a  test    edi, edi
0x18007928c  jz      short loc_1800792BF
0x18007928e  mov     edx, 190h; dwBytes
0x180079293  lea     ecx, [rbp-48h]; dwFlags
0x180079296  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18007929b  mov     [rbx+18h], rax
0x18007929f  test    rax, rax
0x1800792a2  jz      short loc_1800792BF
0x1800792a4  mov     dword ptr [rbx+20h], 5
0x1800792ab  lea     rcx, [rax+190h]
0x1800792b2  jmp     short loc_1800792BA
0x1800792b4  mov     [rax], bp
0x1800792b7  add     rax, rbp
0x1800792ba  cmp     rax, rcx
0x1800792bd  jnz     short loc_1800792B4
0x1800792bf  mov     r9, [rbx+18h]
0x1800792c3  test    r9, r9
0x1800792c6  jz      short loc_180079332
0x1800792c8  test    edi, edi
0x1800792ca  jz      short loc_1800792F8
0x1800792cc  movzx   eax, word ptr [rbx+20h]
0x1800792d0  mov     rcx, r9
0x1800792d3  lea     rdx, [rax+rax*4]
0x1800792d7  shl     rdx, 4
0x1800792db  add     rdx, r9
0x1800792de  cmp     rcx, rdx
0x1800792e1  jz      short loc_1800792F8
0x1800792e3  mov     eax, [rbx+10h]
0x1800792e6  cmp     [rcx+4], eax
0x1800792e9  jbe     short loc_1800792F3
0x1800792eb  mov     eax, [rsi+8]
0x1800792ee  cmp     [rcx+8], eax
0x1800792f1  jz      short loc_180079332
0x1800792f3  add     rcx, rbp
0x1800792f6  jmp     short loc_1800792DE
0x1800792f8  movzx   eax, word ptr [rbx+22h]
0x1800792fc  xor     edx, edx
0x1800792fe  movzx   ecx, word ptr [rbx+20h]
0x180079302  inc     eax
0x180079304  div     ecx
0x180079306  mov     rax, [rbx+8]
0x18007930a  mov     r8d, 1
0x180079310  mov     [rbx+22h], dx
0x180079314  lock xadd [rax], r8d
0x180079319  movzx   eax, dx
0x18007931c  inc     r8d; unsigned int
0x18007931f  mov     rdx, rsi; struct wil::FailureInfo *
0x180079322  lea     rcx, [rax+rax*4]
0x180079326  shl     rcx, 4
0x18007932a  add     rcx, r9; this
0x18007932d  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180079332  add     rsp, 28h
0x180079336  pop     rdi
0x180079337  pop     rsi
0x180079338  pop     rbp
0x180079339  pop     rbx
0x18007933a  retn
```
