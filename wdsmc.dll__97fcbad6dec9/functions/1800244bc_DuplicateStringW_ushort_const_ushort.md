# DuplicateStringW(ushort const *,ushort * *)

- ea: `0x1800244bc`
- end: `0x18002459d`
- name: `?DuplicateStringW@@YAKPEBGPEAPEAG@Z`
- size: `225`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800029f4`
- `0x1800039a0`
- `0x1800039f0`
- `0x180003f10`
- `0x18000480c`
- `0x180006488`
- `0x18000967c`
- `0x180018da4`
- `0x18002048c`
- `0x180020bd0`
- `0x180023b60`

## callees

- `0x18000b3a8`
- `0x18001a9a8`
- `0x1800244bc`
- `0x180025914`
- `0x1800259d8`
- `0x180026694`

## string_xrefs

- `0x180024531`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`

## pseudocode

```c
__int64 __fastcall DuplicateStringW(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v4; // rbx
  unsigned int v5; // esi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rax
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  int v10; // ebx
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // r8
  unsigned int v14; // r9d
  int v15; // eax

  v4 = -1;
  v5 = 0;
  do
    ++v4;
  while ( a1[v4] );
  v6 = v4 + 1;
  v7 = 2 * v6;
  if ( !is_mul_ok(v6, 2u) )
    v7 = -1;
  v8 = (unsigned __int16 *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    v10 = StringCchCopyW(v8, v6, a1);
    ElValidateHrLite(v10, v11, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp", 0x900u);
    if ( v10 >= 0 )
      v15 = v10;
    else
      v15 = ElValidateHr(v10, v12, v13, v14);
    if ( v15 >= 0 )
    {
      *a2 = v9;
      v9 = 0;
    }
    else if ( v10 < 0 && (v10 & 0x1FFF0000) == 0x70000 )
    {
      v5 = (unsigned __int16)v10;
    }
    else
    {
      v5 = v10;
    }
    if ( v9 )
      operator delete(v9);
  }
  else
  {
    return 8;
  }
  return v5;
}

```

## disassembly

```asm
0x1800244bc  mov     [rsp+arg_0], rbx
0x1800244c1  mov     [rsp+arg_8], rbp
0x1800244c6  mov     [rsp+arg_10], rsi
0x1800244cb  push    rdi
0x1800244cc  push    r14
0x1800244ce  push    r15
0x1800244d0  sub     rsp, 20h
0x1800244d4  xor     r15d, r15d
0x1800244d7  mov     rbp, rcx
0x1800244da  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800244de  mov     r14, rdx
0x1800244e1  mov     rbx, rcx
0x1800244e4  mov     esi, r15d
0x1800244e7  inc     rbx
0x1800244ea  cmp     [rbp+rbx*2+0], r15w
0x1800244f0  jnz     short loc_1800244E7
0x1800244f2  inc     rbx
0x1800244f5  mov     eax, 2
0x1800244fa  mul     rbx
0x1800244fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024504  cmovo   rax, rcx
0x180024508  mov     rcx, rax; unsigned __int64
0x18002450b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180024510  mov     rdi, rax
0x180024513  test    rax, rax
0x180024516  jnz     short loc_18002451D
0x180024518  lea     esi, [rax+8]
0x18002451b  jmp     short loc_180024582
0x18002451d  mov     r8, rbp; unsigned __int16 *
0x180024520  mov     rdx, rbx; unsigned __int64
0x180024523  mov     rcx, rdi; unsigned __int16 *
0x180024526  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002452b  mov     r9d, 900h; unsigned int
0x180024531  lea     r8, aOnecoreBaseEco_5; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024538  mov     ecx, eax; int
0x18002453a  mov     ebx, eax
0x18002453c  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x180024541  test    ebx, ebx
0x180024543  jns     short loc_18002454E
0x180024545  mov     ecx, ebx; int
0x180024547  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18002454c  jmp     short loc_180024550
0x18002454e  mov     eax, ebx
0x180024550  test    eax, eax
0x180024552  jns     short loc_18002456F
0x180024554  test    ebx, ebx
0x180024556  jns     short loc_18002456B
0x180024558  mov     eax, ebx
0x18002455a  and     eax, 1FFF0000h
0x18002455f  cmp     eax, 70000h
0x180024564  jnz     short loc_18002456B
0x180024566  movzx   esi, bx
0x180024569  jmp     short loc_180024575
0x18002456b  mov     esi, ebx
0x18002456d  jmp     short loc_180024575
0x18002456f  mov     [r14], rdi
0x180024572  mov     rdi, r15
0x180024575  test    rdi, rdi
0x180024578  jz      short loc_180024582
0x18002457a  mov     rcx, rdi; void *
0x18002457d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024582  mov     rbx, [rsp+38h+arg_0]
0x180024587  mov     eax, esi
0x180024589  mov     rsi, [rsp+38h+arg_10]
0x18002458e  mov     rbp, [rsp+38h+arg_8]
0x180024593  add     rsp, 20h
0x180024597  pop     r15
0x180024599  pop     r14
0x18002459b  pop     rdi
0x18002459c  retn
```
