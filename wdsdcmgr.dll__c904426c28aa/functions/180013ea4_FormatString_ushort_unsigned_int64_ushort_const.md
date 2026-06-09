# FormatString(ushort * *,unsigned __int64,ushort const *,...)

- ea: `0x180013ea4`
- end: `0x18001400a`
- name: `?FormatString@@YAKPEAPEAG_KPEBGZZ`
- size: `358`
- prototype: `__int64(unsigned __int16 **, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012780`

## callees

- `0x180013854`
- `0x180013ea4`
- `0x180014ee0`
- `0x1800150b8`
- `0x1800157a4`

## string_xrefs

- `0x180013f2e`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`
- `0x180013f4e`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`

## pseudocode

```c
__int64 FormatString(unsigned __int16 **a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v3; // esi
  unsigned __int64 v4; // rbp
  unsigned __int64 v7; // rax
  wchar_t *v8; // rdi
  unsigned __int64 v9; // r15
  int v10; // eax
  const char *v11; // rdx
  int v12; // ebx
  unsigned __int64 v13; // r14
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  v3 = 0;
  v4 = a2;
  if ( !a2 )
    v4 = 256;
  v7 = 2 * v4;
  if ( !is_mul_ok(v4, 2u) )
    v7 = -1;
  v8 = (wchar_t *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v8 )
  {
LABEL_22:
    v3 = 8;
    goto LABEL_23;
  }
  while ( 1 )
  {
    v9 = v4;
    v10 = StringCchVPrintfW(v8, v4, a3, va);
    v12 = v10;
    if ( !v10 )
    {
      *a1 = v8;
      return v3;
    }
    if ( v10 != -2147024774
      && (int)ElValidateHr(v10, v11, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp", 0x94Au) < 0 )
    {
      if ( v12 < 0 )
        goto LABEL_19;
LABEL_17:
      v3 = v12;
      goto LABEL_23;
    }
    v13 = v4 + 256;
    v14 = -1;
    v15 = v4;
    if ( v4 + 256 >= v4 )
      v14 = v4 + 256;
    v4 = v14;
    v12 = v13 < v15 ? 0x80070216 : 0;
    if ( (int)ElValidateHr(v12, v11, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp", 0x94Eu) < 0 )
      break;
    operator delete(v8);
    v16 = 2 * v4;
    if ( !is_mul_ok(v4, 2u) )
      v16 = -1;
    v8 = (wchar_t *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v8 )
      goto LABEL_22;
  }
  if ( v13 >= v9 )
    goto LABEL_17;
LABEL_19:
  if ( (v12 & 0x1FFF0000) != 0x70000 )
    goto LABEL_17;
  v3 = (unsigned __int16)v12;
LABEL_23:
  if ( v8 )
    operator delete(v8);
  return v3;
}

```

## disassembly

```asm
0x180013ea4  mov     rax, rsp
0x180013ea7  mov     [rax+18h], r8
0x180013eab  mov     [rax+20h], r9
0x180013eaf  push    rbx
0x180013eb0  push    rbp
0x180013eb1  push    rsi
0x180013eb2  push    rdi
0x180013eb3  push    r12
0x180013eb5  push    r13
0x180013eb7  push    r14
0x180013eb9  push    r15
0x180013ebb  sub     rsp, 28h
0x180013ebf  lea     rbx, [rax+20h]
0x180013ec3  xor     esi, esi
0x180013ec5  test    rdx, rdx
0x180013ec8  mov     rbp, rdx
0x180013ecb  mov     eax, 100h
0x180013ed0  mov     r12, rcx
0x180013ed3  cmovz   rbp, rax
0x180013ed7  mov     r13, r8
0x180013eda  lea     rcx, [rsi-1]
0x180013ede  lea     eax, [rsi+2]
0x180013ee1  mul     rbp
0x180013ee4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013eeb  cmovo   rax, rcx
0x180013eef  mov     rcx, rax; unsigned __int64
0x180013ef2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013ef7  mov     rdi, rax
0x180013efa  test    rax, rax
0x180013efd  jz      loc_180013FE5
0x180013f03  mov     r9, rbx; char *
0x180013f06  mov     r8, r13; unsigned __int16 *
0x180013f09  mov     rdx, rbp; unsigned __int64
0x180013f0c  mov     rcx, rdi; Buffer
0x180013f0f  mov     r15, rbp
0x180013f12  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180013f17  mov     ebx, eax
0x180013f19  test    eax, eax
0x180013f1b  jz      loc_180013FDF
0x180013f21  cmp     eax, 8007007Ah
0x180013f26  jz      short loc_180013F40
0x180013f28  mov     r9d, 94Ah; unsigned int
0x180013f2e  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180013f35  mov     ecx, eax; int
0x180013f37  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180013f3c  test    eax, eax
0x180013f3e  js      short loc_180013FBF
0x180013f40  lea     r14, [rbp+100h]
0x180013f47  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013f4b  mov     rcx, rbp
0x180013f4e  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180013f55  cmp     r14, rbp
0x180013f58  mov     r9d, 94Eh; unsigned int
0x180013f5e  cmovnb  rax, r14
0x180013f62  cmp     r14, rcx
0x180013f65  mov     rbp, rax
0x180013f68  sbb     ebx, ebx
0x180013f6a  and     ebx, 80070216h
0x180013f70  mov     ecx, ebx; int
0x180013f72  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180013f77  test    eax, eax
0x180013f79  js      short loc_180013FC7
0x180013f7b  test    rdi, rdi
0x180013f7e  jz      short loc_180013F88
0x180013f80  mov     rcx, rdi; Block
0x180013f83  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013f88  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180013f8f  mov     eax, 2
0x180013f94  mul     rbp
0x180013f97  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013f9e  cmovo   rax, rcx
0x180013fa2  mov     rcx, rax; unsigned __int64
0x180013fa5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013faa  mov     rdi, rax
0x180013fad  test    rax, rax
0x180013fb0  jz      short loc_180013FE5
0x180013fb2  lea     rbx, [rsp+68h+arg_18]
0x180013fba  jmp     loc_180013F03
0x180013fbf  test    ebx, ebx
0x180013fc1  js      short loc_180013FCC
0x180013fc3  mov     esi, ebx
0x180013fc5  jmp     short loc_180013FEA
0x180013fc7  cmp     r14, r15
0x180013fca  jnb     short loc_180013FC3
0x180013fcc  mov     eax, ebx
0x180013fce  and     eax, 1FFF0000h
0x180013fd3  cmp     eax, 70000h
0x180013fd8  jnz     short loc_180013FC3
0x180013fda  movzx   esi, bx
0x180013fdd  jmp     short loc_180013FEA
0x180013fdf  mov     [r12], rdi
0x180013fe3  jmp     short loc_180013FF7
0x180013fe5  mov     esi, 8
0x180013fea  test    rdi, rdi
0x180013fed  jz      short loc_180013FF7
0x180013fef  mov     rcx, rdi; Block
0x180013ff2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013ff7  mov     eax, esi
0x180013ff9  add     rsp, 28h
0x180013ffd  pop     r15
0x180013fff  pop     r14
0x180014001  pop     r13
0x180014003  pop     r12
0x180014005  pop     rdi
0x180014006  pop     rsi
0x180014007  pop     rbp
0x180014008  pop     rbx
0x180014009  retn
```
