# BuildString::AppendSz(ushort const *,long)

- ea: `0x1800023d0`
- end: `0x180002447`
- name: `?AppendSz@BuildString@@QEAAXPEBGJ@Z`
- size: `119`
- prototype: `void(BuildString *__hidden this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800021d0`
- `0x180008f7c`
- `0x180009708`

## callees

- `0x1800023d0`
- `0x180002450`
- `0x18000d172`

## pseudocode

```c
void __fastcall BuildString::AppendSz(BuildString *this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rbx

  LODWORD(v3) = a3;
  if ( a3 < 0 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
  }
  BuildString::EnsureSpace(this, v3 + *((_DWORD *)this + 3));
  if ( !*((_DWORD *)this + 4) )
  {
    memcpy_0((void *)(*(_QWORD *)this + 2LL * *((int *)this + 3)), a2, 2LL * (int)v3);
    *((_DWORD *)this + 3) += v3;
    *(_WORD *)(*(_QWORD *)this + 2LL * *((int *)this + 3)) = 0;
  }
}

```

## disassembly

```asm
0x1800023d0  mov     [rsp+arg_0], rbx
0x1800023d5  mov     [rsp+arg_8], rsi
0x1800023da  push    rdi
0x1800023db  sub     rsp, 20h
0x1800023df  mov     ebx, r8d
0x1800023e2  mov     rdi, rdx
0x1800023e5  mov     rsi, rcx
0x1800023e8  test    r8d, r8d
0x1800023eb  jns     short loc_1800023FE
0x1800023ed  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800023f4  inc     rbx
0x1800023f7  cmp     word ptr [rdx+rbx*2], 0
0x1800023fc  jnz     short loc_1800023F4
0x1800023fe  mov     edx, [rcx+0Ch]
0x180002401  add     edx, ebx; int
0x180002403  call    ?EnsureSpace@BuildString@@AEAAXJ@Z; BuildString::EnsureSpace(long)
0x180002408  cmp     dword ptr [rsi+10h], 0
0x18000240c  jnz     short loc_180002437
0x18000240e  movsxd  rcx, dword ptr [rsi+0Ch]
0x180002412  mov     rdx, rdi; Src
0x180002415  mov     rax, [rsi]
0x180002418  movsxd  r8, ebx
0x18000241b  add     r8, r8; Size
0x18000241e  lea     rcx, [rax+rcx*2]; void *
0x180002422  call    memcpy_0
0x180002427  add     [rsi+0Ch], ebx
0x18000242a  movsxd  rcx, dword ptr [rsi+0Ch]
0x18000242e  xor     edx, edx
0x180002430  mov     rax, [rsi]
0x180002433  mov     [rax+rcx*2], dx
0x180002437  mov     rbx, [rsp+28h+arg_0]
0x18000243c  mov     rsi, [rsp+28h+arg_8]
0x180002441  add     rsp, 20h
0x180002445  pop     rdi
0x180002446  retn
```
