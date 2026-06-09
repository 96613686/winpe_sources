# WapInsertCookie

- ea: `0x180002bf8`
- end: `0x180002dda`
- name: `WapInsertCookie`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004340`

## callees

- `0x18000167c`
- `0x180002760`
- `0x180002840`
- `0x180002ba0`
- `0x180002bf8`
- `0x180002de0`
- `0x180002e9c`
- `0x18006c6f0`
- `0x18006cf54`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002c54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002c54`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002d24`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002da1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002d24`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002da1`

## pseudocode

```c
__int64 __fastcall WapInsertCookie(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v3; // rax
  unsigned __int64 v7; // rdx
  unsigned int CookieLocation; // ebx
  __int64 v9; // rsi
  __int64 v10; // rbp
  __int64 v12; // rdx
  unsigned int v13; // ecx
  __int64 Cookie; // [rsp+30h] [rbp-48h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-40h] BYREF

  v3 = *(_QWORD *)(a2 + 32);
  Cookie = 0;
  SystemTimeAsFileTime = 0;
  if ( v3 >= 0x13F8 )
    return 87;
  v7 = *(_QWORD *)(a2 + 48);
  if ( v7 + v3 > 0x13F8 )
  {
    v13 = 5112 - *(_DWORD *)(a2 + 32);
    if ( v7 > v13 )
      *(_QWORD *)(a2 + 48) = v13;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  CookieLocation = WapFindCookieLocation(a1, a3, &Cookie);
  if ( !CookieLocation )
  {
    v9 = Cookie;
    if ( Cookie )
    {
      Cookie = WapFindCookie(Cookie, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
      v10 = Cookie;
      if ( Cookie )
      {
        if ( *(_DWORD *)(Cookie + 60) == *(_DWORD *)(a2 + 60)
          && ((*(_DWORD *)(a2 + 56) & 0x4000) == 0
           || (*(_BYTE *)(Cookie + 56) & 0x20) == 0
           || (*(_BYTE *)(a2 + 56) & 0x20) != 0) )
        {
          if ( (*(_BYTE *)(a2 + 56) & 1) != 0 && CompareFileTime((const FILETIME *)(a2 + 64), &SystemTimeAsFileTime) < 0 )
            WapDestroyCookie(v9, v10);
          else
            return (unsigned int)WapUpdateCookie(v9, &Cookie, a2);
          return CookieLocation;
        }
        return 87;
      }
    }
    else
    {
      while ( *(_DWORD *)(a1 + 56) >= 0x14u )
        WapDestroyCookieLocation(a1, *(_QWORD *)(a1 + 40) - 8LL);
      CookieLocation = WapCreateCookieLocation(a1, a3, &Cookie);
      if ( CookieLocation )
        return CookieLocation;
      v9 = Cookie;
    }
    if ( CompareFileTime((const FILETIME *)(a2 + 64), &SystemTimeAsFileTime) >= 0 )
    {
      v12 = WapCreateCookie(
              *(void **)(a2 + 24),
              *(_QWORD *)(a2 + 32),
              *(void **)(a2 + 40),
              *(_QWORD *)(a2 + 48),
              *(_DWORD *)(a2 + 56));
      if ( v12 )
      {
        *(_QWORD *)(v12 + 64) = *(_QWORD *)(a2 + 64);
        WapAddCookieToLocation(v9);
      }
      else
      {
        return 8;
      }
    }
  }
  return CookieLocation;
}

```

## disassembly

```asm
0x180002bf8  push    rbx
0x180002bfa  push    rbp
0x180002bfb  push    rsi
0x180002bfc  push    rdi
0x180002bfd  push    r14
0x180002bff  sub     rsp, 50h
0x180002c03  mov     rax, cs:__security_cookie
0x180002c0a  xor     rax, rsp
0x180002c0d  mov     [rsp+78h+var_38], rax
0x180002c12  mov     rax, [rdx+20h]
0x180002c16  mov     rbp, rcx
0x180002c19  mov     ecx, 13F8h
0x180002c1e  mov     [rsp+78h+var_48], 0
0x180002c27  mov     qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002c30  mov     r14, r8
0x180002c33  mov     rdi, rdx
0x180002c36  cmp     rax, rcx
0x180002c39  jnb     loc_180002D60
0x180002c3f  mov     rdx, [rdx+30h]
0x180002c43  add     rax, rdx
0x180002c46  cmp     rax, rcx
0x180002c49  ja      loc_180002D6A
0x180002c4f  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002c54  call    cs:__imp_GetSystemTimeAsFileTime
0x180002c5b  nop     dword ptr [rax+rax+00h]
0x180002c60  lea     r8, [rsp+78h+var_48]
0x180002c65  mov     rdx, r14
0x180002c68  mov     rcx, rbp
0x180002c6b  call    WapFindCookieLocation
0x180002c70  mov     ebx, eax
0x180002c72  test    eax, eax
0x180002c74  jnz     short loc_180002CD2
0x180002c76  mov     rsi, [rsp+78h+var_48]
0x180002c7b  test    rsi, rsi
0x180002c7e  jz      short loc_180002CFA
0x180002c80  mov     r8, [rdi+20h]
0x180002c84  mov     rcx, rsi
0x180002c87  mov     rdx, [rdi+18h]
0x180002c8b  call    WapFindCookie
0x180002c90  mov     [rsp+78h+var_48], rax
0x180002c95  mov     rbp, rax
0x180002c98  test    rax, rax
0x180002c9b  jz      short loc_180002D1B
0x180002c9d  mov     eax, [rdi+3Ch]
0x180002ca0  cmp     [rbp+3Ch], eax
0x180002ca3  jnz     loc_180002D60
0x180002ca9  test    dword ptr [rdi+38h], 4000h
0x180002cb0  jnz     loc_180002D81
0x180002cb6  test    byte ptr [rdi+38h], 1
0x180002cba  jnz     loc_180002D98
0x180002cc0  mov     r8, rdi
0x180002cc3  lea     rdx, [rsp+78h+var_48]
0x180002cc8  mov     rcx, rsi
0x180002ccb  call    WapUpdateCookie
0x180002cd0  mov     ebx, eax
0x180002cd2  mov     eax, ebx
0x180002cd4  mov     rcx, [rsp+78h+var_38]
0x180002cd9  xor     rcx, rsp; StackCookie
0x180002cdc  call    __security_check_cookie
0x180002ce1  add     rsp, 50h
0x180002ce5  pop     r14
0x180002ce7  pop     rdi
0x180002ce8  pop     rsi
0x180002ce9  pop     rbp
0x180002cea  pop     rbx
0x180002ceb  retn
0x180002ced  mov     rdx, [rbp+28h]
0x180002cf1  sub     rdx, 8
0x180002cf5  call    WapDestroyCookieLocation
0x180002cfa  cmp     dword ptr [rbp+38h], 14h
0x180002cfe  mov     rcx, rbp
0x180002d01  jnb     short loc_180002CED
0x180002d03  lea     r8, [rsp+78h+var_48]
0x180002d08  mov     rdx, r14
0x180002d0b  call    WapCreateCookieLocation
0x180002d10  mov     ebx, eax
0x180002d12  test    eax, eax
0x180002d14  jnz     short loc_180002CD2
0x180002d16  mov     rsi, [rsp+78h+var_48]
0x180002d1b  lea     rdx, [rsp+78h+SystemTimeAsFileTime]; lpFileTime2
0x180002d20  lea     rcx, [rdi+40h]; lpFileTime1
0x180002d24  call    cs:__imp_CompareFileTime
0x180002d2b  nop     dword ptr [rax+rax+00h]
0x180002d30  test    eax, eax
0x180002d32  js      short loc_180002CD2
0x180002d34  mov     eax, [rdi+38h]
0x180002d37  mov     r9, [rdi+30h]; size_t
0x180002d3b  mov     r8, [rdi+28h]; void *
0x180002d3f  mov     rdx, [rdi+20h]; Size
0x180002d43  mov     rcx, [rdi+18h]; Src
0x180002d47  mov     [rsp+78h+var_58], eax; int
0x180002d4b  call    WapCreateCookie
0x180002d50  mov     rdx, rax
0x180002d53  test    rax, rax
0x180002d56  jnz     short loc_180002DC5
0x180002d58  lea     ebx, [rax+8]
0x180002d5b  jmp     loc_180002CD2
0x180002d60  mov     ebx, 57h ; 'W'
0x180002d65  jmp     loc_180002CD2
0x180002d6a  sub     ecx, [rdi+20h]
0x180002d6d  mov     eax, ecx
0x180002d6f  cmp     rdx, rax
0x180002d72  jbe     loc_180002C4F
0x180002d78  mov     [rdi+30h], rax
0x180002d7c  jmp     loc_180002C4F
0x180002d81  test    byte ptr [rbp+38h], 20h
0x180002d85  setnz   cl
0x180002d88  test    byte ptr [rdi+38h], 20h
0x180002d8c  setz    al
0x180002d8f  test    al, cl
0x180002d91  jnz     short loc_180002D60
0x180002d93  jmp     loc_180002CB6
0x180002d98  lea     rcx, [rdi+40h]; lpFileTime1
0x180002d9c  lea     rdx, [rsp+78h+SystemTimeAsFileTime]; lpFileTime2
0x180002da1  call    cs:__imp_CompareFileTime
0x180002da8  nop     dword ptr [rax+rax+00h]
0x180002dad  test    eax, eax
0x180002daf  jns     loc_180002CC0
0x180002db5  mov     rdx, rbp
0x180002db8  mov     rcx, rsi
0x180002dbb  call    WapDestroyCookie
0x180002dc0  jmp     loc_180002CD2
0x180002dc5  mov     rax, [rdi+40h]
0x180002dc9  mov     rcx, rsi
0x180002dcc  mov     [rdx+40h], rax
0x180002dd0  call    WapAddCookieToLocation
0x180002dd5  jmp     loc_180002CD2
```
