# _BuildBackupUserDataPath

- ea: `0x180032918`
- end: `0x180032abb`
- name: `_BuildBackupUserDataPath`
- size: `419`
- prototype: `__int64 __fastcall(__int64, WCHAR *, const WCHAR *, WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180032ac4`

## callees

- `0x180032918`
- `0x1800332b0`
- `0x1800772c0`

## import_xrefs

- `SHELL32!__imp_PathCleanupSpec` at `0x180032a41`
- `SHELL32!__imp_PathCleanupSpec` at `0x180032a41`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180032a6d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180032a6d`
- `OLEAUT32!__imp_VariantClear` at `0x1800329f2`
- `OLEAUT32!__imp_VariantClear` at `0x1800329f2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180032a87`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180032a87`

## pseudocode

```c
__int64 __fastcall BuildBackupUserDataPath(__int64 a1, WCHAR *a2, const WCHAR *a3, WCHAR *a4)
{
  __int64 v7; // rdi
  unsigned int v8; // esi
  BSTR bstrVal; // rax
  __int64 v10; // rcx
  WCHAR *v11; // r8
  __int64 v12; // rdx
  WCHAR *v13; // rcx
  signed int v14; // ebx
  __int64 v15; // rdx
  WCHAR *v16; // rax
  WCHAR *v17; // rcx
  VARIANTARG pvarg; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszSpec[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v7 = 2147483646;
  v8 = -2147467259;
  if ( (int)GetLogonUserSetting(a1, L"DisplayName", &pvarg) >= 0 )
  {
    if ( pvarg.vt == 8 && (bstrVal = pvarg.bstrVal) != 0 && *pvarg.bstrVal )
    {
      v10 = 2147483646;
      v11 = pszSpec;
      v12 = 260;
      do
      {
        if ( !v10 )
          break;
        if ( !*bstrVal )
          break;
        *v11++ = *bstrVal++;
        --v10;
        --v12;
      }
      while ( v12 );
      v13 = v11 - 1;
      if ( v12 )
        v13 = v11;
      v14 = v12 == 0 ? 0x8007007A : 0;
      *v13 = 0;
    }
    else
    {
      v14 = -2147467259;
    }
    VariantClear(&pvarg);
    if ( v14 >= 0 )
      goto LABEL_22;
  }
  v15 = 260;
  v16 = pszSpec;
  do
  {
    if ( !v7 )
      break;
    if ( !*a2 )
      break;
    *v16++ = *a2++;
    --v7;
    --v15;
  }
  while ( v15 );
  v17 = v16 - 1;
  if ( v15 )
    v17 = v16;
  *v17 = 0;
  if ( v15 )
  {
LABEL_22:
    if ( (PathCleanupSpec(a3, pszSpec) & 0x80000008) == 0 && pszSpec[0] )
      return (unsigned int)PathCchCombine(a4, 0x104u, a3, pszSpec);
  }
  if ( LoadStringW(g_hinst, 0x66u, pszSpec, 260) )
    return (unsigned int)PathCchCombine(a4, 0x104u, a3, pszSpec);
  return v8;
}

```

## disassembly

