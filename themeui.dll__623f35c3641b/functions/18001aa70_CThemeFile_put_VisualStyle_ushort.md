# CThemeFile::put_VisualStyle(ushort *)

- ea: `0x18001aa70`
- end: `0x18001acbb`
- name: `?put_VisualStyle@CThemeFile@@UEAAJPEAG@Z`
- size: `587`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800089c0`
- `0x18001aa70`
- `0x1800358c0`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x18001aba7`
- `SHLWAPI!StrStrW` at `0x18001aba7`
- `SHLWAPI!PathIsRelativeW` at `0x18001abbb`
- `SHLWAPI!PathIsRelativeW` at `0x18001abbb`
- `SHLWAPI!__imp_PathUnExpandEnvStringsForUserW` at `0x18001ac80`
- `SHLWAPI!__imp_PathUnExpandEnvStringsForUserW` at `0x18001ac80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001aadb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001aadb`

## pseudocode

```c
__int64 __fastcall CThemeFile::put_VisualStyle(CThemeFile *this, unsigned __int16 *a2)
{
  __int64 *v4; // rbx
  HRESULT v5; // edi
  __int64 v6; // rdx
  unsigned __int16 *v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rcx
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  PWSTR v12; // rax
  __int64 v13; // rax
  LPVOID v14; // rcx
  int v16; // eax
  unsigned __int16 *v17; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszFirst[264]; // [rsp+40h] [rbp-C0h] BYREF

  if ( !*((_QWORD *)this + 4) )
    return (unsigned int)-2147467259;
  v4 = (__int64 *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD))(*v4 + 8))(*((_QWORD *)this + 5));
    v5 = 0;
    goto LABEL_9;
  }
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_PrivateProfile, 0, 1u, &GUID_b57046bc_32e5_428a_9887_19f712b907bf, &ppv);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(
           ppv,
           *((_QWORD *)this + 4),
           0x400000);
    if ( v5 < 0 )
    {
      v14 = ppv;
      v13 = *(_QWORD *)ppv;
LABEL_25:
      (*(void (__fastcall **)(LPVOID, __int64, unsigned __int16 *))(v13 + 16))(v14, v6, v7);
      return (unsigned int)v5;
    }
    v8 = *((_QWORD *)this + 5);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v4 = (__int64 *)ppv;
    *((_QWORD *)this + 5) = ppv;
    (*(void (__fastcall **)(__int64 *))(*v4 + 8))(v4);
LABEL_9:
    *((_BYTE *)this + 48) = 1;
    if ( a2 )
    {
      v9 = 2147483646;
      v10 = pszFirst;
      v7 = a2;
      v6 = 260;
      do
      {
        if ( !v9 )
          break;
        if ( !*v7 )
          break;
        *v10++ = *v7++;
        --v9;
        --v6;
      }
      while ( v6 );
      v11 = v10 - 1;
      if ( v6 )
        v11 = v10;
      *v11 = 0;
      if ( !v6 )
        goto LABEL_21;
      v12 = StrStrW(pszFirst, L",");
      if ( v12 )
        *v12 = 0;
      if ( !PathIsRelativeW(pszFirst) )
      {
        v16 = PathUnExpandEnvStringsForUserW(0, a2, pszFirst, 260);
        v17 = pszFirst;
        if ( !v16 )
          v17 = a2;
        a2 = v17;
      }
    }
    v5 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, const WCHAR *, __int64, unsigned __int16 *))(*v4 + 80))(
           v4,
           L"VisualStyles",
           L"Path",
           1,
           a2);
LABEL_21:
    if ( v5 >= 0 && (int)StringCchPrintfW(pszFirst, 0x104u, L"%s.MUI", L"Path") >= 0 )
      (*(void (__fastcall **)(__int64 *, const WCHAR *, WCHAR *, __int64, _QWORD))(*v4 + 80))(
        v4,
        L"VisualStyles",
        pszFirst,
        1,
        0);
    v13 = *v4;
    v14 = v4;
    goto LABEL_25;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001aa70  mov     [rsp-8+arg_10], rbx
0x18001aa75  push    rbp
0x18001aa76  push    rsi
0x18001aa77  push    rdi
0x18001aa78  push    r14
0x18001aa7a  push    r15
0x18001aa7c  lea     rbp, [rsp-160h]
0x18001aa84  sub     rsp, 260h
0x18001aa8b  mov     rax, cs:__security_cookie
0x18001aa92  xor     rax, rsp
0x18001aa95  mov     [rbp+180h+var_30], rax
0x18001aa9c  xor     r15d, r15d
0x18001aa9f  mov     r14, rdx
0x18001aaa2  mov     rsi, rcx
0x18001aaa5  cmp     [rcx+20h], r15
0x18001aaa9  jz      loc_18001ACB4
0x18001aaaf  mov     rbx, [rcx+28h]
0x18001aab3  test    rbx, rbx
0x18001aab6  jnz     short loc_18001AB37
0x18001aab8  lea     rax, [rsp+280h+var_250]
0x18001aabd  mov     [rsp+280h+var_250], r15
0x18001aac2  lea     r9, _GUID_b57046bc_32e5_428a_9887_19f712b907bf; riid
0x18001aac9  mov     [rsp+280h+ppv], rax; ppv
0x18001aace  xor     edx, edx; pUnkOuter
0x18001aad0  lea     r8d, [r15+1]; dwClsContext
0x18001aad4  lea     rcx, CLSID_PrivateProfile; rclsid
0x18001aadb  call    cs:__imp_CoCreateInstance
0x18001aae1  mov     edi, eax
0x18001aae3  test    eax, eax
0x18001aae5  js      loc_18001AC4B
0x18001aaeb  mov     rcx, [rsp+280h+var_250]
0x18001aaf0  mov     r8d, 400000h
0x18001aaf6  mov     rdx, [rsi+20h]
0x18001aafa  mov     rax, [rcx]
0x18001aafd  mov     rax, [rax+18h]
0x18001ab01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab06  mov     edi, eax
0x18001ab08  test    eax, eax
0x18001ab0a  js      loc_18001AC99
0x18001ab10  mov     rcx, [rsi+28h]
0x18001ab14  test    rcx, rcx
0x18001ab17  jnz     loc_18001ACA3
0x18001ab1d  mov     rbx, [rsp+280h+var_250]
0x18001ab22  mov     [rsi+28h], rbx
0x18001ab26  mov     rcx, rbx
0x18001ab29  mov     rax, [rbx]
0x18001ab2c  mov     rax, [rax+8]
0x18001ab30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab35  jmp     short loc_18001AB49
0x18001ab37  mov     rax, [rbx]
0x18001ab3a  mov     rcx, rbx
0x18001ab3d  mov     rax, [rax+8]
0x18001ab41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab46  mov     edi, r15d
0x18001ab49  mov     byte ptr [rsi+30h], 1
0x18001ab4d  mov     esi, 104h
0x18001ab52  test    r14, r14
0x18001ab55  jz      short loc_18001ABC9
0x18001ab57  mov     ecx, 7FFFFFFEh
0x18001ab5c  lea     rax, [rsp+280h+pszFirst]
0x18001ab61  mov     r8, r14
0x18001ab64  mov     edx, esi
0x18001ab66  test    rcx, rcx
0x18001ab69  jz      short loc_18001AB8A
0x18001ab6b  movzx   r9d, word ptr [r8]
0x18001ab6f  test    r9w, r9w
0x18001ab73  jz      short loc_18001AB8A
0x18001ab75  mov     [rax], r9w
0x18001ab79  add     r8, 2
0x18001ab7d  add     rax, 2
0x18001ab81  dec     rcx
0x18001ab84  sub     rdx, 1
0x18001ab88  jnz     short loc_18001AB66
0x18001ab8a  test    rdx, rdx
0x18001ab8d  lea     rcx, [rax-2]
0x18001ab91  cmovnz  rcx, rax
0x18001ab95  mov     [rcx], r15w
0x18001ab99  jz      short loc_18001ABF3
0x18001ab9b  lea     rdx, pszSrch; ","
0x18001aba2  lea     rcx, [rsp+280h+pszFirst]; pszFirst
0x18001aba7  call    cs:__imp_StrStrW
0x18001abad  test    rax, rax
0x18001abb0  jz      short loc_18001ABB6
0x18001abb2  mov     [rax], r15w
0x18001abb6  lea     rcx, [rsp+280h+pszFirst]; pszPath
0x18001abbb  call    cs:__imp_PathIsRelativeW
0x18001abc1  test    eax, eax
0x18001abc3  jz      loc_18001AC73
0x18001abc9  mov     rax, [rbx]
0x18001abcc  lea     r8, aPath; "Path"
0x18001abd3  mov     r9d, 1
0x18001abd9  mov     [rsp+280h+ppv], r14
0x18001abde  lea     rdx, aVisualstyles; "VisualStyles"
0x18001abe5  mov     rcx, rbx
0x18001abe8  mov     rax, [rax+50h]
0x18001abec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abf1  mov     edi, eax
0x18001abf3  test    edi, edi
0x18001abf5  js      short loc_18001AC3C
0x18001abf7  lea     r9, aPath; "Path"
0x18001abfe  mov     rdx, rsi; unsigned __int64
0x18001ac01  lea     r8, aSMui; "%s.MUI"
0x18001ac08  lea     rcx, [rsp+280h+pszFirst]; unsigned __int16 *
0x18001ac0d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001ac12  test    eax, eax
0x18001ac14  js      short loc_18001AC3C
0x18001ac16  mov     rax, [rbx]
0x18001ac19  lea     r8, [rsp+280h+pszFirst]
0x18001ac1e  mov     r9d, 1
0x18001ac24  mov     [rsp+280h+ppv], r15
0x18001ac29  lea     rdx, aVisualstyles; "VisualStyles"
0x18001ac30  mov     rcx, rbx
0x18001ac33  mov     rax, [rax+50h]
0x18001ac37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac3c  mov     rax, [rbx]
0x18001ac3f  mov     rcx, rbx
0x18001ac42  mov     rax, [rax+10h]
0x18001ac46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac4b  mov     eax, edi
0x18001ac4d  mov     rcx, [rbp+180h+var_30]
0x18001ac54  xor     rcx, rsp; StackCookie
0x18001ac57  call    __security_check_cookie
0x18001ac5c  mov     rbx, [rsp+280h+arg_10]
0x18001ac64  add     rsp, 260h
0x18001ac6b  pop     r15
0x18001ac6d  pop     r14
0x18001ac6f  pop     rdi
0x18001ac70  pop     rsi
0x18001ac71  pop     rbp
0x18001ac72  retn
0x18001ac73  mov     r9d, esi
0x18001ac76  lea     r8, [rsp+280h+pszFirst]
0x18001ac7b  mov     rdx, r14
0x18001ac7e  xor     ecx, ecx
0x18001ac80  call    cs:__imp_PathUnExpandEnvStringsForUserW
0x18001ac86  test    eax, eax
0x18001ac88  lea     rcx, [rsp+280h+pszFirst]
0x18001ac8d  cmovz   rcx, r14
0x18001ac91  mov     r14, rcx
0x18001ac94  jmp     loc_18001ABC9
0x18001ac99  mov     rcx, [rsp+280h+var_250]
0x18001ac9e  mov     rax, [rcx]
0x18001aca1  jmp     short loc_18001AC42
0x18001aca3  mov     rax, [rcx]
0x18001aca6  mov     rax, [rax+10h]
0x18001acaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acaf  jmp     loc_18001AB1D
0x18001acb4  mov     edi, 80004005h
0x18001acb9  jmp     short loc_18001AC4B
```
