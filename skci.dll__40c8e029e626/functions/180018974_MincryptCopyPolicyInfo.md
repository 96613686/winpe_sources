# MincryptCopyPolicyInfo

- ea: `0x180018974`
- end: `0x1800189fe`
- name: `MincryptCopyPolicyInfo`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18004a6d4`

## callees

- `0x180018800`
- `0x180018974`
- `0x18003392c`

## import_xrefs

- `securekernel!SkAllocatePool` at `0x18001899e`
- `securekernel!SkAllocatePool` at `0x18001899e`

## pseudocode

```c
__int64 __fastcall MincryptCopyPolicyInfo(__int64 a1, _OWORD *a2)
{
  unsigned int *v2; // rbp
  void *v5; // rbx
  void *Pool; // rax
  __int64 result; // rax
  __int64 v8; // rdx

  v2 = *(unsigned int **)(a1 + 16);
  if ( v2 )
  {
    Pool = (void *)SkAllocatePool(1, *v2, 1919109443);
    v5 = Pool;
    if ( !Pool )
      return 3221225495LL;
    memcpy_0(Pool, v2, *v2);
    LOBYTE(v8) = 1;
    I_MincryptRebaseChainInfo(v5, v8, v2, v5);
  }
  else
  {
    v5 = 0;
  }
  result = 0;
  *a2 = *(_OWORD *)a1;
  a2[1] = *(_OWORD *)(a1 + 16);
  a2[2] = *(_OWORD *)(a1 + 32);
  *((_QWORD *)a2 + 2) = v5;
  return result;
}

```

## disassembly

```asm
0x180018974  push    rbx
0x180018976  push    rbp
0x180018977  push    rsi
0x180018978  push    rdi
0x180018979  sub     rsp, 28h
0x18001897d  mov     rbp, [rcx+10h]
0x180018981  mov     rsi, rdx
0x180018984  mov     rdi, rcx
0x180018987  test    rbp, rbp
0x18001898a  jnz     short loc_180018990
0x18001898c  xor     ebx, ebx
0x18001898e  jmp     short loc_1800189D8
0x180018990  mov     edx, [rbp+0]
0x180018993  mov     ecx, 1
0x180018998  mov     r8d, 72634943h
0x18001899e  call    cs:__imp_SkAllocatePool
0x1800189a5  nop     dword ptr [rax+rax+00h]
0x1800189aa  mov     rbx, rax
0x1800189ad  test    rax, rax
0x1800189b0  jnz     short loc_1800189B9
0x1800189b2  mov     eax, 0C0000017h
0x1800189b7  jmp     short loc_1800189F4
0x1800189b9  mov     r8d, [rbp+0]; MaxCount
0x1800189bd  mov     rdx, rbp; Src
0x1800189c0  mov     rcx, rbx; void *
0x1800189c3  call    memcpy_0
0x1800189c8  mov     r9, rbx
0x1800189cb  mov     r8, rbp
0x1800189ce  mov     dl, 1
0x1800189d0  mov     rcx, rbx
0x1800189d3  call    I_MincryptRebaseChainInfo
0x1800189d8  movups  xmm0, xmmword ptr [rdi]
0x1800189db  xor     eax, eax
0x1800189dd  movups  xmmword ptr [rsi], xmm0
0x1800189e0  movups  xmm1, xmmword ptr [rdi+10h]
0x1800189e4  movups  xmmword ptr [rsi+10h], xmm1
0x1800189e8  movups  xmm0, xmmword ptr [rdi+20h]
0x1800189ec  movups  xmmword ptr [rsi+20h], xmm0
0x1800189f0  mov     [rsi+10h], rbx
0x1800189f4  add     rsp, 28h
0x1800189f8  pop     rdi
0x1800189f9  pop     rsi
0x1800189fa  pop     rbp
0x1800189fb  pop     rbx
0x1800189fc  retn
```
