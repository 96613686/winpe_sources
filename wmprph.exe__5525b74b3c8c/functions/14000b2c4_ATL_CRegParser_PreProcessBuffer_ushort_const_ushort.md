# ATL::CRegParser::PreProcessBuffer(ushort const *,ushort * *)

- ea: `0x14000b2c4`
- end: `0x14000b543`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEBGPEAPEAG@Z`
- size: `639`
- prototype: `int(ATL::CRegParser *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000b808`

## callees

- `0x140001390`
- `0x14000b2c4`

## import_xrefs

- `KERNEL32!lstrcpynW` at `0x14000b3c5`
- `KERNEL32!lstrcpynW` at `0x14000b3c5`
- `KERNEL32!lstrcmpiW` at `0x14000b3ec`
- `KERNEL32!lstrcmpiW` at `0x14000b3ec`
- `USER32!CharNextW` at `0x14000b35c`
- `USER32!CharNextW` at `0x14000b38c`
- `USER32!CharNextW` at `0x14000b464`
- `USER32!CharNextW` at `0x14000b4a6`
- `USER32!CharNextW` at `0x14000b35c`
- `USER32!CharNextW` at `0x14000b38c`
- `USER32!CharNextW` at `0x14000b464`
- `USER32!CharNextW` at `0x14000b4a6`
- `ole32!CoTaskMemAlloc` at `0x14000b32b`
- `ole32!CoTaskMemAlloc` at `0x14000b32b`
- `ole32!CoTaskMemFree` at `0x14000b4e9`
- `ole32!CoTaskMemFree` at `0x14000b50c`
- `ole32!CoTaskMemFree` at `0x14000b4e9`
- `ole32!CoTaskMemFree` at `0x14000b50c`
- `ole32!CoTaskMemRealloc` at `0x14000b433`
- `ole32!CoTaskMemRealloc` at `0x14000b488`
- `ole32!CoTaskMemRealloc` at `0x14000b4d6`
- `ole32!CoTaskMemRealloc` at `0x14000b433`
- `ole32!CoTaskMemRealloc` at `0x14000b488`
- `ole32!CoTaskMemRealloc` at `0x14000b4d6`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, WCHAR *a2, unsigned __int16 **a3)
{
  unsigned __int16 **v3; // r14
  LPWSTR v4; // rbx
  __int64 v6; // rsi
  int v7; // esi
  void *v8; // rdi
  int v9; // ebp
  WCHAR v10; // ax
  WCHAR v11; // ax
  const WCHAR *v12; // r14
  __int64 v13; // r8
  LPCWSTR v14; // r12
  int v15; // ebx
  unsigned int v16; // ebx
  __int16 *v17; // rbx
  LPVOID v18; // rax
  __int16 v19; // ax
  __int64 v20; // rcx
  const WCHAR *i; // rax
  LPVOID v22; // rax
  __int64 v23; // rcx
  LPVOID v24; // rax
  WCHAR String1[32]; // [rsp+30h] [rbp-88h] BYREF

  v3 = a3;
  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6 + 2;
  v8 = CoTaskMemAlloc(2LL * v7);
  if ( !v8 )
  {
LABEL_41:
    v16 = -2147024882;
    goto LABEL_42;
  }
  *this = v4;
  v9 = 0;
  v10 = *v4;
  if ( !*v4 )
  {
LABEL_39:
    if ( v9 + 1 > v7 )
    {
      v24 = CoTaskMemRealloc(v8, 4LL * v7);
      if ( !v24 )
        goto LABEL_41;
      v8 = v24;
    }
    *((_WORD *)v8 + v9) = *v4;
    *v3 = (unsigned __int16 *)v8;
    CoTaskMemFree(0);
    return 0;
  }
  while ( 1 )
  {
    if ( v10 == 37 )
    {
      v4 = CharNextW(v4);
      *this = v4;
      v11 = *v4;
      if ( *v4 != 37 )
        break;
    }
    if ( v9 + 1 > v7 )
    {
      v7 *= 2;
      v22 = CoTaskMemRealloc(v8, 2LL * v7);
      if ( !v22 )
        goto LABEL_41;
      v8 = v22;
    }
    v23 = v9++;
    *((_WORD *)v8 + v23) = *v4;
LABEL_37:
    v4 = CharNextW(*this);
    *this = v4;
    v10 = *v4;
    if ( !*v4 )
    {
      v3 = a3;
      goto LABEL_39;
    }
  }
  if ( !v4 )
    goto LABEL_21;
  v12 = 0;
  while ( v11 )
  {
    if ( v11 == 37 )
    {
      v12 = v4;
      break;
    }
    v4 = CharNextW(v4);
    v11 = *v4;
  }
  if ( !v12 )
  {
LABEL_21:
    v16 = -2147352567;
    goto LABEL_42;
  }
  v13 = v12 - *this;
  if ( (int)v13 <= 31 )
  {
    lstrcpynW(String1, *this, v13 + 1);
    v14 = this[1];
    v15 = 0;
    if ( *((int *)v14 + 2) <= 0 )
      goto LABEL_21;
    while ( lstrcmpiW(**(LPCWSTR **)(*(_QWORD *)v14 + 8LL * v15), String1) )
    {
      if ( ++v15 >= *((_DWORD *)v14 + 2) )
        goto LABEL_21;
    }
    v17 = *(__int16 **)(*(_QWORD *)(*(_QWORD *)v14 + 8LL * v15) + 8LL);
    if ( !v17 )
      goto LABEL_21;
    while ( *v17 )
    {
      if ( v9 + 1 > v7 )
      {
        v7 *= 2;
        v18 = CoTaskMemRealloc(v8, 2LL * v7);
        if ( !v18 )
          goto LABEL_41;
        v8 = v18;
      }
      v19 = *v17++;
      v20 = v9++;
      *((_WORD *)v8 + v20) = v19;
    }
    for ( i = *this; i != v12; *this = i )
      i = CharNextW(i);
    goto LABEL_37;
  }
  v16 = -2147467259;
LABEL_42:
  CoTaskMemFree(v8);
  return v16;
}

```

## disassembly

```asm
0x14000b2c4  mov     [rsp+arg_8], rbx
0x14000b2c9  push    rbp
0x14000b2ca  push    rsi
0x14000b2cb  push    rdi
0x14000b2cc  push    r12
0x14000b2ce  push    r13
0x14000b2d0  push    r14
0x14000b2d2  push    r15
0x14000b2d4  sub     rsp, 80h
0x14000b2db  mov     rax, cs:__security_cookie
0x14000b2e2  xor     rax, rsp
0x14000b2e5  mov     [rsp+0B8h+var_48], rax
0x14000b2ea  xor     r13d, r13d
0x14000b2ed  mov     [rsp+0B8h+var_98], r8
0x14000b2f2  mov     r14, r8
0x14000b2f5  mov     rbx, rdx
0x14000b2f8  mov     r15, rcx
0x14000b2fb  test    rdx, rdx
0x14000b2fe  jz      loc_14000B516
0x14000b304  test    r8, r8
0x14000b307  jz      loc_14000B516
0x14000b30d  mov     [r8], r13
0x14000b310  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000b314  inc     rsi
0x14000b317  cmp     [rdx+rsi*2], r13w
0x14000b31c  jnz     short loc_14000B314
0x14000b31e  lea     esi, ds:2[rsi*2]
0x14000b325  movsxd  rcx, esi
0x14000b328  add     rcx, rcx; cb
0x14000b32b  call    cs:__imp_CoTaskMemAlloc
0x14000b331  mov     rdi, rax
0x14000b334  test    rax, rax
0x14000b337  jz      loc_14000B4E1
0x14000b33d  mov     [r15], rbx
0x14000b340  mov     ebp, r13d
0x14000b343  movzx   eax, word ptr [rbx]
0x14000b346  test    ax, ax
0x14000b349  jz      loc_14000B4C3
0x14000b34f  cmp     ax, 25h ; '%'
0x14000b353  jnz     loc_14000B474
0x14000b359  mov     rcx, rbx; lpsz
0x14000b35c  call    cs:__imp_CharNextW
0x14000b362  mov     rbx, rax
0x14000b365  mov     [r15], rax
0x14000b368  movzx   eax, word ptr [rax]
0x14000b36b  cmp     ax, 25h ; '%'
0x14000b36f  jz      loc_14000B474
0x14000b375  test    rbx, rbx
0x14000b378  jz      loc_14000B3FF
0x14000b37e  mov     r14, r13
0x14000b381  jmp     short loc_14000B398
0x14000b383  cmp     ax, 25h ; '%'
0x14000b387  jz      short loc_14000B39F
0x14000b389  mov     rcx, rbx; lpsz
0x14000b38c  call    cs:__imp_CharNextW
0x14000b392  mov     rbx, rax
0x14000b395  movzx   eax, word ptr [rax]
0x14000b398  test    ax, ax
0x14000b39b  jnz     short loc_14000B383
0x14000b39d  jmp     short loc_14000B3A2
0x14000b39f  mov     r14, rbx
0x14000b3a2  test    r14, r14
0x14000b3a5  jz      short loc_14000B3FF
0x14000b3a7  mov     r8, r14
0x14000b3aa  sub     r8, [r15]
0x14000b3ad  sar     r8, 1
0x14000b3b0  cmp     r8d, 1Fh
0x14000b3b4  jg      loc_14000B4F3
0x14000b3ba  mov     rdx, [r15]; lpString2
0x14000b3bd  lea     rcx, [rsp+0B8h+String1]; lpString1
0x14000b3c2  inc     r8d; iMaxLength
0x14000b3c5  call    cs:__imp_lstrcpynW
0x14000b3cb  mov     r12, [r15+8]
0x14000b3cf  mov     ebx, r13d
0x14000b3d2  cmp     [r12+8], r13d
0x14000b3d7  jle     short loc_14000B3FF
0x14000b3d9  mov     rax, [r12]
0x14000b3dd  lea     rdx, [rsp+0B8h+String1]; lpString2
0x14000b3e2  movsxd  r13, ebx
0x14000b3e5  mov     rcx, [rax+r13*8]
0x14000b3e9  mov     rcx, [rcx]; lpString1
0x14000b3ec  call    cs:__imp_lstrcmpiW
0x14000b3f2  test    eax, eax
0x14000b3f4  jz      short loc_14000B409
0x14000b3f6  inc     ebx
0x14000b3f8  cmp     ebx, [r12+8]
0x14000b3fd  jl      short loc_14000B3D9
0x14000b3ff  mov     ebx, 80020009h
0x14000b404  jmp     loc_14000B4E6
0x14000b409  mov     rax, [r12]
0x14000b40d  mov     rcx, [rax+r13*8]
0x14000b411  xor     r13d, r13d
0x14000b414  mov     rbx, [rcx+8]
0x14000b418  test    rbx, rbx
0x14000b41b  jz      short loc_14000B3FF
0x14000b41d  jmp     short loc_14000B456
0x14000b41f  lea     r12d, [rbp+1]
0x14000b423  cmp     r12d, esi
0x14000b426  jle     short loc_14000B445
0x14000b428  add     esi, esi
0x14000b42a  mov     rcx, rdi; pv
0x14000b42d  movsxd  rdx, esi
0x14000b430  add     rdx, rdx; cb
0x14000b433  call    cs:__imp_CoTaskMemRealloc
0x14000b439  test    rax, rax
0x14000b43c  jz      loc_14000B4E1
0x14000b442  mov     rdi, rax
0x14000b445  movzx   eax, word ptr [rbx]
0x14000b448  add     rbx, 2
0x14000b44c  movsxd  rcx, ebp
0x14000b44f  mov     ebp, r12d
0x14000b452  mov     [rdi+rcx*2], ax
0x14000b456  cmp     [rbx], r13w
0x14000b45a  jnz     short loc_14000B41F
0x14000b45c  mov     rax, [r15]
0x14000b45f  jmp     short loc_14000B46D
0x14000b461  mov     rcx, rax; lpsz
0x14000b464  call    cs:__imp_CharNextW
0x14000b46a  mov     [r15], rax
0x14000b46d  cmp     rax, r14
0x14000b470  jnz     short loc_14000B461
0x14000b472  jmp     short loc_14000B4A3
0x14000b474  lea     r14d, [rbp+1]
0x14000b478  cmp     r14d, esi
0x14000b47b  jle     short loc_14000B496
0x14000b47d  add     esi, esi
0x14000b47f  mov     rcx, rdi; pv
0x14000b482  movsxd  rdx, esi
0x14000b485  add     rdx, rdx; cb
0x14000b488  call    cs:__imp_CoTaskMemRealloc
0x14000b48e  test    rax, rax
0x14000b491  jz      short loc_14000B4E1
0x14000b493  mov     rdi, rax
0x14000b496  movzx   eax, word ptr [rbx]
0x14000b499  movsxd  rcx, ebp
0x14000b49c  mov     ebp, r14d
0x14000b49f  mov     [rdi+rcx*2], ax
0x14000b4a3  mov     rcx, [r15]; lpsz
0x14000b4a6  call    cs:__imp_CharNextW
0x14000b4ac  mov     rbx, rax
0x14000b4af  mov     [r15], rax
0x14000b4b2  movzx   eax, word ptr [rax]
0x14000b4b5  test    ax, ax
0x14000b4b8  jnz     loc_14000B34F
0x14000b4be  mov     r14, [rsp+0B8h+var_98]
0x14000b4c3  lea     eax, [rbp+1]
0x14000b4c6  cmp     eax, esi
0x14000b4c8  jle     short loc_14000B4FD
0x14000b4ca  lea     eax, [rsi+rsi]
0x14000b4cd  mov     rcx, rdi; pv
0x14000b4d0  movsxd  rdx, eax
0x14000b4d3  add     rdx, rdx; cb
0x14000b4d6  call    cs:__imp_CoTaskMemRealloc
0x14000b4dc  test    rax, rax
0x14000b4df  jnz     short loc_14000B4FA
0x14000b4e1  mov     ebx, 8007000Eh
0x14000b4e6  mov     rcx, rdi; pv
0x14000b4e9  call    cs:__imp_CoTaskMemFree
0x14000b4ef  mov     eax, ebx
0x14000b4f1  jmp     short loc_14000B51B
0x14000b4f3  mov     ebx, 80004005h
0x14000b4f8  jmp     short loc_14000B4E6
0x14000b4fa  mov     rdi, rax
0x14000b4fd  movzx   eax, word ptr [rbx]
0x14000b500  movsxd  rcx, ebp
0x14000b503  mov     [rdi+rcx*2], ax
0x14000b507  xor     ecx, ecx; pv
0x14000b509  mov     [r14], rdi
0x14000b50c  call    cs:__imp_CoTaskMemFree
0x14000b512  xor     eax, eax
0x14000b514  jmp     short loc_14000B51B
0x14000b516  mov     eax, 80004003h
0x14000b51b  mov     rcx, [rsp+0B8h+var_48]
0x14000b520  xor     rcx, rsp; StackCookie
0x14000b523  call    __security_check_cookie
0x14000b528  mov     rbx, [rsp+0B8h+arg_8]
0x14000b530  add     rsp, 80h
0x14000b537  pop     r15
0x14000b539  pop     r14
0x14000b53b  pop     r13
0x14000b53d  pop     r12
0x14000b53f  pop     rdi
0x14000b540  pop     rsi
0x14000b541  pop     rbp
0x14000b542  retn
```
