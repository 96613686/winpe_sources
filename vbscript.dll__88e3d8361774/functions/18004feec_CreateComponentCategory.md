# CreateComponentCategory

- ea: `0x18004feec`
- end: `0x18004fffa`
- name: `CreateComponentCategory`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004494c`

## callees

- `0x18004feec`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18004ff95`
- `msvcrt!wcsncpy_s` at `0x18004ff95`
- `OLE32!CoCreateInstance` at `0x18004ff40`
- `OLE32!CoCreateInstance` at `0x18004ff40`

## pseudocode

```c
HRESULT __fastcall CreateComponentCategory(__int128 *a1, const wchar_t *a2)
{
  __int128 v2; // xmm6
  HRESULT result; // eax
  rsize_t v5; // rbx
  LPVOID v6; // rcx
  int v7; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-158h] BYREF
  __int128 v9; // [rsp+40h] [rbp-148h] BYREF
  int v10; // [rsp+50h] [rbp-138h]
  wchar_t Destination[134]; // [rsp+54h] [rbp-134h] BYREF

  v2 = *a1;
  ppv = 0;
  result = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv);
  if ( result >= 0 )
  {
    memset_0(Destination, 0, 0x100u);
    v5 = -1;
    v10 = 1033;
    v9 = v2;
    do
      ++v5;
    while ( a2[v5] );
    if ( v5 > 0x7F )
      v5 = 127;
    wcsncpy_s(Destination, 0x80u, a2, v5);
    v6 = ppv;
    Destination[v5] = 0;
    v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v6 + 24LL))(v6, 1, &v9);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18004feec  mov     rax, rsp
0x18004feef  mov     [rax+18h], rbx
0x18004fef3  mov     [rax+20h], rsi
0x18004fef7  push    rdi
0x18004fef8  sub     rsp, 180h
0x18004feff  movaps  xmmword ptr [rax-18h], xmm6
0x18004ff03  mov     rax, cs:__security_cookie
0x18004ff0a  xor     rax, rsp
0x18004ff0d  mov     [rsp+188h+var_28], rax
0x18004ff15  movaps  xmm6, xmmword ptr [rcx]
0x18004ff18  lea     rax, [rsp+188h+var_158]
0x18004ff1d  xor     esi, esi
0x18004ff1f  mov     [rsp+188h+ppv], rax; ppv
0x18004ff24  mov     rdi, rdx
0x18004ff27  mov     [rsp+188h+var_158], rsi
0x18004ff2c  lea     r9, IID_ICatRegister; riid
0x18004ff33  xor     edx, edx; pUnkOuter
0x18004ff35  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18004ff3c  lea     r8d, [rsi+1]; dwClsContext
0x18004ff40  call    cs:__imp_CoCreateInstance
0x18004ff46  test    eax, eax
0x18004ff48  js      loc_18004FFD0
0x18004ff4e  xor     edx, edx; Val
0x18004ff50  lea     rcx, [rsp+188h+Destination]; void *
0x18004ff55  mov     r8d, 100h; Size
0x18004ff5b  call    memset_0
0x18004ff60  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004ff64  mov     [rsp+188h+var_138], 409h
0x18004ff6c  movdqu  [rsp+188h+var_148], xmm6
0x18004ff72  inc     rbx
0x18004ff75  cmp     [rdi+rbx*2], si
0x18004ff79  jnz     short loc_18004FF72
0x18004ff7b  mov     eax, 7Fh
0x18004ff80  lea     rcx, [rsp+188h+Destination]; Destination
0x18004ff85  cmp     rbx, rax
0x18004ff88  mov     r8, rdi; Source
0x18004ff8b  cmova   rbx, rax
0x18004ff8f  mov     r9, rbx; MaxCount
0x18004ff92  lea     edx, [rax+1]; SizeInWords
0x18004ff95  call    cs:__imp_wcsncpy_s
0x18004ff9b  mov     rcx, [rsp+188h+var_158]
0x18004ffa0  lea     r8, [rsp+188h+var_148]
0x18004ffa5  mov     [rsp+rbx*2+188h+Destination], si
0x18004ffaa  mov     edx, 1
0x18004ffaf  mov     rax, [rcx]
0x18004ffb2  mov     rax, [rax+18h]
0x18004ffb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffbb  mov     rcx, [rsp+188h+var_158]
0x18004ffc0  mov     ebx, eax
0x18004ffc2  mov     rdx, [rcx]
0x18004ffc5  mov     rax, [rdx+10h]
0x18004ffc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffce  mov     eax, ebx
0x18004ffd0  mov     rcx, [rsp+188h+var_28]
0x18004ffd8  xor     rcx, rsp; StackCookie
0x18004ffdb  call    __security_check_cookie
0x18004ffe0  lea     r11, [rsp+188h+var_8]
0x18004ffe8  mov     rbx, [r11+20h]
0x18004ffec  mov     rsi, [r11+28h]
0x18004fff0  movaps  xmm6, xmmword ptr [r11-10h]
0x18004fff5  mov     rsp, r11
0x18004fff8  pop     rdi
0x18004fff9  retn
```
