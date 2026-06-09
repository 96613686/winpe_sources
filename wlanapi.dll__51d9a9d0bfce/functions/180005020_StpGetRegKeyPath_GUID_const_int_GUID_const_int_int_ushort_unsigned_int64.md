# StpGetRegKeyPath(_GUID const *,int,_GUID const *,int,int,ushort *,unsigned __int64)

- ea: `0x180005020`
- end: `0x180005296`
- name: `?StpGetRegKeyPath@@YAKPEBU_GUID@@H0HHPEAG_K@Z`
- size: `630`
- prototype: `unsigned int __usercall@<eax>(GUID *rguid@<rcx>, int@<edx>, const struct _GUID *@<r8>, int@<r9d>, int, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004b10`

## callees

- `0x180005020`
- `0x1800052a0`
- `0x180019a20`
- `0x18001aea0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180005082`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180005082`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000512f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800051a8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000512f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800051a8`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x18000525e`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x18000525e`

## pseudocode

```c
__int64 __fastcall StpGetRegKeyPath(
        GUID *rguid,
        int a2,
        const struct _GUID *a3,
        __int64 a4,
        int a5,
        unsigned __int16 *a6)
{
  unsigned int v9; // ebx
  __int64 v10; // rbx
  __int64 result; // rax
  unsigned int v12; // ecx
  __int64 v13; // rsi
  int v14; // eax
  __int64 v15; // rsi
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  OLECHAR v19[40]; // [rsp+30h] [rbp-D8h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-88h] BYREF

  if ( !a6 )
    return 87;
  if ( !(unsigned __int8)IsGetCustomRegRootPathPresent()
    || (v9 = 0, (int)GetCustomRegRootPath(a6, 260, L"Software\\Microsoft\\Wlansvc") < 0) )
  {
    v9 = _o_wcscpy_s(a6, 260, L"Software\\Microsoft\\Wlansvc");
  }
  if ( !v9 )
  {
    v10 = -1;
    if ( a2 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a6[v17] );
      v18 = StringCchPrintfW(&a6[v17], 260 - v17, L"\\%s", L"GroupPolicy");
      v12 = v18;
      if ( v18 < 0 )
      {
        if ( (v18 & 0x1FFF0000) == 0x70000 )
          v12 = (unsigned __int16)v18;
        if ( v12 )
          return v12;
      }
    }
    else if ( rguid )
    {
      v15 = -1;
      do
        ++v15;
      while ( a6[v15] );
      StringFromGUID2(rguid, v19, 39);
      v16 = StringCchPrintfW(&a6[v15], 260 - v15, L"\\%s\\%s", L"Interfaces", v19);
      v12 = v16;
      if ( v16 < 0 )
      {
        if ( (v16 & 0x1FFF0000) == 0x70000 )
          v12 = (unsigned __int16)v16;
        if ( v12 )
          return v12;
      }
    }
    if ( !a3 )
      goto LABEL_34;
    v13 = -1;
    do
      ++v13;
    while ( a6[v13] );
    StringFromGUID2(a3, sz, 39);
    v14 = StringCchPrintfW(&a6[v13], 260 - v13, L"\\%s\\%s", L"Profiles", sz);
    v12 = v14;
    if ( v14 >= 0 )
      goto LABEL_34;
    if ( (v14 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v14;
    if ( !v12 )
    {
LABEL_34:
      do
        ++v10;
      while ( a6[v10] );
      LODWORD(result) = StringCchPrintfW(&a6[v10], 260 - v10, L"\\%s", L"MetaData");
      v12 = result;
      if ( (int)result >= 0 )
        return 0;
      if ( (result & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)result;
    }
    return v12;
  }
  return v9;
}

```

## disassembly

