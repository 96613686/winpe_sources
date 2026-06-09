# _UnExpandEnvironmentString(ulong (*)(void *,ushort const *,ushort *,ulong),void *,ushort const *,ushort const *,ushort *,uint)

- ea: `0x180003474`
- end: `0x180003558`
- name: `?_UnExpandEnvironmentString@@YAHP6AKPEAXPEBGPEAGK@Z0112I@Z`
- size: `228`
- prototype: `int(unsigned int (*)(void *, const unsigned __int16 *, unsigned __int16 *, unsigned int), void *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002e6c`
- `0x1800030f0`

## callees

- `0x180003400`
- `0x180003474`
- `0x180003560`
- `0x180012550`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003500`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003500`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000350e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000351b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000350e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000351b`

## pseudocode

```c
__int64 __fastcall _UnExpandEnvironmentString(
        __int64 (__fastcall *a1)(void *, const unsigned __int16 *, WCHAR *, __int64),
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        signed int a6)
{
  int v8; // eax
  __int64 v10; // rdi
  int v11; // ebx
  WCHAR String1[264]; // [rsp+30h] [rbp-248h] BYREF

  v8 = a1(a2, a4, String1, 260);
  if ( !v8 )
    return 0;
  v10 = (unsigned int)(v8 - 1);
  if ( CompareStringW(0x800u, 0x10000001u, String1, v8 - 1, a3, v8 - 1) != 2 )
    return 0;
  v11 = lstrlenW(a3) - v10;
  if ( v11 + lstrlenW(a4) >= a6 )
    return 0;
  StringCchCopyW(a5, (unsigned int)a6, a4);
  StringCchCatW(a5, (unsigned int)a6, &a3[v10]);
  return 1;
}

```

## disassembly

```asm
0x180003474  push    rbx
0x180003476  push    rbp
0x180003477  push    rsi
0x180003478  push    rdi
0x180003479  push    r14
0x18000347b  sub     rsp, 250h
0x180003482  mov     rax, cs:__security_cookie
0x180003489  xor     rax, rsp
0x18000348c  mov     [rsp+278h+var_38], rax
0x180003494  mov     r14, [rsp+278h+arg_20]
0x18000349c  mov     rbp, r9
0x18000349f  mov     r10, rdx
0x1800034a2  mov     rsi, r8
0x1800034a5  mov     rax, rcx
0x1800034a8  lea     r8, [rsp+278h+String1]
0x1800034ad  mov     rdx, rbp
0x1800034b0  mov     rcx, r10
0x1800034b3  mov     r9d, 104h
0x1800034b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034be  test    eax, eax
0x1800034c0  jnz     short loc_1800034E2
0x1800034c2  xor     eax, eax
0x1800034c4  mov     rcx, [rsp+278h+var_38]
0x1800034cc  xor     rcx, rsp; StackCookie
0x1800034cf  call    __security_check_cookie
0x1800034d4  add     rsp, 250h
0x1800034db  pop     r14
0x1800034dd  pop     rdi
0x1800034de  pop     rsi
0x1800034df  pop     rbp
0x1800034e0  pop     rbx
0x1800034e1  retn
0x1800034e2  lea     edi, [rax-1]
0x1800034e5  mov     edx, 10000001h; dwCmpFlags
0x1800034ea  mov     [rsp+278h+cchCount2], edi; cchCount2
0x1800034ee  lea     r8, [rsp+278h+String1]; lpString1
0x1800034f3  mov     r9d, edi; cchCount1
0x1800034f6  mov     [rsp+278h+lpString2], rsi; lpString2
0x1800034fb  mov     ecx, 800h; Locale
0x180003500  call    cs:__imp_CompareStringW
0x180003506  cmp     eax, 2
0x180003509  jnz     short loc_1800034C2
0x18000350b  mov     rcx, rsi; lpString
0x18000350e  call    cs:__imp_lstrlenW
0x180003514  mov     ebx, eax
0x180003516  mov     rcx, rbp; lpString
0x180003519  sub     ebx, edi
0x18000351b  call    cs:__imp_lstrlenW
0x180003521  add     eax, ebx
0x180003523  cmp     eax, [rsp+278h+arg_28]
0x18000352a  jge     short loc_1800034C2
0x18000352c  mov     ebx, [rsp+278h+arg_28]
0x180003533  mov     r8, rbp; unsigned __int16 *
0x180003536  mov     edx, ebx; unsigned __int64
0x180003538  mov     rcx, r14; unsigned __int16 *
0x18000353b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003540  lea     r8, [rsi+rdi*2]; unsigned __int16 *
0x180003544  mov     edx, ebx; unsigned __int64
0x180003546  mov     rcx, r14; unsigned __int16 *
0x180003549  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000354e  mov     eax, 1
0x180003553  jmp     loc_1800034C4
```
