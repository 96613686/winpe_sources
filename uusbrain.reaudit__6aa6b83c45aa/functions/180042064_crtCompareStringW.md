# __crtCompareStringW

- ea: `0x180042064`
- end: `0x180042123`
- name: `__crtCompareStringW`
- size: `191`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpLocaleName@<rcx>, wchar_t *Source, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001f6a0`

## callees

- `0x180042064`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800420ef`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800420ef`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18004208c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800420af`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18004208c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800420af`

## pseudocode

```c
int __fastcall _crtCompareStringW(LPCWSTR lpLocaleName, __int64 a2, const wchar_t *a3, int a4, wchar_t *Source, int a6)
{
  int v6; // ebx
  int cchCount2; // eax
  int result; // eax
  int v11; // ebx

  v6 = a4;
  if ( a4 > 0 )
    v6 = wcsnlen(a3, a4);
  cchCount2 = a6;
  if ( a6 > 0 )
    cchCount2 = wcsnlen(Source, a6);
  if ( v6 && cchCount2 )
    return CompareStringEx(lpLocaleName, 0x1000u, a3, v6, Source, cchCount2, 0, 0, 0);
  v11 = v6 - cchCount2;
  result = ((v11 >> 31) & 0xFFFFFFFE) + 3;
  if ( !v11 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x180042064  mov     [rsp+arg_0], rbx
0x180042069  mov     [rsp+arg_8], rbp
0x18004206e  mov     [rsp+arg_10], rsi
0x180042073  push    rdi
0x180042074  sub     rsp, 50h
0x180042078  movsxd  rbx, r9d
0x18004207b  mov     rsi, r8
0x18004207e  mov     rbp, rcx
0x180042081  test    r9d, r9d
0x180042084  jle     short loc_180042095
0x180042086  mov     rdx, rbx; MaxCount
0x180042089  mov     rcx, r8; Source
0x18004208c  call    cs:__imp_wcsnlen
0x180042092  mov     rbx, rax
0x180042095  movsxd  rax, [rsp+58h+arg_28]
0x18004209d  mov     rdi, [rsp+58h+Source]
0x1800420a5  test    eax, eax
0x1800420a7  jle     short loc_1800420B5
0x1800420a9  mov     rdx, rax; MaxCount
0x1800420ac  mov     rcx, rdi; Source
0x1800420af  call    cs:__imp_wcsnlen
0x1800420b5  test    ebx, ebx
0x1800420b7  jz      short loc_1800420F7
0x1800420b9  test    eax, eax
0x1800420bb  jz      short loc_1800420F7
0x1800420bd  mov     [rsp+58h+lParam], 0; lParam
0x1800420c6  mov     r9d, ebx; cchCount1
0x1800420c9  mov     [rsp+58h+lpReserved], 0; lpReserved
0x1800420d2  mov     r8, rsi; lpString1
0x1800420d5  mov     [rsp+58h+lpVersionInformation], 0; lpVersionInformation
0x1800420de  mov     edx, 1000h; dwCmpFlags
0x1800420e3  mov     [rsp+58h+cchCount2], eax; cchCount2
0x1800420e7  mov     rcx, rbp; lpLocaleName
0x1800420ea  mov     [rsp+58h+lpString2], rdi; lpString2
0x1800420ef  call    cs:__imp_CompareStringEx
0x1800420f5  jmp     short loc_18004210E
0x1800420f7  sub     ebx, eax
0x1800420f9  mov     ecx, 2
0x1800420fe  mov     eax, ebx
0x180042100  sar     eax, 1Fh
0x180042103  and     eax, 0FFFFFFFEh
0x180042106  add     eax, 3
0x180042109  test    ebx, ebx
0x18004210b  cmovz   eax, ecx
0x18004210e  mov     rbx, [rsp+58h+arg_0]
0x180042113  mov     rbp, [rsp+58h+arg_8]
0x180042118  mov     rsi, [rsp+58h+arg_10]
0x18004211d  add     rsp, 50h
0x180042121  pop     rdi
0x180042122  retn
```
