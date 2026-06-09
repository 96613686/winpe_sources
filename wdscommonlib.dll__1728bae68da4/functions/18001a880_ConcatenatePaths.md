# ConcatenatePaths

- ea: `0x18001a880`
- end: `0x18001ab06`
- name: `ConcatenatePaths`
- size: `646`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001a1c8`
- `0x18001a5dc`
- `0x18001b220`
- `0x18001b280`
- `0x18001b610`
- `0x18001b780`
- `0x18001bef0`
- `0x18001c370`
- `0x18001cda0`
- `0x18001d730`
- `0x180029b00`

## callees

- `0x18000214c`
- `0x180019d28`
- `0x18001a880`
- `0x18001afd0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001aacf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aacf`

## pseudocode

```c
__int64 __fastcall ConcatenatePaths(_WORD *a1, __int64 a2, unsigned __int16 **a3)
{
  unsigned int v3; // ebx
  _WORD *v4; // r15
  _WORD *v5; // rax
  unsigned __int64 v6; // rbp
  __int64 v7; // r14
  int v8; // r12d
  __int64 v9; // rbp
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rsi
  bool v13; // zf
  __int64 v14; // r14
  _WORD *v15; // rax
  __int64 v16; // rsi
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // rsi
  __int64 v19; // rdx
  __int64 v20; // r8
  bool v21; // cf
  unsigned __int64 v22; // r14
  unsigned __int64 v23; // rbp
  unsigned __int64 v24; // rax
  unsigned __int16 *v25; // rsi
  const WCHAR *v26; // rax

  v3 = 0;
  v4 = (_WORD *)a2;
  v5 = a1;
  v6 = 0;
  v7 = 0;
  if ( a3 )
  {
    v8 = 0;
    if ( a1 )
    {
      v9 = 0x7FFFFFFF;
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --v9;
      }
      while ( v9 );
      v10 = v9 == 0 ? 0x80070057 : 0;
      v11 = (0x7FFFFFFF - v9) & ((unsigned __int128)-(__int128)(unsigned __int64)v9 >> 64);
      v12 = v11 & -(__int64)(v9 != 0);
      if ( (int)ElValidateHr_5(v10, v11, -v9, 0x9Eu) < 0 )
      {
        v13 = v9 == 0;
        goto LABEL_9;
      }
      v6 = v12;
      if ( v12 && a1[v12 - 1] == 92 )
        v8 = 1;
    }
    if ( v4 )
    {
      v14 = 0x7FFFFFFF;
      v15 = v4;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v14;
      }
      while ( v14 );
      v10 = v14 == 0 ? 0x80070057 : 0;
      v16 = (0x7FFFFFFF - v14) & -(__int64)(v14 != 0);
      if ( (int)ElValidateHr_5(v10, -v14, (__int64)a3, 0xAFu) < 0 )
      {
        v13 = v14 == 0;
LABEL_9:
        if ( !v13 )
          return v10;
        goto LABEL_10;
      }
      v7 = (0x7FFFFFFF - v14) & -(__int64)(v14 != 0);
      if ( v16 && *v4 == 92 )
      {
        if ( v8 )
        {
          ++v4;
          v7 = v16 - 1;
        }
        else
        {
          v8 = 1;
        }
      }
    }
    v17 = v6 + v7;
    v18 = -1;
    if ( v17 >= v6 )
      v18 = v17;
    v10 = v17 < v6 ? 0x80070216 : 0;
    if ( (int)ElValidateHr_5(v10, a2, (__int64)a3, 0xCEu) >= 0 )
    {
      v22 = -1;
      v23 = v18 + 2LL - (v8 != 0);
      if ( v23 >= v18 )
        v22 = v18 + 2LL - (v8 != 0);
      v10 = v23 < v18 ? 0x80070216 : 0;
      if ( (int)ElValidateHr_5(v10, v19, v20, 0xD1u) >= 0 )
      {
        v24 = 2 * v22;
        if ( !is_mul_ok(v22, 2u) )
          v24 = -1;
        v25 = (unsigned __int16 *)operator new[](v24, (const struct std::nothrow_t *)&std::nothrow);
        if ( !v25 )
          return 8;
        v26 = &psz;
        if ( !v8 )
          v26 = L"\\";
        v10 = StringCchPrintfExW(v25, v22, 0, 0, 0x100u, L"%s%s%s", a1, v26, v4);
        if ( (v10 & 0x80000000) == 0 )
        {
          *a3 = v25;
          return v3;
        }
        operator delete(v25);
LABEL_10:
        if ( (v10 & 0x1FFF0000) == 0x70000 )
          return (unsigned __int16)v10;
        return v10;
      }
      v21 = v23 < v18;
    }
    else
    {
      v21 = v17 < v6;
    }
    if ( !v21 )
      return v10;
    goto LABEL_10;
  }
  return 87;
}