```asm
0x180005020  mov     r11, rsp
0x180005023  push    rsi
0x180005024  push    rdi
0x180005025  push    r14
0x180005027  push    r15
0x180005029  sub     rsp, 0E8h
0x180005030  mov     rax, cs:__security_cookie
0x180005037  xor     rax, rsp
0x18000503a  mov     [rsp+108h+var_38], rax
0x180005042  mov     rdi, [rsp+108h+arg_28]
0x18000504a  mov     r15, r8
0x18000504d  mov     esi, edx
0x18000504f  mov     r14, rcx
0x180005052  test    rdi, rdi
0x180005055  jz      loc_18000528C
0x18000505b  mov     [r11+10h], rbx
0x18000505f  mov     [r11-28h], rbp
0x180005063  call    IsGetCustomRegRootPathPresent
0x180005068  mov     ebp, 104h
0x18000506d  test    al, al
0x18000506f  jnz     loc_18000524F
0x180005075  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Wlansvc"
0x18000507c  mov     rdx, rbp
0x18000507f  mov     rcx, rdi
0x180005082  call    cs:__imp__o_wcscpy_s
0x180005088  mov     ebx, eax
0x18000508a  test    ebx, ebx
0x18000508c  jnz     loc_180005285
0x180005092  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005099  test    esi, esi
0x18000509b  jnz     loc_1800051F7
0x1800050a1  test    r14, r14
0x1800050a4  jnz     loc_180005185
0x1800050aa  test    r15, r15
0x1800050ad  jnz     short loc_180005111
0x1800050af  nop
0x1800050b0  inc     rbx
0x1800050b3  cmp     word ptr [rdi+rbx*2], 0
0x1800050b8  jnz     short loc_1800050B0
0x1800050ba  sub     rbp, rbx
0x1800050bd  lea     rcx, [rdi+rbx*2]; unsigned __int16 *
0x1800050c1  mov     rdx, rbp; unsigned __int64
0x1800050c4  lea     r9, aMetadata; "MetaData"
0x1800050cb  lea     r8, aS_1; "\\%s"
0x1800050d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800050d7  mov     ecx, eax
0x1800050d9  test    eax, eax
0x1800050db  js      loc_180005271
0x1800050e1  xor     eax, eax
0x1800050e3  mov     rbx, [rsp+108h+arg_8]
0x1800050eb  mov     rbp, [rsp+108h+var_28]
0x1800050f3  mov     rcx, [rsp+108h+var_38]
0x1800050fb  xor     rcx, rsp; StackCookie
0x1800050fe  call    __security_check_cookie
0x180005103  add     rsp, 0E8h
0x18000510a  pop     r15
0x18000510c  pop     r14
0x18000510e  pop     rdi
0x18000510f  pop     rsi
0x180005110  retn
0x180005111  mov     rsi, rbx
0x180005114  inc     rsi
0x180005117  cmp     word ptr [rdi+rsi*2], 0
0x18000511c  jnz     short loc_180005114
0x18000511e  mov     r8d, 27h ; '''; cchMax
0x180005124  lea     rdx, [rsp+108h+sz]; lpsz
0x18000512c  mov     rcx, r15; rguid
0x18000512f  call    cs:__imp_StringFromGUID2
0x180005135  lea     rax, [rsp+108h+sz]
0x18000513d  mov     rdx, rbp
0x180005140  sub     rdx, rsi; unsigned __int64
0x180005143  mov     [rsp+108h+var_E8], rax
0x180005148  lea     rcx, [rdi+rsi*2]; unsigned __int16 *
0x18000514c  lea     r9, aProfiles; "Profiles"
0x180005153  lea     r8, aSS; "\\%s\\%s"
0x18000515a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000515f  mov     ecx, eax
0x180005161  test    eax, eax
0x180005163  jns     loc_1800050B0
0x180005169  and     eax, 1FFF0000h
0x18000516e  cmp     eax, 70000h
0x180005173  jnz     short loc_180005178
0x180005175  movzx   ecx, cx
0x180005178  test    ecx, ecx
0x18000517a  jnz     loc_180005248
0x180005180  jmp     loc_1800050B0
0x180005185  mov     rsi, rbx
0x180005188  nop     dword ptr [rax+rax+00000000h]
0x180005190  inc     rsi
0x180005193  cmp     word ptr [rdi+rsi*2], 0
0x180005198  jnz     short loc_180005190
0x18000519a  mov     r8d, 27h ; '''; cchMax
0x1800051a0  lea     rdx, [rsp+108h+var_D8]; lpsz
0x1800051a5  mov     rcx, r14; rguid
0x1800051a8  call    cs:__imp_StringFromGUID2
0x1800051ae  lea     rax, [rsp+108h+var_D8]
0x1800051b3  mov     rdx, rbp
0x1800051b6  sub     rdx, rsi; unsigned __int64
0x1800051b9  mov     [rsp+108h+var_E8], rax
0x1800051be  lea     rcx, [rdi+rsi*2]; unsigned __int16 *
0x1800051c2  lea     r9, aInterfaces; "Interfaces"
0x1800051c9  lea     r8, aSS; "\\%s\\%s"
0x1800051d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800051d5  mov     ecx, eax
0x1800051d7  test    eax, eax
0x1800051d9  jns     loc_1800050AA
0x1800051df  and     eax, 1FFF0000h
0x1800051e4  cmp     eax, 70000h
0x1800051e9  jnz     short loc_1800051EE
0x1800051eb  movzx   ecx, cx
0x1800051ee  test    ecx, ecx
0x1800051f0  jnz     short loc_180005248
0x1800051f2  jmp     loc_1800050AA
0x1800051f7  mov     rax, rbx
0x1800051fa  nop     word ptr [rax+rax+00h]
0x180005200  inc     rax
0x180005203  cmp     word ptr [rdi+rax*2], 0
0x180005208  jnz     short loc_180005200
0x18000520a  mov     rdx, rbp
0x18000520d  lea     rcx, [rdi+rax*2]; unsigned __int16 *
0x180005211  sub     rdx, rax; unsigned __int64
0x180005214  lea     r9, aGrouppolicy; "GroupPolicy"
0x18000521b  lea     r8, aS_1; "\\%s"
0x180005222  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005227  mov     ecx, eax
0x180005229  test    eax, eax
0x18000522b  jns     loc_1800050AA
0x180005231  and     eax, 1FFF0000h
0x180005236  cmp     eax, 70000h
0x18000523b  jnz     short loc_180005240
0x18000523d  movzx   ecx, cx
0x180005240  test    ecx, ecx
0x180005242  jz      loc_1800050AA
0x180005248  mov     eax, ecx
0x18000524a  jmp     loc_1800050E3
0x18000524f  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Wlansvc"
0x180005256  mov     rdx, rbp
0x180005259  mov     rcx, rdi
0x18000525c  xor     ebx, ebx
0x18000525e  call    cs:__imp_GetCustomRegRootPath
0x180005264  test    eax, eax
0x180005266  jns     loc_18000508A
0x18000526c  jmp     loc_180005075
0x180005271  and     eax, 1FFF0000h
0x180005276  cmp     eax, 70000h
0x18000527b  jnz     short loc_180005248
0x18000527d  movzx   eax, cx
0x180005280  jmp     loc_1800050E3
0x180005285  mov     eax, ebx
0x180005287  jmp     loc_1800050E3
0x18000528c  mov     eax, 57h ; 'W'
0x180005291  jmp     loc_1800050F3
```
