# Windows::Internal::Notifications::CWpnClient::QueryPackageFullName(ushort const *,ushort * *)

- ea: `0x180005a00`
- end: `0x180005d2b`
- name: `?QueryPackageFullName@CWpnClient@Notifications@Internal@Windows@@AEAAJPEBGPEAPEAG@Z`
- size: `811`
- prototype: `int(Windows::Internal::Notifications::CWpnClient *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005860`
- `0x180025040`

## callees

- `0x180005a00`
- `0x1800070e8`
- `0x180007140`
- `0x1800074d0`
- `0x18001ff00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005aeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005aeb`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180005a81`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180005a81`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CWpnClient::QueryPackageFullName(
        Windows::Internal::Notifications::CWpnClient *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  const unsigned __int16 *v3; // rbx
  int PackagesByPackageFamily; // eax
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rdi
  _WORD *v8; // rax
  _WORD *v9; // rdx
  int v10; // r14d
  unsigned __int64 v11; // rcx
  _WORD *v12; // rcx
  PWSTR v14; // rbx
  unsigned __int64 v15; // rsi
  int v16; // eax
  unsigned int v17; // edi
  unsigned __int64 v18; // rdx
  unsigned __int16 *v19; // r8
  unsigned __int16 *v20; // rcx
  int bufferLength; // [rsp+20h] [rbp-E0h]
  UINT32 count; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v24; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v25; // [rsp+58h] [rbp-A8h]
  UINT32 v26; // [rsp+60h] [rbp-A0h] BYREF
  PWSTR packageFullNames; // [rsp+68h] [rbp-98h] BYREF
  WCHAR buffer[128]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v26 = 128;
  v3 = a2;
  *a3 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  packageFullNames = 0;
  count = 1;
  PackagesByPackageFamily = FindPackagesByPackageFamily(a2, 0x10u, &count, &packageFullNames, &v26, buffer, 0);
  if ( PackagesByPackageFamily > 0 )
    PackagesByPackageFamily = (unsigned __int16)PackagesByPackageFamily | 0x80070000;
  if ( PackagesByPackageFamily || !count )
  {
    if ( !v3 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v23);
      goto LABEL_23;
    }
    v6 = -1;
    do
      ++v6;
    while ( v3[v6] );
    v7 = v6 + 1;
    if ( v6 + 1 >= v6 && is_mul_ok(v7, 2u) )
    {
      v8 = CoTaskMemAlloc(2 * v7);
      v9 = v8;
      if ( !v8 )
      {
        v10 = -2147024882;
        goto LABEL_42;
      }
      v25 = v6 + 1;
      v10 = 0;
      v23 = v8;
      *v8 = 0;
      if ( v6 != -1 )
      {
        if ( v6 > 0x7FFFFFFE || v7 > 0x7FFFFFFF )
        {
          *v8 = 0;
        }
        else
        {
          v11 = v6;
          do
          {
            if ( !v11 )
              break;
            if ( !*v3 )
              break;
            *v9++ = *v3++;
            --v11;
            --v7;
          }
          while ( v7 );
          v12 = v9 - 1;
          if ( v7 )
            v12 = v9;
          *v12 = 0;
        }
      }
      v24 = v6;
    }
    else
    {
      v10 = -2147024362;
    }
    if ( v10 >= 0 )
      goto LABEL_23;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
      (const char *)(unsigned int)v10,
      bufferLength);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v23);
    return (unsigned int)v10;
  }
  if ( count != 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
      (const char *)0x8000FFFFLL,
      bufferLength);
    return 2147549183LL;
  }
  v14 = packageFullNames;
  if ( !packageFullNames || !*packageFullNames )
  {
LABEL_23:
    *a3 = v23;
    return 0;
  }
  v15 = -1;
  do
    ++v15;
  while ( packageFullNames[v15] );
  v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
          (__int64)&v23,
          v15);
  v17 = v16;
  if ( v16 >= 0 )
  {
    v18 = v15 + 1;
    if ( v15 != -1 )
    {
      v19 = v23;
      if ( v15 > 0x7FFFFFFE || v18 > 0x7FFFFFFF )
      {
        *v23 = 0;
      }
      else
      {
        do
        {
          if ( !v15 )
            break;
          if ( !*v14 )
            break;
          *v19++ = *v14++;
          --v15;
          --v18;
        }
        while ( v18 );
        v20 = v19 - 1;
        if ( v18 )
          v20 = v19;
        *v20 = 0;
      }
    }
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAC,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\cwpnclient.cpp",
    (const char *)(unsigned int)v16,
    bufferLength);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v23);
  return v17;
}

