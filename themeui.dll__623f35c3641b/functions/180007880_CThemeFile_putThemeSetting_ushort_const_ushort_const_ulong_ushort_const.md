# CThemeFile::_putThemeSetting(ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x180007880`
- end: `0x180007b0c`
- name: `?_putThemeSetting@CThemeFile@@AEAAJPEBG0K0@Z`
- size: `652`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `21`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800073f4`
- `0x18000b3f0`
- `0x18001f570`
- `0x180020a80`
- `0x180020ff0`
- `0x180021020`
- `0x1800210f0`
- `0x180021f80`
- `0x180051850`
- `0x180051890`
- `0x1800518d0`
- `0x180051910`
- `0x180052b70`
- `0x180052c00`
- `0x180052cc0`
- `0x180052d10`
- `0x180053110`
- `0x180053180`
- `0x180053200`
- `0x180053400`
- `0x180053480`

## callees

- `0x180007880`
- `0x1800089c0`
- `0x1800358c0`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x180007a95`
- `SHLWAPI!StrStrW` at `0x180007a95`
- `SHLWAPI!PathIsRelativeW` at `0x180007aa9`
- `SHLWAPI!PathIsRelativeW` at `0x180007aa9`
- `SHLWAPI!__imp_PathUnExpandEnvStringsForUserW` at `0x180007ac7`
- `SHLWAPI!__imp_PathUnExpandEnvStringsForUserW` at `0x180007ac7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007904`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007904`

## pseudocode

```c
HRESULT __fastcall CThemeFile::_putThemeSetting(
        CThemeFile *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        unsigned __int16 *a5)
{
  const unsigned __int16 *v6; // r15
  LPVOID v10; // rdi
  HRESULT result; // eax
  int v12; // ebp
  __int64 v13; // rcx
  __int64 v14; // rcx
  WCHAR *v15; // r9
  const unsigned __int16 *v16; // rdx
  __int64 v17; // r8
  WCHAR *v18; // rax
  PWSTR v19; // rax
  int v20; // eax
  WCHAR *v21; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-268h] BYREF
  WCHAR pszFirst[264]; // [rsp+40h] [rbp-258h] BYREF

  v6 = a5;
  if ( !*((_QWORD *)this + 6) )
    return -2147467259;
  v10 = (LPVOID)*((_QWORD *)this + 7);
  if ( v10 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 8LL))(v10);
    v12 = 0;
    goto LABEL_8;
  }
  ppv = 0;
  result = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
  if ( result < 0 )
    return result;
  v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
          ppv,
          *((_QWORD *)this + 6),
          0x400000);
  if ( v12 >= 0 )
  {
    v13 = *((_QWORD *)this + 7);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v10 = ppv;
    *((_QWORD *)this + 7) = ppv;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 8LL))(v10);
    *((_BYTE *)this + 64) = 0;
LABEL_8:
    *((_BYTE *)this + 64) = 1;
    if ( (a4 & 1) != 0 && a5 )
    {
      v14 = 2147483646;
      v15 = pszFirst;
      v16 = a5;
      v17 = 260;
      do
      {
        if ( !v14 )
          break;
        if ( !*v16 )
          break;
        *v15++ = *v16++;
        --v14;
        --v17;
      }
      while ( v17 );
      v18 = v15 - 1;
      if ( v17 )
        v18 = v15;
      *v18 = 0;
      if ( !v17 )
        goto LABEL_10;
      v19 = StrStrW(pszFirst, L",");
      if ( v19 )
        *v19 = 0;
      if ( !PathIsRelativeW(pszFirst) )
      {
        v20 = PathUnExpandEnvStringsForUserW(0, a5, pszFirst, 260);
        v21 = pszFirst;
        if ( !v20 )
          v21 = a5;
        v6 = v21;
      }
    }
    v12 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, const unsigned __int16 *, __int64, const unsigned __int16 *))(*(_QWORD *)v10 + 80LL))(
            v10,
            a2,
            a3,
            1,
            v6);
