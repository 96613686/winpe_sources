# CDbAccessor::AddColumn(ulong,ushort,ulong,uchar,uchar,ulong)

- ea: `0x180018520`
- end: `0x18001868c`
- name: `?AddColumn@CDbAccessor@@QEAAJKGKEEK@Z`
- size: `364`
- prototype: `__int64 __fastcall(CDbAccessor *__hidden this, unsigned int, unsigned __int16, unsigned int, char, char, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800186a0`

## callees

- `0x18000214c`
- `0x1800024b2`
- `0x180018520`
- `0x180030362`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180018660`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018660`

## pseudocode

```c
__int64 __fastcall CDbAccessor::AddColumn(
        CDbAccessor *this,
        unsigned int a2,
        __int16 a3,
        unsigned int a4,
        char a5,
        char a6,
        unsigned int a7)
{
  unsigned int v7; // edi
  __int64 v8; // r15
  unsigned __int64 v10; // r10
  __int64 v11; // rbp
  unsigned __int64 v13; // rax
  void *v14; // rsi
  __int64 v15; // rdx
  void *v16; // rcx

  v7 = 0;
  v8 = a2;
  v10 = (unsigned int)(*((_DWORD *)this + 6) + 1);
  v11 = a4;
  v13 = 88 * v10;
  if ( !is_mul_ok(v10, 0x58u) )
    v13 = -1;
  v14 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  if ( v14 )
  {
    memset_0(v14, 0, 88LL * (unsigned int)(*((_DWORD *)this + 6) + 1));
    memmove_0(v14, *((const void **)this + 2), 88LL * *((unsigned int *)this + 6));
    *((_QWORD *)v14 + 11 * *((unsigned int *)this + 6)) = v8;
    *((_WORD *)v14 + 44 * *((unsigned int *)this + 6) + 42) = a3;
    *((_BYTE *)v14 + 88 * *((unsigned int *)this + 6) + 86) = a5;
    *((_BYTE *)v14 + 88 * *((unsigned int *)this + 6) + 87) = a6;
    *((_DWORD *)v14 + 22 * *((unsigned int *)this + 6) + 15) = 0;
    *((_DWORD *)v14 + 22 * *((unsigned int *)this + 6) + 14) = 7;
    *((_DWORD *)v14 + 22 * *((unsigned int *)this + 6) + 16) = a7;
    *((_QWORD *)v14 + 11 * *((unsigned int *)this + 6) + 9) = v11;
    *((_QWORD *)v14 + 11 * *((unsigned int *)this + 6) + 2) = *((unsigned int *)this + 10);
    *((_DWORD *)this + 10) += 8;
    *((_QWORD *)v14 + 11 * *((unsigned int *)this + 6) + 3) = *((unsigned int *)this + 10);
    *((_DWORD *)this + 10) += 4;
    *((_QWORD *)v14 + 11 * *((unsigned int *)this + 6) + 1) = *((unsigned int *)this + 10);
    v15 = *((unsigned int *)this + 6);
    *((_DWORD *)this + 10) += *((_DWORD *)v14 + 22 * v15 + 18);
    *((_DWORD *)this + 6) = v15 + 1;
    v16 = (void *)*((_QWORD *)this + 2);
    if ( v16 )
      operator delete(v16);
    *((_QWORD *)this + 2) = v14;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180018520  mov     [rsp+arg_0], rbx
0x180018525  mov     [rsp+arg_8], rbp
0x18001852a  mov     [rsp+arg_10], rsi
0x18001852f  push    rdi
0x180018530  push    r14
0x180018532  push    r15
0x180018534  sub     rsp, 20h
0x180018538  mov     r10d, [rcx+18h]
0x18001853c  xor     edi, edi
0x18001853e  mov     r15d, edx
0x180018541  mov     rbx, rcx
0x180018544  inc     r10d
0x180018547  mov     ebp, r9d
0x18001854a  movzx   r14d, r8w
0x18001854e  lea     rcx, [rdi-1]
0x180018552  lea     eax, [rdi+58h]
0x180018555  mul     r10
0x180018558  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001855f  cmovo   rax, rcx
0x180018563  mov     rcx, rax; unsigned __int64
0x180018566  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001856b  mov     rsi, rax
0x18001856e  test    rax, rax
0x180018571  jnz     short loc_18001857D
0x180018573  mov     edi, 8007000Eh
0x180018578  jmp     loc_180018670
0x18001857d  mov     eax, [rbx+18h]
0x180018580  xor     edx, edx; Val
0x180018582  inc     eax
0x180018584  mov     rcx, rsi; void *
0x180018587  imul    r8, rax, 58h ; 'X'; Size
0x18001858b  call    memset_0
0x180018590  mov     eax, [rbx+18h]
0x180018593  mov     rcx, rsi; void *
0x180018596  mov     rdx, [rbx+10h]; Src
0x18001859a  imul    r8, rax, 58h ; 'X'; Size
0x18001859e  call    memmove_0
0x1800185a3  mov     eax, [rbx+18h]
0x1800185a6  imul    rcx, rax, 58h ; 'X'
0x1800185aa  mov     [rcx+rsi], r15
0x1800185ae  mov     eax, [rbx+18h]
0x1800185b1  imul    rcx, rax, 58h ; 'X'
0x1800185b5  mov     [rcx+rsi+54h], r14w
0x1800185bb  mov     eax, [rbx+18h]
0x1800185be  imul    rcx, rax, 58h ; 'X'
0x1800185c2  mov     al, [rsp+38h+arg_20]
0x1800185c6  mov     [rcx+rsi+56h], al
0x1800185ca  mov     eax, [rbx+18h]
0x1800185cd  imul    rcx, rax, 58h ; 'X'
0x1800185d1  mov     al, [rsp+38h+arg_28]
0x1800185d5  mov     [rcx+rsi+57h], al
0x1800185d9  mov     eax, [rbx+18h]
0x1800185dc  imul    rcx, rax, 58h ; 'X'
0x1800185e0  mov     [rcx+rsi+3Ch], edi
0x1800185e4  mov     eax, [rbx+18h]
0x1800185e7  imul    rcx, rax, 58h ; 'X'
0x1800185eb  mov     dword ptr [rcx+rsi+38h], 7
0x1800185f3  mov     eax, [rbx+18h]
0x1800185f6  imul    rcx, rax, 58h ; 'X'
0x1800185fa  mov     eax, [rsp+38h+arg_30]
0x1800185fe  mov     [rcx+rsi+40h], eax
0x180018602  mov     eax, [rbx+18h]
0x180018605  imul    rcx, rax, 58h ; 'X'
0x180018609  mov     [rcx+rsi+48h], rbp
0x18001860e  mov     edx, [rbx+28h]
0x180018611  mov     eax, [rbx+18h]
0x180018614  imul    rcx, rax, 58h ; 'X'
0x180018618  mov     [rcx+rsi+10h], rdx
0x18001861d  add     dword ptr [rbx+28h], 8
0x180018621  mov     eax, [rbx+18h]
0x180018624  mov     edx, [rbx+28h]
0x180018627  imul    rcx, rax, 58h ; 'X'
0x18001862b  mov     [rcx+rsi+18h], rdx
0x180018630  add     dword ptr [rbx+28h], 4
0x180018634  mov     eax, [rbx+18h]
0x180018637  mov     edx, [rbx+28h]
0x18001863a  imul    rcx, rax, 58h ; 'X'
0x18001863e  mov     [rcx+rsi+8], rdx
0x180018643  mov     edx, [rbx+18h]
0x180018646  imul    rax, rdx, 58h ; 'X'
0x18001864a  mov     ecx, [rax+rsi+48h]
0x18001864e  add     [rbx+28h], ecx
0x180018651  lea     ecx, [rdx+1]
0x180018654  mov     [rbx+18h], ecx
0x180018657  mov     rcx, [rbx+10h]
0x18001865b  test    rcx, rcx
0x18001865e  jz      short loc_18001866C
0x180018660  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018667  nop     dword ptr [rax+rax+00h]
0x18001866c  mov     [rbx+10h], rsi
0x180018670  mov     rbx, [rsp+38h+arg_0]
0x180018675  mov     eax, edi
0x180018677  mov     rbp, [rsp+38h+arg_8]
0x18001867c  mov     rsi, [rsp+38h+arg_10]
0x180018681  add     rsp, 20h
0x180018685  pop     r15
0x180018687  pop     r14
0x180018689  pop     rdi
0x18001868a  retn
```
