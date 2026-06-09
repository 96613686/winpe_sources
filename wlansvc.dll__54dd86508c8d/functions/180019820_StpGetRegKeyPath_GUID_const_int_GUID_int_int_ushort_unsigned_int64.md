# StpGetRegKeyPath(_GUID const *,int,_GUID *,int,int,ushort *,unsigned __int64)

- ea: `0x180019820`
- end: `0x180019bbd`
- name: `?StpGetRegKeyPath@@YAKPEBU_GUID@@HPEAU1@HHPEAG_K@Z`
- size: `925`
- prototype: `unsigned int __fastcall(const struct _GUID *, int, struct _GUID *, int, int, unsigned __int16 *, unsigned __int64)`
- caller_count: `18`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800191a0`
- `0x180019600`
- `0x180019ecc`
- `0x18001a144`
- `0x18001a988`
- `0x18001b070`
- `0x180069b8c`
- `0x180096f1c`
- `0x1800c9630`
- `0x1800cdf9c`
- `0x180103b1c`
- `0x1801ffff8`
- `0x180200148`
- `0x180201508`
- `0x1802017d4`
- `0x180201a00`
- `0x180201c0c`
- `0x180201e08`

## callees

- `0x18000aa0c`
- `0x180019820`
- `0x180019bd0`
- `0x180106340`
- `0x180108234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180019ab1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180019ac0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180019ab1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180019ac0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800198b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019aea`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800198b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180019aea`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019920`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800199f5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019920`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800199f5`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x180019b0a`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x180019b0a`

## pseudocode

```c
__int64 __fastcall StpGetRegKeyPath(
        struct _GUID *a1,
        int a2,
        struct _GUID *a3,
        int a4,
        int a5,
        unsigned __int16 *a6,
        unsigned __int64 a7)
{
  const GUID *v8; // rbp
  __int64 v10; // rbx
  const wchar_t *v11; // rbp
  unsigned int v12; // esi
  unsigned int v13; // eax
  __int64 v14; // rsi
  int v15; // eax
  int v16; // eax
  __int64 v18; // rsi
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // eax
  GUID *v23; // [rsp+30h] [rbp-F8h]
  OLECHAR v25[40]; // [rsp+40h] [rbp-E8h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-98h] BYREF

  v8 = a3;
  v23 = a1;
  v10 = -1;
  if ( a4 )
  {
    v12 = 0;
    _o_wcscpy_s(a6, a7, L"Software\\Microsoft\\Wlansvc");
    a1 = v23;
    goto LABEL_12;
  }
  v11 = L"GroupPolicy";
  if ( !a2 )
    v11 = 0;
  if ( !a6 || !a7 )
  {
    v12 = 87;
    v13 = 87;
    goto LABEL_30;
  }
  if ( IsGetCustomWfdSettingsRegPathPresent()
    && (v12 = 0, (int)GetCustomRegRootPath(a6, a7, L"Software\\Microsoft\\Wlansvc") >= 0)
    || (v12 = _o_wcscpy_s(a6, a7, L"Software\\Microsoft\\Wlansvc")) == 0 )
  {
    if ( v11 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v11[v20] );
      if ( v20 )
      {
        _o_wcscat_s(a6, a7, L"\\");
        v12 = _o_wcscat_s(a6, a7, v11);
      }
    }
  }
  a1 = v23;
  v13 = v12;
  if ( v12 )
  {
LABEL_30:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, v13);
      return v12;
    }
  }
  v12 = v13;
  if ( v13 )
    return v12;
  v8 = a3;