```asm
0x180032918  mov     [rsp-8+arg_8], rbx
0x18003291d  push    rbp
0x18003291e  push    rsi
0x18003291f  push    rdi
0x180032920  push    r12
0x180032922  push    r13
0x180032924  push    r14
0x180032926  push    r15
0x180032928  lea     rbp, [rsp-160h]
0x180032930  sub     rsp, 260h
0x180032937  mov     rax, cs:__security_cookie
0x18003293e  xor     rax, rsp
0x180032941  mov     [rbp+190h+var_40], rax
0x180032948  mov     r15, r8
0x18003294b  mov     r14, rdx
0x18003294e  xorps   xmm0, xmm0
0x180032951  lea     r8, [rsp+290h+pvarg]
0x180032956  xor     eax, eax
0x180032958  lea     rdx, aDisplayname; "DisplayName"
0x18003295f  movups  xmmword ptr [rsp+290h+pvarg], xmm0
0x180032964  mov     qword ptr [rsp+290h+pvarg+10h], rax
0x180032969  mov     r12, r9
0x18003296c  call    _GetLogonUserSetting
0x180032971  xor     r13d, r13d
0x180032974  mov     edi, 7FFFFFFEh
0x180032979  mov     esi, 80004005h
0x18003297e  test    eax, eax
0x180032980  js      short loc_1800329FC
0x180032982  lea     eax, [r13+8]
0x180032986  cmp     ax, word ptr [rsp+290h+pvarg]
0x18003298b  jnz     short loc_1800329EB
0x18003298d  mov     rax, qword ptr [rsp+290h+pvarg+8]
0x180032992  test    rax, rax
0x180032995  jz      short loc_1800329EB
0x180032997  cmp     [rax], r13w
0x18003299b  jz      short loc_1800329EB
0x18003299d  mov     ecx, edi
0x18003299f  lea     r8, [rsp+290h+pszSpec]
0x1800329a4  mov     edx, 104h
0x1800329a9  test    rcx, rcx
0x1800329ac  jz      short loc_1800329CD
0x1800329ae  movzx   r9d, word ptr [rax]
0x1800329b2  test    r9w, r9w
0x1800329b6  jz      short loc_1800329CD
0x1800329b8  mov     [r8], r9w
0x1800329bc  add     rax, 2
0x1800329c0  add     r8, 2
0x1800329c4  dec     rcx
0x1800329c7  sub     rdx, 1
0x1800329cb  jnz     short loc_1800329A9
0x1800329cd  test    rdx, rdx
0x1800329d0  lea     rcx, [r8-2]
0x1800329d4  cmovnz  rcx, r8
0x1800329d8  neg     rdx
0x1800329db  sbb     ebx, ebx
0x1800329dd  not     ebx
0x1800329df  and     ebx, 8007007Ah
0x1800329e5  mov     [rcx], r13w
0x1800329e9  jmp     short loc_1800329ED
0x1800329eb  mov     ebx, esi
0x1800329ed  lea     rcx, [rsp+290h+pvarg]; pvarg
0x1800329f2  call    cs:__imp_VariantClear
0x1800329f8  test    ebx, ebx
0x1800329fa  jns     short loc_180032A39
0x1800329fc  mov     edx, 104h
0x180032a01  lea     rax, [rsp+290h+pszSpec]
0x180032a06  test    rdi, rdi
0x180032a09  jz      short loc_180032A28
0x180032a0b  movzx   ecx, word ptr [r14]
0x180032a0f  test    cx, cx
0x180032a12  jz      short loc_180032A28
0x180032a14  mov     [rax], cx
0x180032a17  add     r14, 2
0x180032a1b  add     rax, 2
0x180032a1f  dec     rdi
0x180032a22  sub     rdx, 1
0x180032a26  jnz     short loc_180032A06
0x180032a28  test    rdx, rdx
0x180032a2b  lea     rcx, [rax-2]
0x180032a2f  cmovnz  rcx, rax
0x180032a33  mov     [rcx], r13w
0x180032a37  jz      short loc_180032A56
0x180032a39  lea     rdx, [rsp+290h+pszSpec]; pszSpec
0x180032a3e  mov     rcx, r15; pszDir
0x180032a41  call    cs:__imp_PathCleanupSpec
0x180032a47  test    eax, 80000008h
0x180032a4c  jnz     short loc_180032A56
0x180032a4e  cmp     r13w, [rsp+290h+pszSpec]
0x180032a54  jnz     short loc_180032A77
0x180032a56  mov     rcx, cs:g_hinst; hInstance
0x180032a5d  lea     r8, [rsp+290h+pszSpec]; lpBuffer
0x180032a62  mov     r9d, 104h; cchBufferMax
0x180032a68  mov     edx, 66h ; 'f'; uID
0x180032a6d  call    cs:__imp_LoadStringW
0x180032a73  test    eax, eax
0x180032a75  jz      short loc_180032A8F
0x180032a77  lea     r9, [rsp+290h+pszSpec]; pszMore
0x180032a7c  mov     r8, r15; pszPathIn
0x180032a7f  mov     edx, 104h; cchPathOut
0x180032a84  mov     rcx, r12; pszPathOut
0x180032a87  call    cs:__imp_PathCchCombine
0x180032a8d  mov     esi, eax
0x180032a8f  mov     eax, esi
0x180032a91  mov     rcx, [rbp+190h+var_40]
0x180032a98  xor     rcx, rsp; StackCookie
0x180032a9b  call    __security_check_cookie
0x180032aa0  mov     rbx, [rsp+290h+arg_8]
0x180032aa8  add     rsp, 260h
0x180032aaf  pop     r15
0x180032ab1  pop     r14
0x180032ab3  pop     r13
0x180032ab5  pop     r12
0x180032ab7  pop     rdi
0x180032ab8  pop     rsi
0x180032ab9  pop     rbp
0x180032aba  retn
```
