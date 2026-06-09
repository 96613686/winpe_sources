# CRegKey::SetValueMultiSz(ushort const *,ushort const * *,ulong)

- ea: `0x18000f150`
- end: `0x18000f2fb`
- name: `?SetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEBGK@Z`
- size: `427`
- prototype: `unsigned int(CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 **, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18000fff0`
- `0x1800246f0`

## callees

- `0x18000179c`
- `0x18000ce1c`
- `0x18000f150`
- `0x18000f398`
- `0x18002e468`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000f2c5`
- `ADVAPI32!RegSetValueExW` at `0x18000f2c5`

## pseudocode

```c
__int64 __fastcall CRegKey::SetValueMultiSz(
        HKEY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3,
        __int64 a4)
{
  unsigned int v4; // r14d
  unsigned int v5; // ebp
  const unsigned __int16 **v7; // r15
  unsigned __int64 v8; // rdi
  const unsigned __int16 **v9; // r10
  __int64 v10; // rax
  int v11; // esi
  unsigned int v12; // ebx
  unsigned int v13; // esi
  unsigned __int64 v14; // rax
  BYTE *lpData; // rdi
  unsigned __int16 *v16; // r11
  int v17; // eax
  __int64 v18; // r11
  __int64 v19; // rax

  v4 = 0;
  v5 = a4;
  v7 = a3;
  v8 = 0;
  if ( !(_DWORD)a4 )
    goto LABEL_7;
  v9 = a3;
  a4 = (unsigned int)a4;
  do
  {
    v10 = -1;
    do
      ++v10;
    while ( (*v9)[v10] );
    ++v9;
    v8 += v10 + 1;
    --a4;
  }
  while ( a4 );
  v11 = -1;
  if ( v8 <= 0xFFFFFFFF )
LABEL_7:
    v11 = v8;
  v12 = v8 > 0xFFFFFFFF ? 0x80070216 : 0;
  if ( (int)ElValidateHr_1(v12, -1, a3, 1493) >= 0 )
  {
    v13 = 2 - (v5 != 0) + v11;
    v14 = 2LL * v13;
    if ( !is_mul_ok(v13, 2u) )
      v14 = -1;
    lpData = (BYTE *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
    if ( lpData )
    {
      v16 = (unsigned __int16 *)lpData;
      if ( v5 )
      {
        while ( 1 )
        {
          v17 = StringCchCopyW(v16, v13 - ((unsigned __int64)((char *)v16 - (char *)lpData) >> 1), *v7);
          v12 = v17;
          if ( v17 < 0 )
            break;
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)(v18 + 2 * v19) );
          ++v4;
          v16 = (unsigned __int16 *)(v18 + 2 * v19 + 2);
          ++v7;
          if ( v4 >= v5 )
          {
            *v16 = 0;
            goto LABEL_25;
          }
        }
        if ( (v17 & 0x1FFF0000) == 0x70000 )
          v12 = (unsigned __int16)v17;
      }
      else
      {
        *(_DWORD *)lpData = 0;
LABEL_25:
        v12 = RegSetValueExW(*this, a2, 0, 7u, lpData, 2 * v13);
      }
      operator delete(lpData);
    }
    else
    {
      return 8;
    }
  }
  else if ( v8 > 0xFFFFFFFF && (v8 > 0xFFFFFFFF ? 0x70000 : 0) == 0x70000 )
  {
    return (unsigned __int16)v12;
  }
  return v12;
}

