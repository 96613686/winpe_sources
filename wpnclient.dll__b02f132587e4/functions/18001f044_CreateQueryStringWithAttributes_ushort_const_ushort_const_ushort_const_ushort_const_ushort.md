# CreateQueryStringWithAttributes(ushort const *,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18001f044`
- end: `0x18001f308`
- name: `?CreateQueryStringWithAttributes@@YAJPEBG000PEAPEAG@Z`
- size: `708`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ecb0`

## callees

- `0x1800064c0`
- `0x1800074d0`
- `0x18000dca4`
- `0x18001b848`
- `0x18001f044`
- `0x18001f310`
- `0x18002e0e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateQueryStringWithAttributes(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  unsigned __int16 **v9; // r12
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  const unsigned __int16 *Seperator; // rax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  const unsigned __int16 *v17; // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  const unsigned __int16 *v21; // rax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned __int16 *v25; // rax
  unsigned __int16 *v27; // [rsp+20h] [rbp-20h] BYREF
  __int64 v28; // [rsp+28h] [rbp-18h]
  __int64 v29; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v9 = a5;
  *a5 = 0;
  LOBYTE(a5) = 1;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
          (__int64)&v27,
          (unsigned __int64)&pwzBaseUrl,
          0xFFFFFFFFFFFFFFFFuLL);
  v11 = v10;
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
      (const char *)(unsigned int)v10,
      (int)v27);
  if ( !IsNullOrEmptyString(a1) )
  {
    v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v27, a1);
    v11 = v12;
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v12,
        (int)v27);
    LOBYTE(a5) = 0;
  }
  if ( !IsNullOrEmptyString(a2) )
  {
    Seperator = GetSeperator((bool *)&a5);
    v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v27, Seperator);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v14,
        (int)v27);
    v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
            &v27,
            L"ms-scale=");
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v15,
        (int)v27);
    v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v27, a2);
    v11 = v16;
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v16,
        (int)v27);
    LOBYTE(a5) = 0;
  }
  if ( !IsNullOrEmptyString(a3) )
  {
    v17 = GetSeperator((bool *)&a5);
    v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v27, v17);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v18,
        (int)v27);
    v19 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
            &v27,
            L"ms-contrast=");
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x205,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v19,
        (int)v27);
    v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v27, a3);
    v11 = v20;
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x208,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v20,
        (int)v27);
    LOBYTE(a5) = 0;
  }
  if ( !IsNullOrEmptyString(a4) )
  {
    v21 = GetSeperator((bool *)&a5);
    v22 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v27, v21);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x210,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v22,
        (int)v27);
    v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v27, L"ms-lang=");
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x213,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v23,
        (int)v27);
    v24 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&v27, a4);
    v11 = v24;
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\util.cpp",
        (const char *)(unsigned int)v24,
        (int)v27);
  }
  v25 = v27;
  v27 = 0;
  v29 = 0;
  v28 = 0;
  *v9 = v25;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v27);
  return v11;
}

