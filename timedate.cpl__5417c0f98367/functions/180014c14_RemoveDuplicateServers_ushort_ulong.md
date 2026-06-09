# RemoveDuplicateServers(ushort *,ulong)

- ea: `0x180014c14`
- end: `0x180014da7`
- name: `?RemoveDuplicateServers@@YAJPEAGK@Z`
- size: `403`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180014ebc`

## callees

- `0x1800026f8`
- `0x18000893c`
- `0x1800089c8`
- `0x180014c14`
- `0x1800155fc`
- `0x180015700`
- `0x180028f60`
- `0x180028ff0`

## import_xrefs

- `SHLWAPI!PathRemoveBlanksW` at `0x180014d68`
- `SHLWAPI!PathRemoveBlanksW` at `0x180014d68`
- `SHLWAPI!StrChrW` at `0x180014c7c`
- `SHLWAPI!StrChrW` at `0x180014c7c`

## pseudocode

```c
int __fastcall RemoveDuplicateServers(unsigned __int16 *a1)
{
  int result; // eax
  WCHAR *v3; // rbx
  PWSTR v4; // rax
  PWSTR v5; // rdi
  unsigned __int64 v6; // rcx
  const unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // r8
  unsigned int v9; // edi
  const unsigned __int16 *v10; // rdx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszSrch[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszStart[2088]; // [rsp+240h] [rbp+140h] BYREF

  result = StringCchCopyW(pszStart, 0x824u, a1);
  if ( result >= 0 )
  {
    v3 = pszStart;
    while ( 1 )
    {
      v4 = StrChrW(v3, 0x20u);
      v5 = v4;
      if ( !v4 )
        break;
      v6 = v4 - v3 + 1;
      if ( v6 > 0x104 )
        LODWORD(v6) = 260;
      result = StringCchCopyW(pszSrch, (unsigned int)v6, v3);
      if ( result >= 0 )
      {
        result = StringCchCatW(pszSrch, 0x104u, L" ");
        if ( result >= 0 )
        {
          v3 = v5 + 1;
          v8 = v5 + 1;
          v9 = 2084 - (v5 + 1 - pszStart);
          result = StrReplaceToken(pszSrch, v7, v8, v9);
          if ( result >= 0 )
          {
            v12 = 0;
            result = StringCchLengthW(pszSrch, 0x104u, &v12);
            if ( result >= 0 )
            {
              v11 = 2 * v12 - 2;
              if ( v11 >= 0x208 )
                _report_rangecheckfailure();
              *(WCHAR *)((char *)pszSrch + v11) = 0;
              result = StrReplaceToken(pszSrch, v10, v3, v9);
              if ( result >= 0 )
                continue;
            }
          }
        }
      }
      return result;
    }
    PathRemoveBlanksW(pszStart);
    return StringCchCopyW(a1, 0x104u, pszStart);
  }
  return result;
}

