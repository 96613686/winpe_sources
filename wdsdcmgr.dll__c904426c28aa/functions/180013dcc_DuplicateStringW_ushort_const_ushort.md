# DuplicateStringW(ushort const *,ushort * *)

- ea: `0x180013dcc`
- end: `0x180013e9e`
- name: `?DuplicateStringW@@YAKPEBGPEAPEAG@Z`
- size: `210`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `16`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003acc`
- `0x1800051e8`
- `0x180005430`
- `0x1800063b4`
- `0x180008b68`
- `0x180008db4`
- `0x180009680`
- `0x180009894`
- `0x180009b3c`
- `0x18000a644`
- `0x18000b47c`
- `0x18000dfa0`
- `0x18001170c`
- `0x180012780`
- `0x180012ac8`
- `0x180014010`

## callees

- `0x180008574`
- `0x180013dcc`
- `0x180014ee0`
- `0x1800150b8`
- `0x1800157a4`

## string_xrefs

- `0x180013e41`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`

## pseudocode

```c
__int64 __fastcall DuplicateStringW(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v4; // rdi
  unsigned int v5; // esi
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rax
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  int v10; // edi
  const char *v11; // rdx

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
    if ( (int)ElValidateHr(v10, v11, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp", 0x900u) >= 0 )
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
0x180013dcc  mov     [rsp+arg_0], rbx
0x180013dd1  mov     [rsp+arg_8], rbp
0x180013dd6  mov     [rsp+arg_10], rsi
0x180013ddb  push    rdi
0x180013ddc  push    r14
0x180013dde  push    r15
0x180013de0  sub     rsp, 20h
0x180013de4  xor     r15d, r15d
0x180013de7  mov     rbp, rcx
0x180013dea  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013dee  mov     r14, rdx
0x180013df1  mov     rdi, rcx
0x180013df4  mov     esi, r15d
0x180013df7  inc     rdi
0x180013dfa  cmp     [rbp+rdi*2+0], r15w
0x180013e00  jnz     short loc_180013DF7
0x180013e02  inc     rdi
0x180013e05  mov     eax, 2
0x180013e0a  mul     rdi
0x180013e0d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013e14  cmovo   rax, rcx
0x180013e18  mov     rcx, rax; unsigned __int64
0x180013e1b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013e20  mov     rbx, rax
0x180013e23  test    rax, rax
0x180013e26  jnz     short loc_180013E2D
0x180013e28  lea     esi, [rax+8]
0x180013e2b  jmp     short loc_180013E83
0x180013e2d  mov     r8, rbp; unsigned __int16 *
0x180013e30  mov     rdx, rdi; unsigned __int64
0x180013e33  mov     rcx, rbx; unsigned __int16 *
0x180013e36  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013e3b  mov     r9d, 900h; unsigned int
0x180013e41  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180013e48  mov     ecx, eax; int
0x180013e4a  mov     edi, eax
0x180013e4c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180013e51  test    eax, eax
0x180013e53  jns     short loc_180013E70
0x180013e55  test    edi, edi
0x180013e57  jns     short loc_180013E6C
0x180013e59  mov     eax, edi
0x180013e5b  and     eax, 1FFF0000h
0x180013e60  cmp     eax, 70000h
0x180013e65  jnz     short loc_180013E6C
0x180013e67  movzx   esi, di
0x180013e6a  jmp     short loc_180013E76
0x180013e6c  mov     esi, edi
0x180013e6e  jmp     short loc_180013E76
0x180013e70  mov     [r14], rbx
0x180013e73  mov     rbx, r15
0x180013e76  test    rbx, rbx
0x180013e79  jz      short loc_180013E83
0x180013e7b  mov     rcx, rbx; Block
0x180013e7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013e83  mov     rbx, [rsp+38h+arg_0]
0x180013e88  mov     eax, esi
0x180013e8a  mov     rsi, [rsp+38h+arg_10]
0x180013e8f  mov     rbp, [rsp+38h+arg_8]
0x180013e94  add     rsp, 20h
0x180013e98  pop     r15
0x180013e9a  pop     r14
0x180013e9c  pop     rdi
0x180013e9d  retn
```