```

## disassembly

```asm
0x18001f044  push    rbp
0x18001f046  push    rbx
0x18001f047  push    rsi
0x18001f048  push    rdi
0x18001f049  push    r12
0x18001f04b  push    r14
0x18001f04d  push    r15
0x18001f04f  mov     rbp, rsp
0x18001f052  sub     rsp, 40h
0x18001f056  mov     r15, r9
0x18001f059  mov     r14, r8
0x18001f05c  mov     rsi, rdx
0x18001f05f  mov     rdi, rcx
0x18001f062  mov     r12, [rbp+arg_20]
0x18001f066  mov     qword ptr [r12], 0
0x18001f06e  mov     byte ptr [rbp+arg_20], 1
0x18001f072  mov     [rbp+var_20], 0
0x18001f07a  mov     [rbp+var_18], 0
0x18001f082  mov     [rbp+var_10], 0
0x18001f08a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f08e  lea     rdx, pwzBaseUrl
0x18001f095  lea     rcx, [rbp+var_20]
0x18001f099  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001f09e  mov     ebx, eax
0x18001f0a0  mov     rcx, [rbp+38h]; this
0x18001f0a4  test    eax, eax
0x18001f0a6  jns     short loc_18001F0BD
0x18001f0a8  mov     r9d, eax; char *
0x18001f0ab  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f0b2  mov     edx, 1E7h; void *
0x18001f0b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f0bd  mov     rcx, rdi; unsigned __int16 *
0x18001f0c0  call    ?IsNullOrEmptyString@@YA_NPEBG@Z; IsNullOrEmptyString(ushort const *)
0x18001f0c5  test    al, al
0x18001f0c7  jnz     short loc_18001F0F8
0x18001f0c9  mov     rdx, rdi
0x18001f0cc  lea     rcx, [rbp+var_20]
0x18001f0d0  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f0d5  mov     ebx, eax
0x18001f0d7  mov     rcx, [rbp+38h]; this
0x18001f0db  test    eax, eax
0x18001f0dd  jns     short loc_18001F0F4
0x18001f0df  mov     r9d, eax; char *
0x18001f0e2  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f0e9  mov     edx, 1ECh; void *
0x18001f0ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f0f4  mov     byte ptr [rbp+arg_20], 0
0x18001f0f8  mov     rcx, rsi; unsigned __int16 *
0x18001f0fb  call    ?IsNullOrEmptyString@@YA_NPEBG@Z; IsNullOrEmptyString(ushort const *)
0x18001f100  test    al, al
0x18001f102  jnz     loc_18001F196
0x18001f108  lea     rcx, [rbp+arg_20]; bool *
0x18001f10c  call    ?GetSeperator@@YAPEBGAEA_N@Z; GetSeperator(bool &)
0x18001f111  mov     rdx, rax
0x18001f114  lea     rcx, [rbp+var_20]
0x18001f118  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f11d  mov     rcx, [rbp+38h]; this
0x18001f121  test    eax, eax
0x18001f123  jns     short loc_18001F13A
0x18001f125  mov     r9d, eax; char *
0x18001f128  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f12f  mov     edx, 1F4h; void *
0x18001f134  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f13a  lea     rdx, aMsScale; "ms-scale="
0x18001f141  lea     rcx, [rbp+var_20]
0x18001f145  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f14a  mov     rcx, [rbp+38h]; this
0x18001f14e  test    eax, eax
0x18001f150  jns     short loc_18001F167
0x18001f152  mov     r9d, eax; char *
0x18001f155  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f15c  mov     edx, 1F7h; void *
0x18001f161  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f167  mov     rdx, rsi
0x18001f16a  lea     rcx, [rbp+var_20]
0x18001f16e  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f173  mov     ebx, eax
0x18001f175  mov     rcx, [rbp+38h]; this
0x18001f179  test    eax, eax
0x18001f17b  jns     short loc_18001F192
0x18001f17d  mov     r9d, eax; char *
0x18001f180  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f187  mov     edx, 1FAh; void *
0x18001f18c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f192  mov     byte ptr [rbp+arg_20], 0
0x18001f196  mov     rcx, r14; unsigned __int16 *
0x18001f199  call    ?IsNullOrEmptyString@@YA_NPEBG@Z; IsNullOrEmptyString(ushort const *)
0x18001f19e  test    al, al
0x18001f1a0  jnz     loc_18001F234
0x18001f1a6  lea     rcx, [rbp+arg_20]; bool *
0x18001f1aa  call    ?GetSeperator@@YAPEBGAEA_N@Z; GetSeperator(bool &)
0x18001f1af  mov     rdx, rax
0x18001f1b2  lea     rcx, [rbp+var_20]
0x18001f1b6  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f1bb  mov     rcx, [rbp+38h]; this
0x18001f1bf  test    eax, eax
0x18001f1c1  jns     short loc_18001F1D8
0x18001f1c3  mov     r9d, eax; char *
0x18001f1c6  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f1cd  mov     edx, 202h; void *
0x18001f1d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f1d8  lea     rdx, aMsContrast; "ms-contrast="
0x18001f1df  lea     rcx, [rbp+var_20]
0x18001f1e3  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f1e8  mov     rcx, [rbp+38h]; this
0x18001f1ec  test    eax, eax
0x18001f1ee  jns     short loc_18001F205
0x18001f1f0  mov     r9d, eax; char *
0x18001f1f3  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f1fa  mov     edx, 205h; void *
0x18001f1ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f205  mov     rdx, r14
0x18001f208  lea     rcx, [rbp+var_20]
0x18001f20c  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f211  mov     ebx, eax
0x18001f213  mov     rcx, [rbp+38h]; this
0x18001f217  test    eax, eax
0x18001f219  jns     short loc_18001F230
0x18001f21b  mov     r9d, eax; char *
0x18001f21e  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f225  mov     edx, 208h; void *
0x18001f22a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f230  mov     byte ptr [rbp+arg_20], 0
0x18001f234  mov     rcx, r15; unsigned __int16 *
0x18001f237  call    ?IsNullOrEmptyString@@YA_NPEBG@Z; IsNullOrEmptyString(ushort const *)
0x18001f23c  test    al, al
0x18001f23e  jnz     loc_18001F2CE
0x18001f244  lea     rcx, [rbp+arg_20]; bool *
0x18001f248  call    ?GetSeperator@@YAPEBGAEA_N@Z; GetSeperator(bool &)
0x18001f24d  mov     rdx, rax
0x18001f250  lea     rcx, [rbp+var_20]
0x18001f254  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f259  mov     rcx, [rbp+38h]; this
0x18001f25d  test    eax, eax
0x18001f25f  jns     short loc_18001F276
0x18001f261  mov     r9d, eax; char *
0x18001f264  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f26b  mov     edx, 210h; void *
0x18001f270  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f276  lea     rdx, aMsLang; "ms-lang="
0x18001f27d  lea     rcx, [rbp+var_20]
0x18001f281  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f286  mov     rcx, [rbp+38h]; this
0x18001f28a  test    eax, eax
0x18001f28c  jns     short loc_18001F2A3
0x18001f28e  mov     r9d, eax; char *
0x18001f291  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f298  mov     edx, 213h; void *
0x18001f29d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f2a3  mov     rdx, r15
0x18001f2a6  lea     rcx, [rbp+var_20]
0x18001f2aa  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x18001f2af  mov     ebx, eax
0x18001f2b1  mov     rcx, [rbp+38h]; this
0x18001f2b5  test    eax, eax
0x18001f2b7  jns     short loc_18001F2CE
0x18001f2b9  mov     r9d, eax; char *
0x18001f2bc  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001f2c3  mov     edx, 216h; void *
0x18001f2c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f2ce  mov     rax, [rbp+var_20]
0x18001f2d2  mov     [rbp+var_20], 0
0x18001f2da  mov     [rbp+var_10], 0
0x18001f2e2  mov     [rbp+var_18], 0
0x18001f2ea  mov     [r12], rax
0x18001f2ee  lea     rcx, [rbp+var_20]
0x18001f2f2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001f2f7  mov     eax, ebx
0x18001f2f9  add     rsp, 40h
0x18001f2fd  pop     r15
0x18001f2ff  pop     r14
0x18001f301  pop     r12
0x18001f303  pop     rdi
0x18001f304  pop     rsi
0x18001f305  pop     rbx
0x18001f306  pop     rbp
0x18001f307  retn
```
