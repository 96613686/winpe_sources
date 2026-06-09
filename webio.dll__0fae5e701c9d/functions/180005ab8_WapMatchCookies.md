# WapMatchCookies

- ea: `0x180005ab8`
- end: `0x180005c4a`
- name: `WapMatchCookies`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180074064`

## callees

- `0x180003fb0`
- `0x180005ab8`
- `0x1800068a0`
- `0x18000ed38`
- `0x18006deb8`
- `0x1800722f0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b04`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b04`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005c07`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180005c07`

## pseudocode

```c
__int64 __fastcall WapMatchCookies(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall *a3)(__int64, const FILETIME *, _QWORD *),
        __int64 a4)
{
  __int64 v5; // r15
  __int64 v6; // rcx
  int v7; // r9d
  unsigned int TransformedComponentW; // ebx
  unsigned __int64 v9; // rsi
  _QWORD *v11; // r13
  _QWORD *i; // rdi
  _QWORD *v13; // rsi
  const FILETIME *v14; // r15
  char IsCookieMatch; // al
  char v16[8]; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int64 v17; // [rsp+38h] [rbp-31h] BYREF
  __int64 v18; // [rsp+40h] [rbp-29h]
  _WORD *v19; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-19h] BYREF
  __int64 v21; // [rsp+58h] [rbp-11h]
  __int64 (__fastcall *v22)(__int64, const FILETIME *, _QWORD *); // [rsp+60h] [rbp-9h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-1h] BYREF

  v21 = a4;
  SystemTimeAsFileTime = 0;
  v20 = 0;
  v16[0] = 0;
  v5 = a2;
  v22 = a3;
  v18 = a2;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = *(_QWORD *)(v5 + 16);
  v19 = 0;
  v17 = 0;
  TransformedComponentW = WapUriGetTransformedComponentW(v6, 5, 1107427600, v7, (__int64)&v19, (__int64)&v17);
  if ( !TransformedComponentW )
  {
    v9 = v17;
    if ( v17 && *v19 == 47 )
    {
      v11 = (_QWORD *)(a1 + 40);
      for ( i = (_QWORD *)*v11; i != v11; i = (_QWORD *)*i )
      {
        TransformedComponentW = WaQueryUriCookiePath(i[2], 0, &v20);
        if ( TransformedComponentW )
          break;
        if ( v20 <= v9 )
        {
          TransformedComponentW = WapIsCookieUriMatch(*(_QWORD *)(v5 + 16), i[2], v16);
          if ( TransformedComponentW )
            return TransformedComponentW;
          if ( v16[0] )
          {
            v13 = (_QWORD *)i[3];
            while ( v13 != i + 3 )
            {
              v14 = (const FILETIME *)(v13 - 1);
              v13 = (_QWORD *)*v13;
              IsCookieMatch = WapIsCookieMatch(v14, v18);
              if ( (v14[7].dwLowDateTime & 2) == 0 || **(_DWORD **)(*(_QWORD *)(v18 + 16) + 56LL) == 2 )
              {
                if ( IsCookieMatch )
                {
                  if ( CompareFileTime(v14 + 8, &SystemTimeAsFileTime) >= 0 )
                  {
                    TransformedComponentW = v22(v21, v14, i - 1);
                    if ( TransformedComponentW )
                      return TransformedComponentW;
                  }
                }
              }
            }
            v9 = v17;
            v5 = v18;
          }
        }
      }
    }
    else
    {
      return 13;
    }
  }
  return TransformedComponentW;
}

```

## disassembly

