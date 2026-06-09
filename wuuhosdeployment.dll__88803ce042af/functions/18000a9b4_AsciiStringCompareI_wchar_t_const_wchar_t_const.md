# AsciiStringCompareI(wchar_t const *,wchar_t const *)

- ea: `0x18000a9b4`
- end: `0x18000aa6b`
- name: `?AsciiStringCompareI@@YAJPEB_W0@Z`
- size: `183`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002edf4`
- `0x18002fbf4`
- `0x180038658`
- `0x180039040`
- `0x1800392ec`
- `0x180039b40`

## callees

- `0x180003950`
- `0x180003974`
- `0x18000a9b4`
- `0x18000b658`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000aa07`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000aa07`

## pseudocode

```c
int __fastcall AsciiStringCompareI(PCNZWCH lpString1, PCNZWCH lpString2, __int64 a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rdx
  int v7; // eax
  const char *v8; // r9
  int v9; // eax
  int v10; // eax
  int lpString2a; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !lpString1 )
  {
    v5 = 162;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
      (const char *)0x80070057LL,
      lpString2a);
    return -2147024809;
  }
  if ( !lpString2 )
  {
    v5 = 163;
    goto LABEL_3;
  }
  v7 = CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1);
  if ( !v7 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xAA,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
             v8);
  v9 = v7 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
      return 0;
    if ( v10 != 1 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xB1,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\StringUtil.cpp",
               (const char *)0xD,
               a5);
  }
  return 1;
}

```

## disassembly

```asm
0x18000a9b4  sub     rsp, 38h
0x18000a9b8  test    rcx, rcx
0x18000a9bb  jnz     short loc_18000A9E3
0x18000a9bd  mov     edx, 0A2h; void *
0x18000a9c2  mov     rcx, [rsp+38h]; this
0x18000a9c7  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000a9ce  mov     r9d, 80070057h; char *
0x18000a9d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a9d9  mov     eax, 80070057h
0x18000a9de  add     rsp, 38h
0x18000a9e2  retn
0x18000a9e3  test    rdx, rdx
0x18000a9e6  jnz     short loc_18000A9EF
0x18000a9e8  mov     edx, 0A3h
0x18000a9ed  jmp     short loc_18000A9C2
0x18000a9ef  or      r9d, 0FFFFFFFFh; cchCount1
0x18000a9f3  mov     r8, rcx; lpString1
0x18000a9f6  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x18000a9fb  mov     [rsp+38h+lpString2], rdx; lpString2
0x18000aa00  lea     edx, [r9+2]; dwCmpFlags
0x18000aa04  lea     ecx, [rdx+7Eh]; Locale
0x18000aa07  call    cs:__imp_CompareStringW
0x18000aa0d  test    eax, eax
0x18000aa0f  jz      short loc_18000AA51
0x18000aa11  sub     eax, 1
0x18000aa14  jz      short loc_18000AA47
0x18000aa16  sub     eax, 1
0x18000aa19  jz      short loc_18000AA40
0x18000aa1b  cmp     eax, 1
0x18000aa1e  jz      short loc_18000AA47
0x18000aa20  mov     rcx, [rsp+38h]; this
0x18000aa25  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000aa2c  mov     r9d, 0Dh; char *
0x18000aa32  mov     edx, 0B1h; void *
0x18000aa37  add     rsp, 38h
0x18000aa3b  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000aa40  xor     eax, eax
0x18000aa42  add     rsp, 38h
0x18000aa46  retn
0x18000aa47  mov     eax, 1
0x18000aa4c  add     rsp, 38h
0x18000aa50  retn
0x18000aa51  mov     rcx, [rsp+38h]; this
0x18000aa56  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000aa5d  mov     edx, 0AAh; void *
0x18000aa62  add     rsp, 38h
0x18000aa66  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
```