```

## disassembly

```asm
0x18001a880  mov     [rsp+arg_8], rbx
0x18001a885  mov     [rsp+arg_10], r8
0x18001a88a  mov     [rsp+arg_0], rcx
0x18001a88f  push    rbp
0x18001a890  push    rsi
0x18001a891  push    rdi
0x18001a892  push    r12
0x18001a894  push    r13
0x18001a896  push    r14
0x18001a898  push    r15
0x18001a89a  sub     rsp, 50h
0x18001a89e  xor     ebx, ebx
0x18001a8a0  mov     r15, rdx
0x18001a8a3  mov     rax, rcx
0x18001a8a6  mov     ebp, ebx
0x18001a8a8  mov     r14d, ebx
0x18001a8ab  test    r8, r8
0x18001a8ae  jnz     short loc_18001A8B9
0x18001a8b0  lea     ebx, [r14+57h]
0x18001a8b4  jmp     loc_18001AAEB
0x18001a8b9  mov     r12d, ebx
0x18001a8bc  mov     r13d, 7FFFFFFFh
0x18001a8c2  test    rax, rax
0x18001a8c5  jz      loc_18001A95C
0x18001a8cb  mov     ebp, r13d
0x18001a8ce  cmp     [rax], bx
0x18001a8d1  jz      short loc_18001A8DD
0x18001a8d3  add     rax, 2
0x18001a8d7  sub     rbp, 1
0x18001a8db  jnz     short loc_18001A8CE
0x18001a8dd  mov     rax, rbp
0x18001a8e0  mov     rcx, r13
0x18001a8e3  neg     rax
0x18001a8e6  mov     r8, rbp
0x18001a8e9  mov     rax, rbp
0x18001a8ec  mov     r9d, 9Eh
0x18001a8f2  sbb     edi, edi
0x18001a8f4  sub     rcx, rbp
0x18001a8f7  not     edi
0x18001a8f9  and     edi, 80070057h
0x18001a8ff  neg     rax
0x18001a902  sbb     rdx, rdx
0x18001a905  and     rdx, rcx
0x18001a908  mov     ecx, edi
0x18001a90a  neg     r8
0x18001a90d  sbb     rsi, rsi
0x18001a910  and     rsi, rdx
0x18001a913  call    ElValidateHr_5
0x18001a918  test    eax, eax
0x18001a91a  jns     short loc_18001A93E
0x18001a91c  test    rbp, rbp
0x18001a91f  jnz     short loc_18001A937
0x18001a921  mov     eax, edi
0x18001a923  and     eax, 1FFF0000h
0x18001a928  cmp     eax, 70000h
0x18001a92d  jnz     short loc_18001A937
0x18001a92f  movzx   ebx, di
0x18001a932  jmp     loc_18001AAEB
0x18001a937  mov     ebx, edi
0x18001a939  jmp     loc_18001AAEB
0x18001a93e  mov     rbp, rsi
0x18001a941  test    rsi, rsi
0x18001a944  jz      short loc_18001A95C
0x18001a946  mov     rax, [rsp+88h+arg_0]
0x18001a94e  cmp     word ptr [rax+rsi*2-2], 5Ch ; '\'
0x18001a954  jnz     short loc_18001A95C
0x18001a956  mov     r12d, 1
0x18001a95c  test    r15, r15
0x18001a95f  jz      short loc_18001A9DE
0x18001a961  mov     r14, r13
0x18001a964  mov     rax, r15
0x18001a967  cmp     [rax], bx
0x18001a96a  jz      short loc_18001A976
0x18001a96c  add     rax, 2
0x18001a970  sub     r14, 1
0x18001a974  jnz     short loc_18001A967
0x18001a976  mov     rax, r14
0x18001a979  mov     rdx, r14
0x18001a97c  neg     rax
0x18001a97f  mov     r9d, 0AFh
0x18001a985  mov     rax, r14
0x18001a988  sbb     edi, edi
0x18001a98a  sub     r13, r14
0x18001a98d  not     edi
0x18001a98f  and     edi, 80070057h
0x18001a995  neg     rax
0x18001a998  sbb     rcx, rcx
0x18001a99b  and     rcx, r13
0x18001a99e  neg     rdx
0x18001a9a1  sbb     rsi, rsi
0x18001a9a4  and     rsi, rcx
0x18001a9a7  mov     ecx, edi
0x18001a9a9  call    ElValidateHr_5
0x18001a9ae  test    eax, eax
0x18001a9b0  jns     short loc_18001A9BA
0x18001a9b2  test    r14, r14
0x18001a9b5  jmp     loc_18001A91F
0x18001a9ba  mov     r14, rsi
0x18001a9bd  test    rsi, rsi
0x18001a9c0  jz      short loc_18001A9DE
0x18001a9c2  cmp     word ptr [r15], 5Ch ; '\'
0x18001a9c7  jnz     short loc_18001A9DE
0x18001a9c9  test    r12d, r12d
0x18001a9cc  jz      short loc_18001A9D8
0x18001a9ce  add     r15, 2
0x18001a9d2  lea     r14, [rsi-1]
0x18001a9d6  jmp     short loc_18001A9DE
0x18001a9d8  mov     r12d, 1
0x18001a9de  add     r14, rbp
0x18001a9e1  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001a9e5  cmp     r14, rbp
0x18001a9e8  mov     rsi, r13
0x18001a9eb  mov     r9d, 0CEh
0x18001a9f1  cmovnb  rsi, r14
0x18001a9f5  sbb     edi, edi
0x18001a9f7  and     edi, 80070216h
0x18001a9fd  mov     ecx, edi
0x18001a9ff  call    ElValidateHr_5
0x18001aa04  test    eax, eax
0x18001aa06  jns     short loc_18001AA16
0x18001aa08  cmp     r14, rbp
0x18001aa0b  jnb     loc_18001A937
0x18001aa11  jmp     loc_18001A921
0x18001aa16  mov     eax, r12d
0x18001aa19  mov     r14, r13
0x18001aa1c  neg     eax
0x18001aa1e  mov     r9d, 0D1h
0x18001aa24  sbb     rcx, rcx
0x18001aa27  lea     rbp, [rcx+2]
0x18001aa2b  add     rbp, rsi
0x18001aa2e  cmp     rbp, rsi
0x18001aa31  cmovnb  r14, rbp
0x18001aa35  sbb     edi, edi
0x18001aa37  and     edi, 80070216h
0x18001aa3d  mov     ecx, edi
0x18001aa3f  call    ElValidateHr_5
0x18001aa44  test    eax, eax
0x18001aa46  jns     short loc_18001AA4D
0x18001aa48  cmp     rbp, rsi
0x18001aa4b  jmp     short loc_18001AA0B
0x18001aa4d  mov     eax, 2
0x18001aa52  mul     r14
0x18001aa55  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001aa5c  cmovo   rax, r13
0x18001aa60  mov     rcx, rax; unsigned __int64
0x18001aa63  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001aa68  mov     rsi, rax
0x18001aa6b  test    rax, rax
0x18001aa6e  jnz     short loc_18001AA75
0x18001aa70  lea     ebx, [rax+8]
0x18001aa73  jmp     short loc_18001AAEB
0x18001aa75  mov     [rsp+88h+var_48], r15
0x18001aa7a  lea     rcx, SubBlock; "\\"
0x18001aa81  test    r12d, r12d
0x18001aa84  lea     rax, psz
0x18001aa8b  mov     rdx, r14; unsigned __int64
0x18001aa8e  cmovz   rax, rcx
0x18001aa92  xor     r9d, r9d; unsigned __int64 *
0x18001aa95  mov     [rsp+88h+var_50], rax
0x18001aa9a  xor     r8d, r8d; unsigned __int16 **
0x18001aa9d  mov     rax, [rsp+88h+arg_0]
0x18001aaa5  mov     rcx, rsi; unsigned __int16 *
0x18001aaa8  mov     [rsp+88h+var_58], rax
0x18001aaad  lea     rax, aSSS; "%s%s%s"
0x18001aab4  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18001aab9  mov     [rsp+88h+var_68], 100h; unsigned int
0x18001aac1  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18001aac6  mov     edi, eax
0x18001aac8  test    eax, eax
0x18001aaca  jns     short loc_18001AAE0
0x18001aacc  mov     rcx, rsi
0x18001aacf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001aad6  nop     dword ptr [rax+rax+00h]
0x18001aadb  jmp     loc_18001A921
0x18001aae0  mov     rcx, [rsp+88h+arg_10]
0x18001aae8  mov     [rcx], rsi
0x18001aaeb  mov     eax, ebx
0x18001aaed  mov     rbx, [rsp+88h+arg_8]
0x18001aaf5  add     rsp, 50h
0x18001aaf9  pop     r15
0x18001aafb  pop     r14
0x18001aafd  pop     r13
0x18001aaff  pop     r12
0x18001ab01  pop     rdi
0x18001ab02  pop     rsi
0x18001ab03  pop     rbp
0x18001ab04  retn
```
