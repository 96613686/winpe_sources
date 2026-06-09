# AsciiStringCompareI(wchar_t const *,wchar_t const *)

- ea: `0x14000c80c`
- end: `0x14000c8c3`
- name: `?AsciiStringCompareI@@YAJPEB_W0@Z`
- size: `183`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000631c`
- `0x1400080bc`

## callees

- `0x140002ac0`
- `0x140003e74`
- `0x14000c508`
- `0x14000c80c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000c85f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000c85f`

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
0x14000c80c  sub     rsp, 38h
0x14000c810  test    rcx, rcx
0x14000c813  jnz     short loc_14000C83B
0x14000c815  mov     edx, 0A2h; void *
0x14000c81a  mov     rcx, [rsp+38h]; this
0x14000c81f  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c826  mov     r9d, 80070057h; char *
0x14000c82c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c831  mov     eax, 80070057h
0x14000c836  add     rsp, 38h
0x14000c83a  retn
0x14000c83b  test    rdx, rdx
0x14000c83e  jnz     short loc_14000C847
0x14000c840  mov     edx, 0A3h
0x14000c845  jmp     short loc_14000C81A
0x14000c847  or      r9d, 0FFFFFFFFh; cchCount1
0x14000c84b  mov     r8, rcx; lpString1
0x14000c84e  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x14000c853  mov     [rsp+38h+lpString2], rdx; lpString2
0x14000c858  lea     edx, [r9+2]; dwCmpFlags
0x14000c85c  lea     ecx, [rdx+7Eh]; Locale
0x14000c85f  call    cs:__imp_CompareStringW
0x14000c865  test    eax, eax
0x14000c867  jz      short loc_14000C8A9
0x14000c869  sub     eax, 1
0x14000c86c  jz      short loc_14000C89F
0x14000c86e  sub     eax, 1
0x14000c871  jz      short loc_14000C898
0x14000c873  cmp     eax, 1
0x14000c876  jz      short loc_14000C89F
0x14000c878  mov     rcx, [rsp+38h]; this
0x14000c87d  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c884  mov     r9d, 0Dh; char *
0x14000c88a  mov     edx, 0B1h; void *
0x14000c88f  add     rsp, 38h
0x14000c893  jmp     ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000c898  xor     eax, eax
0x14000c89a  add     rsp, 38h
0x14000c89e  retn
0x14000c89f  mov     eax, 1
0x14000c8a4  add     rsp, 38h
0x14000c8a8  retn
0x14000c8a9  mov     rcx, [rsp+38h]; this
0x14000c8ae  lea     r8, aCW1SSrcClientL_0; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c8b5  mov     edx, 0AAh; void *
0x14000c8ba  add     rsp, 38h
0x14000c8be  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
```