```

## disassembly

```asm
0x180014c14  mov     [rsp-8+arg_8], rbx
0x180014c19  mov     [rsp-8+arg_10], rsi
0x180014c1e  push    rbp
0x180014c1f  push    rdi
0x180014c20  push    r14
0x180014c22  lea     rbp, [rsp-11A0h]
0x180014c2a  mov     eax, 12A0h
0x180014c2f  call    _alloca_probe
0x180014c34  sub     rsp, rax
0x180014c37  mov     rax, cs:__security_cookie
0x180014c3e  xor     rax, rsp
0x180014c41  mov     [rbp+11B0h+var_20], rax
0x180014c48  mov     rsi, rcx
0x180014c4b  mov     r8, rcx; unsigned __int16 *
0x180014c4e  lea     rcx, [rbp+11B0h+pszStart]; unsigned __int16 *
0x180014c55  mov     edx, 824h; unsigned __int64
0x180014c5a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014c5f  test    eax, eax
0x180014c61  js      loc_180014D80
0x180014c67  lea     rbx, [rbp+11B0h+pszStart]
0x180014c6e  mov     r14d, 104h
0x180014c74  mov     edx, 20h ; ' '; wMatch
0x180014c79  mov     rcx, rbx; pszStart
0x180014c7c  call    cs:__imp_StrChrW
0x180014c82  mov     rdi, rax
0x180014c85  test    rax, rax
0x180014c88  jz      loc_180014D61
0x180014c8e  mov     rcx, rax
0x180014c91  mov     r8, rbx; unsigned __int16 *
0x180014c94  sub     rcx, rbx
0x180014c97  sar     rcx, 1
0x180014c9a  inc     rcx
0x180014c9d  cmp     rcx, r14
0x180014ca0  cmova   rcx, r14
0x180014ca4  mov     edx, ecx; unsigned __int64
0x180014ca6  lea     rcx, [rsp+12B0h+pszSrch]; unsigned __int16 *
0x180014cab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014cb0  test    eax, eax
0x180014cb2  js      loc_180014D80
0x180014cb8  lea     r8, asc_18002F1D4; " "
0x180014cbf  mov     rdx, r14; unsigned __int64
0x180014cc2  lea     rcx, [rsp+12B0h+pszSrch]; unsigned __int16 *
0x180014cc7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014ccc  test    eax, eax
0x180014cce  js      loc_180014D80
0x180014cd4  lea     rbx, [rdi+2]
0x180014cd8  lea     rax, [rbp+11B0h+pszStart]
0x180014cdf  mov     rcx, rbx
0x180014ce2  sub     rcx, rax
0x180014ce5  mov     r8, rbx; unsigned __int16 *
0x180014ce8  sar     rcx, 1
0x180014ceb  mov     eax, 824h
0x180014cf0  sub     eax, ecx
0x180014cf2  lea     rcx, [rsp+12B0h+pszSrch]; pszSrch
0x180014cf7  mov     r9d, eax; unsigned int
0x180014cfa  mov     edi, eax
0x180014cfc  call    ?StrReplaceToken@@YAJPEBG0PEAGK@Z; StrReplaceToken(ushort const *,ushort const *,ushort *,ulong)
0x180014d01  test    eax, eax
0x180014d03  js      short loc_180014D80
0x180014d05  lea     r8, [rsp+12B0h+var_1290]; unsigned __int64 *
0x180014d0a  mov     [rsp+12B0h+var_1290], 0
0x180014d13  mov     rdx, r14; unsigned __int64
0x180014d16  lea     rcx, [rsp+12B0h+pszSrch]; unsigned __int16 *
0x180014d1b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180014d20  test    eax, eax
0x180014d22  js      short loc_180014D80
0x180014d24  mov     rax, [rsp+12B0h+var_1290]
0x180014d29  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180014d31  cmp     rcx, 208h
0x180014d38  jnb     short loc_180014D5B
0x180014d3a  xor     eax, eax
0x180014d3c  mov     r9d, edi; unsigned int
0x180014d3f  mov     [rsp+rcx+12B0h+pszSrch], ax
0x180014d44  mov     r8, rbx; unsigned __int16 *
0x180014d47  lea     rcx, [rsp+12B0h+pszSrch]; pszSrch
0x180014d4c  call    ?StrReplaceToken@@YAJPEBG0PEAGK@Z; StrReplaceToken(ushort const *,ushort const *,ushort *,ulong)
0x180014d51  test    eax, eax
0x180014d53  jns     loc_180014C74
0x180014d59  jmp     short loc_180014D80
0x180014d5b  call    __report_rangecheckfailure
0x180014d61  lea     rcx, [rbp+11B0h+pszStart]; pszPath
0x180014d68  call    cs:__imp_PathRemoveBlanksW
0x180014d6e  lea     r8, [rbp+11B0h+pszStart]; unsigned __int16 *
0x180014d75  mov     rdx, r14; unsigned __int64
0x180014d78  mov     rcx, rsi; unsigned __int16 *
0x180014d7b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014d80  mov     rcx, [rbp+11B0h+var_20]
0x180014d87  xor     rcx, rsp; StackCookie
0x180014d8a  call    __security_check_cookie
0x180014d8f  lea     r11, [rsp+12B0h+var_10]
0x180014d97  mov     rbx, [r11+28h]
0x180014d9b  mov     rsi, [r11+30h]
0x180014d9f  mov     rsp, r11
0x180014da2  pop     r14
0x180014da4  pop     rdi
0x180014da5  pop     rbp
0x180014da6  retn
```