```asm
0x180005ab8  push    rbp
0x180005aba  push    rbx
0x180005abb  push    rsi
0x180005abc  push    rdi
0x180005abd  push    r12
0x180005abf  push    r13
0x180005ac1  push    r14
0x180005ac3  push    r15
0x180005ac5  lea     rbp, [rsp-1Fh]
0x180005aca  sub     rsp, 88h
0x180005ad1  mov     rax, cs:__security_cookie
0x180005ad8  xor     rax, rsp
0x180005adb  mov     [rbp+57h+var_50], rax
0x180005adf  xor     r12d, r12d
0x180005ae2  mov     [rbp+57h+var_68], r9
0x180005ae6  mov     r13, rcx
0x180005ae9  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180005aed  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005af1  mov     [rbp+57h+var_70], r12
0x180005af5  mov     [rbp+57h+var_90], r12b
0x180005af9  mov     r15, rdx
0x180005afc  mov     [rbp+57h+var_60], r8
0x180005b00  mov     [rbp+57h+var_80], rdx
0x180005b04  call    cs:__imp_GetSystemTimeAsFileTime
0x180005b0b  nop     dword ptr [rax+rax+00h]
0x180005b10  mov     rcx, [r15+10h]
0x180005b14  lea     rax, [rbp+57h+var_88]
0x180005b18  mov     [rsp+0C0h+var_98], rax
0x180005b1d  lea     edx, [r12+5]
0x180005b22  lea     rax, [rbp+57h+var_78]
0x180005b26  mov     [rbp+57h+var_78], r12
0x180005b2a  mov     r8d, 42020110h
0x180005b30  mov     [rsp+0C0h+var_A0], rax
0x180005b35  mov     [rbp+57h+var_88], r12
0x180005b39  call    WapUriGetTransformedComponentW
0x180005b3e  mov     ebx, eax
0x180005b40  test    eax, eax
0x180005b42  jnz     short loc_180005B5C
0x180005b44  mov     rsi, [rbp+57h+var_88]
0x180005b48  test    rsi, rsi
0x180005b4b  jz      short loc_180005B57
0x180005b4d  mov     rax, [rbp+57h+var_78]
0x180005b51  cmp     word ptr [rax], 2Fh ; '/'
0x180005b55  jz      short loc_180005B7F
0x180005b57  mov     ebx, 0Dh
0x180005b5c  mov     eax, ebx
0x180005b5e  mov     rcx, [rbp+57h+var_50]
0x180005b62  xor     rcx, rsp; StackCookie
0x180005b65  call    __security_check_cookie
0x180005b6a  add     rsp, 88h
0x180005b71  pop     r15
0x180005b73  pop     r14
0x180005b75  pop     r13
0x180005b77  pop     r12
0x180005b79  pop     rdi
0x180005b7a  pop     rsi
0x180005b7b  pop     rbx
0x180005b7c  pop     rbp
0x180005b7d  retn
0x180005b7f  add     r13, 28h ; '('
0x180005b83  mov     rdi, [r13+0]
0x180005b87  jmp     short loc_180005B97
0x180005b89  mov     rsi, [rbp+57h+var_88]
0x180005b8d  xor     r12d, r12d
0x180005b90  mov     r15, [rbp+57h+var_80]
0x180005b94  mov     rdi, [rdi]
0x180005b97  cmp     rdi, r13
0x180005b9a  jz      short loc_180005B5C
0x180005b9c  mov     rcx, [rdi+10h]
0x180005ba0  lea     r8, [rbp+57h+var_70]
0x180005ba4  xor     edx, edx
0x180005ba6  call    WaQueryUriCookiePath
0x180005bab  mov     ebx, eax
0x180005bad  test    eax, eax
0x180005baf  jnz     short loc_180005B5C
0x180005bb1  cmp     [rbp+57h+var_70], rsi
0x180005bb5  ja      short loc_180005B94
0x180005bb7  mov     rdx, [rdi+10h]
0x180005bbb  lea     r8, [rbp+57h+var_90]
0x180005bbf  mov     rcx, [r15+10h]
0x180005bc3  call    WapIsCookieUriMatch
0x180005bc8  mov     ebx, eax
0x180005bca  test    eax, eax
0x180005bcc  jnz     short loc_180005B5C
0x180005bce  cmp     [rbp+57h+var_90], r12b
0x180005bd2  jz      short loc_180005B94
0x180005bd4  lea     r12, [rdi+18h]
0x180005bd8  mov     rsi, [r12]
0x180005bdc  cmp     rsi, r12
0x180005bdf  jz      short loc_180005B89
0x180005be1  mov     rdx, [rbp+57h+var_80]
0x180005be5  lea     r15, [rsi-8]
0x180005be9  mov     rsi, [rsi]
0x180005bec  mov     rcx, r15
0x180005bef  call    WapIsCookieMatch
0x180005bf4  test    byte ptr [r15+38h], 2
0x180005bf9  jnz     short loc_180005C37
0x180005bfb  test    al, al
0x180005bfd  jz      short loc_180005BDC
0x180005bff  lea     rcx, [r15+40h]; lpFileTime1
0x180005c03  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x180005c07  call    cs:__imp_CompareFileTime
0x180005c0e  nop     dword ptr [rax+rax+00h]
0x180005c13  test    eax, eax
0x180005c15  js      short loc_180005BDC
0x180005c17  mov     rcx, [rbp+57h+var_68]
0x180005c1b  lea     r8, [rdi-8]
0x180005c1f  mov     rax, [rbp+57h+var_60]
0x180005c23  mov     rdx, r15
0x180005c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c2b  mov     ebx, eax
0x180005c2d  test    eax, eax
0x180005c2f  jnz     loc_180005B5C
0x180005c35  jmp     short loc_180005BDC
0x180005c37  mov     rcx, [rbp+57h+var_80]
0x180005c3b  mov     rcx, [rcx+10h]
0x180005c3f  mov     rdx, [rcx+38h]
0x180005c43  cmp     dword ptr [rdx], 2
0x180005c46  jnz     short loc_180005BDC
0x180005c48  jmp     short loc_180005BFB
```
