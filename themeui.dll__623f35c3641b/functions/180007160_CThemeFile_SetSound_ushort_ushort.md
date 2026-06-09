# CThemeFile::SetSound(ushort *,ushort *)

- ea: `0x180007160`
- end: `0x1800073eb`
- name: `?SetSound@CThemeFile@@UEAAJPEAG0@Z`
- size: `651`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007160`
- `0x1800089c0`
- `0x1800358c0`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x1800072af`
- `SHLWAPI!StrStrW` at `0x1800072af`
- `SHLWAPI!PathIsRelativeW` at `0x1800072c2`
- `SHLWAPI!PathIsRelativeW` at `0x1800072c2`
- `SHLWAPI!__imp_PathUnExpandEnvStringsForUserW` at `0x1800073a5`
- `SHLWAPI!__imp_PathUnExpandEnvStringsForUserW` at `0x1800073a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800071de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800071de`

## pseudocode

```c
HRESULT __fastcall CThemeFile::SetSound(CThemeFile *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  LPVOID v6; // rbx
  HRESULT result; // eax
  int v8; // esi
  __int64 v9; // rcx
  _BYTE *v10; // rax
  __int64 v11; // rcx
  WCHAR *v12; // r9
  unsigned __int16 *v13; // rdx
  __int64 v14; // r8
  WCHAR *v15; // rax
  PWSTR v16; // rax
  int v17; // eax
  unsigned __int16 *v18; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-258h] BYREF
  WCHAR pszFirst[264]; // [rsp+40h] [rbp-248h] BYREF

  if ( !a2 )
    return -2147024809;
  if ( !*((_QWORD *)this + 4) )
    return -2147467259;
  v6 = (LPVOID)*((_QWORD *)this + 5);
  if ( v6 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 8LL))(v6);
    v10 = (char *)this + 48;
    v8 = 0;
  }
  else
  {
    ppv = 0;
    result = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
    if ( result < 0 )
      return result;
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
           ppv,
           *((_QWORD *)this + 4),
           0x400000);
    if ( v8 < 0 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return v8;
    }
    v9 = *((_QWORD *)this + 5);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v6 = ppv;
    *((_QWORD *)this + 5) = ppv;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 8LL))(v6);
    v10 = (char *)this + 48;
    *((_BYTE *)this + 48) = 0;
  }
  *v10 = 1;
  if ( a3 )
  {
    v11 = 2147483646;
    v12 = pszFirst;
    v13 = a3;
    v14 = 260;
    do
    {
      if ( !v11 )
        break;
      if ( !*v13 )
        break;
      *v12++ = *v13++;
      --v11;
      --v14;
    }
    while ( v14 );
    v15 = v12 - 1;
    if ( v14 )
      v15 = v12;
    *v15 = 0;
    if ( !v14 )
      goto LABEL_22;
    v16 = StrStrW(pszFirst, L",");
    if ( v16 )
      *v16 = 0;
    if ( !PathIsRelativeW(pszFirst) )
    {
      v17 = PathUnExpandEnvStringsForUserW(0, a3, pszFirst, 260);
      v18 = pszFirst;
      if ( !v17 )
        v18 = a3;
      a3 = v18;
    }
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, const OLECHAR *, __int64, unsigned __int16 *))(*(_QWORD *)v6 + 80LL))(
         v6,
         a2,
         L"DefaultValue",
         1,
         a3);
LABEL_22:
  if ( v8 >= 0 && (int)StringCchPrintfW(pszFirst, 0x104u, L"%s.MUI", L"DefaultValue") >= 0 )
    (*(void (__fastcall **)(LPVOID, unsigned __int16 *, WCHAR *, __int64, _QWORD))(*(_QWORD *)v6 + 80LL))(
      v6,
      a2,
      pszFirst,
      1,
      0);
  (*(void (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)v6 + 16LL))(v6, v13);
  result = v8;
  if ( v8 >= 0 )
    *((_WORD *)this + 402) = 0;
  return result;
}

```

