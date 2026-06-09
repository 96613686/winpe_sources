# CDbAccessor::CreateAccessor(ulong)

- ea: `0x180018720`
- end: `0x180018842`
- name: `?CreateAccessor@CDbAccessor@@QEAAJK@Z`
- size: `290`
- prototype: `__int64 __fastcall(CDbAccessor *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800189c0`

## callees

- `0x18000214c`
- `0x180018720`
- `0x1800193f0`
- `0x180030362`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180018789`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001881e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018789`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001881e`

## pseudocode

```c
__int64 __fastcall CDbAccessor::CreateAccessor(CDbAccessor *this, unsigned int a2)
{
  unsigned __int64 v4; // rax
  void *v5; // rsi
  int v6; // edi
  void *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rax

  v4 = 4LL * *((unsigned int *)this + 6);
  if ( !is_mul_ok(*((unsigned int *)this + 6), 4u) )
    v4 = -1;
  v5 = operator new[](v4, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    if ( *((_QWORD *)this + 4) )
    {
      CDbAccessor::ReleaseRowBuffer(this);
      v7 = (void *)*((_QWORD *)this + 4);
      if ( v7 )
        operator delete(v7);
      *((_QWORD *)this + 4) = 0;
    }
    v8 = *((_QWORD *)this + 6);
    if ( v8 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)this + 48LL))(*(_QWORD *)this, v8, 0);
      *((_QWORD *)this + 6) = 0;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, char *, void *))(**(_QWORD **)this + 32LL))(
           *(_QWORD *)this,
           a2,
           *((unsigned int *)this + 6),
           *((_QWORD *)this + 2),
           *((unsigned int *)this + 10),
           (char *)this + 48,
           v5);
    if ( v6 >= 0 )
    {
      v9 = operator new[](*((unsigned int *)this + 10), (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 4) = v9;
      if ( v9 )
        memset_0(v9, 0, *((unsigned int *)this + 10));
      else
        v6 = -2147024882;
    }
    operator delete(v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018720  mov     [rsp+arg_0], rbx
0x180018725  mov     [rsp+arg_8], rbp
0x18001872a  mov     [rsp+arg_10], rsi
0x18001872f  push    rdi
0x180018730  sub     rsp, 40h
0x180018734  mov     r8d, [rcx+18h]
0x180018738  mov     ebp, edx
0x18001873a  mov     rbx, rcx
0x18001873d  mov     eax, 4
0x180018742  mul     r8
0x180018745  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001874c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018753  cmovo   rax, rcx
0x180018757  mov     rcx, rax; unsigned __int64
0x18001875a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001875f  mov     rsi, rax
0x180018762  test    rax, rax
0x180018765  jnz     short loc_180018771
0x180018767  mov     edi, 8007000Eh
0x18001876c  jmp     loc_18001882A
0x180018771  cmp     qword ptr [rbx+20h], 0
0x180018776  jz      short loc_18001879A
0x180018778  mov     rcx, rbx; this
0x18001877b  call    ?ReleaseRowBuffer@CDbAccessor@@QEAAXXZ; CDbAccessor::ReleaseRowBuffer(void)
0x180018780  mov     rcx, [rbx+20h]
0x180018784  test    rcx, rcx
0x180018787  jz      short loc_180018795
0x180018789  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018790  nop     dword ptr [rax+rax+00h]
0x180018795  and     qword ptr [rbx+20h], 0
0x18001879a  lea     rdi, [rbx+30h]
0x18001879e  mov     rdx, [rdi]
0x1800187a1  test    rdx, rdx
0x1800187a4  jz      short loc_1800187BC
0x1800187a6  mov     rcx, [rbx]
0x1800187a9  xor     r8d, r8d
0x1800187ac  mov     rax, [rcx]
0x1800187af  mov     rax, [rax+30h]
0x1800187b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187b8  and     qword ptr [rdi], 0
0x1800187bc  mov     r9d, [rbx+28h]
0x1800187c0  mov     edx, ebp
0x1800187c2  mov     rcx, [rbx]
0x1800187c5  mov     r8d, [rbx+18h]
0x1800187c9  mov     [rsp+48h+var_18], rsi
0x1800187ce  mov     [rsp+48h+var_20], rdi
0x1800187d3  mov     rax, [rcx]
0x1800187d6  mov     [rsp+48h+var_28], r9
0x1800187db  mov     r9, [rbx+10h]
0x1800187df  mov     rax, [rax+20h]
0x1800187e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187e8  mov     edi, eax
0x1800187ea  test    eax, eax
0x1800187ec  js      short loc_18001881B
0x1800187ee  mov     ecx, [rbx+28h]; unsigned __int64
0x1800187f1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800187f8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800187fd  mov     [rbx+20h], rax
0x180018801  test    rax, rax
0x180018804  jnz     short loc_18001880D
0x180018806  mov     edi, 8007000Eh
0x18001880b  jmp     short loc_18001881B
0x18001880d  mov     r8d, [rbx+28h]; Size
0x180018811  xor     edx, edx; Val
0x180018813  mov     rcx, rax; void *
0x180018816  call    memset_0
0x18001881b  mov     rcx, rsi
0x18001881e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018825  nop     dword ptr [rax+rax+00h]
0x18001882a  mov     rbx, [rsp+48h+arg_0]
0x18001882f  mov     eax, edi
0x180018831  mov     rbp, [rsp+48h+arg_8]
0x180018836  mov     rsi, [rsp+48h+arg_10]
0x18001883b  add     rsp, 40h
0x18001883f  pop     rdi
0x180018840  retn
```
