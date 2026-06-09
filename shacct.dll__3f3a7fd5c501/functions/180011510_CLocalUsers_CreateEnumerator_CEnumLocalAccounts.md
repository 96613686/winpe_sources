# CLocalUsers::_CreateEnumerator(CEnumLocalAccounts * *)

- ea: `0x180011510`
- end: `0x180011595`
- name: `?_CreateEnumerator@CLocalUsers@@MEAAJPEAPEAVCEnumLocalAccounts@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(CLocalUsers *__hidden this, struct CEnumLocalAccounts **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000d740`
- `0x18000f05c`
- `0x180011510`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CLocalUsers::_CreateEnumerator(CLocalUsers *this, struct CEnumLocalAccounts **a2)
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
        v4 = CEnumLocalUsers::CEnumLocalUsers((CEnumLocalUsers *)v3),
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
0x180011510  mov     [rsp+arg_0], rbx
0x180011515  push    rdi
0x180011516  sub     rsp, 20h
0x18001151a  mov     rdi, rdx
0x18001151d  mov     ecx, 38h ; '8'; unsigned __int64
0x180011522  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011529  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001152e  test    rax, rax
0x180011531  jz      short loc_18001157C
0x180011533  xorps   xmm0, xmm0
0x180011536  xor     ecx, ecx
0x180011538  movups  xmmword ptr [rax], xmm0
0x18001153b  movups  xmmword ptr [rax+10h], xmm0
0x18001153f  movups  xmmword ptr [rax+20h], xmm0
0x180011543  mov     [rax+30h], rcx
0x180011547  mov     rcx, rax; this
0x18001154a  call    ??0CEnumLocalUsers@@QEAA@XZ; CEnumLocalUsers::CEnumLocalUsers(void)
0x18001154f  mov     rbx, rax
0x180011552  test    rax, rax
0x180011555  jz      short loc_18001157C
0x180011557  mov     [rdi], rax
0x18001155a  mov     rcx, [rax]
0x18001155d  mov     rax, [rcx+8]
0x180011561  mov     rcx, rbx
0x180011564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011569  mov     rcx, [rbx]
0x18001156c  xor     edi, edi
0x18001156e  mov     rax, [rcx+10h]
0x180011572  mov     rcx, rbx
0x180011575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001157a  jmp     short loc_180011588
0x18001157c  mov     qword ptr [rdi], 0
0x180011583  mov     edi, 8007000Eh
0x180011588  mov     rbx, [rsp+28h+arg_0]
0x18001158d  mov     eax, edi
0x18001158f  add     rsp, 20h
0x180011593  pop     rdi
0x180011594  retn
```
