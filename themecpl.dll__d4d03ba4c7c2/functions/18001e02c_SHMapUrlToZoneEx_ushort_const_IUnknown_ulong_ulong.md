# SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x18001e02c`
- end: `0x18001e283`
- name: `?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `599`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c2a0`

## callees

- `0x180002280`
- `0x180002f34`
- `0x18001dde0`
- `0x18001e02c`
- `0x1800556e0`
- `0x180055734`

## import_xrefs

- `SHLWAPI!PathIsRootW` at `0x18001e1ff`
- `SHLWAPI!PathIsRootW` at `0x18001e1ff`
- `SHLWAPI!PathStripToRootW` at `0x18001e1ea`
- `SHLWAPI!PathStripToRootW` at `0x18001e1ea`
- `SHLWAPI!PathIsNetworkPathW` at `0x18001e197`
- `SHLWAPI!PathIsNetworkPathW` at `0x18001e197`
- `SHLWAPI!StrStrIW` at `0x18001e15c`
- `SHLWAPI!StrStrIW` at `0x18001e17d`
- `SHLWAPI!StrStrIW` at `0x18001e1b7`
- `SHLWAPI!StrStrIW` at `0x18001e1d4`
- `SHLWAPI!StrStrIW` at `0x18001e15c`
- `SHLWAPI!StrStrIW` at `0x18001e17d`
- `SHLWAPI!StrStrIW` at `0x18001e1b7`
- `SHLWAPI!StrStrIW` at `0x18001e1d4`
- `SHLWAPI!PathIsURLW` at `0x18001e092`
- `SHLWAPI!PathIsURLW` at `0x18001e092`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001e0b4`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18001e0b4`

## pseudocode