```

## disassembly

```asm
0x18000f150  mov     rax, rsp
0x18000f153  mov     [rax+10h], rbx
0x18000f157  mov     [rax+18h], rbp
0x18000f15b  mov     [rax+20h], rsi
0x18000f15f  mov     [rax+8], rcx
0x18000f163  push    rdi
0x18000f164  push    r12
0x18000f166  push    r13
0x18000f168  push    r14
0x18000f16a  push    r15
0x18000f16c  sub     rsp, 30h
0x18000f170  xor     r14d, r14d
0x18000f173  mov     ebp, r9d
0x18000f176  mov     r13, rdx
0x18000f179  mov     r15, r8
0x18000f17c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000f180  mov     edi, r14d
0x18000f183  mov     r12d, 0FFFFFFFFh
0x18000f189  test    r9d, r9d
0x18000f18c  jz      short loc_18000F1BF
0x18000f18e  mov     r10, r8
0x18000f191  mov     r9d, ebp
0x18000f194  mov     rcx, [r10]
0x18000f197  mov     rax, rdx
0x18000f19a  inc     rax
0x18000f19d  cmp     [rcx+rax*2], r14w
0x18000f1a2  jnz     short loc_18000F19A
0x18000f1a4  inc     rax
0x18000f1a7  add     r10, 8
0x18000f1ab  add     rdi, rax
0x18000f1ae  mov     rax, rdi
0x18000f1b1  sub     r9, 1
0x18000f1b5  jnz     short loc_18000F194
0x18000f1b7  mov     esi, r12d
0x18000f1ba  cmp     rax, r12
0x18000f1bd  ja      short loc_18000F1C1
0x18000f1bf  mov     esi, edi
0x18000f1c1  cmp     r12, rdi
0x18000f1c4  mov     r9d, 5D5h
0x18000f1ca  sbb     ebx, ebx
0x18000f1cc  and     ebx, 80070216h
0x18000f1d2  mov     ecx, ebx
0x18000f1d4  call    ElValidateHr_1
0x18000f1d9  test    eax, eax
0x18000f1db  jns     short loc_18000F200
0x18000f1dd  cmp     rdi, r12
0x18000f1e0  jbe     loc_18000F2DB
0x18000f1e6  mov     eax, ebx
0x18000f1e8  and     eax, 1FFF0000h
0x18000f1ed  cmp     eax, 70000h
0x18000f1f2  jnz     loc_18000F2DB
0x18000f1f8  movzx   ebx, bx
0x18000f1fb  jmp     loc_18000F2DB
0x18000f200  mov     eax, ebp
0x18000f202  neg     eax
0x18000f204  mov     eax, 2
0x18000f209  sbb     ecx, ecx
0x18000f20b  add     ecx, eax
0x18000f20d  add     esi, ecx
0x18000f20f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f216  mov     r12d, esi
0x18000f219  mul     r12
0x18000f21c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f223  cmovo   rax, rcx
0x18000f227  mov     rcx, rax; unsigned __int64
0x18000f22a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f22f  mov     rdi, rax
0x18000f232  test    rax, rax
0x18000f235  jnz     short loc_18000F23F
0x18000f237  lea     ebx, [rax+8]
0x18000f23a  jmp     loc_18000F2DB
0x18000f23f  xor     eax, eax
0x18000f241  mov     r11, rdi
0x18000f244  test    ebp, ebp
0x18000f246  jz      short loc_18000F2A3
0x18000f248  mov     r8, [r15]; unsigned __int16 *
0x18000f24b  mov     rax, r11
0x18000f24e  sub     rax, rdi
0x18000f251  mov     rdx, r12
0x18000f254  shr     rax, 1
0x18000f257  mov     rcx, r11; unsigned __int16 *
0x18000f25a  sub     rdx, rax; unsigned __int64
0x18000f25d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f262  xor     ecx, ecx
0x18000f264  mov     ebx, eax
0x18000f266  test    eax, eax
0x18000f268  js      short loc_18000F292
0x18000f26a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f26e  inc     rax
0x18000f271  cmp     [r11+rax*2], cx
0x18000f276  jnz     short loc_18000F26E
0x18000f278  lea     r11, [r11+rax*2]
0x18000f27c  inc     r14d
0x18000f27f  add     r11, 2
0x18000f283  add     r15, 8
0x18000f287  cmp     r14d, ebp
0x18000f28a  jb      short loc_18000F248
0x18000f28c  mov     [r11], cx
0x18000f290  jmp     short loc_18000F2A5
0x18000f292  and     eax, 1FFF0000h
0x18000f297  cmp     eax, 70000h
0x18000f29c  jnz     short loc_18000F2D3
0x18000f29e  movzx   ebx, bx
0x18000f2a1  jmp     short loc_18000F2D3
0x18000f2a3  mov     [rdi], eax
0x18000f2a5  mov     rcx, [rsp+58h+arg_0]
0x18000f2aa  lea     eax, [rsi+rsi]
0x18000f2ad  mov     [rsp+58h+cbData], eax; cbData
0x18000f2b1  mov     r9d, 7; dwType
0x18000f2b7  xor     r8d, r8d; Reserved
0x18000f2ba  mov     [rsp+58h+lpData], rdi; lpData
0x18000f2bf  mov     rdx, r13; lpValueName
0x18000f2c2  mov     rcx, [rcx]; hKey
0x18000f2c5  call    cs:__imp_RegSetValueExW
0x18000f2cc  nop     dword ptr [rax+rax+00h]
0x18000f2d1  mov     ebx, eax
0x18000f2d3  mov     rcx, rdi; lpMem
0x18000f2d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f2db  mov     rbp, [rsp+58h+arg_10]
0x18000f2e0  mov     eax, ebx
0x18000f2e2  mov     rbx, [rsp+58h+arg_8]
0x18000f2e7  mov     rsi, [rsp+58h+arg_18]
0x18000f2ec  add     rsp, 30h
0x18000f2f0  pop     r15
0x18000f2f2  pop     r14
0x18000f2f4  pop     r13
0x18000f2f6  pop     r12
0x18000f2f8  pop     rdi
0x18000f2f9  retn
```