## disassembly

```asm
0x180007160  mov     r11, rsp
0x180007163  push    rdi
0x180007164  push    r14
0x180007166  push    r15
0x180007168  sub     rsp, 270h
0x18000716f  mov     rax, cs:__security_cookie
0x180007176  xor     rax, rsp
0x180007179  mov     [rsp+288h+var_38], rax
0x180007181  mov     r15, r8
0x180007184  mov     r14, rdx
0x180007187  mov     rdi, rcx
0x18000718a  test    rdx, rdx
0x18000718d  jz      loc_18000738E
0x180007193  cmp     qword ptr [rcx+20h], 0
0x180007198  jz      loc_1800073E4
0x18000719e  mov     [r11+20h], rbx
0x1800071a2  mov     rbx, [rcx+28h]
0x1800071a6  mov     [r11-20h], rbp
0x1800071aa  mov     [r11-28h], rsi
0x1800071ae  test    rbx, rbx
0x1800071b1  jnz     loc_18000723F
0x1800071b7  lea     rax, [rsp+288h+var_258]
0x1800071bc  xor     ebp, ebp
0x1800071be  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x1800071c5  mov     [rsp+288h+var_258], rbp
0x1800071ca  xor     edx, edx; pUnkOuter
0x1800071cc  mov     [rsp+288h+ppv], rax; ppv
0x1800071d1  mov     r8d, 1; dwClsContext
0x1800071d7  lea     rcx, CLSID_PrivateProfile; rclsid
0x1800071de  call    cs:__imp_CoCreateInstance
0x1800071e4  test    eax, eax
0x1800071e6  js      loc_180007359
0x1800071ec  mov     rcx, [rsp+288h+var_258]
0x1800071f1  mov     r8d, 400000h
0x1800071f7  mov     rdx, [rdi+20h]
0x1800071fb  mov     rax, [rcx]
0x1800071fe  mov     rax, [rax+18h]
0x180007202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007207  mov     esi, eax
0x180007209  test    eax, eax
0x18000720b  js      loc_1800073BE
0x180007211  mov     rcx, [rdi+28h]
0x180007215  test    rcx, rcx
0x180007218  jnz     loc_1800073D3
0x18000721e  mov     rbx, [rsp+288h+var_258]
0x180007223  mov     [rdi+28h], rbx
0x180007227  mov     rcx, rbx
0x18000722a  mov     rax, [rbx]
0x18000722d  mov     rax, [rax+8]
0x180007231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007236  lea     rax, [rdi+30h]
0x18000723a  mov     [rax], bpl
0x18000723d  jmp     short loc_180007256
0x18000723f  mov     rax, [rbx]
0x180007242  mov     rcx, rbx
0x180007245  mov     rax, [rax+8]
0x180007249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000724e  xor     ebp, ebp
0x180007250  lea     rax, [rdi+30h]
0x180007254  mov     esi, ebp
0x180007256  mov     byte ptr [rax], 1
0x180007259  test    r15, r15
0x18000725c  jz      short loc_1800072D0
0x18000725e  mov     ecx, 7FFFFFFEh
0x180007263  lea     r9, [rsp+288h+pszFirst]
0x180007268  mov     rdx, r15
0x18000726b  mov     r8d, 104h
0x180007271  test    rcx, rcx
0x180007274  jz      short loc_180007293
0x180007276  movzx   eax, word ptr [rdx]
0x180007279  test    ax, ax
0x18000727c  jz      short loc_180007293
0x18000727e  mov     [r9], ax
0x180007282  add     rdx, 2
0x180007286  add     r9, 2
0x18000728a  dec     rcx
0x18000728d  sub     r8, 1
0x180007291  jnz     short loc_180007271
0x180007293  test    r8, r8
0x180007296  lea     rax, [r9-2]
0x18000729a  cmovnz  rax, r9
0x18000729e  mov     [rax], bp
0x1800072a1  jz      short loc_1800072F6
0x1800072a3  lea     rdx, pszSrch; ","
0x1800072aa  lea     rcx, [rsp+288h+pszFirst]; pszFirst
0x1800072af  call    cs:__imp_StrStrW
0x1800072b5  test    rax, rax
0x1800072b8  jz      short loc_1800072BD
0x1800072ba  mov     [rax], bp
0x1800072bd  lea     rcx, [rsp+288h+pszFirst]; pszPath
0x1800072c2  call    cs:__imp_PathIsRelativeW
0x1800072c8  test    eax, eax
0x1800072ca  jz      loc_180007395
0x1800072d0  mov     rax, [rbx]
0x1800072d3  lea     r8, aDefaultvalue; "DefaultValue"
0x1800072da  mov     r9d, 1
0x1800072e0  mov     [rsp+288h+ppv], r15
0x1800072e5  mov     rdx, r14
0x1800072e8  mov     rcx, rbx
0x1800072eb  mov     rax, [rax+50h]
0x1800072ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f4  mov     esi, eax
0x1800072f6  test    esi, esi
0x1800072f8  js      short loc_18000733D
0x1800072fa  lea     r9, aDefaultvalue; "DefaultValue"
0x180007301  mov     edx, 104h; unsigned __int64
0x180007306  lea     r8, aSMui; "%s.MUI"
0x18000730d  lea     rcx, [rsp+288h+pszFirst]; unsigned __int16 *
0x180007312  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007317  test    eax, eax
0x180007319  js      short loc_18000733D
0x18000731b  mov     rax, [rbx]
0x18000731e  lea     r8, [rsp+288h+pszFirst]
0x180007323  mov     r9d, 1
0x180007329  mov     [rsp+288h+ppv], rbp
0x18000732e  mov     rdx, r14
0x180007331  mov     rcx, rbx
0x180007334  mov     rax, [rax+50h]
0x180007338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000733d  mov     rax, [rbx]
0x180007340  mov     rcx, rbx
0x180007343  mov     rax, [rax+10h]
0x180007347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000734c  mov     eax, esi
0x18000734e  test    esi, esi
0x180007350  js      short loc_180007359
0x180007352  mov     [rdi+324h], bp
0x180007359  mov     rbp, [rsp+288h+var_20]
0x180007361  mov     rbx, [rsp+288h+arg_18]
0x180007369  mov     rsi, [rsp+288h+var_28]
0x180007371  mov     rcx, [rsp+288h+var_38]
0x180007379  xor     rcx, rsp; StackCookie
0x18000737c  call    __security_check_cookie
0x180007381  add     rsp, 270h
0x180007388  pop     r15
0x18000738a  pop     r14
0x18000738c  pop     rdi
0x18000738d  retn
0x18000738e  mov     eax, 80070057h
0x180007393  jmp     short loc_180007371
0x180007395  mov     r9d, 104h
0x18000739b  lea     r8, [rsp+288h+pszFirst]
0x1800073a0  mov     rdx, r15
0x1800073a3  xor     ecx, ecx
0x1800073a5  call    cs:__imp_PathUnExpandEnvStringsForUserW
0x1800073ab  test    eax, eax
0x1800073ad  lea     rcx, [rsp+288h+pszFirst]
0x1800073b2  cmovz   rcx, r15
0x1800073b6  mov     r15, rcx
0x1800073b9  jmp     loc_1800072D0
0x1800073be  mov     rcx, [rsp+288h+var_258]
0x1800073c3  mov     rax, [rcx]
0x1800073c6  mov     rax, [rax+10h]
0x1800073ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073cf  mov     eax, esi
0x1800073d1  jmp     short loc_180007359
0x1800073d3  mov     rax, [rcx]
0x1800073d6  mov     rax, [rax+10h]
0x1800073da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073df  jmp     loc_18000721E
0x1800073e4  mov     eax, 80004005h
0x1800073e9  jmp     short loc_180007371
```
