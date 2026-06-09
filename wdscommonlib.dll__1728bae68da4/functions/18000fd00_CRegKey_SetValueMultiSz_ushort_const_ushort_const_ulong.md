# CRegKey::SetValueMultiSz(ushort const *,ushort const * *,ulong)

- ea: `0x18000fd00`
- end: `0x18000feb2`
- name: `?SetValueMultiSz@CRegKey@@QEAAKPEBGPEAPEBGK@Z`
- size: `434`
- prototype: `unsigned int(CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 **, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180010bb0`
- `0x1800257c0`

## callees

- `0x18000214c`
- `0x18000d95c`
- `0x18000fd00`
- `0x18000ff48`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fe86`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fe86`
- `ADVAPI32!RegSetValueExW` at `0x18000fe75`
- `ADVAPI32!RegSetValueExW` at `0x18000fe75`

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
0x18000fd00  mov     rax, rsp
0x18000fd03  mov     [rax+10h], rbx
0x18000fd07  mov     [rax+18h], rbp
0x18000fd0b  mov     [rax+20h], rsi
0x18000fd0f  mov     [rax+8], rcx
0x18000fd13  push    rdi
0x18000fd14  push    r12
0x18000fd16  push    r13
0x18000fd18  push    r14
0x18000fd1a  push    r15
0x18000fd1c  sub     rsp, 30h
0x18000fd20  xor     r14d, r14d
0x18000fd23  mov     ebp, r9d
0x18000fd26  mov     r13, rdx
0x18000fd29  mov     r15, r8
0x18000fd2c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000fd30  mov     edi, r14d
0x18000fd33  mov     r12d, 0FFFFFFFFh
0x18000fd39  test    r9d, r9d
0x18000fd3c  jz      short loc_18000FD6F
0x18000fd3e  mov     r10, r8
0x18000fd41  mov     r9d, ebp
0x18000fd44  mov     rcx, [r10]
0x18000fd47  mov     rax, rdx
0x18000fd4a  inc     rax
0x18000fd4d  cmp     [rcx+rax*2], r14w
0x18000fd52  jnz     short loc_18000FD4A
0x18000fd54  inc     rax
0x18000fd57  add     r10, 8
0x18000fd5b  add     rdi, rax
0x18000fd5e  mov     rax, rdi
0x18000fd61  sub     r9, 1
0x18000fd65  jnz     short loc_18000FD44
0x18000fd67  mov     esi, r12d
0x18000fd6a  cmp     rax, r12
0x18000fd6d  ja      short loc_18000FD71
0x18000fd6f  mov     esi, edi
0x18000fd71  cmp     r12, rdi
0x18000fd74  mov     r9d, 5D5h
0x18000fd7a  sbb     ebx, ebx
0x18000fd7c  and     ebx, 80070216h
0x18000fd82  mov     ecx, ebx
0x18000fd84  call    ElValidateHr_1
0x18000fd89  test    eax, eax
0x18000fd8b  jns     short loc_18000FDB0
0x18000fd8d  cmp     rdi, r12
0x18000fd90  jbe     loc_18000FE92
0x18000fd96  mov     eax, ebx
0x18000fd98  and     eax, 1FFF0000h
0x18000fd9d  cmp     eax, 70000h
0x18000fda2  jnz     loc_18000FE92
0x18000fda8  movzx   ebx, bx
0x18000fdab  jmp     loc_18000FE92
0x18000fdb0  mov     eax, ebp
0x18000fdb2  neg     eax
0x18000fdb4  mov     eax, 2
0x18000fdb9  sbb     ecx, ecx
0x18000fdbb  add     ecx, eax
0x18000fdbd  add     esi, ecx
0x18000fdbf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fdc6  mov     r12d, esi
0x18000fdc9  mul     r12
0x18000fdcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fdd3  cmovo   rax, rcx
0x18000fdd7  mov     rcx, rax; unsigned __int64
0x18000fdda  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000fddf  mov     rdi, rax
0x18000fde2  test    rax, rax
0x18000fde5  jnz     short loc_18000FDEF
0x18000fde7  lea     ebx, [rax+8]
0x18000fdea  jmp     loc_18000FE92
0x18000fdef  xor     eax, eax
0x18000fdf1  mov     r11, rdi
0x18000fdf4  test    ebp, ebp
0x18000fdf6  jz      short loc_18000FE53
0x18000fdf8  mov     r8, [r15]; unsigned __int16 *
0x18000fdfb  mov     rax, r11
0x18000fdfe  sub     rax, rdi
0x18000fe01  mov     rdx, r12
0x18000fe04  shr     rax, 1
0x18000fe07  mov     rcx, r11; unsigned __int16 *
0x18000fe0a  sub     rdx, rax; unsigned __int64
0x18000fe0d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fe12  xor     ecx, ecx
0x18000fe14  mov     ebx, eax
0x18000fe16  test    eax, eax
0x18000fe18  js      short loc_18000FE42
0x18000fe1a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fe1e  inc     rax
0x18000fe21  cmp     [r11+rax*2], cx
0x18000fe26  jnz     short loc_18000FE1E
0x18000fe28  lea     r11, [r11+rax*2]
0x18000fe2c  inc     r14d
0x18000fe2f  add     r11, 2
0x18000fe33  add     r15, 8
0x18000fe37  cmp     r14d, ebp
0x18000fe3a  jb      short loc_18000FDF8
0x18000fe3c  mov     [r11], cx
0x18000fe40  jmp     short loc_18000FE55
0x18000fe42  and     eax, 1FFF0000h
0x18000fe47  cmp     eax, 70000h
0x18000fe4c  jnz     short loc_18000FE83
0x18000fe4e  movzx   ebx, bx
0x18000fe51  jmp     short loc_18000FE83
0x18000fe53  mov     [rdi], eax
0x18000fe55  mov     rcx, [rsp+58h+arg_0]
0x18000fe5a  lea     eax, [rsi+rsi]
0x18000fe5d  mov     [rsp+58h+cbData], eax; cbData
0x18000fe61  mov     r9d, 7; dwType
0x18000fe67  xor     r8d, r8d; Reserved
0x18000fe6a  mov     [rsp+58h+lpData], rdi; lpData
0x18000fe6f  mov     rdx, r13; lpValueName
0x18000fe72  mov     rcx, [rcx]; hKey
0x18000fe75  call    cs:__imp_RegSetValueExW
0x18000fe7c  nop     dword ptr [rax+rax+00h]
0x18000fe81  mov     ebx, eax
0x18000fe83  mov     rcx, rdi
0x18000fe86  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fe8d  nop     dword ptr [rax+rax+00h]
0x18000fe92  mov     rbp, [rsp+58h+arg_10]
0x18000fe97  mov     eax, ebx
0x18000fe99  mov     rbx, [rsp+58h+arg_8]
0x18000fe9e  mov     rsi, [rsp+58h+arg_18]
0x18000fea3  add     rsp, 30h
0x18000fea7  pop     r15
0x18000fea9  pop     r14
0x18000feab  pop     r13
0x18000fead  pop     r12
0x18000feaf  pop     rdi
0x18000feb0  retn
```