LABEL_10:
    if ( v12 >= 0 && (int)StringCchPrintfW(pszFirst, 0x104u, L"%s.MUI", a3) >= 0 )
      (*(void (__fastcall **)(LPVOID, const unsigned __int16 *, WCHAR *, __int64, _QWORD))(*(_QWORD *)v10 + 80LL))(
        v10,
        a2,
        pszFirst,
        1,
        0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
    return v12;
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v12;
}

```

## disassembly

```asm
0x180007880  mov     r11, rsp
0x180007883  push    rbx
0x180007884  push    rsi
0x180007885  push    r12
0x180007887  push    r14
0x180007889  push    r15
0x18000788b  sub     rsp, 270h
0x180007892  mov     rax, cs:__security_cookie
0x180007899  xor     rax, rsp
0x18000789c  mov     [rsp+298h+var_48], rax
0x1800078a4  cmp     qword ptr [rcx+30h], 0
0x1800078a9  mov     esi, r9d
0x1800078ac  mov     r15, [rsp+298h+arg_20]
0x1800078b4  mov     r14, r8
0x1800078b7  mov     r12, rdx
0x1800078ba  mov     rbx, rcx
0x1800078bd  jz      loc_180007B02
0x1800078c3  mov     [r11+20h], rbp
0x1800078c7  mov     [r11-30h], rdi
0x1800078cb  mov     rdi, [rcx+38h]
0x1800078cf  mov     [r11-38h], r13
0x1800078d3  test    rdi, rdi
0x1800078d6  jnz     loc_180007A1C
0x1800078dc  lea     rax, [rsp+298h+var_268]
0x1800078e1  xor     r13d, r13d
0x1800078e4  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x1800078eb  mov     [rsp+298h+var_268], r13
0x1800078f0  xor     edx, edx; pUnkOuter
0x1800078f2  mov     [rsp+298h+ppv], rax; ppv
0x1800078f7  mov     r8d, 1; dwClsContext
0x1800078fd  lea     rcx, CLSID_PrivateProfile; rclsid
0x180007904  call    cs:__imp_CoCreateInstance
0x18000790a  test    eax, eax
0x18000790c  js      loc_1800079E4
0x180007912  mov     rcx, [rsp+298h+var_268]
0x180007917  mov     r8d, 400000h
0x18000791d  mov     rdx, [rbx+30h]
0x180007921  mov     rax, [rcx]
0x180007924  mov     rax, [rax+18h]
0x180007928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000792d  mov     ebp, eax
0x18000792f  test    eax, eax
0x180007931  js      loc_180007AE0
0x180007937  mov     rcx, [rbx+38h]
0x18000793b  test    rcx, rcx
0x18000793e  jnz     loc_180007AF1
0x180007944  mov     rdi, [rsp+298h+var_268]
0x180007949  mov     [rbx+38h], rdi
0x18000794d  mov     rcx, rdi
0x180007950  mov     rax, [rdi]
0x180007953  mov     rax, [rax+8]
0x180007957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000795c  mov     [rbx+40h], r13b
0x180007960  mov     byte ptr [rbx+40h], 1
0x180007964  test    sil, 1
0x180007968  jnz     loc_180007A36
0x18000796e  mov     rax, [rdi]
0x180007971  mov     r9d, 1
0x180007977  mov     r8, r14
0x18000797a  mov     [rsp+298h+ppv], r15
0x18000797f  mov     rdx, r12
0x180007982  mov     rcx, rdi
0x180007985  mov     rax, [rax+50h]
0x180007989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000798e  mov     ebp, eax
0x180007990  test    ebp, ebp
0x180007992  js      short loc_1800079D3
0x180007994  mov     r9, r14
0x180007997  lea     r8, aSMui; "%s.MUI"
0x18000799e  mov     edx, 104h; unsigned __int64
0x1800079a3  lea     rcx, [rsp+298h+pszFirst]; unsigned __int16 *
0x1800079a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800079ad  test    eax, eax
0x1800079af  js      short loc_1800079D3
0x1800079b1  mov     rax, [rdi]
0x1800079b4  lea     r8, [rsp+298h+pszFirst]
0x1800079b9  mov     r9d, 1
0x1800079bf  mov     [rsp+298h+ppv], r13
0x1800079c4  mov     rdx, r12
0x1800079c7  mov     rcx, rdi
0x1800079ca  mov     rax, [rax+50h]
0x1800079ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d3  mov     rax, [rdi]
0x1800079d6  mov     rcx, rdi
0x1800079d9  mov     rax, [rax+10h]
0x1800079dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e2  mov     eax, ebp
0x1800079e4  mov     rdi, [rsp+298h+var_30]
0x1800079ec  mov     rbp, [rsp+298h+arg_18]
0x1800079f4  mov     r13, [rsp+298h+var_38]
0x1800079fc  mov     rcx, [rsp+298h+var_48]
0x180007a04  xor     rcx, rsp; StackCookie
0x180007a07  call    __security_check_cookie
0x180007a0c  add     rsp, 270h
0x180007a13  pop     r15
0x180007a15  pop     r14
0x180007a17  pop     r12
0x180007a19  pop     rsi
0x180007a1a  pop     rbx
0x180007a1b  retn
0x180007a1c  mov     rax, [rdi]
0x180007a1f  mov     rcx, rdi
0x180007a22  mov     rax, [rax+8]
0x180007a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a2b  xor     r13d, r13d
0x180007a2e  mov     ebp, r13d
0x180007a31  jmp     loc_180007960
0x180007a36  test    r15, r15
0x180007a39  jz      loc_18000796E
0x180007a3f  mov     ecx, 7FFFFFFEh
0x180007a44  lea     r9, [rsp+298h+pszFirst]
0x180007a49  mov     rdx, r15
0x180007a4c  mov     r8d, 104h
0x180007a52  test    rcx, rcx
0x180007a55  jz      short loc_180007A74
0x180007a57  movzx   eax, word ptr [rdx]
0x180007a5a  test    ax, ax
0x180007a5d  jz      short loc_180007A74
0x180007a5f  mov     [r9], ax
0x180007a63  add     rdx, 2
0x180007a67  add     r9, 2
0x180007a6b  dec     rcx
0x180007a6e  sub     r8, 1
0x180007a72  jnz     short loc_180007A52
0x180007a74  test    r8, r8
0x180007a77  lea     rax, [r9-2]
0x180007a7b  cmovnz  rax, r9
0x180007a7f  mov     [rax], r13w
0x180007a83  jz      loc_180007990
0x180007a89  lea     rdx, pszSrch; ","
0x180007a90  lea     rcx, [rsp+298h+pszFirst]; pszFirst
0x180007a95  call    cs:__imp_StrStrW
0x180007a9b  test    rax, rax
0x180007a9e  jz      short loc_180007AA4
0x180007aa0  mov     [rax], r13w
0x180007aa4  lea     rcx, [rsp+298h+pszFirst]; pszPath
0x180007aa9  call    cs:__imp_PathIsRelativeW
0x180007aaf  test    eax, eax
0x180007ab1  jnz     loc_18000796E
0x180007ab7  mov     r9d, 104h
0x180007abd  lea     r8, [rsp+298h+pszFirst]
0x180007ac2  mov     rdx, r15
0x180007ac5  xor     ecx, ecx
0x180007ac7  call    cs:__imp_PathUnExpandEnvStringsForUserW
0x180007acd  test    eax, eax
0x180007acf  lea     rcx, [rsp+298h+pszFirst]
0x180007ad4  cmovz   rcx, r15
0x180007ad8  mov     r15, rcx
0x180007adb  jmp     loc_18000796E
0x180007ae0  mov     rcx, [rsp+298h+var_268]
0x180007ae5  mov     rdx, [rcx]
0x180007ae8  mov     rax, [rdx+10h]
0x180007aec  jmp     loc_1800079DD
0x180007af1  mov     rax, [rcx]
0x180007af4  mov     rax, [rax+10h]
0x180007af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007afd  jmp     loc_180007944
0x180007b02  mov     eax, 80004005h
0x180007b07  jmp     loc_1800079FC
```