LABEL_12:
  if ( !a2 && a1 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a6[v18] );
    StringFromGUID2(a1, v25, 39);
    v19 = StringCchPrintfW(&a6[v18], a7 - v18, L"\\%s\\%s", L"Interfaces", v25);
    v12 = v19;
    if ( v19 < 0 )
    {
      if ( (v19 & 0x1FFF0000) == 0x70000 )
        v12 = (unsigned __int16)v19;
      if ( v12 )
        return v12;
    }
    else
    {
      v12 = 0;
    }
  }
  if ( a4 )
  {
    v21 = -1;
    do
      ++v21;
    while ( a6[v21] );
    v22 = StringCchPrintfW(&a6[v21], a7 - v21, L"\\%s", L"UserData");
    v12 = v22;
    if ( v22 < 0 )
    {
      if ( (v22 & 0x1FFF0000) == 0x70000 )
        v12 = (unsigned __int16)v22;
      if ( v12 )
        return v12;
    }
    else
    {
      v12 = 0;
    }
  }
  if ( !v8 )
    goto LABEL_19;
  v14 = -1;
  do
    ++v14;
  while ( a6[v14] );
  StringFromGUID2(v8, sz, 39);
  v15 = StringCchPrintfW(&a6[v14], a7 - v14, L"\\%s\\%s", L"Profiles", sz);
  v12 = v15;
  if ( v15 >= 0 )
  {
    v12 = 0;
LABEL_19:
    if ( a5 )
    {
      do
        ++v10;
      while ( a6[v10] );
      v16 = StringCchPrintfW(&a6[v10], a7 - v10, L"\\%s", L"MetaData");
      v12 = v16;
      if ( v16 < 0 )
      {
        if ( (v16 & 0x1FFF0000) == 0x70000 )
          return (unsigned __int16)v16;
      }
      else
      {
        return 0;
      }
    }
    return v12;
  }
  if ( (v15 & 0x1FFF0000) == 0x70000 )
    v12 = (unsigned __int16)v15;
  if ( !v12 )
    goto LABEL_19;
  return v12;
}

