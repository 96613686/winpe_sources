# PathCchCombineEx

- ea: `0x180027384`
- end: `0x1800275ff`
- name: `PathCchCombineEx`
- size: `635`
- prototype: `HRESULT __stdcall(PWSTR pszPathOut, size_t cchPathOut, PCWSTR pszPathIn, PCWSTR pszMore, ULONG dwFlags)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180007ce0`
- `0x180017524`
- `0x18001bc9c`

## callees

- `0x180003950`
- `0x180026018`
- `0x1800272c8`
- `0x180027384`
- `0x1800278cc`
- `0x180029280`

## import_xrefs

- `msvcrt!iswalpha` at `0x18002749a`
- `msvcrt!iswalpha` at `0x18002749a`
- `KERNEL32!LocalAlloc` at `0x18002744d`
- `KERNEL32!LocalAlloc` at `0x18002744d`
- `KERNEL32!LocalFree` at `0x1800275c6`
- `KERNEL32!LocalFree` at `0x1800275c6`

## pseudocode

```c
HRESULT __stdcall PathCchCombineEx(
        PWSTR pszPathOut,
        size_t cchPathOut,
        PCWSTR pszPathIn,
        PCWSTR pszMore,
        ULONG dwFlags)
{
  unsigned __int16 *v8; // rdi
  __int64 v9; // rdx
  unsigned __int64 v10; // r15
  HRESULT v11; // ebx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // rsi
  unsigned __int16 *v15; // r8
  PCWSTR v16; // r15
  unsigned __int64 v17; // rdx
  unsigned __int16 *v18; // rcx
  WCHAR *v19; // r11
  size_t pcchRemaining; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszEnd; // [rsp+28h] [rbp-D8h] BYREF
  _WORD v23[264]; // [rsp+30h] [rbp-D0h] BYREF

  if ( !pszPathOut )
    return -2147024809;
  v8 = 0;
  v9 = 0x8000;
  if ( pszPathIn )
  {
    v12 = -1;
    do
      ++v12;
    while ( pszPathIn[v12] );
    if ( v12 >= 0x8000 )
      goto LABEL_8;
    v10 = v12 + 1;
    v13 = 0;
    if ( !v12 )
      v10 = 0;
    if ( !pszMore )
    {
LABEL_17:
      v14 = v13 + v10;
      if ( v13 + v10 <= 0x104 )
      {
        v23[0] = 0;
        v8 = v23;
        v14 = 260;
      }
      else
      {
        v8 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v14);
        if ( !v8 )
        {
          v11 = -2147024882;
          goto LABEL_41;
        }
      }
      if ( v10 )
      {
        if ( !v13 )
        {
          v15 = (unsigned __int16 *)pszPathIn;
LABEL_39:
          v18 = v8;
          v17 = v14;
          goto LABEL_40;
        }
        if ( *pszMore == 92 )
        {
          v16 = pszMore + 1;
        }
        else if ( !iswalpha(*pszMore) || (v16 = pszMore + 1, pszMore[1] != 58) )
        {
          v11 = StringCchCopyW(v8, v14, (unsigned __int16 *)pszPathIn);
          if ( v11 < 0 )
            goto LABEL_41;
          pcchRemaining = (size_t)v19;
          ppszEnd = v19;
          v11 = PathCchAddBackslashEx(v8, v14, (PWSTR *)&pcchRemaining, (size_t *)&ppszEnd);
          if ( v11 < 0 )
            goto LABEL_41;
          v17 = (unsigned __int64)ppszEnd;
          v15 = (unsigned __int16 *)pszMore;
          v18 = (unsigned __int16 *)pcchRemaining;
          goto LABEL_40;
        }
        if ( *pszMore == 92 && *v16 != 92 )
        {
          v11 = StringCchCopyW(v8, v14, (unsigned __int16 *)pszPathIn);
          if ( v11 < 0 )
            goto LABEL_41;
          v11 = PathCchStripToRoot(v8, v14);
          if ( v11 < 0 )
            goto LABEL_41;
          ppszEnd = 0;
          pcchRemaining = 0;
          v11 = PathCchAddBackslashEx(v8, v14, &ppszEnd, &pcchRemaining);
          if ( v11 < 0 )
            goto LABEL_41;
          v17 = pcchRemaining;
          v15 = (unsigned __int16 *)v16;
          v18 = ppszEnd;
LABEL_40:
          v11 = StringCchCopyW(v18, v17, v15);
          if ( v11 < 0 )
            goto LABEL_41;
LABEL_42:
          v11 = PathCchCanonicalizeEx(pszPathOut, v9, v8, (enum PATHCCH_OPTIONS)pszMore);
          goto LABEL_43;
        }
      }
      else if ( !v13 )
      {
        goto LABEL_42;
      }
      v15 = (unsigned __int16 *)pszMore;
      goto LABEL_39;
    }
LABEL_12:
    v13 = -1;
    do
      ++v13;
    while ( pszMore[v13] );
    if ( v13 < 0x8000 )
    {
      if ( v13 )
        ++v13;
      goto LABEL_17;
    }
LABEL_8:
    v11 = -2147024690;
    goto LABEL_41;
  }
  v10 = 0;
  if ( pszMore )
    goto LABEL_12;
  v11 = -2147024809;
LABEL_41:
  StringCchCopyW(pszPathOut, 0x104u, (unsigned __int16 *)&Default);
LABEL_43:
  if ( v8 != v23 )
    LocalFree(v8);
  return v11;
}

```

