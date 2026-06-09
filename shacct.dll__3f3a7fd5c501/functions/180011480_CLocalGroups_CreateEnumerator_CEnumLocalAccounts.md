# CLocalGroups::_CreateEnumerator(CEnumLocalAccounts * *)

- ea: `0x180011480`
- end: `0x180011505`
- name: `?_CreateEnumerator@CLocalGroups@@EEAAJPEAPEAVCEnumLocalAccounts@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(CLocalGroups *__hidden this, struct CEnumLocalAccounts **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000d740`
- `0x18000f038`
- `0x180011480`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CLocalGroups::_CreateEnumerator(CLocalGroups *this, struct CEnumLocalAccounts **a2)
{
  _OWORD *v3; // rax
  struct CEnumLocalAccounts *v4; // rax
  struct CEnumLocalAccounts *v5; // rbx
  unsigned int v6; // edi

  v3 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v3
    && (*v3 = 0,
        v3[1] = 0,
        v3[2] = 0,
        *((_QWORD *)v3 + 6) = 0,
        v4 = CEnumLocalGroups::CEnumLocalGroups((CEnumLocalGroups *)v3),
        (v5 = v4) != 0) )
  {
    *a2 = v4;
    (*(void (__fastcall **)(struct CEnumLocalAccounts *))(*(_QWORD *)v4 + 8LL))(v4);
    v6 = 0;
    (*(void (__fastcall **)(struct CEnumLocalAccounts *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else
  {
    *a2 = 0;
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x180011480  mov     [rsp+arg_0], rbx
0x180011485  push    rdi
0x180011486  sub     rsp, 20h
0x18001148a  mov     rdi, rdx
0x18001148d  mov     ecx, 38h ; '8'; unsigned __int64
0x180011492  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011499  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001149e  test    rax, rax
0x1800114a1  jz      short loc_1800114EC
0x1800114a3  xorps   xmm0, xmm0
0x1800114a6  xor     ecx, ecx
0x1800114a8  movups  xmmword ptr [rax], xmm0
0x1800114ab  movups  xmmword ptr [rax+10h], xmm0
0x1800114af  movups  xmmword ptr [rax+20h], xmm0
0x1800114b3  mov     [rax+30h], rcx
0x1800114b7  mov     rcx, rax; this
0x1800114ba  call    ??0CEnumLocalGroups@@QEAA@XZ; CEnumLocalGroups::CEnumLocalGroups(void)
0x1800114bf  mov     rbx, rax
0x1800114c2  test    rax, rax
0x1800114c5  jz      short loc_1800114EC
0x1800114c7  mov     [rdi], rax
0x1800114ca  mov     rcx, [rax]
0x1800114cd  mov     rax, [rcx+8]
0x1800114d1  mov     rcx, rbx
0x1800114d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114d9  mov     rcx, [rbx]
0x1800114dc  xor     edi, edi
0x1800114de  mov     rax, [rcx+10h]
0x1800114e2  mov     rcx, rbx
0x1800114e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114ea  jmp     short loc_1800114F8
0x1800114ec  mov     qword ptr [rdi], 0
0x1800114f3  mov     edi, 8007000Eh
0x1800114f8  mov     rbx, [rsp+28h+arg_0]
0x1800114fd  mov     eax, edi
0x1800114ff  add     rsp, 20h
0x180011503  pop     rdi
0x180011504  retn
```