```

## disassembly

```asm
0x180019820  mov     [rsp+arg_8], rbx
0x180019825  push    rbp
0x180019826  push    rsi
0x180019827  push    rdi
0x180019828  push    r12
0x18001982a  push    r13
0x18001982c  push    r14
0x18001982e  push    r15
0x180019830  sub     rsp, 0F0h
0x180019837  mov     rax, cs:__security_cookie
0x18001983e  xor     rax, rsp
0x180019841  mov     [rsp+128h+var_48], rax
0x180019849  mov     rdi, [rsp+128h+arg_28]
0x180019851  xor     r13d, r13d
0x180019854  mov     r14, [rsp+128h+arg_30]
0x18001985c  mov     r12d, r9d
0x18001985f  mov     [rsp+128h+rguid], r8
0x180019864  mov     rbp, r8
0x180019867  mov     [rsp+128h+var_F8], rcx
0x18001986c  mov     r15d, edx
0x18001986f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180019876  test    r9d, r9d
0x180019879  jnz     loc_180019ADA
0x18001987f  test    edx, edx
0x180019881  lea     rbp, aGrouppolicy_0; "GroupPolicy"
0x180019888  cmovz   rbp, r13
0x18001988c  test    rdi, rdi
0x18001988f  jz      loc_180019A34
0x180019895  test    r14, r14
0x180019898  jz      loc_180019A34
0x18001989e  call    IsGetCustomWfdSettingsRegPathPresent
0x1800198a3  test    al, al
0x1800198a5  jnz     loc_180019AFA
0x1800198ab  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Wlansvc"
0x1800198b2  mov     rdx, r14
0x1800198b5  mov     rcx, rdi
0x1800198b8  call    cs:__imp__o_wcscpy_s
0x1800198be  mov     esi, eax
0x1800198c0  test    eax, eax
0x1800198c2  jnz     short loc_1800198CD
0x1800198c4  test    rbp, rbp
0x1800198c7  jnz     loc_180019A85
0x1800198cd  mov     rcx, [rsp+128h+var_F8]; rguid
0x1800198d2  mov     eax, esi
0x1800198d4  test    esi, esi
0x1800198d6  jnz     loc_180019A3B
0x1800198dc  mov     esi, eax
0x1800198de  test    eax, eax
0x1800198e0  jnz     loc_1800199A4
0x1800198e6  mov     rbp, [rsp+128h+rguid]
0x1800198eb  test    r15d, r15d
0x1800198ee  jz      loc_1800199D1
0x1800198f4  test    r12d, r12d
0x1800198f7  jnz     loc_180019B39
0x1800198fd  test    rbp, rbp
0x180019900  jz      short loc_18001995D
0x180019902  mov     rsi, rbx
0x180019905  inc     rsi
0x180019908  cmp     word ptr [rdi+rsi*2], 0
0x18001990d  jnz     short loc_180019905
0x18001990f  mov     r8d, 27h ; '''; cchMax
0x180019915  lea     rdx, [rsp+128h+sz]; lpsz
0x18001991d  mov     rcx, rbp; rguid
0x180019920  call    cs:__imp_StringFromGUID2
0x180019926  lea     rax, [rsp+128h+sz]
0x18001992e  mov     rdx, r14
0x180019931  sub     rdx, rsi; unsigned __int64
0x180019934  mov     [rsp+128h+var_108], rax
0x180019939  lea     rcx, [rdi+rsi*2]; unsigned __int16 *
0x18001993d  lea     r9, aProfiles; "Profiles"
0x180019944  lea     r8, aSS_0; "\\%s\\%s"
0x18001994b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019950  mov     esi, eax
0x180019952  test    eax, eax
0x180019954  js      loc_180019B8D
0x18001995a  mov     esi, r13d
0x18001995d  cmp     [rsp+128h+arg_20], 0
0x180019965  jz      short loc_1800199A4
0x180019967  nop     word ptr [rax+rax+00000000h]
0x180019970  inc     rbx
0x180019973  cmp     word ptr [rdi+rbx*2], 0
0x180019978  jnz     short loc_180019970
0x18001997a  sub     r14, rbx
0x18001997d  lea     rcx, [rdi+rbx*2]; unsigned __int16 *
0x180019981  mov     rdx, r14; unsigned __int64
0x180019984  lea     r9, aMetadata_0; "MetaData"
0x18001998b  lea     r8, aS_4; "\\%s"
0x180019992  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019997  mov     esi, eax
0x180019999  test    eax, eax
0x18001999b  js      loc_180019BA5
0x1800199a1  mov     esi, r13d
0x1800199a4  mov     eax, esi
0x1800199a6  mov     rcx, [rsp+128h+var_48]
0x1800199ae  xor     rcx, rsp; StackCookie
0x1800199b1  call    __security_check_cookie
0x1800199b6  mov     rbx, [rsp+128h+arg_8]
0x1800199be  add     rsp, 0F0h
0x1800199c5  pop     r15
0x1800199c7  pop     r14
0x1800199c9  pop     r13
0x1800199cb  pop     r12
0x1800199cd  pop     rdi
0x1800199ce  pop     rsi
0x1800199cf  pop     rbp
0x1800199d0  retn
0x1800199d1  test    rcx, rcx
0x1800199d4  jz      loc_1800198F4
0x1800199da  mov     rsi, rbx
0x1800199dd  nop     dword ptr [rax]
0x1800199e0  inc     rsi
0x1800199e3  cmp     word ptr [rdi+rsi*2], 0
0x1800199e8  jnz     short loc_1800199E0
0x1800199ea  mov     r8d, 27h ; '''; cchMax
0x1800199f0  lea     rdx, [rsp+128h+var_E8]; lpsz
0x1800199f5  call    cs:__imp_StringFromGUID2
0x1800199fb  lea     rax, [rsp+128h+var_E8]
0x180019a00  mov     rdx, r14
0x180019a03  sub     rdx, rsi; unsigned __int64
0x180019a06  mov     [rsp+128h+var_108], rax
0x180019a0b  lea     rcx, [rdi+rsi*2]; unsigned __int16 *
0x180019a0f  lea     r9, aInterfaces; "Interfaces"
0x180019a16  lea     r8, aSS_0; "\\%s\\%s"
0x180019a1d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019a22  mov     esi, eax
0x180019a24  test    eax, eax
0x180019a26  js      loc_180019B1D
0x180019a2c  mov     esi, r13d
0x180019a2f  jmp     loc_1800198F4
0x180019a34  mov     esi, 57h ; 'W'
0x180019a39  mov     eax, esi
0x180019a3b  mov     r10, cs:WPP_GLOBAL_Control
0x180019a42  lea     rdx, WPP_GLOBAL_Control
0x180019a49  cmp     r10, rdx
0x180019a4c  jz      loc_1800198DC
0x180019a52  cmp     byte ptr [r10+69h], 1
0x180019a57  jb      loc_1800198DC
0x180019a5d  test    byte ptr [r10+6Ch], 1
0x180019a62  jz      loc_1800198DC
0x180019a68  mov     rcx, [r10+60h]
0x180019a6c  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180019a73  mov     edx, 0Ah
0x180019a78  mov     r9d, eax
0x180019a7b  call    WPP_SF_d
0x180019a80  jmp     loc_1800199A4
0x180019a85  mov     rax, rbx
0x180019a88  nop     dword ptr [rax+rax+00000000h]
0x180019a90  inc     rax
0x180019a93  cmp     [rbp+rax*2+0], r13w
0x180019a99  jnz     short loc_180019A90
0x180019a9b  test    rax, rax
0x180019a9e  jz      loc_1800198CD
0x180019aa4  lea     r8, SubBlock; "\\"
0x180019aab  mov     rdx, r14
0x180019aae  mov     rcx, rdi
0x180019ab1  call    cs:__imp__o_wcscat_s
0x180019ab7  mov     r8, rbp
0x180019aba  mov     rdx, r14
0x180019abd  mov     rcx, rdi
0x180019ac0  call    cs:__imp__o_wcscat_s
0x180019ac6  mov     esi, eax
0x180019ac8  jmp     loc_1800198CD
0x180019acd  test    esi, esi
0x180019acf  jnz     loc_1800199A4
0x180019ad5  jmp     loc_18001995D
0x180019ada  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Wlansvc"
0x180019ae1  mov     rdx, r14
0x180019ae4  mov     rcx, rdi
0x180019ae7  mov     esi, r13d
0x180019aea  call    cs:__imp__o_wcscpy_s
0x180019af0  mov     rcx, [rsp+128h+var_F8]
0x180019af5  jmp     loc_1800198EB
0x180019afa  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Wlansvc"
0x180019b01  mov     rdx, r14
0x180019b04  mov     rcx, rdi
0x180019b07  mov     esi, r13d
0x180019b0a  call    cs:__imp_GetCustomRegRootPath
0x180019b10  test    eax, eax
0x180019b12  jns     loc_1800198C4
0x180019b18  jmp     loc_1800198AB
0x180019b1d  and     eax, 1FFF0000h
0x180019b22  cmp     eax, 70000h
0x180019b27  jnz     short loc_180019B2C
0x180019b29  movzx   esi, si
0x180019b2c  test    esi, esi
0x180019b2e  jnz     loc_1800199A4
0x180019b34  jmp     loc_1800198F4
0x180019b39  mov     rax, rbx
0x180019b3c  inc     rax
0x180019b3f  cmp     word ptr [rdi+rax*2], 0
0x180019b44  jnz     short loc_180019B3C
0x180019b46  mov     rdx, r14
0x180019b49  lea     rcx, [rdi+rax*2]; unsigned __int16 *
0x180019b4d  sub     rdx, rax; unsigned __int64
0x180019b50  lea     r9, aUserdata; "UserData"
0x180019b57  lea     r8, aS_4; "\\%s"
0x180019b5e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019b63  mov     esi, eax
0x180019b65  test    eax, eax
0x180019b67  js      short loc_180019B71
0x180019b69  mov     esi, r13d
0x180019b6c  jmp     loc_1800198FD
0x180019b71  and     eax, 1FFF0000h
0x180019b76  cmp     eax, 70000h
0x180019b7b  jnz     short loc_180019B80
0x180019b7d  movzx   esi, si
0x180019b80  test    esi, esi
0x180019b82  jnz     loc_1800199A4
0x180019b88  jmp     loc_1800198FD
0x180019b8d  and     eax, 1FFF0000h
0x180019b92  cmp     eax, 70000h
0x180019b97  jnz     loc_180019ACD
0x180019b9d  movzx   esi, si
0x180019ba0  jmp     loc_180019ACD
0x180019ba5  and     eax, 1FFF0000h
0x180019baa  cmp     eax, 70000h
0x180019baf  jnz     loc_1800199A4
0x180019bb5  movzx   esi, si
0x180019bb8  jmp     loc_1800199A4
```