## disassembly

```asm
0x180027384  mov     [rsp-8+arg_8], rbx
0x180027389  push    rbp
0x18002738a  push    rsi
0x18002738b  push    rdi
0x18002738c  push    r12
0x18002738e  push    r13
0x180027390  push    r14
0x180027392  push    r15
0x180027394  lea     rbp, [rsp-150h]
0x18002739c  sub     rsp, 250h
0x1800273a3  mov     rax, cs:__security_cookie
0x1800273aa  xor     rax, rsp
0x1800273ad  mov     [rbp+180h+var_40], rax
0x1800273b4  xor     r11d, r11d
0x1800273b7  mov     r14, r9
0x1800273ba  mov     r12, r8
0x1800273bd  mov     r13, rcx
0x1800273c0  test    rcx, rcx
0x1800273c3  jz      loc_1800275D0
0x1800273c9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800273cd  mov     edi, r11d
0x1800273d0  mov     r8d, 104h
0x1800273d6  mov     edx, 8000h; unsigned __int64
0x1800273db  test    r12, r12
0x1800273de  jnz     short loc_1800273F2
0x1800273e0  mov     r15d, r11d
0x1800273e3  test    r9, r9
0x1800273e6  jnz     short loc_180027421
0x1800273e8  mov     ebx, 80070057h
0x1800273ed  jmp     loc_180027596
0x1800273f2  mov     rax, rcx
0x1800273f5  inc     rax
0x1800273f8  cmp     [r12+rax*2], r11w
0x1800273fd  jnz     short loc_1800273F5
0x1800273ff  cmp     rax, rdx
0x180027402  jb      short loc_18002740E
0x180027404  mov     ebx, 800700CEh
0x180027409  jmp     loc_180027596
0x18002740e  test    rax, rax
0x180027411  lea     r15, [rax+1]
0x180027415  mov     rbx, r11
0x180027418  cmovz   r15, rax
0x18002741c  test    r14, r14
0x18002741f  jz      short loc_18002743B
0x180027421  mov     rbx, rcx
0x180027424  inc     rbx
0x180027427  cmp     [r9+rbx*2], r11w
0x18002742c  jnz     short loc_180027424
0x18002742e  cmp     rbx, rdx
0x180027431  jnb     short loc_180027404
0x180027433  test    rbx, rbx
0x180027436  jz      short loc_18002743B
0x180027438  inc     rbx
0x18002743b  lea     rsi, [rbx+r15]
0x18002743f  cmp     rsi, r8
0x180027442  jbe     short loc_180027465
0x180027444  lea     rdx, [rsi+rsi]; uBytes
0x180027448  mov     ecx, 40h ; '@'; uFlags
0x18002744d  call    cs:__imp_LocalAlloc
0x180027453  mov     rdi, rax
0x180027456  test    rax, rax
0x180027459  jnz     short loc_180027473
0x18002745b  mov     ebx, 8007000Eh
0x180027460  jmp     loc_180027596
0x180027465  mov     [rsp+280h+var_250], r11w
0x18002746b  lea     rdi, [rsp+280h+var_250]
0x180027470  mov     rsi, r8
0x180027473  test    r15, r15
0x180027476  jz      loc_18002757D
0x18002747c  test    rbx, rbx
0x18002747f  jnz     short loc_180027489
0x180027481  mov     r8, r12
0x180027484  jmp     loc_180027585
0x180027489  cmp     word ptr [r14], 5Ch ; '\'
0x18002748e  jnz     short loc_180027496
0x180027490  lea     r15, [r14+2]
0x180027494  jmp     short loc_1800274B6
0x180027496  movzx   ecx, word ptr [r14]; C
0x18002749a  call    cs:__imp_iswalpha
0x1800274a0  xor     r11d, r11d
0x1800274a3  test    eax, eax
0x1800274a5  jz      loc_180027535
0x1800274ab  lea     r15, [r14+2]
0x1800274af  cmp     word ptr [r15], 3Ah ; ':'
0x1800274b4  jnz     short loc_180027535
0x1800274b6  cmp     word ptr [r14], 5Ch ; '\'
0x1800274bb  jnz     loc_180027582
0x1800274c1  cmp     word ptr [r15], 5Ch ; '\'
0x1800274c6  jz      loc_180027582
0x1800274cc  mov     r8, r12; unsigned __int16 *
0x1800274cf  mov     rdx, rsi; unsigned __int64
0x1800274d2  mov     rcx, rdi; unsigned __int16 *
0x1800274d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800274da  mov     ebx, eax
0x1800274dc  test    eax, eax
0x1800274de  js      loc_180027596
0x1800274e4  mov     rdx, rsi; cchPath
0x1800274e7  mov     rcx, rdi; pszPath
0x1800274ea  call    PathCchStripToRoot
0x1800274ef  mov     ebx, eax
0x1800274f1  test    eax, eax
0x1800274f3  js      loc_180027596
0x1800274f9  lea     r9, [rsp+280h+pcchRemaining]; pcchRemaining
0x1800274fe  mov     [rsp+280h+ppszEnd], 0
0x180027507  lea     r8, [rsp+280h+ppszEnd]; ppszEnd
0x18002750c  mov     [rsp+280h+pcchRemaining], 0
0x180027515  mov     rdx, rsi; cchPath
0x180027518  mov     rcx, rdi; pszPath
0x18002751b  call    PathCchAddBackslashEx
0x180027520  mov     ebx, eax
0x180027522  test    eax, eax
0x180027524  js      short loc_180027596
0x180027526  mov     rdx, [rsp+280h+pcchRemaining]
0x18002752b  mov     r8, r15
0x18002752e  mov     rcx, [rsp+280h+ppszEnd]
0x180027533  jmp     short loc_18002758B
0x180027535  mov     r8, r12; unsigned __int16 *
0x180027538  mov     rdx, rsi; unsigned __int64
0x18002753b  mov     rcx, rdi; unsigned __int16 *
0x18002753e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027543  mov     ebx, eax
0x180027545  test    eax, eax
0x180027547  js      short loc_180027596
0x180027549  lea     r9, [rsp+280h+ppszEnd]; pcchRemaining
0x18002754e  mov     [rsp+280h+pcchRemaining], r11
0x180027553  lea     r8, [rsp+280h+pcchRemaining]; ppszEnd
0x180027558  mov     [rsp+280h+ppszEnd], r11
0x18002755d  mov     rdx, rsi; cchPath
0x180027560  mov     rcx, rdi; pszPath
0x180027563  call    PathCchAddBackslashEx
0x180027568  mov     ebx, eax
0x18002756a  test    eax, eax
0x18002756c  js      short loc_180027596
0x18002756e  mov     rdx, [rsp+280h+ppszEnd]
0x180027573  mov     r8, r14
0x180027576  mov     rcx, [rsp+280h+pcchRemaining]
0x18002757b  jmp     short loc_18002758B
0x18002757d  test    rbx, rbx
0x180027580  jz      short loc_1800275AC
0x180027582  mov     r8, r14; unsigned __int16 *
0x180027585  mov     rcx, rdi; unsigned __int16 *
0x180027588  mov     rdx, rsi; unsigned __int64
0x18002758b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027590  mov     ebx, eax
0x180027592  test    eax, eax
0x180027594  jns     short loc_1800275AC
0x180027596  lea     r8, Default; unsigned __int16 *
0x18002759d  mov     edx, 104h; unsigned __int64
0x1800275a2  mov     rcx, r13; unsigned __int16 *
0x1800275a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800275aa  jmp     short loc_1800275B9
0x1800275ac  mov     r8, rdi; unsigned __int16 *
0x1800275af  mov     rcx, r13; unsigned __int16 *
0x1800275b2  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x1800275b7  mov     ebx, eax
0x1800275b9  lea     rax, [rsp+280h+var_250]
0x1800275be  cmp     rdi, rax
0x1800275c1  jz      short loc_1800275CC
0x1800275c3  mov     rcx, rdi; hMem
0x1800275c6  call    cs:__imp_LocalFree
0x1800275cc  mov     eax, ebx
0x1800275ce  jmp     short loc_1800275D5
0x1800275d0  mov     eax, 80070057h
0x1800275d5  mov     rcx, [rbp+180h+var_40]
0x1800275dc  xor     rcx, rsp; StackCookie
0x1800275df  call    __security_check_cookie
0x1800275e4  mov     rbx, [rsp+280h+arg_8]
0x1800275ec  add     rsp, 250h
0x1800275f3  pop     r15
0x1800275f5  pop     r14
0x1800275f7  pop     r13
0x1800275f9  pop     r12
0x1800275fb  pop     rdi
0x1800275fc  pop     rsi
0x1800275fd  pop     rbp
0x1800275fe  retn
```