```c
__int64 __fastcall SHMapUrlToZoneEx(const unsigned __int16 *a1, struct IUnknown *a2, __int64 a3, unsigned int *a4)
{
  const WCHAR *v5; // rdi
  struct IUnknown *v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rsi
  __int64 result; // rax
  __int64 v10; // rcx
  WCHAR *v11; // rax
  WCHAR *v12; // rcx
  WCHAR v13; // cx
  WCHAR *v14; // rax
  unsigned int v15; // eax
  WCHAR pszFirst[2088]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v17[4176]; // [rsp+1070h] [rbp+F70h] BYREF

  v5 = a1;
  if ( !a1 )
  {
    if ( a4 )
      *a4 = -1;
    return 2147942487LL;
  }
  if ( !a4 )
    return 2147942487LL;
  memset_0(v17, 0, 0x1048u);
  v8 = 2084;
  if ( !PathIsURLW(v5) && (unsigned int)SHExpandEnvironmentStringsW(v5, v17, 2084) )
    v5 = (const WCHAR *)v17;
  result = SHMapUrlToZone(v5, v6, v7, a4);
  if ( (int)result < 0 )
  {
    memset_0(pszFirst, 0, 0x1048u);
    v10 = 2147483646;
    v11 = pszFirst;
    do
    {
      if ( !v10 )
        break;
      if ( !*v5 )
        break;
      *v11++ = *v5++;
      --v10;
      --v8;
    }
    while ( v8 );
    v12 = v11 - 1;
    if ( v8 )
      v12 = v11;
    *v12 = 0;
    v13 = pszFirst[0];
    if ( pszFirst[0] )
    {
      v14 = pszFirst;
      do
      {
        if ( v13 == 47 )
          *v14 = 92;
        v13 = *++v14;
      }
      while ( *v14 );
    }
    if ( StrStrIW(pszFirst, L"\\??")
      || StrStrIW(pszFirst, L"\\\\?\\GLOBAL")
      || PathIsNetworkPathW(pszFirst)
      || (StrStrIW(pszFirst, L"\\\\") || StrStrIW(pszFirst, L"//"))
      && (!PathStripToRootW(pszFirst)
       || !PathIsRootW(pszFirst)
       || !wcscmp_0(pszFirst, L"\\\\?")
       || !wcscmp_0(pszFirst, L"\\\\.")) )
    {
      v15 = 4;
    }
    else
    {
      v15 = 0;
    }
    *a4 = v15;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001e02c  mov     [rsp-8+arg_8], rbx
0x18001e031  mov     [rsp-8+arg_10], rsi
0x18001e036  push    rbp
0x18001e037  push    rdi
0x18001e038  push    r14
0x18001e03a  lea     rbp, [rsp-1FD0h]
0x18001e042  mov     eax, 20D0h
0x18001e047  call    _alloca_probe
0x18001e04c  sub     rsp, rax
0x18001e04f  mov     rax, cs:__security_cookie
0x18001e056  xor     rax, rsp
0x18001e059  mov     [rbp+1FE0h+var_20], rax
0x18001e060  xor     r14d, r14d
0x18001e063  mov     rbx, r9
0x18001e066  mov     rdi, rcx
0x18001e069  test    rcx, rcx
0x18001e06c  jz      loc_18001E24A
0x18001e072  test    rbx, rbx
0x18001e075  jz      loc_18001E256
0x18001e07b  xor     edx, edx; Val
0x18001e07d  lea     rcx, [rbp+1FE0h+var_1070]; void *
0x18001e084  mov     r8d, 1048h; Size
0x18001e08a  call    memset_0
0x18001e08f  mov     rcx, rdi; pszPath
0x18001e092  call    cs:__imp_PathIsURLW
0x18001e099  nop     dword ptr [rax+rax+00h]
0x18001e09e  mov     esi, 824h
0x18001e0a3  test    eax, eax
0x18001e0a5  jnz     short loc_18001E0CB
0x18001e0a7  mov     r8d, esi
0x18001e0aa  lea     rdx, [rbp+1FE0h+var_1070]
0x18001e0b1  mov     rcx, rdi
0x18001e0b4  call    cs:__imp_SHExpandEnvironmentStringsW
0x18001e0bb  nop     dword ptr [rax+rax+00h]
0x18001e0c0  test    eax, eax
0x18001e0c2  jz      short loc_18001E0CB
0x18001e0c4  lea     rdi, [rbp+1FE0h+var_1070]
0x18001e0cb  mov     r9, rbx; unsigned int *
0x18001e0ce  mov     rcx, rdi; unsigned __int16 *
0x18001e0d1  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x18001e0d6  test    eax, eax
0x18001e0d8  jns     loc_18001E25B
0x18001e0de  xor     edx, edx; Val
0x18001e0e0  lea     rcx, [rsp+20E0h+pszFirst]; void *
0x18001e0e5  mov     r8d, 1048h; Size
0x18001e0eb  call    memset_0
0x18001e0f0  mov     ecx, 7FFFFFFEh
0x18001e0f5  lea     rax, [rsp+20E0h+pszFirst]
0x18001e0fa  test    rcx, rcx
0x18001e0fd  jz      short loc_18001E11B
0x18001e0ff  movzx   edx, word ptr [rdi]
0x18001e102  test    dx, dx
0x18001e105  jz      short loc_18001E11B
0x18001e107  mov     [rax], dx
0x18001e10a  add     rdi, 2
0x18001e10e  add     rax, 2
0x18001e112  dec     rcx
0x18001e115  sub     rsi, 1
0x18001e119  jnz     short loc_18001E0FA
0x18001e11b  test    rsi, rsi
0x18001e11e  lea     rcx, [rax-2]
0x18001e122  cmovnz  rcx, rax
0x18001e126  mov     [rcx], r14w
0x18001e12a  movzx   ecx, [rsp+20E0h+pszFirst]
0x18001e12f  test    cx, cx
0x18001e132  jz      short loc_18001E150
0x18001e134  lea     rax, [rsp+20E0h+pszFirst]
0x18001e139  cmp     cx, 2Fh ; '/'
0x18001e13d  jnz     short loc_18001E144
0x18001e13f  mov     word ptr [rax], 5Ch ; '\'
0x18001e144  add     rax, 2
0x18001e148  movzx   ecx, word ptr [rax]
0x18001e14b  test    cx, cx
0x18001e14e  jnz     short loc_18001E139
0x18001e150  lea     rdx, asc_18005E790; "\\??"
0x18001e157  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x18001e15c  call    cs:__imp_StrStrIW
0x18001e163  nop     dword ptr [rax+rax+00h]
0x18001e168  test    rax, rax
0x18001e16b  jnz     loc_18001E23E
0x18001e171  lea     rdx, aGlobal; "\\\\?\\GLOBAL"
0x18001e178  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x18001e17d  call    cs:__imp_StrStrIW
0x18001e184  nop     dword ptr [rax+rax+00h]
0x18001e189  test    rax, rax
0x18001e18c  jnz     loc_18001E23E
0x18001e192  lea     rcx, [rsp+20E0h+pszFirst]; pszPath
0x18001e197  call    cs:__imp_PathIsNetworkPathW
0x18001e19e  nop     dword ptr [rax+rax+00h]
0x18001e1a3  test    eax, eax
0x18001e1a5  jnz     loc_18001E23E
0x18001e1ab  lea     rdx, asc_18005E7B0; "\\\\"
0x18001e1b2  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x18001e1b7  call    cs:__imp_StrStrIW
0x18001e1be  nop     dword ptr [rax+rax+00h]
0x18001e1c3  test    rax, rax
0x18001e1c6  jnz     short loc_18001E1E5
0x18001e1c8  lea     rdx, asc_18005E7B8; "//"
0x18001e1cf  lea     rcx, [rsp+20E0h+pszFirst]; pszFirst
0x18001e1d4  call    cs:__imp_StrStrIW
0x18001e1db  nop     dword ptr [rax+rax+00h]
0x18001e1e0  test    rax, rax
0x18001e1e3  jz      short loc_18001E239
0x18001e1e5  lea     rcx, [rsp+20E0h+pszFirst]; pszPath
0x18001e1ea  call    cs:__imp_PathStripToRootW
0x18001e1f1  nop     dword ptr [rax+rax+00h]
0x18001e1f6  test    eax, eax
0x18001e1f8  jz      short loc_18001E23E
0x18001e1fa  lea     rcx, [rsp+20E0h+pszFirst]; pszPath
0x18001e1ff  call    cs:__imp_PathIsRootW
0x18001e206  nop     dword ptr [rax+rax+00h]
0x18001e20b  test    eax, eax
0x18001e20d  jz      short loc_18001E23E
0x18001e20f  lea     rdx, asc_18005E7C0; "\\\\?"
0x18001e216  lea     rcx, [rsp+20E0h+pszFirst]; String1
0x18001e21b  call    wcscmp_0
0x18001e220  test    eax, eax
0x18001e222  jz      short loc_18001E23E
0x18001e224  lea     rdx, asc_18005E7C8; "\\\\."
0x18001e22b  lea     rcx, [rsp+20E0h+pszFirst]; String1
0x18001e230  call    wcscmp_0
0x18001e235  test    eax, eax
0x18001e237  jz      short loc_18001E23E
0x18001e239  mov     eax, r14d
0x18001e23c  jmp     short loc_18001E243
0x18001e23e  mov     eax, 4
0x18001e243  mov     [rbx], eax
0x18001e245  mov     eax, r14d
0x18001e248  jmp     short loc_18001E25B
0x18001e24a  test    rbx, rbx
0x18001e24d  jz      short loc_18001E256
0x18001e24f  mov     dword ptr [r9], 0FFFFFFFFh
0x18001e256  mov     eax, 80070057h
0x18001e25b  mov     rcx, [rbp+1FE0h+var_20]
0x18001e262  xor     rcx, rsp; StackCookie
0x18001e265  call    __security_check_cookie
0x18001e26a  lea     r11, [rsp+20E0h+var_10]
0x18001e272  mov     rbx, [r11+28h]
0x18001e276  mov     rsi, [r11+30h]
0x18001e27a  mov     rsp, r11
0x18001e27d  pop     r14
0x18001e27f  pop     rdi
0x18001e280  pop     rbp
0x18001e281  retn
```