```

## disassembly

```asm
0x180005a00  push    rbp
0x180005a02  push    rbx
0x180005a03  push    r12
0x180005a05  push    r15
0x180005a07  lea     rbp, [rsp-98h]
0x180005a0f  sub     rsp, 198h
0x180005a16  mov     rax, cs:__security_cookie
0x180005a1d  xor     rax, rsp
0x180005a20  mov     [rbp+0B0h+var_30], rax
0x180005a27  xor     r12d, r12d
0x180005a2a  mov     [rsp+1B0h+var_150], 80h
0x180005a32  mov     rbx, rdx
0x180005a35  mov     [rsp+1B0h+packageProperties], r12; packageProperties
0x180005a3a  lea     rax, [rbp+0B0h+var_130]
0x180005a3e  mov     [r8], r12
0x180005a41  mov     [rsp+1B0h+buffer], rax; buffer
0x180005a46  lea     r9, [rsp+1B0h+packageFullNames]; packageFullNames
0x180005a4b  lea     rax, [rsp+1B0h+var_150]
0x180005a50  mov     [rsp+1B0h+var_168], r12
0x180005a55  mov     r15, r8
0x180005a58  mov     [rsp+1B0h+bufferLength], rax; int
0x180005a5d  lea     r8, [rsp+1B0h+count]; count
0x180005a62  mov     [rsp+1B0h+var_160], r12
0x180005a67  mov     edx, 10h; packageFilters
0x180005a6c  mov     [rsp+1B0h+var_158], r12
0x180005a71  mov     rcx, rbx; packageFamilyName
0x180005a74  mov     [rsp+1B0h+packageFullNames], r12
0x180005a79  mov     [rsp+1B0h+count], 1
0x180005a81  call    cs:__imp_FindPackagesByPackageFamily
0x180005a87  test    eax, eax
0x180005a89  jg      loc_180005C9E
0x180005a8f  mov     [rsp+1B0h+arg_0], rsi
0x180005a97  mov     [rsp+1B0h+arg_18], rdi
0x180005a9f  mov     [rsp+1B0h+var_20], r14
0x180005aa7  test    eax, eax
0x180005aa9  jz      loc_180005BB5
0x180005aaf  test    rbx, rbx
0x180005ab2  jz      loc_180005D1C
0x180005ab8  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180005abf  nop
0x180005ac0  inc     rsi
0x180005ac3  cmp     [rbx+rsi*2], r12w
0x180005ac8  jnz     short loc_180005AC0
0x180005aca  lea     rdi, [rsi+1]
0x180005ace  cmp     rdi, rsi
0x180005ad1  jb      loc_180005B67
0x180005ad7  mov     eax, 2
0x180005adc  mul     rdi
0x180005adf  test    rdx, rdx
0x180005ae2  jnz     loc_180005B67
0x180005ae8  mov     rcx, rax; cb
0x180005aeb  call    cs:__imp_CoTaskMemAlloc
0x180005af1  mov     rdx, rax
0x180005af4  test    rax, rax
0x180005af7  jz      loc_180005CAB
0x180005afd  mov     [rsp+1B0h+var_158], rdi
0x180005b02  mov     r14d, r12d
0x180005b05  mov     [rsp+1B0h+var_168], rax
0x180005b0a  mov     [rax], r12w
0x180005b0e  test    rdi, rdi
0x180005b11  jz      short loc_180005B60
0x180005b13  cmp     rsi, 7FFFFFFEh
0x180005b1a  ja      loc_180005CDE
0x180005b20  cmp     rdi, 7FFFFFFFh
0x180005b27  ja      loc_180005CDE
0x180005b2d  mov     rcx, rsi
0x180005b30  test    rcx, rcx
0x180005b33  jz      short loc_180005B51
0x180005b35  movzx   eax, word ptr [rbx]
0x180005b38  test    ax, ax
0x180005b3b  jz      short loc_180005B51
0x180005b3d  mov     [rdx], ax
0x180005b40  add     rbx, 2
0x180005b44  add     rdx, 2
0x180005b48  dec     rcx
0x180005b4b  sub     rdi, 1
0x180005b4f  jnz     short loc_180005B30
0x180005b51  test    rdi, rdi
0x180005b54  lea     rcx, [rdx-2]
0x180005b58  cmovnz  rcx, rdx
0x180005b5c  mov     [rcx], r12w
0x180005b60  mov     [rsp+1B0h+var_160], rsi
0x180005b65  jmp     short loc_180005B6D
0x180005b67  mov     r14d, 80070216h
0x180005b6d  test    r14d, r14d
0x180005b70  js      loc_180005CB1
0x180005b76  mov     rax, [rsp+1B0h+var_168]
0x180005b7b  mov     [r15], rax
0x180005b7e  xor     eax, eax
0x180005b80  mov     r14, [rsp+1B0h+var_20]
0x180005b88  mov     rdi, [rsp+1B0h+arg_18]
0x180005b90  mov     rsi, [rsp+1B0h+arg_0]
0x180005b98  mov     rcx, [rbp+0B0h+var_30]
0x180005b9f  xor     rcx, rsp; StackCookie
0x180005ba2  call    __security_check_cookie
0x180005ba7  add     rsp, 198h
0x180005bae  pop     r15
0x180005bb0  pop     r12
0x180005bb2  pop     rbx
0x180005bb3  pop     rbp
0x180005bb4  retn
0x180005bb5  mov     eax, [rsp+1B0h+count]
0x180005bb9  test    eax, eax
0x180005bbb  jz      loc_180005AAF
0x180005bc1  cmp     eax, 1
0x180005bc4  jnz     loc_180005C76
0x180005bca  mov     rbx, [rsp+1B0h+packageFullNames]
0x180005bcf  test    rbx, rbx
0x180005bd2  jz      short loc_180005B76
0x180005bd4  cmp     [rbx], r12w
0x180005bd8  jz      short loc_180005B76
0x180005bda  test    rbx, rbx
0x180005bdd  jz      loc_180005D1C
0x180005be3  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180005bea  nop     word ptr [rax+rax+00h]
0x180005bf0  inc     rsi
0x180005bf3  cmp     [rbx+rsi*2], r12w
0x180005bf8  jnz     short loc_180005BF0
0x180005bfa  mov     rdx, rsi
0x180005bfd  lea     rcx, [rsp+1B0h+var_168]
0x180005c02  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180005c07  mov     edi, eax
0x180005c09  test    eax, eax
0x180005c0b  js      loc_180005CE7
0x180005c11  lea     rdx, [rsi+1]
0x180005c15  test    rdx, rdx
0x180005c18  jz      loc_180005B76
0x180005c1e  mov     r8, [rsp+1B0h+var_168]
0x180005c23  cmp     rsi, 7FFFFFFEh
0x180005c2a  ja      loc_180005D13
0x180005c30  cmp     rdx, 7FFFFFFFh
0x180005c37  ja      loc_180005D13
0x180005c3d  nop     dword ptr [rax]
0x180005c40  test    rsi, rsi
0x180005c43  jz      short loc_180005C62
0x180005c45  movzx   eax, word ptr [rbx]
0x180005c48  test    ax, ax
0x180005c4b  jz      short loc_180005C62
0x180005c4d  mov     [r8], ax
0x180005c51  add     rbx, 2
0x180005c55  add     r8, 2
0x180005c59  dec     rsi
0x180005c5c  sub     rdx, 1
0x180005c60  jnz     short loc_180005C40
0x180005c62  test    rdx, rdx
0x180005c65  lea     rcx, [r8-2]
0x180005c69  cmovnz  rcx, r8
0x180005c6d  mov     [rcx], r12w
0x180005c71  jmp     loc_180005B76
0x180005c76  mov     rcx, [rbp+0B8h]; this
0x180005c7d  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005c84  mov     r9d, 8000FFFFh; char *
0x180005c8a  mov     edx, 0A8h; void *
0x180005c8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c94  mov     eax, 8000FFFFh
0x180005c99  jmp     loc_180005B80
0x180005c9e  movzx   eax, ax
0x180005ca1  or      eax, 80070000h
0x180005ca6  jmp     loc_180005A8F
0x180005cab  mov     r14d, 8007000Eh
0x180005cb1  mov     rcx, [rbp+0B8h]; this
0x180005cb8  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005cbf  mov     r9d, r14d; char *
0x180005cc2  mov     edx, 0B2h; void *
0x180005cc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ccc  lea     rcx, [rsp+1B0h+var_168]
0x180005cd1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180005cd6  mov     eax, r14d
0x180005cd9  jmp     loc_180005B80
0x180005cde  mov     [rax], r12w
0x180005ce2  jmp     loc_180005B60
0x180005ce7  mov     rcx, [rbp+0B8h]; this
0x180005cee  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180005cf5  mov     r9d, edi; char *
0x180005cf8  mov     edx, 0ACh; void *
0x180005cfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d02  lea     rcx, [rsp+1B0h+var_168]
0x180005d07  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180005d0c  mov     eax, edi
0x180005d0e  jmp     loc_180005B80
0x180005d13  mov     [r8], r12w
0x180005d17  jmp     loc_180005B76
0x180005d1c  lea     rcx, [rsp+1B0h+var_168]
0x180005d21  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180005d26  jmp     loc_180005B76
```
