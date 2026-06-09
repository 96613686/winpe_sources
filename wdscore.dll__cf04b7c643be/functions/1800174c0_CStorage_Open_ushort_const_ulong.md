# CStorage::Open(ushort const *,ulong)

- ea: `0x1800174c0`
- end: `0x180017591`
- name: `?Open@CStorage@@QEAAHPEBGK@Z`
- size: `209`
- prototype: `__int64 __fastcall(CStorage *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180016950`

## callees

- `0x180010400`
- `0x18001541c`
- `0x1800165ac`
- `0x18001700c`
- `0x1800174c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStorage::Open(CStorage *this, size_t *a2, int a3)
{
  const unsigned __int16 **v5; // r14
  unsigned __int16 *v7; // [rsp+60h] [rbp+8h] BYREF

  v5 = (const unsigned __int16 **)((char *)this + 8);
  if ( !(unsigned int)CStorage::MakePathConsistent(a2, (_QWORD *)this + 1, a3 & 2) )
    return 0;
  *((_DWORD *)this + 10) = a3;
  if ( !CObjectName::Init((CStorage *)((char *)this + 56), *v5, L"Storage") )
    return 0;
  v7 = 0;
  if ( !CObjectName::Init((CObjectName *)&v7, *((const unsigned __int16 **)this + 7), L"Mtx")
    || !(unsigned int)CStorage::Open(this, (const char *)*v5, v7, a3) )
  {
    CObjectName::Close((CStorage *)((char *)this + 56));
    CObjectName::Close((CObjectName *)&v7);
    return 0;
  }
  CObjectName::Close((CObjectName *)&v7);
  return 1;
}

```

## disassembly

```asm
0x1800174c0  push    rbx
0x1800174c2  push    rsi
0x1800174c3  push    rdi
0x1800174c4  push    r14
0x1800174c6  sub     rsp, 38h
0x1800174ca  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800174d3  mov     esi, r8d
0x1800174d6  mov     rax, rdx
0x1800174d9  mov     rdi, rcx
0x1800174dc  lea     r14, [rcx+8]
0x1800174e0  and     r8d, 2
0x1800174e4  mov     rdx, r14
0x1800174e7  mov     rcx, rax; unsigned __int16 *
0x1800174ea  call    ?MakePathConsistent@CStorage@@SAHPEBGAEAV?$CDynamicArray@GPEAG@@H@Z; CStorage::MakePathConsistent(ushort const *,CDynamicArray<ushort,ushort *> &,int)
0x1800174ef  test    eax, eax
0x1800174f1  jz      short loc_180017545
0x1800174f3  mov     [rdi+28h], esi
0x1800174f6  lea     rbx, [rdi+38h]
0x1800174fa  lea     r8, aStorage; "Storage"
0x180017501  mov     rdx, [r14]; unsigned __int16 *
0x180017504  mov     rcx, rbx; this
0x180017507  call    ?Init@CObjectName@@QEAAHPEBG0@Z; CObjectName::Init(ushort const *,ushort const *)
0x18001750c  test    eax, eax
0x18001750e  jz      short loc_180017545
0x180017510  mov     [rsp+58h+arg_0], 0
0x180017519  lea     r8, aMtx; "Mtx"
0x180017520  mov     rdx, [rbx]; unsigned __int16 *
0x180017523  lea     rcx, [rsp+58h+arg_0]; this
0x180017528  call    ?Init@CObjectName@@QEAAHPEBG0@Z; CObjectName::Init(ushort const *,ushort const *)
0x18001752d  test    eax, eax
0x18001752f  jnz     short loc_180017552
0x180017531  mov     rcx, rbx; this
0x180017534  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180017539  nop
0x18001753a  lea     rcx, [rsp+58h+arg_0]; this
0x18001753f  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180017544  nop
0x180017545  xor     eax, eax
0x180017547  add     rsp, 38h
0x18001754b  pop     r14
0x18001754d  pop     rdi
0x18001754e  pop     rsi
0x18001754f  pop     rbx
0x180017550  retn
0x180017552  mov     r9d, esi; unsigned int
0x180017555  mov     r8, [rsp+58h+arg_0]; unsigned __int16 *
0x18001755a  mov     rdx, [r14]; Src
0x18001755d  mov     rcx, rdi; this
0x180017560  call    ?Open@CStorage@@IEAAHPEBG0K@Z; CStorage::Open(ushort const *,ushort const *,ulong)
0x180017565  test    eax, eax
0x180017567  jnz     short loc_18001757F
0x180017569  mov     rcx, rbx; this
0x18001756c  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180017571  nop
0x180017572  lea     rcx, [rsp+58h+arg_0]; this
0x180017577  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x18001757c  nop
0x18001757d  jmp     short loc_180017545
0x18001757f  lea     rcx, [rsp+58h+arg_0]; this
0x180017584  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180017589  nop
0x18001758a  mov     eax, 1
0x18001758f  jmp     short loc_180017547
```
